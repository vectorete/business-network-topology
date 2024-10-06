<a id="readme-top"></a>

<!-- PROJECT SHIELDS -->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/vectorete/business-network-topology">
    <img src="images/logo.png" alt="Logo" width="30%">
  </a>

<h3 align="center">Network Topology Project for IT Consulting Business</h3>

<p align="center">
A packet tracer project that represents a secure network topology design for a medium-small IT consulting business to ensure efficient operations, secure data management, and seamless communication.
    <br />
    <a href="https://github.com/vectorete/business-network-topology"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/vectorete/business-network-topology">View Demo</a>
    ·
    <a href="https://github.com/vectorete/business-network-topology/issues/new?labels=bug&template=bug-report---.md">Report Bug</a>
    ·
    <a href="https://github.com/vectorete/business-network-topology/issues/new?labels=enhancement&template=feature-request---.md">Request Feature</a>
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">🔎 About The Project</a> ||
      <a href="#business-overview"> 📊 Business Overview</a>
      <ul>
        <li><a href="#features">✨ Features</a></li>
        <li><a href="#built-with">🔨 Built With</a></li>
        <li><a href="#network-topology">🖧 Network Topology</a></li>
        <li><a href="#config-note">📁 Configuration Note </a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">🚀 Getting Started</a>
      <ul>
        <li><a href="#prerequisites">📝 Prerequisites</a></li>
        <li>
          <a href="#installation">📥 Installation</a>
        </li>
      </ul>
    </li>
    <li>
      <a href="#security">🛡️ Security</a>
      <ul>
        <li><a href="#logical-security">💡 Logical Security</a></li>
        <li><a href="#physical-security">🔒 Physical Security</a></li>
        <li><a href="#monitoring-maintenance">🧪 Monitoring and Maintenance</a></li>
      </ul>
    </li>
    <li><a href="#possible-improvements">🔧 Possible Improvements</a></li>
    <li><a href="#resources">📚 Resources</a></li>
    <li><a href="#contributing">🤝 Contributing</a></li>
    <li><a href="#license">©️ License</a></li>
    <li><a href="#contact">☎️ Contact</a></li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->
## 🔎 About The Project <a id="about-the-project"></a>

  <a href="https://github.com/vectorete/business-network-topology">
    <img src="images/topology.png" alt="Logo" width="100%">
  </a>

The Network Topology Project for the fictitious IT Consulting Business aims to establish a secure and effective network infrastructure suitable for a small-medium size business. This setup makes communication between departments, management of information and carrying out business operations effective.

### 📊 Business Overview <a id="business-overview"></a>

#### **Industry**: IT Consulting

#### **Number of Employees**: 50

#### **Location**: Single office building with three floors

**Departments and Their Layout**:

- **Top Floor**:
  - **Executive (5 employees)**: Senior management and leadership team.
  - **Finance (10 employees)**: Handles the budget aspects, accounting, and financial reporting.
  - **HR (5 employees)**: Manages recruitment, employee relations, and benefits.

- **Middle Floor**:
  - **IT (10 employees)**: Responsibles for the network maintenance, technical support, and IT infrastructure.
  - **Sales (10 employees)**: Manages client relationships, sales strategies, and business development.

- **Ground Floor**:
  - **Customer Support (10 employees)**: Provides assistance to clients, handles inquiries, and manages support tickets.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### ✨ Features <a id="features"></a>

- **VLAN Segmentation**: Isolates traffic to improve security, avoiding lateral movement as far as possible, and performance.
- **DMZ Configuration**: Separates the servers, running services, from the internal network to shield them from direct exposure to the internet.
- **Multiple Firewalls**: Provides layered protection against external attacks and internal vulnerabilities.
- **Managed Switches**: Provides control over network traffic and improves scalability.
- **Security Measures**: Includes NIDS and a web application firewall to protect against various threats. It also has a honeypot to lure attackers and provide useful information of their pattern of attack.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- BUILT WITH -->
### 🔨 Built With <a id="built-with"></a>
* [![Cisco][Cisco]][Cisco-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### 🖧 Network Topology <a id="network-topology"></a>

The network topology is developed with a layered security strategy, ensuring that important systems are protected from external and internal threats.

**Network Topology**:

#### 1. **External Firewall**
The external firewall serves as the first line of defence, filtering traffic between the internet and the internal and DMZ networks. It blocks unauthorised access and protects against various threats and malicious IPs, ensuring a secure perimeter.

#### 2. **VLAN Segmentation**
The network is divided into several VLANs to enhance security and performance by isolating different types of traffic. This segmentation is applied both to the DMZ and the internal network:

- **DMZ VLANs:**
  - **VLAN10:** Dedicated to DNS server.
  - **VLAN20:** Web, Mail, and FTP server. The web server will be additionally protected by a Web Application Firewall (WAF).
  - **VLAN30:** Machine running the Network Intrusion Detection System (NIDS) and monitoring the network traffic, logging the suspicious traffic.
  - **VLAN40:** Honeypot machine, acting as a decoy to lure potential attackers, in order to learn from their attack pattern.

- **Internal Network VLANs:**
  - **VLAN10:** HR Department.
  - **VLAN20:** Finance Department.
  - **VLAN30:** Executive Department.
  - **VLAN40:** IT Department.
  - **VLAN50:** Sales Department.
  - **VLAN60:** Customer support.
  - **VLAN70:** Directory server and log centraliser for it's management.

This segmentation limits the area of attack, preventing unauthorised lateral movement as much as possible across the network, reducing the potential impact in case of a successful attack. 

#### 3. **DMZ Firewall and Perimeter Network (DMZ)**
The DMZ firewall protects the perimetrical network, where servers that can be accessed via the internet remain. Servers in the DMZ (Web, Mail, and FTP server) are separated from the internal network to prevent the danger of an intrusion spreading. If the servers are compromised, the internal firewall restricts unauthorised access to the internal network, ensuring that critical infrastructure remains secure.

#### 4. **Internal Firewall**
The internal firewall adds an additional layer of security, handling traffic between the DMZ and the internal network. This redundancy is significant, especially if the DMZ firewall gets compromised, ensuring that even with an intrusion, attackers would face considerable difficulties in getting to valuable assets in the internal computers. 

#### 5. **Layer 3 Switch**
The Layer 3 switch manages inter-VLAN routing, strengthening communication between multiple departments in addition to protection between the VLANs. Access control lists (ACLs) establish security policies throughout the network, allowing more efficient operations and improving security.

---

**Conclusion**
This network topology design implements a deep defense plan of action, with multiple layers of protection that secure the organization's essential assets. This layout ensures that the internal network remains protected, even in the event of a server compromise, by placing servers in a permiter network (DMZ) and establishing VLAN segmentation along external and internal networks. This setup plays an important role for preserving the integrity and availability of the company's activities.

---

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### 📁 Configuration Note <a id="config-note"></a>

There is a configuration file included in the project repository titled `topology.txt` that specifies the full network setup. This file provides a complete overview of the network setup, including specific settings for devices and interfaces. 

**Important Note**:
 - The Cisco Packet Tracer file included in the repository may not fully mimic the setup described in `topology.txt`, because of Packet Tracer's inability to support certain capabilities, such as dividing the interface in the Cisco Firewall ASA connected to the DMZ switch into subinterfaces, which are available in real devices.
- The `topology.txt` file covers the whole setup, including the complex configurations that are not reflected in Packet Tracer. For a comprehensive understanding of the network settings, please refer to this file. 

To access the configuration file, get it from the repository:
- [topology.txt](topology.txt)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- GETTING STARTED -->
## 🚀 Getting Started <a id="getting-started"></a>

To get a local copy up and running, follow these simple steps.

### 📝 Prerequisites <a id="prerequisites"></a>

* Cisco Packet Tracer (I recommend the last version)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### 📥 Installation <a id="installation"></a>

1. **Clone the repository**:
    ```sh
    git clone https://github.com/vectorete/business-network-topology.git
    ```

2. **Open the project file**:
    - Navigate to the cloned repository folder.
    - Open the `.pkt` file with Cisco Packet Tracer.

That's it! The network topology will load in Packet Tracer, and you can start exploring or modifying the design.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- SECURITY ADVICES -->
## 🛡️ Security <a id="security"></a>
### 💡 Logical Security <a id="logical-security"></a>
- **Host Intrusion Detection System (HIDS)**: Use a HIDS like OSSEC to monitor and evaluate movements on each host. It will help detect unusual behaviour, unauthorised access attempts, and potential intrusions.

- **Network Intrusion Detection System (NIDS)**: Use a NIDS like SNORT to constantly monitor network traffic to seek malicious activity or policy breaches. It will be giving real-time alerts each time a rule is triggered.

- **Web Application Firewall (WAF)**: Use a WAF like Cloudflare to defend web applications against the different threats and vulnerabilities. It will filter and monitor the multiple HTTP requests, limiting the unwanted traffic and preventing attacks such as SQL injection, cross-site scripting (XSS), and cross-site request forgery (CSRF).

- **Honeypot**: Use a honeypot, like Dionaea, to draw in and fool intruders. It will act as a decoy to gather intelligence about the attack techniques and tools used by the attackers, thus improving the knowledge around pattern attacks.

- **Log Management and Observability Platforms**: Use software like Splunk or ELK Stack to collect, analyse, and visualise log data. It will improve overall security by processing and representing data across multiple graphs to detect patterns and anomalous behavior.

- **Secure Passwords**: Enforce the usage of robust, complicated login credentials to make them difficult against brute-force attacks. Use tools like the [Password Checker](https://password.kaspersky.com) to check password security.

- **Awareness Program and Employee Training**: Establish a continuous security awareness program to educate staff about security best practices and common risks. Human error plays a big role in data breaches; therefore, training decreases the likelihood of phishing and other social engineering attacks.

- **Manual Backup**: Periodically make manual backups of significant data to guarantee that crucial data is not lost in case of system failures or attacks. It adds a further degree of security against data loss.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### 🔒 Physical Security <a id="physical-security"></a>
- **CCTV Cameras**: Make use of CCTV cameras at strategic locations so you can observe and record actions surrounding areas of concern, improving security and discouragement against illegal access.

- **Biometric Access Control**: Make use of biometric technology, such as fingerprint or retina scanners, to restrict access to server rooms as well as other sensitive places. It guarantees that only authorised workers can enter critically important sites.

- **Fire Protection System**: Make use of a complete fire protection system by incorporating alarms and suppression systems that will safeguard against fire dangers and protect essential infrastructure.

- **Uninterruptible Power Supply (UPS)**: Make use of UPS systems that supply backup power during outages, ensuring ongoing operations for important systems and preventing data loss or hardware damage.
 
- **Security Guard**: Hire a security guard to provide safety for employees, carry out regular patrols, and react to security-related incidents. Their presence strengthens overall security and allows quick reaction to any attack. 

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🧪 Monitoring and Maintenance <a id="monitoring-maintenance"></a>
- **Monitor NIDS Alerts**: Regularly check the Network Intrusion Detection System for any suspicious activity.

- **Honeypot Analysis**: Analyze data captured by the honeypot to learn from the attackers and see what are their pattern of attacks.

- **Log Management**: Use monitoring PCs to review and archive logs from various network components.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- IMPROVEMENTS -->
## 🔧 Possible Improvements <a id="possible-improvements"></a>

In the current Packet Tracer project, the VPN configuration and the RADIUS server setup are not yet completed. The VPN will provide secure remote access through encrypted communication. While configuring the RADIUS server will bring centralised authentication and access control within the internal network.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- RESOURCES -->
## 📚 Resources <a id="resources"></a>

Here are some additional resources that you may find useful:

### 🗃️ Documentation and Tools
- **[Cisco Packet Tracer Documentation](https://www.netacad.com/courses/packet-tracer)**: Official documentation and tutorials for using Cisco Packet Tracer.
- **[Cisco Official Website](https://www.cisco.com)**: Explore Cisco’s networking products and solutions.
- **[Splunk](https://www.splunk.com)**: The most professional software to search, monitor, and analyse log data. Widely used for log management and operational intelligence.
- **[ELK Stack](https://www.elastic.co/what-is/elk-stack)**: A combination of Elasticsearch, Logstash, and Kibana, used for searching, analyzing, and visualizing log data in real-time. It’s a popular choice for log management and data analysis.
- **[Kaspersky Password Checker](https://password.kaspersky.com)**: Online tool to evaluate the strength of passwords and see if they are resistant to brute-force attacks.
- **[Snort](https://www.snort.org)**: Open-source Network Intrusion Detection System (NIDS) that inspects real-time traffic to detect and prevent attacks.
- **[OSSEC](https://www.ossec.net)**: Open-source Host Intrusion Detection System (HIDS) that provides log analysis, file integrity checking, and real-time alerts.
- **[Cloudflare](https://www.cloudflare.com)**: Web security and performance company that offers services such of Web Application Firewall (WAF), DDoS protection, and content delivery.
- **[Dionaea](https://github.com/DinoTools/dionaea)**: Honeypot designed to capture and analyze malware, providing insights into attack methods and tools used by attackers.

### ✅ Security Best Practices
- **[OWASP (Open Web Application Security Project)](https://owasp.org)**: Best resource for web application security and best practices.
- **[NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)**: Guidelines and best practices to improve the overall.

### 🆘 Community and Support
- **[Cisco Community](https://community.cisco.com)**: Forum to discuss questions related Cisco products and networking topics.
- **[Reddit r/networking](https://www.reddit.com/r/networking)**: Subreddit about network-related discussions and questions.
- **[Stack Overflow](https://stackoverflow.com/questions/tagged/networking)**: Q&A site for programming and network-related queries.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- CONTRIBUTING -->
## 🤝 Contributing <a id="contributing"></a>

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement". Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- LICENSE -->
## ©️ License <a id="license"></a>

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- CONTACT -->
## ☎️ Contact <a id="contact"></a>

Victor Kravchuk Vorkevych - victorkravchuk19@gmail.com

Project Link: [https://github.com/vectorete/business-network-topology](https://github.com/vectorete/business-network-topology)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/vectorete/business-network-topology.svg?style=for-the-badge
[contributors-url]: https://github.com/vectorete/business-network-topology/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/vectorete/business-network-topology.svg?style=for-the-badge
[forks-url]: https://github.com/vectorete/business-network-topology/network/members
[stars-shield]: https://img.shields.io/github/stars/vectorete/business-network-topology.svg?style=for-the-badge
[stars-url]: https://github.com/vectorete/business-network-topology/stargazers
[issues-shield]: https://img.shields.io/github/issues/vectorete/business-network-topology.svg?style=for-the-badge
[issues-url]: https://github.com/vectorete/business-network-topology/issues
[license-shield]: https://img.shields.io/github/license/vectorete/business-network-topology.svg?style=for-the-badge
[license-url]: https://github.com/vectorete/business-network-topology/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/victorkvor
[product-project]: images/projectimg.png
[Cisco]: https://img.shields.io/badge/Cisco-1BA0D7?style=for-the-badge&logo=cisco&logoColor=white
[Cisco-url]: https://www.cisco.com
