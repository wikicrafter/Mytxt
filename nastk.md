### Things that network administrator shall to know:
* Network architecture and protocols: Understanding the different layers of the OSI model and how various protocols such as TCP/IP, DNS, DHCP, and SMTP operate is essential for a network administrator.
* Network security: Knowing how to secure a network against threats such as hacking, malware, and viruses is crucial. This includes understanding firewalls, VPNs, and intrusion detection/prevention systems.
* Network monitoring and troubleshooting: Being able to monitor network performance and troubleshoot issues as they arise is critical to maintaining network uptime and availability.
* Cloud computing and virtualization: Familiarity with cloud-based services and virtualization technologies such as AWS, Azure, and VMware is becoming increasingly important as more and more organizations move to the cloud.
* Network automation and scripting: As networks become more complex and the amount of data they handle continues to grow, the ability to automate tasks and use scripting languages such as Python and PowerShell to manage networks is becoming increasingly valuable.
* Network management and documentation: Keeping detailed documentation of network topology, IP addresses, and other key information is important for maintaining a clear overview of the network and making it easier to troubleshoot issues and plan for future changes.


___
### Let's talk about the different layers of the OSI model and how various protocols such as TCP/IP, DNS, DHCP, and SMTP operate is essential for a network administrator.

The OSI (Open Systems Interconnection) model is a framework that describes how different protocols and technologies work together to enable communication between devices on a network. It consists of seven layers, each with a specific function:
1. Physical Layer: This is the lowest layer and deals with the physical aspects of transmitting data, such as cables and connectors.
2. Data Link Layer: The data link layer is responsible for providing reliable communication between devices on the same network segment. It includes protocols like Ethernet and ARP.
3. Network Layer: The network layer is responsible for routing data between different network segments. It includes protocols like IP, ICMP, and IGMP.
4. Transport Layer: The transport layer is responsible for ensuring that data is delivered reliably and in the correct order. It includes protocols like TCP and UDP.
5. Session Layer: The session layer is responsible for establishing, maintaining, and terminating connections between devices.
6. Presentation Layer: The presentation layer is responsible for converting data into a format that can be understood by the application layer.
7. Application Layer: The application layer is the highest layer and deals with the specific applications and services that run on top of the network, such as HTTP, FTP, DNS, DHCP, and SMTP.

As a network administrator, it is important to understand how these different layers and protocols work together to ensure that data is transmitted and received correctly and securely. This understanding will allow you to troubleshoot issues, optimize network performance, and secure the network against potential threats.

Here are some additional details on how specific protocols and technologies operate at each layer of the OSI model:
* At the Physical Layer, protocols like Ethernet and Wi-Fi define how data is transmitted over physical media such as cables and wireless radio waves. Network administrators need to understand how different types of cables (e.g. copper, fiber) and connectors (e.g. RJ-45, SFP) work and how to properly terminate and test them.
* At the Data Link Layer, protocols like Ethernet and ARP (Address Resolution Protocol) are used to create a logical link between devices on the same network segment. Ethernet is used to define how data is packaged into frames and sent over the physical link, while ARP is used to map a device's IP address to its physical MAC address. Network administrators need to understand how these protocols work and how to troubleshoot issues such as collisions and duplex mismatches.
* At the Network Layer, protocols like IP, ICMP (Internet Control Message Protocol), and IGMP (Internet Group Management Protocol) are used to route data between different network segments. IP is used to assign unique addresses to devices and to route data based on those addresses. ICMP is used to send error messages and other control messages between devices, and IGMP is used to manage multicast traffic. Network administrators need to understand how routing works, how to configure and troubleshoot routers, and how to secure the network against attacks such as IP spoofing.
* At the Transport Layer, protocols like TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are used to ensure that data is delivered reliably and in the correct order. TCP establishes a virtual connection between devices and guarantees that data is retransmitted if necessary, while UDP is a simpler, connectionless protocol that doesn't guarantee delivery. Network administrators need to understand how these protocols work and how to optimize their performance and security.
* At the Session Layer, protocols like RPC (Remote Procedure Call) and SQL (Structured Query Language) are used to establish, maintain, and terminate connections between devices. Network administrators need to understand how these protocols work and how to troubleshoot issues such as connection timeouts and dropped sessions.
* At the Presentation Layer, protocols like SSL (Secure Sockets Layer) and TLS (Transport Layer Security) are used to encrypt and decrypt data and to convert data into a format that can be understood by the application layer. Network administrators need to understand how these protocols work and how to configure and troubleshoot them to ensure secure communication.
* At the Application Layer, protocols like HTTP (Hypertext Transfer Protocol), FTP (File Transfer Protocol), DNS (Domain Name System), DHCP (Dynamic Host Configuration Protocol), and SMTP (Simple Mail Transfer Protocol) are used to provide specific services and applications. Network administrators need to understand how these protocols work and how to configure and troubleshoot them to ensure that the services they provide are available and performing well.

This is a high-level summary of how different protocols and technologies operate at each layer of the OSI model, and a network administrator should have a deep understanding of the protocols and technologies that are used in their network.


___

### Securing a network against threats such as hacking, malware, and viruses is a complex process that involves multiple layers of defense. Some steps that can be taken to secure a network include:
* Firewall: A firewall is a device or software that controls access to a network. It can be configured to block incoming traffic from known malicious sources, and to allow traffic from trusted sources.
* Network Segmentation: Network segmentation is the process of dividing a network into smaller segments, or subnets. This can help to limit the spread of malware or a hacker's access to the network.
* Virtual Private Network (VPN): A VPN is a secure connection between two or more devices that is created over the internet. It can be used to allow remote employees to access a company's network securely.
* Antivirus and Anti-malware software: Antivirus and anti-malware software should be installed on all devices that connect to the network, including servers, workstations, and mobile devices. These programs can detect and remove malware, viruses, and other malicious software.
* Patch management: Regularly applying software updates and patches can help to close security vulnerabilities that are discovered in the software.
* Access Control: Setting up an access control system such as a login/password to control access to the network, devices and resources.
* Network monitoring: Regularly monitoring the network and devices can help to detect unusual activity or suspicious traffic.
* Employee education: Training employees on security best practices and the importance of security can help to reduce the risk of human error, which can lead to security breaches.
* Backups: Regularly backing up important data can help to minimize the impact of a security breach or other disaster.

These are just a few examples of the steps that can be taken to secure a network against threats such as hacking, malware, and viruses. A network administrator should also stay current with the latest security threats, best practices and technologies to keep the network safe.

It's important to note that securing a network is an ongoing process, as new threats and vulnerabilities are constantly being discovered. It's also important to have an incident response plan in case of a security incident.



