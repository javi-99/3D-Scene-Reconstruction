# 3D-Scene-Reconstruction
3D scene reconstructions based on classical computer-vision and deep learning methods
## 1. Structure-from-Motion
Structure-from-Motion (SfM) is the process of reconstructing 3D structure from its projections into a series of images. The input is a set of overlapping images of the same object, taken from different viewpoints. The output is a 3D reconstruction of the object, and the reconstructed intrinsic and extrinsic camera parameters of all images. Typically, Structure-from-Motion systems divide this process into three stages:
   * Feature detection and extraction
   * Feature matching and geometric verification
   * Structure and motion reconstruction
  
| ![space-1.jpg](Images/image36.png) | 
|:--:| 
|Block Diagram of SFM |

#### Results
| <img src="Images/frog.gif" width="400" height="400"> |  <img src="Images/cup.gif" width="400" height="400"> | 
|:--:| :--: | 
|Reconstructed Frog-Bin | Reconstructed Cup |



## 2. Intrinsic3D

#### Results
| <img src="Images/lion.gif" width="400" height="400"> |  <img src="Images/lion.gif" width="400" height="400"> | 
|:--:| :--: | 
| Reconstructed Refined Lion | Reconstructed Refined Lion|



