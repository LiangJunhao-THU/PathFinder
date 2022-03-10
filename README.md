# PathFinder
### AI inspired discovery of new biomarker for clinical cancer prognosis
© This code is made available for non-commercial academic purposes. 


## PathFinder: Cancer biomarker discovery via AI
* WSI_decoupling: *Get the macro mode (3D-numpy-array of multi-class tissue probability heatmaps) of WSIs.*
* Prognosis: *Train prognostic deep neural networks (MacroNet, MicroNet and M2MNet) for cancer prognosis.*
* Discovery: *Use attribution methods to find important features for further analyses and discovery.*

## Pre-requisites:
* Linux (Tested on Ubuntu 18.04)
* NVIDIA GPU (Tested on Nvidia GeForce RTX 3090 x 4)
* Python (3.7.7), h5py (2.10.0), matplotlib (3.1.1), numpy (1.18.1), opencv-python (4.1.1), openslide-python (1.1.1), openslide (3.4.1), pandas (1.0.3), pillow (7.0.0), PyTorch (1.5.1), scikit-learn (0.22.1), scipy (1.3.1), tensorflow (1.14.0), tensorboardx (1.9), torchvision (0.6).

### Data Preparation
WSIs and clinical information of patients are used in this project. Raw WSIs are stored as .svs, .mrxs or .tiff files. Clinical information are stored as .csv files. WSIs are first processed by PaSegNet to get multi-class tissue probability heatmaps (macro mode), which sorted as .npy files. Tumor pathces (micro mode) are extracted based on macro mode and WSIs, and stored as .tif files. Macro mode and clinical information is used to train MacroNet, micro mode and clinical information is used to train MicroNet, both macro mode, micro mode and clinical information is used to train M2MNet. The Data distribution is like:
```bash
DATA_ROOT_DIR/
    └──DATASET_DIR/
         ├── clinical_information                                 -------------
                ├── Hospital_1.csv                                            |
                ├── Hospital_2.csv                                            |
                └── ...                                                       |
         ├── WSI_data                                                         |
                ├── Hospital_1                                                |
                       ├── slide_1.svs                                        |
                       ├── slide_2.svs                                   Source Data
                       └── ...                                                |
                ├── Hospital_2                                                |
                       ├── slide_1.svs                                        |
                       ├── slide_2.svs                                        |
                       └── ...                                                |
                └── ...                                            ------------
         ├── macro_mode                                            ------------
                ├── Hospital_1                                                |
                       ├── slide_1_heatmaps.npy                               |
                       ├── slide_2_heatmaps.npy                               |
                       └── ...                                                |
                ├── Hospital_2
                       ├── slide_1_heatmaps.npy
                       ├── slide_2_heatmaps.npy
                       └── ...
                └── ...
         └── micro_mode
                ├── Hospital_1
                       ├── slide_1
                              ├── patch_1.tif
                              ├── patch_2.tif
                              └── ...
                       ├── slide_2
                              ├── patch_1.tif
                              ├── patch_2.tif
                              └── ...
                       └── ...
                └── ...                                           ------------             
```
DATA_ROOT_DIR is the base directory of all datasets (e.g. the directory to your SSD). DATASET_DIR is the name of the folder containing data specific to one experiment and features from each slide is stored as .pt files.



### Training


### Evaluation 


## Issues
- Please report all issues on the public forum.

## License


## Reference
If you find our work useful in your research or if you use parts of this code please consider citing our paper:
