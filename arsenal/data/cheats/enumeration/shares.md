# SMB Shares Enumeration

## Enumerate shares (null session)

```
cme smb <target> -u '' -p '' --shares | tee cme_<target_name>_shares_null.txt
```

= target: $TARGETS/computers.list

## Enumerate shares (anonymous)

```
cme smb <target> -u 'a' -p '' --shares | tee cme_<target_name>_shares_anonymous.txt
```

= target: $TARGETS/computers.list

## Enumerate shares (domain auth)

```
cme smb <target> -u <user> -p '<password>' -d <domain> --shares | tee cme_<target_name>_standard_null.txt
```

= target: $TARGETS/computers.list
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
