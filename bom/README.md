# S18 — Bill of materials

> **First stab.** Prices are *indicative* — a rough "what will this cost me" feel, not quotes.
> Confirm current/local pricing before buying. EU (€, Germany reference) is firmest; UK/NA/Asia are
> approximate. `unknown` means we haven't found a reliable figure yet. EU prices are roughly inc-VAT
> unless noted. Off-the-shelf parts only — no custom tooling.

## What varies, what doesn't

- **Per cabinet, shared across builds:** driver, enclosure material, damping, connectors, fixings.
- **The modular cost:** amp/DSP — see [`/dsp-amp`](../dsp-amp/). Your choice here drives most of the
  total *and* the stereo economics (one stereo amp / one multi-output DSP can serve both subs).

## Sourcing & prices — big-ticket items

### Driver — BMS 18N862 (8 Ω)
*BMS Speakers GmbH, Hannover — not the unrelated Shenzhen "BMS Audio".*

| Region | ~Price | Where to buy |
|---|---|---|
| EU | ~€600 (range €460–740) | [Toutlehautparleur](https://en.toutlehautparleur.com/speaker-bms-18n862-8-ohm-18-inch.html) (FR), Knockoutsound |
| UK | ~£450–600 | [Elements Audio](https://www.elements-audio.com) (~£450), [Lean Audio](https://leanaudio.co.uk/product/bms-18n862-8-ohm-18-1500w-loudspeaker/) (~£600) |
| NA | ~$600 | US Speaker LLC, Reverb |
| Asia | unknown | [BMS Asia-Pacific distributors](https://www.bmsspeakers.com/index.php-791.html?id=bms_distributors_asia_pacific) |

### Reference amp + DSP — Hypex FusionAmp FA502
One box: amp + DSP + limiter. FA501 (single channel) ≈ €505 in the EU; other regions scale or `unknown`.

| Region | ~Price | Where to buy |
|---|---|---|
| EU | ~€720 inc (€585 ex VAT) | [Hypex Direct](https://www.hypexdirect.com/products/fusion-amplifiers/fusionamp-fa502), SoundImports (NL), Lautsprechershop (DE) |
| UK | ~£600–700 | Wilmslow Audio, Audio Hum, KJF Audio |
| NA | unknown US$ (≈$750 — confirm) | Hypex Direct (US), Madisound |
| Asia | unknown | Hypex Direct (ships JP/SG/MY/HK) / local distributor |

### Budget amp + DSP — Crown XLS 1502 DriveCore 2
Amp + onboard DSP in one box; the DSP can host our presets, and **one stereo unit drives a whole pair**.
See [`/dsp-amp`](../dsp-amp/) for the full amp/DSP menu (nCore, Purifi, miniDSP, Raspberry Pi, etc.).

| Region | ~Price | Where to buy |
|---|---|---|
| NA | ~$490–650 | Sweetwater, Parts-Express, Amazon |
| EU | ~€400–450 | Thomann |
| UK | ~£350–400 | Thomann UK |
| Asia | unknown | Thomann / local |

## Small parts (per cabinet)

Cheap, and similar across regions — EU figures shown.

| Part | Spec | Qty | ~EU | Notes |
|---|---|---|---|---|
| Damping wool | Visaton 5070 / VS-Wool (or equiv.) | a few packs | ~€10–40 | light, even fill — see [`/enclosure`](../enclosure/) |
| Panel damping | Self-adhesive bitumen pads | side panels | ~€30 | kills panel ring |
| Connector | Neutrik Speakon NL4 | 1 | ~€8 | optional rear terminal |
| Fixings | T-nuts/screws, sealant, glue | — | ~€20 | airtight assembly |

## Enclosure — by how you get the box

Cabinet ≈ **2.6 m² of 22 mm MDF** (from the [cut list](../enclosure/), 2 braces). Maps to the "How to
get one" paths in the [root README](../README.md):

| Path | What you do | ~Cost (Germany) |
|---|---|---|
| **DIY** — raw MDF | cut everything yourself | MDF ~€24/m² → **~€60/cab** |
| **Part-DIY** — precut plates | route the baffle cutouts + braces yourself | **~€70/cab** |
| **Local build** — full CNC | cutouts included | ~€60–70/m² → **~€160–180/cab** |
| **Built-to-order** — carpenter | hand-built cabinet | varies — **get a local quote** (rough order: a few hundred € of labour on top of materials) |

## Build totals (indicative, EU, precut box ~€70)

### Reference build — Hypex FA502
Per single sub: driver €600 + FA502 €700 + box €70 + damping €40 + Speakon €10 + fixings €20 ≈ **€1,440**.

Stereo pair — the amp choice is where you save or buy headroom:

| Pair amp config | Amps | Pair total | Note |
|---|---|---|---|
| 1× FA502 (one channel per sub) | ~€700 | ~€2,180 | cheapest Hypex; one amp drives both |
| 2× FA501 | ~€1,010 | ~€2,490 | one amp per sub |
| 2× FA502 bridged | ~€1,400 | ~€2,880 | ~1000 W/sub — max headroom |

### Budget build — no FA502
Stereo pair with **1× Crown XLS** (~€400) driving both ≈ **€1,880**. Or go cheaper on the DSP: a generic
~500 W amp + [DSPi on a Pico 2 + Arylic](../dsp-amp/) (~€30 DSP).

## Why a stereo pair is cheaper per sub

The per-sub cost drops as you add the second sub, because the amp/DSP can be **bought once**:

- A **stereo amp** (FA502, Crown XLS) drives both subs — one amp, not two.
- A **multi-output DSP** (miniDSP, Pico 2) processes both channels — bought once.
- The trade-off: a shared amp gives less per-sub headroom. **2× FA502 bridged** spends that saving back
  on ~1000 W/sub of headroom instead.
