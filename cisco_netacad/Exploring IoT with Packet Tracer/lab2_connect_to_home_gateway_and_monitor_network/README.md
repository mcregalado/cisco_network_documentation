# Laboratory 2 – Connect to a Home Gateway and Monitor Network

## Overview
In this lab, I expanded a small home network by adding a Home Gateway, several end-user devices, and multiple IoT devices—both wired and wireless.  
I also integrated Bluetooth devices into the environment and verified that all components successfully registered with the Home Gateway’s IoT server.

This lab simulated a real home setup where multiple technologies coexist: wired Ethernet, Wi-Fi, DHCP, and Bluetooth. Using the Tablet’s IoT Monitor, I confirmed device registration and tested interactions between the newly deployed smart devices.

---

## Objectives
1. Connect a Home Gateway to the existing home network  
2. Add wireless end-user devices  
3. Connect and configure wired and wireless IoT devices  
4. Add and pair Bluetooth devices to extend the home environment  

---

# Part 1: Connect a Home Gateway to the Network

## Step 1: Add a Home Gateway
I began by adding a **Home Gateway** from the Wireless Devices section into the logical workspace.

- After placing it, I opened **Home Gateway0 → Config**  
- Updated the **Display Name** to: `Home Gateway`

This ensured proper identification within the activity.

## Step 2: Connect the Home Gateway to the Cable Modem
Using a **Copper Straight-Through** cable:

- Connected **Cable Modem Port 1 to the Home Gateway Internet port**

This simulated the WAN connection that provides Internet access for the home network.

---

# Part 2: Add End User Devices to the Network

## Step 1: Add a Wireless Tablet
I added a **Tablet PC** and renamed it to: **Display Name:** `Tablet`

## Step 2: Connect the Tablet to the Home Wi-Fi Network
Initially, the Tablet showed a cellular data connection through the cloud.

To connect it to the home network:
1. Opened **Config to Wireless0**  
2. Changed the **SSID** from `Default` to `HomeGateway`  
3. Waited for the device to receive an IP address

The Tablet now had **two active wireless connections** — cellular and Wi-Fi, just like real smart devices.

## Step 3: Verify Access to the Home Gateway
Through the Tablet:
- Opened **Desktop to IoT Monitor**
- Logged in using:
  - **Username:** admin  
  - **Password:** admin  

The login succeeded, confirming that the Tablet could communicate with the IoT server.  
At this point, the device list was empty, as no IoT devices had been added yet.

---

# Part 3: Connect IoT Devices to the Network

## Step 1: Add a Wired IoT Device (Lamp)
I added a **Lamp** from the Home device list and prepared it for wired networking.

Configuration steps:
1. **Advanced to I/O Config**  
   - Set **Network Adapter: PT-IOT-NM-1CFE**  
2. **Config to Display Name:** `Lamp`
3. **FastEthernet0 to DHCP**  
4. Connected **Lamp FastEthernet0 → Home Gateway Ethernet port** using a Copper Straight-Through cable

The lamp received an IP address and became reachable on the network.

## Step 2: Add Wireless IoT Devices (Fan and Door)
Next, I added two more IoT devices: **Fan** and **Door**. Both were renamed accordingly.

Under **Wireless0**, I confirmed:
- SSID was already set to **HomeGateway**
- Each device had received an IP address

## Step 3: Register All IoT Devices to the Home Gateway
For each device (Lamp, Fan, Door):
- Opened **Config to Settings**
- Set **IoT Server:** `Home Gateway`

This step ensured that the Home Gateway’s IoT Monitor recognized and managed them.

## Step 4: Verification
Using the **Tablet go to IoT Monitor**, I logged in again.

All three devices appeared: **Lamp**, **Fan**, and **Door**

I expanded each entry to view details and confirmed I could remotely toggle and interact with their functions in the workspace.

---

# Part 4: Add Bluetooth Devices

## Step 1: Add a Bluetooth Speaker
I added a **Bluetooth Speaker** to the workspace.

After placement:
- It automatically connected to the Home Gateway Wi-Fi
- Received an IP address
- I renamed it to **Speaker**
- Under **Config to Bluetooth**, I enabled **Port Status: On**

## Step 2: Add a Portable Music Player
I added a **Portable Music Player** next.

Just like the speaker:
- It auto-connected to the Home Gateway
- Received an IP address
- I renamed it: **Music Player**

## Step 3: Pair the Music Player to the Speaker
Steps taken:
1. Enabled Bluetooth on the **Music Player**  
2. Clicked **Discover**, selected **Speaker**, clicked **Pair**, then confirmed **Yes**
3. Held **Alt + clicked Music Player** to test playback

The device successfully paired and interacted through Bluetooth.

---

# Part 5: Explore the Network
To further explore the smart home:
- I added additional wired and wireless devices  
- Used **Alt + click** to toggle IoT devices  
- Used the **IoT Monitor** on both the Tablet and Smartphone to control devices remotely  

I was able to:
- Open the Door  
- Turn on the Lamp  
- Turn on the Fan  
- Start the Music Player via Bluetooth  

This provided a realistic simulation of managing a growing IoT smart home environment.

---

# Summary
In this lab, I built and expanded a functional home network by integrating a Home Gateway, IoT devices, user devices, and Bluetooth components.  
By configuring SSIDs, DHCP, IoT server registration, and Bluetooth pairing, I created a complete and responsive smart home ecosystem.

The IoT Monitor allowed centralized control, and hands-on interaction with both wired and wireless devices reinforced how real smart homes operate behind the scenes.
