# EfficientNet_b0

![image](https://user-images.githubusercontent.com/125367053/218742249-5acfc69a-0f6a-4f60-96f9-206dd2066cb9.png)

한정된 Resource 내에서 최대 효율을 내기 위해 model scaling(depth, width, resolution)을 시스템적으로 분석하여 도출한 분류모델 

Depth, width, resolution이 서로 긴밀히 연결되어 있어 어떻게 적절히 조절할지 제시 및 모델 크기와 연산량을 줄이면서 성능 높이는 방법을 제안

단일한 dimension(depth, width, resolution 중 1)을 키우는 것보다 함께 증가시키는 것이 중요함을 실험을 통해 증명

모델 크기는 RestNet-50보다 약 1/5 수준이지만 정확도는 1.1% 우수한 모델(EfficientNet-B0 기준)  


분류모델 EfficientNet-B0를 사용하여 8개의 class 분류

8개 Class : No Error, Gaps, Warping, Lines of Print, Separation, Stringing, Blow out, Etc Print Error


## Data Preprocessing

분류모델 학습 시 필요한 데이터(이미지명, 이미지 클래스)를 json파일에서 추출

Json의 Source_data_image_code, Print error code 데이터 추출 

추출한 데이터를 Train : Valid : Test = 8 : 1 : 1로 split하고 csv파일로 저장

## Model Training

전처리한 csv파일과 이미지들을 넣어서 dataset 구축

8개 class들을 label로 가진 이미지들을 학습하여 test단계에서 class를 분류하는 모델 학습

EfficientNet_b0 모델을 학습 (Epoch=10, Batch size=128, CrossEntropyLoss, Adam, StepLR)

## Model Testing

학습한 Best model weight를 불러와서 평가수행

log 함수를 통해 testing 결과가 txt파일로 찍히도록 구현 (AUROC = 94.2)

이미지별 실제값, 모델예측값을 담은 csv파일 도출

