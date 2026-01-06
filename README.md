# pfSense as a Router & Firewall

## Introduction

In this project, I deploy an instance of **pfSense** to act as both a **router** and a **firewall**.  
I host a **Kali Linux VM** and an **Ubuntu VM** on two separate internal networks to demonstrate routing and traffic control.

**Kali VM:** 192.168.56.150/24  
**Ubuntu VM:** 192.168.57.150/24

### Lab Objectives
In this lab, I demonstrate two key concepts:

- **Routing:** pfSense allows the Kali VM to communicate with the Ubuntu VM even though they are on different networks, because pfSense is configured as the **default gateway**.
- **Firewalling:** pfSense can **allow or block traffic** between networks using firewall rules.

---

## Bird’s Eye View

<img width="1536" height="1024" alt="Network topology with pfSense firewall" src="https://github.com/user-attachments/assets/b3ce0126-b52c-4315-9d5d-e6a1f81976f2" />

---

## Step 1 — Assign a Static IP to the Kali VM

- Assign the **Kali VM a static IP address** on the **same network as pfSense**.
- Configure the **pfSense LAN IP** as the **default gateway** for the Kali VM.

<img width="873" height="963" alt="Kali static IP configuration" src="https://github.com/user-attachments/assets/6e054333-0e9e-4fb3-bcc7-297d7e69ff1e" />

---

## Step 2 — Assign a Static IP to the Ubuntu VM

- Create a **separate private network** for the Ubuntu VM.
- Assign the Ubuntu VM a static IP address.

**Ubuntu IP:** 192.168.57.150/24

<img width="763" height="547" alt="Ubuntu machine on different subnet" src="https://github.com/user-attachments/assets/77472e11-d78a-4fc2-b2f4-7ca483aceb82" />

---

## Step 3 — Ping the Ubuntu VM from Kali

- From the Kali VM (192.168.56.150), ping the Ubuntu VM (192.168.57.150).
- Observe that traffic successfully reaches the Ubuntu VM even though it resides on a different subnet.

**Reason:**  
pfSense is acting as a **router** and has connectivity to both networks, allowing it to forward traffic between them.

<img width="616" height="337" alt="Kali can ping Ubuntu without firewall rules" src="https://github.com/user-attachments/assets/5291dbd3-a253-4cb0-9611-7e566066e600" />

---

## Step 4 — Add Firewall Rules to Block Traffic

- In the pfSense web interface, create a firewall rule to **block ICMP traffic**:
  - **Source:** 192.168.56.0/24
  - **Destination:** 192.168.57.0/24
  - **Protocol:** ICMP

<img width="1785" height="866" alt="pfSense blocks ICMP traffic between subnets" src="https://github.com/user-attachments/assets/eb725b15-a494-4ec8-aba9-dc4e5e21df42" />

---

## Step 5 — Verify Traffic Is Blocked

- Attempt to ping the Ubuntu VM from the Kali VM again.
- The traffic is now **blocked** due to the firewall rule.
- pfSense matches the rule against traffic originating from the 192.168.56.0/24 network and **drops the packets**.

<img width="916" height="129" alt="After firewall rule no traffic passes through" src="https://github.com/user-attachments/assets/0c454748-b3cd-4419-8342-3208318be304" />

---

## Conclusion

In this project, I demonstrated:

- How **pfSense firewall rules** can allow or block traffic between networks
- How pfSense can function as a **router** when configured as the **default gateway**
- How network segmentation and firewall controls can be enforced in a virtual lab environment
