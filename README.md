# Multilingual Audio Classification and Clustering

Machine Learning final project from the **University of Tehran**.

This project develops an end-to-end classical machine-learning pipeline for multilingual audio analysis, combining signal preprocessing, acoustic feature extraction, supervised classification, unsupervised clustering, and speaker-aware evaluation.

This was a **team course project**. The repository preserves the submitted work and its original Git history without implying sole authorship of all team contributions.

## Project Pipeline

### 1. Audio Cleaning and Feature Extraction

`Data_Cleaning_and_Feature_Extraction.ipynb` implements:

- audio loading and resampling;
- silence trimming;
- RMS normalization;
- peak protection;
- fixed-duration padding/trimming;
- optional data augmentation;
- time shifting;
- additive noise;
- time stretching;
- pitch shifting;
- gain augmentation.

Acoustic features include:

- MFCCs;
- first- and second-order MFCC deltas;
- Mel spectrogram features;
- zero-crossing rate;
- RMS energy;
- spectral centroid;
- spectral bandwidth;
- spectral rolloff;
- spectral contrast;
- statistical summaries such as skewness and kurtosis.

The extracted fixed-dimensional representations are stored in `artifacts/` for the later notebooks.

### 2. Classification

`Classification.ipynb` compares preprocessing and classification pipelines.

Dimensionality-reduction alternatives include:

- PCA;
- LDA;
- PCA followed by LDA.

Classifiers include:

- Support Vector Machine;
- Gaussian Naive Bayes;
- Logistic Regression;
- Random Forest.

The workflow uses cross-validation for pipeline/model selection and evaluates the selected models on held-out data.

Additional experiments study cross-gender generalization and augmentation.

### 3. Unsupervised Clustering

`Clustering.ipynb` explores whether the extracted audio features naturally separate into meaningful groups.

The workflow includes:

- feature standardization;
- PCA;
- K-Means;
- Agglomerative Clustering;
- elbow analysis;
- silhouette analysis;
- two- and three-dimensional cluster visualization.

### 4. Evaluation

`Evaluation.ipynb` evaluates both clustering and classification.

Metrics and analyses include:

- silhouette score;
- cluster purity;
- cluster composition;
- accuracy;
- precision;
- recall;
- Macro-F1;
- weighted F1;
- confusion matrices;
- comparison across classification strategies.

### 5. Speaker-Aware Classification

`classification_with_clustering.ipynb` implements an additional speaker-aware workflow designed to reduce speaker leakage.

The method uses:

- unsupervised clustering to infer speaker groups;
- Leave-One-Group-Out cross-validation;
- PCA/LDA preprocessing alternatives;
- model-specific hyperparameter tuning;
- SVM, Naive Bayes, Logistic Regression, and Random Forest.

## Repository Structure

- `Data_Cleaning_and_Feature_Extraction.ipynb`
- `Classification.ipynb`
- `Clustering.ipynb`
- `Evaluation.ipynb`
- `classification_with_clustering.ipynb`
- `artifacts/` — compact derived features used by downstream notebooks
- `Report/` — report source and project-generated figures

## Data

The original raw audio dataset is not redistributed here.

Compact feature representations produced during the project are retained so that the classification and clustering portions can be inspected and, where possible, reproduced without committing the full audio dataset.

## Suggested Notebook Order

1. `Data_Cleaning_and_Feature_Extraction.ipynb`
2. `Classification.ipynb`
3. `Clustering.ipynb`
4. `Evaluation.ipynb`

`classification_with_clustering.ipynb` represents an additional speaker-aware classification experiment.

## Technologies

- Python
- NumPy
- pandas
- SciPy
- librosa
- scikit-learn
- Matplotlib
- Seaborn
- soundfile
- joblib

## Portfolio Cleanup

The repository retains its original development history.

For portfolio presentation, the current tree excludes compiled LaTeX auxiliary files, serialized trained models, redundant generated result artifacts, macOS metadata, and course-assignment PDFs.

The five notebooks in the current version are taken from the collected final course submission.
