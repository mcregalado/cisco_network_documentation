# Laboratory 8 – Troubleshoot a Wireless Connection

## Overview
This lab focused on diagnosing and resolving wireless connectivity issues in a small network.  
Using several end devices (PC3, PC4, Laptop2, and Laptop1), I verified connectivity using command-line tools, validated wireless settings, and corrected the misconfiguration preventing Laptop1 from joining the wireless network.

The troubleshooting process included:
- Testing basic network reachability  
- Using `ping` and `tracert` to identify failures  
- Checking DHCP-assigned addresses and default gateways  
- Verifying wireless SSID/security settings
- Updating the wireless configuration on the affected laptop  

---

## Objectives
1. Test and validate wired and wireless connectivity using command-line tools.  
2. Identify devices with proper network access versus those with connectivity issues.  
3. Use `ipconfig` to verify addressing and gateway configuration.  
4. Use a browser to confirm simulated external connectivity.  
5. Correct wireless settings on Laptop1 to join the “Academy” SSID successfully.

---

# Part 1: Verify Device Connectivity

## Step 1: Test Connectivity with web browser
Using **PC3**, **PC4**, and **Laptop2**, I opened their respective web browser and searched the site, `www.cisco.pka`

### Observations
- **PC3, PC4, and Laptop2** all responded successfully as all three devices were able to open **www.cisco.pka** in a web browser.

These results confirmed proper network operation for most devices.

---

# Part 2: Identify the Problem Device

**Laptop1** failed connectivity tests:
- Could not ping the website 
- `tracert` stopped at the first hop  
- Browser could not load **www.cisco.pka**

### Checking Baseline Configuration
Running `ipconfig` on **Laptop2** (a working device) showed:
- **Default Gateway:** `192.168.1.1`  

This baseline helped identify what Laptop1 *should* have been receiving.

---

# Part 3: Troubleshoot Wireless Settings on Laptop1

## Step 1: Use the Gateway in PC3’s Browser

To confirm the router’s accessibility, I went to PC3, opened the browser, entered: `http://192.168.1.1`
The page loaded successfully, so I was able to check the wireless configuration network for its password.

## Step 2: Inspect Laptop1’s Wireless Settings
Laptop1 showed:
- Not connected to the Academy SSID  
- Missing wireless password  
- No default gateway address (due to authentication failure)

## Step 3: Apply the Fix
To correct the issue:
1. Selected the **Academy** network  
2. Entered the WPA2 password from the website previously
3. Allowed the system to reconnect and obtain a valid IP address

Laptop1 successfully connected afterward.

---

# Part 4: Confirm Restored Connectivity

After correcting the wireless settings:
- `ping 192.168.1.1` succeeded  
- `tracert` displayed normal routing  
- Browser could access **www.cisco.pka**  

Connectivity was fully restored.

---

# Learning Insights
- Practiced using essential troubleshooting tools (`ping`, `tracert`, `ipconfig`).  
- Learned how incorrect wireless passwords prevent DHCP from assigning addresses.  
- Strengthened diagnostic skills by comparing working and non-working devices.  
- Reinforced the importance of verifying SSID and WPA2 credentials in Wi-Fi troubleshooting.  

---

# Summary
In this lab, I located and resolved a wireless connectivity problem affecting Laptop1.  
By comparing device configurations, verifying gateway reachability, and correcting the wireless credentials for the **Academy** SSID, I restored full network function.  
