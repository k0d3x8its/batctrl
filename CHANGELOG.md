# Changelog


## [Unreleased]

---

## [1.0.0-beta] - 2026-05-26

### Added
- ➕ `batctrl` CLI script — set battery charge limit via `-60|-70|-80|-90|-100` flags
- ➕ `--current` / `-c` — display current charge limit
- ➕ `--toggle` / `-t` — toggle between 80% and 100%
- ➕ `--help` / `-h` — usage menu
- ➕ Auto-detect battery device under `/sys/class/power_supply/BAT*`
- ➕ State persistence in `/var/lib/bat-limit/last_limit`
- ➕ `bat-limit.service` systemd unit — restores last limit on reboot
- ➕ Bash completion support (`/etc/bash_completion.d/batctrl`)
- ➕ Debian package (`batctrl_v1.0.0_beta.deb`) with `postinst`/`prerm` lifecycle scripts
- ➕ `.gitignore`

### Changed
- ♻️ Renamed project from `batctl` to `batctrl` to avoid conflict with existing Linux tool

### Fixed
- 🛠️ Removed duplicate files from repo

---

## Glossary

| ➕ | ❌ | 🛠️ | 🐞 | 🚀 | ♻️ | 🛡️ | ⚠️ | ⬆️ |
|-------|---------|-------|-----|----------|---------|----------|------------|---------|
| ADDED | REMOVED | FIXED | BUG | IMPROVED | CHANGED | SECURITY | DEPRECATED | UPDATED |
