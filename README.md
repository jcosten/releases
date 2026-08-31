# Releases

Downloads for my apps. Each project publishes its installers here as a GitHub
Release — grab the latest from the [Releases page](../../releases), or read on
for what each one does.

| App | What it is | Windows | Linux |
| --- | --- | --- | --- |
| [Ruze Chat](#ruze-chat) | Peer-to-peer chat and voice, with no server | Installer | Flatpak |
| [AudioToggle](#audiotoggle) | One hotkey to switch audio devices | Installer | Flatpak |

Releases are tagged per project, so `ruze-chat-v0.0.5` and `v1.7.1` can sit in
the same repo without colliding.

---

# Ruze Chat

**Peer-to-peer, serverless chat.** Servers, channels, voice and everything in
them live on the machines of the people using them. There is no backend to sign
up for, pay for, or wait on when it goes down — because there isn't one.

A "server" here is a replicated document that every member holds a full copy
of. When two members are online they sync directly with each other; when
nobody is online, nothing is lost, it just waits. Someone can hand out an
invite and go to bed, and the person joining still gets the whole history from
whoever else happens to be around.

## What it does

**Chat**

- Text channels, with editing and deleting your own messages
- Emoji reactions, and an emoji picker that works offline — no CDN call on
  first open
- File attachments by button or drag-and-drop, with images and video shown
  inline and a lightbox to open them
- Link previews, and a GIF picker for the rest
- Member profiles — click anyone's name or picture to see who they are and
  whether you're connected to them directly

**Voice**

- Real-time voice channels alongside the text ones
- Echo cancellation and noise suppression, both on by default, so nobody hears
  themselves back through your speakers
- Voice activation that sets its own threshold from the room and follows it,
  or a manual level you place yourself against a live meter
- Input volume, for a microphone that is quieter than it should be
- Pick your microphone and speakers, and test both before you join anything

**Running it**

- Invite someone with a ticket you paste to them — no accounts, no email, no
  phone number
- Optional sync-host mode binds a fixed, forwardable port and starts with your
  machine, so one always-on computer can keep a server reachable

## Install

**Windows** — download `ruze-chat_{version}_x64-setup.exe` from the
[latest release](../../releases) and run it.

**Linux** — download `ruze-chat-{version}.flatpak` and install it:

```bash
flatpak install ruze-chat-{version}.flatpak
flatpak run com.ruze.chat
```

The bundle carries the app; Flatpak fetches the GNOME runtime it needs from
Flathub the first time. Linux builds start at v0.0.6.

## Good to know

It is early software — the version numbers are honest about that — and there
are a couple of design consequences worth understanding before you rely on it:

- **An invite is a key, not a request.** Anyone holding one can read and write
  the server, and it can't be revoked afterwards. Removing a member stops them
  being seen or heard, but if you need to genuinely lock someone out, make a
  new server.
- **Traffic between peers is encrypted, and no server holds a copy** — but
  every member's machine holds a full copy of the history, which is what makes
  the offline-and-catch-up behaviour work.
- **Someone has to be online to sync with.** Two people who are never online at
  the same time will never exchange messages, with or without a host.

---

# AudioToggle

**One keyboard hotkey to toggle between audio devices.** A Windows utility for
switching between audio devices using customizable global hotkeys.

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

- The installer places AudioToggle in your user profile (`%LocalAppData%\Programs\AudioToggle`).
- Running a newer installer upgrades the existing installation in place.

Portable option: unzip `AudioToggle_Windows_v{version}.zip` anywhere you keep your apps/utilities and run the exe.

On Linux, install `AudioToggle_Linux_Flatpak_v{version}_amd64.flatpak` with `flatpak install`.

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

## Usage

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
