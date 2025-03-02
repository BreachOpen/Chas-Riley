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
1: **Analyze Traffic Data**<br />
To investigate, we need to inspect the data in transit to get a better understanding of why the connection is timing out.
- To do this, we use a  network analyzer tool like Wireshark to inspect the data packets.

may be causing attempted to replicate the issue to determine if the issue is at the customer’s end or the client’s end.
- This technique simply assesses whether the issue is occurring on the customer's end or the client's end. This step is vital because it reduces the possible issues to half. Because our team was able to replicate the same problem, we now know the problem is attributed to the client.

![Browser Error Message](../../assets/img/cir/2.png)

2: **Utilize network analyzer tools**<br />
Once replicated, we used the network analyzer tools Wireshark and tcpdump while attempting to load the page.
- This step is important because we are able to visually see the exact steps our computer took to establish a connection with the DNS server. This information replaces the generic response of "Unable to connect" that our browser is telling us.<br />

3: **Analyze the traffic data**<br />
The traffic shows multiple attempts of our UDP data packets attempting to contact the DNS server on port 53. However, the DNS server was unresponsive to our browser’s DNS queries when attempting to resolve the web server's domain name.
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
