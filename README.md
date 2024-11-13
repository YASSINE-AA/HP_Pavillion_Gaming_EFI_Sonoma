
# macOS Sonoma on HP Pavilion Gaming Laptop

This repository provides a comprehensive guide and configuration files for installing and running macOS Sonoma on an HP Pavilion Gaming laptop.

## Requirements

- **HP Pavilion Gaming Laptop**
- **macOS Sonoma installer** (available from the Mac App Store)
- **Config.plist file** (provided in this repository)
- **OpenCore Bootloader** (v0.9.4 or newer)
- **USB drive** with at least 16GB of storage

## Features Supported

- Wi-Fi, Bluetooth, Audio, and Graphics
- Trackpad and Keyboard support
- Battery management
- USB ports and peripherals

## Known Limitations

- **Wi-Fi**: The internal Realtek RT8822CE Wi-Fi card is **not supported**. Consider using an external USB Wi-Fi adapter compatible with macOS.
- **Discrete GPU**: The GTX 1660Ti is **not supported** in macOS. Consequently, the **HDMI port will not work** for external displays. For external displays, use a **USB-C to HDMI adapter** to connect via the integrated GPU (iGPU).

## Preparation

1. **Backup Important Data**: Ensure your data is backed up before starting, as this process may result in data loss.
2. **Create macOS Installer USB**:
   - Download macOS Sonoma from the Mac App Store.
   - Use `createinstallmedia` to create a bootable USB installer.
3. **Download and Configure OpenCore**:
   - Download the latest OpenCore bootloader.
   - Replace the `config.plist` in the OpenCore `EFI` folder with the one provided in this repository.

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

## Disclaimer

Installing macOS on non-Apple hardware is not supported by Apple. This project is for educational purposes only.
