# PFSense as A Router & Firewall

## Introduction

In this project, I launch an instance of PFSense to use as a firewall and router. I host a Kali VM and an Ubuntu VM on two different internal networks:

<b>Kali VM:<b> 192.168.56.150/24 || <b>Ubuntu VM:<b> 192.168.56.150/24


##### In this lab I demonstrate two main things: 
  - PFSense serves as a router and allows the Kali Machine to talk to the Ubuntu machine even though it is on a different network. This is because PFSense is the default gateway for the Kali Machine
  - PFSense can block or allow traffic, in this case, specifically to the Ubuntu machine


## Birds Eye View
<img width="1536" height="1024" alt="Network topology with pfSense firewall" src="https://github.com/user-attachments/assets/b3ce0126-b52c-4315-9d5d-e6a1f81976f2" />

<p>
  <img width="773" height="865" alt="Pfsense router over kali" src="https://github.com/user-  attachments/assets/1af553c5-a8e4-4b4e-bda6-e53973d883f5" />
</p>


##### Step 1 (Not Pictured) 
  - Place the Kali Machine on the same subnet as the PFSense firewall
  - In this case they are both on the 192.168.56.0 network

    


## Conclusion

In this project, 
