# jfet

<!-- generated file -->

JFETs: voltage-controlled, normally-on transistors with very high input impedance.

- **General amplifiers and current sources:** 2N3819, 2N5457 / 2N5458, BF245A/B/C, MPF102. On the letter-graded parts (BF245A/B/C), the letter is the Idss range.
- **Low-current / low-noise:** J201. **RF / VHF:** J310. **Analog switches:** J111–J113.
- **P-channel:** 2N5460.
- Idss and Vp vary by 3–5× between samples of the same part. Treat the model as a typical device.
- ngspice ignores LTspice's JFET extras (`Alpha`, `Vk`, `Isr`, `Nr`), so high-Vds gate current appears only in LTspice.

## Models in this folder

**Works in:** BOTH = LTspice and native ngspice; BOTH-compat = also ngspice, with the repo `.spiceinit`; NG / LT = one simulator only.

| File | Part(s) / model names | What it is | Use it for | Works in | Datasheet |
|---|---|---|---|---|---|
| [2N5457-2N5458-BF245-J11x-MPF102_MicroCap.lib](2N5457-2N5458-BF245-J11x-MPF102_MicroCap.lib) | 2N5457, 2N5458, BF245A/B/C, J111-J113, MPF102 | N-channel JFETs | JFET amplifiers, current sources, analog switches (J11x) | BOTH | [link](https://octopart.com/search?q=2N5457) |
| [standard-jfet_InterFET.lib](standard-jfet_InterFET.lib) | 898 JFETs, e.g. 2N5457-GEN, J201, J310-LS, BF245A-PLP, 2SK170 (J2SK170-GEN), LSK170A-LS, MPF102A-GEN | InterFET's big compilation of JFET models from many makers (suffix/MFG= says which) | finding almost any JFET, incl. audio parts (2SK170/LSK170) and matched pairs (LSK389) | BOTH-compat | [link](https://www.interfet.com/jfet-datasheets/) |
| [standard-jfet_LTspice.lib](standard-jfet_LTspice.lib) | 2N3819, J201, J310, 2N5484, 2N5460 | LTspice's built-in JFET models | general JFET labs; J310 for RF, J201 for low-current | BOTH-compat | [link](https://octopart.com/search?q=2N3819) |

Datasheet links: ti.com links go straight to the PDF (all checked 2026-09-24); nexperia.com and vishay.com links open the product or search page; octopart.com links search for the part and list the official datasheet. Each model file's header (`@url`) says where it was downloaded from.
