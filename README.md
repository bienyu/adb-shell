# Android Configuration via ADB

A collection of ADB shell commands to optimize and configure Android devices, specifically tailored for Samsung Galaxy devices (One UI).

## Features
- **UI Optimization**: Speed up or disable animations.
- **Battery & Power**: Disable adaptive battery, toggle power saving, and manage RAM Plus.
- **Network**: Force specific network types (4G/5G) and manage VoLTE.
- **App Management**: Whitelist apps from background restrictions (Never Sleep) and restrict others.
- **Debloat & Privacy**: Disable Samsung Customization Service, Samsung Free, and diagnostic data.

## Files
- `adb_shell_lists.md`: A comprehensive reference list of ADB commands with descriptions.
- `my_samsung_setup.md`: A ready-to-use setup script for personal device configuration.

## Usage
1. Enable **Developer Options** and **USB Debugging** on your Android device.
2. Connect your device to your computer.
3. Open a terminal and run the desired commands from the files.
4. For commands involving RAM Plus or system services, a **reboot** is usually required.

---
*Disclaimer: Use these commands at your own risk. Modifying system settings via ADB can impact device stability.*
