# Single-View & Multi-View 3D Reconstruction
### Based on classical Computer-Vision and Deep Learning Methods

## 1. Structure-from-Motion (Classic Methods)
**Repelicated Papers and Our Experimental Work**
<br/>Structure-from-Motion (SfM) is the process of reconstructing 3D structure from its projections into a series of images. The input is a set of overlapping images of the same object, taken from different viewpoints. The output is a 3D reconstruction of the object, and the reconstructed intrinsic and extrinsic camera parameters of all images. Typically, Structure-from-Motion systems divide this process into three stages:
   * Feature detection and extraction
   * Feature matching and geometric verification
   * Structure and motion reconstruction

**Block Diagram of SFM**
<br/> After working on relevant research papers and provided tools, Overall method is depicted in our block diagram.
<p align="center">
<img src="./Images/image36.png" width="800" title="Block Diagram of SFM">
</p>

**Results**
3D shape and texture reconstruction of a Frog-Bin and Cup using 35 and 63 multi-view images respectively
| <img src="Images/frog.gif" width="350" height="350"> |  <img src="Images/cup.gif" width="350" height="350"> | 
|:--:| :--: | 
|Reconstructed Frog-Bin | Reconstructed Cup |


## 2. Intrinsic3D-High-Quality 3D Reconstruction by Joint Appearance and Geometry Optimization with Spatially-Varying Lighting (ICCV 2017)
Replicated Results: Intrinsic3D is a method to obtain high-quality 3D reconstructions from low-cost RGB-D sensors. The algorithm recovers fine-scale geometric details and sharp surface textures by simultaneously optimizing for reconstructed geometry, surface albedos, camera poses and scene lighting.

**Results**
| <img src="Images/lion.gif" width="350" height="350"> |  <img src="Images/lion.gif" width="350" height="350"> | 
|:--:| :--: | 
| Reconstructed Refined Lion | Reconstructed Refined Lion|



## 3. SDFDiff: Differentiable Rendering of Signed Distance Fields for 3D ShapeOptimization (CVPR-2020)
Replicated Results:SDF-based dif-ferentiable renderer can be integrated with deep learningmodels, which opens up options for learning approaches on3D objects without 3D supervision.

**Multi-View-3D Resconstruction Results**
| Res 56 | <img src = "Images/SDFDiff/grid_res_56_target_12.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_56_target_14.png" width="120" height="120"> | <img src = "Images/SDFDiff/grid_res_56_target_17.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_56_target_21.png" width="120" height="120"> | <img src ="Images/SDFDiff/grid_res_56_target_25.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_56_target_9.png" width="120" height="120">  |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| Res 32 | <img src = "Images/SDFDiff/grid_res_32_target_12.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_32_target_14.png" width="120" height="120"> | <img src = "Images/SDFDiff/grid_res_32_target_17.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_32_target_21.png" width="120" height="120"> | <img src ="Images/SDFDiff/grid_res_32_target_25.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_32_target_9.png" width="120" height="120"> |
| Res 16 | <img src = "Images/SDFDiff/grid_res_16_target_12.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_16_target_14.png" width="120" height="120"> | <img src = "Images/SDFDiff/grid_res_16_target_17.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_16_target_21.png" width="120" height="120"> | <img src ="Images/SDFDiff/grid_res_16_target_25.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_16_target_9.png" width="120" height="120"> |
| Res 8 | <img src = "Images/SDFDiff/grid_res_8_target_12.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_8_target_14.png" width="120" height="120"> | <img src = "Images/SDFDiff/grid_res_8_target_17.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_8_target_21.png" width="120" height="120"> | <img src ="Images/SDFDiff/grid_res_8_target_25.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_8_target_9.png" width="120" height="120"> |
|-| Rendered View 1  | Rendered View 2 | Rendered View 3 | Rendered View 4 | Rendered View 5 | Rendered View 6 |

## 4. Scene Representation Network: Continuous 3D-Structure-Aware Neural Scene Representations (NeurIPS 2019)
Replicated Results: Scene Representation Networks (SRNs), a continuous, 3D-structure-aware scene representation that encodes both geometry and appearance. SRNs represent scenes as continuous functions that map world coordinates to a feature representation of local scene properties. By formulating the image formation as a neural, 3D-aware rendering algorithm, SRNs can be trained end-to-end from only 2D observations, without access to depth or geometry. SRNs do not discretize space, smoothly parameterizing scene surfaces, and their memory complexity does not scale directly with scene resolution.
