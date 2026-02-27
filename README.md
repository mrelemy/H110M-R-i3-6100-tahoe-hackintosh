ASUS H110M-R intel® Core™ i3-6100 Sapphire Radeon RX580 Tahoe Hackintosh OpenCore
---
![OpenCore](https://img.shields.io/badge/OpenCore-1.0.6-blue) ![macOS](https://img.shields.io/badge/macOS-13.7.8-purple) ![macOS](https://img.shields.io/badge/macOS-14.8.3-yellow) ![macOS](https://img.shields.io/badge/macOS-15.7.3-red) ![macOS](https://img.shields.io/badge/macOS-26.3-green)

**⚠️ Disclaimer:**

• Use this EFI as a **starting point**, remember to always make your efi by following [OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)

• Please read the whole readme before proceeding 

• This readme is not yet complete and the efi is not yet complete

• The [Apple Silicon theme](https://github.com/blackosx/BsxM1) for OpenCore is used in the boot picker

---

![IMG_0944](https://github.com/user-attachments/assets/e443574b-f775-4949-9a69-c6dd86543b23)


---

### 🖥️ Hardware

| Component | info |
|-----------|------|
| CPU       | Intel® Core™ i3-6100 |
| RAM       | Kingston 16GB 2133mhz |
| Storage   | AMD 256GB SSD |
| iGPU      | Intel HD Graphics 530 |
| dGPU      | Sapphire AMD Radeon RX580 4GB |
| Audio     | ALC887 – alcid=3 |
| Ethernet  | Realtek Gigabit Ethernet RTL8111H |

---

### ✅️ What works

• dGPU acceleration

• Audio

• HDMI port

• USB ports (Using USBToolBox.kext and UTBDefault.kext)

• Ethernet

• iMessage

---

### ❌️ What doesn't work

• Airdrop (No natively compatible wifi adapter)

---

### ⚙️ Setup

Generating SMBIOS:

Used [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) from corpnewt, to generate a fake serial number, UUID and MLB.

**This step is mandatory to get the device booting and get iServices to work later on**

Download GenSMBIOS from the link above as .ZIP, then extract it.
Start GenSMBIOS and select option `1` to download and install MacSerial
Select option `3` and enter `iMac20,1`
**IMPORTANT**: reminder that you need an **invalid serial!** to check copy and paste the second part saying `Serial: XXXXX..` in [Apple's Check Coverage Page](https://checkcoverage.apple.com/), if you get a red message saying "We're sorry, we're unable to check coverage for this serial number." then you're good to go! Otherwise, go back and restart from step `2` (more info [here](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html#serial-number-validity))
once you get the right serial number you can go and fill the generated data in the config.plist file under `PlatformInfo` section, and you are good to go!

---

### 🔊 Sound

If you are using macOS Tahoe, please note that starting with macOS Tahoe Beta 2, Apple has removed AppleHDA.kext, which means audio will not work with AppleALC.kext. You can use [VoodooHDA.kext](https://github.com/chris1111/VoodooHDA-Tahoe?ysclid=mktj2hj8pg227179981) directly in the system or apply [OpenCore Legacy Patcher 3.0.0](https://github.com/dortania/OpenCore-Legacy-Patcher/actions/runs/19810638271) to add AppleHDA.kext back into the system.

---

**not completed yet...**
