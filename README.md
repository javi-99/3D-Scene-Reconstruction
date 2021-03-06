# 3D Reconstruction
**Summary**
<br/> The inverse-graphics, such as recovering 3D information from 2D views, is a big challenge. The 3D scene understanding or generating 3D shapes and textures has applications in augmented/virtual reality, computer-aided geometric design, autonomous vehicles, and many more. The traditional multi-view stereo or shape from shading based methods lack in providing surface as prior, have a small resolution, or require volumetric fusion steps. Whereas, the deep learning-based differentiable models provide 3D shape/texture or novel views of a scene without 3D supervision. We can categorize the 3D representation into either
explicit or implicit. The point-based, voxel-based, and mesh-based are of explicit types, whereas the implicit is the continuous field to get iso-surfaces as a binary classifier decision boundary. The implicit provides high resolution, connectivity, remove the requirement of a deformable mesh template, and avoid patches overlapping in the shape’s geometry. That is why it is more flexible to store complex shapes.
<br/>**My Interests**
<br/> **My goal is to have an efficient, expressive, and fully continuous state of the art method for objects in a real scene. The main challenges are perfect camera intrinsic and pose estimation, depth-map, an appropriate data representation able to represent 3D surfaces with complex topologies, and a differentiable neural renderer to provide an accurate and realistic novel views**

**A teaser image on 3D-Reconstruction and Novel-Views**
<br/> 
<p align="center">
<img src="./Images/motivation.gif" width="750" title="A Teaser Image"> </p>

### Classical Method: Structure-from-Motion (Colmap) and Failure Cases
<br/>Structure-from-Motion (SfM) is the process of reconstructing 3D structure from its projections into a series of images. The input is a set of overlapping images of the same object, taken from different viewpoints. The output is a 3D reconstruction of the object, and the reconstructed intrinsic and extrinsic camera parameters of all images.I have implemented SFM and evaluated on several types of objects and found the following drawbacks.
  1. Do not have shapes as prior
  2. Unoccupied regions of an object
  3. Lossy post-processing steps
<br/>
**A brief block diagram of SFM**
<p align="center">
<img src="./Images/image36.png" width="750" title="Block Diagram of SFM">
</p>

**Implementation and Problems I Noticed**
<p align="center">
<img src="./Images/sfm_failures.gif" width="750" title="Failure Cases in SFM">
</p>



### Single-View & Multi-View 3D Reconstruction by Differentiable Volumetric Rendering
I Implemented a differentiable volumetric rendering method, and the idea of the paper is shape and texture reconstruction in continuous implicit representation where the gradient of depth w.r.t. the network parameters θ has been defined by an analytical expression, as shown in the figure below. The main issues where I am working on is to design a model that should be an end-to-end to estimate camera information, lighting, and other material properties while reconstructing any object in a real scene.
<p align="center">
<img src="./Images/dvr_problem.gif" width="750" title="Problem in DVR">
</p>

<!-- +  

## Deep Learning Based Methods
## 1. Scene Representation Network: 
### Continuous 3D-Structure-Aware Neural Scene Representations (NeurIPS 2019)
<br/> Scene Representation Networks (SRNs), a continuous, 3D-structure-aware scene representation that encodes both geometry and appearance. SRNs represent scenes as continuous functions that map world coordinates to a feature representation of local scene properties. By formulating the image formation as a neural, 3D-aware rendering algorithm, SRNs can be trained end-to-end from only 2D observations, without access to depth or geometry. SRNs do not discretize space, smoothly parameterizing scene surfaces, and their memory complexity does not scale directly with scene resolution.
<br/>
<br/> **Repelicated Code and Experiments on Synthetic and Real Dataset**
<br/>  Tweaked and evaluated SRNs on real objects for novel views generation and it failed in this task as **Agustus** and **Flower** are real objects and their 3D scene is rough.
| ShapeNet (Sythetic Data) | <img src = "Images/SRNs/cars.gif" width="450" height="150">|
|:---:|:---:|
| Agustus (Real Data) | <img src = "Images/SRNs/agustus.gif"  width="450" height="150"> |
| Flower (Real Data) | <img src = "Images/SRNs/flower.gif" width="450" height="150">|
| |**Normals** &nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **Rendered** &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **Groundtruth**|



## 2. SDFDiff 
### Differentiable Rendering of Signed Distance Fields for 3D Shape Optimization (CVPR-2020)
<br/> SDF-based differentiable renderer can be integrated with deep learning models, which opens up options for learning approaches on 3D objects without 3D supervision.
<br/> **Repelicated Code and Experimental Work**
<br/> **Multi-View-3D Resconstruction Results**
<br/> based on Signed Distance Field and Differentiable Rendering
| Res 56 | <img src = "Images/SDFDiff/grid_res_56_target_12.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_56_target_14.png" width="120" height="120"> | <img src = "Images/SDFDiff/grid_res_56_target_17.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_56_target_21.png" width="120" height="120"> | <img src ="Images/SDFDiff/grid_res_56_target_25.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_56_target_9.png" width="120" height="120">  |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| Res 32 | <img src = "Images/SDFDiff/grid_res_32_target_12.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_32_target_14.png" width="120" height="120"> | <img src = "Images/SDFDiff/grid_res_32_target_17.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_32_target_21.png" width="120" height="120"> | <img src ="Images/SDFDiff/grid_res_32_target_25.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_32_target_9.png" width="120" height="120"> |
| Res 16 | <img src = "Images/SDFDiff/grid_res_16_target_12.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_16_target_14.png" width="120" height="120"> | <img src = "Images/SDFDiff/grid_res_16_target_17.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_16_target_21.png" width="120" height="120"> | <img src ="Images/SDFDiff/grid_res_16_target_25.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_16_target_9.png" width="120" height="120"> |
| Res 8 | <img src = "Images/SDFDiff/grid_res_8_target_12.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_8_target_14.png" width="120" height="120"> | <img src = "Images/SDFDiff/grid_res_8_target_17.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_8_target_21.png" width="120" height="120"> | <img src ="Images/SDFDiff/grid_res_8_target_25.png" width="120" height="120"> |<img src = "Images/SDFDiff/grid_res_8_target_9.png" width="120" height="120"> |
|-| Rendered View 1  | Rendered View 2 | Rendered View 3 | Rendered View 4 | Rendered View 5 | Rendered View 6 |

## 3. Differentiable Volumetric Rendering
### Learning Implicit 3D Representations without 3D Supervision
Proposes an analytic gradients for the predicted depth map with respect to the network parameters of the implicit shape and texture representation. It use ShapeNet data for single-view 3D reconstruction and real dataset to evaluate multi-view 3D reconstruction performance.
<br/>
**Repelicated Code and Experimental Work**
<br/> I am currently implementing this paper and finding one direction for my publication, any collaboration will be welcomed.


+ -->

## Reference Papers
1. [Sitzmann, Vincent, Michael Zollhöfer, and Gordon Wetzstein. "Scene representation networks: Continuous 3d-structure-aware neural scene representations." Advances in Neural Information Processing Systems. 2019.](http://papers.nips.cc/paper/8396-scene-representation-networks-continuous-3d-structure-aware-neural-scene-representations)
2. [Eslami, SM Ali, et al. "Neural scene representation and rendering." Science 360.6394 (2018): 1204-1210.](https://science.sciencemag.org/content/360/6394/1204/tab-pdf)
3. [Niemeyer, Michael, et al. "Differentiable volumetric rendering: Learning implicit 3d representations without 3d supervision." Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. 2020.](https://openaccess.thecvf.com/content_CVPR_2020/html/Niemeyer_Differentiable_Volumetric_Rendering_Learning_Implicit_3D_Representations_Without_3D_Supervision_CVPR_2020_paper.html)

