# SSH — Linux

## Install SSH server

Reference:

- <https://help.ubuntu.com/community/SSH/OpenSSH/Configuring>
- <https://linuxize.com/post/how-to-enable-ssh-on-ubuntu-18-04/>
- <https://www.cyberciti.biz/faq/ubuntu-linux-install-openssh-server/>

```bash
sudo apt update && sudo apt upgrade
sudo apt install openssh-server
```

## Check SSH server status

```bash
sudo systemctl status ssh
service ssh status
```

## Generate SSH key

Reference: <https://www.ssh.com/ssh/keygen>

```bash
ssh-keygen -t rsa -b 4096 -C A.Czerwinski@pistacje.net

ssh-keygen -t rsa -b 4096 -C "`whoami`-`date +%Y-%m-%d`" \
  -f ~/.ssh/`whoami`-`date +%Y-%m-%d`
```

## Copy public key to remote host

```bash
ssh-copy-id -i ~/.ssh/<filename.pub> <address.com>
```

## Change passphrase

```bash
ssh-keygen -p -f ~/.ssh/id_rsa
```

## SSH agent

```bash
eval "$(ssh-agent -s)"    # start agent
ssh-add ~/.ssh/id_rsa     # add key
ssh-add -K                # add key to keychain (macOS)
ssh-add -l -E sha256      # list keys (with fingerprints)
```

## Remove a known host entry

```bash
ssh-keygen -f "/home/<user>/.ssh/known_hosts" -R <ip-address>
```

## Test connection

```bash
ssh -T user@host
ssh -vT user@host
```

## Install public key on remote machine

```bash
ssh-copy-id user@host

# Alternative
cat ~/.ssh/id_rsa.pub | ssh user@host "cat >> ~/.ssh/authorized_keys"
```

## SSH config file

```
# ~/.ssh/config
Host github-<user>
  User <user>
  AddKeysToAgent yes
  IdentitiesOnly yes
  IdentityFile ~/.ssh/id_rsa
  ForwardAgent yes
```

## SSH file locations

| Path | Description |
|------|-------------|
| `~/.ssh/` | User SSH keys |
| `/etc/ssh/` | System SSH keys |
| `/etc/ssh/ssh_config` | Client configuration |
| `/etc/ssh/sshd_config` | Server configuration |

## View loaded key

```bash
ssh-agent sh -c 'ssh-add; ssh-add -L'
```

## Debugging

```bash
ssh -v user@host

sudo cat /var/log/auth.log | grep sshd

sudo /usr/sbin/sshd -d -p 2020
```

## Troubleshooting

```bash
sudo tcpdump -n -i wlan1 tcp port 22 and host 192.168.1.10
netstat -rn
less /etc/ssh/sshd_config
```

## SSHFS — mount remote filesystem

Reference: <https://www.digitalocean.com/community/tutorials/how-to-use-sshfs-to-mount-remote-file-systems-over-ssh>

```bash
sudo apt-get install sshfs
```
