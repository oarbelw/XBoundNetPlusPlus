# XBoundNet++: Uncertainty-Aware Segmentation of the Ambiguously-Labeled Kidney Ablation Zone 



This repository contains the official implementation of the paper:


> **XBoundNet++: Uncertainty-Aware Segmentation of the Ambiguously-Labeled Kidney Ablation Zone** <br>
> Oren Arbel-Wood, Aaron Fenster, Maryam Rastegarpoor<br>
> Accepted to the 2nd MICCAI Student Board (MSB) EMERGE Workshop held in conjunction with the 28th International Conference on Medical Image Computing Computer Aided Intervention (MICCAI) 2025<br>
> **Paper** [openreview](https://openreview.net/pdf?id=lHgWi8hprO)

## Overview

In this work, we introduce XBoundNet++, a clinically novel deep learning framework designed specifically for a problem that is often overlooked in medical AI: How to accurately delineate a region in ambiguous or roughly labeled scans - in this case, post-treatment analysis for renal cell carcinoma (kidney cancer) CT images. 

Why is this needed? In many real-world clinical settings, ground truth labels are rough approximations, and boundaries are inherently unclear due to poor imaging contrast or subjective interpretations. Traditional segmentation models break down in these contexts - the very situations where clinical AI is most urgently needed.

XBoundNet++ tackles this challenge head-on by providing:
- Boundary-aware segmentation optimized for uncertain labels.
- Layer-wise interpretability via Grad-CAM, enabling clinicians to visualize how the model arrived at a prediction.
- Bayesian uncertainty estimation and probability maps using Monte Carlo dropout and model ensembling. 

The model excels at segmentation while offering spatial uncertainty and probability overlays. These features support more informed clinical review and promote safer, more trustworthy AI-assisted decision-making in interventional radiology - ultimately leading to improved patient outcomes. 

This work was done at the incredible lab at Robarts Research Institute, and was made possible through the guidance of my supervisors - Aaron Fenster and Maryam Rastegarpoor. 

<div align="center">

&nbsp; <img src="assets/architecture.png" width="600"/>

</div>


## 1. Instructions

### 1.1 Installation
It is recommended to use a virtual environment (e.g., venv) to avoid package conflicts. Here we assume you are using venv as your virtual environment. If you are using conda, please adjust the commands accordingly.

```bash
git clone https://github.com/oarbelw/XBoundNetPlusPlus.git
cd XBoundNetPlusPlus
pip install -r requirements.txt
```

### 1.2 Running the Jupyter Notebook
The following will open a Jupyter Notebook environment, please open and run `XBoundNet.ipynb`
```bash
jupyter notebook
```

### 1.3 Dataset
The current dataset is a small dataset of 912 2D DICOM CT slices that are saved in .bmp format. Please indicate the path (and file format) to the dataset in the notebook, such that path is arranged as followed:

```
/path/to/dataset/
├── Images/
│    ├── patient1.bmp
│    ├── patient2.bmp
│    └── ...
└── Masks/
      ├── patient1mask.bmp
      ├── patient2mask.bmp
      └── ...
```

## 2. Acknowledgments
The authors are grateful for funding from the Ontario Institute of Cancer Research (OICR) Grant RA#262 and the Canadian Institutes of Health Research (CIHR) – Grant FRN 154314.

## 3. Contact
Please raise a GitHub issue if you should encounter an issue or contact one of the corresponding authors for access to the dataset.

[oarbelwo@uwo.ca](oarbelwo@uwo.ca) | [afenster@uwo.ca](afenster@uwo.ca) | [mrasteg2@uwo.ca](mrasteg2@uwo.ca)

