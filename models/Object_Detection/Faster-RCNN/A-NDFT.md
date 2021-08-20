# A-NDFT(backbone : faster-RCNN)
Link : https://github.com/2-Chae/A-NDFT

## Installation
#### Requirements
  * Linux(Windows not supported)
  * Python 3.6
  * PyTorch 0.4.1
  * Torchvision 0.2.1
  * CUDA 9.0/9.1

### Start Up
1) Create V-env and install library
```text
conda 
pip install torch==1.0.1 torchvision==0.2.0 -f https://download.pytorch.org/whl/torch_stable.html.
python==3.6.13, numpy==1.19.5, Pillow==8.2.0, and scipy==1.2.0
```

2) Install requirements
```text
cd A-NDFT
pip install -r requirements.txt (cython,cffi,opencv-python,scipy,msgpack,easydict,matplotlib,pyyaml,tensorboardX)
```

3) Make and Setup
```text
cd ./lib
python setup.py build develop
sh ./make.sh
```

3-1) Error handling
When encounter error "invalid command 'develop'
(you can use any other editor like 'nano' || 'gedit')
```python
1) vim setup.py 
2) replace the line "from disutils.core import setup" => "from setuptools import setup"
```

4) Download file && Locate it to directory
download this file[download file](https://c11.kr/ls8k), and locate it in the directory "./lib/model/nms/src"

5) make nms
```text
cd ./lib/model/nms
sh make.sh
```

6) Multi GPU Training
```text
CUDA_VISIBLE_DEVICES=0,1,2,3 python trainval_net_monitor.py --cuda --mGPUs --gamma_weather 0.01  --gamma_angle 0.01 --gamma_altitude 0.01 --use_adversarial_loss --bs 32 --ema-beta 0.99 
```

#### ++) Download Pretrained Model 
[Faster-RCNN_pretrained](https://drive.google.com/file/d/1rxqr0Cq0y9cXhdWyNd_R_8cd68exD1wn/view?usp=sharing)

#### Citation(Original Code : UAV-NDFT)
```text
@InProceedings{Lee_2021_CVPR_Workshops,
author = {Lee, Chaehyeon and Seo, Junghoon and Jung, Heechul},
title = {Training Domain-invariant Object Detector Faster with Feature Replay and Slow Learner},
booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR) Workshops},
month = {June},
year = {2021}
}
`text
