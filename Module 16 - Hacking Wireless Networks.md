# Hacking Wireless Networks

- Wireless networks uses radio-wave transmission, which usually occurs at physical layer of the network structure.

### <u>Wireless Concepts</u>
![Wireless Terms](/images/wireless_terms.png)

![Wireless IEEE](/images/wireless_ieee.png)

### Wi-Fi Authentication Modes
- Open system authentication process
- Shared key authentication process
- Centralized Authentication Server (RADIUS)
  ![image](https://github.com/user-attachments/assets/1a834362-ad5c-4d03-a0ce-01734ddc7ff3)

### Types of wireless antennas
- Directional Antenna
- Omnidirectional Antenna

## Wireless Encryption

### Types of Wireless Encryption
- **WEP (Wired Equivalent Privacy)** : old wireless security standarad.
- **TKIP (Temporal Key Integrity Protocol** : Security protocol used in a WPA as a replacement for WEP.
- **WPA (Wi-Fi Protected Access)** : Advanced wireless encryption protocol using TKIP and message Integrity Check (MIC) to provide strong encryption and authentication.
- **WPA2** : upgarde to WPA using AES.
- **WPA3**: Third generation Wi-Fi security protocol that provides new features.
- **EAP** : Extensible Authentication Protocol (EAP) supports multiple authentication methods, such as token cards, Kerberos, and certificates.
- **LEAP** : Lightweight EAP developed by cisco.
- **PEAP** (Protected Extensible Authentication Protocol) : protocol that encapsulates the EAP within an encrypted and authenticated Transport Layer Security (TLS) tunnel.

![image](https://github.com/user-attachments/assets/096506d9-f323-478a-9351-a16cc954496f)


### Wroking of WAP and WAP2 
![image](https://github.com/user-attachments/assets/086a3f73-234b-4bca-9e74-52c098ca277f)

The three phases of WAP/WAP2 are as follows:
- **Discovery:** Three messages are sent during the discovery phase. The STA advertises security capabilities and negotiates cipher suites with the AP.
- **Authentication:** In the authentication phase, the STA and AP agree on the master key (MK) and derive the pairwise master key (PMK) based on the MK. In the PSK mode, the MK is obtained from the pre-shared password, but in the enterprise model, the MK is created by the AS and securely provided to the AP and STA through RADIUS and 802.1X, respectively.
- **Key management:** Using the four-way handshake, both parties generate the pairwise temporal key (PTK) and confirm possession of the same PTK. The PTK is unique in each association since it is derived from the PMK and two random numbers are picked by each side for a particular association.

### Working of WPA3
The WPA3 have these four phases:
1. **Authentication process**: A variety of Extensible Authentication Protocol (EAP) mechanisms are used.

2. **Authenticated encryption process**: Advanced Encryption of at least 128 bits Standard Counter Mode with Cipher Block Chaining Message Authentication (AES-CCMP 128)

3. **Key derivation and confirmation process**: Hashed Message Authentication Mode (HMAC) of at least 256 bits using Secure Hash Algorithm (HMAC-SHA256)

4. **Robust management frame protection process**: Broadcast/Multicast Integrity Protocol Cipher-based Message Authentication Code of at least 128 bits (BIP-CMAC-128)

### Comparison of WEP, WPA, WPA2 and WPA3
![image](https://github.com/user-attachments/assets/7be33f66-7cd6-4729-8abf-d3103ba15810)

## Wireless Threats
### Access control Attacks:
- WarDriving : Detecting the publicliy available WIFI connections.
- Roque Access Point: This is the fake access point created by hacker in any organization without knowing to them.
- MAC spoofing
- AP misconfiguration
- Ad hoc associations
- Promiscuous client
- Client Mis-association
- Unauthorised association


### Integrity Attacks:
### Condifentiality Attacks:
### Availability Attacks:
### Authentication Attacks:

Popular Attacks:
- Roque Access Point Attack:
- Client Mis-association
- Misconfigured AP attack
- Unauthorized association
- Ad-Hoc Connection Attack
- Honeypot AP Attack
- AP MAC spoofing
- Denial-of-service Attack
- 



### 

## Abbrevations:
- GSM - Global System for Mobile Communications (GSM)
- ISM - Industrial, scientific, and medical (ISM) band
- SSID - Service set identifier
- BSSID - Basic service set identifier
- OFDM - Orthogonal frequency divison multiplexing
- DSSS - Direct-sequence spread spectrum
- FHSS - Frequency-hopping spread spectrum


## Bluetooth Hacking

- **Bluesmacking**:
  -  A Bluesmacking attack occurs when an attacker sends an oversized ping packet to a victim's device, causing a buffer overflow.
  -  This is similar to ping-of-death ICMP attack.
- **Bluejacking**: Sending a message to the victim using bluetooth without his/her constent.
- **Bluesnarfing**: Bluesnarfing is a method of gaining access to sensitive data in a Bluetooth-enabled device.
- **Bluesniff**: (operates in Linux)
  - Bluesniff is a proof-of-concept code for bluetooth war driving utility.
  - useful for finding hidden and discoverable bluetooth devices.
-  **Bluebugging**:
  - In this attack, attacker gains remote access to a target bluetooth enabled device without the victim's awareness.
- **BluePrinting**:
  - It's a foot printing technique performed by an attacker to determine the make and model of the target bluetooth device.
- **Btlejacking**:
  - This is detrimental to Bluetooth low energy (BLE) devices.
  - The attacker can sniff, jam and take control of the data transmission between BLE devices by performing an MITM attack.
  - Succesful attempt, will bypass the security mechanisms and listen to the information being shared.
- **KNOB Attack**:
  - A Key Negotiation of Bluetooth (KNOB) attack enables an attacker to breach Bluetooth security mechanisms and perform am MITM attack on paired devices without being traced.
  - A KNOB attack is especially detrimental to two Bluetooth-enabled devices sharing encrypted keys.
- **MAC Spoofing Attack**:
  - attacker spoof the mac address of target bluetooth-enabled device.
  - To intercept or manipulate the data sent to the target device.

### Bluetooth Reconnaissance Using BlueZ
### Btlejacking uisng BtleJack
### Cracking BLE Encryption Using Crackle


### [Table Of Contents](https://karsyboy.github.io/CEHv10_Ultimate_Study_Guide/)
