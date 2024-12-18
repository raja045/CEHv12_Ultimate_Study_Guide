### <u>Enumeration</u>

- Defined as listing the items that are found within a specific target
- Always is active in nature

### <u>Windows System Basics</u>

- Everything runs within context of an account
- **Security Context** - user identity and authentication information
- **Security Identifier** (SID) - identifies a user, group or computer account
- **Resource Identifier** (RID) - portion of the SID identifying a specific user, group or computer
- The end  of the SID indicates the user number
  - Example SID:  S-1-5-21-3874928736-367528774-1298337465-**500**
  - **Administrator Account** - SID of 500
  - **Regular Accounts** - start with a SID of 1000
  - **Linux Systems** used user IDs (UID) and group IDs (GID).  Found in /etc/passwd
- **SAM Database** - file where all local passwords are stored (encrypted)
  - Stored in C:\Windows\System32\Config
- **Linux Enumeration Commands**
  - **finger** - info on user and host machine
  - **rpcinfo and rpcclient** - info on RPC in the environment
  - **showmount** - displays all shared directories on the machine

### <u>Banner Grabbing</u>

- **Active** - sending specially crafted packets and comparing responses to determine OS
- **Passive** - reading error messages, sniffing traffic or looking at page extensions
- Easy way to banner grab is connect via telnet on port (e.g. 80 for web server)
- **Netcat** can also be used to banner grab
  - nc <IPaddress or FQDN> <port number>
- Can be used to get information about OS or specific server info (such as web server, mail server, etc.)

### <u>NetBIOS Enumeration</u>

- NetBIOS provides name servicing, connectionless communication and some Session layer stuff
- The browser service in Windows designed to host information about all machines within domain or TCP/IP network segment
- NetBIOS name is a **16-character ASCII string** used to identify devices
- Command on Windows is **nbtstat**
  - nbtstat (gives your own info)
  - nbtstat -n (gives local table)
  - nbtstat -A IPADDRESS (gives remote information)
  - nbtstat -c (gives cache information)

| Code | Type   | Meaning                   |
| ---- | ------ | ------------------------- |
| <1B> | UNIQUE | Domain master browser     |
| <1C> | UNIQUE | Domain controller         |
| <1D> | GROUP  | Master browser for subnet |
| <00> | UNIQUE | Hostname                  |
| <00> | GROUP  | Domain name               |
| <03> | UNIQUE | Service running on system |
| <20> | UNIQUE | Server service running    |

- NetBIOS name resolution doesn't work on IPv6
- **Other Tools**
  - SuperScan
  - Hyena
  - NetBIOS Enumerator
  - NSAuditor

### <u>SNMP Enumeration</u>

- **Management Information Base** (MIB) - database that stores information
- **Object Identifiers** (OID) - identifiers for information stored in MIB
- **SNMP GET** - gets information about the system
- **SNMP SET** - sets information about the system
- **Types of objects**
  - **Scalar** - single object
  - **Tabular** - multiple related objects that can be grouped together
- SNMP uses community strings which function as passwords
- There is a read-only and a read-write version
- Default read-only string is **public** and default read-write is **private**
- These are sent in cleartext unless using SNMP v3
- **Tools**
  - Engineer's Toolset
  - SNMPScanner
  - OpUtils 5
  - SNScan

### <u>Other Enumerations</u>

- **LDAP**
  - Connects on 389 to a Directory System Agent (DSA)
  - Returns information such as valid user names, domain information, addresses, telephone numbers, system data, organization structure and other items
  - **Tools**
    - Softerra
    - JXplorer
    - Lex
    - LDAP Admin Tool
- **NTP**
  - Runs on UDP 123
  - Querying can give you list of systems connected to the server (name and IP)
  - **Tools**
    - NTP Server Scanner
    - AtomSync
    - Can also use Nmap and Wireshark
  - **Commands** include ntptrace, ntpdc and ntpq
- **SMTP**
  - VRFY - validates user
  - EXPN - provides actual delivery address of mailing list and aliases
  - RCPT TO - defines recipients
