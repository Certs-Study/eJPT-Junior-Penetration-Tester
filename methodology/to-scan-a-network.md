---
description: Methodology To Scan a Network
---

# 1⃣ To Scan a Network

Usually on certifications labs or execuing a pentestration test on a client we have define in our scope a sub net with specified range of IPs.

Before start scanning the network I usually execute some commands on my machine to verify what interface is associated with the VPN to verify my IP and verify my ARP table.

### What to expect?

Networks can filter types of traffic or traffic to specific port numbers. Pay attention if you trying to get a reverse shell on a random port number, that port could be blocked.

### What if the Network is blocking some types of traffic?

As I said networks can filter types of traffic like TCP/UDP/SCTP/ICMP or even IP, yes IP!&#x20;

UDP traffic can be block only for a specific host and allowed for other inside the same subnet.&#x20;

Or can be blocked on all subnet.

In these case we need to test the network for each host we we've found.

### Traceroute is our Friend!

Traceroute using TCP

```
sudo traceroute -T 192.168.4.5
```

Traceroute using UDP

```
sudo traceroute -U 192.168.4.5
```

#### Traceroute using ICMP

```
sudo traceroute -I 192.168.4.5
```

### Keep in Mind
