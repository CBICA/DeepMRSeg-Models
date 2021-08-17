## DLICV: ICV (Intra-Cranial Volume) Mask Segmentation

## Description

DLICV is a method developed for segmenting a binary mask of the the intra-cranial region from a T1-weighted brain image. It can be applied for ***estimating the intra-cranial volume (ICV)***, a variable commonly used for correcting regional volumes against inter-individual differences in the head size *[1]*. It can also be applied as a pre-processing step, to calculate a ***brain mask*** that is used as input to following processing steps.

## Usage

The DLICV model can be easily applied for segmenting the ICV on a single or multiple T1 images using the tools provided as part of the [DeepMRSeg package](https://github.com/CBICA/DeepMRSeg)

DLICV model was trained using raw T1 images without any preprocessing steps. Users can directly apply it on their raw T1 images.

```
# After installing DeepMRSeg

# Download pre-trained model
deepmrseg_downloadmodel --model dlicv

# Process single subject
deepmrseg_apply --task dlicv --inImg subj1_T1.nii.gz --outImg subj1_T1_DLICV.nii.gz

# Batch processing of multiple subjects using a subject list
#   User provides a csv file with columns: ID,InputT1,OutputImage
deepmrseg_apply --task dlicv --sList subjectList.csv

# Batch processing of multiple subjects in input folder 
#   Testing is applied individually to all images with the given suffix in the input folder
deepmrseg_apply --task dlicv --inDir myindir --outDir myoutdir --inSuff _T1.nii.gz --outSuff _DLICV.nii.gz

# Using the deepmrseg_test command:
deepmrseg_test --mdldir my/path/to/pretrained/dlicv/model --sList subjectList.csv
```


## Method Overview

Current methods typically use the T1-weighted image for brain extraction, as T1 is the most widely available image modality for volumetric analyses. However, T1-based brain extraction methods are not very successful in correctly segmenting the cortical CSF, resulting in a brain mask that may be "tight around the brain", i.e. one that does not segment properly all of the cortical CSF.

This causes a consistent bias if the brain mask is used for estimating the ICV: It under-estimates it when a subject has high global cortical atrophy, e.g. with aging, and over-estimates it in younger subjects, as the brain mask is more prone to include dura and other non-brain tissues in areas difficult to segment.

T2-weighted images provide a better contrast for delineating the cortical CSF. However, high resolution T2 images may not be always available. Also, multi-modal techniques bring increased complexity, as they require additional preprocessing steps. 

The main motivation for DLICV was based on a simple hypothesis:

*"The actual boundary of the ICV, which is best differentiated on T2 images, can be learned ***using only raw T1 images as input***, if a model is intensively trained using accurate ground-truth segmentations obtained from T2 images."*

Validation experiments have demonstrated that the proposed strategy resulted in accurate ICV masks. The final model was trained on a very rich dataset with n=450 subjects from 15 studies, and their carefully curated/verified reference labels [TODO: ref to paper]


### References
[1] Voevodskaya O, Simmons A, Nordenskjöld R, et al. The effects of intracranial volume adjustment approaches on multiple regional MRI volumes in healthy aging and Alzheimer's disease. Front Aging Neurosci. 2014;6:264. Published 2014 Oct 7. doi:10.3389/fnagi.2014.00264


### Contact
For more information, please contact <a href="mailto:software@cbica.upenn.edu">CBICA Software</a>.

