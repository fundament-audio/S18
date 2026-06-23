# FUNDAMENT S18

**Open-source sealed 18″ reference subwoofer.** Build 001 of the [FUNDAMENT](https://github.com/fundament-audio) platform.

> Status: 🟡 **Design + simulation initiated**

A fully documented, measurable, repairable sealed 18″ built around a known-good recipe — made open. Deep, tactile bass with the cone control and low distortion to be taken seriously, not just a home-theatre rumble box.

## Scope (read this first)

The S18 is a **music subwoofer**, designed to ideally work in pairs — crossed **as high as possible (≤ ~80–120 Hz)**. It is intentionally *not* a high-crossover, directivity-controlled module — a single 18″ beams too early to integrate cleanly above that.

## What we deliver

- A documented, measurable, repairable open sealed-18 recipe
- Off-the-shelf parts only — no custom tooling
- Switchable EQ presets, extension vs. SPL
- Published raw measurements, to a shared protocol
- Reproducible stereo pairs

## Target specs

| | |
|---|---|
| **Frequency response** | 20–250 Hz ±3 dB (ground plane), preset-dependent |
| **Typical in-room extension** | ~10 Hz (−3 dB) |
| **Max SPL** (avg 30–80 Hz, 1 m) | ~120 dB |
| **Dimensions (W×H×D)** | 550 × 550 × 600 mm |

## The recipe at a glance

| | |
|---|---|
| **Driver** | BMS 18N862 |
| **Amp / DSP** | Hypex FusionAmp FA502 (easy entrance — or bring your own amp / DSP, see [`/dsp`](dsp/)) |
| **Enclosure** | Sealed, ~115–125 L net |
| **Alignment** | Fc ≈ 47 Hz, **Qtc ≈ 0.64** |
| **Crossover** | User-set in processor/pre-amp; ships full-range to natural roll-off |

## Repo structure

```
s18/
├── enclosure/      # plans, cut lists, bracing, damping
├── dsp/            # amp + DSP paths, EQ presets, Hypex HFD files
├── bom/            # bill of materials + EU suppliers
├── measurements/   # raw data + plots
├── docs/           # build guide, design notes
└── README.md
```

- **[`/dsp`](dsp/)** — amplification + DSP paths (Hypex FA502, or bring your own amp / DSP) and the three EQ presets.
- **[`/enclosure`](enclosure/)** — sealed cabinet design and CAD.
- **[`/measurements`](measurements/)** — simulated + (pending) measured performance.
- **[`/docs/BUILD.md`](docs/BUILD.md)** — step-by-step build guide.
- **`/bom`** — bill of materials + EU suppliers (⏳ pending). All parts off-the-shelf; no custom tooling.

## Reproducibility

- **Stereo pairs:** match drivers (and net volume) within [TODO: tolerance] so the two units track through the LT region — otherwise the bass image smears.

## Contributing

Build it, measure it to the protocol, share the data. Issues, PRs, and especially independent measurements very welcome — see [`CONTRIBUTING.md`](CONTRIBUTING.md). Roadmap and revisions are tracked through GitHub issues + PRs.

💬 **Community:** the main discussion lives on the [Audio Science Review thread](https://www.audiosciencereview.com/forum/index.php?threads/fundament-an-open-source-fully-documented-subwoofer-platform-build-001-sealed-18″-bms-18n862-fa502.72012/) — come say hi.

## Licence

Designs CERN-OHL-S-2.0 · docs/measurements CC-BY-SA-4.0 · code MIT.
