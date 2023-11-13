# DySPN

This project aims to deploy DySPN in detail. The source code has not been changed. For details, see Readme.md for setting up the environment.

Implement of "Dynamic Spatial Propagation Network for Depth Completion"

Paper: [IEEE-TCSVT](https://ieeexplore.ieee.org/document/10284921) [Early Version of AAAI (arxiv)](https://arxiv.org/pdf/2202.09769.pdf)

We will improve our repo as soon as possible.

# Dependence

    pip install torch==1.12.1+cu116 torchvision==0.13.1+cu116 torchaudio==0.12.1 --extra-index-url https://download.pytorch.org/whl/cu116
    pip install -r requirements.txt
    
# Datasets
### 1、KITTI
KITTI DC dataset is available at the [KITTI DC Website](http://www.cvlibs.net/datasets/kitti/eval_depth.php?benchmark=depth_completion).

For color images, KITTI Raw dataset is also needed, which is available at the [KITTI Raw Website](http://www.cvlibs.net/datasets/kitti/raw_data.php).

The overall data directory is structured as follows:

    dataset
    ├── kitti_depth_completion
        ├── data_calib
        │   ├── 2011_09_26_calib
        │   │   ├── 2011_09_26
        │   │   │   ├── calib_cam_to_cam.txt
        │   │   │   ├── calib_imu_to_velo.txt
        │   │   │   └── calib_velo_to_cam.txt
        │   │   └── readme(function's server).txt
        │   ├── 2011_09_28_calib
        │   ├── 2011_09_29_calib
        │   ├── 2011_09_30_calib
        │   └── 2011_10_03_calib 
        ├── data_depth_annotated
        ├── data_depth_selection 
        ├── data_depth_velodyne 
        ├── devkit_depth
        └── image_raw
            ├── 2011_09_26_drive_0001_sync
            ...
            ├── 2011_09_28_drive_0001_sync

# Training

At the same time, we can use settings_kitti_s.py to set the parameter, the default device=1.We can use the following code to train and test：

    python3 lit_kitti_s.py


# Acknowledgement
Thanks the authors for their awesome works:
[NLSPN](https://github.com/zzangjinsun/NLSPN_ECCV20)
[CFormer](https://github.com/youmi-zym/CompletionFormer)
[DySPN](https://github.com/Kyakaka/DySPN)

# Citation
If you find our work useful in your research, please consider citing our paper:
```
@ARTICLE{lin2023dyspn,
  author={Lin, Yuankai and Yang, Hua and Cheng, Tao and Zhou, Wending and Yin, Zhouping},
  journal={IEEE Transactions on Circuits and Systems for Video Technology}, 
  title={DySPN: Learning Dynamic Affinity for Image-guided Depth Completion}, 
  year={2023},
  volume={},
  number={},
  pages={1-1},
  doi={10.1109/TCSVT.2023.3321668}}
```
