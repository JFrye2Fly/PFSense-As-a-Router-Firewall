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
<hr> 
<br> 

### Step 1 
  - Give the **Kali machine a static IP** on the **same network as the PFSense** firewall
  - Then make the PFSense instance the **default gateway for the Kali Machine**

<br> 
  <img width="773" height="865" alt="Pfsense router over kali" src="https://github.com/user-attachments/assets/828d7c12-3c4b-43bd-8099-3ece78f05848" />
<br>


## Conclusion

In this project, 
