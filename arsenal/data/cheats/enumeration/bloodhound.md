# BloodHound

## SharpHound.ps1 ingestor from non-domain computer

```
runas /netonly /user:<domain>\<user> powershell.exe
Import-Module Sharphound.ps1
Invoke-BloodHound --CollectionMethod All --OverrideUserName --Domain <domain>
```

= user: $USER
= domain: $DOMAIN

## SharpHound.exe ingestor from non-domain computer

```
runas /netonly /user:<domain>\<user> SharpHound.exe --CollectionMethod All --OverrideUserName --Domain <domain>
```

= user: $USER
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
