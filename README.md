This is an fMRI-pattern-analysis following the tutorial from [NI-edu]((https://lukas-snoek.com/NI-edu/index.html)), developed by the University of Amsterdam using data from [kaggel](https://www.kaggle.com/datasets/mathurinache/3t-fmri-dataset/data). 

### The three parts of nifti images
Nifti images can be roughly divided into three “parts”:

1. The header with metadata;

2. The image data;

3. The affine matrix

All three parts are of course represented in nibabel’s Nifti1Image class. Let’s go through them one by one.

An example, we can visualize a single slice (e.g., [39, :, :, 0]) of the first volume ( ) as follows:
![image](https://github.com/user-attachments/assets/be332f12-a963-4a46-8ae5-7eb785b7ccbc)

we can also look at fMRI data from a different perspective, that is, from the time dimension! For example, we could extract a single voxel’s time series (i.e., how the signal intensity varies across time) and plot the signal intensity values of that voxel across time. First, let’s extract the time series of one particular voxel (e.g., the middle one across all spatial dimensions):
![image](https://github.com/user-attachments/assets/e293314d-ec20-4c03-9907-53ca62d68af9)

or can be viewed in a time series:
![image](https://github.com/user-attachments/assets/44f8d85a-80b6-4f86-9ed1-2c5438d351e3)

# The affine

an affine matrix, which relates the position of the image coordinates to real world coordinates.
![image](https://github.com/user-attachments/assets/40008f8e-1711-44de-9b4c-a0dab4df3636)

You can clearly see that the first voxel axis represents the sagittal dimension (left ←→ right), the second voxel axis represents the coronal dimension (anterior ←→ posterior), and the third voxel axis represents the axial dimension (inferior ←→ superior).

![image](https://github.com/user-attachments/assets/a27fec85-7cc3-4229-9377-5733568deefc)

The corresponding to the actual coordinate for in fmri

# Generalized linear model (GLM) in fmri analysis
Model the activation of voxels (with some minor additions) based on some design-matrix.

![image](https://github.com/user-attachments/assets/9420cab1-f955-4c09-918a-83c0549ce490)

![image](https://github.com/user-attachments/assets/92fe51bf-155e-4071-b371-560aeffdd7cf)

# The stimulis
the stimulis is made of showing images of circle of squre images. For this tutorial we lump the onsets of these two types of stimuli together in one array. This predictor thus reflects the hypothesis that the signal is affected by the presence of a stimulus (regardless of whether this was a square or a circle).

![image](https://github.com/user-attachments/assets/9ba360e9-df0b-4b56-bea7-9e3cf3154f48)

The stimulis is recorded in an array which is ploted in this graph
![image](https://github.com/user-attachments/assets/cfb622df-9098-498e-9738-aa43b1c1d295)

# Resampling
Resampling in Python can be done using the interp1d function from the scipy.interpolate package. It works by first creating a mapping between the scale of the original array and the values of the original array, and then converting the original array to a different scale. We’ll show you how this would be done with our predictor_all array.
![image](https://github.com/user-attachments/assets/47a47076-015d-4103-b094-e85013645ac2)


The stimulis graph is ploted together with the signal plot
![image](https://github.com/user-attachments/assets/f43a1ac3-63ca-4b2b-ac44-3afd131ce270)

# Using the BOLD response in GLM models
We assumed that in order to model activity in response to our stimuli, our predictor should capture an increase/decrease in activity at the moment of stimulus onset. But this is, given our knowledge of the BOLD-response, kind of unrealistic to assume: it is impossible to measure instantaneous changes in neural activity in response to stimuli or tasks with fMRI, because the BOLD-response is quite slow and usually peaks around 5-7 seconds after the ‘true’ neuronal activity (i.e. at cellular level).


# Convolution 

The figure of the HRF shows the expected idealized (noiseless) response to a single event. But how should we incorporate this HRF into our model? Traditionally, this is done using a mathematical operation called convolution. Basically, it “slides” the HRF across our 0-1 coded stimulus-vector from left to right and elementwise multiplies the HRF with the stimulus-vector.

![image](https://github.com/user-attachments/assets/75ba65e7-b0e9-41d2-8fe5-30c2698275f4)


## After adding Convolution ( with a lag of 6s) 

![image](https://github.com/user-attachments/assets/31960c4c-27e9-4449-a2ba-b00c62925f28)


![image](https://github.com/user-attachments/assets/1fae6a21-1db2-4d52-aa3f-346ee89578d1)


![image](https://github.com/user-attachments/assets/71acc5c7-578b-4c2b-bd3c-a0f358542ca5)


The data wasn't provided for the course I had to modify the existing data slighly.
