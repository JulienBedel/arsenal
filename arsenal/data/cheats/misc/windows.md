# Windows

## PowerShell Execution Policy Bypass

```
powershell.exe -ExecutionPolicy Bypass
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy Bypass -Force
```

## Run As

```
runas /netonly /user:<domain>\<user> powershell.exe
```

## Add user to local admin group

```
net localgroup <admin group> <username> /add
```

## Add user to domain admin group

```
net group <admin group> <user> /ADD /DOMAIN
```

## Add new local user

```
net user /add <user> "<password>"
```

## Add new domain user

```
net user /add <user> "<password>" /domain
```

## Download file from HTTP

```
iwr -uri <url> -Outfile <file>
```

## Copy file from SMB share

```
Copy-Item -Path <source> -Destination <destination>
```

## Use SMB share (before copy)

```
net use x: \\<server>\<sharename> /USER:<domain>\<username> <password>
```
