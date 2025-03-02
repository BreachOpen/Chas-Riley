<div style="display: inline-block;">
  <a href="https://breachopen.github.io/Chas-Riley/">
    <img src="https://img.shields.io/badge/Home-3ba0e6" alt="Home">
  </a>
</div>

<div style="display: inline-block;">
  <a href="https://github.com/BreachOpen/Chas-Riley/" target="_blank">
    <img src="https://img.shields.io/badge/Github_Source-3ba0e6" alt="Github Source">
  </a>
</div>

---

# Cybersecurity Incident Report: Network Traffic Analysis

Bob, an IT employee at Jurassic Park, uses his desktop to log onto the company’s private wired router to access a file stored on the business's file server. The following sections outline the data flow, network protocols, and security measures involved in this process.

## Steps Taken:
1. **Determine which end the issue occurs** 
To investigate, we attempted to replicate the issue to determine if the issue is at the customer’s end or at the client’s end.
  - This technique simply assesses whether the issue is occuring on the customer's end or the client's end. This step is vital because it reduces the possible issues to half. Because our team was able to replicate the same problem, we now know the problem is attributed to the client.
 
2. **Utilyze network analyzer tools**
Once replicated, we used a network analyzer tool and tcpdump while attempting to load the page.
  - This step is important because we are able to visually see the exact steps our computer took to establish a connection with the DNS server. This information replaces the generic response of "Unable to connect" that our browser is telling us.

4. **Analyze the traffic data**
The traffic shows multiple attempts of our UDP data packets attempting to contact the DNS server on port 53. However, the DNS server was unresponsive to our browser’s DNS queries when attempting to resolve the web server's domain name.

5. **Determine Cause**
Lastly, we developed the most likely cause through the process of elimination
  - **Must be client side**: Customer and our system ran into same issue. We also have to assume our system is functioning correctly. 
  - **Webpage is not the issue**: The DNS server not responding prevents any connection from being created, meaning the HTTPS request is never sent to begin with. 
  - **DNS Server or System Configuration is responsible**: 
  


## Key Network Protocols and Concepts:
- **Ethernet Protocol**
- **Switching**
- **Wi-Fi**
- **MAC Address**
- **ARP (Address Resolution Protocol)**
- **IP (Internet Protocol)**
- **ICMP (Internet Control Message Protocol)**
- **Routing**
- **Subnetting**
- **NAT (Network Address Translation)**
- **TCP (Transmission Control Protocol)**
- **UDP (User Datagram Protocol)**
- **Port Numbers**
- **Flow Control**
- **Error Detection and Correction**
- **HTTP (Hypertext Transfer Protocol)**
- **DNS (Domain Name System)**
- **SSL/TLS (Secure Sockets Layer/Transport Layer Security)**
- **Public Firewall**
- **FTP (File Transfer Protocol)**

## Research and Analysis

#### SQL Injection (Application Layer Attack)
- **Incident:** October 2012 breach of 53 universities by "Team GhostShell"
- **Attack Method:** SQL Injection
- **Attackers' Goal:** Unclear, possibly hacktivism
- **Vulnerability Exploited:** Poor input validation, lack of parameterized queries
- **Recommendations:** Use parameterized queries, input validation, output encoding, access controls

#### MAC Address Spoofing (Network Access Layer)
- **Incident:** Aaron Swartz case involving MIT
- **Attack Method:** MAC Address Spoofing
- **Attackers' Goal:** Unauthorized network access, man-in-the-middle attacks
- **Vulnerability Exploited:** Trust in MAC addresses
- **Recommendations:** Implement port security, network access control solutions, 802.1X authentication

#### Man-in-the-Middle (MitM) Attack (Transport Layer Attack)
- **Incident:** 2011 DigiNotar breach in the Netherlands
- **Attack Method:** MitM Attack
- **Vulnerability Exploited:** Compromised digital certificates, lack of oversight
- **Recommendations:** Improved oversight, risk awareness, mitigation strategies

---

## Conclusion



---
