# SQL Injection

### <u>SQL Injection Concepts</u>
 - SQL Injection is a technique used to take advantage of unsanitized input vulnerabilities to pass SQL commands to web applications so that they will execute them on the back end
 - Can be used to gain access or retrieve information

### <u>Types of SQL Injections</u>

#### In Band SQL Injection
 - Attacker use the same communication channel to perform the attack and retrieve the results
 - Types of in band SQL injection attacks
   - **Error-based**
     - Insert bad input causing it to throw database errors
   - **System Store Procedure**
     - Exploit databases stored procedures
   - **Illegal Logically incorrect query**
     - Send an incorrect query to the database intentionally to get an error message 
   - **Union SQL Injection**
     - Use the UNION command to add a malicious query to the requested query
   - **Tautology**
     - Inject statements that are always true
     - Used for bypassing the authentication.
   - **End  of line comment**
     - Adds end of line comment to nullify  legitimate  code 
     - Comments in a line of code are often denoted by (--), and they are ignored by the query. 
   - **Inline comment**
     - Use inline comments to add multiple queries.
   - **Piggybacked query**
     - Inject additional malicious queries into the original query
     - Owing to piggybacking, the DBMS receives multiple SQL queries. Attackers use a **semicolon (;)** as a query delimiter to separate the queries. After executing          the original query, the DBMS recognizes the delimiter and then executes the next query.
   - **Error Based SQL Injection**
   - Forces the database to perform some operation which the result will be an error
 
 #### Blind/Inferential SQL Injection
   - No Error Message
   - Generic Page page is shown instead of a error page 
   - Time-intensive
   - Use wait for a delay to determine if SQL command is ran
     - If command is ran the webpage will have a delay before it loads the generic page
   - **Boolean Exploitation**
     - Multiple valid statements that evaluate true and false are supplied and the returned page is compared to evaluated if 
   - **Heavy query**
     - Perform time delayed SQL injection attacks without using the time delay functions
     - Heavy queries retrieve lots of data and take a huge amount of time to execute on the database engine
     - Uses multiple joins to make a heavy query
     
#### Out of band SQL Injection
 - Attackers use different communication channels to perform the attack and gain the results
 - Uses DNS and HTTP request to get information

### <u>SQL Injection Methodology</u>
 - Error messages give a lot of information
#### ODBC Errors
 - Will show you database type
#### Grouping error
 - Tells us which columns have not been grouped
#### Type Mismatch
 - Insert strings into numeric fields shows data that could not be converted
#### Blind injection
 - Uses time delays to determine if message was executed
#### Additional Methods to Detect SQL Injection
 - Function Testing
   - Scope of black box testing and requires no knowledge of the inner design of the code or logic
 - Fuzzing Testing
   - Used to discover coding errors inputting massive amount of random data and observing the changes in the output
 - Static/Dynamic Testing
   - Analysis of the web application source code
  
  ## Understanding HTTP-POST Method
  - An HTTP POST request is a method for carrying the requested data to the web server.
  - Unlike the HTTP GET method, the HTTP POST request carries the requested data as a part of the message body.
  - Thus, it is considered more secure than HTTP GET. HTTP POST requests can also pass large amounts of data to the server.
  - They are ideal for communicating with an XML web service.

## Google Dorks for finding the Login Pages
For example, the attacker may try the following dorks to find the admin panel of a website: 
- inurl:adminlogin.aspx 
- inurl:admin/index.php
- inurl:administrator.php
- inurl:administrator.asp
- inurl:login.asp
- inurl:login.aspx
- inurl:login.php
- inurl:admin/index.php
- inurl:adminlogin.aspx

**Once you found the login page, you can try injecting these malicious SQL queries**
- ‘ or 1=1 --
- 1'or’1'=’1
- admin’--
- ” or 0=0 --
- or 0=0 --
- ‘ or 0=0 #
- ” or 0=0 #
- or 0=0 #
- ‘ or ‘x’='x
- ” or “x”=”x
- ‘) or (‘x’='x
- ‘ or 1=1--
- ” or 1=1--
- or 1=1--

## Tools
- SQL map, source: https://sqlmap.org
- Mole Source: https://sourceforge.net
  - Mole is an automatic SQL injection exploitation tool.
  - Only by providing a vulnerable URL and a valid string on the site, it can detect the injection and exploit it using the union technique or a Boolean query-         based technique.

### [Table Of Contents](https://karsyboy.github.io/CEHv10_Ultimate_Study_Guide/)
