# Network Architecture for O-UIT Company
## Introduction
- **O-UIT**, a prominent outsourcing firm, manages two primary locations in Ho Chi Minh City, Vietnam, tailored to support both global and local software development initiatives:
  - **Headquarters (Thu Duc):** Housed in a state-of-the-art 5-story building, this facility features a robust Data Center for handling and storing data for international projects. It accommodates leadership teams (CEO, HR, Project Manager, Technical Manager, Business Analyst, IT Manager) and technical units (developers, testers) delivering sophisticated software solutions to meet rigorous global standards.
  - **Branch Office (District 3):** Dedicated to domestic projects, this site supports adaptable development and testing teams that work in sync with the headquarters to deliver high-quality solutions for Vietnamese clients on schedule.
## Project Context
### Client Specifications
#### Headquarters (Thu Duc)
| **Requirement** | **Details** |
|-----------------|-------------|
| **Devices Used** | - Developers and Testers: Restricted to company desktop PCs; personal laptops are not permitted to access the company network.<br>- CEO, HR, Project Manager, Technical Manager, Business Analyst, IT Manager: Permitted to use personal laptops and access internal Wi-Fi via authenticated accounts. |
| **Internal Wi-Fi** | - Provide an internal Wi-Fi system with user authentication (via accounts).<br>- Designated for CEO, HR, Project Manager, Technical Manager, Business Analyst, and IT Manager. |
| **Public Wi-Fi** | - Provide a public Wi-Fi system for guests or low-security needs.<br>- Use a separate Internet connection from the internal Wi-Fi. |
| **Virtual Server Hardware** | - Deploy hardware systems to support application testing phases.<br>- Ensure high performance and scalability for future workload requirements. |
| **Cloud Services** | - Utilize cloud services for deploying applications during the staging phase, allowing clients to test before launch.<br>- Ensure security and data protection during cloud deployment. |
| **Internal Network Connectivity** | - Establish an internal network to connect departments, development teams, testers, servers, and internal applications. |

#### Branch Office (District 3)
| **Requirement** | **Details** |
|-----------------|-------------|
| **Devices Used** | - Developers and Testers: Restricted to company desktop PCs; personal laptops are not permitted to access the company network. |
| **Site-to-Site VPN** | - Implement a site-to-site VPN to deploy applications to the Data Center at the headquarters.<br>- Ensure high security and stable connectivity between the two locations. |
| **Wi-Fi** | - Provide a separate Wi-Fi system at the branch with independent Internet access, isolating work traffic from company PCs and public connections. |
| **Data Center Connectivity** | - Ensure stable connectivity between the branch and the Data Center at the headquarters for application deployment. |
| **Security Systems** | - Implement security solutions to ensure safe connectivity and access between the branch and headquarters, especially for the site-to-site VPN. |

## Network Topology
The network topology diagram outlines the connectivity framework between the headquarters (Thu Duc) and the branch office (District 3), encompassing routers, switches, the Data Center, and VLANs for departments, Wi-Fi, and site-to-site VPN.
## Design Goals
- Create a secure, efficient, and scalable network infrastructure for both locations.
- Protect data integrity during VPN and cloud-based application deployments.
- Isolate network traffic for departments, teams, and guest users.
- Ensure consistent connectivity between the branch office and the headquarters’ Data Center.
