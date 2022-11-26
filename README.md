# Jarkom-Modul-4-I02-2022

**Computational Networking Module 4 Practicum Report**

Group Members:

+ Adam Satria Adidarma - 05111942000001
+ Muhammad Fatih Akbar - 5025201117
+ Rangga Aulia Pradana - 5025201154

## Important Links

+ [Questions](https://docs.google.com/document/d/1a_ITp6WYIqoJFXA2oL1jkox9AzqYGxicjr2LGPBsqBE/edit)

## Table Of Contents

- [Jarkom-Modul-4-I02-2022](#jarkom-modul-4-i02-2022)
  - [Important Links](#important-links)
  - [Table Of Contents](#table-of-contents)
  - [Breakdown](#breakdown)
    - [Topologies](#topologies)
      - [Cisco Packet Tracer](#cisco-packet-tracer)
      - [GNS3](#gns3)
    - [Subnetting](#subnetting)
      - [CPT - CIDR Classless](#cpt---cidr-classless)

## Breakdown

### Topologies

Below are the topology translated to each application as given from the question.

#### Cisco Packet Tracer

![CPT Topology](https://i.imgur.com/3ND4p2t.png)

#### GNS3

![GNS3 Topology](https://i.imgur.com/yPLP7gb.png)

### Subnetting

The topology above have been grouped into multiple subnets which is as visualized below.

![Subnets Visualization](https://i.imgur.com/gKaEqcg.png)

The following are the host count and netmask of each subnets.

| **Subnet** 	| **Host Count** 	| **Netmask** 	|
|:----------:	|:--------------:	|:-----------:	|
| A1         	| 1001           	| /22         	|
| A2         	| 2              	| /30         	|
| A3         	| 251            	| /24         	|
| A4         	| 2              	| /30         	|
| A5         	| 51             	| /26         	|
| A6         	| 2              	| /30         	|
| A7         	| 2              	| /30         	|
| A8         	| 2              	| /30         	|
| A9         	| 271            	| /23         	|
| A10        	| 2              	| /30         	|
| A11        	| 121            	| /25         	|
| A12        	| 2              	| /30         	|
| A13        	| 121            	| /125        	|
| A14        	| 71             	| /25         	|
| A15        	| 2              	| /30         	|
| A16        	| 501            	| /23         	|
| A17        	| 212            	| /24         	|
| A18        	| 2              	| /30         	|
| **TOTAL**   	| 2618           	| /20         	|

The following 2 section will go the two different method of subnetting in the classles type, VLSM & CIDR.

#### CPT - CIDR Classless

By starting from the deepest part of the whole network **(A3-A2, A13-A14, etc.)** and keep adding more subnetwork to merge with as it grows, we wll get the following Tree:

![CIDR Tree](https://i.imgur.com/dSSLN0i.png)

from here on, we can start configuring the nodes within the topology. Below are an example on how the configs are accessed:

> **On a Router:**
> ![Router Config](https://i.imgur.com/OplLW7Q.png)

> **On a Client/Server**
> ![Client Config](https://i.imgur.com/LcUofRL.png)

Below is table of the configuration of the subnetting.

| **Subnet** 	| **Network IP** 	| **Netmask**     	| **Gateway IP** 	| **Client(s) IP**       	|
|------------	|----------------	|-----------------	|----------------	|------------------------	|
| A1         	| 10.36.2.0      	| 255.255.252.0   	| 10.36.2.1      	| 10.36.2.2              	|
| A2         	| 10.36.1.0      	| 255.255.255.252 	| 10.36.1.1      	| 10.36.1.2              	|
| A3         	| 10.36.0.0      	| 255.255.255.0   	| 10.36.0.1      	| 10.36.0.2              	|
| A4         	| 10.36.8.0      	| 255.255.255.252 	| 10.36.8.1      	| 10.36.8.2              	|
| A5         	| 10.36.16.0     	| 255.255.255.192 	| 10.36.16.1     	| 10.36.16.2             	|
| A6         	| 10.36.32.0     	| 255.255.255.252 	| 10.36.32.2     	| 10.36.32.2             	|
| A7         	| 10.36.100.0    	| 255.255.255.252 	| 10.36.100.1    	| 10.36.100.2            	|
| A8         	| 10.36.98.0     	| 255.255.255.252 	| 10.36.98.1     	| 10.36.98.2             	|
| A9         	| 10.36.96.0     	| 255.255.254.0   	| 10.36.96.1     	| 10.36.96.2             	|
| A10        	| 10.36.80.0     	| 255.255.255.252 	| 10.36.80.1     	| 10.36.80.2             	|
| A11        	| 10.36.72.0     	| 255.255.255.128 	| 10.36.72.1     	| 10.36.72.2             	|
| A12        	| 10.36.73.128   	| 255.255.255.252 	| 10.36.73.129   	| 10.36.73.130           	|
| A13        	| 10.36.72.128   	| 255.255.255.128 	| 10.36.72.129   	| 10.36.72.130           	|
| A14        	| 10.36.73.0     	| 255.255.255.128 	| 10.36.73.1     	| 10.36.73.2             	|
| A15        	| 10.36.68.0     	| 255.255.255.252 	| 10.36.68.1     	| 10.36.68.2             	|
| A16        	| 10.36.66.0     	| 255.255.254.0   	| 10.36.66.1     	| 10.36.66.2             	|
| A17        	| 10.36.64.0     	| 255.255.255.0   	| 10.36.64.1     	| 10.36.64.2, 10.36.64.3 	|
| A18        	| 10.36.65.0     	| 255.255.255.252 	| 10.36.65.1     	| 10.36.65.2             	|

#### GNS3 - VLSM Classless

Done as similar to that of a binary tree, as to keep splitting until reaching each clients netmasks. The result is the following tree.

![VLSM Tree](https://i.imgur.com/xL8U24E.png)

Configuration Table

| **Subnet** 	| **Network IP** 	| **Netmask**     	| **Gateway IP** 	| **Client(s) IP**     	|
|------------	|----------------	|-----------------	|----------------	|----------------------	|
| A1         	| 10.36.4.0      	| 255.255.252.0   	| 10.36.4.1      	| 10.36.4.2            	|
| A2         	| 10.36.11.192   	| 255.255.255.252 	| 10.36.11.193   	| 10.36.11.194         	|
| A3         	| 10.36.8.0      	| 255.255.255.0   	| 10.36.8.1      	| 10.36.8.2            	|
| A4         	| 10.36.11.196   	| 255.255.255.252 	| 10.36.11.197   	| 10.36.11.198         	|
| A5         	| 10.36.11.128   	| 255.255.255.192 	| 10.36.11.129   	| 10.36.11.130         	|
| A6         	| 10.36.11.200   	| 255.255.255.252 	| 10.36.11.201   	| 10.36.11.202         	|
| A7         	| 10.36.11.204   	| 255.255.255.252 	| 10.36.11.205   	| 10.36.11.206         	|
| A8         	| 10.36.11.208   	| 255.255.255.252 	| 10.36.11.209   	| 10.36.11.210         	|
| A9         	| 10.36.2.0      	| 255.255.254.0   	| 10.36.2.1      	| 10.36.2.2            	|
| A10        	| 10.36.11.212   	| 255.255.255.252 	| 10.36.11.213   	| 10.36.11.214         	|
| A11        	| 10.36.10.0     	| 255.255.255.128 	| 10.36.10.1     	| 10.36.10.2           	|
| A12        	| 10.36.11.216   	| 255.255.255.252 	| 10.36.11.217   	| 10.36.11.218         	|
| A13        	| 10.36.10.128   	| 255.255.255.128 	| 10.36.10.129   	| 10.36.10.130         	|
| A14        	| 10.36.11.0     	| 255.255.255.128 	| 10.36.11.1     	| 10.36.11.2           	|
| A15        	| 10.36.11.220   	| 255.255.255.252 	| 10.36.11.221   	| 10.36.11.222         	|
| A16        	| 10.36.0.0      	| 255.255.254.0   	| 10.36.0.1      	| 10.36.0.2            	|
| A17        	| 10.36.9.0      	| 255.255.255.0   	| 10.36.9.1      	| 10.36.9.2, 10.36.9.3 	|
| A18        	| 10.36.11.224   	| 255.255.255.252 	| 10.36.11.225   	| 10.36.11.226         	|

### Routing

Done to route packets from one node to another.

#### CPT

> **Router Configuration**
> ![Routing Config](https://i.imgur.com/cqVjpSH.png)

Configuration Table:

| Network IP 	| Netmask 	| Next Hop 	|
|------------	|---------	|----------	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|
|            	|         	|          	|

#### GNS3

Haven't been done since this hasn't passed Subnetting Phase.

### Testing

Due to dificulties and short of time, it hasn't been tested.

## Revisions & Dificulties

+ Revised CIDR, and applied to CPT.
+ Constant Errors received in CPT when applying routing.
+ Unsure if the VLSM is correct or not.
