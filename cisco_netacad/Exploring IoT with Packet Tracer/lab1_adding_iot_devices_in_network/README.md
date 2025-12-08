# Laboratory 1 – Explore and Expand a Smart Home IoT Network

## Overview
In this lab, I worked inside a simulated smart home environment equipped with a Home Gateway, wireless devices, and a growing set of IoT appliances.  
My objective was to explore the existing home network, inspect how devices connect and communicate, and then expand the system by adding new wireless and wired IoT components.

Throughout the activity, I interacted with the devices using their interfaces, the Home Gateway dashboard, and physical/wireless connection settings. I also validated connectivity by confirming that newly added devices appeared and responded under the IoT device manager.

---

## Objectives
1. Explore and understand an existing Smart Home IoT network.  
2. Add and configure wireless IoT devices.  
3. Add and configure wired IoT devices.  
4. Verify that all new devices successfully register with the Home Gateway.

---

# Part 1: Explore the Existing Smart Home Network

## Step 1: Exploring the Available IoT Devices
I began by opening the **End Devices to Home** category in Packet Tracer.  
A wide variety of IoT devices appeared such as smart lamps, garage doors, thermostats, environmental monitors, appliances, sensors, and more.

Hovering over each device displayed its description, helping me understand the roles each could play in an automated home system.

## Step 2: Exploring the Smart Home Layout
The logical workspace contained a fully built smart home with devices pre-installed.

- When I hovered over devices like the **Smart Fan**, a pop-up appeared showing key network information (IP, MAC, IoT Server).
- I could toggle devices on and observe real-time behavior such as lights switching, fans enabling, and doors opening.

### Inspecting the Home Gateway
I opened the **Home Gateway** and moved to the **Config to LAN** tab to review core settings:
- **Home Network IP:** (recorded for later login)
  
Then in **Wireless**, I captured:
- **SSID**
- **WPA2-PSK passphrase**

These credentials were important when adding wireless IoT devices later.

### Using the Tablet for Dashboard Access
Using the **Tablet**, I opened the browser and entered the Home Gateway’s IP address.  
After logging in with:
- **Username:** `admin`  
- **Password:** `admin`

I accessed the centralized IoT management panel.  
Here I viewed each smart device and could remotely toggle states such as:
- Opening/closing the **Garage Door**
- Turning the **Smart Lamp** on/off
- Activating appliances

This dashboard served as the main verification tool throughout the lab.

---

# Part 2: Add Wireless IoT Devices to the Smart Home Network

## Step 1: Adding the Wind Detector
I placed a **Wind Detector** from the IoT device menu into the workspace.

Inside the configuration:
- Set **Display Name:** `Wind Detector`
- Set **IoT Server:** `Home Gateway`
- Under **Wireless0**, I entered:
  - **Authentication:** WPA2-PSK  
  - **Passphrase:** (previously recorded)

After a few seconds, the Wind Detector formed a wireless link with the Home Gateway.

## Step 2: Verification
Returning to the **Tablet to Home Gateway Dashboard**, I refreshed the device list.  
A new entry labeled **Wind Detector** appeared at the bottom—indicating the wireless device successfully joined the network.

---

# Part 3: Add Wired IoT Devices to the Smart Home Network

## Step 1: Cabling the Lawn Sprinkler
Next, I added a **Lawn Sprinkler** to the workspace.

In **Advanced to I/O Config**:
- I changed the network adapter to **PT-IOT-NM-1CFE**, enabling a FastEthernet port.

Then, using a **Copper Straight-Through cable**, I connected:
- **Lawn Sprinkler FastEthernet0 to Home Gateway Ethernet port**

## Step 2: Configuring the Sprinkler
Within the configuration:
- Set **Display Name:** `Smart Sprinkler`
- Set **IoT Server:** `Home Gateway`
- Set **FastEthernet0 → DHCP**

The sprinkler immediately requested an IP address.

## Step 3: Verification
Back in the Home Gateway dashboard, **Smart Sprinkler** appeared in the device list.  
It took a moment to populate, but once it did, it confirmed successful wired connectivity.

---

# Part 4: Add a Water Level Monitor

## Step 1: Installing and Configuring the Water Meter
I added a **Water Level Monitor** and opened its configuration settings.

Changes made:
- **Display Name:** `Water Meter`
- **IoT Server:** `Home Gateway`
- Under **Wireless0**:
  - Verified **SSID = HomeGateway**
  - Entered the wireless passphrase
  - Ensured DHCP was enabled

In **I/O Config**:
- Set **Digital Slots = 1**
- Set **Usage = Component**

## Step 2: Creating the Sensor Link
Using the **IoT Custom Cable**, I connected:
- **Smart Sprinkler D0 → Water Meter D0**

This simulated a physical sensor connection between the two devices.

## Step 3: Verification
Using the **Smartphone** this time, I logged into the Home Gateway’s dashboard.

The newly added **Water Meter** appeared under the IoT devices list, confirming it successfully joined the network and linked to the sprinkler.

---

# Part 5: Additional Device Expansion
After completing the required tasks, I experimented with adding more smart devices—thermostats, smart doors, lighting controls—to further test how quickly they joined the Home Gateway and how they responded to dashboard commands.

---

# Learning Insights
- Exploring a detailed IoT ecosystem and understanding how devices authenticate and register with a controller.  
- Learned how wireless IoT devices rely on SSID and WPA2 passphrase for successful connections.  
- Practiced cabling and configuring wired IoT devices and ensuring DHCP functioned properly.  
- Understanding of how IoT sensors interact using digital I/O connections such as the Water Meter to Smart Sprinkler link.

---

# Summary
In this lab, I explored an existing Smart Home network, interacted with devices, and expanded the network with new wireless and wired IoT components.  
By correctly configuring network credentials, cabling devices, and verifying connectivity through the Home Gateway dashboard, I successfully integrated the **Wind Detector**, **Smart Sprinkler**, and **Water Meter** into the smart home ecosystem.

The activity demonstrated how home IoT devices communicate, authenticate, and respond to centralized control, providing a realistic simulation of modern smart home integration workflows.
