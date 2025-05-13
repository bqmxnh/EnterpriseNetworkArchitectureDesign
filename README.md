# Network Architecture for O-UIT Company
## Introduction
- **O-UIT**, a prominent outsourcing firm, manages two primary locations in Ho Chi Minh City, Vietnam, tailored to support both global and local software development initiatives:
  - **Headquarters (Thu Duc):** Housed in a state-of-the-art 5-story building, this facility features a robust Data Center for handling and storing data for international projects. It accommodates leadership teams (CEO, HR, Project Manager, Technical Manager, Business Analyst, IT Manager) and technical units (developers, testers) delivering sophisticated software solutions to meet rigorous global standards.
  - **Branch Office (District 3):** Dedicated to domestic projects, this site supports adaptable development and testing teams that work in sync with the headquarters to deliver high-quality solutions for Vietnamese clients on schedule.
## Client Specifications
### Headquarters (Thu Duc)
| **Requirement** | **Details** |
|-----------------|-------------|
| **Devices Used** | - Developers and Testers: Restricted to company desktop PCs; personal laptops are not permitted to access the company network.<br>- CEO, HR, Project Manager, Technical Manager, Business Analyst, IT Manager: Permitted to use personal laptops and access internal Wi-Fi via authenticated accounts. |
| **Internal Wi-Fi** | - Provide an internal Wi-Fi system with user authentication (via accounts).<br>- Designated for CEO, HR, Project Manager, Technical Manager, Business Analyst, and IT Manager. |
| **Public Wi-Fi** | - Provide a public Wi-Fi system for guests or low-security needs.<br>- Use a separate Internet connection from the internal Wi-Fi. |
| **Virtual Server Hardware** | - Deploy hardware systems to support application testing phases.<br>- Ensure high performance and scalability for future workload requirements. |
| **Cloud Services** | - Utilize cloud services for deploying applications during the staging phase, allowing clients to test before launch.<br>- Ensure security and data protection during cloud deployment. |
| **Internal Network Connectivity** | - Establish an internal network to connect departments, development teams, testers, servers, and internal applications. |

### Branch Office (District 3)
| **Requirement** | **Details** |
|-----------------|-------------|
| **Devices Used** | - Developers and Testers: Restricted to company desktop PCs; personal laptops are not permitted to access the company network. |
| **Site-to-Site VPN** | - Implement a site-to-site VPN to deploy applications to the Data Center at the headquarters.<br>- Ensure high security and stable connectivity between the two locations. |
| **Wi-Fi** | - Provide a separate Wi-Fi system at the branch with independent Internet access, isolating work traffic from company PCs and public connections. |
| **Data Center Connectivity** | - Ensure stable connectivity between the branch and the Data Center at the headquarters for application deployment. |
| **Security Systems** | - Implement security solutions to ensure safe connectivity and access between the branch and headquarters, especially for the site-to-site VPN. |

## Network Topology
The network topology diagram outlines the connectivity framework between the headquarters (Thu Duc) and the branch office (District 3), encompassing routers, switches, the Data Center, and subnets for departments, Wi-Fi, and site-to-site VPN.
![Network Topology Diagram](https://github.com/user-attachments/assets/436ed20e-ab74-45ff-a972-f011ae8f9aeb)


## IP Address Allocation

### Headquarters (Thu Duc)
| **Subnet** | **Size** | **Address** | **Subnet Mask** | **Broadcast** |
|------------|----------|-------------|-----------------|---------------|
| Guest Network | 50 | 192.168.1.0 | 255.255.255.192 | 192.168.1.63 |
| Developer | 50 | 192.168.1.64 | 255.255.255.192 | 192.168.1.127 |
| Tester | 50 | 192.168.1.128 | 255.255.255.192 | 192.168.1.191 |
| Virtual Server – Data Center | 248 | 192.168.1.192 | 255.255.255.0 | 192.168.10.255 |
| Core Switch 1 – Router 1 | 2 | 192.168.2.0 | 255.255.255.252 | 192.168.2.3 |
| Core Switch 1 – Router 2 | 2 | 192.168.2.4 | 255.255.255.252 | 192.168.2.7 |
| Core Switch 2 – Router 1 | 2 | 192.168.2.8 | 255.255.255.252 | 192.168.2.11 |
| Core Switch 2 – Router 2 | 2 | 192.168.2.12 | 255.255.255.252 | 192.168.2.15 |
| CEO | 10 | 192.168.2.16 | 255.255.255.240 | 192.168.2.31 |
| HR | 10 | 192.168.2.32 | 255.255.255.240 | 192.168.2.47 |
| Project Manager | 10 | 192.168.2.48 | 255.255.255.240 | 192.168.2.63 |
| Technical Manager | 10 | 192.168.2.64 | 255.255.255.240 | 192.168.2.79 |
| Business Analyst | 10 | 192.168.2.80 | 255.255.255.240 | 192.168.2.95 |
| IT Manager | 10 | 192.168.2.96 | 255.255.255.240 | 192.168.2.111 |
| Router 1 – RouterDC | 2 | 192.168.2.112 | 255.255.255.252 | 192.168.2.115 |
| Router 2 – RouterDC | 2 | 192.168.2.116 | 255.255.255.252 | 192.168.2.119 |
| VPN | 2 | 192.168.5.0 | 255.255.255.192 | - |

### Branch Office (District 3)
| **Subnet** | **Size** | **Address** | **Subnet Mask** | **Broadcast** |
|------------|----------|-------------|-----------------|---------------|
| Developer | 50 | 192.168.4.0/26 | 255.255.255.192 | 192.168.4.63 |
| Tester | 50 | 192.168.4.64/26 | 255.255.255.192 | 192.168.4.127 |
| Core Switch 1 – Router 1 | 2 | 192.168.4.128/30 | 255.255.255.252 | 192.168.4.131 |
| Core Switch 1 – Router 2 | 2 | 192.168.4.132/30 | 255.255.255.252 | 192.168.4.135 |
| Core Switch 2 – Router 1 | 2 | 192.168.4.136/30 | 255.255.255.252 | 192.168.4.139 |
| Core Switch 2 – Router 2 | 2 | 192.168.4.140/30 | 255.255.255.252 | 192.168.4.143 |

## License
This project was developed as part of the **Network Design** course. All configurations, diagrams, and documentation are intended solely for educational and academic purposes. 
