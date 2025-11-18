# Laboratory 7 – Router Configuration Using an External End Device

## Objective
In this activity, I configured a “special” 1841 router using an external device while most configuration options were intentionally disabled. The purpose was to determine how to access the router, activate its interfaces, solve connection issues, and apply basic security settings.

## Network Setup
- **1 × 1841 Router** (R)
- **1 × 2960 Switch** (SW)
- **3 × Desktop PCs:** Head_Office, Staff_1, Staff_2
- **1 × Laptop:** Admin
- The 1841 used in this activity behaves differently from standard routers, requiring special access steps.

### IP Addressing
- Staff_1: **192.168.2.11**
- Staff_2: **192.168.2.12**
- Head_Office: **192.168.1.10**
- Router Interfaces:
  - F0/0 : **192.168.1.1**
  - F0/1 : **192.168.2.1**

## Configuration Steps

1. **Connect the Devices**
   - Staff desktops connected to the switch.
   - Switch connected to Router F0/1.
   - Head_Office desktop connected to Router F0/0.
   - Admin laptop connected via console to access the router.

2. **Identify the Problem**
   - The router’s graphical configuration tabs were disabled.
   - The only way to configure R was through the Admin laptop’s Terminal.
   - This simulates real-life router configuration via a console cable.

3. **Configure Router Interfaces**
   - Accessed the CLI through Admin → Terminal.
   - Manually configured IPs and enabled the interfaces.
   - This resolved the “red cable” connection issues caused by disabled ports.

4. **Add Security to the Router**
   - Applied a console password and an enable secret using the following commands:
     ```
     config t
     line vty 0 4
     password computer123
     login
     enable secret computer123
     end
     exit
     exit
     ```

## Reflection Questions & Answers

### **1. How many times do you need to send packets between Head_Office and Staff_2 before it succeeds? Why?**
It takes several attempts (around 3–5 tries) because the router must complete ARP first before forwarding packets.

### **2. How many times do you need to send packets between Staff_1 and Staff_2 before it succeeds? Why?**
It works on the second attempt because the first ping is used for ARP, and the next one succeeds. End devices must learn each other's MAC addresses through ARP before successful communication.

### **3. What shows in the Admin’s Terminal when accessing the router? Does it show the password as you type?**
You see standard router prompts (`R>`, `R#`). Passwords do not show while typing — not even asterisks — for security reasons.

### **4. What is so “special” about a 1841 router?**
The 1841 router in this activity:
- Has disabled GUI configuration tabs, and
- Can only be configured through the console, simulating real-world scenarios where physical access is required.

### **5. What password shows when using `enable secret`?**
It appears as an encrypted hash, not the actual password. Cisco automatically encrypts enable secret passwords for security.

## Summary
Through this activity, I learned how to:
- Configure a router entirely through console access  
- Understand ARP behavior when testing network connectivity  
- Activate router interfaces and correct link issues  
- Apply router security settings using VTY passwords and enable secrets  
- Work with a limited-function “special” router model  
