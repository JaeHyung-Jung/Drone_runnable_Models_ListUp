## Differnce between Normal Detection & Drone Detection
#### First, it is important to realize that we cannot realistically run object detection on general purpose embedded hardware such as the raspberry pi and special purpose hardware built for AI inferencing is required.
=> Embedded환경에서 모델을 돌리므로 성능상의 한계로 RaspberryPi와같은 경량모델보다 AI목적으로 설계된 JetsonXavier, TX2와같은 임베디드 시스템이 적합

#### Second, if you run commonly used object detection models, such as YOLO or SSD trained on COCO and Pascal VOC datasets, they won’t do well at all. This is because the view of an object from a height is quite different from that on the ground. Thus, the distribution of the inference data will be very different from that encountered by the model during training, which will cause it to fail.
=> COCO, PascalVOC같은 데이터셋으로 학습된 일반적인 모델(YOLO,SSD)는 Drone에서 Detect를위해 사용하기 적합하지않다.   
위의 데이터셋과 드론에서 Inference하는 이미지는 드론의 높은고도에서 촬영되는 이미지의 특성상 찾고자하는 객체의 형태가 다르기 때문.

위의 문제를 해결하기위해 드론에 적합한 dataset으로 학습 




# Datasets 
- UA-DETRAC(commonly used)
- UAVDT_Dataset(commonly used)
- Stanford Drone Dataset




# 검증된 model(BenchMarked on )
### SpotNet : https://github.com/hu64/SpotNet (Rank 1 on UAVDT)
  * 오류 수정중 (torch.utils.ffi import하는 과정에서 depcrecate오류가남 DCNv2의 오류이고 https://github.com/xingyizhou/CenterNet/issues/7 를 참고하여 DCNv2의 make해줘야함)

### RN-VID : https://github.com/hu64/RN-VID (Rank 2 on UAVDT)

### R-FCN : https://github.com/daijifeng001/R-FCN

### SSD : https://github.com/lufficc/SSD

### Faster-RCNN : https://github.com/rbgirshick/py-faster-rcnn

### RON :




# models

#### Jetson suitable model(Inference)
Link : https://github.com/dusty-nv/jetson-inference

#### Retinanet Detection on Jetson Xavier(Inference)
Link : https://towardsdatascience.com/detecting-pedestrians-and-bikers-on-a-drone-with-jetson-xavier-93ce92e2c597

#### FasterRCNN Drone Detection(Inference, Chinese)
Link : https://github.com/zhpmatrix/VisDrone2018

#### YOLO Autonomous Drone - Deep Learning Person Detection
Link : https://github.com/durner/yolo-autonomous-drone

#### Drone Realtime_Detection (Yolo, 경량)
Link : https://github.com/carlosfab/drone_object_detection

#### Passive RF Drone Detection for the Georgia Tech Police Department
Link : https://github.com/tesorrells/RF-Drone-Detection

#### ZoominNet(newer model(2021))
Link : https://github.com/qaz670756/ZoomInNet-cross-scale-distillation

#### Keras Retinanet(HighQaulity, Recommeded)
Link : https://github.com/huma-teknofest/Keras-RetinaNet-for-Teknofest-2019

#### GapFlyPt Drone Detection(GoodQuality, not recommended because of License)
Link : https://github.com/prgumd/GapFlyt

#### 
Link : 

#### 
Link : 
