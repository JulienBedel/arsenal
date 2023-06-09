# Domain Enumeration

## Find DNS servers in use (resolvectl)

```
resolvectl status | grep 'DNS Servers'
```

## Find DNS servers in use (nmcli)

```
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
enum4linux -a -u <user> -p <password> -w <domain> <domain-controller>
```

= domain-controller: $DC
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## Anonymous domain enumeration - enum4linux

```
enum4linux -a -u '' -p '' -w <domain> <domain-controller>
```

= domain-controller: $DC
= domain: $DOMAIN

## Domain enumeration - enum4linux-ng

```
enum4linux-ng -A -u <user> -p <password> -w <domain> <domain-controller>
```

= domain-controller: $DC
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## Anonymous domain enumeration - enum4linux-ng

```
enum4linux-ng -A -w <domain> <domain-controller>
```

= domain-controller: $DC
= domain: $DOMAIN

## Anonymous domain enumeration - ldapsearch

```
ldapsearch-ad -l <domain-controller> -t info
```

= domain-controller: $DC

## List domain users

```
windapsearch -d <domain> -u <user> -p <password> --dc <domain-controller> --module users --json | jq -r '.[].sAMAccountName'
```

= domain-controller: $DC
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## List domain computers

```
windapsearch -d <domain> -u <user> -p <password> --dc <domain-controller> --module computers --json | jq -r '.[].dNSHostName'
```

= domain-controller: $DC
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## List domain servers

```
windapsearch -d <domain> -u <user> -p <password> --dc <domain-controller> -m computers --json | jq -r '.[] | select(.operatingSystem | contains("Server"))'.dNSHostName
```

= domain-controller: $DC
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## List domain DNS entries - adidnsdump

```
adidnsdump -u <user> -p <password> <domain_controller>
```

= domain-controller: $DC
= user: $USER
= password: $PASSWORD

## List domain DNS entries - windapsearch

```
windapsearch -d <domain> -u <user> -p <password> --dc <domain-controller> --module dns-names
```

= domain: $DOMAIN
= domain-controller: $DC
= user: $USER
= password: $PASSWORD

## List domain DNS zones - windapsearch

```
windapsearch -d <domain> -u <user> -p <password> --dc <domain-controller> --module dns-zones
```

= domain: $DOMAIN
= domain-controller: $DC
= user: $USER
= password: $PASSWORD