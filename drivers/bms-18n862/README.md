# S18 — Driver: BMS 18N862

The driver is a modular component of the S18. This page is the hub for the **BMS 18N862** in the S18 sealed enclosure: what it's for, the target it's designed to hit, and where to find its DSP settings and measurements.

## Design goal (read this first)

In the S18 enclosure, the 18N862 is tuned as a **music subwoofer**, designed to ideally work in pairs — crossed **as high as possible (≤ ~80–120 Hz)**. The goal is tactile, high-fidelity low end: chest-slam and grunt with the cone control and low distortion to integrate cleanly with mains.

It is intentionally *not* a high-crossover, directivity-controlled module — a single 18″ beams too early to integrate cleanly above that — and *not* a pure LFE box crossed at 50 Hz. Other targets are possible on the same cabinet; this driver is documented for the music-pair target.

## Target specs

| | |
|---|---|
| **Frequency response** | 20–250 Hz ±3 dB (ground plane), preset-dependent |
| **Typical in-room extension** | ~10 Hz (−3 dB) |
| **Max SPL** (avg 30–80 Hz, 1 m) | ~120 dB |

Extension vs. SPL is set by the DSP preset — see [`/dsp-amp/bms-18n862`](../../dsp-amp/bms-18n862/).

## Alignment in the S18 enclosure

| | |
|---|---|
| **Type** | Sealed, ~115–125 L net |
| **Alignment** | Fc ≈ 47 Hz, **Qtc ≈ 0.64** |

Cabinet design and cut list → [`/enclosure`](../../enclosure/).

## Thiele/Small parameters

⏳ pending — to be published from datasheet + per-unit verification (see the measurements protocol). Per-unit T/S verification is tracked under [`/measurements`](../../measurements/).

## Where to go next

- **DSP settings / EQ presets** for this driver → [`/dsp-amp/bms-18n862`](../../dsp-amp/bms-18n862/)
- **Enclosure** it runs in → [`/enclosure`](../../enclosure/)
- **Measurements** (simulated + measured) → [`/measurements/0-simulation/bms-18n862`](../../measurements/0-simulation/bms-18n862/)
