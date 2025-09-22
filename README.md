# OpenHaus Project

**OpenHaus** is a network innovation project that provides **secure internet access** and an **integrated vendor marketplace** to campuses.  
It combines enterprise-grade networking tools with a digital ecosystem to make connectivity simple, affordable, and community-driven.  

---

## 🌐 What is OpenHaus?
OpenHaus is a **gateway platform** where students, staff, vendors and guests can:  
- Connect to reliable internet through a branded captive portal.  
- Manage accounts, subscriptions, and usage.  
- Explore a marketplace of campus vendors and services.  

---

## 🚀 Core Components
- **pfSense** → Firewall & routing.  
- **CoovaChilli** → Captive portal for user login + session control.  
- **FreeRADIUS** → Authentication, authorization, accounting (AAA).  
- **Custom Captive Portal** → Branded OpenHaus web interface.  
- **Website** → Information hub **and marketplace access** for vendors and users. 
- **Mobile App** → User-friendly companion for connectivity and marketplace access.  

---

## ✨ Features
- Seamless internet connectivity for all campus users.  
- Branded captive portal for easy login and management.  
- Integrated vendor marketplace accessible via website and mobile app.  
- Multi-platform support (web and mobile).

--- 

## 📂 Repository Structure
```
openHaus-project/
├── docs/ # Documentation & daily progress logs
├── configs/ # pfSense, CoovaChilli, FreeRADIUS configs
├── captive_portal/ # Custom captive portal (HTML, CSS, JS)
├── website/ # OpenHaus website source
├── mobile_app/ # Mobile app source
└── scripts/ # Setup & deployment scripts
```
---

## 🛠️ Tech Stack / Infrastructure
**Hardware:**  
- TP-Link Access Points (managed via pfSense)  
- 8-Port Network Switch (connects APs, servers, and other network devices)  
- Host machine / server for VMs  

**Virtualization / Platforms:**  
- Ubuntu VM (hosts networking services, website, and mobile app backend)  

**Networking Services / Software:**  
- **pfSense** → Firewall & routing  
- **CoovaChilli** → Captive portal for user login + session control  
- **FreeRADIUS** → Authentication, authorization, accounting (AAA)  

**Web / App Development:**  
- **Website:** React / Django (to be finalized)  
- **Mobile App:** React Native / Flutter (to be finalized) 

---

## 📖 Documentation
Docs live in [`/docs`](docs):  
- Project Overview  
- Setup Notes  
- Network Architecture  
- Progress Logs  

---

## 🧭 Roadmap
- [ ] Configure base network (pfSense + CoovaChilli + FreeRADIUS)  
- [ ] Deploy custom captive portal  
- [ ] Launch website (campus + vendor portal)  
- [ ] Develop mobile app  
- [ ] Integrate marketplace features  

---

## 📜 License
MIT License
