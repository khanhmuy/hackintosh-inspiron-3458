# <div align="center">hackintosh-inspiron-3458</div>
## Intro
![About This Mac](https://i.imgur.com/OzJVxRl.png)

|          | Version                 |
|----------|-------------------------|
| OpenCore | 0.7.7                   |
| macOS    | Big Sur 11.6.3 (20G415) |

- Supported macOS versions: High Sierra, Mojave, Catalina, Big Sur (Use 0.7.7 if you want to boot Big Sur or newer) (~~Monterey should work, I just haven't tested it yet and I'm not gonna spend another 3 hours setting everything up, you will need to generate and use a supported SMBIOS as well~~ Monterey definitely doesn't work lolz)

## Info / Disclaimer
### Usage
- You can use it however you like, except for commercial purposes (such as work enviroments and reselling your Hackintosh), refer to the [Psystar case](https://en.wikipedia.org/wiki/Psystar_Corporation). TLDR, you'll get your ass sued if you do so.
- Reminder that this is only a base for your OpenCore setup, it is strongly recommended that you follow the entire OpenCore guide [here](https://dortania.github.io/OpenCore-Install-Guide/)
- There will be differences probably even for the same line of machine, however if you're feeling lazy I guess you can just copy the config, just remember to add in information such as the MLB or the ROM in `PlatformInfo` (please don't use mine), and try to use different Apple IDs if you're booting multiple macOS verions on the same PlatformInfo as my account got flagged sus by not doing so.
### Notes
Don't use case-sensitive APFS if you want to use Steam or Adobe tools.
### Issues
- Sleep doesn't work
- Brightness controls *do* work, but you have to use Fn+S and Fn+B
- Most of the kexts and OC itself are `DEBUG` versions, which may increase boot times. Replace them if you're bothered. (not needed in 0.7.7)
- Booting on 0.7.7 is a bit hit or miss, sometimes it doesn't boot at all, other times it boots but take a long time and would not have graphics accleration. Works most of the time though

## Hardware

|                                           | Specifications                                                                | macOS Big Sur Compatibility                                                                                                                   |
| ----------------------------------------- | ----------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| ``Chipset``                               | Intel Haswell                                                               |                                                                                                                                               |
| ``CPU``                                   | Intel Core i3-4005U Processor, 2 Cores / 4 Threads, 0.8GHz / 1.7GHz, 3MB Cache | Native power management works                                                                                                                                               |
| ``Memory``                                | 4GB DDR3-1600MHz, up to 8GB                                     |                                                                                                                                               |
| ``GPU``                                   | Intel HD Graphics 4400                                                       | Graphics accleration works                                                                                                                                              |                                                                                         |
| ``Storage``                               | Kingston A400 SATA SSD 240GB (for the love of God, use a fucking SSD; or only install High Sierra or older if you're desperate, keep in mind that it would be almost unusable)                                              |                                                                                                                                               |
| ``Screen``                                | 14.0" 768p 60Hz, 1366 x 768 TN                                            |                                                                                                                                               |
| ``Webcam``                                | Integrated HD Webcam                                                          | Does not work at all                                                                                                                                             |
| ``Ethernet``                              | RJ45 RTL8106E Realtek Ethernet                                                 | Works                                                                                                                                              |
| ``WiFi``                                  | Intel Wireless-AC 3160                                                        | Using [AirportItlwm.kext](https://github.com/OpenIntelWireless/itlwm/releases)                                                                |
| ``Bluetooth``                             | Intel                                                                         | Using [IntelBluetoothFirmware](https://openintelwireless.github.io/IntelBluetoothFirmware). I haven't gotten AirDrop to work at all, will try to fix (although you're better off getting a natively supported card) |
| ``Input & Output``                        | USB 3.0 (USB-A) x1 + USB 2.0 (USB-A) x2<br>HDMI 1.4                    | There are only 15 ports on this laptop so USB mapping isn't really needed, kext still provided though |
| ``Audio``                            | Realtek ALC255 (ALC3234)                                                      |                                                                                                                                               |
| ``Battery``                               | 40Wh Lithium-ion                                                                  | Battery readout works, I can't really test its accuracy though cuz mine is almost dead                                                                                                                                  |
| ``Keyboard``                              | -                                                                             | Use Fn+S and Fn+B for brightness control.                                                                                                                                              |
| ``Touchpad``                              | Dell Touchpad (Synaptics SMBus, I2C)                                                                | No issues. ACPI should be patched to enable gesture                                                                                           |
| ``Dimensions``<br>``Weight``<br>``Power`` | 21.4mm x 345mm x 243mm<br>1.8kg<br>45W Power Adapter                        | ACPI patches won't help with these                                                                                                            |

<div align="center">readme prouldly ~~stolen from~~ inspired by [beerpiss](https://github.com/beerpiss/dell-vostro-15-3568-hackintosh)'s</div>
