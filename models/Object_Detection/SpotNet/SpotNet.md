# SpotNet
SpotNet acheived the 'SOTA' in UAVDT, UA-DETRAC (Link : https://github.com/hu64/SpotNet)

## Paper link : https://arxiv.org/abs/2002.05540

## Architecture : 
![image](https://user-images.githubusercontent.com/79160507/130042875-45fa0e5e-5e85-43f3-9abf-d8ddae348207.png)
Overview of SpotNet: the input image first passes through a double-stacked hourglass network; the segmentation head then produces an attention map that multiplies the final feature map of the backbone network; the final center keypoint heatmap is then produced as well as the size and coordinate offset regressions for each object.

## Functions : 
  * Object Detection
  * Semi-supervised Segmentation

### Results on UAVDT :
| Model |	Overall |
|---|---|
|SpotNet (Ours)|	52.80%|
|CenterNet	|51.18%|
|Wang \etal	|37.81%|
|R-FCN	|34.35%|
|SSD	|33.62%|
|Faster-RCNN|	22.32%|
|RON	|21.59%|
