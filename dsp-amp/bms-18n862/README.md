# S18 — DSP settings: BMS 18N862

DSP settings for the **BMS 18N862** in the S18 sealed enclosure. These are the **source of truth** — amp-agnostic target curves. For ready-to-load files on a specific amp, see [`hypex/`](hypex/) (or apply the biquads on your own DSP).

For the driver's design target and specs, see the driver hub → [`../../drivers/bms-18n862`](../../drivers/bms-18n862/).

## The three presets

Three presets, trading low-frequency extension against maximum SPL. Each pairs a **Linkwitz-style PEQ boost at 20 Hz** (to extend the sealed roll-off) with a **Butterworth high-pass** that sets the excursion limit and protects the driver.

### S18 Deep — maximum extension
Lowest reach, lowest max SPL. For smaller rooms, or when you want the bottom octave over loudness.

| | |
|---|---|
| **High-pass** | 15 Hz · Butterworth · 24 dB/oct |
| **PEQ** | 20 Hz · +15.0 dB · Q 1.6 |
| **Simulated (ground plane)** | F3 20.4 Hz · F6 ~18 Hz · F10 16.1 Hz |
| **Max SPL (sim)** | 106.4 dB |
| **Ground plane (measured)** | ⏳ pending |
| **In-room (measured)** | ⏳ pending |

### S18 — balanced (default)
The all-rounder: sensible extension with healthy headroom.

| | |
|---|---|
| **High-pass** | 20 Hz · Butterworth · 24 dB/oct |
| **PEQ** | 20 Hz · +10.5 dB · Q 1.1 |
| **Simulated (ground plane)** | F3 29.8 Hz · F6 ~25 Hz · F10 19.8 Hz |
| **Max SPL (sim)** | 114.0 dB |
| **Ground plane (measured)** | ⏳ pending |
| **In-room (measured)** | ⏳ pending |

### S18 Loud — maximum output
Loudest, rolls off earliest. For larger rooms, or when you want SPL over the last octave.

| | |
|---|---|
| **High-pass** | 30 Hz · Butterworth · 24 dB/oct |
| **PEQ** | 20 Hz · +10.0 dB · Q 1.3 |
| **Simulated (ground plane)** | F3 37.7 Hz · F6 ~32 Hz · F10 26.2 Hz |
| **Max SPL (sim)** | 120.0 dB |
| **Ground plane (measured)** | ⏳ pending |
| **In-room (measured)** | ⏳ pending |

### Summary

| Preset | High-pass (BW, 24 dB/oct) | PEQ @ 20 Hz | F3 sim (Hz) | F6 sim (Hz)* | F10 sim (Hz) | Max SPL (sim) | F3 ground plane (meas.) | F3 in-room (meas.) |
|---|---|---|---|---|---|---|---|---|
| **S18 Deep** | 15 Hz | +15.0 dB, Q 1.6 | 20.4 | ~18 | 16.1 | 106.4 dB | | |
| **S18** | 20 Hz | +10.5 dB, Q 1.1 | 29.8 | ~25 | 19.8 | 114.0 dB | | |
| **S18 Loud** | 30 Hz | +10.0 dB, Q 1.3 | 37.7 | ~32 | 26.2 | 120.0 dB | | |

\* F3 and F10 are read from the simulation; F6 is interpolated between them. Ground-plane and in-room columns are ⏳ pending measurement.

### Ground plane vs in-room

The figures above are **simulated ground-plane** (anechoic/electrical) targets. In a real room, **room gain** lifts the bottom octave further — typical usable **in-room extension is ~10 Hz (−3 dB)**. So the right preset depends on your room's gain as much as taste. HFDs are pure software presets, so we'll follow up with measurements and iterate here :)

## The files

- **Hypex FA502 HFD presets** → [`hypex/`](hypex/)
- The EQ settings above are the source of truth; per-preset target curves + full biquad allocation → ⏳ pending.
- **Bring your own DSP:** apply the high-pass + PEQ above on your platform.
- Crossover is **user-set upstream** in the processor/pre-amp; nothing is baked into the DSP.

## Protection — do not disable

The onboard limiter is the safety-critical part of this design. Because room EQ runs *upstream*, the amp must survive whatever you feed it — a single null-fill boost can otherwise bottom the driver. (See the [DSP & amplification overview](../).)

## Where to go next

- **Driver hub** (target + specs) → [`../../drivers/bms-18n862`](../../drivers/bms-18n862/)
- **Simulation** these presets are derived from → [`../../measurements/0-simulation/bms-18n862`](../../measurements/0-simulation/bms-18n862/)
