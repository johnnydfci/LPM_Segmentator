# LPM_Segmentator

<p align="center">
  <img src="documentation/graphical_abstract.jpg" alt="Graphical Abstract" width="600">
</p>

Welcome to the LPM_Segmentator repository! This automated deep-learning (DL) pipeline enables segmentation of lumbar paraspinal muscles (LPM) on MRI scans.

## Method Introduction

LPM_Segmentator can automatically segment the lumbar erector spinae and multifidus muscles on T1-weighted, T2-weighted, Dixon water, and Dixon fat MRI scans. This approach significantly enhances muscle health assessment, aiding in the clinical management of low back pain. We collect 1,302 MRIs from 641 participants across five imaging centers. Images from two centers were used for algorithm development, while data from the remaining three centers used for external validation. 

## Implementation Steps

1. **Slice Selection**: Manually annotate the L1/L2 to L5/S1 intervertebral disc slices in a CSV file.  
   Refer to: [img_intercept_L2-L5_github.ipynb](img_intercept_L2-L5_github.ipynb)  

2. **Model Inference**: Use the nnU-Net model for LPM segmentation.  
   Refer to: [Implementation_steps.md](documentation/Implementation_steps.md)  

3. **Post-Processing**: Apply largest component analysis to refine

## Method Introduction

LPM_Segmentator can automatically segment the lumbar erector spinae and multifidus muscles on T1-weighted, T2-weighted, Dixon water, and Dixon fat MRI scans. This approach significantly enhances muscle health assessment, aiding in the clinical management of low back pain.

## Implementation Steps

1. **Slice Selection**: Manually annotate the L1/L2 to L5/S1 intervertebral disc slices in a CSV file.  
   Refer to: [img_intercept_L2-L5_github.ipynb](img_intercept_L2-L5_github.ipynb)  

2. **Model Inference**: Use the nnU-Net model for LPM segmentation.  
   Refer to: [Implementation_steps.md](documentation/Implementation_steps.md)  

3. **Post-Processing**: Apply largest component analysis to refine the predicted mask.  
   Refer to: [LPM_seg_curated_into_top1_mask.ipynb](LPM_seg_curated_into_top1_mask.ipynb)  

4. **Segmentation Accuracy Evaluation**: Calculate segmentation accuracy using DSC metrics.  
   Refer to: [LPM_seg_accuracy_evluate_in_DSC.ipynb](LPM_seg_accuracy_evluate_in_DSC.ipynb)
   
5. **Muscle Volume Statistical Evaluation**: Calculate muscle volume based on automated and manual segmenation.  
   Refer to: [LPM_seg_to_vol_2csv.ipynb](LPM_seg_to_vol_2csv.ipynb)
6. **Fatty ratio Evaluation**: Calculate fatty ratio based on segmentation of dixon water and fat images.  
   Refer to: [LPM_seg_to_fat_ratio_2csv.ipynb](LPM_seg_to_fat_ratio_2csv.ipynb)



## Model Download

The trained nnU-Net model can be downloaded from Google Drive:  
[Download Model](https://drive.google.com/file/d/12hCzBPt2w7ZoYxgQmn8_uJ9kh_4cLqQl/view?usp=sharing)

## License

This project is licensed under the Apache License, Version 2.0.

## Publication

Publication details will be updated soon.
