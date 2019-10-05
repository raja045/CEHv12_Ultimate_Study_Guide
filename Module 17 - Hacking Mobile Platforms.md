### [Table Of Contents](https://karsyboy.github.io/CEHv10StudyGuide/)

# Hacking Mobile Platforms

### <u>Mobile Platform Attack Vectors</u>

### **OWASP Top 10 Mobile Risks**
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

### **Anatomy of a Mobile Attack**
![Anatomy of a Mobile Attack](/images/mobile_anatomy.png)

### **Hackers Proffit**   
![Info that Hackers can Exploit](/images/mobile_hacker-profit.png)

### **Mobile Attack Vectors**
![Attack Vectors](/images/mobile_attack-vectors.png)

### **Platform Vulnerbilities and Risk**
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
