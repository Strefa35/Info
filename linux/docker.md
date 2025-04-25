# Docker install & setup
    https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04
    https://docs.docker.com/engine/install/ubuntu/
    
    Compose is a tool for defining and running multi-container Docker applications. 
    With Compose, you use a YAML file to configure your application’s services. 
    Then, with a single command, you create and start all the services from your configuration. 
    
# Docker HUB
    https://hub.docker.com
    
# Play with Docker    
    https://labs.play-with-docker.com/

# Docker network
    docker network ls
    
    docker network create learning
    
    docker run --rm -ti --net learning --name catserver ubuntu:14.04 bash
    1# ping catserver
    1# ping dogserver
    
    docker run --rm -ti --net learning --name dogserver ubuntu:14.04 bash
    1# ping catsserver
    1# ping dogserver

    2# nc -lp 1234
    1# nc dogserver 1234
    
    docker network create catsonly
    docker network connect catsonly catserver
    
    docker run --rm -ti --net catsonly --name bobcatserver ubuntu:14.04 bash
    3# ping catserver
    3# ping dogserver
    
# Legacy Linking

    1) $ docker run --rm -ti -e SECRET=theinternetlovescats --name catserver ubuntu:14.04 bash
    1) # nc -lp 1234
    
    1) # nc dogserver 4321
    
    1) evn
    
    
    2) $ docker run --rm -ti --link catserver --name dogserver ubuntu:14.04 bash
    2) # nc catserver 1234
    
    2) nc -lp 4321
    
    2) env

# Listing images

    docker images
    
    docker ps -l --format=$FORMAT
    
    docker commit <id> <my-images>
    docker commit <id> <my-images:v2.1>
    
# Volumes - sharing data between containers   

  ## Sharing Data[folders] with the Host
  
    mkdir example
    pwd
    $ docker run -ti -v ${PWD}/example:/shared-folder ubuntu bash
        ls /shared-folder/
        touch /shared-folder/my-data
        exit
    $ ls example/
    
  ## Shering Data between Containers 

    on 1st terminal:
      $ docker run -ti -v /shared-folder ubuntu bash
        echo hello > /shared-data/data-file

    on 2nd terminal:  
      $ docker ps -l --format=$FORMAT
      $ docker run -ti --volumes-from <name> ubuntu bash
        ls /shared-data/
        echo more > /shared-data/more-data
      ls /shared-data/
     
    on 1st terminal:
        exit
    
    on 2st terminal:
        ls /shared-data/

    on 1st terminal:
      $ docker ps 
      $ docker run -ti --volumes-from <name> ubuntu bash
        ls /shared-data/
  
# Docker Registries
    
    ## Finding images
    
      docker search ubuntu
    
# Dockerfile

    docker build -t <name-of-result> .
    
    ## Create Dockerfile
      mkdir example
      cd example
      ls
      nano Dockerfile
        FROM busybox
        RUN echo "building simple docker image."
        CMD echo "hello container"
        
    ## Build image    
      docker build -t hello .

    ## Run created image
      docker run --rm hello
      
    ## Installing a Program with Docker Build
      nano Dockerfile
        FROM debian:sid
        RUN apt-get -y update
        RUN apt-get install nano
        CMD ["/bin/nano", "/tmp/notes"]
      
      docker build -t example/nanoer .
      
      docker run --rm -ti example/nanoer
      
    ## Adding a File through Docker Build
      Put this in a Dockerfile
        FROM example/nanoer
        ADD notes.txt /notes.txt
        CMD ["/bin/nano", "/notes.txt"]
        
      nano Notes.txt
        TODO: learn more about Dockerfile
        
      docker build -t example/notes .
      
      
# Docker socket inside the container

  ```docker run -ti --rm -v /var/run/docker.sock:/var/run/docker.sock docker sh```
  
  ```docker info```
  
  ```docker run -ti --rm ubuntu bash```
  
  
# Networking and namespaces
  ```$ docker run -ti --net=host ubuntu:16.04 bash```
  
  ```$ docker run -ti --rm --net=host --privileged=true ubuntu bash```
  
  ```sudo iptables -n -L -t nat```
  
  ```$ docker inspect --format '{{.State.Pid}}' hello```
  
# Storage

    ```mount -o bind other-work work```
    
# Registries in detail

  ```$ docker run -d -p 5000:5000 --restart=always --name registry registry:2```
  ```$ docker tag ubuntu:14.04 localhost:5000/mycompany/my-ubuntu:99```
  ```$ docker push localhost:5000/mycompany/my-ubuntu:99```
    
  ```$ docker images```
  
  ```$ docker save -o my-images.tar.gz debian:sid busybox ubuntu:14.04```
  
  ```$ docker rmi debian:sid busybox ubuntu:14.04```
  
  ```$ docker load -i my-images.tar.gz```
  
