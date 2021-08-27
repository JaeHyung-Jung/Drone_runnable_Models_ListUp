# RetinaNet
This model uses Keras, Tensorflow so there can be some errors but chose this model because of quality.
This model can also inference on Video.
Link : https://github.com/huma-teknofest/Keras-RetinaNet-for-Teknofest-2019

## Start-up
1) Create a conda virtual environment and activate it.
```python
conda create -n retina python=3.7
conda activate retina
```

2) Install Requirements
```python
cd Keras-RetinaNet-for-Teknofest-2019/retinanet
pip install -r requirements.txt
```

3) Compile library
```python
python3 setup.py build_ext --inplace
```

3-1) Folder Layout
```text
main_dir
- dataset_test
- retinanet
    - keras_retinanet
    - models
        - teknofest19_huma_resnet50_21_37_inference.h5
    - snapshots
        - teknofest19_huma_resnet50_21_37_ss.h5
    - results
    - detect_all_images.py
```

4) Run detect_all_images.py

++ Pretrained Model(Resnet50) ## This link includes Small Data(Snapshots)
[Pretrained](https://drive.google.com/drive/folders/1UQ-QpEN_iw01bYSj2u0k8bepWpjmpxye)
Download pretrained model(.h5) and then locate it below diretory 'retinanet'

++ training procedue : [Retinanet_Link](https://github.com/fizyr/keras-retinanet)

## Inference sample 
![image](https://user-images.githubusercontent.com/79160507/131089959-3bba7885-e7a5-4250-b5b6-050fa74fa9f6.png)



