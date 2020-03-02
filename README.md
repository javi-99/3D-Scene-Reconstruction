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
| ![frog](Images/frog.gif){:height="700px" width="400px"} |  ![cup](Images/cup.gif){:height="700px" width="400px"} | 
|:--:| :--: | 
|Reconstructed Frog-Bin | Reconstructed Cup |

