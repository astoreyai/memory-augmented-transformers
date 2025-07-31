# Beta Regression Framework for Child Face Recognition

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXX)

This repository contains the research materials, implementation code, and manuscript for the beta regression framework applied to longitudinal child face recognition systems.

## Overview

Child face recognition serves a critical social mission—reuniting missing children with their families. This research addresses a methodological concern: when standard linear mixed models are inappropriately applied directly to bounded data, they can predict physically impossible recognition rates, exceeding **100% accuracy** for older children. Our beta regression framework ensures all predictions remain within valid probability bounds while providing better variance modeling and operational insights.

**Paper Status**: Manuscript prepared following IEEE T-BIOM guidelines.

## Key Finding

> **"Linear mixed models produced 229 invalid predictions exceeding 100% accuracy in our simulations, while beta regression maintained 100% valid predictions throughout."**

## Simulation Details

The synthetic dataset was generated using:
```
TAR_ij = logit^(-1)(β₀ + β₁·age_i + β₂·ΔT_ij + β₃·age_i×ΔT_ij + u_i + ε_ij)
```
where u_i ~ N(0, 0.15²) and ε_ij ~ N(0, 0.10²), with age-specific β₂ values: -0.35 (young), -0.08 (middle), -0.20 (older).

## Key Contributions

1. **Methodological Guidance**: Shows when and how to use beta regression for bounded biometric data
2. **Pedagogical Demonstration**: Illustrates risks when linear models are misapplied to bounded data
3. **Discovers Operational Insights**: "Golden window" of facial stability (ages 5.5-7)
4. **Enables Better Decisions**: 16-month improvement in re-enrollment timing for missing child searches

## Repository Structure

```
BetaRegression_Framework/
├── manuscript/              # Paper manuscript
│   ├── paper.tex           # Main LaTeX source (10 pages)
│   ├── paper.pdf           # Compiled paper (1.5MB)
│   ├── references.bib      # Bibliography
│   ├── compile_paper.sh    # Compilation script
│   └── compile_paper.sh    # Compilation script
├── figures/                 # All publication figures
│   ├── age_patterns.pdf
│   ├── boundary_violations.pdf
│   ├── beta_regression_concepts.pdf
│   ├── variance_analysis.pdf
│   ├── prediction_intervals.pdf
│   └── operational_impact.pdf
├── data/                    # Data information (see data/README.md)
├── supplementary/           # Additional materials
│   ├── notebooks/          # Jupyter notebooks with analysis code
│   ├── presentations/      # Conference talks and slides
│   └── references/         # Key papers referenced
├── LICENSE                  # MIT License
└── README.md               # This file
```

## Paper Details

**Title**: "Beta Regression Framework for Modeling Bounded Biometric Performance in Child Face Recognition"

**Authors**: Aaron W. Storey

**Target Journal**: IEEE Transactions on Biometrics, Behavior, and Identity Science (T-BIOM)

**Keywords**: Biometric evaluation, bounded outcomes, beta regression, child face recognition, longitudinal analysis, variance modeling, statistical methods

**Abstract**: Child face recognition systems degrade over time, yet standard statistical models can produce nonsensical predictions when modeling this degradation. This paper examines beta regression as an alternative approach for bounded biometric performance metrics. Building on empirical work by Deb et al. and Bahmani et al., this analysis identifies a methodological gap: while these studies appropriately use standardized scores, practitioners often need to model raw recognition rates for operational decisions. The simulations show that linear mixed models applied to bounded data can predict impossible values---in one case exceeding 100% true accept rate. Beta regression eliminates these violations while maintaining comparable fit. The approach captures age-dependent patterns naturally: young children (ages 3-5) show rapid performance decline, middle childhood (5.5-7 years) exhibits surprising stability near 80%, and older children experience delayed degradation after puberty onset. Perhaps most importantly for operational systems, beta regression correctly models the variance structure of bounded data, with uncertainty peaking at 50% performance. This has practical implications---the analysis suggests the stable middle-age group could use extended re-enrollment intervals, potentially improving resource allocation for missing child searches. Implementation code and guidelines are provided for when this approach offers advantages over traditional methods. Available at: https://github.com/astoreyai/memory-augmented-transformers.

## Quick Start

### Prerequisites
- Python (≥ 3.8) with scientific computing libraries
- LaTeX distribution (for reproducing manuscript)

### Implementation
The beta regression framework is implemented using Python's statsmodels library. See the Jupyter notebooks in `supplementary/notebooks/` for complete analysis code:

#### Interactive Notebooks

| Notebook | Description | Run in Colab |
|----------|-------------|--------------|
| **StoreyAaron_BetaRegression.ipynb** | Complete statistical analysis and model comparison | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/astoreyai/memory-augmented-transformers/blob/main/beta-regression-framework/supplementary/notebooks/StoreyAaron_BetaRegression.ipynb) |
| **StoreyAaron_ChildFaceAnalysis.ipynb** | Empirical data exploration and visualization | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/astoreyai/memory-augmented-transformers/blob/main/beta-regression-framework/supplementary/notebooks/StoreyAaron_ChildFaceAnalysis.ipynb) |

## Key Results

### Age-Specific Degradation Patterns
- **Young children (3-5 years)**: Rapid decline from 97.8% to 63.1%
- **Middle children (5.5-7 years)**: Remarkable stability around 80% ("Golden Window")
- **Older children (7.5-9 years)**: Delayed degradation after 4 years

### Model Comparison
| Model | RMSE | R² | Invalid Predictions | Max Violation |
|-------|------|-----|-------------------|---------------|
| Linear Mixed | 0.0649 | 0.7600 | 229 | >100% |
| Beta Regression | 0.0665 | 0.7479 | 0 | — |

### Operational Impact
- 16-month improvement in re-enrollment timing for stable age group
- Elimination of impossible predictions maintains system credibility
- Direct support for missing children search protocols

## Citation

Please cite this work as:

### BibTeX
```bibtex
@article{storey2025beta,
  title     = {Beta Regression Framework for Modeling Bounded Biometric Performance in Child Face Recognition},
  author    = {Storey, Aaron W.},
  journal   = {IEEE Transactions on Biometrics, Behavior, and Identity Science},
  year      = {2025},
  volume    = {},
  number    = {},
  pages     = {},
  doi       = {},
  note      = {Under review at Clarkson, for submission to IEEE T-BIOM}
}
```

### APA Format
Storey, A. W. (2025). Beta regression framework for modeling bounded biometric performance in child face recognition. *IEEE Transactions on Biometrics, Behavior, and Identity Science*. Under review at Clarkson, for submission to IEEE T-BIOM.

### Plain Text
Aaron W. Storey. "Beta Regression Framework for Modeling Bounded Biometric Performance in Child Face Recognition." IEEE Transactions on Biometrics, Behavior, and Identity Science, 2025. Under review at Clarkson, for submission to IEEE T-BIOM.

## Reproducibility

All results in this paper can be reproduced using:
1. **Jupyter Notebooks**: See `supplementary/notebooks/` for complete analysis
2. **LaTeX Source**: Compile `manuscript/paper.tex` to reproduce the paper
3. **Figures**: All figures in `figures/` are generated from the analysis
4. **Simulation Code**: Python implementations of the simulation code, synthetic datasets calibrated to match YFA patterns, and beta regression model fitting using Python's statsmodels library
5. **Tutorial**: Hands-on tutorial notebook guides readers through applying these methods to their own longitudinal biometric data

## Future Work

- **Paper 2**: Empirical validation on real Children Face Aging dataset
- **Paper 3**: Memory-augmented transformers leveraging these statistical insights
- **Software Package**: Python package for biometric beta regression
- **GitHub Repository**: Implementation code available at https://github.com/astoreyai/memory-augmented-transformers

## Contact

**Aaron W. Storey**  
Department of Computer Science  
Clarkson University  
Potsdam, NY 13699 USA  
Email: storeyaw@clarkson.edu  
ORCID: [0009-0009-5560-0015](https://orcid.org/0009-0009-5560-0015)

## License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file for details.

## Acknowledgments

- Clarkson University for research support
- Authors of the Children Longitudinal Face (Deb et al., 2018) and Young Face Aging (Bahmani et al., 2023) datasets
- IEEE T-BIOM community for research standards

## Related Datasets

For researchers interested in validating these methods:
- **Children Longitudinal Face (CLF)**: [Contact Deb et al.](mailto:)
- **Young Face Aging (YFA)**: [Contact Bahmani et al.](mailto:)

---

*This research contributes to the critical mission of reuniting missing children with their families through improved biometric modeling.*