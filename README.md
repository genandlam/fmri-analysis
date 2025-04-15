

## Summary of Analysis

This repository contains two main Jupyter notebooks: `fmri-analysis.ipynb` and `functional_connectivity+prediction.ipynb`.
`fmri-analysis.ipynb` followes the tutorial from [Ni-edu](https://lukas-snoek.com/NI-edu/index.html), developed by the University of Amsterdam using data from [kaggel](https://www.kaggle.com/datasets/mathurinache/3t-fmri-dataset/data). `functional_connectivity+prediction.ipynb` followes the tutorial from [NI-edu](https://nilearn.github.io/dev/auto_examples/03_connectivity/plot_group_level_connectivity.html) and resting-state fMRI data from [Natural Scenes Dataset](https://naturalscenesdataset.org/)

Below is a brief summary of their contents:

### `fmri-analysis.ipynb`
This notebook provides an introduction to fMRI data analysis, focusing on the following key topics:
- **NIfTI Image Components**: Explains the three main parts of NIfTI images: metadata (header), image data, and the affine matrix.
- **Visualization**: Demonstrates how to visualize slices of fMRI data and extract voxel time series for analysis.
- **Affine Matrix**: Describes how the affine matrix maps voxel coordinates to real-world coordinates.
- **Generalized Linear Model (GLM)**: Introduces GLM for modeling voxel activation based on a design matrix.
- **Stimuli Representation**: Explains how stimuli are represented and processed for analysis.
- **Resampling**: Covers resampling techniques using `scipy.interpolate` to adjust data scales.
- **BOLD Response**: Discusses the delayed nature of the BOLD response and its implications for modeling.
- **Convolution**: Explains how the Hemodynamic Response Function (HRF) is incorporated into models using convolution.
![image](https://github.com/user-attachments/assets/bf3e0dc7-bfc8-4237-9c24-8866d234832b)

### `functional_connectivity+prediction.ipynb`
This notebook focuses on functional connectivity and prediction tasks in fMRI data analysis:
- **Functional Connectivity**: Explores methods to compute connectivity between brain regions using correlation matrices.
- **Feature Extraction**: Demonstrates how to extract features from connectivity matrices for machine learning tasks.
- **Prediction Models**: Implements predictive models (e.g., regression or classification) to analyze relationships between brain connectivity and behavioral or clinical outcomes.
- **Evaluation**: Provides techniques for evaluating model performance using metrics such as accuracy, precision, and recall.

These notebooks serve as a practical guide for fMRI data analysis, combining theoretical concepts with hands-on implementation.

## Functional Connectivity Graphs
![image](https://github.com/user-attachments/assets/fafae9c0-0b22-45da-acb7-5335e1ac7aa9)

## F1 Scores of various algorthims ( Passive Aggressive Classifier (PA), Decision Tree, KNeighbors Classifier(KNN), RandomForestClassifier(RF), LogisticRegression (MLP), SVC)
![image](https://github.com/user-attachments/assets/bccf8ae4-fb56-4601-abff-352be9392c6e)



