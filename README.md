# Genipa Seed Digital Phenotyping

Reproducible analysis repository for digital phenotyping of *Genipa americana* seeds and germination classification. The workflow was organized for linkage with an MDPI manuscript and is centered on a self-contained Jupyter notebook that performs data validation, statistical analysis, machine-learning classification, figure generation, and output-table export.

## Repository Structure

```text
genipa-seed-digital-phenotyping/
├── data/processed/              # Curated analysis-ready CSV files
├── notebooks/                   # Self-contained reproducible notebook
├── figures/                     # Manuscript-ready PDF figures and PNG previews
└── outputs/                     # Model and statistical result tables
```

## Analysis Overview

The self-contained notebook pipeline:

1. Standardizes the seed morphometry and germination dataset.
2. Removes morphometric outliers using the 1.5 IQR rule for analysis.
3. Tests lot effects on seed traits using MANOVA.
4. Performs PCA using length, width, area, and perimeter.
5. Classifies germination using Random Forest and Linear SVM.
6. Exports MDPI-style PDF figures and CSV result tables.

The classification workflow uses `germinated_root_gt_35mm` as the default target, matching the threshold-based germination definition used in the source notebook. The source `Germination` column is retained as `germination_observed` in the analytical dataset.

## Quick Start

Create the environment:

```bash
conda env create -f environment.yml
conda activate genipa-seed-digital-phenotyping
```

Or install with pip:

```bash
python -m pip install -r requirements.txt
```

Open and run the self-contained notebook:

```bash
jupyter notebook notebooks/analysis_pipeline_self_contained.ipynb
```

The notebook is designed to be the primary reproducible artifact for GitHub and manuscript review:

```text
notebooks/analysis_pipeline_self_contained.ipynb
```

It does not call external project scripts. All analysis functions, model definitions, plotting utilities, and figure-display helpers are defined inside the notebook.

## Data

The processed dataset is stored at `data/processed/analytical_dataset.csv`. Column definitions are available in `data/processed/data_dictionary.csv`.

Lot-to-locality labels are stored in `data/processed/lot_locality_mapping.csv`. The source CSV did not include full locality names, so the `locality_name` field should be updated before public release if geographic metadata will be disclosed in the manuscript.

## Citation

Please cite the associated article and this repository using the metadata in `CITATION.cff`. Update the placeholder author and manuscript fields before release.
