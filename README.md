# Fujitsu Lifebook U748 Hackintosh

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
![Zrzut ekranu 2022-09-19 o 12 01 01](https://user-images.githubusercontent.com/36552450/191020794-fcabceac-fdbe-4fe8-9694-10ff6d8d65ad.png)
![Zrzut ekranu 2022-09-19 o 12 01 57](https://user-images.githubusercontent.com/36552450/191020816-bf0100ae-9b0f-4258-a19b-c01a3ff4db84.png)
![Zrzut ekranu 2022-10-10 o 12 12 18](https://user-images.githubusercontent.com/36552450/194848000-c5770298-5ac5-4339-b175-e9f0309b6bbe.png)

### Notes
If you want to install it alongside Windows and OpenCore doesn't display any options but boots Windows by default:
- Boot OpenCore
- wait for OC logs to disappear
- on blank screen quickly press **Left** Arrow **once**, then press **Enter**
- wait until laptop reboots
- now OC should be displayed normally
Windows is first boot option, pressing left arrow will jump to last option, which is "Clear NVRAM". Cleaning NVRAM fixes this issue.
