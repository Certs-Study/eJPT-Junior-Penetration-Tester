# Nmap

```
nmap -sn 10.10.10.0/24
nmap -sV -p- -iL targets -oN nmap.initial -v
nmap -A -p- -iL targets -oN nmap.aggressive -v
nmap -p --script=vuln -v
```
