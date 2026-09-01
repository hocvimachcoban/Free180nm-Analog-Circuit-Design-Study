# Free180nm-Analog-Circuit-Design-Study
180nm Bulk CMOS &amp; GFM_MCU IO Library. 
Purpose: Support Analog and Mixed-Signal circuit design and simulation in LTspice for educational and research purposes. 

File Name:   FREE180nm.model_*
Purpose:     Create to Study Analogic Circuit Design on LTspice
Target Device: PTM 180nm Bulk / GFM_MCU IO Buffer
Author:      max1186 

Email:       mr.max1186@gmail.com

Facebook channel "Diễn Đàn Học Vi Mạch Cơ Bản": https://www.facebook.com/profile.php?id=61568327632465

Date:        2026-04-30

Version:     1.0

LTspice: version 24.0.12

Notes:       Integrated with encrypted PTM 180nm and GFM_MCU libraries.
             Developed for accurate transient, DC analysis, AC simulation

# Content: 
```text
|   Free180nm_ModelManual_Eng.pdf
|
+---Example
|       03_Dev_idvds.asc
|       04_Dev_idvgs.asc
|       BD_GTitleLTS.asy
|       gfmcu_nmos3p3.asy
|       gfmcu_pmos3p3.asy
|       header.asy
|       models_gfmcu.lib
|       ptm180_nmos1p8.asy
|       ptm180_pmos1p8.asy
|
+---LTspice180PDK
|       BD_GTitleLTS.asy
|       FREE180nm.model
|       FREE180_StdCells.sub
|       gfmcu_nmos3p3.asy
|       gfmcu_nplus_u.asy
|       gfmcu_npolyf_u.asy
|       gfmcu_pmos3p3.asy
|       gfmcu_pplus_u.asy
|       gfmcu_ppolyf_u.asy
|       gfmcu_vpnp_0p42x10.asy
|       gfmcu_vpnp_0p42x5.asy
|       gfmcu_vpnp_10x10.asy
|       gfmcu_vpnp_5x5.asy
|       header.asy
|       inv1.asc
|       inv1.asy
|       inv1_33.asc
|       inv1_33.asy
|       inv2.asc
|       inv2.asy
|       na21.asc
|       na21.asy
|       nr21.asc
|       nr21.asy
|       ptm180_nmos1p8.asy
|       ptm180_pmos1p8.asy
|
\---Model
        FREE180nm.model_FF
        FREE180nm.model_SS
        FREE180nm.model_TT
        models_gfmcu.lib
        PTM180nm_bulk_FF.txt
        PTM180nm_bulk_SS.txt
        PTM180nm_bulk_TT.txt
```

# Usage: 
**1. Model:**
There are three process corners in the model (TT, FF, SS).

Use the command .inc to call the process:

.inc \pathtomodel\Model\FREE180nm.model_TT

**2. LTspice symbol:**
In LTspice180PDK, device symbols are used to build your schematic, ranging from individual element devices to standard cells.

**Element devices:**

ptm180_nmos1p8.asy : NMOS 1.8V using PTM 180nm model

ptm180_pmos1p8.asy : PMOS 1.8V using PTM 180nm model

gfmcu_nmos3p3.asy : NMOS 3.3V using GFMCU Free model

gfmcu_pmos3p3.asy : PMOS 3.3V using GFMCU Free model

gfmcu_nplus_u.asy : N-plus resistor

gfmcu_npolyf_u.asy : N-poly resistor

gfmcu_pplus_u.asy : P-plus resistor

gfmcu_ppolyf_u.asy : P-poly resistor

**Standard cells:**

inv1, inv1_33, inv2, na21, nr21, etc.

# Example:
**I_D-V_DS Output Characteristics:
Example\03_Dev_idvds.asc
<img width="2078" height="1221" alt="image" src="https://github.com/user-attachments/assets/70081290-978c-40ab-a68c-1aa4bd3b4c3f" />

Spice netlist from LTSpice:
```text
* E:\00_Semi_Course\Model\Free180nm_PDK_20251023\00_Transfer_to_student\LAB\Lab0\03_Dev_idvds.asc

vvdd33 VDD33 0 3.3
.param pvgn33=0
.step param pvgn33 0.5 3 0.5
.dc vvdd33 0 3 0.05
.inc E:\00_Semi_Course\Upload_git_Face\Model\FREE180nm.model_TT
.param pvdd33=0
vvgn33 vgn33 0 {pvgn33}

XU10 VDD33 VGN33 0 0 gfmcu_nmos3p3 wp=1 lp=0.5 np=1 mp=1

.lib FREE180nm.model
.backanno
.end
```

Result:
<img width="956" height="498" alt="image" src="https://github.com/user-attachments/assets/aecb4127-857d-4d4a-bf3e-0795a1c86251" />

------------------------------------------------------------------------
# DISCLAIMER & FREE-USE NOTICE

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
