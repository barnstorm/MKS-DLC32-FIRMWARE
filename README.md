# MKS-DLC32-FIRMWARE
The source code of MKS DLC32.

## 🔧 Fork Improvements

This fork adds the following enhancements to the original MKS DLC32 firmware:

### ✨ Runtime Laser/CNC Mode Switching via `$32`

**No more reflashing to switch between laser and CNC modes!**

- The PWM spindle now respects the standard GRBL `$32` (Laser Mode) setting
- Toggle between modes at runtime: `$32=0` (CNC) / `$32=1` (Laser)
- When `$32=1`: Enables laser-specific behavior (no spinup delays, dynamic power modulation, M4 support)
- When `$32=0`: Standard CNC spindle behavior with spin-up/down delays
- Works with LightBurn, LaserGRBL, UGS, and other GRBL senders
- Single unified firmware for both use cases

### 🐛 Bug Fixes

- **CoreXY Build**: Added missing `DEFAULT_BEEP_STATUS` and `DEFAULT_LANGUAGE_STATUS` defines
- **CoreXY Build**: Fixed partition file reference to use standard `huge_app.csv`
- **UI Language**: Fixed language initialization using assignment (`=`) instead of comparison (`==`)
- **UI Language**: Defaulted all languages to English (Chinese/German strings not yet implemented)

## Environment construction:

- vscode

- platformIO

PlatformIOc needs to be installed on vscode.

Open Firmware with vscode, and platformIO will be started, In the platform.ini file，

`default_envs = mks_dlc32_v2_1` 

Note:We will make a pin suitable for V1.0，Settings corresponding to the selection of coreXY.

Then compile and download.

