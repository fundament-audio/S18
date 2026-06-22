# FUNDAMENT S18

**Open-source sealed 18″ reference subwoofer.** Build 001 of the [FUNDAMENT](https://github.com/fundament-audio) platform.

> Status: 🟡 **Design + simulation initiated**

A fully documented, measurable, repairable sealed 18 built around a known-good recipe — made open. Deep, tactile bass with the cone control and low distortion to be taken seriously, not just a home-theatre rumble box.

---

## Scope (read this first)

The S18 is a **music subwoofer**, designed to ideally work in pairs - crossed **as high as possible (≤ ~80–120 Hz)**. It is intentionally *not* a high-crossover, directivity-controlled module — a single 18″ beams too early to integrate cleanly above that. 

## Hardware

| | |
|---|---|
| **Driver** | BMS 18N862 |
| **Amp / DSP** | Hypex FusionAmp FA502 |
| **Enclosure** | Sealed, ~115–125 L net |
| **Alignment** | Fc ≈ 47 Hz, **Qtc ≈ 0.64** |
| **Crossover** | User-set in processor/pre-amp; ships full-range to natural roll-off |


## DSP presets

Three presets, switchable directly on the Hypex, trading low-frequency extension against maximum SPL:

| Preset | Character | F3 (Hz) | F6 (Hz) | F10 (Hz) | Max SPL (sim) |
|---|---|---|---|---|---|
| **P1 — Extended** | Lowest reach, lower max SPL | ~20 | ~18 | ~16 | ~108 dB |
| **P2 — Balanced** | All-rounder | ~30 | ~23 | ~20 | ~114 dB |
| **P3 — Output** | Highest SPL, rolls off earlier | ~37 | ~30 | ~26 | ~120 dB |

→ HFD files: `/dsp` · target curves + biquad allocation: `/dsp/README.md`

**Room note:** these are anechoic/electrical **targets**. In a real room you also get room gain, so the right preset depends on your room as much as taste. 

We will follow up with more measurements and iterate on this here. (HFDs are luckily pure software presets :)) 

## Protection — do not disable

The onboard limiter is the safety-critical part of this design. Because room EQ runs *upstream*, the amp must survive whatever you feed it - a single null-fill boost can otherwise bottom the driver.


## Enclosure

⏳ pending

- Dimensions, panel cut list, bracing, damping stack will go into: `/enclosure`
- First prototypes with 22 mm MDF, double front baffle, window bracing, full damping stack, corner fillets.

## Bill of materials

⏳ pending

`/bom` — with suppliers listed. All parts off-the-shelf; no custom tooling.

## Build guide

⏳ pending

`/docs/BUILD.md` — step-by-step, from cut to driver mounting to amp setup and loading the HFD.

## Measurements

`/measurements`

| Measurement | Status |
|---|---|
| Simulated response (3 presets) | ✅ Initial simulations |
| Groundplane (anechoic-ish) | ⏳ pending |
| Nearfield (box response) | ⏳ pending |
| THD vs level (90/100/110 dB) | ⏳ pending |
| Long-term thermal compression | ⏳ pending |
| Per-unit T/S verification | ⏳ pending |
| Independent (Klippel NFS / anechoic) | 🙏 wanted — get in touch |

All raw data published. Protocol: see platform `PROTOCOL.md`.

**Honest expectations:** clean to ~110 dB in the passband; THD rises below ~30 Hz at high SPL

## Reproducibility

- **Stereo pairs:** match drivers (and net volume) within [tolerance] so the two units track through the LT region — otherwise the bass image smears.

## Repo structure

```
s18/
├── enclosure/      # plans, cut lists, bracing, damping
├── dsp/            # Hypex HFD files, target curves, biquad map
├── bom/            # bill of materials + EU suppliers
├── measurements/   # raw data + plots
├── docs/           # build guide, design notes, changelogs, etc
└── README.md
```

## Roadmap / revisions

- **rev A** — initial design + first simulations + discussions (current)
- next: groundplane + nearfield validation → publish
- see `/docs/CHANGELOG.md`

## Contributing

Build it, measure it to the protocol, share the data. Issues, PRs, and especially independent measurements very welcome. See `CONTRIBUTING.md`.

## Licence

Designs CERN-OHL-S-2.0 · docs/measurements CC-BY-SA-4.0 · code MIT.
