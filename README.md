## Model Repository <a name="intro"/>

This repository is a collection of models pre-trained using the [DeepMRSeg package](https://github.com/CBICA/DeepMRSeg), a generic Deep Learning Package designed for MRI image segmentation. In order to obtain robust and accurate models, model training for each different task was performed using large, multi-site MRI image datasets, as well as carefully curated and verified ground-truth segmentations.

Specific details of model training (training datasets, segmentation labels, model parameters) and links to publications that describe the data, models and validation experiments are provided in each model sub-folder.

Models are stored as single zip files using Git LFS (Large File Storage). 

## Usage <a name="usage"/>

Users can apply a model pre-trained for a specific task on their MRI images using the tools provided as part of the [DeepMRSeg package](https://github.com/CBICA/DeepMRSeg). 

A model zip file can be directly downloaded using the Download button on GitHub. Alternatively, users can use the [deepmrseg_downloadmodel]() command to automatically download and extract the model to a pre-defined local folder.

## Segmentation Tasks <a name="seg_tasks"/>

The table below lists models pre-trained for segmentation tasks that are part of this model repository. This table will evolve with time, as new models for new or existing tasks will be added. Models are tagged using a model name and a version number for reproducibility.

|Task Name |Model Name |Date Upload |Description|
|-|-|-|-|
|<b>tissueseg</b>|[deepmrseg_TissueSeg_v1.0](https://github.com/CBICA/DeepMRSeg-Models/raw/main/models/TissueSeg)|08/2021|A model trained for segmenting brain tissues (GM, WM, ventricles and cortical CSF)|
|<b>muse</b>|[deepmrseg_MUSE_v1.0](https://github.com/CBICA/DeepMRSeg-Models/raw/main/models/MUSE)|08/2021|A model trained for segmenting MUSE anatomical regions of interest (ROIs)|
|<b>dlicv</b>|[deepmrseg_DLICV_v1.0](https://github.com/CBICA/DeepMRSeg-Models/raw/main/models/DLICV)|08/2021|A model trained for segmenting intra-cranial volume|
|<b>WMLS</b>|[deepmrseg_WMLS_v1.0](https://github.com/CBICA/DeepMRSeg-Models/tree/main/models/WMLS)|07/2022|A model trained for segmenting white matter lesions|

## Contributions
Please contact the developers for assistance if you would like to contribute to this repository by adding a new model trained using your dataset with ground-truth labels for a specific task.

## Disclaimer
-   The software has been designed for research purposes only and has neither been reviewed nor approved for clinical use by the Food and Drug Administration (FDA) or by any other federal/state agency.
-   This code (excluding dependent libraries) is governed by the license provided in https://www.med.upenn.edu/cbica/software-agreement-non-commercial.html unless otherwise specified.
-   By using DeepMRSeg-Models, you agree to the license as stated in the [license file](https://github.com/CBICA/DeepMRSeg/blob/main/LICENSE).

## Contact
For more information, please contact <a href="mailto:software@cbica.upenn.edu">CBICA Software</a>.
