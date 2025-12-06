---
title: Classic Arch Problem
tags:
    - Arch
draft:
---

If you're running Arch Linux with PipeWire and encounter no sound after a reboot, particularly when only system sounds work in the "Pro Audio" profile, this guide will help you diagnose and fix the issue. This blog post outlines a step-by-step approach to restore audio for applications like browsers and media players, based on a common scenario where the default audio sink is set to `auto_null` or the wrong audio profile is active.

## Understanding the Issue

PipeWire is a modern audio server used in Arch Linux, replacing older systems like PulseAudio or ALSA for many users. However, misconfigurations, such as an incorrect audio profile or default sink, can lead to issues like:
- System sounds working in "Pro Audio" mode but applications (e.g., Firefox, VLC) producing no sound.
- The default sink being set to `auto_null`, a dummy sink that discards audio.
- Missing ALSA test files causing errors like `sndfile: failed to open audio file`.

This guide assumes you have two audio cards:
- **HDA NVidia**: Typically used for HDMI/DisplayPort audio, often set to the `pro-audio` profile.
- **HDA Intel PCH**: Your built-in audio device for analog outputs (speakers, headphones), which may be disabled or misconfigured.

## Step-by-Step Troubleshooting

### 1. Check PipeWire Services
Ensure PipeWire and related services are running:
```bash
systemctl --user status pipewire pipewire-pulse wireplumber
```
If any are inactive, enable and start them:
```bash
systemctl --user enable --now pipewire pipewire-pulse wireplumber
```

### 2. Verify Audio Devices
List available audio devices to confirm your sound cards are detected:
```bash
pactl list cards
```
Check the active profile for each card:
- **HDA NVidia**: If set to `pro-audio`, it may work for system sounds but not consumer applications.
- **HDA Intel PCH**: If set to `off`, no audio will be routed to speakers or headphones.

List available sinks to identify the default:
```bash
pactl list short sinks
```
If the output shows `auto_null` (e.g., `auto_null PipeWire float32le 2ch 48000Hz RUNNING`), this is a dummy sink that discards audio, explaining why applications are silent.

### 3. Switch to the Correct Audio Profile
For the Intel PCH card (built-in audio), enable an analog profile:
```bash
pactl set-card-profile alsa_card.pci-0000_00_1f.3 output:analog-stereo
```
If you need microphone input:
```bash
pactl set-card-profile alsa_card.pci-0000_00_1f.3 output:analog-stereo+input:analog-stereo
```

If no HDMI devices are connected, disable the NVIDIA card to avoid conflicts:
```bash
pactl set-card-profile alsa_card.pci-0000_01_00.1 off
```

### 4. Set the Correct Default Sink
After enabling the Intel PCH profile, list sinks again:
```bash
pactl list short sinks
```
Look for a sink like `alsa_output.pci-0000_00_1f.3.analog-stereo`. Set it as the default:
```bash
pactl set-default-sink alsa_output.pci-0000_00_1f.3.analog-stereo
```

### 5. Test Audio Playback
If you encountered errors like `sndfile: failed to open audio file "/usr/share/sounds/alsa/Front_Center.wav"`, install `alsa-utils`:
```bash
sudo pacman -S alsa-utils
```
Verify the test file exists:
```bash
ls /usr/share/sounds/alsa/
```
Test audio:
```bash
pw-play /usr/share/sounds/alsa/Front_Center.wav
```
Alternatively, play a sample sound:
```bash
pactl play-sample bell
```

### 6. Configure Application Audio
Use `pavucontrol` to check application audio routing:
```bash
pavucontrol
```
- In the **Output Devices** tab, ensure the Intel PCH sink (e.g., "Built-in Audio Analog Stereo") is selected and not muted. If using headphones, select the "Headphones" port.
- In the **Playback** tab, while playing audio (e.g., a YouTube video), ensure applications are routing to the Intel PCH sink, not `auto_null`.

### 7. Adjust ALSA Settings
Check the ALSA mixer to ensure the Intel PCH card is not muted:
```bash
alsamixer
```
- Select the Intel PCH card (press `F6` and choose `HDA Intel PCH`).
- Unmute channels (press `M`) and raise volumes for "Master," "Headphone," and "Speaker."
- Save settings:
  ```bash
  sudo alsactl store
  ```

### 8. Inspect Logs
Check PipeWire and WirePlumber logs for errors:
```bash
journalctl --user -u pipewire
journalctl --user -u wireplumber
```
Look for issues related to the Intel PCH card or sink initialization.

### 9. Reinstall PipeWire and ALSA
If issues persist, reinstall PipeWire and ALSA components:
```bash
sudo pacman -S pipewire pipewire-pulse pipewire-alsa wireplumber alsa-utils
```

### 10. Update Your System
Ensure all packages are up to date:
```bash
sudo pacman -Syu
```

## Additional Tips
- **Headphones vs. Speakers**: If using headphones, ensure the "Headphones" port is selected in `pavucontrol`. If using speakers, verify they’re connected, as they may not be detected.
- **HDMI Audio**: If you want HDMI audio (via the NVIDIA card), connect an HDMI device and set the profile:
  ```bash
  pactl set-card-profile alsa_card.pci-0000_01_00.1 output:hdmi-stereo
  ```
- **Pro Audio Profile**: Avoid `pro-audio` for general use, as it’s incompatible with most consumer applications like browsers.

## Debugging Further
If audio still doesn’t work, collect the following:
- `pactl list short sinks` to verify the active sink.
- `ls /usr/share/sounds/alsa/` to confirm test files are present.
- List of applications with no sound (e.g., Firefox, VLC).
- Errors from `journalctl --user -u pipewire` or `journalctl --user -u wireplumber`.

## Conclusion
By switching the Intel PCH card to an analog profile, setting the correct default sink, and ensuring applications route audio properly, you should restore sound across your system. PipeWire’s flexibility makes it powerful, but profile and sink misconfigurations are common culprits for audio issues. With these steps, your Arch Linux audio setup should be back to normal.
