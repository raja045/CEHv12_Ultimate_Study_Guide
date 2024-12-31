# Sniffing 

- **Network Sniffing**
  - Packet Sniffing is the process of monitoring or capturing all the data packets passing through a given network using software or hardware device.
  - A packet sniffing program (also known as a sniffer) can capture data packets only from within a given subnet,
    
- **How Network Sniffing Works?**
  - Sniffer turns the NIC of a system to promiscuous mode, which will let you listen all the traffic passing through it.
  - **Shared Ethernet**
    - Here message will be broadcasted. So, attacker machine has to respond to the message even though mac address does not match with it' own mac address.
  - **Switched Ethernet**
    - Switch is used instead of Hub.
    - Here Switch maintains a table of mac addresses. So, it will not broadcast the messages. It is not possible to sniff the network the above way.
    - "_Switch is secure than hub But it is possible to sniff the network in switch_"
    - How? **ARP Spoofing**: Switch maintains a table of mac address which is called ARP Table / cache.
    - ARP is stateless and a machine can send an ARP reply even without asking for it;
    - We can manipulate the ARP table / cache, it will led to network sniff.
    - **Mac Flooding** : The Switch will have very limited space to store the mac addresses, If attacker can fill it up with fake addresses.
    - Once the space is full, it will behave like a hub.
    - It's easy to sniff network in a hub.

### Types of Network Sniffing
- **Passive Sniffing**
- Passive Sniffing refers to sniffing through hub.
- Hub is outdated approach, Most modern networks use switch.
- **Active Sniffing**
- It is used to sniff the switch-based Network
- It involves injecting Address Resolution Packets into the network to flood the Switch's _Content Addressable Memory(CAM)_ table.

### Protocols Vulnerable to Sniffing
<img width="735" alt="image" src="https://github.com/user-attachments/assets/14c492c7-01d5-4baf-8fb3-6f05ecebc1d9" />

### <u>Protocols Susceptible</u>

- SMTP is sent in plain text and is viewable over the wire.  SMTP v3 limits the information you can get, but you can still see it.
- FTP sends user ID and password in clear text
- TFTP passes everything in clear text
- IMAP, POP3, NNTP and HTTP all  send over clear text data
- TCP shows sequence numbers (usable in session hijacking)
- TCP and UCP show open ports
- IP shows source and destination addresses
---

## Sniffing in Data Link Layer of the OSI Model
- In this layer, data packets are encoded and decoded into bits.
- Sniffers operate at the data link layer and can capture the packets from this layer.

---


### <u>IPv6</u>

- Uses 128-bit address
- Has eight groups of four hexadecimal digits
- Sections with all 0s can be shorted to nothing (just has start and end colons)
- Double colon can only be used once
- Loopback address is ::1

| IPv6 Address Type | Description                                           |
| ----------------- | ----------------------------------------------------- |
| Unicast           | Addressed and intended for one host interface         |
| Multicast         | Addressed for multiple host interfaces                |
| Anycast           | Large number of hosts can receive; nearest host opens |

| IPv6 Scopes | Description                                                  |
| ----------- | ------------------------------------------------------------ |
| Link local  | Applies only to hosts on the same subnet (Address block fe80::/10) |
| Site local  | Applies to hosts within the same organization (Address block FEC0::/10) |
| Global      | Includes everything                                          |

- Scope applies for multicast and anycast
- Traditional network scanning is **computationally less feasible**
  
### <u>ARP</u>

- Stands for Address Resolution Protocol
- Resolves IP address to a MAC address
- Packets are ARP_REQUEST and ARP_REPLY
- Each computer maintains it's own ARP cache, which can be poisoned
- **Commands**
  - arp -a - displays current ARP cache
  - arp -d * - clears ARP cache
- Works on a broadcast basis - both requests and replies are broadcast to everyone
- **Gratuitous ARP** - special packet to update ARP cache even without a request
  - This is used to poison cache on other machines


### <u>Wiretapping</u>

- **Lawful interception** - legally intercepting communications between two parties
- **Active** - interjecting something into the communication. e.g., MITM
- **Passive** - only monitors and records the data. e.g., snooping or eavesdropping
- **PRISM** - system used by NSA to wiretap external data coming into US

### <u>Active and Passive Sniffing</u>

- **Passive sniffing** - watching network traffic without interaction; only works for same collision domain
- **Active sniffing** - uses methods to make a switch send traffic to you even though it isn't destined for your machine
- **Span port** - switch configuration that makes the switch send a copy of all frames from other ports to a specific port
  - Not all switches have the ability to do this
  - Modern switches sometimes don't allow span ports to send data - you can only listen
- **Network tap** - special port on a switch that allows the connected device to see all traffic
- **Port mirroring** - another word for span port

## Sniffing Technique: MAC Attacks

### **MAC  (Media Access Control)** 
- physical or burned-in address - assigned to NIC for communications at the Data Link layer
- 48 bits long
- Displayed as 12 hex characters separated by colons
- First half of address is the **organizationally unique identifier** - identifies manufacurer
- Second half ensures no two cards on a subnet will have the same address
- NICs normally only process signals meant for it
- **Promiscuous mode** - NIC must be in this setting to look at all frames passing on the wire
- **CSMA/CD** - Carrier Sense Multiple Access/Collision Detection - used over Ethernet to decide who can talk
- **Collision Domains**
  - Traffic from your NIC (regardless of mode) can only be seen within the same collision domain
  - Hubs by default have one collision domain
  - Switches have a collision domain for each port
 
### CAM Table
- The table on a switch that stores which MAC address is on which port
- If table is empty or full, everything is sent  to all ports
- This works by sending so many MAC addresses to the CAM table that it can't keep up
- If a CAM Table is full, then switch will start behave like a hub.
  
### <u>MAC Flooding</u>
- Filling the CAM Table with fake make addresses can be called as Mac Flooding.
- Switches either flood or forward data
- If a switch doesn't know what MAC address is on a port, it will flood the data until it finds out.
- **Tools**
  - Etherflood
  - Macof
- **Switch port stealing** - tries to update information regarding a specific port in a race condition
- MAC Flooding will often destroy the switch before you get anything useful, doesn't last long and it will get you noticed.  Also, most modern switches protect against this.

## Sniffing Technique: DHCP Attacks

### Working of DHCP
<img width="817" alt="image" src="https://github.com/user-attachments/assets/1080baf6-f167-4584-8c4f-bbb3ec497088" />


### <u>DHCP Starvation Attack</u>

- Attempt to exhaust all available addresses from the server
- Attacker sends so many requests that the address space allocated is exhausted
- DHCPv4 packets - DHCPDISCOVER, DHCPOFFER, DHCPREQUEST, DHCPACK
- DHCPv6 packets - Solicit, Advertise, Request (Confirm/Renew), Reply
- **DHCP Steps**
  1. Client sends DHCPDISCOVER
  2. Server responds with DHCPOFFER
  3. Client sends request for IP with DHCPREQUEST
  4. Server sends address and config via DHCPACK
- **Tools**
  - Yersinia
  - DHCPstarv
- Mitigation is to configure DHCP snooping

### Rogue DHCP Server Attack
- setup a fake server which is not in control of network administrator
- to offer IP addresses instead of real server.
- This attack can take advantage of the DHCP starvation attack and make it more sophisiticated.
  
## Sniffing Technique: ARP Attacks

### <u>ARP Poisioning</u>

- Also called ARP spoofing or gratuitous ARP
- This can trigger alerts because of the constant need to keep updating the ARP cache of machines
- Changes the cache of machines so that packets are sent to you instead of the intended target
- **Countermeasures**
  - Dynamic ARP Inspection using DHCP snooping
  - XArp can also watch for this
  - Default gateway MAC can also be added permanently into each machine's cache
- **Tools**
  - Cain and Abel
  - WinArpAttacker
  - Ufasoft
  - dsniff
<img width="733" alt="image" src="https://github.com/user-attachments/assets/22012653-4447-43c4-992a-088ee5cf550e" />
---
- **How to Defend against the ARP Spoofing**
  - Implementation of Dynamic ARP Inspection. (DAI)
  - DAI validates the ARP packets using DHCP snooping binding table.
  - DHCP snooping should be enabled before DAI.
---

### <u>Other Spoofing Attacks</u>

- **MAC Spoofing** - changes your MAC address.  Benefit is CAM table uses most recent address.
- Port security can slow this down, but doesn't always stop it
- MAC Spoofing makes the switch send  all packets to your address instead of the intended one until the CAM table is updated with the real address again
- **IRDP Spoofing** - hacker sends ICMP Router Discovery Protocol messages advertising a malicious gateway

### Sniffing Technique: DNS Poisoning
- **DNS Poisioning** - changes where machines get their DNS info from, allowing attacker to redirect to malicious websites.
- DNS Poisoning is possible using the following techniques:
  - Intranet DNS Poisoning
  - Internet DNS Poisoning
  - Proxy Server DNS Poisoning
  - **DNS Cache Poisoning** - DNS cache poisoning refers to altering or adding forged DNS records in the DNS resolver cache so that a DNS query is redirected to a malicious site.

### <u>Sniffing Tools</u>

- **Wireshark**
  - Previously known as Ethereal
  - Can be used to follow streams of data
  - Can also filter the  packets so you can find  a specific type or specific source address
  - **Example filters**
    - ! (arp or icmp or dns) - filters out the "noise" from ARP, DNS and ICMP requests
    - http.request - displays HTTP GET requests
    - tcp contains string - displays TCP segments that contain the word "string"
    - ip.addr==172.17.15.12 && tcp.port==23 - displays telnet packets containing that IP
    - tcp.flags==0x16 - filters TCP requests with ACK flag set
- **tcpdump**
  - Recent version is WinDump (for Windows)
  - **Syntax**
    - tcpdump flag(s) interface
    - tcpdump -i eth1 - puts the interface in listening mode
- **tcptrace**
  - Analyzes files produced by packet capture programs such as Wireshark, tcpdump and Etherpeek
- **Other Tools**
  - **Ettercap** - also can be used for MITM attacks, ARP poisoning.  Has active and passive sniffing.
  - **Capsa Network Analyzer**
  - **Snort** - usually discussed as an Intrusion Detection application
  - **Sniff-O-Matic**
  - **EtherPeek**
  - **WinDump**
  - **WinSniffer**

### [Table Of Contents](https://karsyboy.github.io/CEHv10_Ultimate_Study_Guide/)
