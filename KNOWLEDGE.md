# batctrl Knowledge

> Curated facts about this project.
> Promoted via /checkpoint or /remember.

---

- batctrl power indicator design settled (2026-06-20): Approach A — GNOME Shell Extension (GJS), flush-left of stock GNOME battery icon, live power readout (`-3.2W`/`+15.0W`), click-to-open dropdown with time-to-charge estimates at all thresholds. AppIndicator and hybrid approaches rejected (can't position near battery icon). Design doc at `docs/brainstorm/menu-bar-power-indicators-2026-06-20.md`.
- GNOME Shell 46.0 target for the batctrl extension. `Main.panel._rightBox.insert_child_at_index()` is semi-private API — may need a different approach on future GNOME versions.
