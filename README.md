# LPM_Segmentator

Welcome to the LPM_Segmentator repository! This automated deep-learning (DL) pipeline enables segmentation of lumbar paraspinal muscles (LPM) on MRI scans.

## Method Introduction

LPM_Segmentator can automatically segment the lumbar erector spinae and multifidus muscles on T1-weighted, T2-weighted, Dixon water, and Dixon fat MRI scans. This approach significantly enhances muscle health assessment, aiding in the clinical management of low back pain.

## Implementation Steps

1. **Slice Selection**: Manually annotate the L1/L2 to L5/S1 intervertebral disc slices in a CSV file.  
   Refer to: [img_intercept_L2-L5_github.ipynb](img_intercept_L2-L5_github.ipynb)  

2. **Model Inference**: Use the nnU-Net model for LPM segmentation.  
   Refer to: [Implementation_steps.md](documentation/Implementation_steps.md)  

3. **Post-Processing**: Apply largest component analysis to refine the predicted mask.  
   Refer to: [LPM_seg_curated_into_top1_mask.ipynb](LPM_seg_curated_into_top1_mask.ipynb)  

4. **Accuracy Evaluation**: Calculate segmentation accuracy using DSC metrics.  
   Refer to: [LPM_seg_accuracy_evluate_in_DSC.ipynb](LPM_seg_accuracy_evluate_in_DSC.ipynb)  

LPM_Segmentator has been developed and externally validated on 1,301 MRIs from five datasets.  

## Model Download

The trained nnU-Net model can be downloaded from Google Drive:  
[Download Model](https://drive.google.com/file/d/12hCzBPt2w7ZoYxgQmn8_uJ9kh_4cLqQl/view?usp=sharing)

## License

This project is licensed under the Apache License, Version 2.0.

## Publication

Publication details will be updated soon.
