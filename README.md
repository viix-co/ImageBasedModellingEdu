## ImageBasedModellingEduV2.0
ImageBasedModellingEdu2.0 - code used to support the image-based 3D model reconstruction course of Deep Blue Academy. The code comes from the famous open source 3D reconstruction open source system: [MVE](https://github.com/simonfuhrmann/mve)
Based on this, we have adjusted the structure of the code to make it more relevant to the course and helpful for reading and learning. This project is managed using CMake, which allows for easy cross-platform compilation. The code includes modules such as feature extraction and matching, epipolar geometry, motion recovery structure, dense reconstruction, surface reconstruction, texture mapping, and visualization, and will be continuously updated as the course progresses.

## Architecture
The project mainly includes: core, math, util, features, sfm, mvs, surface, texturing, and other main modules, among which included:
- core - provides all basic data structures needed for engineering projects，include image, depthmap, mesh, view, and data input and output and other structures and functions;
- math provide matrix，vector, basic mathematical operations such as quaternions;
- features - provide feature extraction and feature matching functions，feature types include sift and surf;
- sfm (**Structure-from-Motion**) - rovides functionality related to **motion recovery structures**, **camera position recovery**，triangulation and bundle adjustment of 3D-points etc..;
- mvs - provide **stereo matching** function，implementation **dense point cloud matching**;
- surface - implement point cloud to mesh surface reconstruction;
- texturing - implement creation of texture images;
- examples - provide sample code for some key modules;
- tmp - store temporary data;

## Compilation（Mac and Linux, Window compilation is not verified)
1.Install dependent libraries including: libpng, libjpeg, libtiff, eigen

 ### Linux
 sudo apt-get install libjpeg-dev
 
 sudo apt-get install libtiff-dev
 
 ### Mac
 brew install libpng 
 
 brew install libjpeg
 
 brew install libtiff
 
2. Build the implementation 

    git clone https://github.com/weisui-ad/ImageBasedModellingEdu.git
    
    cd ~/ImageBasedModellingEdu
    
    mkdir build && cd build
    
    cmake -DCMAKE_BUILD_TYPE=Release .. 
    
    make -j8

3. Code examples/

   ./build/examples/task3/task3-1_incremental_sfm ./examples/data/sequence ./examples/data/sequence_scene

 
