# Denial of Service Attacks

Seeks to take down a system or deny access to it by authorized users
Botnet - network of zombie computers a hacker uses to start a distributed attack
Can be controlled over HTTP, HTTPS, IRC, or ICQ

## **<u>DoS/DDoS Attack Techniques**

**Basic Categories:**

**Volumetric Attacks:**
 - bandwidth attacks; consume all bandwidth for the system or service
 - User Datagram Protocol (UDP) flood attack
 - Internet Control Message Protocol (ICMP) flood attack
 - Ping of Death (PoD) attack
 - Smurf attack
 - Pulse wave attack
 - Zero-day attack
 - Malformed IP packet flood attack
 - Spoofed IP packet flood attack

**Protocol Attacks:**
- These attacks consume the connection state tables present in network infrastructure devices such as load balancers, firewalls, and application servers.
- So, No new connections will be allowed thereafter.
-  Synchronize (SYN) flood attack
-  Fragmentation attack
-  Spoofed session flood attack
-  Acknowledgement (ACK) flood attack
-  SYN-ACK flood attack
-  ACK and PUSH ACK flood attack
-  TCP connection flood attack
-  TCP state exhaustion attack
-  RST attack
-  TCP SACK panic attack

**Application Layer Attacks:**
- Exploit vulnerabilities in application layer protocol or in the application itself.
- destroy a specific aspect of an application or service and can be effective with one or a few attacking machines that produce a low traffic rate.
-  Hypertext Transfer Protocol (HTTP) flood attack
-  Slowloris attack
-  UDP application layer flood attack
-  DDoS extortion attack

**Attack Techniques**:
- **UDP flood Attack:** spoofed UDP packets at a very high packet rate to a remote host on random ports of a target server by using a large source IP range.
- **ICMP flood Attack:** send large volumes of ICMP echo request packets to a victim’s system directly.
- **Ping of Death Attack:** sending malformed or oversized packets using a simple ping command.
- Example:Suppose an attacker sends a packet with a size of 65,538 bytes to the target web server. This size exceeds the size limit prescribed by RFC 791 IP, which is 65,535 bytes. The reassembly process performed by the receiving system might cause the system to crash. 
- **Smurf Attack:** The attacker spoofs the source IP address with the victim’s IP address and sends a large number of ICMP ECHO request packets to an IP broadcast network.
  - causing significant traffic to the victim’s machine and ultimately making it crash.
- <img width="637" alt="image" src="https://github.com/user-attachments/assets/12abf85d-54f2-4b16-b7a7-423cf16e6c70" />
- Pulse wave DDos Attack
- **Zero-Day DDos Attack:** Exploiting zero day vulnerabilities for DDos Attacks.
- **SYN Flood Attack:** The attacker sends a large number of SYN requests to the target server (victim) with fake source IP addresses.
  - The attack creates incomplete TCP connections that use up network resources.
  - The attacker sends a large number of SYN requests to the target server (victim) with fake source IP addresses. The attack creates incomplete TCP connections that use up network resources.
  - The host keeps track of partially open connections while waiting for response ACK packets in a listening queue.
- **SYN-ACK Attack:**  The attacker exploits the second stage of a three-way handshake by sending a large number of SYN-ACK packets to the target machine to exhaust its resources.
- **Fragmentation Attack:** This attack will destroy a victim's ability to reassemble fragmented packets by flooding it with TCP or UDP packets.
- **Spoofed Session Flood Attack:**
- Attackers create fake or spoofed TCP sessions by carrying multiple SYN, ACK, and RST or FIN packets.
- Attackers employ this attack to bypass firewalls and perform DDoS attacks against target networks, exhausting their network resources. 
- **HTTP GET/POST Attack:**
- <img width="514" alt="image" src="https://github.com/user-attachments/assets/30a1a4d9-2ca1-4c70-a3db-c7c403052279" />
- **Slowloris Attack:**
- Slowloris is a DDos Attack Tool.
- The attacker sends partial HTTP requests to the target web server or application.
- Upon receiving the partial requests, the target server opens multiple connections and waits for the requests to complete.
- However, these requests remain incomplete, causing the target server’s maximum concurrent connection pool to be filled up and additional connection attempts to be denied.
- <img width="591" alt="image" src="https://github.com/user-attachments/assets/38229542-b2d1-4622-80d8-faf4785a27dc" />



To be continued....



Note - application level attakcs are against weak code; application attacks are just the general term
TCP state-exhaustion attacks - go after load balancers, firewalls and application servers
SYN attack - sends thousands of SYN packets to the machine with a false source address; eventually engages all resources and exhausts the machine
SYN flood - sends thousands of SYN packets; does not spoof IP but doesn't respond to the SYN/ACK packets; eventually bogs down the computer, runs out of resources
ICMP flood - sends ICMP Echo packets with a spoofed address; eventually reaches limit of packets per second sent
Smurf - large number of pings to the broadcast address of the subnet with source IP spoofed as the target; entire subnet responds exhausting the target
Fraggle - same as smurf but with UDP packets
Ping of Death - fragments ICMP messages; after reassembled, the ICMP packet is larger than the maximum size and crashes the system
Teardrop - overlaps a large number of garbled IP fragments with oversized payloads; causes older systems to crash due to fragment reassembly
Peer to peer - clients of peer-to-peer file-sharing hub are disconnected and directed to connect to the target system
Phlashing - a DoS attack that causes permanent damage to a system; also called bricking a system
LAND attack - sends a SYN packet to the target with a spoofed IP the same as the target; if vulnerable, target loops endlessly and crashes
Low Orbit Ion Cannon (LOIC) - DDoS tool that floods a target with TCP, UDP or HTTP requests
Other Tools
Trinity - Linux based DDoS tool
Tribe Flood Network - uses voluntary botnet systems to launch massive flood attacks
R-U-Dead-Yet (RUDY) - DoS with HTTP POST via long-form field submissions
