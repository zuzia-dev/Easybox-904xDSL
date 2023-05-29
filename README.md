## Arcadyan/Astoria Easybox 904 xDSL (VGV952CJW33-E-IR)
[![Openwrt](https://img.shields.io/badge/os-OpenWrt-<COLOR>.svg)](https://github.com/zuzia-dev/openwrt/) [![GitHub release (latest by date)](https://img.shields.io/github/v/release/zuzia-dev/Easybox-904xDSL?color=orange)](https://github.com/zuzia-dev/Easybox-904xDSL/releases/latest) [![GitHub Downloads](https://img.shields.io/github/downloads/zuzia-dev/Easybox-904xDSL/latest/total)](https://github.com/zuzia-dev/Easybox-904xDSL/releases/latest) [![GitHub issues](https://img.shields.io/github/issues/zuzia-dev/Easybox-904xDSL?color=green)](https://GitHub.com/zuzia-dev/Easybox-904xDSL/issues) [![GitHub latest commit](https://badgen.net/github/last-commit/zuzia-dev/Easybox-904xDSL?color=00BFFF)](https://github.com/zuzia-dev/Easybox-904xDSL/commit) [![GitHub forks](https://img.shields.io/github/forks/zuzia-dev/Easybox-904xDSL?color=93917C)](https://GitHub.com/zuzia-dev/Easybox-904xDSL/forks) [![License: GPL v2](https://img.shields.io/badge/License-GPL_v2-blue.svg)](https://github.com/zuzia-dev/Easybox-904xDSL#license) 
#### Hardware Specification 
- CPU: Lantiq PSB 80920 EL V1.2 VRX200 2x500 MHz with a mips32 architecture called mips_34Kc
- RAM: EtronTech EM68C16CWQD-25H 128 MB DDR II SDRAM 400 MHz
- Flash: Samsung K9F4G08U0x 512 MiB NAND-flash
- Ethernet: Realtek RTL8367RB 4x 10/100/1000 Mbit/s vlan support
- Wlan: Realtek RT3883F + RT5392L 5 GHz / 2.4G Hz 802.11abgn
- xDSL-Modem: Lantiq PSB 80190 V V1.1 XWAY VRX208 up to VDSL2 profile 30a and Vectoring support
- POTS: Lantiq PEF 42068 V V1.2 XWAY SLIC120 2 x FXS Analog Telephone ports
- ISDN: Lantiq PEF 82902 F V1.1 T TSMINTI 4B3T 1 x S0-Bus
- LCD-Screen: ILITEK ILI9341 TFT LCD 320x240 RGB 262K colors
- Simcardreader: one exist but no function
- Serial: yes with connectors
- USB: 2x USB-2.0
- Touchpad: yes
> Based on informations shared by sites: 
- https://openwrt.org/toh/astoria/arcadyan_astoria_easybox_904xdsl_r01
- https://forum.archive.openwrt.org/viewtopic.php?id=44676&p=1
- https://forum.openwrt.org/t/support-for-easybox-904-lte
- https://eko.one.pl/forum/viewtopic.php?id=16158
- http://arny.tjps.eu/OpenWrt/EasyBox904xDSL
- https://github.com/Quallenauge/Easybox-904-XDSL
- https://github.com/Plonkbong/Easybox-904-XDSL

## Small [Recovery] with GUI for the Easybox 904 xDSL 
In case of problems (e.g. bootloop) or if you want to update an older image (<2018-03-11), you need to perform the update in the Recovery. 
Recovery based on OpenWrt. 
#### Available in two versions ->  [Fullimage.img - ver. SMP and Fullimage.img - ver. VPE](https://github.com/zuzia-dev/Easybox-904xDSL/releases/tag/v2.Recovery)

Included:
- support USB 2.0
- kernel kernel 5.4.238 
- LuCI with internationalization and localization (en, de, pl)
- LCD and touch keys - LCD4Linux is installed (default white theme)
- software and configuriation for 3G/LTE modems and USB tethering
- DSL port as a WAN (vlan eth0.2) - working internet connection
- tools for installation hacked bootloader - Internet connection required for script: ```/etc/hacked-bootloader```
- online package repository but run first: ```/etc/opkg-fix```
- CPU utilization info & Internet detector for the LuCI (by gSpotx2f)
- script Sysinfo and CPU temperature applet for LuCI (by Cezary Jackiewicz)
- support filesystem: ext4, vfat, msdos
- active software flow offloading via iptables
- Dnsmasq as DHCP server

Not included:
- DSL software
- WiFi software
- debug options
- IPv6

#### How to use the OpenWrt [Recovery] system
- Connect your router (yellow port) with your PC with a LAN cable. 
- Copy fullimage.img-SMP or fullimage.img-VPE as fullimage.img to the tftp server (e.g. TFTPD64) which listens on IP address 192.168.2.100.
- Turn off the router. Turn it on while pressing the reset button (next to the
  power jack). Keep it pressed for about 5 seconds, then release it - LCD will show information about recovery mode selected. After successfull flash, LCD will show message to shutdown and restart router.
- Turn off the router, then turn it on again.
- You need to wait about two minutes. Then you can connect
  to the router either with a browser - http://192.168.1.1 (or with ssh root@192.168.1.1).
  
For more information please see: [Link](https://chomikuj.pl/ZuzannaCK/ROUTERY/EASYBOX+904+xDSL/OpenWrt+Recovery+(bootloop+lub+pierwsze+wgranie)) (pl)

#### Flash a full OpenWrt 21.02 system:
> It's recommended to update the bootloader before uploading OpenWrt. Instructions for updating: [Link](https://openwrt.org/toh/astoria/arcadyan_astoria_easybox_904xdsl_r01#installing_hacked_bootloader)
- Download the latest version [SMP full image](https://github.com/zuzia-dev/Easybox-904xDSL-repo-source/tree/main/Firmware/SMP) or [VPE full image](https://github.com/zuzia-dev/Easybox-904xDSL-repo-source/tree/main/Firmware/VPE) (file *squashfs-sysupgrade.bin)
- Use the browser to connect to http://192.168.1.1
- Login (no password needs to be set up).
- Use menu item  System -> Backup -> Flash Firmware.
> Important! The "Keep settings and retain the current configuration" option must be unchecked.

After succesfull flash router will reboot into full OpenWrt image.

### License
OpenWrt is licensed under GPL-2.0
