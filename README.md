# Pneumatic Sheet-Bending Machine — Sequential (Electro-Pneumatic) Control

Design and build of a **3-cylinder pneumatic sheet-metal bending machine** with a **classical electro-pneumatic step-sequence controller**, fully modelled in **SolidWorks** and operated as working hardware.

> Full mechatronic loop: mechanical design → pneumatic circuit → sequential control logic → built and operated machine.

---

## Problem

Sheet-metal bending needs the workpiece clamped, then bent on two axes in a fixed, repeatable order. The goal was a low-cost machine that mirrors its industrial counterpart — functional, safe, and repeatable — using pneumatic actuation and classical sequential control.

## Machine concept

Three pneumatic cylinders, sequenced:

1. **Cylinder A — clamp** the sheet to the base
2. **Cylinder B — bend in the Y-axis**, then retract
3. **Cylinder C — bend in the X-axis**
4. **Cylinder A — unclamp**; part removed

The result is a sheet bent 6 cm in Y and 6 cm in X, with **spring-back compensation** designed into the base for true 90° bends.

## Key specifications

| Item | Value |
|------|-------|
| Workpiece | 300 × 150 × 1 mm steel sheet |
| Clamped length (on base) | 180 mm |
| Bend per axis | 60 mm |
| Cylinder A / B stroke | 100 mm |
| Cylinder C stroke | 200 mm |
| Base plate | 180 × 250 × 60 mm |
| End effectors | gap = sheet thickness, for clean bends |

## Approach

- **Mechanical design** — complete SolidWorks assembly (frame, three cylinders, end effectors, base) with exploded view and an engineering BOM.
- **Pneumatic circuit** — designed and simulated the actuation circuit (directional valves, sequencing) in **FluidSIM**.
- **Sequential control** — implemented the classical **step (cascade) sequence** A→B→C→A so each motion completes before the next begins, with end-position confirmation.
- **Build & commissioning** — assembled the hardware and ran the full bend cycle.

## Tech stack

`SolidWorks` · `FluidSIM` · electro-pneumatics · classical sequential (step/cascade) control

## Repository contents

- `/cad` — SolidWorks parts, assembly, exploded view, BOM
- `/pneumatics` — FluidSIM circuit and step diagram
- `/docs` — project report, 2D dimensioned drawings

## Demo

https://github.com/user-attachments/assets/$(REPLACE_WITH_VIDEO_ASSET_ID)

> Replace the line above with the actual GitHub-hosted video asset URL after uploading `Bending machine vod.mp4` via a GitHub issue or release.

## Results & figures

- [ ] Add a photo/GIF of the machine completing a full bend cycle
- [ ] Add the FluidSIM step diagram and the pneumatic schematic
- [ ] Add a render of the SolidWorks assembly

---

*Course: Mechatronics Lab (MCTR704), German University in Cairo.*
