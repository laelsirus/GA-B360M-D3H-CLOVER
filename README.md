# GA-B360M D3H with UHD630 iGPU AMD dGPU CLOVER

## Specifics

- CPU : Intel® Core™ i7-8700 Processor (12M Cache, up to 4.60 GHz)
- Mainboard : Gigabyte GA-B360M D3H Durable Edition
- Graphics : Intel® UHD Graphics 630, SAPPAIRE RX 570 4GB
- Sound : Realtek ALC892
- Memory : Essencore KLEVV DDR4 16G PC4-21300 CL16 2666MHZ (8GB * 2 Dual Channel)
- M.2 NVME SSD : Samsung PM961 512GB
- 2.5 SATA SSD : Samsung 960 EVO 250GB
- Wireless : BCM943602CS
- Power : FSP Hyper K 600W 80Plus Standard 230V EU
- Cooler : Zalman CNPS9X Optima White LED
- Case : Fractal Design Define Mini C Tempered Glass Edition
- External Port & Slot : USB 2.0 * 2, USB 3.2 Gen 1 * 4, USB 3.2 Gen 2 * 1, Type C * 1 (USB 3.2 Gen 1), PS2 Port * 1 Displayport * 1, HDMI * 1, DVI-D * 1, D-SUB * 1, Intel Gigabit LAN * 1, 8CH Audio Port
- Display : Dell P2417H
- Speaker : Dell AC511
- Keyboard : Apple Keyboard with Numeric Keypad (A1243)
- Mouse : Logitech MX Master 2, Logitech Ultra thin Touch Mouse T630
- Windows 10 Pro


## BIOS/Clover Bootloader/macOS Version

- BIOS : F13
- Clover Bootloader : Above v2.5k
- macOS : 10.14.X, 10.15.X


## BIOS Setup

- Load Optimized Defaults
- [Internal Graphics] Enable


## DSDT Patch

- [sys] Add IMEI
- [sys] Fix _WAK Arg0 v2
- [sys] Fix Mutex with non-zero SyncLevel
- [sys] Fix PNOT/PPNT
- [sys] HPET Fix
- [sys] IRQ Fix
- [sys] OS Check Fix (Windows 10)
- [sys] RTC Fix
- [sys] Shutdown Fix v2
- [sys] SMBUS Fix

***Modify DSDT on your system to prevent kernel panic***


## SSDT

- SSDT-EC.aml [USB Power Control]
- SSDT-UIAC.aml [USB Mapping]
- SSDT-UPRW.aml [Prevent wake from USB]


## ACPI DSDT Patches

- change GFX0 to IGPU [IGPU Fix]
- change HDAS to HDEF [Audio Fix]
- change HECI to IMEI
- change MEI to IMEI
- change ECDV to EC [USB Fix]
- change UPRW to XPRW [Prevent wake from USB]
- change GPRW to YPRW [Prevent wake from USB]


## Drivers64UEFI

- ApfsDriverLoader-64.efi
- AptioMemoryFix-64.efi
- EmuVariableUefi.efi
- FwRuntimeServices.efi
- OcQuirks.efi
- VBoxHfs-64.efi
- VirtualSmc.efi


## Kexts

- AGPMInjector.kext    -    Generated with AGPMInjector by Pavo-IM
- AirportBrcmFixup.kext    -    For edit Country Code to #a
- AppleALC.kext
- CPUFriend.kext
- CPUFriendDataProvider.kext    -    Generated with one-key-cpufriend by stevezhengshiqi
- EFICheckDisabler.kext
- IntelMausiEthernet.kext
- Lilu.kext
- SMCBatteryManager.kext
- SMCLightSensor.kext
- SMCProcessor.kext
- SMCSuperIO.kext
- USBPorts.kext    -    Generated with Hackintool
- VirtualSMC.kext
- WhateverGreen.kext

***AGPMInjector.kext, CPUFriend.kext, and CPUFriendDataProvider.kext are not mandatory kext  
But creating it for your system will help you manage power***


## Boot Arguments

- darkwake=10 [Prevent Sleep, Powernap Issue]
- dart=0 [Sidecar Activation]
- brcmfx-country=#a [Set Country Code for Universal]


## ETC

***After Installation***
- Turn off FileVault2 (necessary)  
- Remove these boot flags  
    -v  
    debug=0x100  
    keepsyms=1
- Additional patches are required for iMessage and Facetime activation
- Depending on the case and built-in wireless card installed, additional patches of the internal USB port might be required
- Add a HiDPI patch based on your display resolution
- It is recommended that you do a new ACPI patch on your system

***Intel® Core™ i7-8700 Processor***
- CPUFriendDataProvider.kext has been modified to manage the operation of the 'Intel® Core™ i7-8700 Processor'  
  If your CPU is not 'Intel® Core™ i7-8700 Processor', remove or regenerate the CPUFriendDataProvider.kext

***Intel® UHD Graphics 630 iGPU with AMD dGPU***
- This build is compatible for the GA-B360M-D3H system which uses iGPU of 'Intel® UHD Graphics 630' and AMD dGPU  
  If your iGPU is not 'Intel® UHD Graphics 630' or there is no AMD dGPU, additional graphics patches might be required  
  (First remove all 'Devices/Properties' from config.plist)
- 'AGPMInjector.kext' must be recreated for each type of AMD dGPU being used.

***Works in headless mode***
- The output ports of all iGPU are the dummy port

***Audio***
 - Built-in Output = Green [Front Left, Front Right] (Share with Front Panel Audio)
 - Built-in Line Output 1 = Black [Rear Left, Rear Right]
 - Built-in Line Output 2 = Orange [Front Center, LFE]
 - Built-in Line Output 3 = Gray [Side Left, Side Right]
 - Built-in Input = Pink (Share with Front Panel Audio)
 - Built-in Line Input = Blue


## Issues

- PS2 port not works

- F_USB2(HS14) is disabled to keep macOS USB port limited

- FileVault2 not works


## Screenshots

<img width="698" alt="01SystemOverview" src="https://user-images.githubusercontent.com/46496967/60285360-bf701700-9948-11e9-916b-af54a5a76fa1.png">

<img width="698" alt="02SystemDisplay" src="https://user-images.githubusercontent.com/46496967/60285249-7a4be500-9948-11e9-846b-0245575f76f0.png">

![03VideoProc](https://user-images.githubusercontent.com/46496967/60286879-81282700-994b-11e9-9b40-0f146f05ece0.png)

![04IntelPowerGadget](https://user-images.githubusercontent.com/46496967/60286878-81282700-994b-11e9-848d-7af1ea613dbb.png)

![05GeekBenchCPU](https://user-images.githubusercontent.com/46496967/60286876-808f9080-994b-11e9-9e72-c733238407fa.png)

![06GeekBenchGPU](https://user-images.githubusercontent.com/46496967/60286873-808f9080-994b-11e9-9543-2c24fbafdce2.png)

![07USBPorts](https://user-images.githubusercontent.com/46496967/74525575-bc23ad00-4f64-11ea-9d93-f066e2715b6e.png)
