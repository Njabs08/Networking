# Office-p2p-network.pkt
Peer-to-peer office network simulation using Cisco Packet Tracer

# Peer-to-Peer Office Network — Cisco Packet Tracer
A simulated inter-office network connecting two branch offices using a single router, built and tested in Cisco Packet Tracer.

# Project Overview
This project demonstrates a basic peer-to-peer office network where two offices which are Administrative Office and IT office with different IP addressing schemes communicate through a centrally connected router. It covers core networking concepts including IP addressing, subnetting, inter-LAN routing, and end-to-end connectivity verification.

# NETWORK TOPOLOGY

ADMINISTRATIVE OFFICE1 (192.168.4.0/24)           IT OFFICE (10.0.0.0/16)
 ─────────────────────────                        ───────────────────────
  [PC1]  [PC2]   [PC3]                                 [PC4]   [PC5]
    \       |       /                                   \        /
     [─── SW1 ───]                                     [─── SW2 ───]
            |                                               |
       Gi0/0 │                                          │ Gi0/1
                    └──────── [R1] ────────────┘
                              Router

# IP Addressing Table
Device  Interface  IP Address    Subnet Mask     Default Gateway    

R1        Gi0/0    192.168.4.1   255.255.255.0     — 
R1        Gi0/1    10.0.5.1      255.255.0.0       —
PC1        Fa0     192.168.4.10  255.255.255.0    192.168.4.1  
PC2        Fa0     192.168.4.20  255.255.255.0    192.168.4.1
PC3        Fa0     192.168.4.35  255.255.255.0    192.168.4.1 
PC4        Fa0     10.0.5.20     255.255.0.0      10.0.5.1
PC5        Fa0     10.0.5.21     255.255.0.0      10.0.5.1


# Connectivity Tests
Verified end-to-end connectivity using (ping ) from the PC Command Prompt:
Source   Destination       Result   
PC1      192.168.4.20      Success
PC1      192.168.4.35      Success
PC1      10.0.5.20         Success
PC1      10.0.5.21         Success
PC4      192.168.4.10      Success

# Tools Used
Cisco Packet Tracer
Cisco 2911 Router
Cisco 2960-24TT Switches

# Concepts Demonstrated
IPv4 addressing and subnetting (/24 and /16)
Default gateway configuration
Inter-LAN routing via a single router
Layer 2 switching (no VLAN configuration required)
End-to-end connectivity verification using ping


# 👤 Author
Njabulo Prince Tshuma
BYU Pathway Student — BYU Pathway Worldwide
GitHub: Njabs08
