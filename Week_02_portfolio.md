***********************************************************************************
### COIT20261: Network Services and Automation

# Week 2 | Transport Layer Protocol
 ***********************************************************************************
 
## Tutorial Activities

[Setting IP Addresses Project](./Setting-IP-12323445.gns3project)

This tutorial focused on configuring static IP addresses on Linux hosts in GNS3 and testing network connectivity using the ping command. Different methods of assigning IP addresses were explored, followed by connectivity testing using default and customised ping options.

## Task 1: Setting Static IP Addresses
Configure static IPv4 addresses on four Linux hosts using three different methods and verify the configuration.

Network Topology

![Project](./Setting_IP.png)

![Map](./Map_topology.png)

Host 1

Configured using the GNS3 Configure menu.
![1](./IP_Host1.png)

Host 2

Configured using the GNS3 Configure menu.
![2](./IP_Host2.png)

Host 3

Configured manually by editing and restarting the interface.
![3](./IP_Host3.png)

Configured using " ip address add " command.
![4](./IP_Host4.png)

### Ping Options Tested

- `ping -c 3 <IP>` – limits the test to three ping requests.
- `ping -i 4 <IP>` – changes the interval between ping requests to four seconds.
- `ping -c 2 -s 100 <IP>` – sends two ping requests with a data size of 100 bytes.

Testing these options demonstrated how ping can be customised depending on the type of network test being performed.

Result

All four hosts were successfully configured with static IPv4 addresses in the same subnet (10.1.1.0/24). The addresses were verified using the ip address show command. 

### Testing Result

The successful replies confirmed that Host1 could communicate with Host2 across the LAN. The ping summary also displayed the round-trip time (RTT), which measures the time required for a packet to travel from the source to the destination and for the response to return.

## Task 2: Testing Network Connectivity Using Ping

Verify communication between hosts and understand the behaviour of the ping command.
Basic Ping

Host1 successfully pinged Host2.
![1to2](./Host_1-ping-Host_2.png)

Ping to Wrong Address
Host1 attempted to ping 10.1.1.7, which does not exist.
The result showed:
Destination Host Unreachable
100% Packet Loss
![Diff_IP](./Diff_IP.png)

Ping with Options

Different options were tested:
ping -c 3
ping -i 4
ping -c 2 -s 100
These options changed the number of packets, interval between packets and packet size.
![ping-c](./ping-c.png)

Result

Successful communication was achieved between valid hosts. Testing an invalid IP address demonstrated packet loss and unreachable destination messages. Different ping options altered the behaviour of the command while still allowing connectivity testing.


## Key Concepts Learned

- **Static IPv4 Addressing:** A fixed IP address can be manually assigned to a network interface.
- **Subnet:** Devices within the same subnet can communicate directly through the Ethernet switch.
- **Persistent Configuration:** IP addresses configured through /etc/network/interfaces remain available after reboot.
- **Temporary Configuration:** An address assigned using `ip address add` takes effect immediately but does not persist after reboot.
- **Ping:** A network diagnostic command used to determine whether another device is reachable.
- **Packet Loss:** Indicates that transmitted packets did not successfully receive responses.
- **Round-Trip Time (RTT):** Measures the time required for a request to reach its destination and for the response to return.

**********************************************************************************************************************
### Self Reflection
**************************************************************************************************************************

During Week 2, I learned how to configure static IPv4 addresses on Linux hosts using three different methods in GNS3. I used the GNS3 configuration interface, manually edited the /etc/network/interfaces file, and assigned an IP address using the ip address add command. This helped me understand the differences between persistent and temporary IP configurations.

I also learned how to verify network settings using the ip address show command and ensured that all hosts belonged to the same subnet before testing connectivity.

Using the ping command improved my understanding of network communication. I observed successful communication between hosts with valid IP addresses and learned how incorrect IP addresses result in destination unreachable messages and 100% packet loss. I also experimented with different ping options such as packet count, interval, and packet size, which demonstrated how command-line parameters affect network testing.

Overall, this tutorial strengthened my practical knowledge of Linux networking, static IP configuration, and basic network troubleshooting using GNS3.

************************************************************************************************************************
