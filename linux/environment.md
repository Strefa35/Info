# Linux Environment

## System-wide environment variables

```bash
sudo vi /etc/environment
```

## Install GCC on Ubuntu

Reference: <https://linuxize.com/post/how-to-install-gcc-compiler-on-ubuntu-18-04/>

```bash
sudo apt install build-essential
sudo apt-get install manpages-dev
gcc --version

sudo apt install software-properties-common
sudo add-apt-repository ppa:ubuntu-toolchain-r/test

sudo apt install gcc-7 g++-7 gcc-8 g++-8 gcc-9 g++-9

sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-9 90 \
  --slave /usr/bin/g++ g++ /usr/bin/g++-9 \
  --slave /usr/bin/gcov gcov /usr/bin/gcov-9

sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-8 80 \
  --slave /usr/bin/g++ g++ /usr/bin/g++-8 \
  --slave /usr/bin/gcov gcov /usr/bin/gcov-8

sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-7 70 \
  --slave /usr/bin/g++ g++ /usr/bin/g++-7 \
  --slave /usr/bin/gcov gcov /usr/bin/gcov-7

sudo update-alternatives --config gcc
```

## Install Java on Ubuntu

Reference: <https://linuxize.com/post/install-java-on-ubuntu-18-04/>

```bash
sudo apt update
java -version
sudo apt install default-jre
sudo update-alternatives --config java
```

## Python — multiple versions

```bash
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt install python3.8 python3.9

sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.6 1
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.7 2
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.8 3
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.9 4
sudo update-alternatives --install /usr/bin/python python /usr/bin/python2.7 10

sudo update-alternatives --config python
```

## Permanently set $PATH

Reference: <https://hackprogramming.com/2-ways-to-permanently-set-path-variable-in-ubuntu/>

## NFS

Reference: <https://help.ubuntu.com/community/SettingUpNFSHowTo>

```bash
dpkg -l | grep nfs-kernel-server
sudo apt-get install nfs-kernel-server nfs-common
```

### Server side

```bash
sudo mkdir -p /home/pub/nfs
sudo chown nobody:nogroup /home/pub /home/pub/nfs
sudo chmod -R 777 /home/pub

sudo gedit /etc/exports
# Add:
#   /home/pub/nfs  192.168.1.0/24  (rw,sync,no_subtree_check)
#   /home/pub/nfs  192.168.1.231   (rw,sync,no_subtree_check)

sudo exportfs -a
sudo systemctl restart nfs-kernel-server
```

### Client side

```bash
mkdir -p /tmp/nfs
mount -t nfs -o nolock 192.168.1.102:/home/pub/nfs /tmp/nfs
```

## TFTP

Reference:

- <https://help.ubuntu.com/community/TFTP>
- <https://askubuntu.com/questions/201505/how-do-i-install-and-run-a-tftp-server>

### Install

```bash
sudo apt install tftpd-hpa
```

### Configure

```bash
sudo nano /etc/default/tftpd-hpa
```

```ini
TFTP_USERNAME="tftp"
TFTP_DIRECTORY="/home/pub/tftp"
TFTP_ADDRESS=":69"
TFTP_OPTIONS="--secure --create"
```

```bash
sudo mkdir /home/pub/tftp
sudo chown tftp:tftp /home/pub/tftp
sudo systemctl status tftpd-hpa
```

### Restart

```bash
sudo service tftpd-hpa restart
```

### Test

```bash
tftp 192.168.1.102
get test.txt
```

## Nginx

Reference:

- <https://www.cyberciti.biz/faq/install-and-configure-nginx-on-ubuntu-linux-18-04-lts/>
- <https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-18-04>

### Install

```bash
sudo apt install nginx
```

### Configure

```bash
sudo nano /etc/nginx/nginx.conf
```

### Manage service

```bash
sudo systemctl enable nginx    # enable at boot
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx
sudo systemctl reload nginx
sudo systemctl status nginx
```
