# Laboratory 5 – Router Configuration and IP Addressing Lab

## Objective
In this lab, I built a simple network with two subnets, configured a router to enable IP addressing, and verified connectivity between all devices across different network segments.

## How I Did It

### Part 1: Building the Network Topology

1. **Adding Devices**  
   I added a **1841 Router**, two **2960 Switches**, two **PCs**, and two **Laptops**

2. **Renaming Devices**  
   I renamed the devices as follows:
   - Router: **R1**
   - Switches: **SW1** and **SW2**
   - PCs: **Desktop_1** and **Desktop_2**
   - Laptops: **Laptop_1** and **Laptop_2**

3. **Connecting Devices**  
   - Connected **Desktop_1** to **SW1** (FastEthernet0/2)
   - Connected **Desktop_2** to **SW1** (FastEthernet0/3)
   - Connected **Laptop_1** to **SW2** (FastEthernet0/2)
   - Connected **Laptop_2** to **SW2** (FastEthernet0/3)
   - Connected **SW1** to **R1** (FastEthernet0/1 → FastEthernet0/0)
   - Connected **SW2** to **R1** (FastEthernet0/1 → FastEthernet0/1)

### Part 2: Configuring the Router (R1)

I accessed the router's CLI and configured both interfaces:

```
R1> enable
R1# config t
R1(config)# interface FastEthernet0/0
R1(config-if)# no shut
R1(config-if)# ip address 192.168.0.1 255.255.255.0
R1(config-if)# exit
R1(config)# interface FastEthernet0/1
R1(config-if)# no shutdown
R1(config-if)# ip address 192.168.1.1 255.255.255.0
R1(config-if)# exit
R1(config)# exit
```

This enabled both router interfaces and assigned IP addresses to serve as default gateways for each subnet.

### Part 3: Configuring End Devices

#### Configuring Desktops (Subnet 1)
- Assigned **Desktop_1** IP address: **192.168.0.10** with subnet mask **255.255.255.0** and default gateway **192.168.0.1**
- Assigned **Desktop_2** IP address: **192.168.0.11** with subnet mask **255.255.255.0** and default gateway **192.168.0.1**

#### Configuring Laptops (Subnet 2)
- Assigned **Laptop_1** IP address: **192.168.1.10** with subnet mask **255.255.255.0** and default gateway **192.168.1.1**
- Assigned **Laptop_2** IP address: **192.168.1.11** with subnet mask **255.255.255.0** and default gateway **192.168.1.1**

### Part 4: Verification

- I waited for all connection indicators to turn **green**, confirming successful link establishment.
- Tested connectivity by pinging between devices:
  - Desktop_1 to Desktop_2 (same subnet)
  - Laptop_1 to Laptop_2 (same subnet)
  - Desktop_1 to Laptop_1 (across subnets via router)
- All ping tests were successful, confirming proper network configuration.

### Reflection

- I learned how to properly enable router interfaces using the `no shutdown` command.
- Understood how IP addressing works across multiple subnets and the importance of matching default gateways to router interface IPs.
- The router successfully routed traffic between the two subnets, allowing devices on different networks to communicate.
- All devices successfully communicated within and across networks, and the lab was completed with **100% success**.

**IP Address Ranges Used:**  
- Subnet 1: 192.168.0.0/24 (Desktops)  
- Subnet 2: 192.168.1.0/24 (Laptops)
