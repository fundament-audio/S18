# S18 — 0 · Simulation

Initial sealed-box simulation of the BMS 18N862 in ~125 L sealed, including the three DSP presets.

**Live dashboard:** <https://simulator.00aud.io/app/share/18N862-125L-sealed-cmqpbl62e0003jp042uz99kmr>

## Results (simulated, ground plane)

| Preset | F3 (Hz) | F6 (Hz) | F10 (Hz) | Max SPL |
|---|---|---|---|---|
| S18 Deep | 20.4 | ~18 | 16.1 | 106.4 dB |
| S18 | 29.8 | ~25 | 19.8 | 114.0 dB |
| S18 Loud | 37.7 | ~32 | 26.2 | 120.0 dB |

Full EQ settings (high-pass + PEQ) per preset → [`/dsp`](../../dsp/).

## Screenshots

- `spl-presets.png` — SPL vs frequency, all three presets (S18 Deep · S18 · S18 Loud)
- `eq-s18.png` — S18 (balanced) EQ: PEQ 20 Hz +10.5 dB Q 1.1 · HP 20 Hz BW 24 dB/oct
- `eq-s18-deep.png` — S18 Deep EQ: PEQ 20 Hz +15.0 dB Q 1.6 · HP 15 Hz BW 24 dB/oct
- `eq-s18-loud.png` — S18 Loud EQ: PEQ 20 Hz +10.0 dB Q 1.3 · HP 30 Hz BW 24 dB/oct
