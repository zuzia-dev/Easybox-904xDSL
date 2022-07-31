## Arcadyan/Astoria Easybox 904 xDSL (VGV952CJW33-E-IR)

#### Hardware Specification 
- CPU: Lantiq PSB 80920 EL V1.2 VRX200 2x500MHz with a mips32 architekture called mips_34Kc
- RAM: EtronTech EM68C16CWQD-25H 128MB DDRII SDRAM 400MHz
- Flash: Samsung K9F4G08U0x 512MiB NAND-flash
- Ethernet: Realtek RTL8367RB 4x 10/100/1000 Mbit/s vlan support
- Wlan: Realtek RT3883F + RT5392L 5GHz/2.4GHz 802.11abgn
- xDSL-Modem: Lantiq PSB 80190 V V1.1 XWAY VRX208 up to VDSL2 profile 30a and Vectoring support
- POTS: Lantiq PEF 42068 V V1.2 XWAY SLIC120 2 x FXS Analog Telefon ports
- ISDN: Lantiq PEF 82902 F V1.1 T TSMINTI 4B3T 1 x S0-Bus
- LCD-Screen: ILITEK ILI9341 TFT LCD 320x240 RGB 262K colors
- Simcardreader: one exist but no function
- Serial: yes with connectors
- USB: 2 x USB-2.0
- Touchpad: yes

## Small [Recovery] with GUI for the Easybox 904 xDSL 

Recovery based on OpenWrt 19.07 r14162-ef765ceb09. Available in two versions: SMP and VPE.

#### [Fullimage.img - SMP](https://github.com/zuzia-dev/Easybox-904xDSL/raw/master/fullimage.img-SMP)
> MD5: 8056a33ec2bb4352e00174ad8a08f18d
> SHA256: e93f2635607ea62292d2f85e8eb55641afcd76621ae932397bf251d9a3ea00b8

#### [Fullimage.img - VPE](https://github.com/zuzia-dev/Easybox-904xDSL/raw/master/fullimage.img-VPE)
> MD5: 604346bc439cee9fb16a57fee00ffb52
> SHA256: a3bc8ec78d468200854d3404c4be16ccab015fa0e25497ef5ff466c0b2c37cbd

Included:
- support USB 2.0
- kernel 4.19.138 
- LuCI with internationalization and localization (en, de, pl)
- LCD and touch keys - LCD4Linux is installed (white and black theme)
- software and configuriation for 3G/LTE modems and USB tethering
- DSL port as a WAN (vlan eth0.2) - working internet connection
- support filesystem: ext4, vfat, msdos, f2fs
- script Sysinfo and CPU temperature applet for LuCI (by Cezary Jackiewicz).
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

Flash a full OpenWrt system:
- Use the browser to connect to http://192.168.1.1.
- Login (no password needs to be set up).
- Use menu item  System -> Backup -> Flash Firmware.

After succesfull flash router will reboot into full OpenWrt image.

## License
OpenWrt is licensed under GPL-2.0
