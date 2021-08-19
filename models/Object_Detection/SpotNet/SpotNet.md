# SpotNet (Link : https://github.com/hu64/SpotNet)
SpotNet acheived the 'SOTA' in UAVDT, UA-DETRAC

## Paper link : https://arxiv.org/abs/2002.05540

## Architecture : 
![image](https://user-images.githubusercontent.com/79160507/130042875-45fa0e5e-5e85-43f3-9abf-d8ddae348207.png)
Overview of SpotNet: the input image first passes through a double-stacked hourglass network; the segmentation head then produces an attention map that multiplies the final feature map of the backbone network; the final center keypoint heatmap is then produced as well as the size and coordinate offset regressions for each object.

## Functions : 
  * Object Detection
  * Semi-supervised Segmentation

### Results on UA-DETRAC :
Model	Overall	Easy	Medium	Hard	Cloudy	Night	Rainy	Sunny
SpotNet (ours)	86.80%	97.58%	92.57%	76.58%	89.38%	89.53%	80.93%	91.42%
CenterNet	83.48%	96.50%	90.15%	71.46%	85.01%	88.82%	77.78%	88.73%
FG-BR_Net	79.96%	93.49%	83.60%	70.78%	87.36%	78.42%	70.50%	89.8%
HAT	78.64%	93.44%	83.09%	68.04%	86.27%	78.00%	67.97%	88.78%
GP-FRCNNm	77.96%	92.74%	82.39%	67.22%	83.23%	77.75%	70.17%	86.56%
R-FCN	69.87%	93.32%	75.67%	54.31%	74.38%	75.09%	56.21%	84.08%
EB	67.96%	89.65%	73.12%	53.64%	72.42%	73.93%	53.40%	83.73%
Faster R-CNN	58.45%	82.75%	63.05%	44.25%	66.29%	69.85%	45.16%	62.34%
YOLOv2	57.72%	83.28%	62.25%	42.44%	57.97%	64.53%	47.84%	69.75%
RN-D	54.69%	80.98%	59.13%	39.23%	59.88%	54.62%	41.11%	77.53%
3D-DETnet	53.30%	66.66%	59.26%	43.22%	63.30%	52.90%	44.27%	71.26%
