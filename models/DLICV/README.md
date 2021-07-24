## DLICV: ICV (Intra-Cranial Volume) Mask Segmentation

## Overview

Brain extraction is  a critical pre-processing step in most MRI analyses. The output brain mask is also used to estimate the intra-cranial volume (ICV), an important variable used for correcting regional volumes against inter-individual differences in the head size [1].

Current techniques typically use the T1-weighted image for brain extraction, as T1 is the most widely available image modality for volumetric analyses. However, T1-based brain extraction methods are not very successful in correctly segmenting the cortical CSF, resulting in a brain mask that may be "tight around the brain", i.e. one that does not segment properly all of the cortical CSF.

This results in consistent bias to under-estimate actual ICV when a subject has high global cortical atrophy, e.g. with aging, and to over-estimate it in younger subjects, as the brain mask is more prone to include dura and other non-brain tissues in areas difficult to segment.

T2-weighted images provide a better contrast for delineating the cortical CSF. However, high resolution T2 images may not be always available. Also, multi-modal techniques bring increased complexity, as they require additional preprocessing steps. 

DLICV presents a novel deep learning based model for the segmentation of intra-cranial volume. The main motivation for DLICV was to test the hypothesis that ***"The actual boundary of the ICV, which is best differentiated on T2 images, can be accurately learned from ___only T1 images___, if a model is intensive trained using ground-truth segmentations obtained using T2 images."

### References
[1] Voevodskaya O, Simmons A, Nordenskjöld R, et al. The effects of intracranial volume adjustment approaches on multiple regional MRI volumes in healthy aging and Alzheimer's disease. Front Aging Neurosci. 2014;6:264. Published 2014 Oct 7. doi:10.3389/fnagi.2014.00264
