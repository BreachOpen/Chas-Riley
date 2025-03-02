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

## Scenario
You are a cybersecurity analyst working at a company that specializes in providing IT services for clients. Several customers of clients reported that they were not able to access the client company website www[.]yummyrecipesforme[.]com and saw the error “destination port unreachable” after waiting for the page to load.<br /><br />

## Information Found Within tcpdump Log <br />
![Data Traffic](../../assets/img/cir/1.png) <br />
- The first two lines of the log file show the initial outgoing request from your computer to the DNS server for the IP address of yummyrecipesforme[.]com, sent in a UDP packet.
- The third and fourth lines show the response to your UDP packet, with ICMP 203.0.113.2 indicating the UDP packet was undeliverable to port 53 on the DNS server.
- Each request and response is preceded by timestamps indicating when the incident occurred. For example, 13:24:32.192571 translates to 1:24 p.m. and 32.192571 seconds.
- Following the timestamps, the source and destination IP addresses are shown. In the first line, the UDP packet travels from your computer (192.51.100.15) to the DNS server (203.0.113.2.domain). In the ICMP error response, the source is 203.0.113.2, and the destination is your computer (192.51.100.15).
- After the IP addresses, additional details such as protocol, port number, and flags are provided. In the first line, the query ID "35084" indicates flags associated with the UDP message. "A?" indicates a DNS request for an A record. The third line shows the response protocol as "ICMP" followed by the ICMP error message.
- The error message "udp port 53 unreachable" indicates that the UDP request for the domain "www[.]yummyrecipesforme[.]com" did not reach the DNS server because no service was listening on port 53.
- The remaining lines show two more ICMP packets were sent, but the same delivery error was received each time.

## Steps Taken:
1. **Determine which end the issue occurs** 
To investigate, we attempted to replicate the issue to determine if the issue is at the customer’s end or the client’s end.
- This technique simply assesses whether the issue is occurring on the customer's end or the client's end. This step is vital because it reduces the possible issues to half. Because our team was able to replicate the same problem, we now know the problem is attributed to the client.

![Browser Error Message](../../assets/img/cir/2.png)

2. **Utilize network analyzer tools**
Once replicated, we used the network analyzer tools Wireshark and tcpdump while attempting to load the page.
- This step is important because we are able to visually see the exact steps our computer took to establish a connection with the DNS server. This information replaces the generic response of "Unable to connect" that our browser is telling us.<br /><br />

3. **Analyze the traffic data**
The traffic shows multiple attempts of our UDP data packets attempting to contact the DNS server on port 53. However, the DNS server was unresponsive to our browser’s DNS queries when attempting to resolve the web server's domain name.


4. **Determine Cause**
Lastly, we developed the most likely cause through the process of elimination
- **Must be client side**: The customer and our system ran into the same issue. We also have to assume our system is functioning correctly. 
- **Webpage is not the issue**: The DNS server not responding prevents any connection from being created, meaning the HTTPS request is never sent to begin with. 
- **DNS Server or System Configuration is responsible**: All communication attempts end here.

5. **Follow up Team**
There are a few possibilities as to why this issue is occurring. The scenario had many details, and the investigation/correction portion is left to another team, however, I'd like to elaborate more on what the next team should be trying to identify.
- Determine previous trends of the client's system
- Is the client's company system well established or new?
- Has the client's company recently implemented any significant updates or additions to their digital security systems or operational programs?<br />
Assuming the client hasn't made any recent changes to their digital security systems or operational programs, the issue then falls on their DNS server.
- **Established DNS Server**: DNS server is most likely down or overloaded with requests.
- **New DNS Server**: Misconfiguration of the client’s DNS server itself, network, or firewall is preventing communication with the client’s customers.

![Cybersecurity Incident Report](../../assets/img/cir/3.png)
