# 3D Vision

## Scene Reconstruction

##### SceneComplete

[link](https://arxiv.org/abs/2410.23643); A single RGBD image to a complete scene; 1) a VLM for identifying and generating short descriptions of the objects (ChatGPT-4o); a text-grounded image-segmentation model (Grounded2Sam2); a 2D image-inpainting model for predicting the appearance of occluded parts of objects (BrushNet, they also use LoRA to fine-tune the BrushNet on single fully observed object); an image-to-3D model for generating complete object meshes (InstantMesh and Mesh Scaling using Dense Correspondence Matching because InstantMesh outputs meshes in an arbitrary orientation and at an arbitrary scale); visual descriptor and pose-estimation tools ( FoundationPose);