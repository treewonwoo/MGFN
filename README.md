# 🔐 MGFN Cryptanalysis Collection

This repository contains **full C and Python implementations** for cryptanalysis and 128-bit master-key recovery on two variants of the MGFN block cipher:

- **MGFN-18R:** Linear Cryptanalysis & Key Recovery  
- **MGFN-24R:** Differential Cryptanalysis & Key Recovery

Each method has its own folder, usage, and README.

---

## 📚 Project Overview

MGFN is a 128-bit block cipher.  
This repository contains two independent cryptanalytic projects:

- `MGFN_Linear_Cryptanalysis/`  
  — 18-round version, C-only  
  — Linear cryptanalysis, 3-round key recovery, full master-key search

- `MGFN_Differential_Cryptanalysis/`  
  — 24-round version, C+Python  
  — Differential cryptanalysis, S-box analysis, full master-key search, scriptable pipeline

All file paths, dataset sizes, and mask values must be configured at the top of each script/source before running.  
**There is no “one-click” automation.**  
You have full control over every step.

---

## 📂 Repository Structure

```text
MGFN/
├── MGFN_Linear_Cryptanalysis/
│   ├── MGFN_18R_LC.c
│   ├── MGFN_18R.c
│   ├── MGFN_18R.h
│   ├── recover_masterkey.c
│   └── recover_masterkey.h
│   └── README.md        # Usage and details for linear attack
│
├── MGFN_Differential_Cryptanalysis/
│   ├── dif_gen_data.c
│   ├── MGFN_DC.c
│   ├── find_masterkey.c
│   ├── key_condition.py
│   ├── gen_all_possible_difference.py
│   ├── merge_with_dif.py
│   ├── merge_with_dif_1.py
│   ├── merge_with_dif_2.py
│   ├── filter.py
│   └── README.md        # Usage and details for differential attack
│
├── data/
│   └── (generated/filtered datasets)
│
└── README.md           # (this file)
