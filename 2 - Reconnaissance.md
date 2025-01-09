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
---

- Monitoring Web Pages for Updates and Changes 
 - Web updates monitoring tools such as WebSite-Watcher, Visual Ping, and Follow That Page are capable of detecting any changes or updates on a particular website, and they can send notifications or alerts to interested users through email or SMS.












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
