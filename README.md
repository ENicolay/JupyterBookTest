# High-content imaging workflow for automated region and cell detection
This repository contains multiple notebooks that can be used to prepare images, train and apply a predicition model (modified from [nn-Unet](https://github.com/mic-dkfz/nnunet) and peform cell segmentation in 3D.

Follow this link to the website: 
https://enicolay.github.io/JupyterBookTest/intro.html#

It is maintained using [Jupyter lab](https://jupyterlab.readthedocs.io/en/stable/) and build using [Jupyter book](https://jupyterbook.org/intro.html).

This workflow was designed for high-content imaging data (96-well plate data A01-H12) with raw image filenames structured like this:
**ExperimentID_well_site_wavelength+randomID**

## Workflow overview

* **Preprocessing:** The workflow takes raw data stored in Z-slice folders, which must be stacked and merged to .ome.tiffs. During stacking metadata are saved as .csv.  
* **Classify images:** Bring images into a gallery view to double check image quality.
* **Gut detection:** Train and apply the nn-Unet model to detect regions in 3D transmitted light images.
* **Cell detection:** Apply Voronoi-Otsu-Labeling to 3D fluorescence images for feature extraction based on their positions.
* **Quantification:** Cell quantification plots for the publication

