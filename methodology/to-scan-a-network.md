---
description: >-
  Dive deep into this comprehensive article on the methodology to scan a
  network. Learn about effective strategies, tools, and best practices used in
  network scanning techniques.
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

### Methodology To Scan a Network

**Identify the Network Range**

Start by determining the range of IP addresses within the scope of the penetration test. This information is typically provided in the rules of engagement document.

```bash
# Example command for identifying local network interface details
ip addr show
```

**Reconnaissance**

Perform initial reconnaissance to gather as much information as possible about the target network. This may include using tools like `nmap` to discover hosts, services, and their characteristics.

```bash
# Example Nmap command to discover live hosts
nmap -sn 192.168.4.0/24
```

**Port Scanning**

After identifying active hosts, proceed to scan for open ports and running services to gather more granular intelligence.

```bash
# Example Nmap command to scan for open ports
nmap -p 1-65535 192.168.4.5
```

**Vulnerability Assessment**

Analyze the discovered services for known vulnerabilities using automated tools or manual techniques. Tools like OpenVAS or Nessus can be used for automated scans.

**Analysis and Planning**

Analyze the data collected to identify potential attack vectors. Use this information to plan your penetration test, such as what tools and exploits to use.

**Exploitation**

Attempt to exploit identified vulnerabilities to gain unauthorized access, escalate privileges, or gather sensitive data.

**Post-Exploitation**

Once access is gained, further explore the network to discover additional systems, data, and maintain persistence if within the scope.

**Reporting**

Document all discovered vulnerabilities, exploited systems, and recommended remediation strategies in a detailed report for the client.

**Cleanup**

Ensure that any modifications made to the target network during the test are reverted to leave the network in its original state.
