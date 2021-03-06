# SpotNet
SpotNet acheived the 'SOTA' in UAVDT, UA-DETRAC (Link : https://github.com/hu64/SpotNet)   
File size is too big to upload. So use git clone

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

#### Test 
```text
1. git clone https://github.com/hu64/SpotNet.git
```

activate v-env with codes below
```text
2. conda activate
```

```text
3. cd 'object detection' &&
pip install -r requirements.txt #opencv-python, Cython, numba, progress, matplotlib, easydict, scipy
```

```text
4. cd src && python demo.py
```
If you see errors like "ModuleNotFoundError : No module named '_ext', then
```text
5-1. build nms
cd SpotNet/'object detection'/src/lib/external
#python setup.py install
python setup.py build_ext --inplace
```

Clone and build original DCN2 
```text
5-2. cd SpotNet/'object detection'/src/lib/models/networks
rm -rf DCNv2
git clone https://github.com/CharlesShang/DCNv2
cd DCNv2

vim src/cuda/dcn_v2_cuda.cu
"""
# extern THCState *state;
THCState *state = at::globalContext().lazyInitCUDA();
"""

python setup.py build develop
```

```text
6. test
cd CenterNet/'object detection'/src
python demo.py ctdet --demo ../images/17790319373_bd19b24cfc_k.jpg --load_model ../models/ctdet_coco_dla_2x.pth --debug 2
python demo.py multi_pose --demo ../images/17790319373_bd19b24cfc_k.jpg --load_model ../models/multi_pose_dla_3x.pth --debug 2
```

+++ Pretrained model Link :  https://polymtlca0-my.sharepoint.com/:f:/g/personal/hughes_perreault_polymtl_ca/EhqSkfDIJ-JBh9_YhCrPQrEBocvfP6BIucODKdcNjZzlcA?e=niahaB

## Inference Results with UA-DETRAC data
![Spotnet_UADETRAC](https://user-images.githubusercontent.com/79160507/131088374-4d265a66-521c-495a-9f98-a16f4134eec7.PNG)

## Inference Results with UAVDT data
![Spotnet-UAVDT](https://user-images.githubusercontent.com/79160507/131088402-b1c8dceb-dbf5-4859-8ca1-0d6efa4ab302.PNG)

## UA-DETRAC BenchMark 
![Spotnet_Benchmark](https://user-images.githubusercontent.com/79160507/131088571-007f5087-375e-483b-bd9b-6c59403dd659.PNG)

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
