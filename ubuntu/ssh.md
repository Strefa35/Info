# SSH Server on Ubuntu
    https://help.ubuntu.com/community/SSH/OpenSSH/Configuring
    https://linuxize.com/post/how-to-enable-ssh-on-ubuntu-18-04/
    https://www.cyberciti.biz/faq/ubuntu-linux-install-openssh-server/

    sudo apt update
    sudo apt upgrade

    sudo apt install openssh-server

    sudo systemctl status ssh

## Generate SSH key
    https://www.ssh.com/ssh/keygen

    ssh-keygen -t rsa -b 4096 -C A.Czerwinski@pistacje.net

## 
    ssh -T git@github.com

## SSH FS - mount remote file system
    https://www.digitalocean.com/community/tutorials/how-to-use-sshfs-to-mount-remote-file-systems-over-ssh

    sudo apt-get install sshfs


