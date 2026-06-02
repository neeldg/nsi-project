# Neighborhood Stability Index (NSI)

A perturbation-based method for quantifying cellular neighborhood robustness in multiplexed imaging data.

## Overview

NSI systematically removes each cell type from a cellular neighborhood and measures the resulting compositional shift using Jensen-Shannon divergence. It produces both a scalar stability score and a per-cell-type profile vector, enabling spatial mapping of neighborhood fragility across tissue sections.

## Biological Motivation

Cellular neighborhoods in tumor tissue determine immune cell function more reliably than individual cell type frequencies. This project asks: how much does a neighborhood's identity depend on any given cell type? Neighborhoods that collapse under single cell type removal are structurally fragile -- high-value therapeutic targets.

## Data

Uses the SPACEc tonsil CODEX demo dataset (healthy + tonsillitis). Download from:
https://datadryad.org/dataset/doi:10.5061/dryad.brv15dvj1

Place the processed h5ad file at: `data/adata_nn_demo_tonsil.h5ad`

## Structure



cat > ~/nsi-project/README.md << 'EOF'
# Neighborhood Stability Index (NSI)

A perturbation-based method for quantifying cellular neighborhood robustness in multiplexed imaging data.

## Overview

NSI systematically removes each cell type from a cellular neighborhood and measures the resulting compositional shift using Jensen-Shannon divergence. It produces both a scalar stability score and a per-cell-type profile vector, enabling spatial mapping of neighborhood fragility across tissue sections.

## Biological Motivation

Cellular neighborhoods in tumor tissue determine immune cell function more reliably than individual cell type frequencies. This project asks: how much does a neighborhood's identity depend on any given cell type? Neighborhoods that collapse under single cell type removal are structurally fragile -- high-value therapeutic targets.

## Data

Uses the SPACEc tonsil CODEX demo dataset (healthy + tonsillitis). Download from:
https://datadryad.org/dataset/doi:10.5061/dryad.brv15dvj1

Place the processed h5ad file at: `data/adata_nn_demPlace the processed h5ad file at: ├── nsi/                  # core package
│   ├── composition.py    # composition vector utilities
│   ├── perturbation.py   # perturbation engine
│   ├── classify.py       # outcome classification
│   ├── metrics.py        # NSI profile and scalar
│   └── visualize.py      # spatial heatmap utilities
├── notebooks/            # exploration and validation notebooks
├── decision_log.md       # methodological decisions and rationale
└── README.md

## Environment

```bash
conda create -n nsi-env python=3.10 -y
conda activate nsi-env
pip install numpy pandas scipy scikit-learn matplotlib seaborn anndata scanpy jupyter
```

## Status

- [x] Environment setup
- [x] Data exploration
- [ ] Perturbation engine
- [ ] NSI profile and scalar
- [ ] Validation against tonsil biology
- [ ] Local NSI (spatial heatmaps)

## Credit
This project was made by Neel Dutta Gupta.
