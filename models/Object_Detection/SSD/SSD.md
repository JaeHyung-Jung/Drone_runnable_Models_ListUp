# LRF-Net (backbone SSD)
Link : https://github.com/vaesl/LRF-Net

## Installation
1) Clone repository. 
```text
    LRFNet_ROOT=/path/to/clone/LRFNet
    git clone https://github.com/vaesl/LRF-Net $LRFNet_ROOT
```

2) Create Virtual Environment : Ubuntu16.04, Python 3.5/6, pytorch v0.3.1, need Nvidia GPU
```text
    conda create -n LRFNet python=3.5
    source activate LRFNet
    conda install pytorch=0.3.1 torchvision -c pytorch
```

3) Install opencv
```text
    conda install opencv || pip install opencv
```

4) Compile both COCOAPI & NMS
```text
    cd $LRFNet_ROOT/
    ./make.sh
```

5) Download Dataset
Download COCO dataset with link [COCO](https://cocodataset.org/#download)

5-1) Locate the data to be like below. 
```text
${$LRF_ROOT}
|-- data
`-- |-- coco
    `-- |-- annotations
        |   |-- instances_train2014.json
        |   |-- instances_val2014.json
        |   |-- image_info_test-dev2015.json
        `-- images
        |   |-- train2014
        |   |-- val2014
        |   |-- test2015
        `-- cache
```

6) Download Pretrained Models
```text
[LRF_COCO_PrModel](https://drive.google.com/drive/folders/1_k6EOL1aIVtjI-3m5PEYC2Ri3ahUEi8T)
and then put this pth to directory ('~/weights/COCO/LRF_COCO_300/')
```

7) Evaluate
```text
python test_LRF.py -d COCO -s 300 --trained_model /path/to/model/weights
```
the option '-d' is for choosing dataset, '-s' for reshaped image size(300 || 512)

8) License(Cite)
```text
@article{Wang2019LRF,
    title = {Learning Rich Features at High-Speed for Single-Shot Object Detection},
    author = {Tiancai Wang, Rao Muhammad Anwer, Hisham Cholakkal, Fahad Shahbaz Khan, Yanwei Pang, Ling Shao},
    booktitle = {ICCV},
    year = {2019}
}
```

## Inference Results with UAVDT17 dataset![LRFNet_benchmark]![LRFNet_benchmark]
![UAVDT_LRFnet](https://user-images.githubusercontent.com/79160507/131087394-b863315e-0534-4e50-8d13-cfe643d913a8.PNG)

## UAVDT-BenchMark
![LRFNet_benchmark](https://user-images.githubusercontent.com/79160507/131087486-a2991876-a328-4c65-8bf0-9a79b0a969a3.PNG)
