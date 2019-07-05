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
- Case : Fractal Design Define Mini C Tempered Glass Edition
- Power : FSP Hyper K 600W 80Plus Standard 230V EU
- Cooler : Zalman CNPS9X Optima White LED
- External Port & Slot : USB 2.0 * 2, USB 3.2 Gen 1 * 4, USB 3.2 Gen 2 * 1, Type C * 1 (USB 3.2 Gen 1), PS2 Port * 1 Displayport * 1, HDMI * 1, DVI-D * 1, D-SUB * 1, Intel Gigabit LAN * 1, 8CH Audio Port
- Display : Dell P2417H
- Speaker : Dell AC511
- Keyboard : Apple Keyboard with Numeric Keypad (A1243)
- Mouse : Logitech T630
- Windows 10 Pro


## Bios/Clover Bootloader/macOS Version

- Bios : F12
- Clover Bootloader : Above v2.4k r4920
- macOS : Above 10.14


## Bios Setup

- Load Optimized Defaults
- [Internal Graphics] Enable


## DSDT Patch

- [sys] Add IMEI
- [sys] Fix _WAK Arg0 v2
- [sys] Fix Mutex with non-zero SyncLevel
- [sys] Fix PNOT/PPNT
- [sys] HPET Fix
- [sys] Fix IRQ Fix
- [sys] OS Check Fix (Windows 10)
- [sys] RTC Fix
- [sys] Shutdown Fix
- [sys] Shutdown Fix v2
- [sys] SMBUS Fix


## Drivers64UEFI

- ApfsDriverLoader-64.efi
- AptioMemoryFix-64.efi
- EmuVariableUefi.efi
- FSInject-64.efi
- VBoxHfs-64.efi
- VirtualSmc.efi


## Kexts

- AirportBrcmFixup.kext
- AppleALC.kext
- BrcmFirmwareRepo.kext
- BrcmPatchRAM2.kext
- EFICheckDisabler.kext
- IntelMausiEthernet.kext
- Lilu.kext
- SMCBatteryManager.kext
- SMCLightSensor.kext
- SMCProcessor.kext
- SMCSuperIO.kext
- USBPorts.kext    -    Hackintool generated
- VirtualSMC.kext
- VoodooPS2Controller.kext


## ETC

***After installation***
- Turn off FileVault2 (necessary)  
- Remove these boot flags  
    -v  
    debug=0x100  
    keepsyms=1
- Additional patches are required for iMessage and Facetime activation
- Add a HiDPI patch based on your display resolution
- Depending on the case and built-in wireless card installed, additional patches of the internal USB port might be required

***Intel UHD Graphics 630 iGPU with AMD dGPU***
- This build is suitable for the GA-B360M-D3H system which uses iGPU of 'Intel UHD Graphics 630' and AMD dGPU  
  If your iGPU is not 'Intel UHD Graphics 630' or there is no AMD dGPU, additional graphics patches might be required

***Works in headless mode***
- The output ports of all iGPU are the dummy port


## Issues
- PS2 port has not been tested yet

- FileVault2 not works


## Screenshots

<img width="698" alt="01SystemOverview" src="https://user-images.githubusercontent.com/46496967/60285360-bf701700-9948-11e9-916b-af54a5a76fa1.png">

<img width="698" alt="02SystemDisplay" src="https://user-images.githubusercontent.com/46496967/60285249-7a4be500-9948-11e9-846b-0245575f76f0.png">

![03VideoProc](https://user-images.githubusercontent.com/46496967/60286879-81282700-994b-11e9-9b40-0f146f05ece0.png)

![04IntelPowerGadget](https://user-images.githubusercontent.com/46496967/60286878-81282700-994b-11e9-848d-7af1ea613dbb.png)

![05GeekBenchCPU](https://user-images.githubusercontent.com/46496967/60286876-808f9080-994b-11e9-9e72-c733238407fa.png)

![06GeekBenchGPU](https://user-images.githubusercontent.com/46496967/60286873-808f9080-994b-11e9-9543-2c24fbafdce2.png)

![07USBPorts](https://user-images.githubusercontent.com/46496967/60286872-7ff6fa00-994b-11e9-8f46-c7815c39a556.png)
