# 🔐 MGFN Cryptanalysis Projects

This repository provides **C and Python implementations** for cryptanalysis and 128-bit master-key recovery on the MGFN block cipher:

- **MGFN-18R Linear Cryptanalysis** (fully automated, C)
- **MGFN-24R Differential Cryptanalysis** (manual step-by-step pipeline, C+Python)

Each project is self-contained with its own subdirectory and detailed README.

---

## 📚 Project Overview

MGFN is a 128-bit block cipher.  
This repository contains two separate attacks:

- `MGFN_Linear_Cryptanalysis/`  
  **Linear cryptanalysis** for 18 rounds (fully automatic, single command execution)  
  - End-to-end C implementation: dataset generation, 3-round key recovery, and exhaustive master-key search

- `MGFN_Differential_Cryptanalysis/`  
  **Differential cryptanalysis** for 24 rounds (manual, step-by-step scripts and C programs)  
  - Modular pipeline: Python+ C scripts for each stage  
  - User must configure and run each stage individually

All dataset sizes, file paths, and parameters must be set at the top of each script or source file before running.  
**The 18R linear attack is fully automatic; the 24R differential attack is modular and requires manual control for each step.**

---

## 📂 Repository Structure

```text
MGFN/
├── MGFN_Linear_Cryptanalysis/
│   ├── MGFN_18R_LC.c
│   ├── MGFN_18R.c
│   ├── MGFN_18R.h
│   ├── recover_masterkey.c
│   ├── recover_masterkey.h
│   └── README.md        # Details for linear attack (automatic)
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
│   └── README.md        # Details for differential attack (manual)
│
├── data/
│   └── (generated/filtered datasets)
│
└── README.md           # (this file)

## 🚦 How to Use

### 🔹 Linear Cryptanalysis (18R)
- Go to the `MGFN_Linear_Cryptanalysis/` folder.
- See the `README.md` in that folder for a **fully automated** attack—simply run a single command to perform end-to-end key recovery.

### 🔹 Differential Cryptanalysis (24R)
- Go to the `MGFN_Differential_Cryptanalysis/` folder.
- See the `README.md` in that folder for a **step-by-step pipeline**—you’ll need to edit variable values and file paths, and run each stage manually in order (data generation, merging, filtering, key search, etc).

---

**General Notes**
- For both variants, you must manually set file paths, dataset sizes, mask values, and performance parameters at the top of each script or source file before running.
- Intermediate files can be several gigabytes—make sure you have enough disk space.

---

> For full details and options, see the individual `README.md` files inside each project folder.


