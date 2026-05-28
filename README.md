# batctrl ⚡

[![Release CI](https://img.shields.io/github/actions/workflow/status/k0d3x8its/batctl/release.yml?style=flat&label=Release%20CI)](https://github.com/k0d3x8its/batctl/actions/workflows/release.yml)

A lightweight Linux CLI utility to control battery charge limits (e.g. 60%–100%), persist settings across reboot, and restore state automatically using systemd.

Designed for systems that expose:
  -  `/sys/class/power_supply/BAT*/charge_control_end_threshold`

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
sudo dpkg -i batctrl_v1.0.0_beta.deb
```
Fix dependencies if needed:
```bash
sudo apt-get install -f
```
## 🧠 Usage

### Set battery limit

conducted in increments of 10
```bash
sudo batctrl -60
sudo batctrl -70
sudo batctrl -80
```

### Show current limit

```bash
sudo batctrl --current
# or

sudo batctrl -c
```

### Toggle between 80% <---> 100%

```bash
sudo batctrl --toggle
# or

sudo batctrl -t
```
### Help

```bash
batctrl --help
```

## 🔁 Persistence

The last selected battery limit is stored in:
- `/var/lib/bat-limit/last_limit`

On reboot, a systemd service automatically restores it:
- `bat-limit.service`

## ⚙️ systemd Service

Installed at:
- `/etc/systemd/system/bat-limit.service`

Enable manually (if needed):
- `sudo systemctl enable bat-limit.service`
- `sudo systemctl start bat-limit.service`

Check status:
- `systemctl status bat-limit.service`

## 📁 Project Structure

```bash
batctrl/
├── DEBIAN/
│   ├── control
│   ├── postinst
│   ├── prerm
├── usr/
│   └── local/
│       └── bin/
│           └── batctrl
├── etc/
│   └── bash_completion.d/
│         └── batctrl
```
