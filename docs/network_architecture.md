# OpenHaus Network Architecture

## Components
- **ISP Router**: Provides internet connectivity to **pfSense VM**.
- **pfSense VM**: Main router and firewall (WAN to ISP, LAN to **Switch**).
- **TP-Link AP**: Wireless access point for user **Wi-Fi** connections.
- **Ubuntu VM**: Hosts **CoovaChilli** (captive portal) and **FreeRADIUS** (AAA).
- **Switch**: Connects **MacBook**, **TP-Link AP**, and **VMs**.
- **MacBook**: Admin workstation for network management.

## Flow Diagram
[ISP Router] → [pfSense VM: WAN]
[pfSense VM: LAN] → [Switch]
→ [TP-Link AP] → [Users]
→ [Ubuntu VM: CoovaChilli + FreeRADIUS]
→ [MacBook: Admin]

## Diagram
![OpenHaus Network Architecture Diagram](/docs/images/network_architecture.png)

## Session Flow
1. User connects to **Wi-Fi** via **TP-Link AP**.
2. **TP-Link AP** redirects to **CoovaChilli** captive portal.
3. User authenticates via **FreeRADIUS** (OTP/email verification).
4. Captive portal grants access based on account type (**guest**, **registered**, **premium**).
5. Mobile app syncs with portal for seamless login.

## Related Documentation
- [Project Overview](docs/project_overview.md)
- [Setup Notes](docs/setup_notes.md)
- [Progress Logs](docs/progress_logs/day1_planning.md)
- [GitHub Repo](https://lnkd.in/dFRRjj85)


