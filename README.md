# First-Line Team
Image classification(2024 spring)  
스푸핑 이미지와 실제 이미지를 분류하는 AI 모델 개발  
<br>
### Environment
캐글 및 코랩  
<br>
### Experiment
총 5개의 모델을 앙상블 했으며, 각 모델은 독립적인 파일에서 학습 및 테스트 진행이 필요합니다.

| Model | augmentation | Notes | Accuracy(Public) |
|-------|--------------|-------|----------|
| Model 1 | RandAugment | OneCycleLR(epochs=15) | 98.12% |
| Model 2 | RandAugment | OneCycleLR(epochs=7) | 98.00% |
| Model 3 | JpegCompression & ColorJitter & RandomPerspective & RandomHorizontalFlip | Crop20 - Remove bottom 20%(1080*1920) | 96.87% |
| Model 4 | JpegCompression, RandomRotation, RandomHorizontalFlip, ColorJitter | Resize(380d), CenterCrop(380), OneCycleLR(epochs=7) | 97.37% |
| Model 5 | JpegCompression & ColorJitter | Resize(380down) & CenterCrop(380up) | 96.5% |
<br>
<br>

## Usage 

### Training
1. 캐글에서 모델의 train 파일을 실행 후 `pth` 파일을 저장합니다. 
2. 생성된 `pth`을 저장합니다.
(pth파일은 "checkpoint/model_모델번호.pth"에 생성됌)
<br>
  
### Test
1. model_path에 'pth' 파일이 존재하는 경로를 지정합니다.
2. 테스트 코드를 실행 후 submission 파일을 저장합니다.
(submission_model(모델번호).csv로 생성됌)
<br>
  
### Ensemble
1. 학습과 테스트 과정을 모델 5개 각각 독립적으로 수행합니다.
2. voting 파일과 같은 경로에 submission 파일 5개를 위치시킵니다.
3. voting 파일을 실행하면 앙상블 결과 파일이 생성됩니다.
(ensemble_submission.csv로 생성됌)
<br>

  
최종 정확도는 다음과 같습니다.
| Public Accuracy | Private Accuracy |
|----------|----------|
| 98.65%   | 97.66%  |


