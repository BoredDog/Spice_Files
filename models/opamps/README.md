# opamps

<!-- generated file -->

Operational amplifiers: amplifiers, filters, integrators, buffers and instrumentation front ends.

**Choosing one**
- **Single supply (5–30 V), inputs down to ground:** LM358 (dual) or LM324 (quad). The outputs do **not** reach the top rail.
- **±15 V general-purpose / audio:** TL071 / TL072 / TL074 (low-noise JFET input), TL081 family, LM833, NE5532 / NE5534, OPA2134 (hi-fi).
- **Precision DC** (sensors, thermocouples, strain gauges): OP07, OPA2277. **3.3–5 V rail-to-rail:** MCP6001 family, OPA350, AD8605.
- **Instrumentation amplifier** (bridges, ECG): INA128. **Voltage-controlled gain (OTA):** LM13700. **Fast JFET:** LF356.
- **Textbook 741:** UA741_TI, LM741_TI or UA741_MicroSim (fastest to simulate). `741_ngspice` is the transistor-level circuit, for studying the inside of the chip.
- **Audio power amplifiers:** LM386 (0.5 W, 5–12 V single supply), LM1875 (20 W), LM3886 (68 W). TI's LM1875 subckt lists the **inverting** input first. In LTspice the LM3886 needs supplies that ramp up (e.g. `PWL(0 0 1m 25)`).
- Concept sims where only gain and bandwidth matter: `genopa1` (generic-opamp_ngspice).

**Usage:** most use `X1 IN+ IN- V+ V- OUT <name>`, which matches LTspice's `Opamps/opamp2` symbol. Check `@pins`: NE5534 has extra compensation pins. The dual/quad TI files model one amplifier, so instantiate it once per section.

## Models in this folder

**Works in:** BOTH = LTspice and native ngspice; BOTH-compat = also ngspice, with the repo `.spiceinit`; NG / LT = one simulator only.

| File | Part(s) / model names | What it is | Use it for | Works in | Datasheet |
|---|---|---|---|---|---|
| [741_ngspice.lib](741_ngspice.lib) | KI741 (O1 Inv Ninv Vee O2 Out Vcc) | transistor-level 741 (ngspice project) | teaching the inside of an op-amp | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/ua741.pdf) |
| [AD620_ADI.lib](AD620_ADI.lib) | AD620_AD | classic instrumentation amplifier, gain set by one resistor | ECG, strain gauges, bridge sensors | BOTH | [link](https://www.analog.com/en/products/ad620.html) |
| [AD623_ADI.lib](AD623_ADI.lib) | AD623_AD (IN+ IN- Rg+ Rg- V+ V- OUT REF) | single-supply rail-to-rail instrumentation amplifier | 3-12 V sensor front ends | BOTH | [link](https://www.analog.com/en/products/ad623.html) |
| [AD8605_ADI.lib](AD8605_ADI.lib) | AD8605 | precision CMOS rail-to-rail op-amp, 5 V | low-offset single-supply sensor front ends | BOTH | [link](https://www.analog.com/en/products/ad8605.html) |
| [INA125_TI.lib](INA125_TI.lib) | INA125 | instrumentation amp with built-in precision reference | load cells and bridges | BOTH | [link](https://www.ti.com/lit/ds/symlink/ina125.pdf) |
| [INA128_TI.lib](INA128_TI.lib) | INA128 | instrumentation amplifier, gain set by one resistor | bridge/strain-gauge/ECG front ends | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/ina128.pdf) |
| [INA180A1_TI.lib](INA180A1_TI.lib) | INA180A1 (INP INN VCC GND OUT) | current-sense amplifier, gain 20 | measuring load current with a shunt resistor | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/ina180.pdf) |
| [INA240A1_TI.lib](INA240A1_TI.lib) | INA240A1 (OUT INP INN REF1 REF2 VCC GND) | current-sense amp with PWM rejection, gain 20 | motor-current sensing on PWM-driven phases | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/ina240.pdf) |
| [INA333_TI.lib](INA333_TI.lib) | INA333 | micropower zero-drift instrumentation amp | battery-powered precision sensors | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/ina333.pdf) |
| [INA826_TI.lib](INA826_TI.lib) | INA826 (IN+ IN- RG+ RG- VDD GND OUT REF) | 36 V precision instrumentation amp | industrial / wide-supply sensor front ends | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/ina826.pdf) |
| [LF356_TI.lib](LF356_TI.lib) | LF356/NS | JFET-input op-amp, fast (5 MHz) | sample-and-hold, fast integrators | BOTH | [link](https://www.ti.com/lit/ds/symlink/lf356.pdf) |
| [LF411_TI.lib](LF411_TI.lib) | LF411C | low-offset JFET-input op-amp | integrators, sample-and-hold, LAoE labs | BOTH | [link](https://www.ti.com/lit/ds/symlink/lf411.pdf) |
| [LM13700_TI.lib](LM13700_TI.lib) | LM13700/NS | dual operational transconductance amplifier (OTA) | voltage-controlled filters/amplifiers (synths) | BOTH | [link](https://www.ti.com/lit/ds/symlink/lm13700.pdf) |
| [LM1875_TI.lib](LM1875_TI.lib) | LM1875_0 (Vin Vip VSS VDD Vout -- inverting input first!) | 20 W audio power amplifier | compact audio amps, +/-25 V | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/lm1875.pdf) |
| [LM324_TI.lib](LM324_TI.lib) | LMX24_LM2902 | quad single-supply op-amp, inputs to ground | general single-supply circuits (4 per chip) | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/lm324.pdf) |
| [LM358_TI.lib](LM358_TI.lib) | LMX58_LM2904 | dual single-supply op-amp, inputs to ground | the default cheap op-amp for 5-30 V single supply | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/lm358.pdf) |
| [LM386_Bordodynov.lib](LM386_Bordodynov.lib) | LM386 (pins 1 GAIN, 2 IN-, 3 IN+, 4 GND, 5 OUT, 6 VS, 7 BYPASS, 8 GAIN) | 0.5 W low-voltage audio power amplifier, gain 20 (200 with 10 uF across pins 1-8) | small speakers from 5-12 V: intercoms, toy radios, buzzers | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/lm386.pdf) |
| [LM3886_TI.lib](LM3886_TI.lib) | lm3886 (Vip Vin VDD VSS Vout MUTE) | 68 W high-performance audio power amplifier | hi-fi power amp projects; pull >0.5 mA from MUTE to VSS to un-mute; in LTspice ramp the supplies | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/lm3886.pdf) |
| [LM4871_TI.lib](LM4871_TI.lib) | LM4871 (+IN -IN VDD GND SHUTDOWN BYPASS Vo1 Vo2) | 1.5 W bridge-tied-load audio amp, 5 V | small speakers from USB/5 V without an output capacitor | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/lm4871.pdf) |
| [LM741_TI.lib](LM741_TI.lib) | LM741 | classic general-purpose op-amp (TI/National model) | textbook 741 labs, +/-15 V | BOTH | [link](https://www.ti.com/lit/ds/symlink/lm741.pdf) |
| [LM833_TI.lib](LM833_TI.lib) | LM833 | dual low-noise audio op-amp | audio preamps/filters | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/lm833.pdf) |
| [LMC6482_TI.lib](LMC6482_TI.lib) | LMC648x | CMOS rail-to-rail I/O op-amp, 3-15 V | single-supply precision circuits (ngspice only) | NG-compat-only | [link](https://www.ti.com/lit/ds/symlink/lmc6482.pdf) |
| [LMV358A_TI.lib](LMV358A_TI.lib) | LMV358A | low-voltage LM358 replacement, rail-to-rail output, 2.5-5.5 V | 3.3 V circuits where an LM358 would not swing (ngspice only) | NG-compat-only | [link](https://www.ti.com/lit/ds/symlink/lmv358a.pdf) |
| [MCP6001-MCP6021-MCP6041-MCP6L01_Microchip.lib](MCP6001-MCP6021-MCP6041-MCP6L01_Microchip.lib) | MCP6001, MCP6021, MCP6041, MCP6L01 | low-voltage CMOS rail-to-rail op-amps (1.8-6 V) | 3.3 V / battery circuits; MCP6002 = dual MCP6001 | BOTH-compat | [link](https://www.microchip.com/en-us/product/MCP6001) |
| [NE5532_Bordodynov.lib](NE5532_Bordodynov.lib) | NE5532 | dual low-noise audio op-amp | audio (use NE5534_TI for the single) | BOTH | [link](https://www.ti.com/lit/ds/symlink/ne5532.pdf) |
| [NE5534_TI.lib](NE5534_TI.lib) | NE5534 | single low-noise op-amp (7 pins incl. compensation) | low-noise audio/instrumentation | BOTH | [link](https://www.ti.com/lit/ds/symlink/ne5534.pdf) |
| [OP07_TI.lib](OP07_TI.lib) | OP07 | precision low-offset op-amp | DC-accurate amplifiers (thermocouples, strain gauges) | BOTH | [link](https://www.ti.com/lit/ds/symlink/op07.pdf) |
| [OPA2134_TI.lib](OPA2134_TI.lib) | OPAx134 | high-performance audio op-amp (FET input) | hi-fi audio stages | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/opa2134.pdf) |
| [OPA2277_TI.lib](OPA2277_TI.lib) | OPAx277 | ultra-precision low-drift op-amp | precision DC measurement | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/opa2277.pdf) |
| [OPA2340_TI.lib](OPA2340_TI.lib) | OPAx340 | 5 V rail-to-rail CMOS op-amp, 5.5 MHz | ADC buffers on 3.3-5 V | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/opa2340.pdf) |
| [OPA350_TI.lib](OPA350_TI.lib) | OPAx350 | rail-to-rail CMOS op-amp, 38 MHz, 5 V | ADC drivers, fast single-supply circuits | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/opa350.pdf) |
| [TDA2030_Bordodynov.lib](TDA2030_Bordodynov.lib) | TDA2030 (IN+ IN- VCC VEE OUT) | 14 W audio power amplifier | hobby amplifier builds | BOTH | [link](https://octopart.com/search?q=TDA2030) |
| [TL071_TI.lib](TL071_TI.lib) | TL071 | low-noise JFET-input op-amp (single) | audio, active filters on +/-15 V | BOTH | [link](https://www.ti.com/lit/ds/symlink/tl071.pdf) |
| [TL072_TI.lib](TL072_TI.lib) | TL072 | dual TL071 | the default +/-15 V audio / filter op-amp | BOTH | [link](https://www.ti.com/lit/ds/symlink/tl072.pdf) |
| [TL074_TI.lib](TL074_TI.lib) | TL074 | quad TL071 |  | BOTH | [link](https://www.ti.com/lit/ds/symlink/tl074.pdf) |
| [TL081_TI.lib](TL081_TI.lib) | TL081 | general JFET-input op-amp (single) | general +/-15 V circuits | BOTH | [link](https://www.ti.com/lit/ds/symlink/tl081.pdf) |
| [TL082_TI.lib](TL082_TI.lib) | TL082 | dual TL081 |  | BOTH | [link](https://www.ti.com/lit/ds/symlink/tl082.pdf) |
| [TL084_TI.lib](TL084_TI.lib) | TL084 | quad TL081 |  | BOTH | [link](https://www.ti.com/lit/ds/symlink/tl084.pdf) |
| [TLV2372_TI.lib](TLV2372_TI.lib) | TLV2372 (pins 3 4 6 2 1 = IN+ IN- VCC VEE OUT) | rail-to-rail I/O CMOS op-amp, 2.7-16 V | general single-supply rail-to-rail use | BOTH | [link](https://www.ti.com/lit/ds/symlink/tlv2372.pdf) |
| [UA741_MicroSim.lib](UA741_MicroSim.lib) | UA741 | Boyle macromodel of the 741 (loads everywhere, fast) | quick 741 simulations | BOTH | [link](https://www.ti.com/lit/ds/symlink/ua741.pdf) |
| [UA741_TI.lib](UA741_TI.lib) | UA741 | TI's 741 macromodel | textbook 741 labs | BOTH | [link](https://www.ti.com/lit/ds/symlink/ua741.pdf) |
| [generic-opamp_ngspice.lib](generic-opamp_ngspice.lib) | genopa1 (params GAIN POLE VOFF ROUT) | parameterised ideal-ish op-amp | concept sims where only gain/bandwidth matter | BOTH | — |

Datasheet links: ti.com links go straight to the PDF (all checked 2026-09-24); nexperia.com and vishay.com links open the product or search page; octopart.com links search for the part and list the official datasheet. Each model file's header (`@url`) says where it was downloaded from.
