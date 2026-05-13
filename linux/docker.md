# Docker

## Install & Setup

Reference:

- <https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04>
- <https://docs.docker.com/engine/install/ubuntu/>

Compose is a tool for defining and running multi-container Docker applications.
Use a YAML file to configure services, then start everything with a single command.

## Docker Hub

<https://hub.docker.com>

## Play with Docker

<https://labs.play-with-docker.com/>

## Docker Network

```bash
docker network ls
docker network create learning

# Terminal 1 — catserver
docker run --rm -ti --net learning --name catserver ubuntu:14.04 bash
# ping catserver
# ping dogserver

# Terminal 2 — dogserver
docker run --rm -ti --net learning --name dogserver ubuntu:14.04 bash
# nc -lp 1234

# Terminal 1
# nc dogserver 1234

# Separate network for cats only
docker network create catsonly
docker network connect catsonly catserver

# Terminal 3
docker run --rm -ti --net catsonly --name bobcatserver ubuntu:14.04 bash
# ping catserver    ✓
# ping dogserver    ✗ (not on this network)
```

## Legacy Linking

```bash
# Terminal 1 — catserver
docker run --rm -ti -e SECRET=theinternetlovescats --name catserver ubuntu:14.04 bash
# nc -lp 1234
# nc dogserver 4321
# env

# Terminal 2 — dogserver
docker run --rm -ti --link catserver --name dogserver ubuntu:14.04 bash
# nc catserver 1234
# nc -lp 4321
# env
```

## Images

```bash
docker images

docker ps -l --format=$FORMAT

docker commit <id> <my-image>
docker commit <id> <my-image:v2.1>
```

## Volumes — Sharing Data

### Share folder with the host

```bash
mkdir example
docker run -ti -v ${PWD}/example:/shared-folder ubuntu bash
# touch /shared-folder/my-data
ls example/
```

### Share data between containers

```bash
# Terminal 1
docker run -ti -v /shared-folder ubuntu bash
# echo hello > /shared-data/data-file

# Terminal 2
docker ps -l --format=$FORMAT
docker run -ti --volumes-from <name> ubuntu bash
# ls /shared-data/
# echo more > /shared-data/more-data
```

## Docker Registries

```bash
docker search ubuntu
```

## Dockerfile

```bash
docker build -t <name-of-result> .
```

### Minimal image

```dockerfile
FROM busybox
RUN echo "building simple docker image."
CMD echo "hello container"
```

```bash
docker build -t hello .
docker run --rm hello
```

### Install a program

```dockerfile
FROM debian:sid
RUN apt-get -y update
RUN apt-get install nano
CMD ["/bin/nano", "/tmp/notes"]
```

```bash
docker build -t example/nanoer .
docker run --rm -ti example/nanoer
```

### Add a file

```dockerfile
FROM example/nanoer
ADD notes.txt /notes.txt
CMD ["/bin/nano", "/notes.txt"]
```

```bash
docker build -t example/notes .
```

## Docker socket inside container

```bash
docker run -ti --rm -v /var/run/docker.sock:/var/run/docker.sock docker sh
docker info
docker run -ti --rm ubuntu bash
```

## Networking and namespaces

```bash
docker run -ti --net=host ubuntu:16.04 bash
docker run -ti --rm --net=host --privileged=true ubuntu bash

sudo iptables -n -L -t nat
docker inspect --format '{{.State.Pid}}' hello
```

## Storage

```bash
mount -o bind other-work work
```

## Registries in detail

```bash
docker run -d -p 5000:5000 --restart=always --name registry registry:2
docker tag ubuntu:14.04 localhost:5000/mycompany/my-ubuntu:99
docker push localhost:5000/mycompany/my-ubuntu:99

docker images

docker save -o my-images.tar.gz debian:sid busybox ubuntu:14.04
docker rmi debian:sid busybox ubuntu:14.04
docker load -i my-images.tar.gz
```
