# Semi-supervised machine learning workflow for analysis of nanowire morphologies from TEM images

# <img src="./github header image.png" width="500" height="673" class="center">

This repository contains implementation of semi-supervised transfer learning workflow for nanowire morphology classification and segmentation from transmission electron microscopy (TEM) images.

Paper: [Semi-supervised machine learning workflow for analysis of nanowire morphologies from transmission electron microscopy images](https://arxiv.org/abs/2203.13875) is available in arXiv
## Dataset
The peptide / protein nanowires used in this study were synthesized and imaged by Brian Montz in Prof. Todd Emrick's research group at the Department of Polymer Science and Engineering Department, University of Massachusetts Amherst. 

The TEM image dataset of the nanowire morphologies along with manual segmentation ground truth masks and image encoders trained via self-supervised training are hosted on Zenodo, [DOI: 10.5281/zenodo.6377140](https://zenodo.org/record/6377140)

## Brief description of functionality of each jupyter notebook
[Preprocess images](https://github.com/arthijayaraman-lab/self-supervised_learning_microscopy_images/blob/main/notebooks/Preprocess%20images.ipynb): Perform augmentation for singular morphology images, create binary segmentation ground truth data from manually labeled images. Note: users do not need to run this again.

[Percolation_analysis](https://github.com/arthijayaraman-lab/self-supervised_learning_microscopy_images/blob/main/notebooks/percolation_analysis.ipynb): Serve as pixel-level quantification to distinguish dispersed vs. network morphologies.

[SimCLR_Barlow_encoder_training](https://github.com/arthijayaraman-lab/self-supervised_learning_microscopy_images/blob/main/notebooks/SimCLR_Barlow_encoder_training.ipynb): Perform self-supervised training of image encoders on unlabeled images.

[Hyperparameter tuning](https://github.com/arthijayaraman-lab/self-supervised_learning_microscopy_images/blob/main/notebooks/Hyperparameter%20tuning.ipynb): Assess hyperparameter tuning results with downstream classification task for self-supervised training.

[Assessment of label-efficient training of downstream classification task](https://github.com/arthijayaraman-lab/self-supervised_learning_microscopy_images/blob/main/notebooks/Assessment%20of%20label-efficient%20training%20of%20downstream%20classification%20task.ipynb): Assess classification performance on nanowire morphology images with feature maps obtained from encoders trained under self-supervision with optimized hyperparameters.

[Assessment of classification performance on mNP dataset](https://github.com/arthijayaraman-lab/self-supervised_learning_microscopy_images/blob/main/notebooks/Assessment%20of%20classification%20performance%20on%20mNP%20dataset.ipynb): Assess classification performance on metal nanoparticle morphology images with feature maps obtained from encoders trained under self-supervision with optimized hyperparameters.

[Assessment of classification performance on TEM virus dataset](https://github.com/arthijayaraman-lab/self-supervised_learning_microscopy_images/blob/main/notebooks/Assessment%20of%20classification%20performance%20on%20TEM%20virus%20dataset.ipynb): Assess classification performance on TEM virus images with feature maps obtained from encoders trained under self-supervision with optimized hyperparameters.

[Training_of_segmentation_models](https://github.com/arthijayaraman-lab/self-supervised_learning_microscopy_images/blob/main/notebooks/training_of_segmentation_models.ipynb): Assess segmentation performance on nanowire morphology images with feature maps obtained from encoders trained under self-supervision with optimized hyperparameters.

[Result_plots_for_classification_segmentation_and_hyperparameter_tuning](https://github.com/arthijayaraman-lab/self-supervised_learning_microscopy_images/blob/main/notebooks/result_plots_for_classification_segmentation_and_hyperparameter_tuning.ipynb): Create boxplots for the three sets classification results and segmentation results.

[One-shot learning result plots](https://github.com/arthijayaraman-lab/self-supervised_learning_microscopy_images/blob/main/notebooks/one-shot%20learning%20result%20plots.ipynb): Examine one-shot learning with the nanowire morphology dataset.

## Instructions to use/adapt the notebooks

Download the open-access contents from the Zenodo dataset listed above to your local drive, unzip them into respective folders. A "2022-nanowire-morphology" folder should be created and unzip "dispersed", "bundle", "network" and "singular" into the "2022-nanowire-morphology" folder.

Create a folder named "TEM image datasets" in your google drive and upload the unzipped folders to "TEM image datasets".

Additional folders that are needed to be created (under the main folder "TEM image datasets") to store intermediate models and figures are mentioned in the beginning of each individual notebooks if necessary. These should be created manually when you see the text requirement that's different for each notebook (some may not need additional folder creation).

The notebooks can be adapted to test on different user-provided datasets with modifications.

## Citing
If you use the codes in this repository, please cite the following [manuscript](https://arxiv.org/abs/2203.13875):
```
@misc{lu2022selfsupervised,
      title={Self-supervised machine learning model for analysis of nanowire morphologies from transmission electron microscopy images}, 
      author={Shizhao Lu and Brian Montz and Todd Emrick and Arthi Jayaraman},
      year={2022},
      eprint={2203.13875},
      archivePrefix={arXiv},
      primaryClass={cond-mat.mtrl-sci}
}
```
## Funding
This project is financially supported by the U.S. National Science Foundation, Grant NSF DMREF #1921839 and #1921871.
