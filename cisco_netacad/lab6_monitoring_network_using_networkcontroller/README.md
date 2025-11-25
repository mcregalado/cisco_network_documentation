# Laboratory 6 - Monitor Your Network Using a Network Controller

## Overview
This activity demonstrates how to use a **Network Controller** to manage, monitor, and document network devices using a desktop's graphical user interface (GUI).

A Network Controller allows administrators to:
- Monitor network performance
- View device information
- Discover new hosts
- Manage devices through centralized provisioning and dashboards

---

## Objectives
1. Implement a Network Controller in an existing network.
2. Verify connectivity between a host and the Network Controller.
3. Access and explore the Network Controller GUI.
4. Discover newly connected hosts and examine changes in the controller.

---

# Part 1: Implement a Network Controller

## Connect the Network Controller to switch: Office-SW1
1. In the **Wiring Closet**, locate the preconfigured Network Controller on the shelf.
2. Had moved the controller to the Rack and powered it on.
3. Connecting the ports **Network Controller G0 and Office-SW1 Gi1/0/19** using a *copper straight-through cable*.

The Network Controller uses the static IP: **192.168.20.5**

---

# Part 2: Verify Connectivity
1. On **Office-Admin PC**, went to **Desktop → Command Prompt**
2. Run: **ipconfig** to ensure the PC has an ip address, the use the command **ping 192.168.20.5** to check the connection of the network controller.

Expected: **4 successful replies**

---

# Part 3: Monitor the Network

## Log into the Network Controller GUI
1. From **Office-Admin**, open **Web Browser**.
2. Navigated to:  `http://192.168.20.5`
3. Logged in using an admin account

### Menu Items Found
- Dashboard  
- Provisioning  
- License  
- Assurance  
- Policy  
- API Docs  

---

# Part 4: Discover New Devices in the Office Network

### A. Check the Initial Host List  
Before adding any new clients, I first confirmed what the Network Controller already recognized some existing devices on the network.

I navigated to:  
- **Assurance → HOSTS**

From here, I observed only the wired office devices—no wireless clients were present yet.

### B. Connect Wireless Devices  
Next, I simulated the process of wireless clients joining an enterprise Wi-Fi network.

For both the **Office Tablet** and **Office Smartphone**, I performed the ff.:

1. Opened the **Config tab** on each device  
2. Selected **Wireless0**  
3. Enabled the interface by setting **Port Status: ON**  
4. Waited for each device to request and receive a DHCP in the **192.168.2.0/24** network  
   - This subnet represents the wireless VLAN segment, similar to a real corporate WLAN  

Once online, both devices behaved as typical Wi-Fi clients joining a managed wireless infrastructure.

### C. Run Network Discovery  
To emulate how enterprise controllers identify newly joined devices, I triggered a manual discovery scan.

Steps:

1. Navigated to:  
   - **Provisioning → DISCOVERY**
2. Selected the existing discovery profile: **Office LAN**
3. Clicked **START** to begin the discovery operation
4. Once the scan completed, the controller reported the Tablet and Smartphone as newly seen devices


### D. View the Updated Host List  
With discovery complete, I returned to:

- **Assurance → HOSTS**

Now the host list correctly displayed both wireless clients with their assigned IPs. This reflects how network assurance systems updates as new hosts authenticate and connect.

### Assigned IP Addresses
- **Office-Tablet:** 192.168.2.14  
- **Smartphone:** 192.168.2.13  

---

# Learning Insights

- Understanding how **network controllers** interface with switches
- Verifying connectivity using basic networking tools (`ping`, `ipconfig`)
- Navigating controller dashboards to interpret device and host information
- Observing real-time host discovery processes
- Understanding how enterprise networks maintain device visibility and management

---

# Summary
This activity shows how modern networks use centralized controllers to simplify monitoring and configuration. 
You connected the controller, validated connectivity, explored monitoring tools, and observed automatic host discovery.



