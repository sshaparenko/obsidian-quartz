---
date: 2024-04-22T16:32
tags:
  - Networks
  - IP
---
[source](https://www.freecodecamp.org/news/setting-a-static-ip-in-ubuntu-linux-ip-address-tutorial/)

```
#1 Note information about current network
> ip a

------

wlp0s20f3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000
    link/ether b4:6b:fc:15:15:85 brd ff:ff:ff:ff:ff:ff
    inet 172.20.10.2/28 brd 172.20.10.15 scope global dynamic noprefixroute wlp0s20f3
       valid_lft 86147sec preferred_lft 86147sec
    inet6 fe80::7e72:32a8:ec40:aae0/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever

------

172.20.10.2/28 -> 28 bits reserved for the netmask
172.20.10.15 -> broadcast address
```

```
#2 based on ip_address/netmask_bits (172.20.10.2/28) determine usable host IP range
> ipcalc -n -b 172.20.10.2/28

HostMin:   172.20.10.1          
HostMax:   172.20.10.14 

---
Range is 172.20.10.1 - 172.20.10.14
```

