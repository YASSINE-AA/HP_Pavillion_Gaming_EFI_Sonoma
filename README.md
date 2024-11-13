
# macOS Sonoma on HP Pavilion Gaming Laptop

This repository provides a comprehensive guide and configuration files for installing and running macOS Sonoma on an HP Pavilion Gaming laptop.

## Hardware Specifications

- **Model**: HP Pavilion Gaming Laptop 15-ec1xxx
- **Memory**: 24.0 GiB
- **Processor**: AMD Ryzen 7 4800H with Radeon Graphics x16
- **Graphics**: AMD Radeon Graphics, NVIDIA GeForce GTX 1660 Ti with Max-Q Design

## Requirements

- **macOS Sonoma installer** (available from the Mac App Store or using macrecovery.py, see instructions below)
- **Config.plist file** (provided in this repository)
- **OpenCore Bootloader** (v0.9.4 or newer)
- **USB drive** with at least 16GB of storage

## Features Supported

- iGPU (integrated GPU) graphics
- Trackpad and Keyboard support
- Battery management
- USB ports and peripherals

## Known Limitations

- **Wi-Fi**: The internal Realtek RT8822CE Wi-Fi card is **not supported**. Consider using an external USB Wi-Fi adapter compatible with macOS.
- **Discrete GPU**: The GTX 1660Ti is **not supported** in macOS. Consequently, the **HDMI port will not work** for external displays. For external displays, use a **USB-C to HDMI adapter** to connect via the integrated GPU (iGPU).

## Important Disclaimer

For successful installation, it is crucial to **boot into recovery with WhateverGreen enabled**. Avoid using NootedRed to prevent black screen issues.

## Preparation

1. **Backup Important Data**: Ensure your data is backed up before starting, as this process may result in data loss.
2. **Create macOS Installer USB on Windows** (using macrecovery.py):
   - Download [OpenCorePkg](https://github.com/acidanthera/OpenCorePkg) and navigate to `/Utilities/macrecovery/`.
   - Open a Command Prompt in this directory by clicking next to the folder path and typing `cmd`.
   - Run the following command to download the Sonoma installer (requires Python 3):

     ```
     py macrecovery.py -b Mac-226CB3C6A851A671 -m 00000000000000000 download
     ```

   - This will download the BaseSystem or RecoveryImage files required to create a bootable installer.

## Installation

1. **Boot from USB**:
   - Insert the USB installer and restart your laptop.
   - Press `F9` during boot to access the boot menu and select the USB drive.
2. **Install macOS Sonoma**:
   - Follow the on-screen instructions to install macOS Sonoma.
   - Once installed, use the same USB to boot into macOS and complete initial setup.

## Post-Installation

1. **Copy OpenCore to Internal Drive**:
   - Mount your EFI partition and copy the OpenCore EFI folder to the internal drive.
2. **Adjust Display Settings**:
   - For optimal performance, configure the display and resolution settings.

## Troubleshooting

- **Black screen during boot**: Verify the `config.plist` and ensure proper SMBIOS settings.
- **No audio**: Ensure the correct layout ID is used in `config.plist`.

## Additional Resources

- [OpenCore Documentation](https://dortania.github.io/OpenCore-Install-Guide/)
- [WhateverGreen Documentation](https://github.com/acidanthera/WhateverGreen)

## Disclaimer

Installing macOS on non-Apple hardware is not supported by Apple. This project is for educational purposes only.
