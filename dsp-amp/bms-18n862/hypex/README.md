# S18 — Hypex FA502 (BMS 18N862)

Ready-to-load presets for the **Hypex FusionAmp FA502** driving the BMS 18N862. These implement the three target curves documented one level up → [`../`](../).

## The HFD files

⏳ pending — one `.hfd` per preset (S18 Deep / S18 / S18 Loud).

## Loading a preset

1. Open the Hypex Filter Designer (HFD) and connect to the FA502.
2. Load the `.hfd` for the preset you want.
3. Verify the **limiter is active** before playing — see below.

## Protection — do not disable

The onboard limiter is safety-critical. Room EQ runs **upstream** of the amp, so the FA502 must survive whatever it's fed — a single null-fill boost can bottom the driver if the limiter is off. Keep it enabled on every preset.
