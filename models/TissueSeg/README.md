## TissueSeg: Tissue Segmentation

## Description

TissueSeg is a DeepMRSeg model trained for segmenting the brain into 4 tissue types: gray matter (GM), white matter (WM), ventricles (VN) and cortical cerebro-spinal fluid (CSF). The multi-site training dataset included T1-weighted scans of a large number of subjects. Ground-truth labels of these images for the 4 tissue types were automatically calculated and verified for quality prior to model training.

## Usage

The TissueSeg model can be easily applied for segmenting a single or multiple T1 images using the tools provided as part of the [DeepMRSeg package](https://github.com/CBICA/DeepMRSeg). 

__Important:__ 

- TissueSeg model was trained using a set of T1 images that were skull-stripped using the DLICV model. Accordingly, the suggested usage on raw T1 images is to apply first the DLICV model, mask the image with the output mask, and then apply the TissueSeg model. However, it can also be applied directly if the user has an already skull-stripped image.

- A dictionary with the indices and names of the output labels is provided inside the model folder (configs/ROI_Indices.csv)

```
# After installing DeepMRSeg

# Download pre-trained model
deepmrseg_downloadmodel --model tissueseg

# Process single subject
deepmrseg_apply --task tissueseg --inImg subj1_T1_BrainOrICV.nii.gz --outImg subj1_T1_SEG.nii.gz

# Batch processing of multiple subjects using a subject list
#   User provides a csv file with columns: ID,InputT1,OutputImage
deepmrseg_apply --task tissueseg --sList subjectList.csv

# Batch processing of multiple subjects in input folder 
#   Testing is applied individually to all images with the given suffix in the input folder
deepmrseg_apply --task tissueseg --inDir myindir --outDir myoutdir --inSuff _T1_BrainOrICV.nii.gz --outSuff _SEG.nii.gz

# Using the deepmrseg_test command:
deepmrseg_test --mdlDir my/path/to/pretrained/tissueseg/model --sList subjectList.csv
```

### Contact
For more information, please contact <a href="mailto:software@cbica.upenn.edu">CBICA Software</a>.
