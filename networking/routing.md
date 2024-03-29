---
description: >-
  Explore our comprehensive article where we explain routing in-depth.
  Understand the process, protocols, and more with our detailed guide on network
  routing.
---

# 🟢 Routing

### Routing Basics

Routing is the process of selecting paths in a network along which to send network traffic. It is crucial for connecting different networks and for the correct delivery of data from one network to another.

### Adding Static Routes on Linux

To add a static route on a Linux system, you use the `ip route add` command followed by the network range, the gateway address, and the device name.

### **Example Command**

```bash
ip route add 10.10.10.0/24 via 10.10.10.1 dev tun0
```

This specific command is telling the operating system to send all traffic destined for the `10.10.10.0/24` network to the next-hop gateway at `10.10.10.1` via the `tun0` network interface.
