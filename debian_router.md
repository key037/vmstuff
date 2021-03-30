# setting up debian as a router 

You need to add a forwarding rule using iptables command, where:
	- eth0 is the interface, that will receive packets, 
	- eth1 outgoing interface 
```
modprobe iptable_nat
echo 1 > /proc/sys/net/ipv4/ip_forward
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
iptables -A FORWARD -i eth1 -j ACCEPT
```
