### [Table Of Contents](https://karsyboy.github.io/CEHv10StudyGuide/)

# Hacking Mobile Platforms

### <u>Mobile Platform Attack Vectors</u>

#### **OWASP Top 10 Mobile Risks**
  - **M1 - Improper Platform Usage** - misuse of features or security controls (Android intents, TouchID, Keychain)
  - **M2 - Insecure Data Storage** - improperly stored data and data leakage
  - **M3 - Insecure Communication** - poor handshaking, incorrect SSL, clear-text communication
  - **M4 - Insecure Authentication** - authenticating end user or bad session management
  - **M5 - Insufficient Cryptography** - code that applies cryptography to an asset, but is insufficient (does NOT include SSL/TLS)
  - **M6 - Insecure Authorization** - failures in authroization (access rights)
  - **M7 - Client Code Quality** - catchall for code-level implementation problems
  - **M8 - Code Tampering** - binary patching, resource modification, dynamic memory modification
  - **M9 - Reverse Engineering** - reversing core binaries to find problems and exploits
  - **M10 - Extraneous Functionality** - catchall for backdoors that were inadvertently placed by coders

#### **Anatomy of a Mobile Attack**
![Anatomy of a Mobile Attack](/images/mobile_anatomy.png)

#### **Hackers Proffit**   
![Info that Hackers can Exploit](/images/mobile_hacker-profit.png)

#### **Mobile Attack Vectors**
![Attack Vectors](/images/mobile_attack-vectors.png)

#### **Platform Vulnerbilities and Risk**
- **Malicious app in stores** 
  - No vetting of apps
- **Mobile Application vulnerbilities**
- **Mobile Malware**
- **Privacy Issues (Geolocation)**
- **App sandboxing vulnerabilities** 
  - Protects systems and users by limiting the resources that the app can access to the mobile platform
- **Weak data security**
- **Weak device and app encryption**
- **Excessive Permissions**
- **OS and app updates' issues**
- **Weak Communication security**
- **Jailbreaking and rooting**
- **Physical attacks**
- **Mobile Spam**
  - Unsolicited text/email messages sent to mobile devices
  - Can contain ads or malicious links
- **SMS Phishing Attack**
  - Aquire personal and financial information by sending SMS
  - Acts the same as a phishing attack but instead uses SMS
- **Pairing to Open Bluetooth and Wi-Fi Connections**
  - Allows for eavesdrop and interception of data transmission
  - Bluesnarfing and Bluebugging

### <u>Hacking Android OS</u>

- **Android OS Basic Info**
  - Devolped by google
  - **Features**
    - Enabling reuse and replacement of components
    - Variety of pre-build UI components
    - Open source Blink and Webkit engine
    - Media Support
    - Rich development enviorment

![Attack Vectors](/images/mobile_androidos.png)

- **Android Device Administration API** 
  - Allows for security-aware apps that may IT professionals
![Attack Vectors](/images/mobile_androidap1.png)
![Attack Vectors](/images/mobile_androidap2.png)

- **Android Rooting**
  - Allows user to attain privileged control within androids subsystem
  - Involves exokiutubg security vulnerbilities in the device firmware and granting execute permissions
  - **Rooting Tool**
    - **KingoRoot** - can be used with or without a PC
    - **TunesGo - Root Android** - Done with PC
    - **One Click Root** - Done with PC

- **Android Attack Tools**
  - **NetCut** - Wifi killing application; blocks Wifi access to targeted device
  - **zANTI**
    - Spoof MAC
    - Create Malicious Wifi Hotspot
    - Scan for open ports
    - Exploit Router Vulnerabilities
    - Password complexity audits
    - Man-in-Middle attack
    - DoS attaack
  - **Network Spoofer** - Change websites on other peoples computers
  - **Low Orbit Ion Cannon** - Perfrom DoS and DDoS attacks
  - **DroidSheep** - Pefrom web session hijacking
  - **Orbot** - Proxy app that hids identity
  - **FaceNiff** - Sniff and intercept web session profiles
  - **Android Trojans**
    - **BankBot**
    - **SpyDealer**
#### Securing Android Devices
![Securing Android](/images/mobile_android-secure.png)

### <u>Hacking IOS</u>

- **Apple IOS**
  - Apples Mobile OS
  - Uses direct manipulation and multi touch gestures

![IOS Framework](/images/mobile_ios.png)

- **Jailbreaking**
  - Installing a modified set of kernel patches that allows users to run third party applications not singed by OS vendor
  - Provides root access to the OS
  - Removes sandbox restrictions
  - **Types of Jailbreaking**
    - **Userland Exploit** - Allows user-level access
    - **iBoot Exploit** - Allows user-level access and iboot-level access
    - **Bootrom Exploit** - Allows user-level access and iboot-level access
  - **Jailbreaking Techniques**
    - **Untethered Jailbreaking** - Allows the device to reboot and the kernel will still be patched
    - **Semi-tethered Jailbreaking** - If the device reboots the kernel will no longer have a patched kernel but will still be usable for normal functions
    - **Tethered Jailbreaking** - If the device reboots the kernel will no longer have a patched kernel and will get stuck in a partially started state
  - **Jailbreaking Tools**
    - **Cydia** - Enables a user to find and install software packages
    - **Pangu Anzhuang** - Online jailbraking app
    - **Keen Jailbreak** - Unofficial semi-tethered tool
  - **IOS Trojans**
    - **AceDeceiver** - Exploits flaw in DRM (Digitals Rights Management)
    - **Spy/MobileSpy!iPhoneOS** - Malware allows and attacker to eavesdrop all incoming and outgoing communications

#### Securing IOS Devices
![IOS Framework](/images/mobile_ios-secure.png)


### <u>Mobile Device Management</u>
