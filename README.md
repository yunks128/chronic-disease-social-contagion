# Social Contagion and Spatial Clustering of Chronic Conditions

> **Manuscript:** "Social Contagion and Spatial Clustering of Chronic Conditions: A Dual-State Analysis in Utah and New Hampshire, USA (2020–2024)"  
> **Authors:** Daniel E. Zoughbie & Kyongsik Yun  
> **Journal:** PLOS ONE (under review, PONE-D-25-45329)

---

## Overview

This repository contains all author-generated analysis code and processed/summary data supporting the findings of the manuscript. The study applies a dual-framework approach—combining network-based social reproduction number (social R₀) modeling with geospatial and demographic clustering analysis—to investigate social contagion and spatial clustering of chronic conditions using all-payer claims data from Utah (2020–2022) and New Hampshire (2020–2024).

---

## Repository Structure

```
.
├── code/
│   ├── utah_analysis.ipynb                  # Utah: social R₀ computation and network clustering
│   ├── nh_spatial_analysis.ipynb            # New Hampshire: spatial autocorrelation & demographics
│   └── nh_social_contagion.ipynb            # New Hampshire: social R₀ and contagion analysis
├── data/
│   ├── DATA_AVAILABILITY.md                 # Data access instructions
│   └── nh_summary/
│       ├── icd_code_pairs_longitudinal_2020_2024_sanitized.csv  # Aggregated ICD pair counts (sanitized)
│       ├── top_10_icd_code_pairs.csv         # Top 10 most frequent ICD code co-occurrence pairs
│       ├── covid_co_occurrence_matrix.csv    # COVID-related co-occurrence matrix
│       ├── covid_respiratory_co_occurrence_ranking.csv
│       └── respiratory_data.csv              # Respiratory condition summary
├── figures/
│   ├── figure1.png                          # Social R₀ estimates (Utah)
│   ├── figure2.png                          # Disease network comparisons (Utah)
│   ├── figure3.png                          # Spatial clustering maps (New Hampshire)
│   └── supplementary/
│       ├── demographic_*.png                # Supporting Figures SF1–SF6: demographic distributions
│       ├── disease_map_*.png                # Supporting Figures SF8–SF13: spatial LISA/Gi* maps
│       ├── disease_correlations.png         # Supporting Figure SF7: county-level correlation matrix
│       ├── disease_comparison.png           # Condition comparison figure
│       ├── disease_r0_comparison.png        # Supporting Figure SF14: social R₀ (New Hampshire)
│       └── disease_network.png             # Disease network visualization
└── shapefiles/
    └── SHAPEFILES.md                        # Instructions for downloading Census TIGER/Line shapefiles
```

---

## Code

### Requirements

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn geopandas pysal libpysal esda splot folium
```

Python 3.9+ recommended.

### Notebooks

| Notebook | Description |
|----------|-------------|
| `utah_analysis.ipynb` | Loads Utah APCD claims data, computes ZIP-level concentration indices, Gini-like coefficients, social R₀ for five conditions, and generates network visualizations |
| `nh_spatial_analysis.ipynb` | Loads MedInsight NH claims data, computes county-level prevalence, Global Moran's Index, LISA clusters, Getis-Ord Gi* hotspots, and demographic stratifications |
| `nh_social_contagion.ipynb` | Applies the social R₀ framework to NH claims data across six chronic conditions; generates Figure SF14 |

> **Note:** Raw data file paths in the notebooks reference local file system locations. Update paths to match your local data directory before running.

---

## Data

### New Hampshire (MedInsight / NH CHIS)

The raw New Hampshire all-payer claims data (PUBLICUSE_CLAIM_MC_20xx files) are publicly available from the New Hampshire Department of Health and Human Services (NH DHHS) through the New Hampshire Comprehensive Health Care Information System (NHCHIS):

> **Download:** https://www.dhhs.nh.gov/programs-services/medicaid/medinsight

Files used:
- `PUBLICUSE_CLAIM_MC_2020.txt` through `PUBLICUSE_CLAIM_MC_2024.txt` (medical claims)
- `PUBLICUSE_CLAIM_DC_2023.zip`, `PUBLICUSE_CLAIM_DC_2024.zip` (dental claims)
- `PUBLICUSE_CLAIM_PC_2023.zip`, `PUBLICUSE_CLAIM_PC_2024.zip` (pharmacy claims)
- `PUBLICUSE_REF_TABLES/` (reference/lookup tables)

All data are de-identified public-use files provided under the MedInsight Public Use data use terms.

**Processed summary files** (included in this repository under `data/nh_summary/`):
- `icd_code_pairs_longitudinal_2020_2024_sanitized.csv`: Aggregated co-occurrence counts of ICD-10 diagnosis code pairs across all years (2020–2024), sanitized (no individual-level records)
- `top_10_icd_code_pairs.csv`: Top 10 most frequent ICD code pair co-occurrences
- Additional small summary CSVs

### Utah (APCD)

The Utah all-payer claims data were obtained under a formal data use agreement with the **Utah All-Payer Claims Database (APCD)**, administered by the Utah Department of Health and Human Services. Individual-level Utah APCD data cannot be publicly shared; researchers may apply for access at:

> **Access:** https://healthcarestats.utah.gov/about-the-data/apcd/ (Utah DHHS Health Care Statistics Programs — APCD)

The Utah notebook (`utah_analysis.ipynb`) documents the full analytical pipeline. Summary outputs (social R₀ values, concentration indices) are reported in the manuscript and Figure 1.

### Shapefiles

County boundary shapefiles are from the **U.S. Census Bureau TIGER/Line** program (public domain). See `shapefiles/SHAPEFILES.md` for download instructions.

---

## Citation

If you use this code or data, please cite:

```
Zoughbie DE, Yun K (2025). Social Contagion and Spatial Clustering of Chronic Conditions:
A Dual-State Analysis in Utah and New Hampshire, USA (2020–2024).
PLOS ONE. [Under review, PONE-D-25-45329]
```

---

## License

- **Code** is released under the [MIT License](LICENSE).
- **Processed summary data** are released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
- Raw MedInsight NH CHIS data are subject to NH DHHS MedInsight Public Use terms.
- Raw Utah APCD data are subject to the Utah APCD data use agreement.

---

## Contact

- **Kyongsik Yun** — yunkss@gmail.com — Computation and Neural Systems, California Institute of Technology
- **Daniel E. Zoughbie** — University of California, Berkeley; New England Complex Systems Institute

---

## Competing Interests

D.Z. and K.Y. are co-founders of Hammurabi, which was supported by UC Berkeley SkyDeck. This does not alter our adherence to PLOS ONE policies on sharing data and materials.
