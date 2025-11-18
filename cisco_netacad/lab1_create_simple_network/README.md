# Laboratory 1 – Simple Network

## Objective
In this lab, I built and configured a simple network in Packet Tracer, connected end devices, and verified connectivity to a server.

## How I Did It

### Part 1: Building the Network
1. **Adding Devices**  
   I added a **PC**, a **Laptop**, and a **Cable Modem** from the Device-Type Selection Box since it was not present at the start of the laboratory.  

2. **Renaming Devices**  
   I updated the display names to PC, Laptop, and Cable Modem.  

3. **Connecting Devices**  
   - Connected the **PC** to the **Wireless Router** using a copper straight-through cable (FastEthernet0 → Ethernet1).  
   - Connected the **Wireless Router** to the **Cable Modem** using a copper straight-through cable (Internet → Port1).  
   - Connected the **Cable Modem** to the Internet Cloud using a coaxial cable (Port0 → Coaxial7).  

### Part 2: Configuring End Devices

#### Configuring the PC (Wired)
- I enabled **DHCP** in the IP Configuration to get an IP automatically.  
- Verified the IP using `ipconfig /all` in the Command Prompt (IPv4 was in the 192.168.0.x range).  
- Tested connectivity by pinging `cisco.srv` and confirmed four successful replies.  

#### Configuring the Laptop (Wireless)
- I powered off the Laptop, removed the Ethernet module, and installed the **Wireless WPC300N** module.  
- Powered the Laptop back on and connected it to the **HomeNetwork** wirelessly.  
- Opened the Web Browser and navigated to `cisco.srv` to verify connectivity.  

### Reflection
- I recorded the IPv4 Address, Subnet Mask, and Default Gateway for both devices.  
- Learned how the **subnet mask** separates network and host IDs and how the **default gateway** routes traffic to external networks.  
- All devices successfully communicated within the network, and the lab was completed with **100% success**.

**IP Address Range Used:** 192.168.0.1 (Laptop) - 192.168.0.2 (PC)
