# Networking

## OSI Model

Open Systems Interconnect.

## Transport Layer Addressing

Uses port numbers.

### Well-known ports

```
    0 –  1023  well known
 1024 – 49151  registered
49152 – 65535  temporary (ephemeral)

 80       HTTP
443       HTTPS
20, 21    FTP
22        SSH
23        Telnet
```

## Application Layer Protocol Dependency

| Protocol | HTTP | HTTPS | FTP    | SFTP | SMB | POP3    | IMAP    | SMTP   | LDAPS | LDAP | TFTP |
|----------|------|-------|--------|------|-----|---------|---------|--------|-------|------|------|
| Port     | 80   | 443   | 20, 21 | 22   | 445 | 110/995 | 143/993 | 25/587 | 636   | 389  | 69   |
| Transport | TCP | TCP   | TCP    | TCP  | TCP | TCP     | TCP     | TCP    | TCP   | TCP/UDP | UDP |

## Transport Layer Protocol

| Protocol | Full name |
|----------|-----------|
| TCP | Transmission Control Protocol |
| UDP | User Datagram Protocol |

## Port Numbers

```
    0 –  1023  well known
 1024 – 49151  registered
49152 – 65535  temporary (ephemeral)
```

## Classful Addressing

| Class | Type | IP Range |
|-------|------|----------|
| A | Unicast | 0.0.0.0 – 127.255.255.255 |
| B | Unicast | 128.0.0.0 – 191.255.255.255 |
| C | Unicast | 192.0.0.0 – 223.255.255.255 |
| D | Multicast | 224.0.0.0 – 239.255.255.255 |
| E | Reserved | 240.0.0.0 – 255.255.255.255 |

## Address Types

| Type | Description |
|------|-------------|
| Network Address | Identifier for a group of devices |
| Broadcast Address | Identifier for all devices on a network |
| Host Address | Identifies a unique device on a network |

## Private IP Ranges

| Range | Start | End | CIDR |
|-------|-------|-----|------|
| Class A | 10.0.0.0 | 10.255.255.255 | /8 |
| Class B | 172.16.0.0 | 172.31.255.255 | /12 |
| Class C | 192.168.0.0 | 192.168.255.255 | /16 |

### Special addresses

| Address | Purpose |
|---------|---------|
| 169.254.0.0/16 | APIPA — avoid this |
| 127.0.0.1 | Loopback |
