# Domain Enumeration

## Find DNS servers in use

```
systemd-resolve --status
nmcli dev show | grep DNS | sed 's/\s\s*/\t/g' | cut -f 2
```

## Responder analyze mode

```
responder-http-on
responder-smb-on
responder -I <interface> -A
```

= interface: enp0s31f6

## Find DCs from FQDN - nmap

```
nmap --script dns-srv-enum --script-args dns-srv-enum.domain=<fqdn>
```

= fqdn: $FQDN

## Find DCs from FQDN - nslookup

```
nslookup -type=srv _ldap._tcp.pdc._msdcs.<fqdn>
nslookup -type=srv _ldap._tcp.dc._msdcs.<fqdn>
```

= fqdn: $FQDN

## Domain enumeration - enum4linux

```
enum4linux -a -u '<user>' -p '<password>' -w <domain> <domain-controller>
```

= domain-controller: $DOMAIN_CONTROLLER
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## Domain enumeration - enum4linux-ng

```
enum4linux-ng -A -u <user> -p '<password>' -w <domain> <domain-controller>
```

= domain-controller: $DOMAIN_CONTROLLER
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## Find basic domain info (anonymous)

```
ldapsearch-ad.py -l <domain-controller> -t info
```

= domain-controller: $DOMAIN_CONTROLLER

## List domain users - enum4linux-ng

```
enum4linux-ng -u '<user>' -p '<password>' -w <domain> <domain-controller> -U -oJ temp  > /dev/null 2>&1 ; jq -r '.users[].username' temp.json ; rm temp.json
```

= domain-controller: $DOMAIN_CONTROLLER
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## List domain users

```
windapsearch -d <domain> -u <user> -p '<password>' --dc <domain-controller> --module users --json | jq -r '.[].sAMAccountName'
```

= domain-controller: $DOMAIN_CONTROLLER
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## List domain computers

```
windapsearch -d <domain> -u <user> -p '<password>' --dc <domain-controller> --module computers --json | jq -r '.[].dNSHostName'
```

= domain-controller: $DOMAIN_CONTROLLER
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## List domain servers

```
windapsearch -d <domain> -u <user> -p '<password>' --dc <domain-controller> -m computers --json | jq -r '.[] | select(.operatingSystem | contains("Server"))'.dNSHostName
```

= domain-controller: $DOMAIN_CONTROLLER
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## List domain privileged users

```
windapsearch -d <domain> -u <user> -p '<password>' --dc <domain-controller> --module privileged-users
```

= domain-controller: $DOMAIN_CONTROLLER
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## List domain DNS entries - adidnsdump

```
adidnsdump -u '<user>' -p '<password>' <domain_controller>
```

= domain-controller: $DOMAIN_CONTROLLER
= user: $USER
= password: $PASSWORD

## List domain DNS entries - windapsearch

```
windapsearch -d <domain> -u <user> -p '<password>' --dc <domain-controller> --module dns-names
```

= domain-controller: $DOMAIN_CONTROLLER
= user: $USER
= password: $PASSWORD

## List domain DNS zones - windapsearch

```
windapsearch -d <domain> -u <user> -p '<password>' --dc <domain-controller> --module dns-zones
```

= domain-controller: $DOMAIN_CONTROLLER
= user: $USER
= password: $PASSWORD