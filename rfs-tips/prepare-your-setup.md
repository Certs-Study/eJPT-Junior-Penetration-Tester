# Prepare your Setup

Here I will explain my setup, for me it works.  I hope it will work for you too.

We know the basic access is thought a VPN I configure the my account on a router and connect a switch to It.

### Local LAN for Exam Build&#x20;

### Router

This router will connect to my main router and firewall and I will configure the VPN connection to the Lab on it. I can get a more stable connection this way and avoid networks/performance problems on the attacker machine.

### Switch

Just a cheap unmanaged switch to connect all machines needed to perform the exam.

### Buffer Overflows - Windows 7

Then I connected my Windows 7 machine dedicated to buffer overflows to the switch and my attack machine. Equipped with Immunity debugger and Mona.

And _Ghidra_ in case I am stuck...

### Attack Machine - Kali

Kali machine fully updated, I know must people don't recommend this. After fully update I start configuring all the Operating System and tools as I like.&#x20;

I wrote a script to this for me, you can use it:&#x20;

### Cracking Machine - Debian

I've my cracking machine prepare with all wordlists, keys, hashs, rainbow tables and all the tools needed to create new wordlists.

And is connected to online APIs in case I can't break it at home... :joy:
