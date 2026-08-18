***********************************************************************************
### COIT20261: Network Services and Automation

# Week 1 | Introduction to Internetworking
 ***********************************************************************************
 
## Tutorial Activities
[GNS3 Introduction Project](./GNS3-Intro-12323445.gns3project)

## Task 1: Introduction to GNS3 Basics

GNS3 is not separate software, it is a virtual computer that operates on VirtualBox. There are supplied files provided in onedrive are used to install it. <br>
An IP address will appear once the VirtualBox machine has been started. <br>
To access the GNS3 interface and start a new project, you need to input this IP address into a web browser.<br>

![IP address in Virtual box](./Virtual_box.png)
<br>
<br>

Click "Add Blank Project" and enter a suitable project name to start a new project. <br>
Next, add a Linux host (shown by a computer icon) and fill in a text field with information such the host name, IP address, title, and date.<br>

![Introduction to gns3](./gns3_Intro.png)
<br>
<br>


Configure the host settings after that. By deleting the comment box and making the necessary adjustments, the IP address can be modified. <br>
Every host that is added to the project should go through the same configuration procedure.<br>

![Map topology](./Machine_ok.png)
<br>
<br>

Run the project once the configuration is complete. <br>
To view a host's IP address, right-click on it and choose the command option.<br>

![IP address of Host 1](./Ip_addr.png)
<br>

### Static IP Configuration

The Linux host was configured with a static IP address by editing the /etc/network/interfaces configuration before starting the node.

The basic configuration followed this structure:
    auto eth0
    iface eth0 inet static
    address 192.168.0.7
        netmask 255.255.255.0

This configuration ensures that the etho0 interface uses a manually assigned static IP address rather than obtaining one dynamically.


## Testing Results

After configuring the Linux host with a static IP address, I started the node and opened its web console.

I used the following Linux command to verify the network configuration:

`ip address show`

The command output confirmed that the configured IP address was successfully assigned to the `eth0` network interface. This verified that the changes made in `/etc/network/interfaces` were applied correctly and that the Linux host was configured successfully.

## Key Concepts Learned

- **GNS3:** A network simulation environment used to create and test virtual network topologies.
- **VirtualBox:** Provides the virtualisation environment required for the GNS3 virtual machine.
- **Static IP Addressing:** Allows an IP address to be manually assigned to a network interface.
- **eth0:** The network interface configured on the Linux host during this activity.
- **/etc/network/interfaces:** The Linux configuration file used to configure the static IP address.
- **ip address show:** A Linux command used to inspect network interfaces and verify assigned IP addresses.
- **Network Testing:** Command output can be used to confirm whether network configuration has been applied correctly.

## Additional Insight

This activity helped me understand that configuring an IP address and verifying an IP address are two separate stages. Editing `/etc/network/interfaces` defines the intended configuration, while using `ip address show` allows the administrator to verify that the configuration has actually been applied to the network interface. This demonstrates the importance of testing configuration changes rather than assuming they were successful.

**********************************************************************************************************************
### Self Reflection
**************************************************************************************************************************

The above is the Tutorial-1 class. In this class, we learned how to set up GNS3 with VirtualBox, create a project, add Linux hosts, configure IP addresses, and run a basic network simulation. Week 01 provided me with the foundation required for future networking and automation activities. GNS3 and Linux network configuration were unfamiliar concepts, but completing the practical tasks helped me understand how virtual network environments operate.

<br>

I learned how to create and manage a GitHub portfolio, which will help me document future technical tasks in a structured and professional way. Configuring a static IP address improved my understanding of network interfaces, IP addressing, and the relationship between configuration files and network functionality.

<br>

One challenge I faced was understanding the Linux network configuration syntax and interpreting command outputs. By reviewing the configuration steps and testing the IP address using the console, I became more confident in troubleshooting basic networking issues.

<br>

In future weeks, I aim to improve my understanding of networking commands, automation tools, and documentation practices so that I can create clearer and more detailed technical reports. This completes the first tutorial class.

<br>

***************************************************************************************************************************
