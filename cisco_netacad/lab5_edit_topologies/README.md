# Laboratory 5 - Office Network Lab – Patch Panel, Wall Mount, and Clusters
---

## Objectives
In this lab, I installed a patch panel and a wall mount, and used them to connect devices in the office to the wiring closet.  
I also worked with clusters to organize devices and added a second home network to the activity.  
The tasks included:  
- Adding an additional switch to the rack in the office network  
- Connecting a PC to the office network  
- Working with clusters  
- Adding a second home cluster and connecting it to the ISP  

---

# Part 1: Add an Additional Switch to the Rack

1. I opened the Wiring Closet and dragged **Office-SW2** from the shelf into the rack.  
2. I connected a **copper straight-through cable** from **FastEthernet 0/1** on Office-SW2 to **Jack 1** on the patch panel. The first cable connects the switch to the office network infrastructure.
      The patch panel acts as a central point where cables from all office devices (like PCs and wall jacks) terminate.
      By connecting the switch to the patch panel, the switch can send and receive data from devices plugged into the office network.
3. I connected another **copper straight-through cable** from **GigabitEthernet 0/1** on Office-SW2 to **GigabitEthernet1/1/1** on Office-SW1. The second cable connects the new switch to the main switch to integrate it into the network.
      This creates a link between the two switches so devices connected to either switch can communicate with each other.
      Essentially, this step extends the network and ensures all devices in the office can share resources, like printers and servers. 

---

# Part 2: Connect a PC to the Office Network

## Step 1: Connect the PC to the Wall Mount
1. I returned to the Office workspace.  
2. I connected **Office-User PC** to **Copper Wall Mount1 → Jack1** using a straight-through cable.
      I did this to physically connect the user’s PC to the office network. The wall mount acts as a convenient endpoint in the office where devices can plug in without running cables directly to the wiring closet.
      This makes the network more organized and accessible for users.
4. I connected **PunchDown1** on Wall Mount1 to **PunchDown1** on the patch panel in the Equipment Cabinet.
       The patch panel serves as the central hub in the wiring closet, linking all office devices to the network switches.
       This allows the PC to communicate with other devices on the network, like servers, printers, and other PCs.

## Step 2: Test Connectivity
1. From **Office-User**, I opened **Desktop → Command Prompt** and pinged **Office-Admin PC (192.168.20.5)** using the command > ping 192.168.20.5.
2. The ping was successful.  
3. I opened a web browser on **Office-User** and accessed **office.srv** to verify connectivity.

---

# Part 3: Work with Clusters


## Step 1: Add Devices
1. I added a **PC**, **Home Gateway**, and **Cable Modem** to the workspace.  

## Step 2: Connect the Devices
1. Connecting **PC0 FastEthernet0 → Home Gateway1 Ethernet1** using copper straight through cable.  
2. Connecting **Home Gateway1 Internet → Cable Modem0 Port1** using copper straight through cable.  

## Step 3: Cluster Devices
 I selected all devices in the second home, clicked **Create New Cluster**, and renamed it **Second Home**.  

## Step 4: Connect the Second Home to the ISP
 Connecting **Cable Modem0 Port0 → ISP Cloud0** using coaxial cable.  

## Step 5: Document Devices
 I used the **Place Note** tool to list all devices added to the **Second Home cluster**.  

---

# Learning Insights
- I learned how to physically connect devices in a structured network using patch panels, wall mounts, and cabling.  
- Creating clusters to logically organize devices for easier management.  
- Conecting multiple networks (Office and Home) to a central ISP.  
- This activity showed the importance of structured cabling, proper device placement, and network organization in both small office and home networks.  
- Using Packet Tracer helped me understand how these concepts apply to real-world office and home network deployments, including troubleshooting connectivity issues and testing configurations before implementation.  

