# Data

This directory contains the analysis-ready data used by the manuscript workflow.

## Files

- `processed/analytical_dataset.csv`: curated seed morphometry and germination dataset.
- `processed/lot_locality_mapping.csv`: mapping from numeric lot identifiers to publication labels.
- `processed/data_dictionary.csv`: column definitions and source-column provenance.

## Notes

The source file included one missing `Root_Length` value. The processed dataset retains this missing value in `root_length_mm`; downstream analyses drop missing values only for the variables required by each analysis step.

The source dataset includes both an observed germination class and a root-length measurement. This repository preserves both:

- `germination_observed`: original source class.
- `germinated_root_gt_35mm`: derived class where `root_length_mm > 35.0`.

The classification workflow uses `germinated_root_gt_35mm` by default.

