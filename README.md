# LPM_Segmentator

Welcome to our GitHub repository. LPM segmentator is an automated deep-learning (DL) pipeline for segmenting lumbar paraspinal muscles (LPM) on MRI scans. 

### Method introduction

LPM_Segmentator can automatically segment the lumbar erector spinae and multifidus muscles on T1-weighted, T2-weighted, Dixon water, and Dixon fat MRI scans. This approach can significantly enhance the assessment of muscle health, aiding in the treatment of lower back pain. 

### Implementation steps

1. Slice selection of L1/L2 to L5/S1 intervertebral disc by manual annoation in CSV file. [img_intercept_L2-L5_github.ipynb](img_intercept_L2-L5_github.ipynb)  
  
2. nnU-Net model inference for LPM segmentation: [Implementation_steps.md](documentation/Implementation_steps.md)

3. Post-process of predicted mask by largest component analysis: [LPM_seg_curated_into_top1_mask.ipynb](LPM_seg_curated_into_top1_mask.ipynb)  

4. Segmentation accuracy calculation: [LPM_seg_accuracy_evluate_in_DSC.ipynb](LPM_seg_accuracy_evluate_in_DSC.ipynb)  

LPM segmentator was developed and externally validated on a total of xxx MRI images from five datasets. Curated MRI images and LPM segmentations can be freely downloaded from Google Drive or Baidu Wangpan (link TBD).

## Publication

To be dated

## License

Apache License, Version 2.0
