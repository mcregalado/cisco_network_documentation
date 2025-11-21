# Laboratory 4 – Device Configuration Using the CLI (Console)

## Objectives  
In this activity, I used a console connection cable and the terminal of the laptop to configure a Cisco switch.  
I completed the ff. tasks:
- Connected to the switch using a console cable  
- Configured the device using IOS commands inside the laptop terminal
- Saved the updated configuration of the switch which included: a new hostname and login credentials

---

# Overview
A new switch, **Office-SW2**, is being added to the network. Before deploying a networking device, it must be configured and tested.  
Many networking devices do not come preconfigured, allowing access through Ethernet or wireless, so a **console cable** is used to perform the initial setup.  
In Packet Tracer, this console cable is the **light blue cable**.

---

# Part 1: Connect to the Switch Using a Console Cable

## Step 1: Open the Terminal Emulation Program  
1. I went to the **Desktop** tab of the laptop and opened **Terminal**.  
2. I accepted the default terminal settings and clicked **OK**.  
3. Once the console loaded and displayed **“Press RETURN to get started!”**, I pressed ENTER.

## Step 2: Access Privileged EXEC Mode  
1. At the `Switch>` prompt, I entered `?` to view all available User EXEC commands.  
2. I entered `enable` to move into Privileged EXEC mode: 
        Switch> enable
        Switch#
3. I entered `?` again to view Privileged EXEC commands.  
4. I typed `show running-config` to view the current configuration and used **CTRL+C** to return to the prompt.

---

# Part 2: Configuration Information to the Device

## Step 1: Enter Global Configuration Mode  
1. I entered:  
        Switch# configure terminal
        Switch(config)#

## Step 2: Configuration Commands  
2. I typed the following commands into the switch:

        hostname Office-SW2
        line con 0
        password Cisco123
        login
        end
The output appeared as:

Switch(config)# hostname Office-SW2
Office-SW2(config)# line con 0
Office-SW2(config-line)# password Cisco123
Office-SW2(config-line)# login
Office-SW2(config-line)# end
Office-SW2#
%SYS-5-CONFIG_I: Configured from console by console

## Step 3: Test the New Configuration  
1. I typed `exit` to return to the console login screen.
        User Access Verification
        Password:

2. Typing the password **Cisco123**, and the User EXEC prompt appeared.

---

# Part 3: Save the Updated Configuration to the Device

## Step 1: Enter Privileged EXEC Mode  

        Office-SW2> enable
        Office-SW2#

## Step 2: Save the Running Configuration  
1. Saving the configuration using:  

        Office-SW2# copy running-config startup-config
        Destination filename [startup-config]?
        Building configuration...
        [OK]

2. I then reloaded the switch to verify the configuration persisted:  

        Office-SW2# reload
        Proceed with reload? [confirm]

3. After reboot:
        - I pressed ENTER at “Press RETURN to get started!”
        - The switch displayed the **User Access Verification** message  
        - I entered **Cisco123** and regained access
   
---

# Learning Insight  
- Using a console cable to access and configure a Cisco device that has no prior network setup.
- Entering different IOS modes, applying configuration commands, securing console access, and saving settings to NVRAM.
- This activity gave significance to initial device configuration and how the CLI directly manages and controls network hardware.

