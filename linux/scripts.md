# Base64 String to Hex
    echo -n "AAAANHBzc2gAAAAA7e+LqXnWSs6jyCfc1R0h7QAAABQIARIQnrQFDeRLSAKTLifXUIPiZg==" | base64 -d -i | hexdump -v -e '/1 "0x%02X, "' > 1.hex
    
    echo -n "AAAAW3Bzc2gAAAAA7e+LqXnWSs6jyCfc1R0h7QAAADsIARIQ62dqu8s0Xpa7z2FmMPGj2hoNd2lkZXZpbmVfdGVzdCIQZmtqM2xqYVNkZmFsa3IzaioCSEQyAA==" | base64 -d -i | hexdump -v -e '/1 "0x%02X, "' > 2.hex

# 