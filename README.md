MIDI-ANALYSER-BLE — Firmware

An 8-in-1 MIDI diagnostic and utility tool built around the ESP32: live message analyser, raw byte viewer, clock/BPM meter, per-channel monitor, note histogram, CC scope, CC auto-learn, and settings — all on a 160×128 colour TFT. This repo hosts the firmware and a one-click browser-based installer — no Arduino IDE required.

Install or update firmware

👉 Open the installer


Connect the device to your computer via USB
Open the link above in Chrome, Edge, or Opera
Click Connect, choose the correct serial port, then click Install


That's it — no drivers or software to install beyond your browser.


⚠️ Not supported in Safari or Firefox (no Web Serial support).



MIDI input modes

The device supports two MIDI input sources:

ModeHow to boot into itDIN MIDI (default)Power on normallyBLE MIDIHold button C while powering on

The intro screen and a short banner confirm which mode is active at boot. In BLE mode, the device advertises as MB_ANALYSER — pair to it from your MIDI source. Every app (Analyser, Raw View, Clock Meter, Monitor, Histogram, CC Scope/Learn) works identically regardless of which MIDI source is active.

Apps (cycle with button C)


Analyser — scrolling/step/filtered event log with channel activity + velocity
Raw View — hex/binary/decoded views, byte rate, SysEx capture
Clock Meter — BPM, sparkline, beat indicator, jitter stats
MIDI Monitor — per-channel note/volume/pitch-bend dashboard
Note Histogram — note-on counts across 12 semitones
CC Scope — live graph of a selected CC
CC Learn — auto-detect and scope any CC or pitch-bend
Settings — brightness, channel-activity timing, reboot
