## Linux Network Related Commands

### Add/Remove Address With ip Commands

#### Add IP address

```shell
# check ip address
sudo ip a
```

Assume you want assign 10.1.1.10 with netmask 255.255.255.0 to device ens3

```shell
sudo ip a add 10.1.1.10/24 dev ens3
```

#### Remove Address
Remove assigned IP 10.1.1.10 from device ens3

```shell
sudo ip a del 10.1.1.10/24 dev ens3
```

### Bring up/down NIC With ip Commands

#### Bring up NIC
Before you start, please make sure it was connected(use **ethtool** to check it).

We take **ens3** as example:
```shell
# Check devices link status
sudo ip l

sudo ip l set dev ens3 up
```

#### Bring down NIC
```shell
# Check devices link status
sudo ip l

sudo ip l set dev ens3 down
```

### Scan all up host with nmap

Suppose you want to scan 172.16.0.0/24 all up hosts

```shell
sudo nmap -sn 172.16.0.0/24
```
It will list all up hosts and their MAC address.