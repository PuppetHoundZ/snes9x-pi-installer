# SNES9X Manager for Raspberry Pi 4

A self-contained manager script that compiles the latest `snes9x-gtk` from source and applies pre-tuned performance configurations specifically optimized for the Raspberry Pi 4 hardware profile.

## Features
* **Optimized Source Compilation:** Builds SNES9X-GTK 1.63 from source using targeted Pi 4 compiler flags (`-O3 -mcpu=cortex-a72`) for native Wayland EGL performance via +rpt Mesa.
* **Pre-Tuned Configuration:** Generates a fully optimized configuration file on deployment (Frame Skip = 0, Vsync ON, OpenGL backend pre-configured) for out-of-the-box 60 FPS gameplay.
* **PipeWire Native Alignment:** Configured to map audio through the PulseAudio shim, allowing the emulator to run smoothly alongside concurrent tools like Cava or Shairport Solace.
* **Direct Desktop Integration:** Installs a clean desktop shortcut linking directly to the native binary.
* **Fault-Tolerant Installer:** Features crash recovery and compilation rollback protections via internal installation marker tracking.
* **Safe Uninstallation:** Clean removal removes application infrastructure and binaries but never touches your stored ROM files.

## Installed Infrastructure
* `~/.local/bin/snes9x-gtk` — Compiled emulator binary
* `~/.config/snes9x/snes9x.conf` — Tuned runtime configuration file
* `~/.local/share/` — Desktop shortcut and application icon assets

## Prerequisites & Requirements
* **OS:** Raspberry Pi OS Trixie (Debian 13) arm64 running the default `labwc` Wayland compositor.
* **Audio Server:** PipeWire (standard default on Trixie).
* **Storage:** ~400 MB free disk space required during compilation (~250 MB is automatically reclaimed post-build).
* **Network:** Internet connection required for the initial codebase fetch and dependency resolution.

## References & Documentation
* [Source](https://github.com/snes9xgit/snes9x)
* [Compiling](https://github.com/snes9xgit/snes9x/wiki/Compiling)
* [License](https://github.com/snes9xgit/snes9x/blob/master/LICENSE)

> **License Note:** Snes9x is freeware for PERSONAL USE only (non-commercial).
## Credits & Upstream Sources
This installer builds [snes9x](https://github.com/snes9xgit/snes9x) from source.
Snes9x is freeware for personal, non-commercial use only — commercial use
requires permission from the copyright holders (see the project's LICENSE
file for full terms). This installer script is independently authored and
MIT-licensed; it is not affiliated with the Snes9x team.


## Usage

Do **NOT** run this script as root or via `sudo`. Execute it directly within your user environment:

```bash
chmod +x snes9x-manager.sh
./snes9x-manager.sh

