# AudioToggle - One keyboard hotkey to toggle between audio devices

AudioToggle is a Windows utility for switching between audio devices using customizable global hotkeys.

## Features

- 🎧 **Quick Device Switching**: Switch between audio devices with a single hotkey
- ⚙️ **Customizable Hotkeys**: Set your own key combination
- ✅ **Device Selection**: Choose which devices to cycle through
- 🔄 **Switch Notification**: Notification of what the default is when changed via the hotkey
- 🚀 **Windows Startup**: Run at windows startup option.

## System Requirements

- **OS**: Windows 10 version 1809 or later
- **Memory**: ~50MB RAM
- **Storage**: ~33MB for installation

## Installation

Preferred: download and run `AudioToggle_Setup_v{version}.exe` from release assets.

- The installer places AudioToggle in your user profile (`%LocalAppData%\\Programs\\AudioToggle`).
- Running a newer installer upgrades the existing installation in place.

Portable option: unzip `AudioToggle_Windows_v{version}.zip` anywhere you keep your apps/utilities and run the exe.

### Windows Compression Dependency (Equalizer APO)

Compression on Windows requires Equalizer APO.

- The AudioToggle installer includes a post-install option to install Equalizer APO.
- By default this opens the official SourceForge download page.
- Maintainers can optionally bundle a local Equalizer APO installer during release packaging.

#### Maintainer: optional bundled Equalizer APO installer

```powershell
scripts/build-release.ps1 -EqualizerApoInstallerPath "C:\path\to\EqualizerAPO-x64-*.exe"
```

Compliance note:

- Equalizer APO is listed as GNU GPL v2.0 on SourceForge.
- Redistribution is typically allowed under GPL terms, but if you bundle third-party binaries, include required notices and provide corresponding source access as required.
- If unsure, use the default download-link flow.

### First Time Setup
2. **Select Devices**: Check the audio devices you want to cycle through
3. **Set Hotkey**: Click in the hotkey box and press your desired key combination **Default Hotkey**: Ctrl+F1
4. **Save**: Settings are automatically saved

### Basic Usage
1. Press your configured hotkey (default: Ctrl+F1)
2. Audio switches to the next enabled device in the list
3. Green checkmark shows current default device in settings

### Settings Window
- **Audio Devices Tab**: Select which devices to include in cycling
- **Hotkeys Tab**: Customize hotkey combinations
- **General Tab**: Application preferences and about information

### Hotkey Combinations
Supported modifiers: Ctrl, Alt, Shift, Win
Supported keys: F1-F12, A-Z, 0-9, Space, Enter, etc.


