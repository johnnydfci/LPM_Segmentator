# LPM_Segmentator

### Deep learning to segment lumbar paraspinal muscle on multi-national MRI with curated datasets 

Welcome to our GitHub repository for the DL-LPM method, an automated deep-learning (DL) system for segmenting lumbar paraspinal muscles (LPM) on MRI scans. The DL-based LPM segmentator can segment lumbar earator spine and multifidues on T1 weighted, T2 weighted, Dixon water, and Dixon fat MRI.

This repository provides the implementation of our method, including a nnU-Net for LPM segmentation, the script for automated segmentation, and the dataset used for development and validation.

### Method introduction

LPM_Segmentator can automatically segment lumbar earator spine and multifidues on T1 weighted, T2 weighted, Dixon water, and Dixon fat MRI. This approach can enhance the assessment of muscle health, aiding in the treatment of lower back pain (LBP).  [Method details.md](documentation/Method_introduction.md)

### Implementation steps

1. nnU-Net model training for LPM segmentation: [Implementation_steps.md](documentation/Implementation_steps.md)

2. nnU-Net model inference for LPM segmentation: [Implementation_steps.md](documentation/Implementation_steps.md)

3. post-process: largest component analysis of automated segmentation: [230402_github_Figure_S5_cofusion_matrix_95CI.ipynb](stats_to_figure/230402_github_Figure_S5_cofusion_matrix_95CI.ipynb)  

4. plot figures of results of segment accuaries: ```dir: stats_to_figure/ ```

LPM segmentator was developed and externally validated on a total of 647 MRI images from six diverse datasets. Curated MRI images and LPM segmentations can be freely downloaded from Google Drive or Baidu Wangpan (link TBD).

## Publication

To be dated

## License

Apache License, Version 2.0
