# Data

This directory contains small, reproducible datasets used by the optimization experiments.

Expected datasets include:

- `demand.csv`
- `prices.csv`
- `solar.csv`
- `workloads.csv`

The project will initially use synthetic data so that experiments are fully reproducible.

For every dataset, document:

- Units
- Time resolution
- Generation method or source
- Meaning of each column
- Assumptions
- Random seed, when applicable

Large datasets should not be committed directly to Git.

If larger external datasets are introduced later, document how to obtain or regenerate them.