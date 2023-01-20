# hackintosh-inspiron-3458
## Intro
![About This Mac](https://cdn.discordapp.com/attachments/885809091459575828/952168289793110046/unknown.png)

|          | Version                 |
|----------|-------------------------|
| OpenCore | 0.7.7                   |
| macOS    | Big Sur 11.6.5 (20G5D7) |

- Supported macOS versions: High Sierra, Mojave, Catalina, Big Sur, Monterey (Use 0.7.7 if you want to boot Big Sur or newer).
- Even though you can run Monterey without any deal-breaking issues, I would recommend sticking with 11 or older because of the *very* underpowered CPU and excessive paging. Monterey kexts will not be included with 0.8.4 and newer.

## Info / Disclaimer
### Info
- `boot-args` used: `-v alcid=86 -disable_nightshift keepsyms=1 debug=0x100 swd_panic=1`
- `alcid`: `86`
- Recommended SMBIOS: `MacBookAir6,2`, `MacBookPro11,4` (use this if you want to boot Monterey).
- On 0.8.4, `ShowPicker`, `ScanPolicy` and `HideAuxilary` are set up in a way that automatically boots to a APFS partition with macOS installed without user confirmation. Adjust accordingly for installation (that's why you should read the guide).
### Usage
- You can use it however you like, except for commercial purposes (such as work enviroments and reselling your Hackintosh), refer to the [Psystar case](https://en.wikipedia.org/wiki/Psystar_Corporation). TLDR, you'll get your ass sued if you do so.
- Reminder that this is only a base for your OpenCore setup, it is strongly recommended that you follow the entire OpenCore guide [here](https://dortania.github.io/OpenCore-Install-Guide/)
- There will be differences probably even for the same line of machine, however if you're feeling lazy I guess you can just copy the config, just remember to add in information such as the MLB or the ROM in `PlatformInfo` (please don't use mine), and try to use different Apple IDs if you're booting multiple macOS verions on the same PlatformInfo as my account got flagged sus by not doing so.
- Remember to disable Apple Secure Boot before installing any version older than Big Sur (Enabled by default).
- Please use an SSD, please, please. However, do keep in mind that SSDs with lower TBWs should probably stay away from macOS 11 and newer. This can be mitigated by not logging in to iCloud (basically stops the `secd` process from running, which for some reason writes a lot, I wish I had known this sooner).
- **DO NOT USE ANY INSTALLER NOT FROM APPLE**, no one knows if/how they've been tampered with, and they *always* break the APFS system volume seal, which breaks OTA updates, and are generally not trustworthy at all.
#### Post-install
- [Disable CFG Lock](https://github.com/dreamwhite/bios-extraction-guide/tree/master/Dell): my offset is `0x37`, found on whatever the heck is latest, probably best to update your firmware before doing stuff like this as well. Or if you don't want to disable it, or while installing, enable `Kernel -> Quirks -> AppleXcpmCfgLock` (Enabled by default).
### Issues
- Audio over HDMI doesn't work.
- Brightness controls *do* work, but you have to use `Fn+S` and `Fn+B`. Fix it yourself if you're bothered.
- Most of the kexts and OC itself are `DEBUG` versions, which may increase boot times. Replace them if you're bothered (not needed in 0.7.7 and newer).
- The card reader doesn't work (although mine is probably dead because it doesn't work in Windows either :skull:)
### Notes
- Don't use case-sensitive APFS if you want to use Steam or Adobe tools.
- After installation, open System Preferences and go to Displays -> Color, uncheck `Show profiles for this display only`, then select `sRGB IEC61966-2.1`, this will make your colors look *somewhat* right (definitely not calibrated or anything but yeah, not an oversaturated mess)
 
![color](https://media.discordapp.net/attachments/885809091459575828/966112499487346718/unknown.png)
## Hardware

|                                           | Specifications                                                                | macOS Compatibility                                                                                                                   |
| ----------------------------------------- | ----------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| ``Chipset``                               | Intel Lynx Point (Haswell-ULT)                                                               |                                                                                                                                               |
| ``CPU``                                   | Intel Core i3-4005U Processor, 2 Cores / 4 Threads, 0.8GHz / 1.7GHz, 3MB Cache | With native power management                                                                                                                                               |
| ``Memory``                                | 4GB DDR3-1600MHz, up to 8GB                                     |                                                                                                                                               |
| ``GPU``                                   | Intel HD Graphics 4400                                                       | With full QE/CI (Graphics accleration)                                                                                                                                             |                                                                                         |
| ``Storage``                               | Kingston A400 SATA SSD 240GB                                              | For the love of God, use a fucking SSD; or only install High Sierra or older if you're desperate, keep in mind that it would be almost unusable                                                                                                                                              |
| ``Screen``                                | 14.0" 768p 60Hz, 1366 x 768 TN                                            |                                                                                                                                               |
| ``Webcam``                                | Integrated HD Webcam                                                          | Works!                                                                                                                                            |
| ``Ethernet``                              | RJ45 RTL8106E Realtek Ethernet                                                 | Works.                                                                                                                                              |
| ``WiFi``                                  | Intel(R) Dual Band Wireless AC 3160                                                        | Using [AirportItlwm.kext](https://github.com/OpenIntelWireless/itlwm/releases)                                                                |
| ``Bluetooth``                             | Intel                                                                         | Using [IntelBluetoothFirmware](https://openintelwireless.github.io/IntelBluetoothFirmware). |
| ``Input & Output``                        | USB 3.0 (USB-A) x1 + USB 2.0 (USB-A) x2<br>HDMI 1.4                    | There are only 15 ports on this laptop so USB mapping isn't really needed, kext still provided though |
| ``Audio``                            | Realtek ALC255 (ALC3234)                                                      |                                                                                                                                               |
| ``Battery``                               | 40Wh Lithium-ion                                                                  | Battery readout works, I can't really test its accuracy though cuz mine is basically dead                                                                                                                                  |
| ``Keyboard``                              | -                                                                             | Use Fn+S and Fn+B for brightness control.                                                                                                                                              |
| ``Touchpad``                              | Dell Touchpad (Synaptics SMBus, I2C)                                                                | No issues.                                                                                            |
| ``Dimensions``<br>``Weight``<br>``Power`` | 21.4mm x 345mm x 243mm<br>1.8kg<br>45W Power Adapter                        | ACPI patches won't help with these                                                                                                            |

Special thanks to:
- [acidanthera](https://github.com/acidanthera) - the maker of OpenCore and your favourite kexts, for making this Hackintosh possible in the first place
- [dortania people](https://github.com/orgs/dortania/people) for the OpenCore Install Guide
- [Dreamwhite](https://github.com/dreamwhite) for their [Dell CFG Lock disabling guide](https://github.com/dreamwhite/bios-extraction-guide/tree/master/Dell)
- [NLTD2010](https://github.com/NLTD2010) for helping me fix sleeping and the webcam
- My sister in-law for buying me an SSD

readme prouldly ~~stolen from~~ inspired by [beerpiss](https://github.com/beerpiss/dell-vostro-15-3568-hackintosh)'s
