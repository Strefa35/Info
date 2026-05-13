# WSL — Windows Subsystem for Linux

Reference: <https://docs.microsoft.com/en-us/windows/wsl/install>

## Install

```powershell
wsl --install
wsl --install -d <DistroName>
```

## List available distros

```powershell
wsl --list --online
```

## Check distro & IP

```powershell
wsl -l -v
wsl -d "Ubuntu-20.04" hostname -I
```

## Static IP

To prevent `/etc/hosts` and `/etc/resolv.conf` from regenerating on restart, create `/etc/wsl.conf`:

```ini
[network]
generateHosts = false
generateResolvConf = false
```

Then in PowerShell (as Administrator):

```powershell
# Add IP address 192.168.50.2 to Ubuntu-20.04 on eth0:1
wsl -d Ubuntu-20.04 -u root ip addr add 192.168.50.2/24 broadcast 192.168.50.255 dev eth0 label eth0:1

# Add IP address 192.168.50.20 to Windows
netsh interface ip add address "vEthernet (WSL)" 192.168.50.20 255.255.255.0
```

Save these as a `.bat` file and add it to startup to run automatically.

## Network problem (unable to ping host machine)

<https://github.com/microsoft/WSL/issues/4171>

## OpenSSH Server

Reference: <https://ubuntu.com/server/docs/openssh-server>

```bash
sudo apt install openssh-server

sudo vi /etc/ssh/sshd_config
# Set:
#   PasswordAuthentication yes
#   AllowUsers yourusername
```

### Start / restart SSH

```bash
service ssh status
sudo service ssh start
sudo service ssh --full-restart
```

### Start SSH agent

```bash
eval `ssh-agent -s`
ssh-add ~/.ssh/slb/id_rsa
```

### Start SSH service without password prompt

```bash
sudo visudo
# Find:   %sudo  ALL=(ALL:ALL) ALL
# Paste after:  %sudo ALL=NOPASSWD: /usr/sbin/sshd
```

## Docker on WSL

- <https://docs.docker.com/desktop/windows/wsl/>
- <https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-containers>

## SSHFS — mount remote filesystem

Reference: <https://www.digitalocean.com/community/tutorials/how-to-use-sshfs-to-mount-remote-file-systems-over-ssh>

- [WinFsp](https://github.com/winfsp/winfsp/releases)
- [sshfs-win](https://github.com/winfsp/sshfs-win)

```
\\sshfs\user@host
```

## Setup after WSL start

```bash
service ssh status
sudo service ssh start
sudo service ssh --full-restart

eval `ssh-agent -s`
ssh-add ~/.ssh/slb_20220412/id_rsa
```

## Develop in remote containers using VS Code

<https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-containers>

## Python

```bash
sudo apt-get install python3 python3-pip

update-alternatives --install /usr/bin/python python /usr/bin/python3.5 1
update-alternatives --install /usr/bin/python python /usr/bin/python2.7 2
update-alternatives --config python
```
