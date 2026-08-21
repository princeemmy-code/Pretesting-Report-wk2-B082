# | CYBERSECURITY

FOOTPRINTING & NETWORK SCANNING PHASES

W2-PM-FINA ( C Y N WORF ALK

4 = Chukwuemeka Lord David

# | BO82-Networkwalks

\|

i] Dat 19 August 2026

## W2-PM1 (Multiple Kali Tools)

d W2-PMS5 (Zenmap Scanning)

# 7 Client/T: : 1. Networkwalks (secured written permission already)

  1. My own local LAN Network

i

Permission cured

# v | Yes

2

## Phase 1: Reconnaissance & Footprinting

A Ph covered Phase 2: Scanning & Network Discovery Phase 3-5: In Progress

1. LIABILITY DISCLAIMER

# All activities described in this report were carried out only on systems and devices for which | had

# | ) written authorization or that were personally owned by me. The work is strictly intended for learning

### and cybersecurity research. The information must not be used for unlawful access or harmful activities.

Networkwalks, the instructor and the report authors accept no responsibility for misuse of the knowledge provided. Any unauthorized activity may result in legal consequences, financial penalties, employment consequences and a permanent criminal record. Accessing a system without permission can be illegal even when no damage occurs.

PENTESTING PROJECT REPORT \| N W G

1. Introduction

This report documents the footprinting of the networkwalks.com domain using multiple Kali Linux tools (W2-PM1) and the discovery scan of my own local network with Zenmap (W2-PM5). The two pracital exercise demonstrate the progression from collecting publicly available information to identifying actve systems within a network. One module covers the footprinting phase and the other covers the scanning phase, so together they show how an attacker moves from gathering public information to mapping live hosts on a network. It is the Week 2 part of my ongoing internship program at Networkwalks. The footprinting tasks were completed in Kali Linux, while the network discovery exercise was carried out on a Windows computer running Zenmap. For each activity, \| recorded the command or procedure used, the result obtained, supporting screenshot evidence and a brief explanation of the security relevance of the observation.

1. Tools Used

The table below lists each tool used in this report and its purpose.

## Tool Purpose

Kali Linux & Windows Operating systems used to carry out the reconnaissance and scanning exercises.

WHOIS Retrieve publicly available domain registration information, including dates and name servers.

Fingerprint web technologies (server, CMS, plugins, IP). nslookup Use DNS resolution to determine the IP address associated with the domain.

Inspect the website's HTTP response headers for technical information.

### wafw00f Check whether the website is protected by a Web Application Firewall.

dnsrecon Collect and enumerate DNS records such as NS, MX, SPF, TXT and SRV entries.

Zenmap (Nmap GUI) Discover active devices on the local subnet and obtain IP and MAC address information.

Windows CMD Determine local network IP configuration and MAC address details.

1. Activities Performed

### 4.1 Footprinting & Reconnaissance

\| carried out reconnaissance on the networkwalks.com domain with six Kali Linux tools: WHOIS, WhatWeb, Nslookup, Curl, Wafw00f and DNSRecon. Each utility was selected to gather a specific category of information about the target. The first step involved WHOIS, which \| used to retrieve publicly available registration information and identify the domain name servers. This supplied useful details about the domain and elements of its hosting infrastructure.

Pentesting Project Report \| Networkwalks \| Page 2

### I next used WhatWeb to examine the technologies exposed by the website. The scan

### identified WordPress 7.0.4 and WP Download Manager 3.7.1, together with other

publicly detectable technical information.

With Nslookup, \| translated the domain name into its associated IP address. The result returned the address 192.232.216.135.

### | then ran Curl with the option to review the website's HTTP response headers. The

### response revealed additional application information, including the WordPress REST

### API endpoint /wp-json/.

### Wafw0O0f was used to check for the presence of a Web Application Firewall. The result

### indicated that ModSecurity (SpiderLabs) was being used.

### Lastly, DNSRecon was used to gather DNS-related records. The output included

information about name servers, mail servers, SPF/TXT entries, service records and DNS software. 4.2 Network Scanning with Zenmap

### 4.2 Network Scanning with Zenmap

In the second practical exercise, \| used Zenmap for network discovery on my local LAN. The objective was to determine the local IP address and subnet, locate active hosts, record their IP and MAC addresses and produce a visual network topology.

\| began by running the Windows ipconfig command to determine the computer's local IP configuration and LAN subnet. \| then supplied the identified subnet to Zenmap and selected Ping Scan to locate devices that were responding on the network.

The practical example produced four active hosts:

10.0.0.1

10.0.04

10.0.0.19

10.0.0.5

The example results also included four MAC addresses.

Once the scan was completed, \| accessed the Topology view in Zenmap, turned on the legend and exported the resulting network topology as a PDF in accordance with the practical requirements.

Note: Before final submission, the sample subnet, host count and addresses should be replaced with the values obtained from my actual local network.

Pentesting Project Report \| Networkwalks \| Page 3

# From the information gathered during reconnaissance and network discovery, ®

I noted the following potential security risks and areas that may require review.

\# Risk / Finding Evidence / Observation Potential Impact Risk Level

Exposed software and Public web + WhatWeb detected version details could help

# 1 2) technology details 'WordPress and WP an identify @® Medium

### Download Manager technologies that may

need additional security review

# 2 Q Web server IP can + Nslookup returned about

### be determined 192.232.216.135

hosting the web service

HTTP « Curl displayed HTTP Could support technology

## 3 / > implementation response headers and identification and additional @ Low

details exposed the /wp-json/ endpoint information gathering

WAF « Wafw0Of detected Provides insight into the

# 4 0 implementation ModSecurity security controls protecting @ Low

### can be identified (SpiderLabs) the web application

### DNS and service resumed May help an attacker develop

# 5 CIE information Ns; a wider picture of the Medium

### publicly available service-related organization's infrastructure

records

# Several active + Zenmap found four Ck

# devices detected live hosts in the Q oh a @® Medium

### on the LAN example network veg

authorization checks

# (0) RISK LEVEL KEY: @® Critical Medium ® Low

@ listed above represent observations from the reconnaissance and scanning exercises and should not be treated as confirmed vulnerabilities.

@ The practical work focused on information collection and identifying reachable hosts. No exploitation, penetration of vulnerabilities or vulnerability confirmation was carried out during these modules.

@ Consequently, discovering a software version, IP address or DNS record does not automatically indicate that a security weakness exists. Additional authorized assessment would be necessary before confirming any vulnerability.

Pentesting Project Report \| Networkwalks \| Page 4

1. Recommendations

The following measures are recommended based on the observations made during the practical exercises:

1. Review publicly visible technology information Organizations should periodically assess the technical

details exposed by their websites, CMS platforms and installed plugins.

1. Maintain current software versions CMS software, plugins and related technologies should be

updated regularly and checked against relevant security advisories.

1. Assess HTTP response headers Review server response headers to identify and reduce technical

information that does not need to be publicly disclosed.

1. Regularly audit DNS records DNS entries should be reviewed at intervals so that only necessary

records and services remain publicly accessible.

1. Configure and monitor the WAF correctly ModSecurity should remain active, properly configured and

regularly monitored to strengthen web application protection.

1. Conduct routine internal network discovery Organizations should periodically scan their internal

networks to maintain visibility of active and connected devices.

1. Validate unfamiliar devices Any device that is not recognized during a network scan should be

investigated and confirmed as authorized.

1. Keep network records current Network diagrams, device details and topology information should be

maintained and updated when changes occur.

1. Limit testing to authorized environments Reconnaissance and scanning should always be conducted

only against systems and networks for which appropriate permission has been obtained.

Pentesting Project Report \| Networkwalks \| Page 5

1. Conclusion

As part of Week 2 of my Cybersecurity & Ethical Hacking internship, \| completed practical exercises focused on reconnaissance, footprinting and network scanning. During the footprinting exercise, \| worked with six Kali Linux utilities to gather information about the target domain. This helped me understand how WHOIS can reveal domain details, WhatWeb can identify website technologies, Nslookup can resolve domain names, Curl can review HTTP headers, can detect WAF protection and DNSRecon can collect DNS-related information. For the network discovery exercise, \| used Zenmap to examine my local network configuration and identify active devices. \| also recorded IP and MAC address information and produced a network topology as part of the required practical work. These exercises demonstrated the importance of information gathering in cybersecurity. Before any exploitation is considered, a security practitioner can obtain substantial insight into an environment by analyzing publicly available information and network responses. Another key lesson was the importance of presenting technical findings in a clear and structured manner. An effective cybersecurity report should state the activity performed, the evidence obtained, the meaning of each observation, the possible security impact and the recommended corrective action. Most importantly, \| learned that reconnaissance and network scanning must remain within an approved scope. All activities documented in this report were completed for the assigned educational cybersecurity practical and within the stated authorization requirements.

Pentesting Project Report \| Networkwalks \| Page 6

= + \| Wg

bes mA \|

Sf

COM SERA

### ne ICANN

im Ge dete The = in the ef che THis dems the meme we

### = Tor

ar sur

### or veu sre mot te OF

the use of slectrenic domain SE

### am

The vided Dy f=

### fr in

and

### To a you

3 may usw

Edt View

\| ie, [300 si Alc rae a Ch 3 3.3 SBE, HAL TT 17,

Pentesting Project Report \| Networkwalks \| Page 7

## en

### |

### GOT Not fron

# acd run: 143 168.

Hon answers

192 333

re

sar en

Ls -1 con 208

### we

df con® fwd con" COUT pn bend )

### ThE.

Toles

## ay (1

nly wien ©

date: Was, 19 Ang GMT

L]

# RL

Pentesting Project Report \| Networkwalks \| Page 8

### MA

# Tot: {sem

## 1] 1 4 |

.

### pak sig

### I

### ik x 7

FE \| \|

The Beh Applicetion Firewall

if con Me

### The site meeps: con war.

Lol of 2

LE \| \|

=

Box

a

ad EEL

TELE

LURE \|

po

# dmg en 47

160 Vo

FEE

### Lie pe

se

Pentesting Project Report \| Networkwalks \| Page 9

### is

we

-End-

2 Author Chukwuemeka Lord David Cybersecurity Professional B082 LinkedIn: www.linkedin.com/in/chukwuemeka-lorddavid

Project Information Program Name: Cybersecurity program at Networkwalks \| Week: 02 \| Repository: GitHub

Pentesting Project Report \| Networkwalks \| Page 10
