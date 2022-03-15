# SSH Server on Ubuntu
    https://help.ubuntu.com/community/SSH/OpenSSH/Configuring
    https://linuxize.com/post/how-to-enable-ssh-on-ubuntu-18-04/
    https://www.cyberciti.biz/faq/ubuntu-linux-install-openssh-server/

    sudo apt update
    sudo apt upgrade

    sudo apt install openssh-server

## Check SSH server status
    sudo systemctl status ssh

    service ssh status
        
## Generate SSH key
    https://www.ssh.com/ssh/keygen

    ssh-keygen -t rsa -b 4096 -C A.Czerwinski@pistacje.net
    
    ssh-keygen -t rsa -b 4096 -C "`whoami`-`date +%Y-%m-%d`" -f ~/.ssh/`whoami`-`date +%Y-%m-%d`
    
## Copy a new SSH public key to the <address.com>
    ssh-copy-id -i ~/.ssh/<filename.pub> <address.com>

## Adding or changing a passphrase
    ssh-keygen -p -f ~/.ssh/id_rsa

## Start the ssh-agent in the background
    eval "$(ssh-agent -s)"

# Find and take a note of your public key fingerprint
    ssh-add -l -E sha256

## Add SSH key
    ssh-add ~/.ssh/id_rsa
    ssh-add -K

## Remove SSH key
    ssh-keygen -f "/home/<user>/.ssh/known_hosts" -R <ip address>

## Testing SSH connection
    ssh -T user@host
    ssh -vT user@host

## Install your public key in a remote machine's authorized_keys 
    ssh-copy-id user@host
    
    cat ~/.ssh/id_rsa.pub | (ssh user@host "cat >> ~/.ssh/authorized_keys")

    cat ~/.ssh/id_rsa.pub > authorized_key
    
    cd ~/.ssh
    nano authorized_key

## Setup SSH config file..
    cat ~/.ssh/config

    Host github-<user>
      User <user>
      AddKeysToAgent yes
      IdentitiesOnly yes
      IdentityFile ~/.ssh/id_rsa
      ForwardAgent yes

## SSH Files
    1. SSH user keys location
      /home/username/.ssh/
    2. SSH system keys location
      /etc/ssh/
    3. SSH configuration files
      /etc/ssh/ssh_config   (Control client behaviour)
      /etc/ssh/sshd_config  (Control server behaviour)

## View the key
    ssh-agent sh -c 'ssh-add; ssh-add -L'

## Debuging
    ssh -v <user@host>

    sudo cat /var/log/auth.log | grep sshd

    sudo /usr/sbin/sshd -d -p 2020

## SSH Troubleshooting
    sudo tcpdump -n -i wlan1 tcp port 22 and host 192.168.1.10

    netstat -rn

    less /etc/ssh/sshd_config

## SSH FS - mount remote file system
    https://www.digitalocean.com/community/tutorials/how-to-use-sshfs-to-mount-remote-file-systems-over-ssh

    sudo apt-get install sshfs
