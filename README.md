markdown
# Brain-EVs-mtDNA: EV-mtDNA and Brain Aging Biomarkers

Code and data for the manuscript **"Extracellular Vesicle-Derived Mitochondrial DNA and Brain Aging Biomarkers: A Cross-Sectional Study"**.

## 📁 Repository Structure
```
brain-evs-mtDNA/
├── data/
│   └── mtdna_deidentified.csv          # De-identified participant data (CSV format)
├── code/
│   ├── Table1_age_group_analysis.R                     # Generates Table 1: Distribution by age groups
│   ├── Figure3_correlation_analysis.R                  # Generates Figure 3: Spearman correlation heatmap
│   ├── Supplementary_Table1_baseline_traits.R          # Generates Supplementary Table 1: Baseline characteristics
│   ├── Supplementary_Table2_regression_analysis.R      # Generates Supplementary Table 2: Multivariable regression
│   └── Supplementary_Figure9_partial_correlation.R     # Generates Supplementary Figure 9: Residual partial correlation plots
├── results/
│   ├── tables/                          # Generated tables in CSV/Excel format
│   └── figures/                         # Generated figures in PDF/PNG format
├── supplementary/
│   ├── primer_sequences.txt             # Primer sequences (Supplementary Table 3)
│   └── spikein_sequence.txt             # Spike-in DNA sequence (Supplementary Table 4)
└── README.md                            # This file

## 📊 Data Description

### De-identified Data File: `data/mtdna_deidentified.csv`

This file contains de-identified participant data used for all analyses. All personally identifiable information has been removed.

**Key Variables Included:**

| Column Name | Description | Units/Format |
|-------------|-------------|--------------|
| `age` | Participant age | Years |
| `age_group` | Age category (0=20-40, 1=41-65, 2=66-90) | Categorical |
| `sex` | Sex (1=Male, 2=Female) | Categorical |
| `MT_ND1` | EV-derived mitochondrial ND1 gene copies | Copies/mL |
| `MT_CO3` | EV-derived mitochondrial CO3 gene copies | Copies/mL |
| `Dloop` | EV-derived mitochondrial D-loop copies | Copies/mL |
| `NfL` | Neurofilament Light Chain | pg/mL |
| `Aβ42` | Amyloid-beta 42 | pg/mL |
| `Aβ40` | Amyloid-beta 40 | pg/mL |
| `pTau181` | Phosphorylated Tau181 | pg/mL |
| `Aβ42_Aβ40` | Aβ42/Aβ40 ratio | Ratio |
| `eGFR` | Estimated glomerular filtration rate | mL/min |
| `ALT` | Alanine aminotransferase | U/L |

*Additional clinical and laboratory variables as described in Supplementary Table 1 of the manuscript are also included.*

**Note:** The dataset has been fully de-identified. Missing values are represented as empty cells.

## 🧬 Primer and Sequence Information

Primer sequences (Supplementary Table 3) and the exogenous spike-in DNA sequence (Supplementary Table 4) are provided in the `supplementary/` directory.

## 🔧 Software Requirements

### R Environment
- **R version**: ≥ 4.0.0
- **Required packages** (will be installed automatically by the scripts):
  - `tidyverse`, `broom`, `Hmisc`, `corrplot`, `ggpubr`
  - `flextable`, `officer`, `naniar`, `car`, `patchwork`, `openxlsx`, `readxl`
Note: Each R script in the code/ directory begins by checking for and installing any missing required packages, ensuring full reproducibility.

## 🚀 How to Reproduce the Analysis

### 1. Clone the Repository
```bash
git clone https://github.com/Yuqian60/Brain-EVs-mtDNA.git
cd Brain-EVs-mtDNA
2. Install R Dependencies
Run the following command in R to install required packages (or let the scripts handle it):

r
install.packages(c("tidyverse", "dplyr", "broom", "Hmisc", "corrplot",
                   "ggplot2", "ggpubr", "flextable", "officer", "naniar",
                   "car", "patchwork", "openxlsx", "readxl"))
3. Run Analysis Scripts
Execute the R scripts in the code/ directory in any order. Each is self-contained.

Example:

r
source("code/Supplementary_Table1_baseline_traits.R")
This will generate Supplementary_Table1_Baseline_Traits.xlsx in the results/tables/ folder.

4. Output
All generated tables and figures will be saved in the results/ directory.

🔬 Experimental Methods Summary
For complete details, refer to the manuscript. Briefly:

EV Isolation: Plasma EVs were isolated by [Describe method briefly, e.g., "size-exclusion chromatography"].

mtDNA Extraction & Quantification: DNA was extracted using the [Kit Name] kit and quantified via qPCR.

Biomarker Measurement: Plasma biomarkers (Aβ40, Aβ42, pTau181, NfL) were measured using the [Platform/Assay Name] platform.

Statistical Analysis: All analyses were performed in R (version 4.x) using two-tailed tests with α=0.05, applying Benjamini-Hochberg correction for multiple testing where appropriate.

🙏 Acknowledgments
We thank all study participants and clinical staff. This work was supported by:

Taishan Scholars Program of Shandong Province (tsqnz20240852)

Jinan Clinical Medical Science and Technology Innovation Plan (202134029)

Key Technology Research and Development Program of Shandong Province (2022CXGC010507)
