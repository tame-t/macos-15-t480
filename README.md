<div align="center">

<h1>A guide for installing macOS 15 on a ThinkPad T480</h1>

<p>A complete guide for installing <a href="https://apps.apple.com/us/app/macos-sequoia/id6596773750?mt=12">macOS</a> Sequoia on the <a href="https://www.lenovo.com/us/en/p/laptops/thinkpad/thinkpadt/thinkpad-t480/22tp2tt4800?srsltid=AfmBOooXFtlhLQXZFbJswnsfmBPZG1QH3bZPpnrvW3ITn5nMiqsZHqEH">ThinkPad T480</a> from start to finish using <a href="https://dortania.github.io/OpenCore-Install-Guide/">OpenCore</a> as the bootloader, including a guide for undervolting via <a href="https://github.com/sicreative/voltageshift">VoltageShift</a>, WiFi patching via <a href="https://github.com/laobamac/OCLP-Mod">OCLP Mod</a>.</p>

<img src="thinkpadpro.png" alt="Macos Preview" />

<br/>

[![macOS](https://img.shields.io/badge/macOS-Sequoia_15-007AFF?style=flat-square&logo=apple&logoColor=white)](https://www.apple.com/macos/macos-sequoia/)
[![OpenCore](https://img.shields.io/badge/Bootloader-OpenCore-1baff9?style=flat-square&logo=apple&logoColor=white)](https://dortania.github.io/OpenCore-Install-Guide/)
[![VoltageShift](https://img.shields.io/badge/Undervolting-VoltageShift-9b59b6?style=flat-square&logo=github&logoColor=white)](https://github.com/sicreative/voltageshift)
[![OCLP Mod](https://img.shields.io/badge/WiFi-OCLP_Mod-27ae60?style=flat-square&logo=github&logoColor=white)](https://github.com/laobamac/OCLP-Mod)
[![License](https://img.shields.io/badge/License-MIT-brightgreen?style=flat-square&logo=opensourceinitiative&logoColor=white)](LICENSE)

**This repo is made for educational purposes, and I do not condone the piracy of any Apple products.**

**I am not responsible for causing any harm to your devices; this guide is provided as is and should only be used at your own risk.**

**This guide was made for my ThinkPad T480 and is not guaranteed to work for your t480.**

</div>

---

### Things You Need
1. A working ThinkPad T480.
2. A working Windows computer, this can be your ThinkPad too.
3. A 4GB USB drive. **You can use an SD card if you have an SD card to USB adapter, since the T480 SD card slot is not loaded in OpenCore's boot menu and in BIOS**.
4. Some time to get things working.

---

### My Specs

| T480      | Model |
|--|--|
| CPU       | Intel Core i5-8350U |
| GPU       | Integrated Intel UHD Graphics 620 |
| SSD       | NVMe SSD 256GB |
| Display   | 1080p panel |
| Memory    | 8GB DDR4 2400MHz |
| Camera    | Camera works on macOS |
| WiFi & BT | Intel Dual Band Wireless-AC 8265 |
| Keyboard  | Backlight Keyboard |

---

### What's Working, Not, or Not tested

| Working | Not Working | Not Tested |
|--|--|--|
| Native WiFi 🛜 | Finger Print Reader 🫆 | Dual Booting 🥾 |
| Bluetooth 🔵 |AirDrop & Continuity 💨 | Simcard 📶 wwan |
| Find My 📱 (needs to be enable in settings)| Thunderbolt 3 ♆ | Ethernet port 🌐 |
| Brightness ☀︎ & Volume Control 🎧 | Sidecar Wireless 🌐 ||
| Battery Information 🔋 |Apple Watch Unlock ⌚ ||
| Audio (Audio Jack & Speaker) 🔊
| Location services 🌍
| USB Ports 🔌 
| Built-in Camera 🎥
| Graphics Acceleration ▶️
| Trackpoint ➤
| Touchpad 🖱️
| Power management ⚡
| Sleep 💤
| FaceTime 👩🏻‍💻
| iMessage 💬
| HDMI 🖥️
| Automatic macOS updates 🔄
| Handoff 🫴
| Universal Clipboard 📋
| USB-C 🔌
| Undervotling 🪫
 
### Why use macOS
For me, I have an iPhone, and the Apple ecosystem is very well-rounded.
Everything works together: Universal Clipboard, my iMessages sync, my passwords sync, Find My iPhone or Mac.
They are really built for one another.

### Getting started
We are going to start by installing macOS Ventura, then upgrading to macOS Sequoia, applying the patches that fix airportltwm, and allowing native Wi-Fi connectivity with an Intel Wi-Fi card. Then we will add the Voltageshift to startup for undervolting.

First, we are going to configure the BIOS settings for OpenCore to function properly.

#### The bios settings:
-  `Security > Security Chip`: must be **Disabled**
-  `Memory Protection > Execution Prevention`: must be **Enabled**
-  `Virtualization > Intel Virtualization Technology`: must be **Enabled**
-  `Virtualization > Intel VT-d Feature`: must be **Enabled**
-  `Anti-Theft > Computrace -> Current Setting`: must be **Disabled**
-  `Secure Boot > Secure Boot`: must be **Disabled**
-  `Intel SGX -> Intel SGX Control`: must be **Disabled**
-  `Device Guard`: must be **Disabled**

In the Thunderbolt menu, set the following options:

-  `Thunderbolt BIOS Assist Mode`: **UEFI Only**
-  `Wake by Thunderbolt(TM) 3`: **No**
-  `Security Level`: **No**
-  `Support in Pre Boot Environment > Thunderbolt(TM) device`: **No**

In the Startup menu, set the following options:

-  `UEFI/Legacy Boot`: **UEFI Only**
-  `CSM Support`: **No**

Now we will prepare the USB for installing Ventura. 
The USB must be at least 4 GB for it to house the recovery images. 

The reason why we are installing macOS Ventura first is that macOS Sequoia patches the airportilwm.kext; the older version used to get wifi in recovery. 
I have seen some people who use the Ethernet connection with Sequoia's recovery, but for this guide, I will use Wi-Fi instead.

Unfortulatly i can't provide a .img or .iso file that is preconfigured because that is considered pricey and is very illegal. 
