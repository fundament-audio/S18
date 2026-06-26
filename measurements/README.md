# S18 — Measurements

All raw data published. Protocol: see the platform [MEASUREMENT_PROTOCOL.md](https://github.com/fundament-audio/platform/blob/main/MEASUREMENT_PROTOCOL.md).

Measurements are modular like the rest of the build — data nests per **stage → driver → amp/DSP** (e.g. `0-simulation/bms-18n862/`).

| Measurement | Status |
|---|---|
| Simulated response (3 presets) | ✅ [`0-simulation/bms-18n862/`](0-simulation/bms-18n862/) · [live dashboard](https://simulator.00aud.io/app/share/18N862-125L-sealed-cmqpbl62e0003jp042uz99kmr) |
| Groundplane (anechoic-ish) | ⏳ pending |
| Nearfield (box response) | ⏳ pending |
| THD vs level (90/100/110 dB) | ⏳ pending |
| Long-term thermal compression | ⏳ pending |
| Per-unit T/S verification | ⏳ pending |
| Independent (Klippel NFS / anechoic) | 🙏 wanted — get in touch |

**Honest expectations:** clean to ~110 dB in the passband; THD rises below ~30 Hz at high SPL.
