# MVFormer
The official implementation of "MVFormer: UNet-like Transformer with Mix-Voxel Attention for Camera-based 3D Semantic Scene Completion"

![The architecture of our MVFOrmer.](./assets/arch.pdf)

![The demo of our MVFormer.](./assets/demo.gif)

# Preliminary
### Installation
1.Install PyTorch and Torchvision referring to https://pytorch.org/get-started/locally/.

2.Install MMDetection referring to https://mmdetection.readthedocs.io/en/latest/get_started.html#installation.

3.Install the rest of the requirements with pip.

    pip install -r requirements.txt

### Dataset Preparation
#### 1.Download the Data
**SemanticKITTI:** Download the RGB images, calibration files, and preprocess the labels, referring to the documentation of [Symphonies](https://github.com/hustvl/Symphonies), [VoxFormer](https://github.com/NVlabs/VoxFormer)) or [MonoScene](https://github.com/astra-vision/MonoScene).

**SSCBench-KITTI-360:** Refer to https://github.com/ai4ce/SSCBench/tree/main/dataset/KITTI-360.

#### 2.Generate Depth Predications
**SemanticKITTI:** Our method is consistent with VoxFormer. Please refer to [VoxFormer](https://github.com/NVlabs/VoxFormer/tree/main/preprocess#3-image-to-depth) and use pre trained MobileStereoNet to generate deep predictions.

**SSCBench-KITTI-360:** Follow the same procedure as SemanticKITTI but ensure to [adapt the disparity value](https://github.com/ai4ce/SSCBench/issues/8#issuecomment-1674607576).

# Result
#### 1.SemanticKITTI
|Method|Split|IoU|mIoU|
|------|-----|---|----|
|MVFormer|val|42.78|15.76|
|MVFormer|test|43.02|15.81|

#### 2.KITTI-360
|Method|Split|IoU|mIoU|
|------|-----|---|----|
|MVFormer|test|44.38|18.94|


# Acknowledgements
The development of this project is inspired and informed by [MonoScene](https://github.com/astra-vision/MonoScene), [MaskDINO](https://github.com/IDEA-Research/MaskDINO), [mobilestereonet](https://github.com/cogsys-tuebingen/mobilestereonet), [VoxFormer](https://github.com/NVlabs/VoxFormer) and [Symphonies](https://github.com/NVlabs/VoxFormer). We are thankful to build upon the pioneering work of these projects.
