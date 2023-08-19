# Planning-IPv4-Assignments-for-Devices
Successfully planned an IPv4 address assignment of over 400 devices at QADev for its UK headquarters in London and three branch offices in Manchester, Glasgow, and Birmingham. Each of the branch offices, were to use IP addresses from the list of addresses assigned to the London office. 


<p><img src="QADev-Network-Diagram.png" alt="QADev Newtork Diagram" width="900" height="600"></p>
<br>
<h3>Background</h3>
<link rel="stylesheet" href="/css/styles.css">
<table class="tg">
<thead>
  <tr>
    <th class="tg-fymr">Location</th>
    <th class="tg-fymr">Computer and device requirements</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky">Manchester</td>
    <td class="tg-0pky">300 desktop computers</td>
  </tr>
  <tr>
    <td class="tg-0lax"></td>
    <td class="tg-0lax">100 laptops connecting to both wireless and wired networks</td>
  </tr>
  <tr>
    <td class="tg-0lax"></td>
    <td class="tg-0lax">50 tablet devices connecting to the wireless network only</td>
  </tr>
  <tr>
    <td class="tg-0lax">Glasgow</td>
    <td class="tg-0lax">100 desktop computers</td>
  </tr>
  <tr>
    <td class="tg-0lax"></td>
    <td class="tg-0lax">50 laptops connecting to both wireless and wired networks</td>
  </tr>
  <tr>
    <td class="tg-0lax"></td>
    <td class="tg-0lax">20 tablet devices connecting to the wireless network only</td>
  </tr>
  <tr>
    <td class="tg-0lax">Birmingham</td>
    <td class="tg-0lax">100 desktop computers</td>
  </tr>
  <tr>
    <td class="tg-0pky"></td>
    <td class="tg-0pky">75 laptops connecting to both wireless and wired networks</td>
  </tr>
  <tr>
    <td class="tg-0pky"></td>
    <td class="tg-0pky">150 tablet devices connecting to the wireless network only</td>
  </tr>
</tbody>
</table><br>
QADev uses Office 365 for all email and file access for the UK branch offices, with some shared folders located in the London regional office on Windows Server 2022 servers. Because all offices have fast and highly available WANconnections to the London office, QADev was not planning to deploy any servers in the branch offices at first.The team had assigned the subnets 172.16.18.0/18 to the London regional office. The London office was currently using the network assignments shown in the following table.<br>
<table class="tg">
<thead>
  <tr>
    <th class="tg-fymr">IP Subnet</th>
    <th class="tg-fymr">Purpose</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky">172.16.18.0 /24</td>
    <td class="tg-0pky">Network devices and printers</td>
  </tr>
  <tr>
    <td class="tg-0lax">172.16.19.0 /24</td>
    <td class="tg-0lax">Servers</td>
  </tr>
  <tr>
    <td class="tg-0lax">172.16.20.0 /24 to <br>172.16.45.0 /24</td>
    <td class="tg-0lax">Desktop</td>
  </tr>
  <tr>
    <td class="tg-0lax">172.16.46.0 /24 <br>to 172.16. 55.0 /24</td>
    <td class="tg-0lax">Wireless devices</td>
  </tr>
</tbody>
</table><br>
<h3>My Task</h3>
1. I was responsible for planning an IPv4 address assignment for each of the branch offices, using IP addresses from the list of addresses assigned to the London office.<br> 
2. I needed to ensure that the IP addresses assigned to computers connected to wired connections differed from the IP addresses assigned to devices connected to the wireless networks                                                                          3. I had to plan the IP address assignment for each UKbranch office. The IP addressing scheme must meet the following requirements: <br>
    •Wired and wireless clients must be assigned IP addresses from different IP address ranges<br>
    •Each branch office location should have dedicated IP address ranges<br>
    •Keep subnets in branch office locations as simple as possible<br>
    •Ensure that branch office subnets have IP addresses for all potential wired and wireless clients that might request an IP       address<br>
    
<h3>My Solution  :cloud:</h3>
I used a subnet table to calculate IP address ranges for each resource in each location. I used the subnet assignment range for the following resources: Network devices and printers, Servers, Desktop and Wireless devices.<br>

<b>Interactions between London and Other Branch Offices:</b><br>

<b>Data Exchange</b>:
London is a hub for other locations.<br>

<b>Communication Patterns:</b>
Azure and Office365 were be used to build and manage applications that will be accessed from any of the locations.<br>

<b>Shared Resources:</b>
Any shared folders located on Windows Server 2022 servers in the London regional office can be accessed from all branch offices.<br>

<b>Communication Security:</b>
Virtual Network Peering or VPN Gateway will be used between London and branch offices to ensure secure data transmission.
Each branch office has its own dedicated subnet and IP address range.

<b>Security and Compliance:</b>
Security resources used are:<br> 1. Azure Network Security Groups (NSGs) to control inbound and outbound traffic between London and branch offices, ensuring security and compliance.<br> 2. Azure Firewall and Azure Bastion which are deployed in the London office to enhance network security and control access to resources.<br>

<b>Monitoring and Management:</b>
Azure Monitor and Azure Security Center is used to monitor network activity, detect threats, and ensure compliance across all locations.<br>

<b>Backup and Recovery:</b>
Backup and disaster recovery solutions, such as Azure Site Recovery was configured to ensure continuity in case of disruptions.<br>

<b>Documentation and Troubleshooting:</b>
I ensure Network architecture, IP assignments, security configurations, and communication paths are well-documented for reference and troubleshooting.
With this plan, London acts as a central hub for network communication, resource access, and data exchange with branch offices in Glasgow, Birmingham, and Manchester. The WAN connection ensures efficient and secure communication, while Azure networking features enhance security, monitoring, and management across all locations.
