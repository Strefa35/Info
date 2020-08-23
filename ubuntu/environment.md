
sudo vi /etc/environment


# How to Install GCC Compiler on Ubuntu 18.04
    https://linuxize.com/post/how-to-install-gcc-compiler-on-ubuntu-18-04/

    sudo apt install build-essential
    sudo apt-get install manpages-dev
    gcc --version
    
    sudo apt install software-properties-common
    sudo add-apt-repository ppa:ubuntu-toolchain-r/test

    sudo apt install gcc-7 g++-7 gcc-8 g++-8 gcc-9 g++-9
    
    sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-9 90 --slave /usr/bin/g++ g++ /usr/bin/g++-9 --slave /usr/bin/gcov gcov /usr/bin/gcov-9
    sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-8 80 --slave /usr/bin/g++ g++ /usr/bin/g++-8 --slave /usr/bin/gcov gcov /usr/bin/gcov-8
    sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-7 70 --slave /usr/bin/g++ g++ /usr/bin/g++-7 --slave /usr/bin/gcov gcov /usr/bin/gcov-7
    
    sudo update-alternatives --config gcc
    

# How to Install Java on Ubuntu 18.04
    https://linuxize.com/post/install-java-on-ubuntu-18-04/
    
    sudo apt update
    java -version
    sudo apt install default-jre
    
    sudo update-alternatives --config java
    
    
# Python 2 & 3 together

    sudo apt update
    sudo apt install software-properties-common
    sudo add-apt-repository ppa:deadsnakes/ppa
    sudo apt install python3.8
    sudo apt install python3.9

    sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.8 1
    sudo update-alternatives --install /usr/bin/python python /usr/bin/python2.9 2

    sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.6 1
    sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.7 2
    sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.8 3
    sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.9 4
    sudo update-alternatives --install /usr/bin/python python /usr/bin/python2.7 10

    sudo update-alternatives --config python

# How to permanently set $PATH variable

    https://hackprogramming.com/2-ways-to-permanently-set-path-variable-in-ubuntu/

# NFS
    https://help.ubuntu.com/community/SettingUpNFSHowTo
    
    dpkg -l | grep nfs-kernel-server
    
    sudo apt-get install nfs-kernel-server nfs-common

    ## Server side
      sudo mkdir /home/pub
      sudo mkdir /home/pub/nfs
      sudo chown nobody:nogroup /home/pub
      sudo chown nobody:nogroup /home/pub/nfs
      sudo chmod -R 777 pub

      sudo gedit /etc/exports

          /home/pub/nfs  192.168.1.0/22  (rw,sync,no_subtree_check)
          /home/pub/nfs  192.168.1.231   (rw,sync,no_subtree_check)

      sudo exportfs -a
      sudo systemctl restart nfs-kernel-server
      
    ## Tests
        
      touch file1.txt file2.txt file3.txt
      
    ## Client side
      
      mkdir -p /tmp/nfs;mount -t nfs -o nolock 192.168.1.102:/home/pub/nfs /tmp/nfs

    ## Tests

# TFTP

  ## Install
    https://help.ubuntu.com/community/TFTP
    https://askubuntu.com/questions/201505/how-do-i-install-and-run-a-tftp-server

    sudo apt install tftpd-hpa
    
  ## Configure  
    
    sudo systemctl status tftpd-hpa
    
    sudo nano /etc/default/tftpd-hpa
    
      TFTP_USERNAME="tftp"
      TFTP_DIRECTORY="/home/pub/tftp"
      TFTP_ADDRESS=":69"
      TFTP_OPTIONS="--secure --create"
    
    sudo mkdir /home/pub/tftp
    sudo chown tftp:tftp /home/pub/tftp

    sudo systemctl status tftpd-hpa
    
  ## Restart:
    sudo service tftpd-hpa restart    

  ## Test
    tftp 192.168.1.102
    get test.txt

# NGinx

  ## Install
    https://www.cyberciti.biz/faq/install-and-configure-nginx-on-ubuntu-linux-18-04-lts/
    https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-18-04

    sudo apt install nginx

  ## Configure

    sudo nano /etc/nginx/nginx.conf


  ## Enable Nginx server at boot time using the systemctl command:
    $ sudo systemctl enable nginx

  ## Start Nginx server using the systemctl command:
    $ sudo systemctl start nginx

  ## Restart Nginx server using the systemctl command:
    $ sudo systemctl restart nginx

  ## Stop Nginx server using the systemctl command:
    $ sudo systemctl stop nginx

  ## Reload Nginx server using the systemctl command:
    $ sudo systemctl reload nginx

  ## Get status of Nginx server using the systemctl command:
    $ sudo systemctl status nginx

