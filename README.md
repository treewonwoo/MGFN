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

### 🔷 Linear Cryptanalysis (18R)
- Enter the `MGFN_Linear_Cryptanalysis/` directory.
- See its `README.md` for a **fully automated** key recovery: just run a single command for end-to-end attack.

### 🔷 Differential Cryptanalysis (24R)
- Enter the `MGFN_Differential_Cryptanalysis/` directory.
- See its `README.md` for a **manual step-by-step pipeline**: edit variables and file paths as needed, and run each stage of the pipeline in order (data generation, merging, filtering, key recovery, etc.).


**General Notes**
- For both variants, you must set file paths, dataset sizes, mask values, and performance parameters at the top of each script or source file before running.
- Intermediate files can be several gigabytes—ensure you have enough disk space.

> For full details, see the individual `README.md` files in each subdirectory.



## 📄 License

```
MIT License

Copyright (c) 2025 Wonwoo Song, Namil Kim, Seungjun Baek, Yongjin Jeon, Giyoon Kim and Jongsung Kim

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the “Software”), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
---


