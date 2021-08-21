# Disclaimer: Windows sucks dogs so it may have fucked up the source by using CRLF, download from the [releases](https://github.com/khanhmuy/hackintosh-inspiron-3458/releases) tab

# hackintosh-inspiron-3458
## Supported macOS versions: High Sierra, Mojave, Catalina, BigSur

## Laptop specs:

- Intel Core i3-4005U
- 4GB RAM
- Graphics: Intel HD4400
- Wi-fi/Bluetooth card: Intel AC3160 (i'm cheap so i just don't bother swapping out the card)
- Audio: ALC 255/3234 (they're the same)
- Ethernet: *Real*tek RTL8106E

## Working:
- Wifi 
- Bluetooth
- Native Power Management
- Bluetooth
- USB ports
- Battery status (kinda sloopy tho)
- Keyboard & Trackpad
- Internal Audio & Microphone
- Headphone Jack
- HDMI Port (HDMI Audio)
- Graphics (Use Fn+B and Fn+S to control the screen brightness)
- Ethernet
- Battery
- iCloud/FaceTime/iMessage

## Not working:
- Sleep (would stay in a "half-asleep" state when the drive doesn't sleep, wake is fine tho)
- Internal webcam
- ~~Big Slurp~~ i mean Big Sur

## Known issues
- Sleep (as mentioned above)
- Proper brightness control remap

## Usage
You can use it however you like, except for commercial purposes (such as work enviroments and reselling their Hackintosh), refer to the [Psystar case](https://en.wikipedia.org/wiki/Psystar_Corporation)

*I expect you to have already read through OpenCore's guide **at least** one so this is only a vague guide*
## Pre-installation
### Creating the installer
- Follow [OpenCore's guide](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) on how to download and copy the online installer to your USB drive
- Get the [opencorepkg](https://github.com/acidanthera/OpenCorePkg/releases), copy the **contents** of X64 to the root of the USB drive
- Replace the **contents** of EFI\OC on your USB drive with the EFI folder that you downloaded from this repository
**Bios configuration**
Bios Config | Setting 
:---:| :---:
Intel SpeedStep | Enabled
Virtualization    | Enabled
USB Wake Support | Disabled
SATA Operation | AHCI

## Installation and Post-installation
- Follow [OpenCore's installation guide](https://dortania.github.io/OpenCore-Install-Guide/installation/installation-process.html#double-checking-your-work) then [OpenCore's Post-Install Guide](https://dortania.github.io/OpenCore-Post-Install/)
- As for SMBIOS, use MacSerial (included in opencorepkg) to generate a MacbookAir6,2 SMBIOS

## Credits:
- ~~Apple~~ no
- [Acidanthera](https://github.com/acidanthera) for the amazing boot manager that is OpenCore and your favourite kexts
- [Dortania](https://github.com/dortania) for the [OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)