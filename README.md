# Poverty Index Construction and 4Ps Program Efficiency Analysis

A multi-method statistical study using Philippine household survey data to construct
a composite poverty index and evaluate the effectiveness of the Pantawid Pamilyang
Pilipino Program (4Ps) across regions and provinces.

---

## Methodology Overview

```
Objective 1                     Objective 2
───────────────────────────      ───────────────────────────────────
23 Binary Utilities/Assets  →   13 Poor Indicator Variables
Variables (FIES 2023)            (FIES 2023)
        ↓                               ↓
Index Construction:              Binary Logistic Regression Model
Multiple Correspondence                 ↓
Analysis (MCA)              Variable Selection: Recursive Feature
        ↓                        Elimination (RFE)
  2023 Poor Index ──────────────────────────↓
                                            ↓
                          Objective 3
                          ────────────────────────────────────────
                          2023 Poor Index (from Obj 1 & 2)
                          2021 Poor Index     (NHTS-PR 2021)
                          2-Year 4Ps Penetration
                          2021 & 2023 Population
                                            ↓
                          Negative Binomial Loglinear Model
                                            ↓
Objective 4                                 ↓
────────────────────────────────────────────↓
6 Budget Allocation Variables (NEP 2021)
[EXPLORATORY]
        ↓
Negative Binomial Loglinear Model
(DepEd / DOLE / DSWD)
```

---

## Repository Structure

```
.
├── poverty_analysis_combined.Rmd   # Main analysis script (all 4 objectives)
├── README.md                       # This file
└── data/
    └── README.md                   # Data availability & access instructions
```

---

## Requirements

### R Version
R ≥ 4.2.0

### Packages

| Group | Packages |
|-------|----------|
| Data I/O | `readr`, `readxl`, `writexl`, `data.table` |
| Manipulation | `dplyr`, `tidyr`, `stringr`, `purrr`, `tibble` |
| Modelling | `car`, `caret`, `pROC`, `DescTools`, `ResourceSelection`, `MASS`, `AER`, `glmmTMB`, `performance`, `DHARMa` |
| MCA | `FactoMineR`, `factoextra` |
| Missing Data | `mice` |
| Visualization | `ggplot2`, `ggthemes`, `corrplot`, `gridExtra`, `DT` |

Install all at once:
```r
pkgs <- c(
  "readr", "readxl", "writexl", "data.table", "dplyr", "tidyr", "stringr",
  "purrr", "tibble", "psych", "MASS", "car", "caret", "pROC",
  "ResourceSelection", "DescTools", "AER", "glmmTMB", "performance",
  "DHARMa", "FactoMineR", "factoextra", "mice", "ggplot2", "ggthemes",
  "corrplot", "gridExtra", "DT"
)
install.packages(pkgs)
```

---

## Data

All datasets are proprietary and **not included** in this repository.  
See [`data/README.md`](data/README.md) for source information and access instructions.

---

## How to Run

1. Clone the repository
2. Obtain the required datasets (see `data/README.md`) and place them in the `data/` folder
3. Open `poverty_analysis_combined.Rmd` in RStudio
4. Click **Knit** (or run `rmarkdown::render("poverty_analysis_combined.Rmd")`)
