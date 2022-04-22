# Cross-View-SLAM

This is the offical repository of the paper:

**Cross-view SLAM solver: global pose estimation of monocular ground-level video frames for 3D reconstruction using a reference 3D model from satellite images**

[Paper](https://www.sciencedirect.com/science/article/pii/S0924271622000910)

```bibtex
@article{elhashash2022,
author = {Mostafa Elhashash and Rongjun Qin},
title = {Cross-view {SLAM} solver: {Global} pose estimation of monocular ground-level video frames for {3D} reconstruction using a reference {3D} model from satellite images},
journal = {ISPRS Journal of Photogrammetry and Remote Sensing},
volume = {188},
pages = {62-74},
year = {2022},
issn = {0924-2716},
doi = {https://doi.org/10.1016/j.isprsjprs.2022.03.018},
}
```


## Usage example
Execute the following command after modifying the `config.yaml`. 
```
 Cross_View_SLAM.exe PATH_TO_YAML_FILE
```

`config.yaml` contains all the parameters needed for the program to run. Descriptions for each parameter are provided as comments in the file.

The results folder should contain `trajectory.txt` for the estimated poses defined in [TUM trjectory format](https://vision.in.tum.de/data/datasets/rgbd-dataset/file_formats) with replacing the timestamp by the image name.
The results also contain the undistorted images and reconstruction results in VisualSFM NVM format. You can use [OpenMVS](https://github.com/cdcseacave/openMVS) to densify the results. Note we split the reconstruction into a few segments before densification to avoid memory issues.

## Note
As mentioned in the paper, the weights `alpha` and `beta` in Eq. (4) need to be tuned to get good resuls. Refer to the conclusion section for the limitations of this work.
Code release might be possible but will take a longer time.
