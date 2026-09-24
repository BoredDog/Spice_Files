# Licences and notices

**Short version:** our own files are MIT-licensed. Every other model file
belongs to its publisher, keeps the publisher's terms and is **not
relicensed**. The collection exists for non-commercial education and research
(courses and projects at IIIT Hyderabad). Everything is provided **as is,
without warranty**; use it at your own risk. Each file's header gives the
original download location (`@url`), and where possible you should download
models directly from the publisher.

**Copyright holders:** if you don't want a file to be included here, please
open an issue on this repository and it will be removed promptly.

## What is ours

Files written for this repository are MIT-licensed
([LICENSES/MIT.txt](LICENSES/MIT.txt)):
- the documentation and `.spiceinit`
- model files named `*_Repo.lib`, e.g. the generic diodes, optocouplers and passives

## Everything else

Every other file in `models/` was published by someone else: semiconductor
vendors (TI, onsemi, Nexperia, Vishay, Infineon, ST, Microchip, ADI, Diodes /
Zetex, AOS, InterFET, …), simulator vendors (Analog Devices / LTspice, Cadence
PSpice EVAL, Spectrum Software Micro-Cap, Intusoft), the ngspice project,
independent model developers (e.g. Symmetry Design Systems, Thomatronik) and
community collections (Bordodynov's LTspice library, ltwiki,
KiCad-Spice-Library). **None of it is relicensed here.**

How the terms are handled:
- **Vendor text kept verbatim.** Each file keeps the vendor's own copyright
  and licence text. When a model was taken out of a larger library file, the
  vendor notice for it was copied along, so conditions like Zetex's "may be
  used or copied intact (including this notice)" are met.
- **`* @licence:` quotes the file itself.** It says what the vendor text
  contains (copyright notice, grant or restriction), or states that the file
  has no licence text at all. The section below collects these by maker.
- **No redistribution means not included.** Files whose text forbids
  redistribution are not in this repository. That covers models from Central
  Semiconductor, some onsemi files and onsemi's MC34063A.
- **No modification means no fixes.** Files whose text forbids modification
  are included unchanged: no fixes and no helper renaming. Where a file was
  changed so it runs in both simulators, its `* @patched:` line says exactly
  what changed.
- **Legacy attributed lines.** `*_LTspice.lib`, `D1N4148_PSpiceEval.lib`,
  `UA741_MicroSim.lib` and `*_Datasheet.lib` are individual attributed model
  lines from those sources (LTspice: "© Linear Technology / Analog Devices,
  all rights reserved").

If you want to use a model anywhere other than your own simulations (a
publication, a product, another repository), read that file's header and the
publisher's terms first, and ask the publisher if in doubt.

<!-- BEGIN generated terms -->

## Terms found in the files (generated)

Quoted from each file's `* @licence:` header, which is taken from the vendor's own text. **RESTRICTED** = the vendor text limits use or modification; read the file before using it outside a simulation.

### ADI

- **2 file(s):** notice: "Copyright 1999 by Analog Devices"  
  _e.g. AD623_ADI.lib, AD8605_ADI.lib_
- **1 file(s):** notice: "Copyright 1990 by Analog Devices, Inc."  
  _e.g. AD620_ADI.lib_

### AOS

- **2 file(s):** no licence or copyright text in the vendor file (terms unknown)  
  _e.g. AO3400_AOS.lib, AO3401A_AOS.lib_

### Bordodynov

- **20 file(s):** no licence or copyright text in the vendor file (terms unknown)  
  _e.g. ULN2003_Bordodynov.lib, CD4066B_Bordodynov.lib, LM386_Bordodynov.lib, NE5532_Bordodynov.lib, TDA2030_Bordodynov.lib, 6N137_Bordodynov.lib …_
- **1 file(s):** notice: "Copyright (c) U.A.V. aka Skywarrior 2005. All rights reserved."  
  _e.g. 2W04G-W04G-DF04M_Bordodynov.lib_
- **1 file(s):** notice: "Copyright (c) International Rectifier"  
  _e.g. IR2110-IR2104_Bordodynov.lib_

### Datasheet

- **1 file(s):** datasheet parameters  
  _e.g. 2N3904-2N3906-BC546_Datasheet.lib_

### DiodesInc

- **4 file(s):** no licence or copyright text in the vendor file (terms unknown)  
  _e.g. 1N400x_DiodesInc.lib, 1N47xxA_DiodesInc.lib, 1N5231B_DiodesInc.lib, 1N5406-1N5408-1N5711WS_DiodesInc.lib_

### Fairchild

- **2 file(s):** no licence or copyright text in the vendor file (terms unknown)  
  _e.g. PN2222A-PN2907A_Fairchild.lib, MOC3043M_Fairchild.lib_

### Infineon

- **5 file(s):** notice: "Copyright(c) Symmetry Design Systems"  
  _e.g. IRF3205_Infineon.lib, IRF540N_Infineon.lib, IRF9540N_Infineon.lib, IRFZ44N_Infineon.lib, IRLZ44N_Infineon.lib_

### InfineonIR

- **2 file(s):** notice: "Copyright(c) Symmetry Design Systems"  
  _e.g. IRF4905_InfineonIR.lib, IRF540N-IRF9540N-IRFZ44N-IRF3205-IRF520_InfineonIR.lib_

### InterFET

- **1 file(s):** no licence or copyright text in the vendor file (terms unknown)  
  _e.g. standard-jfet_InterFET.lib_

### KiCadLib

- **1 file(s):** no licence or copyright text in the vendor file (terms unknown)  
  _e.g. UF4007-DF10M_KiCadLib.lib_
- **1 file(s):** notice: "Copyright Intusoft 1993-1997"  
  _e.g. BT136_KiCadLib.lib_

### LTspice

- **4 file(s):** (c) Linear Technology / Analog Devices, all rights reserved; attributed lines  
  _e.g. standard-bjt_LTspice.lib, standard-diodes_LTspice.lib, standard-jfet_LTspice.lib, standard-vdmos_LTspice.lib_
- **2 file(s):** notice: "Copyright © Linear Technology Corp. 1998, 1999, 2000. All rights reserved."  
  _e.g. 4N25_LTspice.lib, 4N27_LTspice.lib_

### LTwiki

- **3 file(s):** no licence or copyright text in the vendor file (terms unknown)  
  _e.g. 2N4401-2N4403-2N5551-2N5401_LTwiki.lib, 2SC5200-2SA1943-2SC1815-2SA1015_LTwiki.lib, BC546-BC559_LTwiki.lib_

### MicroCap

- **2 file(s):** no licence or copyright text in the vendor file (terms unknown)  
  _e.g. 2N5457-2N5458-BF245-J11x-MPF102_MicroCap.lib, CD4013-CD4017-CD4040-CD4060_MicroCap.lib_

### Microchip

- **1 file(s):** condition: "The software supplied herewith by Microchip Technology Incorporated (the 'Company') is intended and supplied to you, the Company's customer, for use soley and exclusively on Microchip products."; notice: "under applicable copyright laws. All rights are reserved. Any use in"  
  _e.g. TC4420-TC4427_Microchip.lib_
- **1 file(s):** condition: "The software supplied herewith by Microchip Technology Incorporated (the "Company") is intended and supplied to you, the Company's customer, for use soley and exclusively on Microchip products."; notice: "under applicable copyright laws. All rights are reserved. Any use in"  
  _e.g. MCP6001-MCP6021-MCP6041-MCP6L01_Microchip.lib_

### MicroSim

- **1 file(s):** no explicit grant  
  _e.g. UA741_MicroSim.lib_

### Motorola

- **1 file(s):** notice: "Copyright(c) Symmetry Design Systems"  
  _e.g. TIP31C_Motorola.lib_

### Nexperia

- **13 file(s):** no licence or copyright text in the vendor file (terms unknown)  
  _e.g. BC817-25_Nexperia.lib, BC817-40_Nexperia.lib, BC847_Nexperia.lib, BC857_Nexperia.lib, PMBT3904_Nexperia.lib, 1N4148_Nexperia.lib …_

### ngspice

- **19 file(s):** none stated  
  _e.g. 74HC00m_ngspice.lib, 74HC02m_ngspice.lib, 74HC04m_ngspice.lib, 74HC08m_ngspice.lib, 74HC10m_ngspice.lib, 74HC138m_ngspice.lib …_
- **2 file(s):** 3-clause BSD (Holger Vogt)  
  _e.g. ICL8038_ngspice.lib, LTC1044_ngspice.lib_
- **1 file(s):** public domain (Holger Vogt)  
  _e.g. LR8_ngspice.lib_
- **1 file(s):** modified BSD (Holger Vogt)  
  _e.g. LM3914_ngspice.lib_

### OnSemi

- **16 file(s):** notice: "Copyright(c) Symmetry Design Systems"  
  _e.g. 2N3055A_OnSemi.lib, 2N3055H_OnSemi.lib, 2N3055_OnSemi.lib, 2N3904_OnSemi.lib, 2N3906_OnSemi.lib, BC547B_OnSemi.lib …_
- **1 file(s):** notice: "Copyright(c) ON Semiconductor"  
  _e.g. TIP29-TIP32-TIP2955-TIP3055_OnSemi.lib_
- **1 file(s):** no licence or copyright text in the vendor file (terms unknown)  
  _e.g. 1N4148_OnSemi.lib_

### Philips

- **1 file(s):** no licence or copyright text in the vendor file (terms unknown)  
  _e.g. BD135-BD140_Philips.lib_

### PSpiceEval

- **1 file(s):** no explicit grant  
  _e.g. D1N4148_PSpiceEval.lib_

### Repo

- **3 file(s):** MIT  
  _e.g. generic-diodes_Repo.lib, OPTO-generic_Repo.lib, generic-passive_Repo.lib_

### ST

- **1 file(s):** notice: "(c) 1997 ST Microelectronics. All rights reserved."  
  _e.g. P6KE6V8A_ST.lib_
- **1 file(s):** notice: "(c) 2005 STMicroelectronics. All rights reserved."  
  _e.g. BTA16-600B_ST.lib_

### TI

- **10 file(s):** no licence or copyright text in the vendor file (terms unknown)  
  _e.g. LF411_TI.lib, NE5534_TI.lib, TL071_TI.lib, TL072_TI.lib, TL074_TI.lib, TL081_TI.lib …_
- **9 file(s):** condition: "The model is provided solely on an "as is" basis."; notice: "(C) Copyright 2022 Texas Instruments Incorporated. All rights reserved."  
  _e.g. LM339_TI.lib, INA125_TI.lib, INA333_TI.lib, INA826_TI.lib, LMC6482_TI.lib, OPA2134_TI.lib …_
- **6 file(s):** condition: "The model is provided solely on an "as is" basis."; notice: "(C) Copyright 2016 Texas Instruments Incorporated. All rights reserved."  
  _e.g. LM5109B_TI.lib, LM833_TI.lib, LM1086-3P3_TI.lib, LM1086-5P0_TI.lib, LM1086-ADJ_TI.lib, LM2576_TI.lib_
- **5 file(s):** condition: "The model is provided solely on an "as is" basis."; notice: "(C) Copyright 2015 Texas Instruments Incorporated. All rights reserved."  
  _e.g. LM1117_TI.lib, LM2596-12P0_TI.lib, LM2596-3P3_TI.lib, LM2596-5P0_TI.lib, LM2940-10_TI.lib_
- **4 file(s):** condition: "The model is provided solely on an "as is" basis."; notice: "[Copyright] (C) Copyright 2019 Texas Instruments Incorporated.All rights reserved."  
  _e.g. CD4011B_TI.lib, CD4093B_TI.lib, SN74HC00_TI.lib, SN74HC14_TI.lib_
- **4 file(s):** condition: "The model is provided solely on an "as is" basis."; notice: "(C) Copyright 2012 Texas Instruments Incorporated. All rights reserved."  
  _e.g. INA180A1_TI.lib, INA240A1_TI.lib, LM1875_TI.lib, LM3886_TI.lib_
- **3 file(s):** condition: "The model is provided solely on an "as is" basis."; notice: "(C) Copyright 2011 Texas Instruments Incorporated. All rights reserved."  
  _e.g. UCC27211_TI.lib, INA128_TI.lib, TLV2372_TI.lib_
- **3 file(s):** grant: "The file may be copied, and distributed; however, reselling the material is illegal"; notice: "(C) National Semiconductor, Inc."  
  _e.g. LF356_TI.lib, LM13700_TI.lib, LM741_TI.lib_
- **3 file(s):** notice: "Copyright 2018 by Texas Instruments Corporation"  
  _e.g. LM324_TI.lib, LM358_TI.lib, LMV358A_TI.lib_
- **2 file(s):** condition: "The model is provided solely on an "as is" basis."; notice: "(C) Copyright 2019 Texas Instruments Incorporated. All rights reserved."  
  _e.g. LM311_TI.lib, LM393_TI.lib_
- **2 file(s):** condition: "The model is provided solely on an "as is" basis."; notice: "(C) Copyright 2013 Texas Instruments Incorporated. All rights reserved."  
  _e.g. LM4871_TI.lib, LM4040-2V5_TI.lib_
- **1 file(s):** condition: "The model is provided solely on an "as is" basis."; notice: "(C) Copyright 2025 Texas Instruments Incorporated. All rights reserved."  
  _e.g. OP07_TI.lib_
- **1 file(s):** condition: "The model is provided solely on an "as is" basis."; notice: "(C) Copyright 2014 Texas Instruments Incorporated. All rights reserved."  
  _e.g. LM317_TI.lib_
- **1 file(s):** condition: "The model is provided solely on an "as is" basis."; notice: "(C) Copyright 2009 Texas Instruments Incorporated. All rights reserved."  
  _e.g. TL431_TI.lib_
- **1 file(s):** condition: "The software (if any) is provided solely on an "as is" basis."; notice: "(C) Copyright 2008 Texas Instruments Incorporated. All rights reserved."  
  _e.g. UCC28C43_TI.lib_

### Vishay

- **7 file(s):** notice: "Copyright: Thomatronik GmbH, Germany"  
  _e.g. 1N4148WS_Vishay.lib, BAT85_Vishay.lib, BZX55C5V1_Vishay.lib, BZX55_Vishay.lib, BZX84C16_Vishay.lib, BZX85C15_Vishay.lib …_
- **4 file(s):** notice: "Copyright(c) Symmetry Design Systems"  
  _e.g. BC327_Vishay.lib, BC337_Vishay.lib, BC807_Vishay.lib, BZX84C5V6_Vishay.lib_
- **4 file(s):** notice: "(c)2000 Thomatronik GmbH info@thomatronik.de"  
  _e.g. BZX55C24_Vishay.lib, BZX55C3V9_Vishay.lib, BZX55C9V1_Vishay.lib, GLL4747_Vishay.lib_
- **1 file(s):** no licence or copyright text in the vendor file (terms unknown)  
  _e.g. SI2302_Vishay.lib_

### Zetex

- **3 file(s):** grant: "It is supplied free of charge by Zetex for the purpose of research and design and may be used or copied intact (including this notice) for that purpose only."; notice: "(C) 1996 ZETEX PLC The copyright in this model and the design embodied belong to"  
  _e.g. BC107-BC108-BC109-BC177_Zetex.lib, BC546-BC560_Zetex.lib, 2N7000-BS170_Zetex.lib_

<!-- END generated terms -->
