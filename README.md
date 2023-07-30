# Fujitsu Lifebook U748 Hackintosh

![pol_pl_Fujitsu-LifeBook-U748-Core-i7-8550U-8-gen-1-8-GHz-8-GB-240-SSD-14-FullHD-Win-11-Prof-Update-22762_3](https://github.com/KrzysiuWojcik/Fujitsu-Lifebook-U748-Hackintosh/assets/36552450/26fe46df-1f7c-4293-b7e9-2ad960ddf2fa)


## Sonoma Beta 14.0
```diff
! Work in progress
```

Boots on Ventura package, exceptions are:
- Wi-Fi: AirportItlwm needs to be replaced with Itlwm (no AirportItlwm for Sonoma yet) - need to use HeliPort to connect with Wi-Fi.
- iGPU: AAPL,ig-platform-id needs to be replaced from AAAWWQ== to BQAcWQ== in config.plist (line 389)

Everything seems to work as it worked in earlier macOS versions, tests + screenshots are coming soon.

## Ventura 13.5 OpenCore 0.9.3
```diff
+ Works good
- No Bluetooth
```

**For creating USB installer use installer branch (download as ZIP and put files in OC folder)**
[Installer branch](https://github.com/KrzysiuWojcik/Fujitsu-Lifebook-U748-Hackintosh/tree/installer)

### What's working and what's not?

- [x] Boots, sleeps and wakes
- [x] iGPU - Intel UHD 620 with full QE/CI
- [x] Wi-Fi - using latest AirportItlwm Pre-Release (itlwm works but makes boot process much longer)
- [ ] Bluetooth (?)
- [x] SierraWireless EM7305 4G LTE modem - works, but you need to manually add file "/System/Library/CoreServices/Menu Extras/WWAN.menu" to auto-start
- [x] SmartCard reader (shows up in System Info, can't test properly)
- [x] O2Micro SDXC card reader (1217: 8621 faked to 14e4: 16bc + CtlnaSDXC.kext)
- [x] ELAN I<sup>2</sup>C Touchpad (buttons working as Force Touch, disable it in preferences to make left click working)
- [x] Function keys (F2, F3 & F4 for volume, F7 & F8 for brightness)
- [x] Battery time is decent
- [x] Power management (lower frequency on idle, turbo boost on stress)
- [x] M.2 SATA SSD
- [x] M.2 NVMe SSD
- [x] Audio is working with latest AppleALC installed
- [x] Continuity Camera works only over USB (that's known to happen also on real Macs)
- [ ] HandOff is not working (because of no bluetooth)
- [x] External video output is working on internal DisplayPort and PortReplicator's DisplayPort, other ports not tested

### Screenshots

![Zrzut ekranu 2022-11-30 o 12 58 58](https://user-images.githubusercontent.com/36552450/204908256-7abdb75f-e943-4f4d-9ebe-51b8de7f151b.png)
![Zrzut ekranu 2022-12-5 o 20 56 02](https://user-images.githubusercontent.com/36552450/205731586-852f0c2d-e715-465d-8a27-a7b5935bed9c.png)



## Monterey 12.6.1 OpenCore 0.8.6
```diff
+ Works good
! External video output was not tested 
```

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
- [ ] External video output not tested

### Screenshots
![Zrzut ekranu 2022-11-30 o 21 08 29](https://user-images.githubusercontent.com/36552450/204898628-bdf417e0-ea71-426e-924f-e0908857b1d5.png)
<br><i>macOS Monterey
- custom WWAN icons (iOS style) placed into /S*/L*/CoreServices/Menu\ Extras/WWAN.menu
- HandOff from iPhone is working
</i><br>



### Notes
To make your EM7305 LTE modem working, you need to use Linux, in this example Ubuntu.
- Install qmicli: <code>sudo apt install -y qmicli</code>
- Make sure your device is recognized: <code>ls /dev/cdc-wdm0</code> (it can be also cdc-wdm1 etc.)
- Get your USB compositions: <code>sudo qmicli --device=/dev/cdc-wdm0 --dms-swi-get-usb-composition</code>
- Set your USB composition that provides both QMI and MBIM (or only QMI if you don't dual boot) and is marked as SUPPORTED (in my case it will be comp 14): <code>sudo qmicli --device=/dev/cdc-wdm0 --dms-swi-set-usb-composition 14</code>
- reset your card and reboot to macOS: <code>sudo qmicli --device /dev/cdc-wdm0 --dms-set-operating-mode=offline && sudo qmicli --device /dev/cdc-wdm0 --dms-set-operating-mode=reset && init 6</code>

