# Pneumatic Sheet-Bending Machine — Sequential (Electro-Pneumatic) Control

Design and build of a **3-cylinder pneumatic sheet-metal bending machine** with a **classical electro-pneumatic step-sequence controller**, fully modelled in **SolidWorks** and operated as working hardware.

> Full mechatronic loop: mechanical design → pneumatic circuit → sequential control logic → built and operated machine.

---

## Problem

Sheet-metal bending needs the workpiece clamped, then bent on two axes in a fixed, repeatable order. The goal was a low-cost machine that mirrors its industrial counterpart — functional, safe, and repeatable — using pneumatic actuation and classical sequential control.

## Machine concept

Three pneumatic cylinders, sequenced:

1. **A+** — clamp the sheet to the base
2. **B+** — bend in the Y-axis
3. **C+** — bend in the X-axis (while B is still extended, reducing spring-back)
4. **C−** → **B−** → **A−** — retract in reverse order; part removed

Full sequence: **A+ B+ C+ C− B− A−**

The result is a sheet bent 6 cm in Y and 6 cm in X, with **spring-back compensation** designed into the base for true 90° bends.

## Key specifications

| Item | Value |
|------|-------|
| Workpiece | 300 × 150 × 1 mm steel sheet |
| Clamped length (on base) | 180 mm |
| Bend per axis | 60 mm |
| Cylinder A / B bore × stroke | 20 × 100 mm |
| Cylinder C bore × stroke | 25 × 200 mm |
| Frame | 727 × 850 × 275 mm (wooden) |
| Position sensing | Reed switches (×6, one per cylinder end) |
| Solenoid valves | 5/2 bistable, 24 V DC (×3) |
| Controller | Relay-based step-sequence, 10 relays, 24 V DC |

## Approach

- **Mechanical design** — complete SolidWorks assembly (frame, three cylinders, end effectors) with exploded view and engineering BOM (13 part numbers, 23 line items).
- **Pneumatic circuit** — three 5/2 solenoid valves, one per cylinder, shared supply rail; reed switches A1/A2, B1/B2, C1/C2 confirm end positions.
- **Sequential control** — classical relay step-sequence circuit: each step energises only when the previous end-position reed switch closes, preventing out-of-order actuation.
- **Build & commissioning** — wooden frame assembled, electrical panel wired, full bend cycle demonstrated.

## Tech stack

`SolidWorks` · `FluidSIM` · electro-pneumatics · classical relay step-sequence control

## Documentation

Full project report (SolidWorks renders, exploded view, BOM, pneumatic circuit, step diagram, component list):
**[Bending Machine Report.pdf](Bending%20Machine%20Report.pdf)**

| Report section | Pages |
|---|---|
| 3D SolidWorks renders (4 views) | 4 |
| Exploded view | 5–6 |
| BOM (13 part numbers) | 7 |
| Component list with photos (23 items) | 10–12 |
| Pneumatic circuit diagram | 13 |
| Step diagram + sequence description | 14 |

## Demo

![Full bend cycle demo](Bending%20machine%20vod.mp4)

---

*Course: Mechatronics Lab (MCTR704), German University in Cairo. Winter 2023.*
*Team: Mohammed Ahmed Saeed (52-10194) · Mohamed Hassan Elattar (52-19674), Group 27.*
