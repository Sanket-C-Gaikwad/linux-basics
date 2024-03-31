## Networking in Linux

```
cat /etc/os-release

- List all Network Interfaces
ifconfig -a 
ip a s

- IP Address setting using ip command
ip a s | grep eth1
ip addr add 172.62.62.200/24 dev eth1

- Deletion of an IP Address using ip command
ip addr del 172.62.62.200/24 dev eth1
ip a s | grep eth1

- Set the interface link up or down using ip command
ip link set dev eth1 down
ip link set dev eth1 up

- Configure a default gateway using ip command
ip route show
ip route add default via 172.62.62.1
ip route del default via 172.62.62.1

- Flush IP settings from an interface using ip command
ip addr flush eth1
```
