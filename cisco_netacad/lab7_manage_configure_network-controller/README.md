# Laboratory 7 – Deploy and Monitor a Network Using a Network Controller

## Overview
This activity simulates a real-world scenario of deploying a **Network Controller** to centrally manage an enterprise network.  
Using Packet Tracer, I configured the controller, authenticated devices, ran automated discovery, and validated how newly added devices appear in the management dashboard.

A Network Controller provides:
- Centralized monitoring
- Automated device discovery
- Credential-based access for configuration
- A GUI for simplified network visibility and management
- API capabilities (beyond scope, but present in real controllers)

---

## Objectives
1. Deploy and configure a Network Controller on a live network.
2. Test host-to-controller connectivity.
3. Access and configure the controller through its GUI.
4. Connect new wireless devices (creating credentials) and observe how the controller discovers them. 
5. Add a new switch, observe how the controller automatically detects it, and understand host management.

---

# Part 1: Deploy a Network Controller

## Connect the Network Controller to Office-SW1
1. Located the preconfigured **Network Controller** inside the Wiring Closet.  
2. Moved it onto the rack and powered it on.
3. Connected **Network Controller G0** to **Office-SW1 Gi1/0/19** using a **copper straight-through cable**.  
   This establishes the controller’s management link to the LAN.
4. Configured global settings:  
   - **Default Gateway:** 192.168.20.1  
   - **DNS Server:** 192.168.20.126  
5. Configured **GigabitEthernet0**:  
   - IPv4: **Static**  
   - Address: **192.168.20.5**  
   - Subnet Mask: **255.255.255.128**

This establishes the controller as a reachable management device on the Management VLAN (VLAN 20).

---

# Part 2: Verify Connectivity

1. On **Office-Admin PC**, opened: **Laptop and Command Prompt**
2. Ran `ipconfig` to confirm the PC received a proper IP address.  
3. Used `ping 192.168.20.5` to test reachability to the Network Controller.  
   - **Expected:** 4 successful replies  
   This verifies that the PC and Controller are on the same routed network.

## Device Discovery

### Step 1: Access the Network Controller GUI
1. On the Laptop → **Desktop → Web Browser**  
2. Navigate to: `http://192.168.20.5`  
3. Registered a new user 
4. Log in using the newly created account.

---

### Step 2: Create a Credentials List
These credentials allow the controller to log into devices during discovery.

1. Navigate to:  
- **Dashboard → Provisioning → CREDENTIALS**
2. Click **+ CREDENTIAL**  
3. Enter the following: username, password, enable password (may be different from the password previously), and its description
  
This provides the controller with SSH/console login details required for CDP-based discovery.

---

### Step 3: Create a Discovery Process
1. Navigate to:  
- **Provisioning → DISCOVERY**
2. Click **+ DISCOVERY**
3. Configure the new discovery profile:
- **Discovery Type:** CDP  
- **Name:** Office – LAN  
- **IP Address:** 0.0.0.0  
    Instructs the controller to scan the entire local network)
- **CLI Credential List:** `student – Student Profile`  (username - description)
4. Click **ADD**
5. Wait for the discovery to complete.  
6. Select **Office – LAN** to view discovered devices.  
7. Some devices display multiple entries due to **multiple interfaces advertising CDP information**.

Return to the **Dashboard** to observe network conditions.

---

# Part 3: Add a New Network Device to the Office Network

### Step 1: Deploy the New Switch (Office-SW2)
1. Connect the new switch: **Office-SW2 Gi0/1 to Office-SW1 Gi1/0/5**  using  **Copper Straight-Through**  
2. Open **Laptop → Desktop → Terminal**  
3. Access the CLI of **Office-SW2**  
4. Press Enter and apply the following configuration:
            `enable
            configure terminal
            hostname Office-SW2
            interface vlan 20
            ip address 192.168.20.7 255.255.255.128
            no shut
            enable secret Cisco123
            username student privilege 1 password StudentPass
            line vty 0 4
            login local
            interface range g0/1-2
            switchport mode trunk
            switchport trunk native vlan 20
            interface range f0/1-24
            switchport mode access
            switchport access vlan 2
            vlan 2 name UserNetwork
            vlan 20 name Management
            end
            copy run start`
   
This config correctly places the switch into VLAN 20 for management and prepares its trunk/access ports.

---

### Step 2: Review the Network via the Controller
1. Log back into the **Network Controller GUI**.  
2. Go to: **Dashboard → Provisioning → DISCOVERY**  
3. Check the **Office – LAN** discovery list; Office-SW2 will NOT appear yet.  
4. Click **START** to manually re-run the discovery process.  
5. Once finished, open **Office – LAN** again or check the **Dashboard**.  
6. Confirm that **Office-SW2** now appears in the list of discovered devices.

This simulates how newly added infrastructure is integrated into a controller-managed network.

---

# Learning Insights
- Learned how to deploy a Network Controller and integrate it into a managed VLAN.  
- Understood how discovery credentials allow controllers to authenticate into switches/routers.  
- Practiced configuring a CDP-based discovery process to populate the controller database.  
- Observed real-time updates as a new network switch was added to the topology.  
- Gained knowledge in comparing pre- and post-discovery states to verify network.  

---

# Summary
This lab demonstrated the complete workflow of deploying and using a Network Controller.  
From initial installation and IP configuration, through device discovery, to adding new infrastructure—this simulation reflects how modern enterprise networks are centrally monitored and maintained using controller-driven architectures.
