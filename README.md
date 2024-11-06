# NIST Based Security Policy Implementation for Small Office Environment

This project simulates a small office network using virtualization on a single laptop. The goal is to create a network environment with servers, client workstations, and a firewall to practice IT infrastructure and cybersecurity configurations.

## Project Overview

This network setup includes:
- **Windows Server** for Active Directory, user roles, and file sharing
- **Linux Server** for web and database services
- **Client Machines** to simulate employee workstations
- **Router/Firewall (pfSense)** to control and secure network traffic

This environment allows for testing various security policies, network configurations, and monitoring techniques in a controlled, virtualized setting.

---

## Setup Requirements

### Software
- **VirtualBox** (preferred) or **VMware Workstation Player**
- **Operating Systems**:
  - **Windows Server** (trial or evaluation version)
  - **Linux Server** (e.g., Ubuntu Server or CentOS)
  - **pfSense** (open-source firewall software)
  - **Windows/Linux client OS** for client machines

### Hardware
- A laptop with:
  - **8GB RAM (minimum)**; 16GB or more is recommended for smoother performance
  - **20GB+ free disk space** for VM storage

---

## Project Setup

### Step 1: Install Virtualization Software

1. Download and install [VirtualBox](https://www.virtualbox.org/) or [VMware Workstation Player](https://www.vmware.com/products/workstation-player.html).
2. Configure VirtualBox or VMware to allocate sufficient resources to each VM.

### Step 2: Set Up Virtual Machines

1. **Windows Server VM**:
   - Download and install a Windows Server evaluation version.
   - Configure it as an Active Directory Domain Controller.
   - Set up DNS and other server roles as needed.

2. **Linux Server VM**:
   - Download and install a Linux distribution (e.g., Ubuntu Server).
   - Install web server or database services for testing (e.g., Apache, MySQL).
   - Configure SSH and other secure settings.

3. **Client VMs**:
   - Install one or more client operating systems (Windows/Linux).
   - Configure them to join the domain managed by the Windows Server.

4. **pfSense Firewall VM**:
   - Download and install [pfSense](https://www.pfsense.org/download/).
   - Configure it as a network firewall and router to manage traffic between VMs.

### Step 3: Network Configuration

1. **Virtual Network Interfaces**:
   - Create network interfaces in VirtualBox/VMware to simulate internal and external networks.
   - Set up **Internal Network** for servers and **NAT/Bridged Network** for clients.

2. **IP Addressing**:
   - Assign static IPs for Windows Server, Linux Server, and pfSense.
   - Set clients to obtain IPs via DHCP from pfSense.

3. **Network Segmentation**:
   - Create separate subnets for servers and client machines.
   - Configure pfSense firewall rules to control access between subnets.

### Step 4: Configure Network Services

1. **Windows Server Configuration**:
   - Set up **Active Directory Domain Services (AD DS)** and create a domain.
   - Add users, groups, and configure role-based access control.
   - Set up **Group Policy** for security settings (e.g., password policies).

2. **VPN Configuration**:
   - Configure **OpenVPN** on pfSense to enable secure remote access.
   - Set up VPN users and enforce strong authentication.

3. **Linux Server Configuration**:
   - Install web and database services (Apache, MySQL) for testing.
   - Implement basic hardening (SSH configuration, firewall settings).

### Step 5: Security Policies and Access Control

1. **Role-Based Access Control (RBAC)**:
   - Define roles on the Windows Server and enforce access based on user roles.

2. **Firewall Rules**:
   - Use pfSense to restrict access to specific services and segments.
   - Block unnecessary ports and secure traffic between clients and servers.

3. **System Hardening**:
   - Disable unnecessary services, enforce strong password policies, and implement multi-factor authentication where possible.

### Step 6: Logging and Monitoring

1. **Enable Centralized Logging**:
   - Configure Syslog or ELK Stack on Linux Server to collect logs.
   - Set up logging for Windows Server and pfSense.

2. **SIEM Setup (Optional)**:
   - If resources permit, install **Splunk** or **Graylog** to centralize and analyze security logs.

---

## Testing and Validation

After setting up the network, test the following:

- **Domain Login**: Ensure client VMs can join the domain and access resources.
- **VPN Access**: Confirm VPN connectivity for remote users.
- **Firewall**: Attempt external access and confirm that pfSense blocks unauthorized traffic.
- **File Sharing**: Set up shared folders and confirm access based on permissions.

---

## Resources

- [VirtualBox Documentation](https://www.virtualbox.org/wiki/Documentation)
- [Windows Server Evaluation](https://www.microsoft.com/en-us/evalcenter/)
- [Ubuntu Server](https://ubuntu.com/download/server)
- [pfSense Documentation](https://docs.netgate.com/pfsense/en/latest/)
- [OpenVPN Setup Guide](https://openvpn.net/community-resources/installation/)

---

## License

This project is for educational and personal development purposes. Please ensure compliance with software licenses and ethical usage practices.
