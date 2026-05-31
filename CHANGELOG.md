# Changelog


## [Unreleased]

---

## [1.0.0] - 2026-05-30

### Added
- ➕ CI release pipeline (`.github/workflows/release.yml`) — tag-triggered `.deb` build and GitHub draft release with artifact attached
- ➕ Release CI status badge in `README.md`

### Changed
- ♻️ Battery auto-detection uses `find` instead of `ls | grep` — more reliable across kernel versions

### Fixed
- 🛠️ Fail fast on hardware write rejection via `set -e`
- 🛠️ `prerm` now stops `bat-limit.service` before disabling — cleaner uninstall
- 🛠️ Bash completion now completes `-h`, `-c`, `-t`
- 🛠️ Corrected Debian package description

### Verified
- 🚀 Smoke-tested on real hardware (BAT0, `charge_control_end_threshold`): all set flags `-60/-70/-80/-90/-100`, `-c`, `-t`, `-h`, invalid-input rejection, state persistence, and reboot restore via `bat-limit.service` — 18/18 pass

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
