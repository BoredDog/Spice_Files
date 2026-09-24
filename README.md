# SPICE model library (LTspice + ngspice)

Ready-to-use simulation models for the parts we use in labs, course projects and
research: op-amps, transistors, MOSFETs, diodes, regulators, timers, drivers,
optocouplers and more. Every model file has been loaded in **LTspice** and
**ngspice** (which KiCad also uses), and the key parts are checked against their
datasheets.

> Collected for education and research at IIIT Hyderabad. Our own files are
> MIT-licensed. Every vendor model keeps its owner's terms and is **not
> relicensed**; each file's header gives the original download link. Provided
> as is, use at your own risk. Copyright holders can ask for removal by opening
> an issue. See [NOTICE.md](NOTICE.md) and [LICENSE](LICENSE).

---

## 1. Find a part

**Know the part number?** Open **[PARTS.md](PARTS.md)**, press **Ctrl+F / Cmd+F**
and type it, e.g. `BC547`, `LM2596` or `IRF540`. Each entry tells you what the
part is, which file it's in, whether it runs in your simulator, and gives a
datasheet link. If the part has no model anywhere, the bottom of PARTS.md says
what to use instead.

**Know what you need, not the part?** Start with this table, or browse a family
folder below.

### I want to…

| I want to… | Use | File | Works in |
|---|---|---|---|
| build a general op-amp circuit on ±15 V (filters, audio) | TL072 | [opamps/TL072_TI.lib](models/opamps/TL072_TI.lib) | both |
| build an op-amp circuit on a single 5–30 V supply | LM358 | [opamps/LM358_TI.lib](models/opamps/LM358_TI.lib) | both* |
| run an op-amp rail-to-rail on 3.3 V / 5 V | OPA2340 or MCP6001 | [opamps/OPA2340_TI.lib](models/opamps/OPA2340_TI.lib) | both* |
| simulate the textbook 741 | LM741 | [opamps/LM741_TI.lib](models/opamps/LM741_TI.lib) | both |
| amplify a bridge / strain gauge / ECG signal | AD620 or INA128 | [opamps/AD620_ADI.lib](models/opamps/AD620_ADI.lib) | both |
| compare two voltages / make a Schmitt trigger | LM393 | [comparators/LM393_TI.lib](models/comparators/LM393_TI.lib) | both* |
| use a small NPN / PNP transistor | 2N3904 / 2N3906, BC547B / BC557B | [bjt/2N3904_OnSemi.lib](models/bjt/2N3904_OnSemi.lib), [bjt/BC547B_OnSemi.lib](models/bjt/BC547B_OnSemi.lib) | both |
| switch a load from an Arduino / 5 V logic pin | IRLZ44N (logic-level MOSFET) | [mosfet/IRLZ44N_Infineon.lib](models/mosfet/IRLZ44N_Infineon.lib) | both |
| switch a small load (LED, relay) from logic | 2N7000 | [mosfet/2N7000_OnSemi.lib](models/mosfet/2N7000_OnSemi.lib) | both |
| drive relays or a stepper motor from a microcontroller | ULN2003, TIP120 | [drivers/ULN2003_Bordodynov.lib](models/drivers/ULN2003_Bordodynov.lib), [bjt/TIP120_OnSemi.lib](models/bjt/TIP120_OnSemi.lib) | both |
| rectify mains / transformer AC | 1N4007, W04G bridge | [diodes/1N400x_DiodesInc.lib](models/diodes/1N400x_DiodesInc.lib), [diodes/2W04G-W04G-DF04M_Bordodynov.lib](models/diodes/2W04G-W04G-DF04M_Bordodynov.lib) | both |
| use a fast signal diode / low-drop Schottky | 1N4148 / 1N5819 | [diodes/1N4148_OnSemi.lib](models/diodes/1N4148_OnSemi.lib), [diodes/1N5819_OnSemi.lib](models/diodes/1N5819_OnSemi.lib) | both |
| make a voltage reference with a zener | 1N47xxA series | [diodes/1N47xxA_DiodesInc.lib](models/diodes/1N47xxA_DiodesInc.lib) | both |
| get a precise 2.5 V reference | LM4040 | [regulators/LM4040-2V5_TI.lib](models/regulators/LM4040-2V5_TI.lib) | both* |
| get 5 V / 12 V from a higher DC voltage (linear) | LM7805 / LM7812 | [regulators/LM78xx_Bordodynov.lib](models/regulators/LM78xx_Bordodynov.lib) | both |
| get 3.3 V with low dropout (instead of AMS1117) | LM1086-3.3 | [regulators/LM1086-3P3_TI.lib](models/regulators/LM1086-3P3_TI.lib) | both* |
| get an adjustable voltage | LM317 | [regulators/LM317_TI.lib](models/regulators/LM317_TI.lib) | both* |
| step down 12–24 V to 5 V efficiently (buck) | LM2596-5.0 | [regulators/LM2596-5P0_TI.lib](models/regulators/LM2596-5P0_TI.lib) | ngspice only |
| build a 555 oscillator / timer | 555 | [timers/555-bipolar_ngspice.lib](models/timers/555-bipolar_ngspice.lib) | both* |
| drive a small speaker | LM386 | [opamps/LM386_Bordodynov.lib](models/opamps/LM386_Bordodynov.lib) | both* |
| build a hi-fi power amp | LM3886 | [opamps/LM3886_TI.lib](models/opamps/LM3886_TI.lib) | both* |
| isolate a signal (PC817-style optocoupler) | PC817_GEN | [optocouplers/OPTO-generic_Repo.lib](models/optocouplers/OPTO-generic_Repo.lib) | both |
| dim an AC lamp (triac + diac + opto driver) | BT136, DB3, MOC3021 | [thyristors/](models/thyristors/README.md), [optocouplers/](models/optocouplers/README.md) | both |
| simulate logic gates with real analog edges | SN74HC00 | [logic/SN74HC00_TI.lib](models/logic/SN74HC00_TI.lib) | both* |
| simulate a crystal, relay or transformer | XTAL_16M, RELAY_SPST_5V, XFMR_10TO1 | [passive/generic-passive_Repo.lib](models/passive/generic-passive_Repo.lib) | both |

\* **both\*** = works in ngspice only with the repo's `.spiceinit` (see §2).

### Browse by family

Each folder's README explains what the parts do, how to choose one, the pin
order, and links every datasheet.

| Family | What's inside |
|---|---|
| [opamps](models/opamps/README.md) | op-amps, instrumentation amps, current-sense amps, audio power amps |
| [bjt](models/bjt/README.md) | small-signal, medium-power and power transistors, Darlingtons |
| [diodes](models/diodes/README.md) | rectifiers, signal, Schottky, zeners, TVS, LEDs, bridges |
| [logic](models/logic/README.md) | 74HC / CD4000 gates, counters, analog switches |
| [regulators](models/regulators/README.md) | 78xx, LM317, LDOs, buck converters, references, PWM controller |
| [mosfet](models/mosfet/README.md) | small-signal, logic-level and power MOSFETs (N and P) |
| [thyristors](models/thyristors/README.md) | SCRs, triacs, diac |
| [optocouplers](models/optocouplers/README.md) | transistor-output, logic-output, triac drivers |
| [special](models/special/README.md) | function generators, modulator, UJT, LED bar driver |
| [drivers](models/drivers/README.md) | Darlington array, MOSFET gate drivers |
| [comparators](models/comparators/README.md) | LM311, LM339, LM393 |
| [jfet](models/jfet/README.md) | JFETs, incl. InterFET's 898-part library |
| [timers](models/timers/README.md) | 555 / 556 |
| [passive](models/passive/README.md) | relays, crystal, transformer, ideal switch |

---

## 2. Use a model

### LTspice

1. Add a SPICE directive (press **S**) with the full path to the file:
   ```
   .include /path/to/Spice_Files/models/opamps/TL072_TI.lib
   ```
2. Place a symbol and set its **Value** to the model or subckt name. The name
   is in PARTS.md and in the file's `* @pins:` line.
   - **Diodes, BJTs, JFETs, simple MOSFETs** (`.model` lines): use LTspice's
     stock `diode` / `npn` / `pnp` / `njf` / `nmos` symbol.
   - **5-pin op-amps** (pins IN+ IN− V+ V− OUT): use the stock
     `Opamps/opamp2` symbol.
   - **Other subcircuits:** let LTspice make a symbol. Open the `.lib` file
     in LTspice, right-click the `.subckt` line and choose *Create Symbol*.

### ngspice / KiCad

1. Copy [`.spiceinit`](.spiceinit) into your project folder (or your home
   folder). It contains one important line:
   ```
   set ngbehavior=ltps
   ```
   It lets ngspice read the LTspice- and PSpice-style files. Parts marked
   **both\*** or **BOTH-compat** don't load without it.
2. In your netlist:
   ```spice
   .include /path/to/Spice_Files/models/opamps/TL072_TI.lib
   X1 in fb vcc vee out TL072        ; pins: IN+ IN- V+ V- OUT
   ```
3. In **KiCad**, add the file to the symbol's *Simulation Model* field
   (*SPICE model from file*), then pick the subckt and map the pins.

### Check the pin order

Every file has a `* @pins:` line at the top, for example
`* @pins: LM1875_0: Vin Vip VSS VDD Vout`. Some vendors put pins in an unusual
order (the LM1875 has the **inverting** input first). The family README flags
these.

---

## 3. If something doesn't work

| Problem | Fix |
|---|---|
| ngspice: `Undefined parameter [onsemi]` / `no such function 'if'` / `could not find a valid modelname` | the `.spiceinit` is missing. Copy it next to your netlist (§2) |
| `unknown subckt` / `can't find model` | wrong name: copy it exactly from the `@pins` line or PARTS.md, and check the `.include` path |
| the part says **ngspice only** / **LTspice only** | use that simulator, or pick another maker's file for the same part (PARTS.md lists all of them) |
| LTspice: `time step too small` at start-up (power amps, regulators) | ramp the supplies up, e.g. `V1 vp 0 PWL(0 0 1m 25)` |
| output stuck / no switching | check the pin order in `@pins`, and that enable / mute / shutdown pins are connected as the datasheet says |
| the part isn't in PARTS.md | see *Not in the library* at the bottom of PARTS.md for a stand-in, or ask the maintainers to add it |

Two models of the same part can give noticeably different results. The
LTspice and datasheet 2N3904 models differ in gain by a factor of two. For
anything you'll report, say which file you used.

---

## 4. Reference

| File | What it is |
|---|---|
| [PARTS.md](PARTS.md) | A–Z part index |
| `models/<family>/README.md` | family guides: what each part does, pin order, datasheet links |
| `models/<family>/<Part>_<Maker>.lib` | the model files. The header of each says where it came from (`@url`), its licence terms (`@licence`), its pins (`@pins`) and any change made to it (`@patched`) |
| [`.spiceinit`](.spiceinit) | ngspice compatibility setting (see §2) |
| [NOTICE.md](NOTICE.md), [LICENSE](LICENSE) | licence terms: our files are MIT, vendor files keep their owners' terms |

**Known differences between the simulators:**
- **LTspice-only fields:** `mfg=`, `Iave=` and similar are fatal in plain ngspice, so the `.spiceinit` is needed.
- **Small numeric differences:** 1N4148 (PSpice EVAL) forward voltage differs by 2.5 %, the CMOS 555 period by 2.6 %, and ULN2003 V<sub>CE(sat)</sub> by 10 %.
- **JFET extras:** ngspice ignores LTspice's `Alpha`, `Vk`, `Isr` and `Nr`.
- **PC817 / CNY17:** LTspice's own models need a parameter from its symbol. Use `PC817_GEN` / `CNY17_GEN` instead.
