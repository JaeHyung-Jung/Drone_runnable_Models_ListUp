## Differnce between Normal Detection & Drone Detection
#### First, it is important to realize that we cannot realistically run object detection on general purpose embedded hardware such as the raspberry pi and special purpose hardware built for AI inferencing is required.
=> Embedded환경에서 모델을 돌리므로 성능상의 한계로 RaspberryPi와같은 경량모델보다 AI목적으로 설계된 JetsonXavier, TX2와같은 임베디드 시스템이 적합

#### Second, if you run commonly used object detection models, such as YOLO or SSD trained on COCO and Pascal VOC datasets, they won’t do well at all. This is because the view of an object from a height is quite different from that on the ground. Thus, the distribution of the inference data will be very different from that encountered by the model during training, which will cause it to fail.
=> COCO, PascalVOC같은 데이터셋으로 학습된 일반적인 모델(YOLO,SSD)는 Drone에서 Detect를위해 사용하기 적합하지않다.
위의 데이터셋과 드론에서 Inference하는 이미지는 드론의 높은고도에서 촬영되는 이미지의 특성상 찾고자하는 객체의 형태가 다르기 때문.

위의 문제를 해결하기위해 Stanford대학교에서 공개한 Stanford Drone Dataset(6Classes labeled)으로 학습하는 방법이 있음 

# models

#### Jetson suitable model(Inference)
Link : https://github.com/dusty-nv/jetson-inference

#### Retinanet Detection on Jetson Xavier(Inference)
Link : https://towardsdatascience.com/detecting-pedestrians-and-bikers-on-a-drone-with-jetson-xavier-93ce92e2c597
