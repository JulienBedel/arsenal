# Unix

## Grep IP

```
grep -oE "\b([0-9]{1,3}\.){3}[0-9]{1,3}\b"
```

## Convert list of hosts to IP

```
while read in; do host "$in"; done < <file> | grep -oE "\b([0-9]{1,3}\.){3}[0-9]{1,3}\b"
```

## Share the current directory via SMB (auth required)

```
docker run --rm -v $PWD:/mount -p 0.0.0.0:445:445 -it -e USERID=1000 -e GROUPID=1000 --name samba dperson/samba -p -u '<user>;<password>' -s "<name>;/mount;yes;no;no;<user>"
```

## Share the current directory via SMB (guest access)

```
docker run --rm -v $PWD:/mount -p 0.0.0.0:445:445 -it -e USERID=1000 -e GROUPID=1000 --name samba dperson/samba -p -s "public;/mount;yes;yes;yes"
```

## Launch Nessus using Gnome keyring

```
docker run --name "nessus" -p 127.0.0.1:8834:8834 -e ACTIVATION_CODE="$(secret-tool search --all xdg:schema org.gnome.keyring.Note | awk '/<nessus_license>/{getline; print}' | cut -d '=' -f 2 | xargs)" -e USERNAME=nessus -e PASSWORD="$(secret-tool search --all xdg:schema org.gnome.keyring.Note | awk '/<nessus_password>/{getline; print}' | cut -d '=' -f 2 | xargs)" -e AUTO_UPDATE=no tenableofficial/nessus:latest
```

= keyring_license: nessus_license
= keyring_password: nessus_password
