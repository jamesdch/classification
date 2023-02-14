# EfficientNet_b0

![image](https://user-images.githubusercontent.com/125367053/218742249-5acfc69a-0f6a-4f60-96f9-206dd2066cb9.png)

한정된 Resource 내에서 최대 효율을 내기 위해 model scaling(depth, width, resolution)을 시스템적으로 분석하여 도출한 분류모델 

Depth, width, resolution이 서로 긴밀히 연결되어 있기에 어떻게 적절히 조절할지 제시 및 모델 크기와 연산량을 줄이면서 성능 높이는 방법을 제안

단일한 dimension(depth, width, resolution 중 1)을 키우는 것보다 함께 증가시키는 것이 중요함을 실험을 통해 증명

모델 크기는 RestNet-50보다 약 1/5 수준이지만 정확도는 1.1% 우수한 모델(EfficientNet-B0 기준)  

분류모델 EfficientNet-B0를 사용하여 8개의 class 분류

8개 Class : No Error, Gaps, Warping, Lines of Print, Separation, Stringing, Blow out, Etc Print Error

## Data Preprocessing


## Model Training

## Model Testing
