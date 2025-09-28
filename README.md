# 🧰 UK Biobank Toolbox

A lightweight, transparent, and reproducible pipeline to clean, standardize, and group UK Biobank data for epidemiological and clinical research — with a focus on **nervous system disorders** and **socioeconomic covariates**.

Designed for clarity and ease of use, this toolbox transforms raw UK Biobank field codes (`p12345`) into analysis-ready datasets with human-readable labels and clinically meaningful groupings.



---

## 📊 What Each Notebook Does

### `participant_data.ipynb`
- Renames cryptic UKB field codes (e.g., `p31` → `sex`, `p26410` → `england_imd`)
- Harmonizes **Index of Multiple Deprivation (IMD)** scores across England, Scotland, and Wales into unified columns:
  - `imd_overall`, `imd_income`, `imd_employment`, etc.
- Keeps essential covariates: age, sex, birth year, contact frequency
- Outputs a clean participant-level covariate table

### `disease_labels.ipynb`
- Uses the UK Biobank data dictionary to extract disease names from feature descriptions
- Cleans labels by removing ICD codes, extra whitespace, and standardizing casing
- Renames DataFrame columns from `p12345` → `Migraine`, `Parkinson's disease`, etc.
- Saves a mapping file (`clean_disease_mapping.csv`) for reproducibility

### `clinical_groups.ipynb`
- Groups >50 detailed neurological conditions into **9 clinically coherent categories**:
  - CNS infection & inflammation  
  - Neurodegenerative disorders  
  - Demyelinating diseases  
  - Epilepsy  
  - Headache disorders  
  - Cerebrovascular disease  
  - Peripheral nervous system disorders  
  - Paralytic/cerebral palsy syndromes  
  - Other CNS disorders  
- Creates binary flags (1 = any diagnosis in group)
- Adds a `healthy` indicator (1 = no neurological condition)
- Outputs a compact, analysis-ready phenotype matrix

---



Let me know if you'd like a GitHub repo description, a `requirements.txt` file, or a logo suggestion!
