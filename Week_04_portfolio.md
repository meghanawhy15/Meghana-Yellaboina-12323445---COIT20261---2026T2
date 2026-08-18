***********************************************************************************
### COIT20261: Network Services and Automation

# Week 4 | Classful & classless Addressing
 ***********************************************************************************
 
## Tutorial Activities

[HTTPClient-GUI-12323445-project](./HTTPClient-GUI-12323445.gns3project)

[HTTPClient-CLI-12323445-project](./HTTPClient-CLI-12323445.gns3project)

## Task 1: HTTP Client using GUI
The objective of this task was to access a web server using a graphical web browser and capture the generated HTTP traffic between the routers.
Network Topology

The network was divided into three subnets.

Subnet A
Firefox Host
Switch1
Subnet B
Router1
Router2
Switch2
Subnet C
Linux Server
Switch3

Router1 connected Subnet A and B.

Router2 connected Subnet B and C.
![HTTPClient-GUI-12323445-network diagram](./HTTPClient-GUI-12323445-network.png)

The Firefox Host was accessed using the built-in VNC client provided by GNS3.

Firefox was opened and the following URL was entered:

http://10.10.3.102

The webpage successfully displayed the default Networkers' Toolkit page hosted by the Linux Server.


![FireFox](./FireFox.png)



Packet capture was started on the Ethernet link between Router1 and Router2 located in Subnet B.

This location captures all HTTP traffic travelling between the client and server.
The packet capture file was opened in Wireshark.

The capture contained:

ARP packets
TCP Three-Way Handshake
HTTP GET Request
HTTP Response
ACK packets

The successful HTTP communication confirmed that the browser successfully retrieved the webpage from the Linux Server.

[HTTPClient-GUI-12323445-SubnetB-Captured Packets](./HTTPClient-GUI-12323445-SubnetB.pcap)

![HTTPClient-GUI-12323445-SubnetB-Captured Packets](./HTTPClient-GUI-12323445-SubnetB.png)
The Firefox browser successfully communicated with the remote web server over HTTP. The captured packets showed the TCP connection establishment followed by HTTP requests and responses between the client and server.

### Network Addressing

The network was divided into three separate IPv4 subnets. Static IP addresses and appropriate default gateways were configured so that traffic could be routed between Subnet A, Subnet B and Subnet C through Router1 and Router2.

After configuring the network, connectivity between the required hosts was verified before testing HTTP communication.

### Connectivity Testing

Before accessing the web server, connectivity between the client and server was tested using `ping`. Successful replies confirmed that the configured IP addresses, default gateways and routing between the subnets were functioning correctly.


### Testing Result

The Firefox client successfully accessed the web server at `http://10.10.3.102`, confirming end-to-end HTTP connectivity across the three-subnet network. The packet capture on Subnet B provided additional evidence that the traffic passed between Router1 and Router2. The capture showed TCP connection establishment followed by the HTTP request and response required to retrieve the webpage.

## Task 2: HTTP Client using Command Line
The purpose of this task was to access the same web server using Linux command-line HTTP clients (wget and curl) and compare their behaviour with a graphical browser.

Network Configuration

The Firefox Host was replaced with a Linux Host while maintaining the same IP configuration.

The remainder of the network remained unchanged.

![HTTPClient-CLI-12323445-network_diagram](./HTTPClient-CLI-12323445-network_diagram.png)
Using wget

The following command was executed:

wget http://10.10.3.102

The webpage was successfully downloaded and saved locally as:

index.html

The terminal displayed the download progress, confirming successful communication with the HTTP server.
![weget](./weget.png)
Using curl

The following command was executed:

curl -o page.html http://10.10.3.102

The webpage was downloaded and stored as:

page.html

The terminal displayed transfer statistics including download percentage, transfer speed, and total bytes received.
![curl](./curl.png)
Packet Capture

Packet capture was again started on the Router1–Router2 link while the wget command was executed.
The captured packets verified that both wget and curl successfully communicated with the web server.
[HTTPClient-CLI-12323445-Captured Packets](./HTTPClient-CLI-12323445.pcap)

![HTTPClient-CLI-12323445-Captured Packets](./HTTPClient-CLI-12323445.png)

### Testing Result

Both command-line HTTP clients successfully accessed the server at `10.10.3.102`. The `wget` command downloaded the webpage and saved it locally as `index.html`, while `curl` downloaded the content and saved it as `page.html`. This demonstrated that HTTP communication can be performed without a graphical browser and is therefore suitable for scripting and automation.

## Key Concepts Learned

- **HTTP:** An application-layer protocol used for communication between web clients and web servers.
- **HTTP Client:** Software such as Firefox, wget or curl that sends requests to a web server.
- **HTTP Server:** Provides web content in response to HTTP requests from clients.
- **TCP Three-Way Handshake:** Establishes a TCP connection before HTTP data is exchanged.
- **HTTP GET:** A request used by a client to retrieve a resource from a web server.
- **Default Gateway:** Allows a host to send traffic to destinations outside its local subnet.
- **Routing:** Routers forward packets between different IP subnets.
- **wget:** A command-line HTTP client commonly used to download web resources.
- **curl:** A flexible command-line tool used to transfer data using URLs.
- **Packet Capture:** Allows network traffic to be recorded and analysed to verify protocol behaviour.

**********************************************************************************************************************
### Self Reflection
**************************************************************************************************************************
During Week 4, I developed a stronger understanding of HTTP communication by using both graphical and command-line HTTP clients. Accessing the web server through Firefox helped me understand how browsers communicate with web servers, while using wget and curl demonstrated how HTTP requests can be automated without a graphical interface. Comparing these approaches showed that command-line tools are lightweight, efficient, and well suited for scripting and network administration tasks.

Capturing traffic between the routers and analysing it in Wireshark improved my ability to identify the sequence of ARP, TCP, and HTTP packets exchanged during web communication. Observing the TCP handshake, HTTP GET requests, and server responses gave me practical insight into how web applications operate over a network. Overall, this tutorial strengthened my confidence in configuring multi-subnet networks, using different HTTP clients, capturing network traffic, and interpreting protocol behaviour through packet analysis. These skills are valuable for future networking, system administration, and cybersecurity tasks.

**************************************************************************************************************************
