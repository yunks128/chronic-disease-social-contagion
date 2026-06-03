# Data Availability

## Summary data (included in this repository)

The `nh_summary/` directory contains processed, de-identified aggregate summary files derived from the New Hampshire MedInsight all-payer claims data:

| File | Description | Rows |
|------|-------------|------|
| `icd_code_pairs_longitudinal_2020_2024_sanitized.csv` | ICD-10 diagnosis code pair co-occurrence counts by year (2020–2024), sanitized | ~1M |
| `top_10_icd_code_pairs.csv` | Top 10 most frequent ICD code pairs | 10 |
| `covid_co_occurrence_matrix.csv` | COVID-related ICD code co-occurrence matrix | — |
| `covid_respiratory_co_occurrence_ranking.csv` | COVID/respiratory co-occurrence ranking | — |
| `respiratory_data.csv` | Respiratory condition summary statistics | — |

All summary files contain only aggregate counts (no individual-level records) and are released under CC BY 4.0.

---

## Raw data access

### New Hampshire MedInsight (NH CHIS)

Raw New Hampshire all-payer claims data are publicly available from the New Hampshire Department of Health and Human Services:

- **Portal:** https://www.dhhs.nh.gov/programs-services/medicaid/medinsight
- **Files used:** `PUBLICUSE_CLAIM_MC_2020` through `PUBLICUSE_CLAIM_MC_2024` (medical claims)
- **Data dictionary:** Milliman NH CHIS Public Use Data Dictionary (available from NH DHHS)
- **Terms:** NH DHHS MedInsight Public Use data use agreement

### Utah All-Payer Claims Database (APCD)

Utah APCD data are restricted and require a formal data use agreement:

- **Application:** https://healthcarestats.utah.gov/about-the-data/apcd/ — Utah DHHS Office of Health Care Statistics
- **Files used:** `fact_services_2021.txt`, `dim_member.txt`, and related APCD files
- **Format:** Pipe-delimited text files

### Shapefiles

County boundary shapefiles are from the U.S. Census Bureau TIGER/Line (public domain):

```bash
# Download 2020 county boundaries (500k resolution)
wget https://www2.census.gov/geo/tiger/GENZ2020/shp/cb_2020_us_county_500k.zip
unzip cb_2020_us_county_500k.zip -d shapefiles/
```

Or download from: https://www.census.gov/geographies/mapping-files/time-series/geo/cartographic-boundary.html
