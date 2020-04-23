# 3D Object & Scene Reconstruction using Few 2D Images
I worked as 
3D scene reconstructions based on classical computer-vision and deep learning methods
## 1. Structure-from-Motion
**Repelicated Papers and run on our own data**
Structure-from-Motion (SfM) is the process of reconstructing 3D structure from its projections into a series of images. The input is a set of overlapping images of the same object, taken from different viewpoints. The output is a 3D reconstruction of the object, and the reconstructed intrinsic and extrinsic camera parameters of all images. Typically, Structure-from-Motion systems divide this process into three stages:
   * Feature detection and extraction
   * Feature matching and geometric verification
   * Structure and motion reconstruction
**Block Diagram of SFM**
<p align="center">
<img src="./Images/image36.png" width="800" title="Block Diagram of SFM">
</p>

**Results**
| <img src="Images/frog.gif" width="350" height="350"> |  <img src="Images/cup.gif" width="350" height="350"> | 
|:--:| :--: | 
|Reconstructed Frog-Bin | Reconstructed Cup |


## 2. Intrinsic3D

**Results**
| <img src="Images/lion.gif" width="350" height="350"> |  <img src="Images/lion.gif" width="350" height="350"> | 
|:--:| :--: | 
| Reconstructed Refined Lion | Reconstructed Refined Lion|


