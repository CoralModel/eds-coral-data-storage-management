# Coral Demography Data Cleaning

<img width="1500" height="505" alt="coral-photo" src="https://github.com/user-attachments/assets/d74d8abb-d2b9-4000-a9b5-819c7c068822" />
<br>
This repository contains a data cleaning and processing pipeline that prepares raw coral demography field data from the Moorea Coral Reef (MCR) Long Term Ecological Research (LTER) site for downstream analysis and visualization. Raw data arrive in wide format with inconsistent column naming across survey years; this pipeline standardizes, reconciles, and reshapes them into a single long-format dataset spanning 2013–2024.

## What this repository does

- Reads and harmonizes raw Excel files from two sources: a consolidated wide-format workbook (2013–2023) and individual data sheets for each transect/plot (2024)
- Resolves inconsistent column naming across survey years (e.g., `L2024` vs. `L24`, `Dynam` vs. `Dynamics`)
- Pivots data from wide to long format, with one row per coral per year
- Filters to transect-level observations
- Encodes coral dynamic events (recruitment, death, fission, fusion, etc.) as binary indicator columns
- Corrects duplicate recruitment and death flags
- Assigns unique coral IDs and transect IDs for use in downstream figures and models
- Calculates volume using unique formulas for each coral genera

## Repository structure

```
├── analysisdata
│   ├── clean_corals.csv                      # Cleaned long-format data with plot and transect observations
│   └── volume_corals.csv                     # Cleaned long-format data with volume measurements and added variables for GLMM analysis
├── eds-coral-data-storage-management.Rproj
├── LICENSE
├── R                                         # Unique volume functions for each coral genera
│   ├── cyl_vol.R
│   ├── hemisph_vol.R
│   └── sph_vol.R
├── rawdata
│   ├── 2024sheets                            # Transect-level sheets
│   └── coral_raw_wide_2013-2023_v2.xlsx      # Wide observations from 2013–2023
├── README.md
├── volume_cleaning_script.qmd                # Supplementary script for volume calculations
└── wide-to-long-processing-script.qmd        # Main cleaning and reshaping script
```

> **Note:** Raw data files are not tracked in this repository (see Data Access below).

## Data access

Raw data are sourced from the **Moorea Coral Reef (MCR) LTER** and are not yet publicly available. Please contact the authors for data access inquiries.

## Authors

- [Kylie Newcomer](https://github.com/kylienewcomer)
- [Joaquin Sandoval](https://github.com/sandovaljoaquin)
- [Vedika Shirtekar](https://github.com/vedikaS-byte)

## References & acknowledgements

Data are from the **Moorea Coral Reef Long Term Ecological Research** (MCR LTER) site, funded by the National Science Foundation.
