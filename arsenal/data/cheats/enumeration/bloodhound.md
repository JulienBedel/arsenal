# BloodHound

## SharpHound.ps1 ingestor from non-domain computer

```
Import-Module Sharphound.ps1
Invoke-BloodHound -CollectionMethod All -Domain <domain> -OverrideUsername <user> -ldapusername <user> -ldappassword <password> -domaincontroller <domain-controller> 
```

= domain-controller: $DOMAIN_CONTROLLER
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## SharpHound.exe ingestor from non-domain computer

```
.\SharpHound.exe --collectionmethods All --domain <domain> --overrideusername <user> --ldapusername <user> --ldappassword <password> --domaincontroller <domain-controller>
```

= domain-controller: $DOMAIN_CONTROLLER
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## BloodHound.py ingestor

```
bloodhound.py -c All -d <domain> -u <user> -p '<password>' -dc <domain-controller>
```

= domain-controller: $DOMAIN_CONTROLLER
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## BloodHound module for CME (mark as owned)

```
cme smb <target> -u <user> -p '<password>' -d <domain> -M bh_owned -o PASS=<neo4j_password>
```

= neo4j_password: mustafar4thewin

## BloodHound import

```
bloodhound-import -du neo4j -dp <password> <bloodhound_files>/*.json
```