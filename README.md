# Fujitsu Lifebook U748 Hackintosh

![pol_pl_Fujitsu-LifeBook-U748-Core-i7-8550U-8-gen-1-8-GHz-8-GB-240-SSD-14-FullHD-Win-11-Prof-Update-22762_3](https://github.com/KrzysiuWojcik/Fujitsu-Lifebook-U748-Hackintosh/assets/36552450/26fe46df-1f7c-4293-b7e9-2ad960ddf2fa)


## Sonoma Beta 14.0

Boots on Ventura package, exceptions are:
- Wi-Fi: AirportItlwm needs to be replaced with Itlwm (no AirportItlwm for Sonoma yet) - need to use HeliPort to connect with Wi-Fi.
- iGPU: AAPL,ig-platform-id needs to be replaced from AAAWWQ== to BQAcWQ== in config.plist (line 389)

Everything seems to work as it worked in earlier macOS versions, tests + screenshots are coming soon.

## Ventura 13.0.1

### <code>main</code> branch is still following Monterey-related changes. Ventura support is work-in-progress. You can download pre-release from Releases tab.

### What's working and what's not?

- [x] Boots, sleeps and wakes
- [x] iGPU - Intel UHD 620 with full QE/CI
- [x] Wi-Fi - using latest AirportItlwm Pre-Release (itlwm works but makes boot process much longer)
- [x] Bluetooth (?)
- [x] SierraWireless EM7305 4G LTE modem - works, but you need to manually add file "/System/Library/CoreServices/Menu Extras/WWAN.menu" to auto-start
- [x] SmartCard reader (assuming, can't test)
- [x] O2Micro SDXC card reader (1217: 8621 faked to 14e4: 16bc + CtlnaSDXC.kext)
- [x] ELAN I<sup>2</sup>C Touchpad (buttons working as Force Touch, disable it in preferences to make left click working)
- [x] Function keys (F2, F3 & F4 for volume, F7 & F8 for brightness)
- [x] Battery time is decent
- [x] Power management
- [x] M.2 SATA SSD
- [x] M.2 NVMe SSD - if laptop freezes at boot process with no reason, it's NVMe bug. Install on some SATA M.2 drive, let everything configure, reboot several times and move your APFS container to NVMe disk. If you have no SATA M.2 drive, you can use 2,5" SATA drive connected trough USB.
- [x] Audio is working with latest AppleALC installed
- [x] Continuity Camera works over USB (that's known to happen also on real Mac's)
- [x] HandOff is not working
- [x] Video output working on DisplayPort, other ports not tested

### Screenshots

![Zrzut ekranu 2022-11-30 o 12 58 58](https://user-images.githubusercontent.com/36552450/204908256-7abdb75f-e943-4f4d-9ebe-51b8de7f151b.png)
![Zrzut ekranu 2022-12-5 o 20 56 02](https://user-images.githubusercontent.com/36552450/205731586-852f0c2d-e715-465d-8a27-a7b5935bed9c.png)



## Monterey 12.6.1

### What's working and what's not?

- [x] Boots, sleeps and wakes
- [x] iGPU - Intel UHD 620 with full QE/CI
- [x] Wi-Fi - using AirportItlwm
- [x] Bluetooth
- [x] SierraWireless EM7305 4G LTE modem (WWAN modem is detected and can connect to internet, using QMI.kext)
- [x] SmartCard reader
- [x] O2Micro SDXC card reader (1217: 8621 faked to 14e4: 16bc + CtlnaSDXC.kext)
- [x] ELAN I<sup>2</sup>C Touchpad (buttons working as Force Touch)
- [x] Function keys (F2, F3 & F4 for volume, F7 & F8 for brightness)
- [x] Battery time is decent
- [x] Power management - laptop stays cool and silent
- [x] M.2 SATA SSD
- [x] M.2 NVMe SSD
- [x] Audio using AppleALC
- [x] HandOff is working
- [ ] Video output not working on any port

### Screenshots
![Zrzut ekranu 2022-11-30 o 21 08 29](https://user-images.githubusercontent.com/36552450/204898628-bdf417e0-ea71-426e-924f-e0908857b1d5.png)
<br><i>macOS Monterey
- custom WWAN icons (iOS style) placed into /S*/L*/CoreServices/Menu\ Extras/WWAN.menu
- HandOff from iPhone is working
</i><br>

## Big Sur 11.7

### Last changes

- 11.24.2022 - Display HiDPI scaling (internal LG panel) fixed to work together with brightness control
- 11.23.2022 - EM7305 4G LTE WWAN modem brought to live - signal icon shows on top bar and can finally connect to the Internet
- 11.07.2022 - Upgraded OpenCore (now it has text interface and no NTFS driver because I use rEFInd as my main OS chooser)
- 10.19.2022 - SMBIOS, Graphics and Display related changes - fixed graphical issues when playing videos in full screen (2048 MB VRAM, Intel UHD 617 ID, MacBookAir8,1 SMBIOS)

### What's working and what's not?

- [x] Boots, sleeps and wakes
- [x] iGPU - Intel UHD 620 with full QE/CI
- [x] Wi-Fi - using AirportItlwm
- [x] Bluetooth
- [x] SierraWireless EM7305 4G LTE modem (WWAN modem is detected and can connect to internet, using QMI.kext)
- [x] SmartCard reader
- [x] O2Micro SDXC card reader (1217: 8621 faked to 14e4: 16bc + CtlnaSDXC.kext)
- [x] ELAN I<sup>2</sup>C Touchpad (buttons working as Force Touch)
- [x] Function keys (F2, F3 & F4 for volume, F7 & F8 for brightness)
- [x] Battery time is decent
- [x] Power management - laptop stays cool and silent
- [x] M.2 SATA SSD
- [x] M.2 NVMe SSD
- [x] Audio using AppleALC
- [ ] Video output not working on any port
- [ ] HandOff is not working

### What's untested?

- [ ] USB-C PowerDelivery - as I don't have PD charger
- [ ] ~USB-C, VGA and DisplayPort video output - I will test it at some free time~
- [ ] Fingerprint Scanner - my laptop revision doesn't include FP scanner

### Things to be done
- [x] ~Upgrade to latest OpenCore~

### Screenshots
![Zrzut ekranu 2022-09-19 o 12 01 57](https://user-images.githubusercontent.com/36552450/191020816-bf0100ae-9b0f-4258-a19b-c01a3ff4db84.png)<br><i>"i" services working and USB ports mapped</i><br><br>
![Zrzut ekranu 2022-10-19 o 18 21 15](https://user-images.githubusercontent.com/36552450/196748776-0dad07c5-89cb-4b21-b796-dd3b6b2067c2.png)<br><i>Intel UHD 617</i><br><br>
<img width="1440" alt="Zrzut ekranu 2022-11-24 o 02 19 38" src="https://user-images.githubusercontent.com/36552450/203677135-bc49e665-9da0-45f6-b9b1-7897b1b4ff50.png"><br><i>EM7305 working in QMI mode</i><br><br>
<img width="1366" alt="Zrzut ekranu 2022-11-24 o 13 26 05" src="https://user-images.githubusercontent.com/36552450/203786636-e988638d-ecc8-4b51-b555-17c4efb4c973.png"><br><i>Display supports scaling and brightness control</i><br>

### Notes
To make your EM7305 LTE modem working, you need to use Linux, in this example Ubuntu.
- Install qmicli: <code>sudo apt install -y qmicli</code>
- Make sure your device is recognized: <code>ls /dev/cdc-wdm0</code> (it can be also cdc-wdm1 etc.)
- Get your USB compositions: <code>sudo qmicli --device=/dev/cdc-wdm0 --dms-swi-get-usb-composition</code>
- Set your USB composition that provides both QMI and MBIM (or only QMI if you don't dual boot) and is marked as SUPPORTED (in my case it will be comp 14): <code>sudo qmicli --device=/dev/cdc-wdm0 --dms-swi-set-usb-composition 14</code>
- reset your card and reboot to macOS: <code>sudo qmicli --device /dev/cdc-wdm0 --dms-set-operating-mode=offline && sudo qmicli --device /dev/cdc-wdm0 --dms-set-operating-mode=reset && init 6</code>

