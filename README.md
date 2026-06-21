# MIDI-ANALYSER-BLE — Firmware

An 8-in-1 MIDI diagnostic and utility tool built around the ESP32: live message analyser, raw byte viewer, clock/BPM meter, per-channel monitor, note histogram, CC scope, CC auto-learn, and settings — all on a 160×128 colour TFT. This repo hosts the firmware and a one-click browser-based installer — no Arduino IDE required.

## Install or update firmware

👉 **[Open the installer](https://mindburners.github.io/midi-analyser-ble-firmware/)**

1. Connect the device to your computer via USB
2. Open the link above in **Chrome**, **Edge**, or **Opera**
3. Click **Connect**, choose the correct serial port, then click **Install**

That's it — no drivers or software to install beyond your browser.

> ⚠️ Not supported in Safari or Firefox (no Web Serial support).

## MIDI input modes

The device supports two MIDI input sources:

| Mode | How to boot into it |
|---|---|
| **DIN MIDI** (default) | Power on normally |
| **BLE MIDI** | Hold button **C** while powering on |

The intro screen and a short banner confirm which mode is active at boot. In BLE mode, the device advertises as `MB_ANALYSER` — pair to it from your MIDI source. Every app (Analyser, Raw View, Clock Meter, Monitor, Histogram, CC Scope/Learn) works identically regardless of which MIDI source is active.

## Apps (cycle with button C)

1. **Analyser** — scrolling/step/filtered event log with channel activity + velocity
2. **Raw View** — hex/binary/decoded views, byte rate, SysEx capture
3. **Clock Meter** — BPM, sparkline, beat indicator, jitter stats
4. **MIDI Monitor** — per-channel note/volume/pitch-bend dashboard
5. **Note Histogram** — note-on counts across 12 semitones
6. **CC Scope** — live graph of a selected CC
7. **CC Learn** — auto-detect and scope any CC or pitch-bend
8. **Settings** — brightness, channel-activity timing, reboot

## What's in this repo

| File | Purpose |
|---|---|
| `index.html` | The installer page |
| `manifest.json` | Tells the installer where each firmware part goes in flash |
| `bootloader.bin`, `partitions.bin`, `firmware.bin` | The compiled firmware |
| `logo.png` | Branding shown on the installer page |

## Releasing an update

1. In Arduino IDE: **Sketch → Export Compiled Binary**
2. Rename the three exported files to `bootloader.bin`, `partitions.bin`, `firmware.bin`
3. Drag them into this repo, overwriting the existing files
4. Done — the installer link above always serves the latest version

## Hardware

- ESP32-WROOM-32E
- ST7735S 160×128 SPI colour TFT
- 3-button interface (per-app context-sensitive controls)
- just upload latest files and remember to change the version number in manifest.json

---
Mindburner — Alan G. Watkins
