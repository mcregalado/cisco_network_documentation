# Laboratory 1 – Computer Networking and Security

## Objective
In this lab, I built a simple network to understand the basics of device connectivity and switch configurations in a LAN environment.

## Network Setup
- Two **2950T-24 switches** (S1 and S2) are used to connect multiple end devices.
- **End Devices Connected to S1:**  
  - PC_1 (PC-PT)  
  - PC_2 (PC-PT)  
  - PC_3 (PC-PT)  
- **End Devices Connected to S2:**  
  - Laptop L1 (Laptop-PT)  
  - Laptop L2 (Laptop-PT)  
  - Laptop L3 (Laptop-PT)  
- The two switches (S1 and S2) are connected to each other to allow communication between all devices in the network.

## Configuration Steps
1. **Connect End Devices to Switches**  
   - PCs were connected to switch S1 using Ethernet cables.  
   - Laptops were connected to switch S2 using Ethernet cables.  

2. **Connect Switches Together**  
   - S1 and S2 were linked with a straight-through Ethernet cable to enable inter-switch communication.  

3. **Verify Connectivity**  
   - Checked that all PCs and Laptops can communicate across the network using `ping` commands.  
   - Confirmed IP addressing and network connectivity for each device.  

## Reflection
- Learned the importance of proper switch connections in a LAN.  
- Observed how devices on different switches can communicate through inter-switch links.  
- Gained hands-on experience with basic Ethernet connectivity and verifying network communication in a simulated environment.
