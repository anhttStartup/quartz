## What
**Contact**
	Website https://cgv.cs.nthu.edu.tw/projects/dulanet
	Gitlab https://github.com/SunDaDenny/DuLa-Net
**Intro**
	A Dual-Projection Network for Estimating Room Layouts from a Single RGB Panorama
**Thumbnail**
	![](https://i.imgur.com/SJgXM6P.png)

## How
#### Algorithm
Given the input as an equirectangular panoramic image, we follow the same pre-processing step used in [PanoContext](http://panocontext.cs.princeton.edu/) to align the panoramic image with a global coordinate system, i.e. we make a Manhattan world assumption. Then, we transform the panoramic image into a perspective ceiling-view image through an equirectangular to perspective (E2P) conversion. The panorama-view and ceiling-view images are then fed to a network consisting of two encoder-decoder branches. These two branches are connected via an E2P-based feature fusion scheme and jointly trained to predict a floor plan probability map, a floor-ceiling probability map, and the layout height. Two intermediate probability maps are derived from the floor-ceiling probability map using E2P conversion and combined with floor plan probability map to obtain a fused floor plan probability map. The final 3D Manhattan layout is determined by extruding a 2D Manhattan floor plan estimated on the fused floor plan probability map using the predicted layout height.

![](https://i.imgur.com/3zQhtvS.png)
