# OpenHaus Setup Notes

## Hardware and VM Setup
This section details the configuration of the OpenHaus network components, covering the OpenWrt AP, USB-C Ethernet, pfSense VM, and Ubuntu VM setups.

---

### OpenWrt AP Configuration
**Summary**: Configuration of the OpenWrt AP to serve as a wireless access point with captive portal support.
- **LAN**:
  - Static IP: 192.168.1.5
  - Subnet Mask: 255.255.255.0
  - DHCP: Disabled
  - Gateway: None
- **Wireless**:
  - SSID: OpenHaus Free Wi-Fi (Demo)
  - Key: ********
  - Security: WPA2-PSK/WPA3-SAE, 802.11w Optional
- **Notes**: Relies on pfSense for DHCP and routing; OpenWrt firmware on TP-Link AP for enhanced captive portal support.
- **Screenshots**:
  - ![OpenWrt Config 01](/docs/images/config/OpenWrt/openwrt_config_01.png) (Dashboard)
  - ![OpenWrt Config 02](/docs/images/config/OpenWrt/openwrt_config_02.png) (Dashboard Cont.)
  - ![OpenWrt Config 03](/docs/images/config/OpenWrt/openwrt_config_03.png) (Wireless Settings)
  - ![OpenWrt Config 04](/docs/images/config/OpenWrt/openwrt_config_04.png) (LAN Settings)

---

### Openhaus USB-C Ethernet Configuration
**Summary**: Setup of the USB-C Ethernet adapter on the MacBook for network management.
- **Static IP**: 192.168.1.3
- **Subnet Mask**: 255.255.255.0
- **Gateway**: 192.168.1.1 (pfSense)
- **DNS**: 192.168.1.1
- **Device**: MacBook via USB-C Ethernet adapter
- **Notes**: Configured via MacBook Network settings.
- **Screenshots**:
  - ![USB-C Ethernet Config]('/docs/images/config/OpenHaus USB-C to Ethernet/usbc_ethernet_config.png') (Network Settings Panel)

---

### pfSense VM Configuration
**Summary**: Configuration of the pfSense VM as the primary router and firewall.
- **LAN**:
  - Static IP: 192.168.1.1/24
  - DHCP: Enabled
  - DHCP Range: 192.168.1.100 - 200
  - DNS Servers: 127.0.0.1 (local), 8.8.8.8 (Google), 1.1.1.1 (Cloudflare)
  - Upstream Gateway: None
- **WAN**:
  - Dynamic IP: From Wi-Fi (ISP) via Bridged (Wi-Fi)
- **System Settings**:
  - Hostname: openhaus-pfsense
  - Domain: home.openhaus
  - DNS Resolver: Enabled
  - DNS Override by DHCP/PPP: Disabled
- **Notes**: WebConfigurator accessed via https://192.168.1.1
- **Screenshots**:
  - ![pfSense VM Config 01](/docs/images/config/pfSense/VM/pfsense_vm_config_01.png) (VM Settings)
  - ![pfSense VM Config 02](/docs/images/config/pfSense/VM/pfsense_vm_config_02.png) (DHCP & LAN Configuration)
  - ![pfSense VM Config 03](/docs/images/config/pfSense/VM/pfsense_vm_config_03.png) (DHCP & LAN Configuration Cont.)
  - ![pfSense WebConfigurator Config 01](/docs/images/config/pfSense/WebConfigurator/pfsense_webconfigurator_config_01.png) (Dashboard)
  - ![pfSense WebConfigurator Config 02](/docs/images/config/pfSense/WebConfigurator/pfsense_webconfigurator_config_02.png) (General Setup)
  - ![pfSense WebConfigurator Config 03](/docs/images/config/pfSense/WebConfigurator/pfsense_webconfigurator_config_03.png) (LAN Interface)
  - ![pfSense WebConfigurator Config 04](/docs/images/config/pfSense/WebConfigurator/pfsense_webconfigurator_config_04.png) (WAN Interface)

---

### Ubuntu VM Setup
**Summary**: Setup of the Ubuntu VM for hosting CoovaChilli and FreeRADIUS, including network configuration and testing.
- **Static IP**: 192.168.1.2
- **Subnet Mask**: 255.255.255.0
- **Gateway**: 192.168.1.1 (pfSense)
- **DNS**: 192.168.1.1, 8.8.8.8
- **Network Interface**: ens33
- **Netplan Config**: `/etc/netplan/00-installer-config.yaml`
  ```yaml
  network:
    ethernets:
      ens33:
        dhcp4: no
        addresses: [192.168.1.2/24]
        nameservers:
          addresses: [192.168.1.1, 8.8.8.8]
        routes:
          - to: default
            via: 192.168.1.1
    version: 2
- **Screenshots**:
  - ![Ubuntu Network Config 01](/docs/images/config/Ubuntu/ubuntu_network_config_01.png) (Netplan File Edit)
  - ![Ubuntu Network Config 02](/docs/images/config/Ubuntu/ubuntu_network_config_02.png) (Network Status Check)
  - ![Ubuntu Network Config 03](/docs/images/config/Ubuntu/ubuntu_network_config_03.png) (IP Address Confirmation)
  - ![Ubuntu Ping Success](/docs/images/config/Ubuntu/ubuntu_ping_success.png) (Ping Test to 8.8.8.8)
  - ![Ubuntu SSH Login Success](/docs/images/config/Ubuntu/ubuntu_ssh_login_success.png) (SSH Session from Mac Terminal)
