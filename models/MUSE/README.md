## MUSE: Segmentation of anatomical regions of interest (ROIs)

## Description

MUSE is a DeepMRSeg model trained for segmenting the brain into 153 anatomical regions of interest (ROIs). MUSE algorithm was initially developed as a multi-atlas registration and label fusion based segmentation method [_[1]_](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4806537). The multi-site training dataset included T1-weighted scans of a large number of subjects. Ground-truth labels of these images for the 4 tissue types were automatically calculated and verified for quality prior to model training.

## Usage

The MUSE model can be easily applied for segmenting a single or multiple T1 images using the tools provided as part of the [DeepMRSeg package](https://github.com/CBICA/DeepMRSeg). 

__Important:__ 

- MUSE model was trained using a set of T1 images that were skull-stripped using the DLICV model as a pre-processing step. Accordingly, the suggested usage on raw T1 images is to apply first the DLICV model, mask the image with the output mask, and then apply the MUSE model. However, it can also be applied directly if the user has an already skull-stripped image.

- MUSE segmentation using DeepMRSeg is work in progress. As such, the method has not been thoroughly validated yet. Final results may include segmentation errors or the model may fail, depending on the input data. We recommend users not to use it for their subsequent MRI data analyses.

- A dictionary with the indices and names of the ROI labels is provided inside the model folder (configs/ROI_Indices.csv)

For usage, please see the [usage info](https://github.com/CBICA/DeepMRSeg#usage) in DeepMRSeg README.


### Contact
For more information, please contact <a href="mailto:software@cbica.upenn.edu">CBICA Software</a>.
