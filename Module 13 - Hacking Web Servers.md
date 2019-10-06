# Hacking Web Servers

### <u>Web Server Concepts</u>

#### Web Server Operations
 - A web server is a computer System that stores processes and delivers web pages to clients via HTTP 
 - **Components of a Web Server**
   - **Document Root**
     - Store critical HTML files related to the web pages of a domain name that will be served in response to the request
    - **Server Root**
       - Stores servers configuration error executable and log files
    - **Virtual Document Tree**
       - Provides storage on a different machine or disk after the original disk is filled up
    - **Virtual Hosting**
       - Technique of hosting multiple domains or websites on the same server
    - **Web Proxy**
       - Proxy server that sits in between the web client and web server to prevent IP blocking and maintain anonymity

#### Open Source Web Server Architecture
![Web Server Architecture](/images/webserver-arch.png)

#### IIS Web Server Architecture
 - IIS for windows server is a flexible secure and easy to manage web server for hosting anything on the web

![IIS Web Server Architecture](/images/webserver-arch2.png)

#### Web Server Security Issues
 - Attackers usually target software vulnerabilities and configuration errors to compromise web servers
 - Network and OS level attacks can be well defended using proper network security measures such as firewall IDS 
 - Web servers are accessible to the internet which makes them more vulnerable 

#### Why Web Servers are Compromised
![Why Web Servers Are Compromised](/images/webserver-compromised.png)

#### Impact of Web Server Attacks
 - Compromise of user account
 - Website defacement
 - Secondary attack from the website
 - Root access to other applications or servers
 - Data tampering and data theft

### <u>Web Server Attacks</u>

#### DoS/DDoS Attacks
 - Attackers may send numerous fake request to the web server which results in the web server crashing or becoming unavailable to the legitimate users
 - Attacker may target high profile web servers to steal user credentials
#### DNS Server Hijacking
 - Attacker compromises DNS server and changes the DNS settings to that all the request coming towards the target webserver are redirected to the attacker 
#### DNS Amplification Attack
 - Attacker takes advantage of DNS recursive method of DNS redirection to perform DNS amplification attack
 - Attacker uses compromised PCs with spoofed IP address to amplify the DDosS attacks on victims DNS server by exploiting DNS recursive method
#### Directory Traversal Attack	
 - Attackers use ../ to access restricted directories outside of the web server root directory
 - Attacker can use trail and error method to navigate outside of the root directory and access sensitive information in the system
#### Man in the middle / sniffing attack
 - MITM attack allows an attacker to access sensitive information by intercepting and altering communications between and end user and web server
 - Attacker acts as a proxy such that all the communication between the user and the web server passes through the attacker
#### Phishing Attacks
 - Attackers tricks user to submit login details for website that looks legitimate but it redirect to the malicious website hosted on the attacker web server
 - Attacker steals credentials and uses them to impersonate the user
 - Attack can then perform malicious operations
#### Website Defacement
 - Intruder maliciously alters the visual appearance of a web page
 - Defacing pages expose visitors to some propaganda 
 - Attackers us variety of methods such as MYSQL injection to access a site in order to deface it
#### Web Server Misconfiguration
 - Server misconfiguration refers to configuration weaknesses in web infrastructure that can be exploited to launch various attacks on web servers such as directory traversal server intrusion and data theft

![Web Server Misconfiguration](/images/webserver-misconfig.png)

#### HTTP Response splitting attack 
 - Involves adding header response data into the input field so that the server splits the response into two responses
 - The attacker can control the first response to redirect the user to a malicious website whereas the other responses will be discarded by the web browser
#### Web Cache Poisoning Attack
 - Attacks the reliability of an intermediate web cache source
 - Attacker swaps cached content for a random URL with infected content
 - Users of the web cache source and unknowingly use the poisoned content instead of the true content
#### SSH Brute Force Attack
 - SSH protocols are used to create an encrypted SSH tunnel between two hosts in order to transfer un-ecrypted data over and insecure network
 - Attackers brute force the SSH login
 - SSH tunnels are used to transmit malware and other exploits to victims without being detected
#### Web Server Password Cracking
 - Attacker tries to exploit weakness to hack well chosen passwords
 - Many hacking attempts start with password cracking to prove to the web server that you are a trusted user
 - Password can be cracked manually or by using automated tools
#### Web Application Attacks
 - **Parameter/Form tampering**
   - The attacker manipulates the parameters exchanged between client and server in order to modify application data
 - **Cookie Tampering**
   - Sends a modified cookie form the client side to the server
 - **Unvalidated Input and File injection Attack**
   - Unvalidated input and file injection attacks are performed by supplying and Unvalidated input or by injecting files into a web application
 - **SQL Injection Attacks**
   - SQL injection attacks exploits the security vulnerability of a database for attacks. 
   - Attacker injects malicious SQL code into a string that is later sent to the SQL server by the web server
 - **Session Hijacking**
   - Attack in which the attacker exploits steals, predicts and negotiates the real valid web session
 - **Directory Traversal**
   - Attackers can access restricted directories and execute commands outside the web servers root directory by changing the URL
 - **DoS**
   - Overwhelms the server and causes it to stop responding
 - **Cross-Site Scripting (XSS)**
   - Attackers inject HTML tags or scripts into the target website
 - **Buffer Overflow**
   - Attackers flood the application with too much data which in turn cause a buffer overflow attack 
 - **Cross-Site Request Forgery (CSRF)**
   - Attacker exploits the trust of an authenticated user to pass malicious code or commands to the web server
 - **Command Injection**
   - Hackers alter the content of the web page by using HTML code and by identifying the form fields that lack valid constraints
 - **Source code Disclosure**
   - Misconfiguration allow an attacker to access source information of the web application

### <u>Web Server Attack Methodology</u>

#### Information Gathering
 - Collecting information about the target company
 - Use whois to look up information
 - **Roboots.txt File**
   - Contains the list of the web servers directories and files
    - Attackers can use this to retrieve sensitive information such as the root directory structure, content management system information 
#### Web Server Footprinting
 - **Banner Grabbing**
    - Gathers valuable system level data like account details OS software version servername and database scheme
    - Telnet can be used for banner grabbing
 - **Enumerating webserver information using NMAP**
    - Nmap scripting can be used to get information off web servers
#### Website Mirroring
 - Creates a complete profile of the sites directory structure file structure external links, ext.
 - Search for comments and other items in the HTML source code to make footprinting activities more efficient
 - Use tools such as HTTrack, Webcopier Pro, Ect.
#### Finding Default Creds of Web Server
 - Many web servers administrative interfaces are publicly accessible and are located In the web root directory
#### Finding Default Content of web servers
 - Default content and functionalities allow attackers to leverage attacks
 - Check the following default contents
    - Debug and test functionality
    - Sample functionality
    - Powerful functions
    - Installation manuals
#### Finding directory listings of web severs
 - Gives access to the directory listing and allows you to view files in directories
#### Vulnerability Scanning 
 - Identifies weaknesses in a network and determine if the system can be exploited
 - Allows you to find Hosts services and vulnerabilities
 - Test the web server infrastructure for any misconfigurations outdated content and vulnerabilities using vulnerability scanners like acunetic web vulnerability scanner
#### Finding Exploitable vulnerabilities 
 - Search vulnerability databases
#### Session Hijacking
 - Sniff valid session IDs to gain unauthorized access
 - Capture valid session cookies and IDs
#### Web server password hacking 
 - Use brute force dictionary attacks and password guessing
#### Using Application server as a proxy
 - Web servers with forwarding and reverse http proxy functions enable can be used by attackers for the following attacks
    - Attacking third party systems
    - Connection to arbitrary hosts on the orgs network
    - Connection back to other services running on the proxy host itself
 - Attacker use GET and CONNECT request to use vulnerable web servers as proxies to connect and obtain information from target systems through these proxy web servers

### <u>Web Server Attack Tools</u>

#### Metasploit
 - Fully automated exploitation of web servers by using know vulnerabilities 
 - **Metasploit Module**
   - Basic Module of Metasploit used to encapsulate and exploit
   - Comes with simplified meta information fields
   - Using Mixins feature users can also modify exploit behavior dynamically
 - **Payload Module**
   - Payload module establishes a communication channel between the framework and the victim host
   - Combines arbitrary code that is executed as a result of an exploit succeeding
 - **Auxiliary Module**
   - Used to perform arbitrary one-off actions such as port scanning DoS and even fuzzing 
   - To run auxiliary module use run or exploit
 - **NOPS Module**
   - NOP module generate a no operation instruction used for blocking out buffers
   - Use generate command to generate a NOP sled of an arbitrary size and display it in a given format

### <u>Countermeasures</u>

 - Place web servers in separate secure server security segment on network 
 - An ideal web hosting network should be designed with at least three segments 
   - Internet
   - DMZ
   - Internal network
   - DMZ should be isolated from public networks and internal networks

#### Patches and updates
![Patches and updates](/images/webserver-cont1.png)

#### Protocols
![Protocols](/images/webserver-cont2.png)

#### Accounts
![Accounts](/images/webserver-cont3.png)

#### Files and Directories
![Files and Directories](/images/webserver-cont4.png)

#### Detecting Web Server Hacking Attempts
![Detecting Web Server Hacking Attempts](/images/webserver-cont5.png)

#### How to Defend Against Web Server Attacks
![How to Defend Against Web Server Attacks 1](/images/webserver-cont6.png)
![How to Defend Against Web Server Attacks 2](/images/webserver-cont7.png)

#### Defend against DNS Hijacking
![Defend against DNS Hijacking](/images/webserver-cont8.png)

### <u>Patch Management</u>

#### Patches and Hotfixes
 - Hotfixes are an update to fix a specific customer issue  not always distributed outside the customers organization
 - A patch is a small piece of software designed to fix a problem
 - Hotfixes are sometimes combined as a set and called combined hotfixes or service packs
#### What is patch management
 - Process used to ensure that the appropriate patches are installed on a system and help fix known vulnerabilities

#### Installation of a patch
![Installation of a patch](/images/webserver-patch.png)

### [Table Of Contents](https://karsyboy.github.io/CEHv10_Ultimate_Study_Guide/)