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

### Whats Working, Not, or Not tested

| Working | Not Working | Not Tested |
|--|--|--|
| Native WiFi 🛜 | Finger Print Reader 🫆 | Dual Booting 🥾 |
| Bluetooth 🔵 |AirDrop & Continuity 💨 | |
|Find My 📱 (needs to be enable in settings)| Thunderbolt 3 ♆ ||
| Brightness ☀︎ & Volume Control 🎧 | Sidecar Wireless 🌐 ||
| Battery Information 🔋 |Apple Watch Unlock ⌚ ||
| Audio (Audio Jack & Speaker) 🔊
| USB Ports 🔌 
| Built-in Camera 🎥
| Graphics Acceleration ▶️
| Trackpoint ➤
| Touchpad 🖱️
| Power management ⚡
| Sleep 💤
| FaceTime 👩🏻‍💻
| iMessage
| HDMI
| Automatic OS updates
| Handoff 
| Universal Clipboard
| USB-C
| Undervotling
 
### Why use macos,
For me i have a iphone and the apple ecosystem is very well rounded,
Everything works togeter, Universla Clipbore, My i messages syncs, my passwords syncs, find my iphone or mac.
They are really build for one another.
