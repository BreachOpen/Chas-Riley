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



## Steps Taken:
1. **Determine which end the issue occurs** 
To investigate, we attempted to replicate the issue to determine if the issue is at the customer’s end or at the client’s end.
  - This technique simply assesses whether the issue is occuring on the customer's end or the client's end. This step is vital because it reduces the possible issues to half. Because our team was able to replicate the same problem, we now know the problem is attributed to the client.
 
2. **Utilyze network analyzer tools**
Once replicated, we used the network analyzer tools wireshark and tcpdump while attempting to load the page.
  - This step is important because we are able to visually see the exact steps our computer took to establish a connection with the DNS server. This information replaces the generic response of "Unable to connect" that our browser is telling us.

4. **Analyze the traffic data**
The traffic shows multiple attempts of our UDP data packets attempting to contact the DNS server on port 53. However, the DNS server was unresponsive to our browser’s DNS queries when attempting to resolve the web server's domain name.

5. **Determine Cause**
Lastly, we developed the most likely cause through the process of elimination
  - **Must be client side**: Customer and our system ran into same issue. We also have to assume our system is functioning correctly. 
  - **Webpage is not the issue**: The DNS server not responding prevents any connection from being created, meaning the HTTPS request is never sent to begin with. 
  - **DNS Server or System Configuration is responsible**: All communication attempts end here.

6. **Follow up Team**
There are a few possibilities as to why this issue is occuring. The scenario had many details, and the investigation/correction portion is left to another team, I'd like to elaborate more on what the next team should be trying to identify.
  - Determine previous trends of the client's system
    - Is the client's company system well established or new?
    - Has the client's company recently implemented any significant updates or additions to their digital security systems or operational programs?
Assuming the client hasn't made any recent changes to their digital security systems or operational programs, the issue then falls on their DNS server.
  - **Established DNS Server**: DNS server is most likely down or overloaded with requests.
  - **New DNS Server**: Misconfiguration of the client’s DNS server itself, network, or firewall is preventing communication with the client’s customers.

  ---

  
