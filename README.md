# Mitnick Attack Lab

## Project Overview

The Mitnick Attack Lab was a cybersecurity project that helped me understand how TCP session hijacking and trusted-host attacks can work in a controlled network environment. For this lab, I worked with Docker containers to simulate different systems on a network and examined how an attacker could take advantage of a trusted connection between two machines.

## What I Did

During the lab, I used Python and Scapy to work with network packets and monitor TCP communication between systems. I performed packet sniffing to capture network traffic and examined TCP sequence numbers that were needed to create spoofed packets.

I then used packet spoofing to simulate traffic coming from a trusted system. The lab involved working with the rsh protocol and trusted-host authentication to demonstrate how weaknesses in this type of configuration could allow remote commands to be executed on another system.

I also created a `.rhosts` entry during the controlled lab to demonstrate persistent trusted access. Wireshark was used to examine the network traffic and verify what was happening throughout different stages of the attack.

## Skills and Technologies

- Docker
- Linux
- Python
- Scapy
- Wireshark
- TCP/IP
- Packet Sniffing
- Packet Spoofing
- TCP Sequence Numbers
- TCP Session Hijacking
- rsh
- Network Security

## What I Learned

This project gave me a better understanding of how TCP connections work and how attackers can take advantage of trust relationships between systems. It also gave me more hands-on experience with packet analysis, network traffic, Linux networking, and tools such as Scapy and Wireshark.

The lab also showed me why properly securing trusted connections and monitoring network traffic are important parts of protecting a network.

## Disclaimer

This project was completed in a controlled lab environment for educational and cybersecurity training purposes.
