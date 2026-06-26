# S18 — DSP & amplification

The S18 ships **full-range** to its natural roll-off. You choose how to power and shape it — amp and DSP are modular.

## Reference — Hypex FusionAmp FA502 ✅

Amp + DSP + limiter in one box, and the **only path we've validated so far**. Load our HFD presets and you're done → [`bms-18n862/hypex`](bms-18n862/hypex/).

Everything below is **documented as compatible, not measured by us** — each option *can* apply the same presets (a Butterworth high-pass + the 20 Hz PEQ, ideally with a limiter). If you build and measure one, publish the data and we'll fold it in.

## Amplifier options

For when you're not running the FA502. Only the Crown XLS has its own DSP; the rest are **amp-only** and need a DSP from the next section.

| Amp | DIY / turnkey | Onboard DSP? | Notes | Cost |
|---|---|---|---|---|
| **Hypex FA502** ✅ | turnkey plate amp | yes (+ limiter) | the reference — amp + DSP in one box | €€ |
| **[Crown XLS DriveCore 2](https://www.crownaudio.com/en-US/products/xls-1002)** (1002/1502/2002) | turnkey pro amp | **yes** — PEQ + HP/LP to 24 dB/oct + Peakx limiter, presets persist | can host our presets standalone; measures a step below the Class-D references and has a fan — the gap shows more if you cross higher | € |
| **[Hypex nCore module](https://www.hypex.nl/products/amplifier-families/mains-powered-ncore-family/nc502mp-oem)** (NC252MP / NC502MP) | DIY module | no | same Class-D as the FA502, minus the DSP; superb measurements; pair with a DSP | €€ (~€375 module) |
| **[Purifi Eigentakt 1ET400A](https://purifi-audio.com/eigentakt)** | DIY module | no | about the best-measuring there is; needs SMPS + input buffer + chassis | €€€€ |
| **[Audiophonics assembled](https://www.audiophonics.fr/en/audiophonics-workshop-amplifiers-c-6421.html)** (LPA-S400ET Purifi · AP300-S500NC nCore) | turnkey (EU) | no | built boxes if you want Purifi/nCore without soldering | €€€ |
| **Any competent amp** | — | no | the driver is just a driver — ~500 W / 4 Ω class, stable and low-noise; pair with a DSP | varies |

Hypex owns the hi-fi "amp + DSP in one box" niche. **Purifi and Pascal are amp *modules* only** — there's no hi-fi DSP plate amp from either. (Pro Pascal + Marani DSP / Four Audio PPA plate amps exist, but they're install-grade and out of scope here.) So beyond the Hypex, your only integrated-DSP amp is the Crown XLS; everything else is amp + a separate DSP.

## DSP options

For any amp-only chain, the DSP applies the presets: a Butterworth high-pass (15/20/30 Hz, 24 dB/oct) plus the ~20 Hz PEQ boost, ideally with a protection limiter. The per-driver values in [`bms-18n862/`](bms-18n862/) are the source of truth.

| DSP | Type | HP 24 dB/oct + PEQ + limiter? | Notes | Cost |
|---|---|---|---|---|
| **[miniDSP 2x4 HD / Flex](https://www.minidsp.com/products/minidsp-in-a-box/minidsp-2x4-hd)** | dedicated | yes — all three | purpose-built for exactly this; standalone; clean — the easy recommendation | €€ |
| **Raspberry Pi + DAC HAT + [CamillaDSP](https://github.com/HEnquist/camilladsp)** | computer-based | yes (CamillaDSP biquads) | open and flexible; best-measuring HATs e.g. [HiFiBerry](https://www.hifiberry.com) DAC2 HD / DAC8x; some setup | € |
| **[DSPi](https://github.com/WeebLabs/DSPi) on a Raspberry Pi Pico 2 + Arylic ES9023 I2S DAC** | microcontroller | PEQ + crossovers yes; limiter ⚠️ verify | a full modern DSP for **~€30 all-in** — wild value for tinkerers; any decent I2S DAC works, the Arylic ES9023 is the cheap known-good one | € |
| **[Behringer Ultradrive DCX2496](https://www.behringer.com/en/products/0825-AAA)** | dedicated (pro) | yes — BW/Bessel/LR 6–48 dB/oct + PEQ + limiter | cheap and capable; dated/noisy analog I/O — feed it digitally if you can | € (~€300) |
| **[MOTU UltraLite-mk5](https://motu.com/en-us/products/gen5/ultralite-mk5/)** (or similar studio interface) | studio interface | PEQ + dynamics yes; steep HP ⚠️ approximate | runs standalone after config; a true 24 dB/oct protective HP isn't a normal PEQ band — lean on its dynamics/limiter, or use a dedicated DSP for the protective filter | €€€ |

Whatever you pick, apply the high-pass + PEQ from [`bms-18n862/`](bms-18n862/) and make sure a **working limiter sits somewhere in the chain** — see Protection below.

## How this folder is organized

DSP settings are modular — per driver, then per amp/DSP:

- **`dsp-amp/<driver>/`** — the DSP settings (target curves / EQ presets) for that driver. This is the source of truth, amp-agnostic.
- **`dsp-amp/<driver>/<dsp>/`** — ready-to-load files and notes for one specific amp/DSP (e.g. Hypex HFD presets).

The amp/DSP alternatives above are a documented menu for now; a `<driver>/<dsp>/` folder gets created once an option is validated with real files — as [`bms-18n862/hypex/`](bms-18n862/hypex/) is.

### Drivers

- **[`bms-18n862/`](bms-18n862/)** — the three EQ presets (extension vs. SPL) for the BMS 18N862.
  - [`bms-18n862/hypex/`](bms-18n862/hypex/) — Hypex FA502 HFD files + loading notes.

## Protection — do not disable

The onboard limiter is the safety-critical part of this design. Because room EQ runs *upstream*, the amp must survive whatever you feed it — a single null-fill boost can otherwise bottom the driver. This applies on every amp/DSP path, not just the Hypex.
