# Laboratory 3 – Modify and Test a Security Camera IoT Device

## Overview
In this lab, I modified a **Security Camera** IoT device to add motion detection, updated its icons, copied and edited programming code from a Motion Detector, and registered it with a remote IoT Registration Server for monitoring.

---

## Objectives
1. Modify the Security Camera icon and behavior  
2. Copy and edit programming code for motion detection  
3. Register the device with the IoT Registration Server  
4. Test activation and monitoring from a Tablet  

---

# Part 1: Modify Your Thing

## Step 1: Save the Device Icon
Save the camera image from the instructions file for use as the activated icon.

## Step 2: Add Additional Icon
1. Open **Security Camera, Config, Advanced, then Thing Editor**.  
2. Click **New** and select the saved image for the activated state.  
3. In **Rules**, add two entries:
   - **LOW:** inactive icon  
   - **HIGH:** activated icon

## Step 3: Copy Code from Motion Detector
1. Add a **Motion Detector** and open **Programming to main.js**  
2. Copy all code, then delete the Motion Detector.

## Step 4: Paste and Edit Code in Security Camera
1. Create a new project: **Security Camera**  
2. Paste the copied code into **main.js**  
3. Change `type: "Motion Detector"` to `type: "Security Camera"`  
4. Click **Run**

---

# Part 2: Test Your Modified Thing

## Step 1: Register with IoT Server
1. In **Security Camera, Config, and IoT Server**, select **Remote Server**  
2. Enter:
   - **Server Address:** 203.0.0.3  
   - **Username/Password:** home  
3. Click **Connect**

## Step 2: Monitor from Tablet
1. Open **Tablet, Desktop, Web Browser, then home.com**  
2. Log in with **home/home**  
3. Expand **Security Camera** in IoTServer → Devices  
4. Hold **Alt** and hover over the camera to simulate motion:
   - Icon changes to red-dot (activated)  
   - Status turns green, then back to red after no motion  

---

# Learning Insights
- Customizing IoT icons for active/inactive states  
- Copying and modifying JavaScript code for device functionality  
- Registering IoT devices with a remote server  
- Observing real-time monitoring and control in a smart home simulation

---

# Summary
Modifying the Security Camera to detect motion, updated icons, edited code, and registered it with the IoT Server.  
The device successfully responded to motion events, having real-time monitoring and control in a simulated smart home environment.
