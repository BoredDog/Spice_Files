# comparators

<!-- generated file -->

Comparators: output a logic level saying which input is higher. Unlike op-amps, they are built to run open-loop and switch fast.

- All three here have **open-collector outputs**: add a pull-up resistor (1–10 kΩ) from the output to your logic supply.
- **LM393** (dual) or **LM339** (quad): single 3–30 V supply, inputs can go down to ground. Use them for battery monitors, window comparators and Schmitt triggers (add positive feedback).
- **LM311**: single comparator with strobe/balance pins, faster, runs on ±15 V. Use it for zero-crossing detectors and PWM generation.
- Don't use an op-amp as a comparator in simulation or on the bench; it saturates slowly.

## Models in this folder

**Works in:** BOTH = LTspice and native ngspice; BOTH-compat = also ngspice, with the repo `.spiceinit`; NG / LT = one simulator only.

| File | Part(s) / model names | What it is | Use it for | Works in | Datasheet |
|---|---|---|---|---|---|
| [LM311_TI.lib](LM311_TI.lib) | LM311 | single comparator, open-collector, strobe pin | threshold detectors, zero-crossing, PWM from triangle wave | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/lm311.pdf) |
| [LM339_TI.lib](LM339_TI.lib) | LM2901 (LM339 family) | quad comparator, open-collector, single supply | four comparisons from one chip, window comparators | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/lm339.pdf) |
| [LM393_TI.lib](LM393_TI.lib) | LM2903B (LM393 family) | dual comparator, open-collector, single supply | battery monitors, Schmitt triggers on 3-30 V supplies | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/lm393.pdf) |

Datasheet links: ti.com links go straight to the PDF (all checked 2026-09-24); nexperia.com and vishay.com links open the product or search page; octopart.com links search for the part and list the official datasheet. Each model file's header (`@url`) says where it was downloaded from.
