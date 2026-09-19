# Free180nm-Analog-Circuit-Design-Study

180nm Bulk CMOS \& GFM\_MCU IO Library.

Purpose: Support Analog and Mixed-Signal circuit design and simulation in LTspice for educational and research purposes.

File Name:   FREE180nm.model\_\*

Purpose:     Create to Study Analogic Circuit Design on LTspice

Target Device: PTM 180nm Bulk / GFM\_MCU IO Buffer

Author:      max1186

Email:       mr.max1186@gmail.com

GitHub package: https://github.com/hocvimachcoban/Free180nm-Analog-Circuit-Design-Study/tree/main

Facebook channel "Diễn Đàn Học Vi Mạch Cơ Bản": https://www.facebook.com/profile.php?id=61568327632465

Date:        2026-09-19

Version:     1.1

LTspice: version 24.0.12

Notes:       Integrated with encrypted PTM 180nm and GFM\_MCU libraries.
Developed for accurate transient, DC analysis, AC simulation

# Content:

```text
|   Free180nm\_ModelManual\_Eng.pdf
|
+---Example
|       03\_Dev\_idvds.asc
|       04\_Dev\_idvgs.asc
|       BD\_GTitleLTS.asy
|       gfmcu\_nmos3p3.asy
|       gfmcu\_pmos3p3.asy
|       header.asy
|       models\_gfmcu.lib
|       ptm180\_nmos1p8.asy
|       ptm180\_pmos1p8.asy
|
+---LTspice180PDK
|       BD\_GTitleLTS.asy
|       FREE180nm.model
|       FREE180\_StdCells.sub
|       gfmcu\_nmos3p3.asy
|       gfmcu\_nplus\_u.asy
|       gfmcu\_npolyf\_u.asy
|       gfmcu\_pmos3p3.asy
|       gfmcu\_pplus\_u.asy
|       gfmcu\_ppolyf\_u.asy
|       gfmcu\_vpnp\_0p42x10.asy
|       gfmcu\_vpnp\_0p42x5.asy
|       gfmcu\_vpnp\_10x10.asy
|       gfmcu\_vpnp\_5x5.asy
|       header.asy
|       inv1.asc
|       inv1.asy
|       inv1\_33.asc
|       inv1\_33.asy
|       inv2.asc
|       inv2.asy
|       na21.asc
|       na21.asy
|       nr21.asc
|       nr21.asy
|       ptm180\_nmos1p8.asy
|       ptm180\_pmos1p8.asy
|
\\---Model
        FREE180nm.model\_FF
        FREE180nm.model\_SS
        FREE180nm.model\_TT
        models\_gfmcu.lib
        PTM180nm\_bulk\_FF.txt
        PTM180nm\_bulk\_SS.txt
        PTM180nm\_bulk\_TT.txt
```

# Usage:

**1. Model:**
There are three process corners in the model (TT, FF, SS).

Use the command .inc to call the process:

.inc \\pathtomodel\\Model\\FREE180nm.model\_TT

**2. LTspice symbol:**
In LTspice180PDK, device symbols are used to build your schematic, ranging from individual element devices to standard cells.

**Element devices:**

ptm180\_nmos1p8.asy : NMOS 1.8V using PTM 180nm model

ptm180\_pmos1p8.asy : PMOS 1.8V using PTM 180nm model

gfmcu\_nmos3p3.asy : NMOS 3.3V using GFMCU Free model

gfmcu\_pmos3p3.asy : PMOS 3.3V using GFMCU Free model

gfmcu\_nplus\_u.asy : N-plus resistor

gfmcu\_npolyf\_u.asy : N-poly resistor

gfmcu\_pplus\_u.asy : P-plus resistor

gfmcu\_ppolyf\_u.asy : P-poly resistor

**Standard cells:**

inv1, inv1\_33, inv2, na21, nr21, etc.

# Example:

\*\*I\_D-V\_DS Output Characteristics:
Example\\03\_Dev\_idvds.asc
<img width="2078" height="1221" alt="image" src="https://github.com/user-attachments/assets/70081290-978c-40ab-a68c-1aa4bd3b4c3f" />

Spice netlist from LTSpice:

```text
\* E:\\00\_Semi\_Course\\Model\\Free180nm\_PDK\_20251023\\00\_Transfer\_to\_student\\LAB\\Lab0\\03\_Dev\_idvds.asc

vvdd33 VDD33 0 3.3
.param pvgn33=0
.step param pvgn33 0.5 3 0.5
.dc vvdd33 0 3 0.05
.inc E:\\00\_Semi\_Course\\Upload\_git\_Face\\Model\\FREE180nm.model\_TT
.param pvdd33=0
vvgn33 vgn33 0 {pvgn33}

XU10 VDD33 VGN33 0 0 gfmcu\_nmos3p3 wp=1u lp=0.5u np=1 mp=1

.lib FREE180nm.model
.backanno
.end
```

Result:
<img width="956" height="498" alt="image" src="https://github.com/user-attachments/assets/aecb4127-857d-4d4a-bf3e-0795a1c86251" />

\---

# DISCLAIMER \& FREE-USE NOTICE

This library is provided completely FREE of charge.

This library is intended for educational, academic, research, and non-commercial purposes.

The author does not sell, license, or commercially distribute this library.

The author provides this library on an "as-is" basis and assumes no responsibility or liability for any direct or indirect damage, loss, design failure, simulation error, fabrication issue, or other consequence resulting from the use of these models or any circuit designed using them.

Users are responsible for independently verifying the accuracy, suitability, and limitations of the models before using them in any application.

This library is not intended to replace official foundry documentation, PDK documentation, process design rules, qualified semiconductor models, or production-grade simulation environments.

# Source and Attribution

The library integrates or is based on freely available models and resources, including:

•	GF180MCU PDK (Free / Open PDK resources)

•	Predictive Technology Model (PTM) 180nm models

For the GF180MCU PDK electrical specifications and related SPICE model information, refer to the official documentation:
GF180MCU PDK – Analog SPICE Electrical Specifications

The original source materials remain subject to their respective licenses, copyrights, and terms of use. Users should consult the original source repositories and documentation for the applicable licensing conditions.

Non-Commercial Distribution

This project is distributed free of charge.

•	No purchase is required.

•	No payment is requested for access to this library.

•	The author does not commercially sell the included model files.

•	The library is intended for learning, experimentation, circuit research, and simulation.

•	Any redistribution or modification should respect the licenses and terms associated with the original source materials.

Important: "Free" in this document refers to the availability of this library for free use and distribution under applicable source licenses. It does not override or replace the licenses of the original GF180MCU PDK, PTM models, or other third-party materials.

# DONATE:

ETH address: 0x5C91cA7CF8e1936837eb40DE57947d36C86355AC

Solona address: 5eMdzhnXcDCoqUr9kS1N87eFekzzHYZBhfsLo4yP328T

BTC address: bc1qk59q3r8v9cejrr6uyvvucapegs9uc4gs3fvkhl

