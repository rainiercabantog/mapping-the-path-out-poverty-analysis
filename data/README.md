# Data Files

The following files are required to run the analysis. They are **not included**
in this repository as they contain restricted microdata.

---

## Required Files

Place all files directly in this `data/` folder.

| Filename | Source | Description | Objective |
|----------|--------|-------------|-----------|
| `FIES_expenditure_data.xlsx` | PSA — Family Income and Expenditure Survey (FIES) 2023 | Household-level expenditure on 23 utilities/assets categories (used to construct binary MCA indicators) | 1 |
| `FIES_logit_data.xlsx` | PSA — FIES 2023 | Household-level socioeconomic variables (income, wages, family size, demographics) | 1, 2 |
| `logistic_data.xlsx` | Derived from FIES 2023 | Pre-processed modeling dataset for BLRM (numeric covariates, top-coded variables, MCA binary label) | 2 |
| `NHTS_4PS_data.xlsx` | DSWD — National Household Targeting System (NHTS-PR) 2021 | Province-level 4Ps beneficiary counts, 2021 poor population estimates, 2021 & 2023 population figures | 3 |
| `NEP_budget_data.xlsx` | DBM — National Expenditure Program (NEP) 2021 | Regional budget allocation sub-components for DepEd, DOH, DOLE, and DSWD | 4 |

---

## Data Access

| Dataset | Access |
|---------|--------|
| FIES 2023 | Available upon request from the [Philippine Statistics Authority (PSA)](https://psa.gov.ph) |
| NHTS-PR 2021 | Available upon request from the [Department of Social Welfare and Development (DSWD)](https://dswd.gov.ph) |
| NEP 2021 | Publicly available from the [Department of Budget and Management (DBM)](https://www.dbm.gov.ph) |

---

## Variable Notes

- `MEM_RFACT`: Household expansion factor (used to weight poor counts to population level)
- `income_q`: Income quintile identifier (1 = lowest, 5 = highest)
- `W_REGN`, `W_PROV`: PSA region and province codes (numeric)
- Budget columns follow the convention `Col_N_Agency_Component` where `N` is the column index
