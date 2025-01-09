# Reconnaissance







## Website FootPrinting


- Hackers can map the entire website of the target without being noticed
- Gives information about:
  - Software
  - Operating system
  - Subdirectories
  - Contact information
  - Scripting platform
  - Query details

### Web spiders

- Programs designed to help in website footprinting
- Methodically browse a website in search of specific information.
- Information collected this way can help attackers perform social engineering attacks.
- User directed Spidering:
  - Web spidering tools such as Web Data Extractor, ParseHub, and SpiderFoot can collect sensitive information from the target website.
 

### Cookie examination

- Reveals what software that is running on the server and its behavior
- Possible to identify the scripting platforms.

### Examining website headers

- By examining the website headers, it is possible to obtain information about:
  - `Content-Type`
  - `Accept-Ranges`
  - Connection Status
  - `Last-Modified` Information
  - `X-Powered-By` Information
    - E.g. `ZendServer 8.5.0,ASP.NET`
  - Web Server Information
    - `Server` header can give you e.g. `Apache Server on CentOS`
- You can also analyze what website pulls
  - In debugging developer tool of most browsers (ctrl+shift+c) network section
  - For each request you can see remote IP address, and response headers for further analysis.

## Source code examination

### Comment analysis

- Possible to extract information from the comments
- In most of browsers you can right click and how source
- Walkthrough
  - In almost any browser: Right click => Show source
  - Check for HTML `<!-- comment -->` or JavaScript `// comment` comments
  - They are skipped by interpreters and compilers, only for human eyes
  - They can be instructions for other developers, notes for themselves
    - E.g. this library won't work as this element is not supported
      - Gives you clues about what technology (frameworks, languages) they use in the background

### Observing link and image tags

- Html links: `href=cloudarchitecture.io`
- Gain insight into the file system structure
- You can find e.g. a caching server and check vulnerabilities for that caching server.

## Cloning websites

- Also called **website mirroring**
- Helps in
  - browsing the site offline
  - searching the website for vulnerabilities
  - discovering valuable information and metadata.
- Can be protected with some detections based on e.g. page pull speed, behavior, known scrapers, AI.
- 💡 Good tool for setting up fake websites.
  - E.g. manually recreate login pages
  - If you control the DNS you can do a redirect.
- Allows you to save social media pages with this however most are protected, and illegal to clone.
- **Website monitoring tools** can send notifications on detected changes.
- 💡 Protection against fake websites
  - Always check domain name for misspelling
  - Make sure it's HTTP**S**, if it's not the data can be sniffed easily
    - Protects against someone taking over DNS
    - If the other part does not have the certificate, browser does not accept communication
  - Check SSL certificate authority, if it's changing, it can prompt a question.
    - Certificates expire usually in a year.

### Website cloning tools

- [`httrack`](https://github.com/xroche/httrack)
  - `httrack https://testwebpage.com` to copy
- 📝 `wget`
  - Basic utility that can be used for mirroring website
- Or one could manually copy paste source code of HTML + CSS
- - **Web mirroring** - allows for discrete testing offline
  - HTTrack
  - Black Widow
  - Wget
  - WebRipper
  - Teleport Pro
  - Backstreet Browser
- **Archive.org** - provides cached websites from various dates which possibly have sensitive information that has been now removed


### Other Techniques for Website FootPrinting
- Extractign website links
  - Attackers can use tools such as **Photon to retrieve archived URLs of the target website** from archive.org
  - Octoparse
- Gathering the Wordlist from the Target Website
  - CeWL tool to gather a list of words from the target website and perform a brute-force attack on the email addresses gathered earlier.
- **Extracting metadata**

- You can extract metadata of files (e.g. images) from a webpage
- Metadata can include
  - Owner of the file
  - GPS coordinates (images)
  - File type metadata
    - 🤗 Linux does not work with extensions e.g. `.pdf` but checks for the metadata.
    - Helpful as you will not be fooled by the extension

### Tools for extracting metadata

- **`hexdump`**
  - Dump file as ASCII and inspect manually
  - E.g. `hexdump -C TEST_DOCUMENT.docx`
  - ❗ Not recommended as it's pretty hard to extract information from binary.
- **[`ExifTool`](https://exiftool.org/)**
  - Reads + writes metadata of audio, video, PDF, docs etc.
  - E.g. `exiftool TEST_DOCUMENT.docx` would return something like `Microsoft Office Word`, `Version: 16.0`
- 📝 **[Metagoofil | Google hacking tool](./search-engines-and-online-resources.md#google-hacking-tools)**
  - Search for files that may have metadata for a website using Google and dump their metadata.

- Monitoring Web Pages for Updates and Changes 
 - Web updates monitoring tools such as WebSite-Watcher, Visual Ping, and Follow That Page are capable of detecting any changes or updates on a particular website, and they can send notifications or alerts to interested users through email or SMS.

---


--- 


# Email footprinting

- By monitoring the email delivery and inspecting the e-mail headers
- Information includes
  - IP address of the recipient
  - Geolocation of the recipient
  - Delivery information
  - Visited links
  - Browser and OS information
  - Reading time
- Can track emails using various **email tracking tools**
  - E.g. notifies sender of the email being delivered and opened by the recipient
  - Used by marketers, sellers etc.

## Email header analysis

- Helps to determine an e-mail contains something malicious or not
- Email-headers include
  - Sender's name
  - IP/Email address of the sender
  - Mail server
  - Mail server authentication system
  - Send and delivery stamps
  - Unique number of the message

### Authentication protocol headers

- Allows you to detect forged sender addresses.
- The goal is for sender to identify itself to the receiver.
- E-mail headers include information about their pass status

#### SPF: Sender Policy Framework

- E.g. `'PASS' with IP 209.85.220.69` or `'NEUTRAL' ...`
- Verifies if the domain of the e-mail owned by the sending server.
  - If not passed, many e-mail providers just block it.
- Based on e-mail servers who publish records and says "here's the IP addresses we'll send e-mails"

#### DKIM: DomainKeys Identified Mail

- E.g. `'PASS' with domain accounts.google.com`
- Allows the receiver to verify that an email claimed to have come from a specific domain was authorized by the owner of that domain using a digital signature on the domain.

#### DMARC: Domain-based Message Authentication, Reporting and Conformance

- E.g. `PASS` or `FAIL`
- Combination of two protocols SPF + DKIM
- It builds on them and adds more policy

## Verifying email legitimacy

- Double check `FROM`
- Check the spelling in domain name so it's coming from the domain of the company
  - If it's random e-mail check if it's from one of the biggest domain providers or if something legit.
- Check IP of the domain
  - It can be someones computer (home router IP) or a private server
  - Major mail service providers checks to determine if domain of the e-mail is tied to the source IP of the e-mail (e.g. have a record)
    - 🤗 You can tie a public WiFi (e.g. coffee shop) IP to domain and send the e-mails from there.

## E-mail policies

- Different e-mail service provider have different policies regarding to their SMTP
- 💡 Once hacker recognizes e-mail servers then then he/she can create accounts there, send e-mails back and further to figure out what the rules are.
- E.g. google does not allow you to see the IP address of the sender
  - They proxy it behind one of their servers
  - Workarounds are not so efficient.
- Each have own ruling list
  - Determines e.g. what kind of files that can be send

## Getting an IP address from an e-mail

- You can then get IP and a lot from browser headers including
  - browser information, OS info, device types
  - Revealing your IP is not safe as even home routers have pretty static IP addresses
    - Last usually 30 days up to 3 months
    - 💡 You can still release DHCP lease in your home router settings to get a new IP from the ISP.
- You can send an image from a back-end server that you own
  - Some e-mail providers request it and hide users IP
- You can send a direct link
  - No e-mail provider can protect you from that
  - 🤗 Can be done through social engineering e.g.
    - You know from social media that Bob was celebrating yesterday. You send an e-mail stating "Hi Bob, crew and I had a great time last night, you're never going to guess what Sam did in toilet, threw himself up, check out his pictures"
  - E.g.
    1. Install apache `yum install httpd`
    2. Start apache `systemctl start httpd`
    3. Create a file: `cd /var/www/html/` then `touch <RESOURCE_NAME>;`
    4. Check logs live: `tail -f /var/log/httpd/access_log`
    5. You'll get the IP address when the link (`<IP_ADDRESS>/<RESOURCE_NAME>`) is opened
       - You can find out self IP address using `curl ifconfig.me`
    6. And you can look at the location of IP using `geoiplookup <IP_ADDRESS>;`

### Email Tracking Tools
- Email tracking tools such as eMailTrackerPro, Infoga, Mailtrack, and PoliteMail allow an attacker to track an email and extract information such as sender identity, mail server, sender’s IP address, location, and so on.
- Infoga
---
---

## WHOIS FootPrinting

- Query and response protocol (port 43)
- Used for retrieving information about assigned Internet resources
- To get WHOIS information you can
  - Use different websites such as [whois.net](https://www.whois.net)
  - Use command-line: `whois cloudarchitecture.io`
- Two models
  - **Thick WHOIS**: information from all registrars for the specified set of data.
  - **Thin WHOIS**: limited information about the specified set of data.

### WHOIS results

- Domain details
- 📝 Domain owner details
  - Includes contact information of the owner
  - Can be hidden by a **WHOIS guard**
    - A proxy between the owner of the domain and who's accessing
    - Emails are usually still redirected to the owner.
      - 💡 Allows for e-mail phishing to learn who the actual owner is.
- Domain server
  - Who it's registered with e.g. [NameCheap.com](https://www.namecheap.com), [Gandi.net](https://www.gandi.net)
  - 💡 Site owner might have account in the server, and you can test passwords there.
- Net range
- Domain expiration
  - 💡 If auto-renewal fails, someone can transfer a domain to another address for malicious behaviors or just to sell it back to you.
- Creation and last update dates

### Regional internet registries

- WHOIS databases are maintained by the Regional Internet Registries (RIRs) such as:
  - **ARIN**: American Registry for Internet Numbers
  - **AFRINIC**: African Network Information Center
  - **APNIC**: Asia Pacific Network Information Center
  - **RIPE**: Réseaux IP Européens Network Coordination Centre
  - **LACNIC**: Latin American and Caribbean Network Information Center
- 🤗 Every ISP, hosting company etc. must be member of one of the registries to get IP addresses.

## IP geolocation

- Helps find location information about a target
- Includes country, city, postal code, ISP, and so on
  - Country is mostly accurate but city, coordinates are not but approximated
- Helps with social engineering attacks
- E.g. [GeoIpTool.com](https://geoiptool.com)


---
---






### <u>Footprinting</u>

- Looking for high-level information on a target
- Types
  - **Anonymous** - information gathering without revealing anything about yourself
  - **Pseudonymous** - making someone else take the blame for your actions

### <u>Four Main Focuses</u>

- Know the security posture
- Reduce the focus area
- Identify vulnerabilities
- Draw a network map

### <u>Types of Footprinting</u>

- **Active** - requires attacker to touch the device or network
  - Social engineering and other communication that requires interaction with target
- **Passive** - measures to collect information from publicly available sources
  - Websites, DNS records, business information databases

**Competitive Intelligence** - information gathered by businesses about competitors

**Alexa.com** - resource for statistics about websites

### <u>Methods and Tools</u>

**Search Engines**

- **NetCraft** - information about website and possibly OS info
- **Job Search Sites** - information about technologies can be gleaned from job postings
- **Google**
  - filetype:  - looks for file types
  - index of - directory listings
  - info: - contains Google's information about the page
  - intitle: - string in title
  - inurl: - string in url
  - link: - finds linked pages
  - related: - finds similar pages
  - site: - finds pages specific to that site
- **Metagoofil** - uses Google hacks to find information in meta tags

**Website Footprinting**

- **Web mirroring** - allows for discrete testing offline
  - HTTrack
  - Black Widow
  - Wget
  - WebRipper
  - Teleport Pro
  - Backstreet Browser
- **Archive.org** - provides cached websites from various dates which possibly have sensitive information that has been now removed
- Attackers can use tools such as Photon to retrieve archived URLs of the target website from archive.org

**Email Footprinting**

- **Email  header** - may show servers and where the location of those servers are
- **Email tracking** - services can track various bits of information including the IP address of where it was opened, where it went, etc.

**DNS Footprinting**

- Ports

  - Name lookup - UDP 53
  - Zone transfer - TCP 53

- Zone transfer replicates all records

- **Name resolvers** answer requests

- **Authoritative Servers** hold all records for a namespace

- **DNS Record Types**

  

  - | Name  | Description        | Purpose                                        |
    | ----- | ------------------ | ---------------------------------------------- |
    | SRV   | Service            | Points to a specific service                   |
    | SOA   | Start of Authority | Indicates the authoritative NS for a namespace |
    | PTR   | Pointer            | Maps an IP to a hostname                       |
    | NS    | Nameserver         | Lists the nameservers for a namespace          |
    | MX    | Mail Exchange      | Lists email servers                            |
    | CNAME | Canonical Name     | Maps a name to an A reccord                    |
    | A     | Address            | Maps an hostname to an IP address              |

- **DNS Poisoning** - changes cache on a machine to redirect requests to a malicious server

- **DNSSEC** - helps prevent DNS poisoning by encrypting records

- **SOA Record Fields**

  - **Source Host** - hostname of the primary DNS
  - **Contact Email** - email for the person responsible for the zone file
  - **Serial Number** - revision number that increments with each change
  - **Refresh Time** - time in which an update should occur
  - **Retry Time** - time that a NS should wait on a failure
  - **Expire Time** - time in which a zone transfer is allowed to complete
  - **TTL** - minimum TTL for records within the zone

- **IP Address Management**

  - **ARIN** - North America
  - **APNIC** - Asia Pacific
  - **RIPE** - Europe, Middle East
  - **LACNIC** - Latin America
  - **AfriNIC** - Africa

- **Whois** - obtains registration information for the domain

- **Nslookup** - performs DNS queries

  - nslookup [ - options ] [ hostname ]
  - interactive zone transfer
    - nslookup
    - server <IP Address>
    - set type = any
    - ls -d domainname.com

- **Dig** - unix-based command like nslookup

  - dig @server name type

**Network Footprinting**

- IP address range can be obtained from regional registrar (ARIN here)
- Use traceroute to find intermediary servers
  - traceroute uses ICMP echo in Windows
- Windows command - tracert
- Linux Command - traceroute

**Other Tools**

- **OSRFramework** - uses open source intelligence to get information about target
- **Web Spiders** - obtain information from the website such as pages, etc.
- **Social Engineering Tools**
  - Maltego
  - Social Engineering Framework (SEF)
- **Shodan** - search engine that shows devices connected to the Internet

**Computer Security Incident Response Team** (CSIRT) - point of contact for all incident response services for associates of the DHS

### [Table Of Contents](https://karsyboy.github.io/CEHv10_Ultimate_Study_Guide/)
