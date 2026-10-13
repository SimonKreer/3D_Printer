# Klipper configuration (documentation copy)

These files show how the printer is configured. They are **not** a ready-to-flash setup.

| File | Purpose |
|---|---|
| `printer.cfg` | Klipper main config (SKR Mini E3 V3, Cartesian bed-slinger) |
| `moonraker.conf` | Moonraker API / update manager / power devices (lights, printer power) |
| `crowsnest.conf` | Webcam stream (720p USB webcam) |
| `KlipperScreen.conf` | Touchscreen UI settings |

Notes:

- Machine-specific IDs (MCU serial) are replaced by `<PLACEHOLDERS>`.
- `printer.cfg` includes `mainsail.cfg`. That file comes from the upstream project
  [mainsail-config](https://github.com/mainsail-crew/mainsail-config) (GPLv3) and is therefore **not** included here.
- `max_velocity: 1000` and `max_accel: 20000` are **configured limits**, not measured performance.
- Input shaping / resonance testing is not part of the published configuration.
- Bed probing / nozzle probing is not part of the published configuration (not installed yet).
- The configuration files are covered by the repository license (CC BY-NC-ND 4.0).
- Third-party software (Klipper, Moonraker, Crowsnest, KlipperScreen, Mainsail) keeps its own licenses.
