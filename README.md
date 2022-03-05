# hackintosh-inspiron-3458
## Intro
![About This Mac](https://media.discordapp.net/attachments/885809091459575828/949673236210274304/unknown.png)

|          | Version                 |
|----------|-------------------------|
| OpenCore | 0.7.7                   |
| macOS    | Big Sur 11.6.3 (20G415) |

- Supported macOS versions: High Sierra, Mojave, Catalina, Big Sur (Use 0.7.7 if you want to boot Big Sur or newer, High Sierra, Mojave, Catalina not tested on 0.7.7) (~~Monterey should work, I just haven't tested it yet and I'm not gonna spend another 3 hours setting everything up, you will need to generate and use a supported SMBIOS as well~~ Monterey definitely doesn't work lolz)

## Info / Disclaimer
### Usage
- You can use it however you like, except for commercial purposes (such as work enviroments and reselling your Hackintosh), refer to the [Psystar case](https://en.wikipedia.org/wiki/Psystar_Corporation). TLDR, you'll get your ass sued if you do so.
- Reminder that this is only a base for your OpenCore setup, it is strongly recommended that you follow the entire OpenCore guide [here](https://dortania.github.io/OpenCore-Install-Guide/)
- There will be differences probably even for the same line of machine, however if you're feeling lazy I guess you can just copy the config, just remember to add in information such as the MLB or the ROM in `PlatformInfo` (please don't use mine), and try to use different Apple IDs if you're booting multiple macOS verions on the same PlatformInfo as my account got flagged sus by not doing so.
- Please use an SSD, please, please. However, do keep in mind that SSDs with lower TBWs should probably stay away from macOS 11 and newer. This can be mitigated by not logging in to iCloud (basically stops the `secd` process from running, which for some reason writes a lot, I wish I had known this sooner). The thing legit written 20 FUCKING TERRABYTES TO MY POOR 3-WEEK-OLD SSD
### Issues
- ~~Sleep doesn't work.~~ HOLY FUCK SLEEPS WORKS NOW. WEBCAM WORKS AS WELL. Thanks to [NLTD2010](https://github.com/NLTD2010) for letting me know how to fix it and ~~fucking up my efi without letting me back the thing up~~
- Audio over HDMI doesn't work (~~will try to fix~~ nah too lazy sorry)
- Brightness controls *do* work, but you have to use Fn+S and Fn+B.
- Most of the kexts and OC itself are `DEBUG` versions, which may increase boot times. Replace them if you're bothered (not needed in 0.7.7).
- Booting on 0.7.7 is a bit hit or miss, sometimes it doesn't boot at all, other times it boots but take a long time and would boot to safe mode and not have graphics accleration. Works most of the time though, try again if it doesn't. Also try to boot with `-v`, will be helpful when the thing doesn't boot.
### Notes
- Don't use case-sensitive APFS if you want to use Steam or Adobe tools.
- After installation, open System Preferences and go to Displays -> Color, uncheck `Show profiles for this display only`, then select `Generic RGB Profile`, this will make your colors look right (deffo not calibrated or anything but yeah, not an oversaturated mess)
 
![color](https://cdn.discordapp.com/attachments/885809091459575828/949294054053658634/unknown.png)
## Hardware

|                                           | Specifications                                                                | macOS Big Sur Compatibility                                                                                                                   |
| ----------------------------------------- | ----------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| ``Chipset``                               | Intel Haswell                                                               |                                                                                                                                               |
| ``CPU``                                   | Intel Core i3-4005U Processor, 2 Cores / 4 Threads, 0.8GHz / 1.7GHz, 3MB Cache | With native power management                                                                                                                                               |
| ``Memory``                                | 4GB DDR3-1600MHz, up to 8GB                                     |                                                                                                                                               |
| ``GPU``                                   | Intel HD Graphics 4400                                                       | With full QE/CI (Graphics accleration)                                                                                                                                             |                                                                                         |
| ``Storage``                               | Kingston A400 SATA SSD 240GB                                              | For the love of God, use a fucking SSD; or only install High Sierra or older if you're desperate, keep in mind that it would be almost unusable                                                                                                                                              |
| ``Screen``                                | 14.0" 768p 60Hz, 1366 x 768 TN                                            |                                                                                                                                               |
| ``Webcam``                                | Integrated HD Webcam                                                          | Works!                                                                                                                                            |
| ``Ethernet``                              | RJ45 RTL8106E Realtek Ethernet                                                 | Works, 100mbps link kinda lame tho, blame Dell for that                                                                                                                                              |
| ``WiFi``                                  | Intel Wireless-AC 3160                                                        | Using [AirportItlwm.kext](https://github.com/OpenIntelWireless/itlwm/releases)                                                                |
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
- [NLTD2010](https://github.com/NLTD2010) for helping me fix sleeping and the webcam
- My sister in-law for buying me an SSD

readme prouldly ~~stolen from~~ inspired by [beerpiss](https://github.com/beerpiss/dell-vostro-15-3568-hackintosh)'s
