# D2Det
(Link : https://github.com/JialeCao001/D2Det)

## Installation
### Requirements
* Linux(Windows not supported)
* Python 3.5+
* PyTorch 1.1 or higher
* CUDA 9.0 or higher
* NCCL 2
* GCC 4.9 or higher
* mmcv

### Install mmdetection
1) Create a conda virtual environment and activate it.
```text
conda create -n open-mmlab python=3.7 -y
conda activate open-mmlab
```

2) Install PyTorch and torchvision 
```text
conda install pytorch torchvision -c pytorch
```

3) Clone the mmdetection repository
```text
git clone https://github.com/open-mmlab/mmdetection.git
cd mmdetection
```

4) Install build requirements and then install mmdetection. (We install pycocotools via the github repo instead of pypi because the pypi version is old and not compatible with the latest numpy.)
```text
pip install -r requirements/build.txt
pip install "git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI"
python setup.py develop
```
### Demo
```text
python ./demo/D2Det_demo.py ./configs/D2Det/D2Det_instance_r101_fpn_2x.py ./D2Det-instance-res101.pth ./demo/demo.jpg --out ./demo/aa.jpg
```

### Inference
```text
python tools/test.py configs/faster_rcnn_r50_fpn_1x.py \
    checkpoints/faster_rcnn_r50_fpn_1x_20181010-3d1b3351.pth \
    --show
```

## Results(BenchMark)
|name	|backbone	|iteration	|task	|validation	|test-dev	|download|
|---|---|---|---|---|---|---|
|D2Det	|ResNet50	|24 epoch	|object detection	|43.7 (box)	|43.9 (box)	|[Resnet50](https://drive.google.com/file/d/1es6y8Uu-fByOmTq_Y_M5uMuO42_ARI7k/view)|
|D2Det	|ResNet101	|24 epoch	|object detection	|44.9 (box)	|45.4 (box)	|[Resnet101](https://drive.google.com/open?id=14Cw9Y3vSdirkR3xLcb6F6H1hHr3qzLNj)|
|D2Det	|ResNet101-DCN	|24 epoch	|object detection	|46.9 (box)	|47.5 (box)	|[Resnet101-DCN](https://drive.google.com/open?id=1jDeAj_rMKLMf64BGwqiysis9IyZzTQ6w)|
|D2Det	|ResNet101	|24 epoch	|instance segmentation	|39.8 (mask)	|40.2 (mask)	|[Resnet101](https://drive.google.com/open?id=14Cw9Y3vSdirkR3xLcb6F6H1hHr3qzLNj)|


## Inference Results with UAVDT dataset.
![UAVDT_D2Det](https://user-images.githubusercontent.com/79160507/131081442-0bcac618-1aa8-4b44-8d54-c35302f32db2.PNG)

![UAVDT_D2Det2](https://user-images.githubusercontent.com/79160507/131081445-ede4dbda-6637-4b90-8f08-65e0796f1031.PNG)

Backbone model : Resnet101, AP : 47.4
*black regions are ignored.

### Reference : D2Det paper (https://openaccess.thecvf.com/content_CVPR_2020/papers/Cao_D2Det_Towards_High_Quality_Object_Detection_and_Instance_Segmentation_CVPR_2020_paper.pdf)
