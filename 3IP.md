# IP Adressing

as we saw in the previous chapter, IP stands for Internet Protocol. IP is the protocol that is used to send data from one device to another. IP is a layer 3 protocol. IP is used in the Internet Layer of the TCP/IP model. and it's devided into 4 classes like the following table:

| Class | First Digit | Range | Number of Hosts | Number of Networks |
|-------|-------------|-------|-----------------|--------------------|
| A     | 1-126       | 1-126 | 16,777,214      | 127                |
| B     | 128-191     | 128-191 | 65,534          | 16,383             |
| C     | 192-223     | 192-223 | 254             | 2,097,151          |
| D     | 224-239     | 224-239 | -               | -                  |

## Division into sub-networks

before we pass to sub-networks we need to know that there are special IP addresses that are used for special purposes. the following table shows the special IP addresses:

| IP Address | Purpose |
|------------|---------|
| if the digits of host part are all 0s | Network Address |
| if the digits of host part are all 1s | Broadcast Address |

that means that if we have a network of 10.5.2.1/24 we can classify draw the following table:

| Network Address | First Usable Address | Last Usable Address | Broadcast Address |
|-----------------|----------------------|---------------------|-------------------|
| 10.5.2.0/24     | 10.5.2.1/24          | 10.5.2.254/24       | 10.5.2.255/24     |

### Mask address

the mask address is used to divide the network into sub-networks. the mask address is used to determine the number of hosts and the number of networks. the following table shows the mask addresses:

| Class | Mask Address |
|-------|--------------|
| A     | 255.0.0.0    |
| B     | 255.255.0.0  |
| C     | 255.255.255.0|

### Sub-networks

the following table shows the number of hosts and the number of networks for each class:

| Class | Number of Hosts | Number of Networks |
|-------|-----------------|--------------------|
| A     | 16,777,214      | 127                |
| B     | 65,534          | 16,383             |
| C     | 254             | 2,097,151          |

### Sub-networks division

we can divide the network into sub-networks by subtracting the number of bits that we want to use for the sub-networks from the number of bits that we want to use for the hosts.
like the following example:

we have the next network Address: 167.128.0.0/16 and we want to divide it into 4 sub-networks. so we need to subtract 2 bits from the number of bits that we want to use for the hosts. so we have $16^2 = 4$ bits for the hosts. and we have 2 bits for the sub-networks. so we have the following table:

| Sub-network | Network Address | First Usable Address | Last Usable Address | Broadcast Address |
|-------------|-----------------|----------------------|---------------------|-------------------|
| 1           |167.128.0.0/18   | 167.128.0.1/18       | 167.128.63.254/18   |167.128.63.255/18  |
| 2           |167.128.64.0/18   | 167.128.64.1/18       | 167.128.127.254/18   |167.128.127.255/18  |
| 3           |167.128.128.0/18   | 167.128.128.1/18       | 167.128.191.254/18   |167.128.191.255/18  |
| 4           |167.128.192.0/18   | 167.128.192.1/18       | 167.128.255.254/18   |167.128.255.255/18  |

### VLSM

stands for Variable Length Subnet Masking. it's a technique that is used to divide the network into sub-networks. it's used to divide the network into sub-networks with different number of hosts. but it's not like the previous division

## Private & Public IP Addresses

the following table shows the private IP addresses:

| Class | Range |
|-------|-------|
| A     | 10    |
| B     | 172.16-172.31 |
| C     | 192.168 |

every adress that is not in the previous table is a public IP address.

the use of private IP addresses is to avoid the use of public IP addresses. the use of public IP addresses is to connect to the Internet. the use of private IP addresses is to connect to the local network.

# Network Address Translation (NAT)

NAT is a technique that is used to translate the private IP addresses to public IP addresses. NAT is used to connect to the Internet. NAT is used to connect to the local network.
there are 3 types of NAT:

## Static NAT

Static NAT is a technique that is used to translate the private IP addresses to public IP addresses. Static NAT is used to connect to the Internet. Static NAT is used to connect to the local network.
to configure Static NAT we need to use the following commands:

at the router:

```bash
Router(config)#interface FastEthernet 0/0
Router(config-if)#ip address 192.168.1.1 255.255.255.0
Router(config-if)#ip nat inside
Router(config-if)#exit
Router(config)#interface FastEthernet 0/1
Router(config-if)#ip address 41.41.15.18 255.0.0.0
Router(config-if)#ip nat outside
Router(config-if)#exit
Router(config)#ip nat inside source list 1 interface FastEthernet 0/1 overload
Router(config)#access-list 1 permit
```

at the PC:

```bash
PC>ipconfig
```

## Dynamic NAT

Dynamic NAT is a technique that is used to translate the private IP addresses to public IP addresses. Dynamic NAT is used to connect to the Internet. Dynamic NAT is used to connect to the local network.

to configure Dynamic NAT we need to use the following commands:

at the router:

```bash
Router(config)#interface FastEthernet 0/0
Router(config-if)#ip address
Router(config-if)#ip nat inside
Router(config-if)#exit
Router(config)#interface FastEthernet 0/1
Router(config-if)#ip address
Router(config-if)#ip nat outside
Router(config-if)#exit
Router(config)#ip nat inside source list 1 interface FastEthernet 0/1 overload
Router(config)#access-list 1 permit
```

at the PC:

```bash
PC>ipconfig
```

## Overload NAT

Overload NAT is a technique that is used to translate the private IP addresses to public IP addresses. Overload NAT is used to connect to the Internet. Overload NAT is used to connect to the local network.

to configure Overload NAT we need to use the following commands:

at the router:

```bash
Router(config)#interface FastEthernet 0/0
Router(config-if)#ip address
Router(config-if)#ip nat inside
Router(config-if)#exit
Router(config)#interface FastEthernet 0/1
Router(config-if)#ip address
Router(config-if)#ip nat outside
Router(config-if)#exit
Router(config)#ip nat inside source list 1 interface FastEthernet 0/1 overload
Router(config)#access-list 1 permit
```

at the PC:

```bash
PC>ipconfig
```

