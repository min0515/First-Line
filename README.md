# First-Line Team
Image classification(2024 spring)  
스푸핑 이미지와 실제 이미지를 분류하는 AI 모델 개발  
<br>
<br>
### Environment
캐글 및 코랩  
<br>
<br>
### Experiment
총 5개의 모델을 앙상블 했으며, 각 모델은 독립적인 파일에서 학습 및 테스트 진행이 필요합니다.

| Model | agumentation | Notes | Accuracy(Public) |
|-------|--------------|-------|----------|
| Model 1 | Yes | - | 92.3% |
| Model 2 | No | - | 90.5% |
| Model 3 | Yes | Improved data handling | 93.1% |
| Model 4 | No | - | 89.9% |
| Model 5 | JpegCompression & ColorJitter | Resize(380down) & CenterCrop(380up) | 96.5% |
<br>
<br>
<br>
<br>

## Usage 

### Training
1. 캐글에서 모델의 train 파일을 실행 후 `pth` 파일을 저장합니다. 
2. 생성된 `pth`을 저장합니다.
(pth파일은 "checkpoint/model_모델번호.pth"에 생성됌)
<br>
  
### Test
1. 'pth' 파일을 "checkpoint/model(모델번호).pth"에 위치하게 합니다.
2.  테스트 코드를 실행 후 submission 파일을 저장합니다.
(submission_model(모델번호).csv로 생성됌)
<br>
  
### Ensemble
1. 학습과 테스트 과정을 모델 5개 각각 독립적으로 수행합니다.
2. voting 파일과 같은 경로에 submission 파일 5개를 위치시킵니다.
3. voting 파일을 실행하면 앙상블 결과 파일이 생성됩니다.
(ensemble_submission.csv로 생성됌)
<br>

  
최종 정확도는 다음과 같습니다.
| Publick | Private |
|----------|----------|
| 98.65%   | 97.66%  |


