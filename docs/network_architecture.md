# OpenHaus Network Architecture

## Overview
The OpenHaus network is designed to provide secure, managed internet access through a captive portal and integrated vendor marketplace. It leverages virtual machines, a wireless access point, and a switch, with statically managed IP assignments within the 192.168.1.0/24 subnet.

## Components
- **ISP Router**: Provides internet connectivity to the pfSense VM via WAN.
- **pfSense VM**: Acts as the primary router, firewall, and DHCP server.
- **OpenWrt AP**: Serves as a wireless access point for user Wi-Fi connections.
- **Ubuntu VM**: Hosts CoovaChilli (captive portal) and FreeRADIUS (AAA) services.
- **Switch**: Connects the MacBook, TP-Link AP, and VMs.
- **MacBook (USB-C Ethernet)**: Used for network management and testing.

## IP Assignments
- **pfSense VM (Router/Firewall)**:
  - LAN: 192.168.1.1/24
  - DHCP Range: 192.168.1.100 - 200
  - WAN: Dynamic IP (Bridged via Wi-Fi)
- **OpenWrt AP**:
  - Static IP: 192.168.1.5/24
  - SSID: OpenHaus Free Wi-Fi (Demo)
  - Security: WPA2-PSK/WPA3-SAE
- **Ubuntu VM**:
  - Static IP: 192.168.1.2/24
  - Gateway: 192.168.1.1 (pfSense)
  - DNS: 192.168.1.1, 8.8.8.8
- **Openhaus USB-C Ethernet (MacBook)**:
  - Static IP: 192.168.1.3/24
  - Gateway: 192.168.1.1 (pfSense)
  - DNS: 192.168.1.1

## Network Diagram
![Network Architecture](/docs/images/network_architecture.png)  

## Flow Diagram
ISP Router → pfSense VM → Switch → [OpenWrt AP, Ubuntu VM, MacBook]

## Session Flow
1. Wi-Fi Connection: User connects to OpenWrt AP (SSID: OpenHaus Free Wi-Fi).
2. Captive Portal: Redirected to CoovaChilli on Ubuntu VM.
3. Authentication: User authenticates via FreeRADIUS (OTP/email).
4. Access Granted: captive portal grants access based on account type.(**Guest**, **Registered**, **Premium**).
5. Mobile App Sync: App syncs with portal for seamless login.

## Connectivity
- **Ping Tests**: Successful from Ubuntu VM to 192.168.1.1 (pfSense) and 192.168.1.5 (OpenWrt AP).
- **SSH**: Successful login from MacBook to Ubuntu VM (`ssh openhaus@192.168.1.2`).

## Notes
- VMware Bridged network must align with USB-C Ethernet.
- Potential IP conflicts to verify (e.g., 192.168.1.2, 1.3, 1.5).

## Related Documentation
- [Project Overview](docs/project_overview.md)
- [Setup Notes](docs/setup_notes.md)
- [Progress Logs](docs/progress_logs)
- [GitHub Repo](https://github.com/savedyute/openhaus-project)