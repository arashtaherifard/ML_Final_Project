# Derived Feature Artifacts

This directory retains the compact derived data needed by the downstream machine-learning notebooks.

The raw audio dataset is not distributed in this repository.

Preserved artifacts may include:

- `X.npy` — extracted acoustic feature matrix
- `y.npy` — corresponding target labels
- `features.csv` — feature metadata
- `metadata.csv` — indexed sample metadata

Model files, predictions, clustering outputs, and other results that can be regenerated from the notebooks are intentionally excluded.
