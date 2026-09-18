# Mitnick Attack Lab

## Project Overview

The Mitnick Attack Lab was a hands-on network security project where I studied how a TCP session hijacking attack can be carried out against systems that rely on trusted-host authentication. The lab was completed in a controlled Docker environment where different containers represented systems communicating across a network.

The main purpose of the project was to understand how weaknesses in older trust-based authentication methods could allow an attacker to impersonate another system. Instead of only learning about TCP spoofing and session hijacking from a textbook, this lab allowed me to work directly with network packets and observe how the attack worked.

## Lab Environment

The lab used multiple Linux-based Docker containers to simulate different computers on the same network. The environment included systems representing the attacker, the target, and a trusted host.

Using separate containers made it possible to observe communication between the systems while keeping the attack isolated inside a controlled lab environment.

Some of the main technologies used during the lab included:

- Docker
- Linux
- Python
- Scapy
- Wireshark
- TCP/IP
- rsh
- .rhosts

## Understanding the Attack

The attack focused on a trust relationship between systems using the `rsh` protocol. With this type of configuration, a system can allow another trusted computer to execute commands without requiring the normal username and password authentication process.

This creates a security risk if an attacker is able to make network traffic appear as if it came from the trusted system.

The goal of the lab was to study how an attacker could take advantage of this trust relationship by observing network communication and then creating spoofed TCP packets.

## Packet Sniffing and Traffic Analysis

One of the first parts of the lab involved monitoring network traffic between the systems.

I used Python and Scapy to capture and inspect TCP packets traveling across the lab network. This allowed me to examine important information contained inside the packets, including source and destination addresses, TCP flags, ports, and sequence numbers.

Understanding the TCP sequence numbers was especially important because TCP uses them to keep track of the order of data being transmitted between two systems.

For a spoofed packet to be accepted as part of a TCP connection, the packet has to contain information that the receiving system expects.

This part of the project gave me more experience reading TCP packet information and understanding how systems maintain TCP sessions.

## TCP Packet Spoofing

After examining the network traffic, I worked with Scapy to create custom packets.

The spoofed packets were created so that they appeared to originate from a trusted system instead of the attacker's machine. This demonstrated how changing information inside network packets can be used to impersonate another host.

Working with Scapy allowed me to better understand packet construction because I was able to work directly with different fields contained inside IP and TCP headers instead of relying only on normal network applications.

This part of the lab helped connect concepts such as:

- Source IP addresses
- Destination IP addresses
- TCP ports
- TCP flags
- Sequence numbers
- Acknowledgment numbers
- Packet spoofing

## Exploiting the Trusted rsh Relationship

The next part of the project focused on the `rsh` trust relationship.

Because the target system trusted another host, the attack demonstrated how spoofed network communication could be used to take advantage of that trust.

By manipulating the TCP communication and making packets appear to come from the trusted system, I was able to demonstrate remote command execution against the target inside the controlled environment.

This showed why authentication based mainly on trusting another machine can be dangerous. If an attacker can successfully impersonate the trusted host, the target may accept communication that should not normally be authorized.

## Demonstrating Persistent Access

The lab also demonstrated how an attacker could attempt to maintain access after successfully executing a command.

I worked with the `.rhosts` configuration to demonstrate how trusted access could be modified on the target system.

Creating the `.rhosts` entry showed how a successful network attack could potentially lead to a larger security issue if the attacker is able to change system configuration after gaining access.

This part of the lab helped me understand the difference between initially gaining access to a system and establishing a method that could allow continued access afterward.

## Using Wireshark to Verify the Attack

Wireshark was also used throughout the project to examine the network communication between the Docker containers.

I used packet captures to look at the TCP traffic and compare what was happening during different stages of the attack.

Wireshark helped me visually examine the packets involved in the communication and verify that the traffic being generated matched what I expected to see.

Using both Scapy and Wireshark was useful because Scapy allowed me to work with and create packets while Wireshark allowed me to analyze those packets and see how they appeared on the network.

## Security Concepts Demonstrated

This project covered several important networking and cybersecurity concepts, including:

- TCP session hijacking
- IP spoofing
- Packet sniffing
- Packet spoofing
- TCP sequence numbers
- TCP acknowledgments
- Trusted-host authentication
- Remote command execution
- Linux networking
- Network traffic analysis
- Persistence
- Network security monitoring

## Skills and Technologies

**Operating Systems and Environments**
- Linux
- Docker

**Networking**
- TCP/IP
- TCP Connections
- TCP Sequence Numbers
- IP Addressing
- Network Traffic Analysis

**Security**
- TCP Session Hijacking
- Packet Sniffing
- Packet Spoofing
- Trusted-Host Authentication
- Network Attack Analysis

**Tools**
- Python
- Scapy
- Wireshark
- rsh

## What I Learned

The Mitnick Attack Lab gave me a much better understanding of how TCP communication works at the packet level. Before completing the project, I understood concepts such as TCP connections, IP addresses, and ports, but this lab allowed me to see how those concepts can become important during an actual network security attack.

I also learned why TCP sequence numbers and acknowledgment numbers are important for maintaining a connection and why an attacker attempting to spoof TCP communication needs to understand the state of the connection.

The project also demonstrated the security problems that can come from relying too heavily on trusted-host relationships. A system should not assume that network traffic is safe only because it appears to come from a trusted IP address or computer.

Overall, the lab strengthened my experience with Linux networking, Python, Scapy, Wireshark, TCP/IP, packet analysis, and network security.

## Disclaimer

This project was completed in an isolated and controlled lab environment as part of cybersecurity education and training. The techniques demonstrated in this repository were used only to understand network security vulnerabilities and defensive security concepts.
