> using nmap with sudo makes different operations from without sudo
#### Ping scan
```bash
nmap -sn 192.168.1.0/24
# used to identify running hosts in a network
```

#### SYN scan
```bash
nmap -sS 192.168.1.0/24
# used to scan a network by making 2 TCP handshakes only and your IP address won't be logged but this process makes your connection weird to the server
```

#### TCP scan
```bash
nmap -sT 192.168.1.0/24
# used to scan a network by making the full 3 handshake TCP connection and your IP address will be logged but the connection will look normal to the server
```

#### UDP scan
```bash
nmap -sU 192.168.1.0/24
# used to scan networks using UDP protocol
```

#### Port scan
```bash
nmap -p- 192.168.1.1 # scan all ports
nmap -p80 192.168.1.1 # scan port 80 only
nmap -p1-20 192.168.1.1 # scan ports from 1 to 20
namp -p U:1,3,T:6,7 # scan specific TCP and UDP ports
```

#### Fast mode
```bash
nmap -F 192.168.1.1
# scan just the most popular 100 ports
```

#### Version detection
```bash
nmap -sV 192.168.1.1
# determine service/version info
```

#### OS detection
```bash
nmap -O 192.168.1.1
# show information about operating system from it's IP address
```

#### Aggressive scan
```bash
nmap -A 192.168.1.1
# enable OS detection, version detection, script scanning, and traceroute
```

#### Show more details for the scan
```bash
nmap -sT 192.168.1.1 -v
nmap -sT 192.168.1.1 -v # show more details
```

#### Scan output
```bash
nmap -sT 192.168.1.1 -oN file.txt
# store scan output in a file
```

#### Timing template
```bash
nmap 192.168.1.1 -T[0|1|2|3|4|5]
# the less the number is it becomes slow but the scan is more secure
```

#### Update nmap scripts
```bash
nmap --script-updatedb
```

#### Scan with default scripts
```bash
nmap -sC 192.168.1.1
# slow scan but gives a lot of details but not secure
```

#### Scan with a specific script
```bash
nmap --script "SCRIPT_NAME*" 192.168.1.1
```

#### Fragment scan
```bash
nmap -sS -f 192.168.1.1
# split request into packets of 8 bits to make it hard to be detected by firewalls and IDS
nmap --mtu <number>
# the same as above but you control the bits size and the bits must be multiple of 8
```

#### Make scan with multiple IP address
```bash
nmap -D RND:<number> 192.168.1.1
# make the scan with random IP address to make it hard to know the correct IP
```

#### Don't check if host is online
```bash
nmap -Pn 192.168.1.1
# use this flag if you are sure that the target is online
```