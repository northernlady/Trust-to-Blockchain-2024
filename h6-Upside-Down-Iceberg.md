##### Homework 6 - [Upside Down Iceberg](https://terokarvinen.com/trust-to-blockchain/#h6-upside-down-iceberg)

##### x) Summaries

###### Reference: [Dingledine, Mathewson and Syverson 2004: Tor: The Second-Generation Onion Route](https://css.csail.mit.edu/6.858/2022/readings/tor-design.pdf)

Goal: Frustrate attempts to link communication partners or trace a single user's multiple communications

Key Design Goals:
- Deployability: Easy to run, low liability, simple implementation
- Usability: Minimmum configuration desicions, easy implementable
- Flexibility: Well-specified and flexible protocol for future research
- Simple design: Clear security parameters, minimal complexity

Non-Goals:
- Not peer-to-peer
- Not secure against end-to-end attacks
- No protocol normalization
- Not steganographic

Threat Model. Adversary can:
- Observe some fraction of network traffic
- Generate/modify/delete/delay traffic
- Operate own routers
- Compromise some network nodes


<br/>

###### Reference: [Karunanayake, Ahmed, Malaney, Islam and Jha 2021: De-Anonymisation Attacks on Tor: A Survey](https://ieeexplore.ieee.org/ielx7/9739/9621320/09471821.pdf)

Tor, a leading anonymity network, provides privacy for users and hidden services but is increasingly misused for illegal activities.

Tor Network Components Overview:
- Onion Proxy (client software)
- Directory Servers (network status tracking)
- Entry/Guard Nodes (first connection point)
- Exit Nodes (final network hop)
- Hidden Services (anonymous .onion websites)
- Introduction Points(random nodes selected by Hidden Services)
- Rendezvous Points (random Tor nodes selected by the client)
- Bridges (Tor relays to bypass censorship)

The network creates multi-hop circuits to anonymize user traffic, with each node only knowing the immediately adjacent nodes in the communication path. This design aims to protect user privacy while providing a mechanism for anonymous internet browsing and hidden services.


<br/>

##### Reference: [Halonen, Ollikainen, Rajala 2023: PhishSticks - The Ethical Hackers tool for BadUSB](https://www.youtube.com/watch?v=bDzVevtZiWE)

Attack Method: PhishStick:
- Ethical hacker leaves a disguised USB device on CEO's desk
- Phishstick contains keylogger payload
- Triggers via Windows Run command
- Quickly fetches and installs payload via PowerShell
- Captures and exfiltrates keystrokes silently
- Removes log data after transmission via HTTP POST

Potential Impact:
- Credential theft
- Significant monetary losses
- Potential legal consequences

<br/>

---

##### a) TOR installation

Went to [https://www.torproject.org/download/](https://www.torproject.org/download/) and downloaded Tor Browser for Linux:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h6/a1.JPG" width="700">


Unpacked the file:

```
tar -xf tor-browser-linux-x86_64-14.0.3.tar.xz
```

Launched the browser:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h6/a2.JPG" width="700">

Connected to the Tor network

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h6/a3.JPG" width="700">

Navigated to the Ahmia search engine and clicked the **.onion available** button:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h6/a4.JPG" width="700">

Welcome to the Dark Web!

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h6/a5.JPG" width="700">

---

##### b) Browsing TOR network

Search engine for onion sites:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h6/b1.JPG" width="700">

<br/>
  
Human rights or civil rights organization:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h6/b2.JPG" width="700">

<br/>

Some marketplace:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h6/b3_1.JPG" width="700">

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h6/b3_2.JPG" width="700">

<br/>

Fraud:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h6/b4.JPG" width="700">

<br/>

Forum. Dread is a Reddit-like dark web discussion forum featuring news and discussions around darknet markets. [Wikipedia](https://en.wikipedia.org/wiki/Dread_(forum))

Apparently, there was a queue to access the forum:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h6/b5_1.JPG" width="700">

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h6/b5_2.JPG" width="700">

<br/>

A well known organization (with regular postal addresses, offices or similar presence outside darknet):

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h6/b6_1.JPG" width="700">

<br/>

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h6/b6_2.JPG" width="700">

---

#### c) Onion

Tor creates anonymity through layered encryption across multiple volunteer-operated nodes. The data is encrypted in nested layers, like an onion. Each relay only knows the immediately preceding and following relay, decrypting just one layer of routing information. This means no single node can trace the full path of communication. The system uses public key cryptography for initial connections, with symmetric encryption protecting the actual data transmission. By constantly changing circuit routes and using multiple encryption stages, Tor obscures both the origin and destination of internet traffic.


##### Reference: [How does Tor *really* work?](https://hackernoon.com/how-does-tor-really-work-c3242844e11f)
###### Reference: [Dingledine, Mathewson and Syverson 2004: Tor: The Second-Generation Onion Route](https://css.csail.mit.edu/6.858/2022/readings/tor-design.pdf)
---
#### d) What kind of the threat models could TOR fit? 

- Network distuption attacks
- Censorship attacks
- De-anonymization attacks


###### Reference: [Karunanayake, Ahmed, Malaney, Islam and Jha 2021: De-Anonymisation Attacks on Tor: A Survey](https://ieeexplore.ieee.org/ielx7/9739/9621320/09471821.pdf)

---

#### e) Don't stick that stick. 

PhishSticks Attack Mechanism:
- Disguised USB device left on target's desk
- Contains hidden keylogger payload
- Uses Windows Run command to quickly fetch malicious code
- Executes via PowerShell in a split second
- Captures and exfiltrates keystrokes silently
- Sends logged data via HTTP POST
- Automatically removes log data after transmission


High risk for organizations with:
- Weak physical security
- Limited USB device controls
- Lack of security awareness training

Risk Mitigation Strategies:

Technical Controls
- Disable USB autorun
- Implement USB device control policies
- Configure strict PowerShell execution policies

Physical Security:
- Restrict unauthorized device access
- Use security cameras
- Control physical workspace entry

Employee Training:
- Security awareness programs
- Phishing and social engineering education
- Protocol for handling unknown devices
- Reporting suspicious objects


##### References:
- [Why USB Attacks Are Back and How to Prevent Them](https://www.coro.net/blog/why-usb-attacks-are-back-and-how-to-prevent-them)
- [Preventing USB Attacks in 2024: The Importance of Encrypted USB Devices and Always-On Security](https://datalocker.com/blog/preventing-usb-attacks-in-2024-the-importance-of-encrypted-usb-devices-and-always-on-security/)

