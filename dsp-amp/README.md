# S18 — DSP & amplification

The S18 ships **full-range** to its natural roll-off. You choose how to power and shape it — amp and DSP are modular.

## Paths

**1. Hypex FusionAmp FA502 — the easy entrance** (recommended for now)
Amp + DSP in one box. Load our HFD presets and you're done — see [`bms-18n862/hypex`](bms-18n862/hypex/).

**2. Bring your own amp** — ⏳
The driver is just a driver: any competent amp with adequate power and control works. Pair it with a DSP path.

**3. Bring your own DSP** — ⏳
Have a separate processor (miniDSP, CamillaDSP, …)? Apply our target curves / biquad coefficients on your own platform.

## How this folder is organized

DSP settings are modular — per driver, then per amp/DSP:

- **`dsp-amp/<driver>/`** — the DSP settings (target curves / EQ presets) for that driver. This is the source of truth, amp-agnostic.
- **`dsp-amp/<driver>/<dsp>/`** — ready-to-load files and notes for one specific amp/DSP (e.g. Hypex HFD presets).

### Drivers

- **[`bms-18n862/`](bms-18n862/)** — the three EQ presets (extension vs. SPL) for the BMS 18N862.
  - [`bms-18n862/hypex/`](bms-18n862/hypex/) — Hypex FA502 HFD files + loading notes.

## Protection — do not disable

The onboard limiter is the safety-critical part of this design. Because room EQ runs *upstream*, the amp must survive whatever you feed it — a single null-fill boost can otherwise bottom the driver. This applies on every amp/DSP path, not just the Hypex.
