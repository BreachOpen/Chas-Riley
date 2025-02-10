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

## Research Paper: Network Communication and Security Analysis

This research paper explores and analyzes the flow of network communication and the various layers involved when an IT employee at Jurassic Park accesses a file stored on the company's private server. Additionally, it delves into specific network vulnerabilities and attacks, including SQL Injection, MAC Address Spoofing, and Man-in-the-Middle (MitM) attacks. The research underscores the significance of robust cybersecurity measures and provides insights into securing networks against common threats.

---

### Resource Request and Data Flow Analysis

Bob, an IT employee at Jurassic Park, uses his desktop to log onto the company’s private wired router to access a file stored on the business's file server. The following sections outline the data flow, network protocols, and security measures involved in this process.

#### Data Flow:
1. Bob's desktop to the internal switch
2. Internal switch to the private router
3. Private router to the firewall
4. Firewall to the internet
5. Internet to the public server (if accessed)
6. Public server to the internet
7. Internet to the firewall
8. Firewall to the private router
9. Private router to the internal switch
10. Internal switch to Bob's desktop

#### Key Network Protocols and Concepts:
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

### Research and Analysis

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

Summarize the findings of your research paper, highlighting the key points and insights gained from the analysis. Discuss the importance of implementing robust cybersecurity measures to protect against common network vulnerabilities and attacks.

---

## References

List all the references cited in your research paper in the appropriate citation style.
