# Week 2 – Footprinting & Reconnaissance

## Project Overview

This project focuses on the first stage of ethical hacking: **footprinting and reconnaissance**.

The objective was to collect publicly available information about a target website using several reconnaissance tools available in Kali Linux.

The target used in this lab was:

**Target:** `networkwalks.com`

> ⚠️ **Ethical Disclaimer:** This project was conducted for educational and ethical hacking purposes as part of a cybersecurity training exercise. The activities were limited to reconnaissance and information gathering.

### Objectives

The project involved using six Kali Linux tools to gather different types of information about the target:

1. WHOIS – Domain registration information
2. WhatWeb – Web technology fingerprinting
3. NSLookup – DNS/IP resolution
4. cURL – HTTP response headers
5. WAFW00F – Web Application Firewall detection
6. DNSRecon – DNS record enumeration

### Tools Used

| Tool | Purpose |
|---|---|
| `whois` | Obtaining domain registration information |
| `whatweb` | Identifying web technologies |
| `nslookup` | Resolving the domain to an IP address |
| `curl` | Examining HTTP response headers |
| `wafw00f` | Detecting a Web Application Firewall |
| `dnsrecon` | Enumerating DNS records |
| Kali Linux | Operating system used for the lab |

# Task 1 – WHOIS

#### Command
'whois networkwalks.com'

 ### Objective

The purpose of this task was to obtain publicly available domain registration information, including registration details and name servers.

### Findings
Domain: networkwalks.com


Registrar: GoDaddy.com, LLC


Registration Date: 2019-11-06T22: 51 :46Z


Expiration Date: 2027-11-06T22: 51 :46Z


Name Servers: NS6L35.HOSTGATOR.COM
              NS6L36.HOSTGATOR.COM

              
Screenshot: <img width="1920" height="964" alt="image" src="https://github.com/user-attachments/assets/cb1babbb-6744-4e37-9cb7-c04630f02068" />

Output

The complete command output is available in:
[Task 1-WHOIS Output](/home/kali/task1_whois.txt)


# TASK 2 - WHATWEB

### Command
'whatweb networkwalks.com'

#### Objective
The purpose of this task was to fingerprint the technologies used by the website, including it's web server, CMS, plugins, frameworks, and other undentifiable technologies.

#### Findings
Web Server: Apache
CMS: WordPress 7.1
Plugin: WordPress Download Manager 3.3.58
Other Technologies: Bootstrap, jQuery 3.7.1, Google Tag Manager, HTML5, Open Graph Protocol and JavaScript
IP Address: 192.232.216.135
Website Title: Networkwalks Academy

Screenshot:
<img width="1920" height="964" alt="image" src="https://github.com/user-attachments/assets/f90c6b9c-3f94-497c-9fb8-9a2c2a9eaab3" />

Output

The complete command output is available in:
[Task 2-WHATWEB Output](/home/kali/task2-whatweb.txt)

# TASK 3 - NSLookup

### Command
'nslookup networkwalks.com'

#### Objective
The purpose of this task was to resolve the domain name to its IP address

#### Finding
The domain resolved to:
IP Address: 192.232.216.135

Screenshot:
<img width="1920" height="964" alt="image" src="https://github.com/user-attachments/assets/f2e376c3-576f-4ed2-968b-e4bfe2e0b35d" />

Output

The complete command output is available in:
[Task 3-Nslookup Output](/home/kali/task3-nslookup.txt)


# Task 4-HTTP Response Headers

### Command
'curl -sI https://networkwalks.com'

#### Objective
The purpose of this task was to enumerate publicly available DNS records associated with target domain.

### Headers Observed
The response included headers such as:

Content-Type

Set-Cookie

Referrer-Policy

Link

Server

Date

Screenshot:
<img width="1920" height="964" alt="image" src="https://github.com/user-attachments/assets/5da21641-9813-4100-a50c-b826a19ebf88" />

Output

The complete command output is available in:
[Task4-Curl Ouput](/home/kali/task4-curl.txt)

# TASK 5-WAF DETETCTION

### Command
'wafwoof networkwalks.com'

### Objective
The purpose of this task was to determine whether the target website was protected by a Web Application Firewall(WAF)

### Finding
The scan identified:
ModSecurity (SpiderLabs) WAF

The result indicated that networkwalks.com is behind a ModSecurity (SpiderLabs) Web Application Firewall.

Screenshot
<img width="1920" height="964" alt="image" src="https://github.com/user-attachments/assets/fb5da71c-f33b-4f4f-868b-ecd3c714901b" />

Output

The complete command output is available in:
[Task 5-WAFW00F Output](/home/kali/task5-wafw00f.txt)

# TASK 6-DNS ENUMERATION

### Command
'dnsrecon -d networkwalks.com'

# Objective
The purpose of this task was to enumerate publicly available DNS records associated with the target domain.

# Findings
The DNS enumeration identified 8 records.

|Record Type | Finding|
|---|---|
|SOA     |   ns6135.hostgator.com|
|NS	     |       ns6135.hostgator.com|
|NS	     |      ns6136.hostgator.com|
|A	     |           192.232.216.135|
|MX	     |     mail.networkwalks.com → 192.232.216.135|
|TXT	   |        Site verification records|
|TXT/SPF |        SPF policy record|
|SRV     |      	_autodiscover._tcp.networkwalks.com|

The enumeration also reported the BIND version as:
9.16.23-RH

Screenshot:
<img width="1920" height="964" alt="image" src="https://github.com/user-attachments/assets/d73d9b0f-3867-4464-b5e3-40d4ffbedda6" />

Output

The complete command output is available in:
[Task 6-DNS Output](/home/kali/task6-dnsrecon.txt)

# Key Observations

The reconnaissance activities demonstrated how publicly available information can be used to build a profile of a web domain.

The investigation identified:
The domain's registration information
Technologies associated with the website
The domain's resolved IP address
HTTP response headers
The presence of a Web Application Firewall
DNS, mail, TXT, and service records

These findings demonstrate why organizations should carefully manage the information exposed through their public-facing infrastructure.

# Conclusion

Footprinting and reconnaissance are important stages of ethical hacking because they allow security professionals to understand what information is publicly exposed by an organization.

Using Kali Linux tools such as whois, whatweb, nslookup, curl, wafw00f, and dnsrecon, this project demonstrated how different sources of publicly available information can be collected and analyzed to build an overview of a web domain.

