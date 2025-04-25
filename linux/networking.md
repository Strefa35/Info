
# OSI Model
  Open Systems Interconnect

# Transport Layer Adressing

    Use port numbers.

  ## Port numbers
  ```
        0 -  1023 - well known
     1024 - 49151 - registered
    49152 - 65535 - temporary (ephemeral)

    80      HTTP
    443     HTTPs
    20, 21  FTP
    22      SSH
    23      Telnet
```
# Application Layer Protocol Dependency
```
   | HTTP | HTTPs |   FTP  | SFTP | SMB |  POP3   |   IMAP  |  SMTP  | LDAPs |   LDAP  | TFTP |
   |  80  | 443   | 20, 21 |  22  | 445 | 110/995 | 143/993 | 25/587 |  636  |   389   | 69   |
   |                               TCP                                       | TCP/UDP | UDP  |
   |                                         IP                                               |
```
# Transport Layer Protocol

  TCP - Transport Control Protocol
  UDP - User Datagram Protocol


# Port numbers
      0 -  1023 - well known
   1024 - 49151 - registered
  49152 - 65535 - temporary (ephemeral)


# Classful Addressing
```
          | Class |        IP Range
   Unicast|   A   | 0.0.0.0       127.255.255.255
          |   B   | 128.0.0.0     191.255.255.255
   _______|   C   | 192.0.0.0     223.255.255.255 ____
 Multicast|   D   | 224.0.0.0     239.255.255.255
          |   E   | 240.0.0.0     255.255.255.255
```

# Address Types

  - Network Address   - identifier for a group of devices
  - Broadcast Address - identifier for all devices on a network
  - Host Address      - identifies unique device on a network

# Private IP Address
```
   10.0.0.0   |  10.255.255.255  |  10.0.0.0/8
  172.16.0.0  | 172.31.255.255   | 172.16.0.0/12
  192.168.0.0 | 192.168.255.255  | 192.168.0.0/16
```
  ## APIPA - Avoid this
    169.254.0.0/16

  ## Loopback Address
    127.0.0.1

