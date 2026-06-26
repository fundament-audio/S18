# FUNDAMENT S18

**Deep 18″ bass without black boxes. Open, measurable, repairable — built to stay alive.**

> Status: 🟡 **Design + simulation initiated** — headline numbers below are simulated; measurements pending.

Open-source sealed 18″ reference subwoofer. Build 001 of the [FUNDAMENT](https://github.com/fundament-audio/platform) platform.

💬 Main discussion lives on the [Audio Science Review thread](https://www.audiosciencereview.com/forum/index.php?threads/fundament-an-open-source-fully-documented-subwoofer-platform-build-001-sealed-18%E2%80%B3-bms-18n862-fa502.72012/) — come say hi.

## Scope

The S18 is a **music subwoofer**, best in pairs, crossed **as high as possible (≤ ~80–120 Hz)**. It is intentionally *not* a high-crossover, directivity-controlled module — a single 18″ beams too early to integrate cleanly above that.

Deep, tactile bass with the cone control and low distortion to be taken seriously — not a home-theatre rumble box.

## Proven parts, missing data

The engineering here isn't novel - that's the point. The BMS 18N862 in a sealed ~120 L box is one of the most-trodden paths in serious DIY: documented across a scatter of forum builds, and a driver respected enough that designers like Troels Gravesen run it in their flagship full-range systems. The materials are known-good. By every account that exists, this driver is fast, low-distortion and properly excellent.

What's never existed is that knowledge in **one place, built to one spec, and measured to a published protocol** — instead of six forum posts and a dead image host.

Prior art tells us roughly where it lands. Measurements will follow and try to prove it.

## Target specs

| | |
|---|---|
| **Frequency response** | 20–250 Hz ±3 dB (ground plane, simulated), preset-dependent |
| **Typical in-room extension** | ~10 Hz (−3 dB, simulated) |
| **Max SPL** (avg 30–80 Hz, 1 m) | ~120 dB (simulated) |
| **Dimensions (W×H×D)** | 550 × 550 × 600 mm |

## The recipe

| Part | Reference |
|---|---|
| **Driver** | BMS 18N862 |
| **Amp / DSP** | Hypex FusionAmp FA502 — or bring your own, see [`/dsp-amp`](dsp-amp/) |
| **Enclosure** | Sealed, ~115–125 L net |
| **Alignment** | Fc ≈ 47 Hz, **Qtc ≈ 0.64** |
| **Crossover** | User-set in processor/pre-amp; ships full-range to natural roll-off |
| **EQ** | Switchable presets — extension vs. SPL |

Off-the-shelf parts only. No custom tooling.

The Hypex is the validated reference. Alternative amps (Crown XLS, DIY Purifi/nCore, Audiophonics) and DSPs (miniDSP, Raspberry Pi + CamillaDSP, a ~€30 Pico 2 + Arylic, Behringer DCX2496) are documented in [`/dsp-amp`](dsp-amp/).

## Built to stay alive

Nothing here is a sealed black box. Driver, amp, DSP, enclosure, tuning and measurements are all documented, versioned and replaceable. Driver dies — replace it. Amp dies — swap it. Want a different target? Validate it, publish the data: same platform, different validated outcome.

## How to get one

| Path | What it means |
|---|---|
| **DIY** | Download files, source parts, build it all |
| **Part-DIY** | Plans + flatpack or local CNC, assemble yourself |
| **Local build** | Cabinets or parts made locally from the open files |
| **Built-to-order** | Future: hand-built systems from the same open design |

Built-to-order is convenience, not a paywall. The engineering stays open.

Rough cost per build (and per stereo pair) → [`/bom`](bom/).

## Repository map

```text
S18/
├── drivers/        # driver choices, targets and use cases
├── dsp-amp/        # DSP + amplifier paths, presets and protection
├── enclosure/      # cabinet design, cut list, bracing and DXF
├── measurements/   # simulations, ground-plane data and future measurements
├── bom/            # bill of materials and suppliers
├── docs/           # build guide and design notes
└── README.md
```

Start here:

* [drivers/](drivers/) — choose the driver path
* [dsp-amp/](dsp-amp/) — choose DSP / amplifier implementation
* [enclosure/](enclosure/) — build the cabinet
* [measurements/](measurements/) — check simulation and measured data
* [bom/](bom/) — source parts
* [docs/BUILD.md](docs/BUILD.md) — build guide

## Built on FUNDAMENT

This repo is one implementation; the platform defines how it thinks: [PHILOSOPHY](https://github.com/fundament-audio/platform/blob/main/PHILOSOPHY.md) · [DECISION_MODEL](https://github.com/fundament-audio/platform/blob/main/DECISION_MODEL.md) · [MEASUREMENT_PROTOCOL](https://github.com/fundament-audio/platform/blob/main/MEASUREMENT_PROTOCOL.md) · [DOCUMENTATION_STANDARD](https://github.com/fundament-audio/platform/blob/main/DOCUMENTATION_STANDARD.md).

## Contributing

Build it, measure it to the protocol, share the data. Independent measurements especially welcome — see [`CONTRIBUTING.md`](CONTRIBUTING.md). Roadmap and revisions tracked through GitHub issues + PRs.

💬 Main discussion lives on the [Audio Science Review thread](https://www.audiosciencereview.com/forum/index.php?threads/fundament-an-open-source-fully-documented-subwoofer-platform-build-001-sealed-18%E2%80%B3-bms-18n862-fa502.72012/) — come say hi.

## Licence

Designs CERN-OHL-S-2.0 · docs/measurements CC-BY-SA-4.0 · code MIT.
