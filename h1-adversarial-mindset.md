
### h1 - Adversarial mindset
#### x) Summaries

###### Reference: Hutchins et al 2011: [Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains](https://lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf)
The paper introduces the seven-stage Intrusion Kill Chain framework *(reconnaissance, weaponization, delivery, exploitation, installation, command and control (C2), actions on objectives)*, arguing that traditional vulnerability-focused security is insufficient against Advanced Persistent Threats (APT). Defenders need to develop a deep understanding of their adversaries - including their motivations, capabilities, methodologies, and behavioral patterns - to build robust defenses.

Intrusion Kill Chain model can be used to:
- Analyze intrusions systematically
- Identify indicators of compromise
-	Guide defensive responses
-	Prioritize security investments
-	Evaluate defense effectiveness

This framework reveals that persistent attackers actually create opportunities for defenders. Each time adversaries repeat their tactics, they expose predictable patterns that defenders can exploit. The key is recognizing these patterns. By understanding and anticipating attacker's repeated behaviors, defenders can steadily reduce the likelihood of successful breaches with each attempt.


<br/>  


###### Reference: Darknet Diaries. [EP 21: Black Duck Eggs](https://darknetdiaries.com/transcript/21/ )

In this Darknet Diaries episode, Ira Winkler, a cybersecurity expert, assembled a team of highly trained special agents for special missions. His breakthrough came when he was hired to test an investment bank’s security using social engineering. By persuading employees over the phone, he gathered login credentials and even received a computer preconfigured for their VPN. After this success, companies began hiring Ira to simulate internal breaches, showcasing the important role of human psychology in cybersecurity.

He eventually started his own security consulting company and gathered a team of highly skilled former intelligence officers. Ira began taking on bigger jobs, using his crew to gain access to some of the most secure buildings, including nuclear reactor facilities and banks. Once Ira’s team was hired to test vulnerabilities at an R&D center holding data worth billions. Through detailed planning, reconnaissance, and their diverse expertise, the team simulated an advanced adversary attack, exposing weaknesses and demonstrating the critical need for strong security defenses.

In addition to their main task, one of the team members accidentally discovered a Chinese spy scheme in a local restaurant, suspecting it was linked to intelligence activities targeting an R&D center. The restaurant had several suspicious features that raised red flags. The menu was written only in Chinese and included rare dishes (Black Duck Eggs) that you wouldn't usually find in a small town like this. They also offered free meeting rooms and special discounts for business gatherings, which seemed unusual. The FBI later dismantled this Chinese intelligence operation. This case demonstrates how intelligence operations can hide in plain sight using seemingly innocent businesses as fronts.

<br/>  

###### Reference: [MITRE ATT&CK FAQ](https://attack.mitre.org/resources/faq/)
###### Reference: [MITRE ATT&CK® Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise/)

MITRE ATT&CK is a comprehensive knowledge base developed in 2013 that documents cyber adversary behaviors. It consists of two main parts: Enterprise (covering IT networks and cloud) and Mobile devices.


| Key component | Description | Example |
|---------------|-------------|---------|
|**Tactics: The "why"**|Adversary's tactic goals|Initial Access|
|**Techniques: The "how"**|Specific actions to achieve those goals|Phishing |
|**Sub-techniques:**|More detailed descriptions of adversarial behaviors| Spearphishing Attachment|
|**Procedures:**|Actual observed attack | APT29 has used spearphishing emails with an attachment to deliver files with exploits to initial victims|

It can be considered as a structured hierarchy:   
Tactic (Initial Access) → Technique (Phishing) → Sub-technique (Spearphishing Attachment) → Procedure (APT29's specific PDF campaign)

<br/>     






#### a) Cyber Kill Chain and ATT&CK Enterprise matrix comparison

This two frameworks serve different purposes and have different levels of granularity.

**Cyber Kill Chain:**
-	Linear, sequential
-	7 stages (Reconnaissance → Weaponization → Delivery → Exploitation → Installation → Command & Control → Actions on Objectives)
-	High-level, strategic view of an attack lifecycle
-	Focuses on attack progression


**ATT&CK Enterprise Matrix:**
-	Comprehensive, modular, non-linear framework
-	Covers 14 tactical categories with hundreds of specific techniques and sub-techniques
- Granular, detailed and tactical view, including specific adversary behaviors
-	Regular updates (bi-annual) to reflect new threats and techniques
-	Provides real-world examples and procedure descriptions
-	Focuses on adversary behavior

<br/>     

---

#### b) Security incident: Equifax data breach

Equifax is one of the three largest consumer credit reporting agencies in the United States. In 2017, the data breach exposed the sensitive personal information of 147 million customers. This breach led to severe consequences, making it one of the most significant data breaches in history in terms of both scope and impact.

**Threat Actor:** Chinese military hackers. 

**Vulnerability:** Unpatched Apache Struts framework (CVE-2017-5638) - a critical vulnerability in the web application framework that allowed remote code execution.

**Exploit:** The attackers exploited the Apache Struts vulnerability to gain unauthorized access to Equifax's systems. They used this access to move within the network and download data over 76 days.

**Business Impact:**
-	147 million customers' sensitive data exposed (names, home addresses, phone numbers, dates of birth, social security numbers, and driver’s license numbers)
- Approximately 209,000 consumers credit card numbers were compromised
-	Major reputational damage
-	Multiple lawsuits
-	High-level executives resigned
-	Up to $700 million settlement with Federal Trade Commision
-	Equifax’s stock price dropped significantly

This incident highlights the importance of basic security practices like timely patching and the potential catastrophic impact of failing to address known vulnerabilities. It also demonstrates how a single vulnerability can lead to massive business consequences when exploited by sophisticated threat actors.

###### Reference 1: Equifax Data Breach [archive.epic.org](https://archive.epic.org/privacy/data-breach/equifax/)
###### Reference 2: Equifax Data Breach Explained: A Case Study [https://www.breachsense.com/](https://www.breachsense.com/blog/equifax-data-breach/)
###### Reference 3: 2017 Equifax data breach [Wikipedia](https://en.wikipedia.org/wiki/2017_Equifax_data_breach)    
###### Reference 4: Equifax, Inc. [Federal Trade Commision](https://www.ftc.gov/legal-library/browse/cases-proceedings/172-3203-equifax-inc)

 <br/>     

---
 
#### c) Installation Debian on Virtualbox 
###### Reference:  Tero Karvinen [Install Debian on Virtualbox](https://terokarvinen.com/2021/install-debian-on-virtualbox/)

HW: HP ENVY 700-160eo Desktop PC

Host OS: Windows 10 Home

1. Downloaded the Debian ISO image: debian-live-12.7.0-amd64-xfce
2. Downloaded the VirtualBox installer: VirtualBox-7.1.4-165100-Win
3. Installed VirtualBox successfully
4. Created a new Virtual Machine, skipping Unattended Install as advised
5. Verified the Controller IDE settings; the ISO disk image was already selected
 
   <img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h1_0.png" width="500">
   
6. Booted to Desktop to the newly created virtual machine and selecting "Live System"  
7. Confirmed successful desktop load and tested functionality: browser, mouse, keyboard, and network all working properly
   
   <img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h1_1.png" width="500">
   
8. Installed Debian, configured keyboard settings, and created user credentials. Installation completed successfully

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h1_2.png" width="500">
    
9. Logged in for the first time and re-tested browser functionality (network, keyboard, and mouse confirmed working)
   
10. Updated and upgraded the system, installed and enabled a firewall, then rebooted the virtual machine    
    ```
    sudo apt-get update    
    sudo apt-get -y dist-upgrade     
    sudo apt-get -y install ufw    
    sudo ufw enable
    ```

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h1_3.png" width="500">
