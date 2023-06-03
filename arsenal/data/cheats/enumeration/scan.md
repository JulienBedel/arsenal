# Scanning the network

## Read scan targets from a file
```
nmap -iL <target_file>
```

## Ping Scan

```
nmap -sn <target>
```

## Top Ports

```
nmap <options> --top-ports <top-port-number> <target> <output>
```

= options: -Pn -sV
= top-ports-number: 200

## Full Scan

```
TARGET=<target>;
ports=$(nmap -p- $TARGET | grep ^[0-9] | cut -d '/' -f 1 | tr  '\n' ',' | sed s/,$//)  
nmap -p$ports -A $TARGET
```

## UDP Scan

See :
https://security.stackexchange.com/questions/52566/increase-speed-in-nmap-udp-scan
https://nmap.org/book/scan-methods-udp-scan.html
https://nmap.org/book/reduce-scantime.html

```
TODO
```

## Enumerate hosts with CME

```
cme smb <target>
```

= target: ./targets/domain/computers.txt

## Filter hosts with specific port open

```
nmap -Pn -p445 <target> -oG - | awk '/445\/open/ {print $2}'
```

## gowitness (nmap)

```
gowitness nmap -f /data/nmap/192.168.201.85.xml --open --service-contains http
```

