# LPM_Segmentator

<p align="center">
  <img src="documentation/graphical_abstract.jpg" alt="Graphical Abstract" width="600">
</p>

Welcome to the **LPM_Segmentator** repository! This automated deep-learning (DL) pipeline enables the segmentation of lumbar paraspinal muscles (LPM) on MRI scans, advancing muscle health assessment and clinical management of low back pain.

---

## Method Overview

**LPM_Segmentator** automatically segments the lumbar erector spinae (LES) and multifidus (MF) muscles across T1-weighted, T2-weighted, Dixon water, and Dixon fat MRI scans. The pipeline leverages data from 1,302 MRIs of 641 participants across five imaging centers. Images from two centers were used for algorithm development, while data from the remaining three centers were reserved for external validation.

---

## Implementation Workflow

1. **Slice Selection**:  
   Annotate the L1/L2 to L5/S1 intervertebral disc slices manually and save the data in a CSV file.  
   Refer to: [img_intercept_L2-L5_github.ipynb](img_intercept_L2-L5_github.ipynb)  

2. **Model Inference**:  
   Use the nnU-Net framework for LPM segmentation.  
   Refer to: [Implementation_steps.md](documentation/Implementation_steps.md)  

3. **Post-Processing**:  
   Apply largest component analysis to refine the predicted segmentation mask.  
   Refer to: [LPM_seg_curated_into_top1_mask.ipynb](LPM_seg_curated_into_top1_mask.ipynb)  

4. **Segmentation Accuracy Evaluation**:  
   Assess segmentation performance using Dice Similarity Coefficient (DSC) metrics.  
   Refer to: [LPM_seg_accuracy_evluate_in_DSC.ipynb](LPM_seg_accuracy_evluate_in_DSC.ipynb)  

5. **Muscle Volume Statistical Evaluation**:  
   Calculate muscle volume using both automated and manual segmentations.  
   Refer to: [LPM_seg_to_vol_2csv.ipynb](LPM_seg_to_vol_2csv.ipynb)  

6. **Fatty Ratio Evaluation**:  
   Compute the fatty ratio using Dixon water and fat segmentations.  
   Refer to: [LPM_seg_to_fat_ratio_2csv.ipynb](LPM_seg_to_fat_ratio_2csv.ipynb)  

---

## Model Download

The trained nnU-Net model is available for download from Google Drive:  
[Download Model](https://drive.google.com/file/d/12hCzBPt2w7ZoYxgQmn8_uJ9kh_4cLqQl/view?usp=sharing)

---

## Data Download

The curated MyoSegmenTUM spine dataset, including 54 Dixon fat images and 54 Dixon water images, is available for download from Google Drive:
[Download data](https://drive.google.com/file/d/1ESqzjEMm8GoZDNKcQe6NJCTeNP54dYj3/view?usp=drive_link)

---

## License

This project is licensed under the **Apache License, Version 2.0**.  
Refer to the [LICENSE](LICENSE) file for details.

---

## Publication

Details of the associated publication will be updated soon.
