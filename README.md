# Bed-Slinger 3D Printer Built from Industrial Components

> **Documentation only.** This repository documents a one-off, self-built 3D printer. It is **not** a build guide,
> and it is not meant to be reproduced. Licensed under [CC BY-NC-ND 4.0](LICENSE.md).

🇩🇪 **Kurzfassung:** Dokumentation eines selbstgebauten 3D-Druckers (Bedslinger, Klipper) aus Industriekomponenten:
Bosch-Rexroth-Profile und -Führungen, Industrie-Schaltschrank, massiver Aufbau (ca. 80 kg). Der Bau war nur dadurch
wirtschaftlich möglich, dass ein Großteil der Industrieteile bereits vorhanden war. Dieses Repo dient ausschließlich der
Dokumentation, nicht dem Nachbau. Lizenz: CC BY-NC-ND 4.0 (Namensnennung, nicht kommerziell, keine Bearbeitung).

<!-- ![Front view](docs/images/overview-front.jpg) -->
*Photo coming soon: overall view.*

---

## Overview

A Cartesian bed-slinger with a heavy, rigid aluminium frame, Bosch Rexroth linear guides on every axis and a
Klipper-based control system housed in an industrial control cabinet. The focus is on mechanical rigidity, a stable
bed and a stable extruder, rather than on minimal moving mass.

| | |
|---|---|
| Name / model | Custom build |
| Manufacturer | Custom build |
| Kinematics | Bed-slinger (Cartesian) |
| Firmware | Klipper |
| UI | KlipperScreen on a Raspberry Pi touchscreen, plus Mainsail |
| Weight | approx. 80 kg |

## Background and economics

Most of the structural and electrical components are industrial parts from surplus stock. They were provided by my
father, who has 20 years of experience in industry. His contribution was **theory consulting at extremely difficult
points and donated industrial components**. The design, construction and implementation were done by me.

**The project was only economical because of these donated parts.** Bought new, the same set of components would cost a
very large amount of money, so rebuilding this printer from new parts makes no economic sense. Apart from the donated
parts, I spent roughly 200 € on additional materials. For the same reason, the component selection is partly
dictated by what was available and not by what would be ideal.

## Design decisions

- **Bed-slinger instead of CoreXY.** A CoreXY would be the better kinematic choice. I did not have enough linear
  guides to build one, so I built a bed-slinger with the guides that were available.
- **Mass and rigidity over low moving mass.** The priority was a stable heated bed and a stable extruder. The
  higher inertia of the heavy bed and printhead is a known trade-off, which is addressed with stiff guides and
  stronger motors rather than by reducing mass.
- **Vibration isolation by mass.** The machine weighs approx. 80 kg, stands on rubber feet and sits on a very rigid
  workbench. Each axis runs on a 15 mm Bosch Rexroth guide.
- **Consistent over-engineering.** Components are dimensioned considerably stronger than strictly necessary. All
  brackets are machined from thick aluminium.

## Specifications

### Frame and enclosure

| | |
|---|---|
| Frame | Bosch Rexroth 45 × 45 aluminium profiles |
| Brackets | Machined from thick aluminium |
| Outer dimensions | 460 × 550 × 550 mm |
| Enclosure | Yes – Macrolon (polycarbonate) and Aludibond panels |
| Insulation | Planned: fixed on opaque panels (floor, lid, rear wall), removable on transparent side panels. Still to be drawn in CAD and installed |
| Chamber heater | Planned; target: sufficient for PC-CF / PA6-CF |
| Feet | Rubber |

### Motion

| | |
|---|---|
| Motors | 5 stepper motors: X, Y, 2× Z, extruder (both Z motors run on a single driver) |
| Guides | Bosch Rexroth industrial linear guides, 15 mm, on all axes |
| Belts | GT2, 6 mm |
| Z drive | TR8 × 1.5 lead screws |
| Endstops | Mechanical |
| Configured limits | `max_velocity` 1000 mm/s, `max_accel` 20000 mm/s² (configured limits, not measured values) |

### Hotend, extruder and bed

| | |
|---|---|
| Extruder | Direct drive, dual gear, custom design |
| Hotend | Volcano, up to 300 °C |
| Nozzle | Interchangeable (brass / hardened steel / steel) |
| Heated bed | Ender 5 heated bed, 24 V, 220 W, up to 130 °C |
| Bed size | 235 × 235 mm (extendable) |
| Build surface | PEI spring steel sheet on glass |
| Bed probe | None installed yet |

### Cooling

| | |
|---|---|
| Hotend fan | 24 V, 40 mm |
| Part cooling | 2× 24 V 5015 blowers |
| Electronics cooling | None |

### Electronics

| | |
|---|---|
| Mainboard | BIGTREETECH SKR Mini E3 V3 |
| Supply | 24 V, 600 W power supply (expandable) |
| Host | Raspberry Pi 3B+ |
| Accelerometer | ADXL345 installed |
| Cabinet | Rittal industrial control cabinet |
<!-- TODO: add further details on cabinet wiring and protection -->

<!-- ![Control cabinet](docs/images/control-cabinet-inside.jpg) -->
*Photo coming soon: control cabinet.*

### Software and connectivity

| | |
|---|---|
| Firmware / stack | Klipper, Moonraker, Mainsail, KlipperScreen, Crowsnest |
| Slicer | OrcaSlicer |
| Network | LAN + Wi-Fi |
| Remote access | Tailscale |
| Camera | 720p USB webcam |
| Filament sensor | None |
| Filament dryer | Yes |
| Materials | Everything except exotic materials; PA6-CF / PC-CF planned after upgrades |

## Images

| | |
|---|---|
| Linear guides and drives | *coming soon* <!-- ![Guides and drives](docs/images/linear-guides-drives.jpg) --> |
| Current printhead | *coming soon* <!-- ![Printhead](docs/images/printhead-current.jpg) --> |
| CAD (Autodesk Inventor) | *coming soon* <!-- ![CAD](docs/images/cad-render.png) --> |
| Heated bed and mount | *in progress* |
| Test print | *after completion* |
| Mainsail during a print | *after completion* |

## Status

| State | Items |
|---|---|
| Built | Frame, guides and drives on all axes, control cabinet and wiring, Klipper setup, current printhead |
| In progress | Finishing mechanical build, heated bed mount |
| Planned | Chamber heating (designed in CAD, not built yet), enclosure insulation (still to be drawn in CAD and installed), upgraded printhead and probing system (designed in CAD, not built yet) |

## Performance and validation

No measurements yet. They will be added after the build is finished.

| Metric | Value | Status |
|---|---|---|
| Configured limits | 1000 mm/s / 20000 mm/s² | From `printer.cfg` |
| Maximum tested speed | TBD | Pending |
| Maximum tested acceleration | TBD | Pending |
| Resonance / input shaping | TBD | Not configured yet |
| Bed temperature stability | TBD | Pending |
| Bed flatness / mesh | TBD | Pending |
| Chamber temperature | TBD | Pending |
| Test prints | TBD | Pending |

## Repository contents

| Path | Content |
|---|---|
| `cad/` | STEP export of the printer *(coming soon)* |
| `config/` | Klipper / Moonraker / Crowsnest / KlipperScreen configuration (sanitized) |
| `electrical/` | Wiring diagram, EPLAN PDF export *(coming soon)* |
| `docs/images/` | Photos and renders |

## Safety notice

The printer and its control cabinet run on mains voltage. This repository is a description of one machine, not
instructions. Nothing here is a recommendation or safety-approved design. Use of any information is at your own risk.

## License

Licensed under [Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0)](LICENSE.md).
