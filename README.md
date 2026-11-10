<div align="center">

# Computational Investigation of Radiation-Induced Vacancy Formation and Multi-Objective Screening of Inorganic Halide Perovskites

**Abiha Saqib**

[![Python](https://img.shields.io/badge/Python-Scientific%20Computing-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-F37626?logo=jupyter&logoColor=white)](notebooks/)
[![License: MIT](https://img.shields.io/badge/Code%20License-MIT-green.svg)](LICENSE)
[![Latest commit](https://img.shields.io/github/last-commit/abihasaqib24-lab/perovskite-radiation-study)](https://github.com/abihasaqib24-lab/perovskite-radiation-study/commits/main)
[![Repository](https://img.shields.io/badge/Repository-GitHub-24292f?logo=github)](https://github.com/abihasaqib24-lab/perovskite-radiation-study)

**Radiation-defect modeling · Materials informatics · Pareto screening**

[Read the manuscript](Research%20Paper/) · [Explore notebooks](notebooks/) · [See figures](figures/) · [Browse results](results/)

</div>

---

## Overview

This repository documents a computational investigation of proton-induced vacancy distributions and electronic/thermodynamic screening of inorganic halide perovskites. The study contains two **complementary, distinct** analyses:

- **Phase 1 — Radiation-defect analysis:** Existing simulation profiles for **CsPbI₃** and **Cs₃Sb₂I₉** were analyzed at **20, 50, 100, and 500 keV**. A multi-output multilayer perceptron (MLP) was evaluated using entire held-out energy profiles and compared with simple baselines.
- **Phase 2 — Materials screening:** **15 Materials Project phase records** across **seven compositions** were examined using calculated band gaps, energy above hull, two-objective Pareto analysis, and sensitivity testing.

The two streams inform research priorities; the Phase 1 MLP was **not** used to predict irradiation behavior of new compositions.

## Research at a glance

| Radiation analysis | Materials screening |
|---|---|
| 2 studied materials | 7 queried compositions |
| 4 proton energies | 15 phase records |
| 8 material–energy profiles | 30 sensitivity scenarios |
| 796 depth observations | Phase-specific Pareto results |

### Main observations

- Reported vacancy maxima generally move deeper between **20 and 100 keV**; several 500 keV maxima approach the recorded depth boundary.
- The improved MLP reduces prediction error in several held-out conditions, but the **zero-vacancy baseline outperforms it at 500 keV**.
- Under the investigated screening objectives, **Cs₂AgInCl₆ (mp-1096926)** and **Cs₃Sb₂I₉ (mp-541014)** are noteworthy Pareto candidates.
- **Pareto selection is not evidence of radiation hardness.** Original simulation normalization and some irradiation metadata still require verification.

## Repository contents

```text
perovskite-radiation-study/
├── data/                   # Raw, cleaned and external materials records
├── notebooks/              # Radiation-modeling and materials-screening workflows
├── results/                # Model metrics, profile descriptors and Pareto tables
├── figures/                # Paper figures (PNG and PDF)
├── Research Paper/          # Manuscript PDF and LaTeX files (if present)
├── README.md
└── LICENSE                 # MIT license for original code only
```

> Folder names reflect the existing repository. See individual notebook cells for the expected input paths. The `Research Paper/` folder may be renamed to `paper/` after updating links accordingly.

## Reproducing the analysis

1. Clone the repository and create a Python environment.
2. Install the dependencies used by the notebooks (NumPy, pandas, SciPy, Matplotlib, scikit-learn, TensorFlow, openpyxl, and for Phase 2 `mp-api`/`pymatgen`). Prefer the tested environment versions documented with the project.
3. Run the radiation notebook before the materials-screening notebook, following the file paths indicated there.
4. Materials Project data retrieval requires an API key supplied at runtime; **do not commit credentials**.

The notebooks and existing result tables are the source of truth for numerical analysis. Training uses the underlying simulation observations, not measurements performed by this repository.

## Scientific scope and limitations

Only **eight material–energy profiles** are available for radiation modeling; observations along the same profile are correlated. Held-out-energy evaluations probe energy transfer, not generalization to new chemical compositions. Integrated profiles are numerical descriptors until the original simulation units and normalization are verified. Calculated DFT band gaps are not automatically experimental optical gaps or photovoltaic performance metrics.

## Data and code availability

The repository provides research notebooks and associated outputs as available. Original simulation data may be redistributed only with appropriate permission. The source code license does not cover third-party data or the manuscript.

## Generative AI disclosure

Generative AI tools assisted with debugging, code organization, visualization refinement, and manuscript editing; the author is responsible for verifying all scientific analyses, interpretations, and conclusions.

## License

Original code is available under the [MIT License](LICENSE). Dataset and manuscript rights are separate.
