# Big-Sur-Acer-A515-52G-577T-OpenCore

#### Supports MacOS 11.0.x

<p align="center">
  <img src="https://i.imgur.com/q7VSJPa.png" alt="Specs">
</p>


## What's Working...
 - [x] Audio & headphone jack
 - [x] QE/CI on iGPU
 - [x] Battery Management
 - [x] ACPI Display brightness with hot keys / slider
 - [x] Ethernet
 - [x] HDMI + Audio
 - [x] Touchpad + Gestures
 - [x] Webcam
 - [x] Usb 3.0 + Type C
 - [x] Native hotkey support with Fn keys
 - [x] SD Card reader 

## What's NOT Working...
 - [ ] dGPU does not work, It's disabled (nVidia Optimus is not supported)
 - [ ] Qualcomm Wifi Card, You'll need to replace it with a BroadCom card, In my case I used a Bcm94350zae (CN-0VW3T3).

### Important
 Please change `SystemSerialNumber`, `SystemUUID` and `MLB` in the config.plist file located at the EFI folder, see Basic Installation section below.<br/><br/>
 With the Bcm94350zae I used, bluetooth was not working (not even on windows or linux), To make it work I needed to cover
 some of the card's pins, I tried to search on the web the pictures of the pins needed to isolate but unfortunately I wasn't able to find it anymore. Note that this
 may not happen with you, but if it does and I still hadn't updated this, feel free to open an issue about that and I'll try to help.<br/><br/>
 These files are relatively old and I haven't tested it using the newest macOS version because I don't have a hackintosh anymore, before trying to install Monterey
 using these files, update the opencore binaries in this repo to the [latest version here.](https://github.com/acidanthera/OpenCorePkg/releases)
 


## Installation

 ### BIOS Settings
* *Security* → Set supervisor password (to disable secure boot)
* *Security* → Password on boot → **Disable**
* *Boot* → Secure Boot → **Disable**
* *Boot* → Boot Mode → **UEFI**
* *Main* → Lid Open resume → **Enabled**
* You will also need to set sata mode to **AHCI**.



###  Basic Installation

- Create a Bootable USB for MacOS by using by Dortania's [OpenCore-Install-Guide](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/).
- Install MacOS to SSD / Hard drive. (While installing, connect USB keyboard and mouse).
- Copy **ALL**  content of this repo inside the EFI partition of SSD / Hard drive.
- **[IMPORTANT]** Make sure to Generate system definitions of MacBook pro 15.2 in config.plist file using [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) & change `SystemSerialNumber`, `SystemUUID` and `MLB` values to your generated values..

### Post Installation
- If you have Installed MacOS on SSD, Enable TRIM using following command:

```sh

$ sudo trimforce enable

```


<p align="center">
<b>⭐ Please consider starring this repository if it helped you! ⭐</b><br/>
<b>Huge thanks to SiddheshNan for providing alot of files including this README in his repository, AcidAnthera and to tonymacx86 and olarila community for all of the
other resources I used during my setup</b>
</p>

