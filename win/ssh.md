# SSH — Windows 10

## Generate SSH key

Reference: <https://www.ssh.com/ssh/keygen>

```powershell
ssh-keygen -t rsa -b 4096 -C A.Czerwinski@pistacje.net
```

## SSHFS — mount remote filesystem

Reference: <https://www.digitalocean.com/community/tutorials/how-to-use-sshfs-to-mount-remote-file-systems-over-ssh>

```bash
sudo apt-get install sshfs    # in WSL
```
