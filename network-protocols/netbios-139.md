# 🟢 NetBIOS 139

```
sudo nmap -sT -sU -sV -p135,137,138,139,445 --open <IP>
```

## Enumerate shares

nmap --script smb-enum-shares -p 445

## OS Discovery

nmap --script smb-os-discovery -p 445

## Enumerate Users

nmap --script=smb-enum-users -p 445

## All

nmap --script=smb-enum-users,smb-enum-shares,smb-os-discovery -p 139,445

### NULL / Anonymous Login

```
# On some configuration omitting '-N' will grant access.
smbclient -U '' -L \\\\<IP> 

smbclient -U '' -N -L \\\\<IP> 
smbclient -U '%' -N -L \\\\<IP>
smbclient -U '%' -N \\\\<IP>\\<Folder>

# Enter a random username with no password and try for anonymous login.
crackmapexec smb <IP> -u 'anonymous' -p ''

crackmapexec smb <IP> -u '' -p ''
crackmapexec smb <IP> -u '' -p '' --shares
```

### Crackmapexec

{% code overflow="wrap" %}
```
crackmapexec smb <IP> -u <User> -p <Password> --rid-brute
crackmapexec smb <IP> -u <User> -p <Password> --lsa
crackmapexec smb <IP> -u <User> -p <Password> --sam
crackmapexec smb <IP> -u <User> -p <Password> --pass-pol
crackmapexec smb <IP> -u <User> -p <Password> --local-groups
crackmapexec smb <IP> -u <User> -p <Password> --groups
crackmapexec smb <IP> -u <User> -p <Password> --users
crackmapexec smb <IP> -u <User> -p <Password> --sessions
crackmapexec smb <IP> -u <User> -p <Password> --disks
crackmapexec smb <IP> -u <User> -p <Password> --loggedon-users
crackmapexec smb <IP> -u <User> -p <Password> --loggedon-users --sessions --users --groups --local-groups --pass-pol --sam --rid-brute 2000
```
{% endcode %}
