# Unix

## Grep IP

```
grep -oE "\b([0-9]{1,3}\.){3}[0-9]{1,3}\b"
```

## Convert list of hosts to IP

```
while read in; do host "$in"; done < <file> | grep -oE "\b([0-9]{1,3}\.){3}[0-9]{1,3}\b"
```