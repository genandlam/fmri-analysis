

## Summary of Analysis

This repository contains a Jupyter notebook: `fmri-analysis.ipynb` .
`fmri-analysis.ipynb` follows the tutorial from [Ni-edu](https://lukas-snoek.com/NI-edu/index.html), developed by the University of Amsterdam using data from [kaggel](https://www.kaggle.com/datasets/mathurinache/3t-fmri-dataset/data).

Below is a brief summary of it's content: 

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



