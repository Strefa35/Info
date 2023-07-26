# Install WSL
  https://docs.microsoft.com/en-us/windows/wsl/install

  From PowerShell:
    wsl --install
    
    wsl --install -d <DistroName> 
    
## List available distros
  wsl --list --online

## Check distro & IP
  From PowerShell:
    wsl -l -v
    wsl -d "Ubuntu-20.04" hostname -I

## Static IP
  If you don't want /etc/hosts, /etc/resolv.conf to change after restart, you can create /etc/wsl.conf
    [network]
    generateHosts = false
    generateResolvConf = false


    In Windows 10, run CMD or Powershell with administrator privilege, and then execute the following two commands:

      :: Add an IP address in Ubuntu-20.04, 192.168.50.2, named eth0:1
      wsl -d Ubuntu-20.04 -u root ip addr add 192.168.50.2/24 broadcast 192.168.50.255 dev eth0 label eth0:1

      :: Add an IP address in Win10, 192.168.50.20
      netsh interface ip add address "vEthernet (WSL)" 192.168.50.20 255.255.255.0

    In the future, you will use 192.168.50.2 when you access Ubuntu, and 192.168.50.20 when you access Win10.
    You can save the above two lines of commands as a .bat file, and then put it into the boot area, and let it execute automatically every time.

## Network problem (Unable to ping host machine)
  https://github.com/microsoft/WSL/issues/4171
  
# SSH server
  https://www.illuminiastudios.com/dev-diaries/ssh-on-windows-subsystem-for-linux/

  sudo apt install openssh-server
  
  sudo vi /etc/ssh/sshd_config
    PasswordAuthentication yes
    AllowUsers yourusername
    
## Start or restart the SSH service    
    service ssh status
    
    sudo service ssh start
    sudo service ssh --full-restart

## Start SSH agent

    eval `ssh-agent -s`; ssh-add ~/.ssh/slb/id_rsa
    
## Start SSH service without password    
  sudo visudo
    Find: %sudo ALL=NOPASSWD: /usr/sbin/sshd
    Past after: %sudo  ALL=(ALL:ALL) ALL

# Docker on WSL
	https://docs.docker.com/desktop/windows/wsl/
	https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-containers

## SSH FS - mount remote file system
    https://www.digitalocean.com/community/tutorials/how-to-use-sshfs-to-mount-remote-file-systems-over-ssh

    https://github.com/winfsp/winfsp/releases
    https://github.com/winfsp/sshfs-win

     \\sshfs\user@host
     
# Setup after WSL started

    service ssh status
    
    sudo service ssh start
    sudo service ssh --full-restart
    
    eval `ssh-agent -s`; ssh-add ~/.ssh/slb_20220412/id_rsa

# Develpp in remote containers using VS Code
    https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-containers
    
    
# Python

    sudo apt-get install python python3

	sudo apt-get install python-pip python3-pip


    update-alternatives --install /usr/bin/python python /usr/bin/python3.5 1
    update-alternatives --install /usr/bin/python python /usr/bin/python2.7 2
    update-alternatives --config python


