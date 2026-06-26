# FUNDAMENT S18

**Open-source sealed 18″ reference subwoofer.** Build 001 of the [FUNDAMENT](https://github.com/fundament-audio) platform.

> Status: 🟡 **Design + simulation initiated**

A fully documented, measurable, repairable sealed 18″ built around a known-good recipe — made open. Deep, tactile bass with the cone control and low distortion to be taken seriously, not just a home-theatre rumble box.

**Who it's for:** people who want a reference-grade music subwoofer they can build, measure, and repair themselves — ideally as a stereo pair. For the full scope and design target, see the driver hub → [`/drivers/bms-18n862`](drivers/bms-18n862/).

## Built on the FUNDAMENT platform

The S18 is one *build* on a shared platform. The platform defines the philosophy, decision model, measurement protocol, and documentation standard once; each build extends them rather than redefining them. The structuring idea:

> The **enclosure is the durable foundation** (decades-long lifespan). Everything bolted to it — **driver, amplifier, DSP, and measurements** — is modular: replaceable, upgradeable, and documented per configuration.

That's why this repo nests per driver, and per amp/DSP within that: one cabinet can host different drivers, each with its own design target, DSP settings, and measurements.

Platform docs (read these for the "why"):
[PHILOSOPHY](https://github.com/fundament-audio/platform/blob/main/PHILOSOPHY.md) ·
[DECISION_MODEL](https://github.com/fundament-audio/platform/blob/main/DECISION_MODEL.md) ·
[MEASUREMENT_PROTOCOL](https://github.com/fundament-audio/platform/blob/main/MEASUREMENT_PROTOCOL.md) ·
[DOCUMENTATION_STANDARD](https://github.com/fundament-audio/platform/blob/main/DOCUMENTATION_STANDARD.md) ·
[AGENTS](https://github.com/fundament-audio/platform/blob/main/AGENTS.md)

## What we deliver

- A documented, measurable, repairable open sealed-18 recipe
- Off-the-shelf parts only — no custom tooling
- Switchable EQ presets, extension vs. SPL
- Published raw measurements, to a shared protocol
- Reproducible stereo pairs

## Official reference build (current configuration)

The reference build is the combination we measure, validate, and document. Each row is modular — follow the link to that component.

| | | |
|---|---|---|
| **Driver** | BMS 18N862 | [`/drivers/bms-18n862`](drivers/bms-18n862/) |
| **Amp / DSP** | Hypex FusionAmp FA502 (easy entrance — or bring your own) | [`/dsp-amp`](dsp-amp/) |
| **Enclosure** | Sealed, ~115–125 L net | [`/enclosure`](enclosure/) |
| **Alignment** | Fc ≈ 47 Hz, **Qtc ≈ 0.64** | [driver](drivers/bms-18n862/) · [enclosure](enclosure/) |
| **Crossover** | User-set in processor/pre-amp; ships full-range to natural roll-off | [`/dsp-amp`](dsp-amp/) |

## Repo structure

```
s18/
├── enclosure/      # the durable foundation — sealed cabinet, cut list, bracing, DXF
├── drivers/        # modular: each driver, its design target + T/S params
│   └── bms-18n862/
├── dsp-amp/        # modular: DSP settings per driver, ready-to-load files per amp/DSP
│   └── bms-18n862/
│       └── hypex/
├── measurements/   # raw data, nested per stage → driver → amp
│   └── 0-simulation/bms-18n862/
├── bom/            # bill of materials + EU suppliers
├── docs/           # build guide, design notes
└── README.md
```

- **[`/drivers/bms-18n862`](drivers/bms-18n862/)** — the driver hub: design target, target specs, T/S, alignment in this enclosure.
- **[`/dsp-amp`](dsp-amp/)** — amplification + DSP paths (Hypex FA502, or bring your own) and the per-driver EQ presets.
- **[`/enclosure`](enclosure/)** — sealed cabinet design, cut list, and CAD.
- **[`/measurements`](measurements/)** — simulated + (pending) measured performance.
- **[`/bom`](bom/)** — bill of materials + EU suppliers (⏳ pending). All parts off-the-shelf; no custom tooling.
- **[`/docs/BUILD.md`](docs/BUILD.md)** — step-by-step build guide.

## Reproducibility

- **Stereo pairs:** match drivers (and net volume) within [TODO: tolerance] so the two units track through the LT region — otherwise the bass image smears.

## Contributing

Build it, measure it to the protocol, share the data. Issues, PRs, and especially independent measurements very welcome — see [`CONTRIBUTING.md`](CONTRIBUTING.md). Roadmap and revisions are tracked through GitHub issues + PRs.

💬 **Community:** the main discussion lives on the [Audio Science Review thread](https://www.audiosciencereview.com/forum/index.php?threads/fundament-an-open-source-fully-documented-subwoofer-platform-build-001-sealed-18″-bms-18n862-fa502.72012/) — come say hi.

## Licence

Designs CERN-OHL-S-2.0 · docs/measurements CC-BY-SA-4.0 · code MIT.
