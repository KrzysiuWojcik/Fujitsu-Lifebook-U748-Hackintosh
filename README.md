# Fujitsu Lifebook U748 Hackintosh

## Big Sur 11.7

### Last changes

- 10.19.2022 - SMBIOS, Graphics and Display related changes - fixed graphical issues when playing videos in full screen (2048 MB VRAM, Intel UHD 617 ID, MacBookAir8,1 SMBIOS)

### What's working and what's not?

- [x] Boots, sleeps and wakes
- [x] iGPU - Intel UHD 620 with full QE/CI
- [x] Wi-Fi - using Itlwm (HeliPort required)
- [x] Bluetooth
- [x] 4G LTE modem
- [x] SmartCard reader
- [x] O2Micro SDXC card reader (1217: 8621 faked to 14e4: 16bc + CtlnaSDXC.kext)
- [x] ELAN I<sup>2</sup>C Touchpad (buttons working as Force Touch)
- [x] Function keys (F2, F3 & F4 for volume, F7 & F8 for brightness)
- [x] Battery time is decent
- [x] Power management - laptop stays cool and silent
- [x] M.2 SATA SSD
- [x] M.2 NVMe SSD

### What's untested?

- [ ] USB-C PowerDelivery - as I don't have PD charger
- [ ] USB-C, VGA and DisplayPort video output - I will test it at some free time
- [ ] Fingerprint Scanner - my laptop revision doesn't include FP scanner

### Things to be done
- [ ] Upgrade to latest OpenCore

### Screenshots
![Zrzut ekranu 2022-09-19 o 12 01 57](https://user-images.githubusercontent.com/36552450/191020816-bf0100ae-9b0f-4258-a19b-c01a3ff4db84.png)
![Zrzut ekranu 2022-10-19 o 18 21 15](https://user-images.githubusercontent.com/36552450/196748776-0dad07c5-89cb-4b21-b796-dd3b6b2067c2.png)


### Notes
If you want to install it alongside Windows and OpenCore doesn't display any options but boots Windows by default:
- Boot OpenCore
- wait for OC logs to disappear
- on blank screen quickly press **Left** Arrow **once**, then press **Enter**
- wait until laptop reboots
- now OC should be displayed normally

Windows is first boot option, pressing left arrow will jump to last option, which is "Clear NVRAM". Cleaning NVRAM fixes this issue.
