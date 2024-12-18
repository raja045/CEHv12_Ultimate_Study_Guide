# Denial of Service Attacks

Seeks to take down a system or deny access to it by authorized users
Botnet - network of zombie computers a hacker uses to start a distributed attack
Can be controlled over HTTP, HTTPS, IRC, or ICQ

## **<u>DoS/DDoS Attack Techniques**

**Basic Categories:**

Volumetric attacks - bandwidth attacks; consume all bandwidth for the system or service

Fragmentation attacks - attacks take advantage of the system's ability to reconstruct fragmented packets
Application attacks - consume the resources necessary for the application to run
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