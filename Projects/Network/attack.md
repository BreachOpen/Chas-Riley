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

# Analyze Network Attacks

## Scenario
You work as a security analyst for a travel agency that advertises sales and promotions on the company’s website. The employees of the company regularly access the company’s sales webpage to search for vacation packages their customers might like. 
<br /><br />
One afternoon, you receive an automated alert from your monitoring system indicating a problem with the web server. You attempt to visit the company’s website, but you receive a connection timeout error message in your browser.
<br /><br />
You use a packet sniffer to capture data packets in transit to and from the web server. You notice a large number of TCP SYN requests coming from an unfamiliar IP address. The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. You suspect the server is under attack by a malicious actor. 
<br /><br />
You take the server offline temporarily so that the machine can recover and return to a normal operating status. You also configure the company’s firewall to block the IP address that was sending the abnormal number of SYN requests. You know that your IP blocking solution won’t last long, as an attacker can spoof other IP addresses to get around this block. You need to alert your manager about this problem quickly and discuss the next steps to stop this attacker and prevent this problem from happening again. You will need to be prepared to tell your boss about the type of attack you discovered and how it was affecting the web server and employees.
<br /><br />

## Steps Taken:
1: **Gather Traffic Data**<br />
To investigate, we need to inspect the data in transit to get a better understanding of why the connection is timing out.
- To do this, we use a  network analyzer tool like Wireshark to inspect the data packets.

2: **Analyze Traffic Data**<br />
- A large number of TCP SYN requests are coming from the IP address "203.0.113.0".
- In the 52 seconds of recorded traffic, we received 140 SYN requests from the IP address "203.0.113.0" <br />
![Excelsheet](../../assets/img/attack/1.png)

3: **Determine Reason for Connection Timing Out**<br />
- The traffic shows numerous SYN requests and it's reasonable to assume our organization's system is currently being attacked
- Based on the information available to us, this is most likely a Denial of service attack (DoS), but more specifically, a SYN Flood Attack.
<br /><br />

4: **Determine Cause**<br />
Lastly, we developed the most likely cause through the process of elimination
- **Must be client side**: The customer and our system ran into the same issue. We also have to assume our system is functioning correctly. 
- **Webpage is not the issue**: The DNS server not responding prevents any connection from being created, meaning the HTTPS request is never sent to begin with. 
- **DNS Server or System Configuration is responsible**: All communication attempts end here.

5: **Follow up Team**<br />
There are a few possibilities as to why this issue is occurring. The scenario had many details, and the investigation/correction portion is left to another team, however, I'd like to elaborate more on what the next team should be trying to identify.
- Determine previous trends of the client's system
- Is the client's company system well established or new?
- Has the client's company recently implemented any significant updates or additions to their digital security systems or operational programs?<br />
Assuming the client hasn't made any recent changes to their digital security systems or operational programs, the issue then falls on their DNS server.
- **Established DNS Server**: DNS server is most likely down or overloaded with requests.
- **New DNS Server**: Misconfiguration of the client’s DNS server itself, network, or firewall is preventing communication with the client’s customers.

![Cybersecurity Incident Report](../../assets/img/cir/3.png)
