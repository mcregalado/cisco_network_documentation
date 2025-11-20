# Laboratory 2 – Patch Panel and Wall Mount Installation

## **Objective**
Installing and configuring structured cabling components in a simulated office environment. This includes installing a patch panel in the wiring closet, attaching wall mounts in office areas, and connecting additional devices to the network through proper cabling and punchdowns.

---

# Part 1: Installing a Patch Panel in the Wiring Closet

## **Step 1: Patch Panel Installation**
I opened the **Equipment Cabinet** to access the Wiring Closet.  
Then I chose a **Copper Patch Panel**. It organizes and connects the cables between the switch and the wall mounts. I didn’t use a fiber patch panel because all the devices in this lab use copper Ethernet connections. The switch ports, wall mounts, and cables are copper-based, so a copper patch panel is required for proper compatibility. 
I installed it in the rack and ensured it was named **Patch Panel0**.

## **Step 2: Connecting Office-SW1 to Patch Panel0**
I used **Copper Straight-Through** cables from the Cable Pegboard and connected the switch to the patch panel using the following mapping:

| Office-SW1 Port | Patch Panel0 Jack | Color code |
|----------------|-------------------|-------------------|
| G1/0/13        | Jack13            | Green
| G1/0/14        | Jack14            | Yellow
| G1/0/15        | Jack15            | Blue
| G1/0/16        | Jack16            | Red

After wiring, I optionally organized and color-coded the cables, then returned to the Office.

---

# Part 2: Attaching a Wall Mount in the Office

## **Step 1: Wall Mount Installation**
I installed a **Copper Wall Mount** near the Equipment Cabinet.

I used straight-through cables to connect the punchdowns on Wall Mount0 to Patch Panel0:

| Wall Mount0 Punchdown | Patch Panel0 Punchdown |
|-----------------------|------------------------|
| Punchdown1            | Punchdown13            |
| Punchdown2            | Punchdown14            |
| Punchdown3            | Punchdown15            |
| Punchdown4            | Punchdown16            |

## **Step 2: Connecting Office Devices**
I connected the **Office-Admin PC** and **Printer0** to Wall Mount0.  
Both devices received DHCP addressing after I setup in the desktop settings.  
I verified network connectivity by opening the browser on Office-Admin and navigating to **http://office.srv**.

## **Step 3: Cable Organization**
I used bendpoints to neatly route the cables along walls and the floor, preventing them from crossing the room. As well as strictly used different color wires to easily distinguish them.

---

# Part 3: Adding an Additional Wall Mount and More Cabling

## **Step 1: Additional Wiring in the Closet**
I added more cabling between Office-SW1 and Patch Panel0:

| Office-SW1 Port | Patch Panel0 Jack | Color code |
|----------------|-------------------|-------------------|
| G1/0/21        | Jack21            | Green
| G1/0/22        | Jack22            | Yellow
| G1/0/23        | Jack23            | Blue
| G1/0/24        | Jack24            | Red

## **Step 2: Installing the Second Wall Mount**
I installed a second wall mount near the office window and ensured it was named **Wall Mount1**.

I connected it to Patch Panel0 using this mapping:

| Wall Mount1 Punchdown | Patch Panel0 Punchdown |
|-----------------------|------------------------|
| Punchdown1            | Punchdown21            |
| Punchdown2            | Punchdown22            |
| Punchdown3            | Punchdown23            |
| Punchdown4            | Punchdown24            |

## **Step 3: Connecting the Office-User PC**
I connected the Office-User PC to Wall Mount1 using a straight-through cable.  
After receiving DHCP information, I confirmed connectivity by browsing to **http://office.srv**.

## **Step 4: Final Cable Organization**
I added bendpoints to clean up and organize all the new cables.

---

# **Learning Insights**
This lab demonstrated:
- Installing and configuring structured cabling components
- Connecting a patch panel to a network switch
- Adding wall mounts and making punchdown connections
- Connecting office devices through structured cabling
- Verifying network connectivity via DHCP configuration
- Organizing physical cabling using bendpoints
