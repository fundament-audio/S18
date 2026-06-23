# S18 — DSP & amplification

The S18 ships **full-range** to its natural roll-off. You choose how to power and shape it.

## Paths

**1. Hypex FusionAmp FA502 — the easy entrance** (recommended for now)
Amp + DSP in one box. Load our HFD presets and you're done — see the files below.

**2. Bring your own amp** — ⏳
The driver is just a driver: any competent amp with adequate power and control works. Pair it with a DSP path.

**3. Bring your own DSP** — ⏳
Have a separate processor (miniDSP, CamillaDSP, …)? Apply our target curves / biquad coefficients on your own platform.

## The three EQ presets

Three presets, switchable directly on the Hypex, trading low-frequency extension against maximum SPL:

- **P1 — Extended:** reaches the lowest, gives up max SPL. For smaller rooms or where room gain already fills the bottom.
- **P2 — Balanced:** the all-rounder. Sensible extension with healthy headroom.
- **P3 — Output:** loudest, rolls off earlier. For larger rooms or when you want SPL over the last octave.

| Preset | F3 (Hz) | F6 (Hz) | F10 (Hz) | Max SPL (sim) |
|---|---|---|---|---|
| **P1 — Extended** | ~20 | ~18 | ~16 | ~108 dB |
| **P2 — Balanced** | ~30 | ~23 | ~20 | ~114 dB |
| **P3 — Output** | ~37 | ~30 | ~26 | ~120 dB |

**Room note:** these are anechoic/electrical **targets**. In a real room you also get room gain, so the right preset depends on your room as much as taste. We'll follow up with measurements and iterate here — HFDs are luckily pure software presets :)

## The files

- HFD presets → [`/dsp/hypex`](hypex/)
- Per-preset target curves + biquad allocation → ⏳ pending
- Crossover is **user-set upstream** in the processor/pre-amp; nothing is baked into the DSP.

## Protection — do not disable

The onboard limiter is the safety-critical part of this design. Because room EQ runs *upstream*, the amp must survive whatever you feed it — a single null-fill boost can otherwise bottom the driver.
