# PFSense as A Router & Firewall

## Introduction

In this project, I launch an instance of PFSense to use as a firewall and router. I host a Kali VM and an Ubuntu VM on two different internal networks:

<b>Kali VM:<b> 192.168.56.150/24 || <b>Ubuntu VM:<b> 192.168.56.150/24


##### In this lab I demonstrate two main things: 
  - PFSense serves as a router and allows the Kali Machine to talk to the Ubuntu machine even though it is on a different network. This is because PFSense is the default gateway for the Kali Machine
  - PFSense can block or allow traffic, in this case, specifically to the Ubuntu machine


## Birds Eye View
<br>
  <img width="1536" height="1024" alt="Network topology with pfSense firewall" src="https://github.com/user-attachments/assets/b3ce0126-b52c-4315-9d5d-e6a1f81976f2" />
<br>

<br> 
<br> 
<hr> 
<br> 
 

### Step 1 
  - Give the __Kali machine a static IP__ on the **same network as the PFSense** firewall
  - Then make the PFSense instance the **default gateway for the Kali Machine**

<br> 
 <img width="873" height="963" alt="image" src="https://github.com/user-attachments/assets/6e054333-0e9e-4fb3-bcc7-297d7e69ff1e" />
<br>

### Step 2
  - Make sure you have created a different private network to place your Ubuntu VM.
  - Assign it a static IP. In this case its IP i92.168.57.150.

<p>
<img width="763" height="547" alt="ubuntu machine on different subnet" src="https://github.com/user-attachments/assets/77472e11-d78a-4fc2-b2f4-7ca483aceb82" />
</p>  


### Step 3
  - From your Kali Machine (192.168.56.150) ping the Ubuntu machine (192.168.57.150)
  - Notice how traffic can successfully be sent to the Ubuntu machine even though it is on a different network.
  - **This is because our PFSense instance has internet access directly linked from our host computer so it send traffic outside of its own LAN.**

<p>
<img width="616" height="337" alt="Kali can ping Ubuntu without firewall rules" src="https://github.com/user-attachments/assets/5291dbd3-a253-4cb0-9611-7e566066e600" />
</p>  




## Conclusion

In this project, 
