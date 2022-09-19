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

### What's untested?

- [ ] USB-C PowerDelivery - as I don't have PD charger
- [ ] USB-C, VGA and DisplayPort video output - I will test it at some free time
- [ ] Fingerprint Scanner - my laptop revision doesn't include FP scanner
- [ ] M.2 NVMe SSD - should work

### Things to be done
- [ ] Upgrade to latest OpenCore and disable Verbose boot

### Screenshots
![Zrzut ekranu 2022-09-19 o 12 01 01](https://user-images.githubusercontent.com/36552450/191020794-fcabceac-fdbe-4fe8-9694-10ff6d8d65ad.png)
![Zrzut ekranu 2022-09-19 o 12 01 57](https://user-images.githubusercontent.com/36552450/191020816-bf0100ae-9b0f-4258-a19b-c01a3ff4db84.png)
