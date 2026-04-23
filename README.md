# batctrl ⚡

A lightweight Linux CLI utility to control battery charge limits (e.g. 60%–100%), persist settings across reboot, and restore state automatically using systemd.

Designed for systems that expose:
    `/sys/class/power_supply/BAT*/charge_control_end_threshold`

---

## 🚀 Features

- Set battery charge limit (60–100%)
- Quick shortcuts:
  - `-c` / `--current` → show current limit
  - `-t` / `--toggle` → toggle between 80% and 100%
- Persistent state across reboot
- systemd service auto-restores last value
- Bash completion support
- Root-protected execution (requires sudo)

---

## ⚠️ Requirements

- Linux (kernel with charge control support)
- systemd
- sudo access
- Battery device exposed under `/sys/class/power_supply/`

---

## 📦 Installation (Debian package)

```bash
sudo dpkg -i batctrl_1.0.0.deb
