- VPC: 
  - ```like a fence around an AWS resources```
  - it helps seperating all the resoures within one VPC to another VPC
  - CIDR block ranges in VPC:
    - (10.0.0.0/24) Each numbers after '/' are called octate, representing 8 bits
    - '/24' above indicates that the first 24 bits are part of network address, 192.168.10, leaving only last octate '8 bits' to be able to change for IP numbers or specific host address (0-254) ```/24 last octate -> 10.0.0.1 - 10.0.0.254```
    - This means in '/16' can only change last two octates or 16 bits ```/16 last two octates -> 10.0.0.1 - 10.0.255.254``` Can have total number of 65,536 hosts.
    - And '/8' leaves the remaining 24 bits to be able to change. ```/8 last three octates -> 10.0.0.1 - 10.255.255.254```

- Subnet:
  - Defined set of IP addresses.
  - ```like postal codes, used for routing pckgs from one location to another```
  - Public subnet and Private subnet
  - In cloud, 2 Public and Private subnest are created on 2 different Availability Zones, just to avoid any blockers.
  - ```Subnets are required to launch any cloud resources in VPC.```

- EC2:
  - Images of different Operating Systems (OS)

- Security Groups (SG):
  - ```like virtual firewalls for EC2 instances to control incomming and outgoing traffic'''
  - SG is stateful.

- Gateway:
  - To allow Internet access to the subnet, it needs gateway
  - Internet Gateway:
    - connects VPC to another outer network.
  - NAT (Network Access Translation) Gateway:
    - Helps to reach out to the internet, but cannot reach inbound.
    - connects instances in private subnet can connect outside of VPC, but external services cannot connect into that subnet
    - Create NAT Gateway inside Public subnet, which creates Private ROu0te Tables for Private subnet
  - Can only have 1 Gateway per VPC

- Route tables:
  - This gives subnet rules to route out to the Internet
  - Route tables allows Private and Public traffic

- NACL (Network Access Control List):
  - ```like a virtual firewalls that protects the subnet```
  - NACL is stateless, meaning if it allows anything inside the subnet, it doesn't remember where it came from, so it needs outbound rules to allow it outside.
  - By default, NACL allows everything in and everything out.
