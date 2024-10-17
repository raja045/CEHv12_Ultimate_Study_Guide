# Hacking Web Applications

## <u>Web App Concepts</u>

 - Provide an interface between the end users and webservers
 - Used to support critical business functions

<img width="775" alt="image" src="https://github.com/user-attachments/assets/b4588943-a79f-4c31-888a-4d9213ba1c4e">


#### Web Application Architecture
 - Clients or Application Layer
 - Business layer: Web Server logic layer and Bussiness logic layer
 - Database layer
<img width="807" alt="image" src="https://github.com/user-attachments/assets/f1fe19ba-f661-4d7d-993b-e02770f03c1d">


#### Web 2.0 Applications
 - Web applications that provide and infrastructure

#### Vulnerability Stack
![Vulnerability Stack](/images/webapp-vuln_stack.png)

## <u>Web App Threats</u>
![OWSAP-10-Blog-Post--OM-Networks](https://github.com/user-attachments/assets/042232bc-dfa3-45f4-9cd8-989647c1f98e)

### A01 Broken Access Control
 - Access control is broken and allows an attacker to act as users or administrators.

#### common vulnerabilities associated with the access control are as follows:
- Gaining permission to read or modify someone's account through their unique idenitifer.
- Abusing the Least privileges.
- Gaining access to the APIs without the access controls for PUT, POST, and DELETE.
- Escalating privileges, where a user can act as an administrator after logging in. 
<img width="764" alt="image" src="https://github.com/user-attachments/assets/7614a3b7-6c93-4ae9-8790-3eede684064b">

#### More Resources:
- https://owasp.org/Top10/A01_2021-Broken_Access_Control/
- https://portswigger.net/web-security/access-control


### A02 Cryptographic Failures / Sensitive Data Exposure
- Web applications use cryptographic algorithms to encrypt data and other sensitive information that they need to transfer from the server to the client or vice versa. Sensitive data exposure occurs because of flaws such as insecure cryptographic storage and information leakage.


### A03 Injection Flaws
 - Allow untrusted data to be interpreted and executed as part of a command or query
 - Done be constructing malicious commands or queries
 - Prevalent in legacy code
 - **Types of Injection Flaw attacks**
   - SQL Injection
   - Command Injection
   - LDAP Injection
   - Cross-site Scripting(XSS)
#### SQL Injection 
 - Series of malicious SQL queries that manipulate the database
 - Allows you to bypass normal security measures and obtain access to the valuable data
 - Can often be executed from the address bar
 - **Example of an SQL injection**
   - Test’) ;DROP TABLE Messages;--
 <img width="748" alt="image" src="https://github.com/user-attachments/assets/ed26987e-2b05-4dfe-bc07-9d8d7130bc8c">

#### Command Injection 
 - **Shell injection**
   - Crafts an input string to gain shell access to a web server
   - Functions include system(),StartProcess(), java.lang.runtime.exec(), system.diagnostics.process.start(), and similar APIs

![Web App Shell Injection](/images/webapp-shellinjection.png)

 - **HTML Embedding**
   - Used to deface websites virtually
   - Allows attacker to add extra HTML based content to the vulnerable web application
 - **File Injection**
   - Allows injection of malicious code into system files

![Web App File Injection](/images/webapp-fileinjection.png)

#### LDAP Injection
 - Exploit users parameters
 - Allows you to pass LDAP filters used to search the Directory services to obtain direct access to databases behind the LDAP tree
 - To test send an LDAP query to a server that generates an invalid input if the LDAP server returns an error it can be exploited

![Web App LDAP Injection](/images/webapp-ldap1.png) ![Web App LDAP Injection](/images/webapp-ldap2.png)

#### Other Injection Attacks
- Server-side JS Injection
- Server-side Includes Injection
- Server-side Template Injection
- Log Injection
- HTML Injection
- CRLF Injection
- JNDI Injection

#### Cross-Site Scripting (XSS)
 - Exploits vulnerabilities in dynamically generated web pages
 - Allows attackers to inject client side scripts into web pages viewed by other users
 - Occurs when invalidated input data is included in dynamic content 
 - Can inject malicious scripts or web content by hiding it within legitimate requests

 <img width="813" alt="image" src="https://github.com/user-attachments/assets/01dd4911-7fbd-403a-84a9-dd9ac9aa0881">


### A04 Insecure Design
- Attackers often attempt to exploit poorly implemented APIs, which fail to filter requests properly. They search for weak APIs that are not integrated with security gateways to differentiate malicious inputs. Then, they attach malicious code to a vulnerable API.

<img width="804" alt="image" src="https://github.com/user-attachments/assets/16c2299c-7cb9-4724-809c-f9b7a9c0d127">

### A05 Security Misconfiguration
 - Can occur on any level of an application stack
 - **Unvalidated Inputs**
   - Input from a client is not validated
 - **Parameter/Form Tampering**
   - Manipulation of parameters exchanged between client and server in order to modify data
 - **Improper Error Handling**
   - Gives insight into source code 
 - **Insufficient Transport Layer Protection**
   - Supports weak algorithms and uses expired or invalid certificates
 - **Bypassing**
   - An attacker may bypass the need to choose between two accounts by adding another account in the HTML page source code. The web browser displays       the new combo box, and the attacker can choose the new account.
     
### XML External Entity (XXE)
 - Server-side request forgery (SSRF) attack where an application is able to parse XML input from an unreliable source because of the misconfigured XML parser
 - Attacker send malicious XML input containing reference to an external entity to the victim web application
 - Allows attackers to access protected files and services

![Sensitive Data Exposure](/images/webapp-xxe.png)

### A06 Vulnerable and Outdated Components/Using Components with Known Vulnerabilities
- attackers tries to find the outdated softwares, and exploit them with know vulnerabilities listed on exploit sites such as Exploit Database (https://www.exploit-db.com), CXSecurity (https://cxsecurity.com), and Zero Day Initiative (https://www.zerodayinitiative.com). 

### A07 – Identification and Authentication Failures/Broken Authentication

 - Uses vulnerbilites in the authentication or session manager functions 
 - **Session ID in URLS**
   - Attacker sniffs the network traffic and is able to acquire a session ID
 - **Password Exploitation**
   - Gains access to the web applications password database
 - **Timeout Exploitation**
   - It the timeouts are not set right and a user does not log out on a public computer the computer and be used to re open that session later.
     
#### Sensitive Data Exposure
 - Many web applications do not protect their sensitive data properly
 - Application uses poorly written encryption code 
 - Allows an attacker to steal or modify weakly protected sensitive data

![Sensitive Data Exposure](/images/webapp-sensitivedata.png)







#### Insecure Deserialization
 - Process of liberalizing and demineralizing data objects
 - Attackers inject malicious code into serialized data
 - Insecure deserialization the malicious serialized content along with the injected malicious code
#### Using Components with Known Vulnerabilities
 - Uses libraries and frameworks that have known vulnerabilities
#### Other Web Application Threats
![Other Threats](/images/webapp-otherthreats.png)

#### Directory Traversal
 - Allows an attacker to access restricted directories
 - Can manipulate variables using ../ variations
#### Unvalidated Redirects and Forwards
 - Allow attackers to install malware or trick victims 
#### Watering Hole Attack
 - Identifies the site frequently surfed by victims
 - Finds vulnerabilities in this site and exploits these vulnerabilities 
#### Cross-Site Request Forgery (CSRF)
 - Exploits web page vulnerabilities that allow an attacker to force an unsuspected users browser to send malicious requests the did not intend
 - Done by victim holding an active session visiting a malicious site which injects an HTTPP request which compromised the trusted sites integrity
#### Cookie/Session Poisoning
 - Modification of the contents of a cookie in order to bypass security mechanisms
 - Proxy can be used to specify new user ID or other session identifiers

#### Web Services Architecture
![Web Services Architecture](/images/webapp-arch.png)

 - **SOAP (Simple Object Access Protocol)**
   - An XML based protocol that allows application running on a platform to communicate with applications running on a different platform
 - **UDDI**
   - Universal Description, Discovery, and Integration (UDDI) is a directory service that lists all services available
 - **WSDL**
   - Web Services Description Language is an XML based language that describes and traces web services
 - **WS-Security**
   - WS-Security plays an important role in securing the web services. WS is an extension to SOAP and aims at maintaining the integrity and confidentiality of SOAP messages and authenticating user

#### Web Service Attack
 - Web Services are based on XML protocols such as WSDL for describing the connection points; UDDI for the description and discovery of web services; and SOAP for communication between web services which are vulnerable to various web application threats

![Web Service Attack](/images/webapp-serviceattack.png)
#### Web Services Footprinting 
 - Footprint a web application to get UDDI information
#### Web Services XML Poisoning
 - Insert malicious XML codes in SOAP
 - XML schema poisoning to generate errors in XML parsing logic
 - Allows attackers to cause denial of service attacks
#### Hidden Field Manipulation 

# Hacking Methodology

### Footprint Web Infrastructure
 - First step in web application hacking
 - Helps attackers select victims
 - **Server Discovery**
   - Finds servers
   - Use tools : WHOIS LOOKUP(Netcraft, whois Lookup, smart whois), DNS Interrogation(DNS Recon, DNS).
 - **Service Discovery**
   - Find ports 
   - Use tools : nmap, NetScanTools Pro, Sandcat Browser.
 - **Server Identification**
   - Banner grabbing
   - use tools: Telnet, openSSL, ID Serve, Netcraft.
 - **Detecting Web App Firewalls and proxies**
   - Use tools :WAF00F, SHIELDFY, WhatWaf, Nmap.
   - Add certain headers in the response header field
   - Use TRACE to find changes the proxy server made to the request
 - **Hidden Content Discovery**
   - Web Spidering/Crawling
     - use tools: Burpsuite, ZAP Automated Scan, WebScarab, Mozenda Web Agent Builder, Octoparse, Giant Web Crawl(https://80legs.com)
   - Attacker Directed Spidering
   - Brute Forcing
  - **Detect Load Balaners**
    - use host command
    - use dig command
    - use load balancing detecter(LBD)
    - These are tools which will give you enough idea about the load balancers used for their servers.

Some additional information is provided about the spidering and it's tools below:
#### Web Spidering Using Burp Suite
 - Make burp suite proxy
 - Spider visits every single link on site
#### Mozenda Web Agent
 - Web Crawler
#### Attack Web Servers
 - Scan for known vulnerabilities 
 - Launch web server attacks on exploits found
 - Launch DoS attacks
   
### Analyze Web Application
 - **Identify Entry points for User Input**
   - Review HTTP request
   - Determine all user input fields
   - Determine encoding techniques
 - **Identify Server-Side Technologies**
   - HTTP Fingerprinting
   - Examine Error messages
   - Examine session tokens
   - Tools: httprint (https://net-square.com), WhatWeb(github.com).
   - These tools can idenitifes version numbers, email addresses, account IDs, web framework modules, SQL errors, and more.
 - **Server Side Functionality**
   - Applications revealed to the client
   - Examine URLS
 - **Identify Files and Directories**
   - GoBuster
     - gobuster -u <target_URL> -w common.txt -s 200
   - Nmap
     - nmap -sV --script=http-enum <target_domain_or_IP_address>
  - **Identify Web Application Vulnerabilities**
    - This is the automated scan, which can give you some potential entry points, or something which you can take forward from here.
    - Vega (https://www.subgraph.com) 
    - WPScan Vulnerability Database (https://wpscan.com)
    - Arachni (https://www.arachni-scanner.com)
    - Appspider (https://www.rapid7.com)
    - Uniscan (https://sourceforge.net)

 - **Map Attack Surface**
   - Identify Various attack surfaces
     <img width="720" alt="image" src="https://github.com/user-attachments/assets/45c2e59d-fd64-4d16-8f25-048380e8aec5">
     <img width="740" alt="image" src="https://github.com/user-attachments/assets/43039385-81a4-4112-a8dd-b990078b463e">


#### Bypass Client-Side Controls
 - Client side controls restrict user inputs in transmitting data via client components and implementing measures
#### Attack Authentication Mechanism
 - Exploit design and implementation flaws in web applications
   #### Bypass Authentication: Bypass SAML-based SSO
    - SAML is an XML-based infrastructure that serves as an authorization and authentication medium between two peers, such as identity provider (IDP) and service provider.
      <img width="724" alt="image" src="https://github.com/user-attachments/assets/bc0fed76-05ff-433c-9745-8eb78681ff8c">
    - Can use the "SAML Raider" extension in the burpsuite to find and tamper the requests.

#### Attack Authorization Schemes
- In an authorization attack, the attacker first finds a legitimate account with limited privileges, then logs in as that user, and gradually escalates privileges to access protected resources. 
#### Username Enumeration
 - Uses trail and error method to guess username based off services response to incorrect tries

### Attack Application Logics

#### Local File Inclusion
- Local file inclusion (LFI) vulnerability enables attackers to add their own files on a server via a web browser.
- Example: http://xyz.com/page=../../../../../../etc/passwd
- Evade added .php :
- Now, php is appended to the file name, which means the user cannot find the required file because file /etc/passwd.php does not exist. If an attacker tries to insert null bytes (%00) at the end of the attack string,
- The .php can be easily evaded: http://xyz.com/page=../../../../../../etc/passwd%00
- Another method to evade the added php is to add a question mark (?) to the attack string:
- http://xyz.com/page=../../../../../../etc/passwd?

#### Some additional web application hacking tools are listed below: 
- Metasploit (https://www.metasploit.com)
- w3af (https://w3af.org)
- Nikto (https://cirt.net)
- Sn1per (https://github.com)
- WSSiP (https://github.com)
- X Attacker (https://github.com)
- timing_attack (https://github.com)
- HTTrack (https://www.httrack.com)
- SQL Injection Scanner (https://pentest-tools.com)
- XSS Scanner (https://pentest-tools.com)
- SQLi Exploiter (https://pentest-tools.com)
- HTTP Request Logger (https://pentest-tools.com)
- WebCopier (https://www.maximumsoft.com)
- WPScan (https://wpscan.com)
- TIDoS-Framework (https://github.com)

### Web API, Webhooks, and Web Shell

- **REST API vulnerability scanning tools are as follows:**
- Fuzzapi (https://github.com)
- w3af (https://w3af.org)
- appspider (https://www.rapid7.com)
- Vooki (https://www.vegabird.com)
- OWASP ZAP (https://www.zaproxy.org)


## Web Application Security Testing

#### Manual Web Application security Testing 
- This involves testing a web application using manually designed data, customized code, and some browser extension tools.
- Security professionals also use other tools such as:
  - Selenium,
  - JMeter,
  - Loadrunner,
  - QTP,
  - Bugzilla, and Test Link to perform manual testing.




### [Table Of Contents](https://karsyboy.github.io/CEHv10_Ultimate_Study_Guide/)
