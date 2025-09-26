# OpenHaus Project Overview

## What is OpenHaus?
OpenHaus is a platform designed to deliver secure internet access and an integrated vendor marketplace to campuses. It serves as a gateway to community connectivity, enabling students, staff, and vendors to:
- Connect via a branded captive portal.
- Manage accounts, subscriptions, and usage.
- Explore a campus vendor marketplace.

## Project Goals
- Build a robust network infrastructure to support user access and services.
- Deploy a custom captive portal for user authentication.
- Integrate a marketplace for campus vendors.
- Develop a companion mobile app and website.

## Core Components
- **Custom Captive Portal**: Branded web interface for user access.
- **Website**: Information hub with pricing, FAQs, and vendor onboarding.
- **Mobile App**: User-friendly companion for connectivity and marketplace access.

## Tech Stack
- **Networking**: pfSense, OpenWrt (TP-Link AP), CoovaChilli, FreeRADIUS.
- **Web**: React / Django (TBD for Website and Captive Portal).
- **Mobile**: React Native / Flutter (TBD for Mobile App).
- **Infrastructure**: Ubuntu VM, TP-Link AP, MacBook (USB-C Ethernet), Switch.

## Current Status
The project has completed the Day 2 setup, establishing a functional network infrastructure to support the core components:
- Configured pfSense VM as the router/firewall with LAN IP 192.168.1.1/24, DHCP range 192.168.1.100-200, and WAN via Bridged Wi-Fi.
- Set up OpenWrt AP with static IP 192.168.1.5/24, SSID "OpenHaus Free Wi-Fi (Demo)", and WPA2-PSK/WPA3-SAE security.
- Configured Ubuntu VM with static IP 192.168.1.2/24.
- Established Openhaus USB-C Ethernet (MacBook) with static IP 192.168.1.3/24 for management.
- Verified connectivity with successful ping tests from Ubuntu VM to 192.168.1.1 (pfSense) and 192.168.1.5 (OpenWrt AP), and SSH login from MacBook to Ubuntu VM (`ssh openhaus@192.168.1.2`).
- Updated documentation with configuration screenshots in `/docs/images/config/`.

## Next Steps
- **Day 3**: Develop and deploy the Custom Captive Portal on the Ubuntu VM.
- Design the Website with pricing, FAQs, and vendor onboarding features.
- Build the Mobile App for connectivity and marketplace access.
- Test user authentication workflows and scalability.

## Roadmap
- [x] Build base network (pfSense + CoovaChilli + FreeRADIUS)
- [ ] Deploy custom captive portal design
- [ ] Launch website (campus + vendor portal)
- [ ] Develop user mobile app
- [ ] Integrate marketplace features

## Repository Structure
- `/docs/`: Project documentation and images
- `/configs/`: Configuration files
- `/captive_portal/`: Captive portal code
- `/website/`: Website source
- `/mobile_app/`: Mobile app source
- `/scripts/`: Deployment scripts

