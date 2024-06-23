# nnU-Net model for lumbar paraspinal muscle segmentation

The nnU-Net of LPM segmentator was implemented on Linux (Ubuntu 18.04) with an RTX 3060 GPU (12GB VRAM). A nnU-Net model is developed using this repository [https://github.com/MIC-DKFZ/nnUNet/tree/nnunetv1](https://github.com/MIC-DKFZ/nnUNet). 

### Environment setup

```conda create -n lpm python=3.8.5``` # create a conda environment with python3.8.5; ```conda remove -n lpm --all ```if you want to delete this conda environment. 'lpm' stands for lumbar paraspinal muscle

```conda activate lpm```  # activate the conda environment

```conda install nb_conda_kernels```  # Install jupyter notebook

```pip3 install -r requirements.txt``` # Once you change directories into the root path of the project

 ```pip3 install torch==1.11.0+cu113 torchvision==0.12.0+cu113 torchaudio==0.11.0 --extra-index-url https://download.pytorch.org/whl/cu113```# install pytorch under CUDA 11.3
 
 ```pip3 install nnunet==1.7.1```# install nnunet==1.7.1
 
 ### nnunet paths setup 
 
 -  set nnunet environment path, replace the following with your own user name and repo dir
 -  suppose user name is 'zhongyi' and repo dir is '/home/zhongyi/Desktop/nn-unet_train'

                ```
                cd /home/zhongyi/.bashrc     
                       
                export nnUNet_raw_data_base="/home/zhongyi/Desktop/nn-unet_train/nnUNet_raw_data_base"
                export nnUNet_preprocessed="/home/zhongyi/Desktop/nn-unet_train/nnUNet_preprocessed"
                export RESULTS_FOLDER="/home/zhongyi/Desktop/nn-unet_train/nnUNet_trained_models"                ```                
 
 ### nnunet scripts to segment test images of lumbar MRI 
 
 ```nnUNet_raw_data_base/nnUNet_test_data/test_img_in_nii_raw/ ``` # download open-source data into the dir, one image is stored in our repository as an example
 
 ```file_op_to_infer_by_nnunet.ipynb```  # prepare data into the required format, where each nifty image name has to end with '0000.nii.gz'
 
  ```nnUNet_trained_models/ ``` # download pre-trained model from Gdrive or baiduwangpan ```Files_for_running_github/nnUNet_trained_models.zip``` dir. The required paths are shown in this [screenshot.png](Pre_trained_model_paths.png)
   
 ```nnUNet_predict -i $nnUNet_raw_data_base/nnUNet_test_data/test_img_in_nii/ -o  $nnUNet_raw_data_base/nnUNet_test_data/test_seg_in_nii_raw/ -t 515 -m 3d_fullres -f 1```  # nnunet predict, the '1' stands for the trained model of 1st fold of the five-fold cross validation
  

### -optional: training your own model 

-  ```  nnUNet_raw_data_base/nnUNet_train_data_raw/ ``` # download training data into the dir.  ```Files_for_running_github/nnUNet_train_data_raw.zip``` dir. Required paths are shown in this [screenshot.png](Images_paths_for_training.png)

-  ``` file_op_to_prepare_training_nnunet.ipynb```  #  prepare data into the required format of nnunet: 1/2 step

-   ```python nnunet/dataset_conversion/515_muscle_4class_seg.py```   #   prepare data into the required format of nnunet 2/2 step

-   ```python  nnunet/experiment_planning/nnUNet_plan_and_preprocess.py -t 515 --verify_dataset_integrity```    # pre-process the data using nnunet scripts
             
-   ```nnUNet_train 3d_fullres nnUNetTrainerV2 515 1```  # nnunet training, the '1' stands for training 1st fold of the five-fold cross validation

