# Dell Inspiron 3650 (2018) - Hackintosh
As posted by myself on [Reddit](https://www.reddit.com/r/hackintosh/comments/vkfgrq/finally_monterey_on_dell_inspiron_3650_2018_w), this specific Hack runs on macOS 12.4 Monterey.

![Hackintosh Specifications](https://preview.redd.it/r1qygyc3vr791.png?width=960&crop=smart&auto=webp&s=7159326fad8099f5eff431102490a26537796bdf)

### Specifications
- CPU: Intel(R) Core(TM) i5-6400 @ 2.70 Ghz Quad Core
- iGPU: Intel HD Graphics 530 (Not used as Display)
- dGPU: NVIDIA GT 730 2GB DDR3
- RAM: Dell OEM 1600mhz
- Motherboard: Dell OEM (Based off H110 Chipset)
- Audio Codec: Realtek AC3600
- Ethernet Card: Realtek RTL3111
- Wifi/BT: Disabled, (removed because it broke like years ago)
- BIOS Revision: 3.12.1
- OC Version: 0.7.8 (but shows up as 0.8.0 for some reason?)

### Guide
- Use [Dortanias Guide](https://dortania.github.io/OpenCore-Install-Guide/) and enable this specific [Dell Quirk](https://dortania.github.io/OpenCore-Install-Guide/config.plist/skylake.html#kernel) in config.plist sticking with iMac17,1 SMBIOS
- You will encounter a Kernel Panic during the installer, it is a **USB Handoff Issue** (due to lack of XCHI Handoff Bios Setting) so make sure to enable this in config.plist: `UEFI -> Quirks -> ReleaseUsbOwnership -> True`
- You will also have problems regarding keyboard and mouse detection + Power Delivery during the installer prompting you to connect a Magic Mouse. Install `VoodooI2C` as a Workaround and additionally use the `IOHIDFamily` Patch under [Userspace Issues](https://dortania.github.io/OpenCore-Install-Guide/troubleshooting/extended/userspace-issues.html#keyboard-and-mouse-broken-in-big-sur).

### What's Working
- Keyboard, Mouse, IO Ports, USB 3.0 & USB 2.0, SD Card Reader (Front)
- Ethernet
- Display up to 2K 21:9 @ 60hz or 4K @ 60hz (Screenshot is 1080p @ 120hz)
- iMessage/Facetime

### Not Working
- DVI Port but who uses that anyway >.>

### Credits
- [Dortanias Guide](https://dortania.github.io/OpenCore-Install-Guide/)
