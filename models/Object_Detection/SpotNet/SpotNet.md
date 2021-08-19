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

#### Train & Test 
```text
1. git clone https://github.com/hu64/SpotNet.git
```

```text
2. install 'requirements.txt' (opencv-python, Cython, numba, progress, matplotlib, easydict, scipy)
```


```text
3. Download pretrained model 
Link : https://polymtlca0-my.sharepoint.com/:f:/g/personal/hughes_perreault_polymtl_ca/EhqSkfDIJ-JBh9_YhCrPQrEBocvfP6BIucODKdcNjZzlcA?e=niahaB
```


```text
2. 
```


```text
2. 
```


```text
2. 
```


#### License
MIT License

Copyright (c) 2020 Hu 

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
