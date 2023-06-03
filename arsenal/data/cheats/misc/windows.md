# Windows

## Run As

```
runas /netonly /user:<domain>\<user> powershell.exe
```

## Add user to local admin group

```
net r <user> /add
```

## Add user to domain admin group

```
net group <admin group> <user> /ADD /DOMAIN
```

## Add new domain user

```
net user /add <user> "<password>" /domain
```

## PowerShell Execution Policy Bypass

```
powershell.exe -ExecutionPolicy Bypass
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy Bypass -Force
```



