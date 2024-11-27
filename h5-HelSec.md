##### Homework 5 - [HelSec](https://terokarvinen.com/trust-to-blockchain/#homework)

##### x) Summaries
###### Reference: [HelSec November 2024 Meetup](https://events.helsec.fi/helsec/nvmbr/)
#### 1. Jos Helmich - Industrial Cyber Security


- The **ENISA** (European Union Agency for Cybersecurity) Advisory Group is responsible for allocating funds, addressing strategic questions, reviewing the threat landscape 2030, publishing white papers on relevant topics, and providing advisory papers to the EU Parliament and Commission. The group is composed of members from academia, research, NGOs, industry, the NIS sector, and consumer/citizen groups, representing 19 different countries.

<br/>

Industrial EU Directives:
- Machinery Directive - Ensures a common safety level in machinery placed on the market
- **RED** (Radio Equipment Directive) - Regulation for the design, manufacturing, and placing on the market of radio equipment in the European Union

General EU Laws and Directives:
- **GPDR** (General Directive Data Protection) - Demands that privacy is respected
- **NIS-2** (Network Information and Systems #2) - Demands that organizations are cyber resilient
- **CRA** (Cyber Resilience Act) - Demands that digital products are cyber secure
- **AIA** (Artificial Intelligence Act) - Demands that makers of AI products take fundamental rights and product requirements into account


NIS-2 requirements are about the organization's cybersecurity:
- ISO-27001 - Information security
- ISO-27036 - Supply chain security
- ISO-30111 - Vulnerability management

NIS-2 in Manufacturing:
- IT Security (ISO/IEC-27001) - Confidentiality, Integrity, Availability
- OT Security (ISA/IEC-62443) - Availability, Integrity, Confidentiality

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/h5_1-1.jpg" width="500">

<br/>

Manufacturing and cloud applications security considerations:

 <img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/h5_1-2.jpg" width="500"> <img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/h5_1-3.jpg" width="500">

 

* Office Cloud - This covers applications related to finance, HR, travel, etc.
  * The office network is protected by a firewall that faces the internet 
* Industrial Cloud - This covers applications related to fleet management, diagnostics, etc.
  * The Industrial network is protected by two firewalls which use different hardware and software and it's a good place to put a virus scanner
*  The security zones are divided into 5 different levels within the manufacturing and enterprise network, including
    * Enterprise Security Zone
    * Site Business Planning and Logistics Network
    * Manufacturing Security Zone
    * Control Center/Processing LAN
    * Area Control: Local HMI LAN
    * Basic Control: Controller LAN
    * Process: Field I/O Devices, Instrument Bus

<br/>

NIS-2 vs CRA
|NIS-2|CRA|
|-----|---|
|Keep your house in order|Don't mess up someone else's house|
|Don't buy stuff in the garage sale|Don't sell bad stuff to the customer|

* NIS-2 in Europe (in Finland is not implemented yet) aims to improve cyber security
* There is not yet a certifiable standard to address the CRA

<br/>

The 62443 family provides good advice on industrial cybersecurity:
- 62443-4-1 Secure Software Development Lifecycle Requirements
- 62443-3-3 System Requirements
- 62443-4-2 Component Requirements

 Security Levels in 62443:
 1. Accidental tourist (Protection against unintentional or accidental misuse.)
 2. Normal users (Protection against intentional misuse by simple means with few resources, general skills and low motivation.)
 3. Hackers (Protection against intentional misuse by sophisticated means with moderate resources, IACS-specific knowledge and moderate motivation.)
 4. Nation state (Protection against intentional misuse using sophisticated means with extensive resources, IACS-specific knowledge and high motivation.)

Reference: [Wikipedia](https://en.wikipedia.org/wiki/IEC_62443)

<br/>

**AI PART** 

EU Legislation - New Legislative Framework:
* Artificial Intelligence Act
  * Product safety requirements
  * Data requirements - GDPR
  * Cyber Resilience Act

There are acts(laws) and there are directives.

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/h5_1-4.jpg" width="500"> 



Standards and publications:
- ISO/IEC 42001:2023
- ENISA - Multilayer Framework for Good Cybersecurity Practices for AI
- ENISA - Generative AI cybersecurity assessment report (to be published)
- ETSI - Secure Artificial Intelligence Technical Committee
- NIST - Artificial Intelligence Risk Management Framework

<br/>



---


   
### 2. Heikki ”zokol” Juva - State of Union

Regulations regarding hardware devices include two upcoming projects: 

1. Radio Equipment Directive **(RED)**:
- 18031-1: Network security (potential harm to network users)
- 18031-2: Protecting personal information of the user
- 18031-3: Financial misuse

2. Cyber Resilience Act **(CRA)**:
- Technical security requirements
- Vulnerability handling requirements

<br/>

**GOAL:** To measure hardware how they apply or not to those of regulations

**MINDSET:** Supporting market entry regulations monitoring

**RESEARCH QUESTIONS:** How do consumer devices communicate? To Where? Why?

<br/>

Timeline:
|Date|Description|
|---|---|
|11/2019|Launch of the Traficom IoT Cybersecurity label|
|1/2022|RED standard work starts|
|Q2 2024|CRA standard work starts|
|08/2025|RED is enforced|
|??/2026|CRA vulnerability notification starts|
|??/2027|CRA is enforced|

Learnings from RED will be fed to CRA. 

<br/>

Device classification:
* Device is connected to the network?
  * RED part 1 (18031-1) requirements apply
* Does the device collect personal information? Is the device a smart toy or childcare equipment?
  * RED part 2 (18031-2) requirements apply
* Does the device handle financial assets (money transactions, cryptocurrency, etc.)?
  * RED part 3 (18031-3) requirements apply

<br/>

Some requirements are quite promising/"good" requirements:
- **Vulnerability coordination.** Forces companies to establish vulnerability coordination and to report vulnerabilities to centralized authority
- **Input validation.** Input validation in all interfaces
- **Crypto.** Is cryptography the best practice concerning the protection of security assets or network assets?
- **Passwords.** Is the password strong, unique OR changed by the user?
- **Content filtering.** Is digital content loaded only from trusted sources? 


Other requirements might have some problems/"problematic" requirements:
- **Compatibility.** Less secure solutions are accepted, if they are required e.g. due to backward compatibility
- **Outsourcing security.** If external devices ensure security, most security measures do not need to be implemented
- **Paper-based evaluation.** Practically all requirements are proven by manufacturer-produced documentation

<br/>

##### REAL LIFE TESTING. CASE EAGLE

TESTING PROCESS

- EagleCam - IP Camera
- EagleSock - O2-meter and heart rate monitor
- Childcare product
- Collects video, audio, biometrics
- Connects to home WiFi
- Sends all collected information to the cloud

RED part 1 and RED part 2 applies. (<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/V.JPG" width="20"> PASS ,  <img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/X.JPG" width="20"> FAIL)


RED Part 1:
* <img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/V.JPG" width="20"> Software updates are enforced?
* <img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/X.JPG" width="20"> Device storage is secure
* <img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/X.JPG" width="20"> No known non-mitigated exploitable vulnerabilities? 
* <img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/X.JPG" width="20"> Passwords are unique or strong?


RED Part 2:
* <img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/V.JPG" width="20"> All sensors that may affect user's privacy are documented?
* <img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/X.JPG" width="20"> User is notified if protection or privacy of personal information is altered? 
* <img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/X.JPG" width="20"> 3rd party access to personal information is denied by default? 
* <img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/X.JPG" width="20"> User or authorized parte can delete all personal information, passwords and other security information? 

<br/>

#### STATISTICS. 10 bestselling devices from Healthcare category

Popular consumer-facing internet-connected products were tested and evaluated using black-box testing methodologies.

* Countries by amount of data

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/h5_2-1.jpg" width="500">

* Domain communication overview
  
<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/h5_2-2.jpg" width="500">

* Protocols by amount of data

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/h5_2-3.jpg" width="500">

* TLS Ciphers by amount of data

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/h5_2-4.jpg" width="500">

* TLS Versions by amount of data

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h5/h5_2-5.jpg" width="500">

Implementation:
 - 90% use TLS and cert pinning
 - 80% implemented on baremetal (no OS)
 - 66% use WiFi for communication
 - 90% are online only temporarily

Most common issues:
- Data is not removed
- Sharing privacy information with 3rd party
- Complex manufacturing, the seller does not know how the device works

**Extra content: Can we find the original author of the device?**
* By analyzing the firmware of a device, it is possible to identify the original manufacturer, their contact information, and details about the company's research and development efforts.
















