# Small [Recovery] OpenWrt 19.07 r14162-ef765ceb09 for the Arcadyan/Astoria Easybox 904 xDSL 
Available in two versions: SMP and VPE.

Fullimage.img - SMP:
MD5: 8056a33ec2bb4352e00174ad8a08f18d
SHA256: e93f2635607ea62292d2f85e8eb55641afcd76621ae932397bf251d9a3ea00b8

Fullimage.img - VPE:
MD5: 604346bc439cee9fb16a57fee00ffb52
SHA256: a3bc8ec78d468200854d3404c4be16ccab015fa0e25497ef5ff466c0b2c37cbd

Included:
- support USB 2.0
- kernel 4.19.138 
- LuCI with internationalization and localization (en, de, pl)
- LCD and touch keys - LCD4Linux is installed (white and black theme)
- software and configuriation for 3G/LTE modems and USB tethering
- DSL port as a WAN (vlan eth0.2) - working internet connection
- Dnsmasq as DHCP server
- support filesystem: ext4, vfat, msdos, f2fs
- script Sysinfo and CPU temperature applet for LuCI (by Cezary Jackiewicz).

Not included:
- DSL software
- WiFi software
- debug options
- IPv6.

How to use the OpenWrt [Recovery] system.

1) Connect your router (yellow port) with your PC with a LAN cable. 
2) Copy fullimage.img-SMP or fullimage.img-VPE as fullimage.img to the tftp server (e.g. TFTPD32) which listens on ip address 192.168.2.100.
3) Turn off the router. Turn it on while pressing the reset button (next to the
  power jack). Keep it pressed for about 5 seconds, then release it - LCD will show information about recovery mode selected. After successfull flash, LCD will show message to shutdown and restart router.
4) Turn off the router, then turn it on again.
5) You need to wait about two minutes. Then you can connect
  to the router either with a browser - http://192.168.1.1 (or with ssh root@192.168.1.1).

Flash a full OpenWrt system:
1) Use the browser to connect to http://192.168.1.1.
2) Login (no password needs to be set up).
3) Use menu item  System -> Backup -> Flash Firmware.

After succesfull flash router will reboot into full OpenWrt image.
