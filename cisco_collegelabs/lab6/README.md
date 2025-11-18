# Laboratory 6 – Router Configuration, IP Addressing, and Default Gateway Implementation

## Objective
In this lab, I configured a small routed network to understand console access, IP addressing, router setup, and the importance of proper default gateway configuration for full network functionality.

## Network Setup
- **1 × 1941 Router** (R1)  
- **1 × 2960 Switch**  
- **3 × Desktop PCs:** HR, Finance, Staff  
- **1 × Laptop:** Admin  
- Devices were renamed for easier identification.

### IP Addressing Used
- Admin Laptop: **192.168.1.5**  
- HR Desktop: **192.168.0.10**  
- Finance Desktop: **192.168.0.11**  
- Staff Desktop: **192.168.0.12**  
- Router G0/0: **192.168.0.1 /24**  
- Router G0/1: **192.168.1.1 /24**

## Configuration Steps
1. **Connect End Devices to the Switch**  
   - HR, Finance, and Staff desktops were connected to the switch’s first three ports.  

2. **Connect Router to the Network**  
   - Router **G0/0** was connected to the switch.  
   - Router **G0/1** was connected to the Admin laptop.  

3. **Access the Router via Console**  
   - The Admin laptop was connected to the router’s console port using a blue console cable.  
   - The terminal was opened to begin router configuration.

4. **Configure the Router**  
   - Set the hostname to `Admin_Router`.  
   - Assigned IP addresses to G0/0 and G0/1 interfaces.  
   - Activated both interfaces using `no shutdown`.  
   - Applied basic console password security.

5. **Configure Default Gateways (Final Step for 100% Completion)**  
   - HR, Finance, Staff desktops were assigned **192.168.0.1** as their default gateway.  
   - Admin laptop was assigned **192.168.1.1** as its default gateway.  
   - This step completed the activity and enabled full network communication.

## Reflection
- Learned how to access and configure a router using a console connection.  
- Understood proper IP addressing and interface activation.  
- Experienced how default gateways allow communication between different networks.  
- Successfully completed the activity with **100% completion** by ensuring all devices had the correct gateway settings.
