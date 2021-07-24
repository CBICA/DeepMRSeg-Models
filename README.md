## Model Repository <a name="intro"/>

This repository is a collection of models pre-trained using the [DeepMRSeg package](https://github.com/CBICA/DeepMRSeg), a generic Deep Learning Package designed for MRI image segmentation. In order to obtain robust and accurate models, model training for each different task was performed using large, multi-site MRI image datasets, as well as carefully curated and verified ground-truth segmentations.

Specific details of model training (training datasets, segmentation labels, model parameters) and links to publications that describe the data, models and validation experiments are provided in each model sub-folder.

Models are stored as single zip files using Git LFS (Large File Storage). 

## Usage <a name="usage"/>

Users can apply a model pre-trained for a specific task on their MRI images using the tools provided as part of the [DeepMRSeg package](https://github.com/CBICA/DeepMRSeg). 

A model zip file can be directly downloaded using the Download button on GitHub. Alternatively, users can use the [deepmrseg_downloadmodel]() command to automatically download and extract the model to a pre-defined local folder.

## Segmentation Tasks <a name="seg_tasks"/>

The table below lists models pre-trained for segmentation tasks that are part of this model repository. This table will evolve with time, as new models for new or existing tasks will be added. Models are tagged using a model name and a version number for reproducibility.

|Task Name |Model Name |Date Upload |Description |File Name |
|-|-|-|-|-|
|<b>bmask</b>|deepmrseg_brain_v1.1|07/2021|A model trained for segmenting a brain mask|deepmrseg_brainmask_v1.1.zip|
|<b>wmlesion</b>|deepmrseg_wml_v1.1|07/2021|A model trained for segmenting white matter lesions|deepmrseg_wml_v1.1.zip|
|<b>hippocampus</b>|deepmrseg_hippo_v2.1|07/2021|A model trained for segmenting hippocampus sub-parts|deepmrseg_hippo_v2.1.zip|
|<b>dlicv</b>|deepmrseg_dlicv_v1.1|07/2021|A model trained for segmenting intra-cranial volume|deepmrseg_dlicv_v1.1.zip|

## Contributions
Please contact the developers for assistance if you would like to contribute to this repository by adding a new model trained using your dataset with ground-truth labels for a specific task.

# License
TODO

