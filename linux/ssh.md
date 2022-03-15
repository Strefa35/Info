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

## Adding or changing a passphrase
    ssh-keygen -p -f ~/.ssh/id_rsa

## Start the ssh-agent in the background
    eval "$(ssh-agent -s)"

# Find and take a note of your public key fingerprint
    ssh-add -l -E sha256

## Add SSH key
    ssh-add ~/.ssh/id_rsa
    ssh-add -K

## Testing SSH connection
    ssh -T git@github.com

## SSH FS - mount remote file system
    https://www.digitalocean.com/community/tutorials/how-to-use-sshfs-to-mount-remote-file-systems-over-ssh

    sudo apt-get install sshfs
