# Memory-Augmented Transformers for Child Face Recognition

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Research Status](https://img.shields.io/badge/Status-IEEE%20T--BIOM%20Submission%20Ready-brightgreen.svg)](https://github.com/astoreyai/memory-augmented-transformers)
[![DOI](https://img.shields.io/badge/DOI-Pending-blue.svg)]()

## Overview

This repository contains dissertation research advancing the state-of-the-art in longitudinal child face recognition through statistical modeling and future deep learning approaches. The research addresses critical challenges in child biometric systems used for reuniting missing children with their families.

## Research Components

### 1. Beta Regression Framework (Paper 1)
**Status**: IEEE T-BIOM submission manuscript

The first paper establishes a robust statistical foundation for modeling bounded biometric performance data. Key findings:

- **Critical Discovery**: Standard linear models predict impossible accuracies exceeding 100% for older children
- **Solution**: Beta regression framework ensures all predictions remain within valid probability bounds
- **Impact**: 16-month improvement in re-enrollment timing recommendations for missing child searches
- **Validation**: 229 boundary violations eliminated while maintaining comparable model fit

**Paper**: ["Beta Regression Framework for Modeling Bounded Biometric Performance in Child Face Recognition"](beta-regression-framework/manuscript/paper.pdf)

### 2. Memory-Augmented Transformers (Future Work)
**Status**: In Development

Building on the statistical insights from Paper 1, this research will develop transformer architectures that leverage temporal patterns in child face aging:

- Memory mechanisms to capture age-specific degradation patterns
- Attention modules focused on the "golden window" of facial stability (ages 5.5-7)
- Integration of statistical priors from beta regression framework

## Repository Structure

```
memory-augmented-transformers/
├── README.md                           # This file
├── beta-regression-framework/          # Paper 1: Statistical Foundation
│   ├── manuscript/                     # IEEE T-BIOM submission materials
│   │   ├── paper.pdf                  # Full paper (10 pages)
│   │   ├── paper.tex                  # LaTeX source
│   │   └── references.bib             # Bibliography
│   ├── figures/                        # Publication-quality figures
│   ├── supplementary/                  # Additional materials
│   │   ├── notebooks/                 # Jupyter analysis notebooks
│   │   │   ├── StoreyAaron_BetaRegression.ipynb
│   │   │   └── StoreyAaron_ChildFaceAnalysis.ipynb
│   │   ├── presentations/             # Conference talks
│   │   └── references/                # Key literature
│   ├── data/                          # Data documentation
│   └── README.md                      # Detailed project description
└── memory-augmented-transformers/      # Paper 2: Deep Learning (Future)
    └── [To be developed]
```

## Quick Start

### Accessing the Research

1. **Read the Paper**: 
   ```bash
   open beta-regression-framework/manuscript/paper.pdf
   ```

2. **Explore the Analysis**:
   ```bash
   cd beta-regression-framework/supplementary/notebooks/
   jupyter notebook
   ```

3. **View Key Figures**:
   ```bash
   cd beta-regression-framework/figures/
   ls *.pdf
   ```

### Key Notebooks

- **`StoreyAaron_BetaRegression.ipynb`**: Complete statistical analysis and model comparison
- **`StoreyAaron_ChildFaceAnalysis.ipynb`**: Empirical data exploration and visualization

## Research Highlights

### Statistical Innovation
- First application of beta regression to child face recognition degradation
- Methodological guidance for practitioners working with bounded biometric data
- Discovery of age-specific "golden window" for facial stability

### Practical Impact
- Direct application to missing children search protocols
- Improved resource allocation through optimized re-enrollment schedules
- Elimination of nonsensical predictions that undermine system credibility

### Technical Contributions
- Comprehensive simulation framework calibrated to real-world data
- Implementation in both R and Python for accessibility
- Tutorial notebook for applying methods to new datasets

## Citation

If you use this research in your work, please cite:

```bibtex
@article{storey2025beta,
  title     = {Beta Regression Framework for Modeling Bounded Biometric 
               Performance in Child Face Recognition},
  author    = {Storey, Aaron W.},
  journal   = {IEEE Transactions on Biometrics, Behavior, and Identity Science},
  year      = {2025},
  note      = {Manuscript submitted for publication}
}
```

## Author

**Aaron W. Storey**  
Department of Computer Science  
Clarkson University  
Potsdam, NY 13699 USA  
Email: storeyaw@clarkson.edu  
ORCID: [0009-0009-5560-0015](https://orcid.org/0009-0009-5560-0015)

## License

This project is licensed under the MIT License - see the [LICENSE](beta-regression-framework/LICENSE) file for details.

## Acknowledgments

- Clarkson University for research support
- Authors of the Children Longitudinal Face and Young Face Aging datasets
- The biometrics community working on child protection applications

---

*This research contributes to the critical mission of reuniting missing children with their families through improved biometric modeling and recognition systems.*