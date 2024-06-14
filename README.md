# First-Line
Image classification(2024 spring)  
스푸핑 이미지와 실제 이미지를 분류하는 AI 모델 개발

### 환경
캐글

### 실험 설정
총 5개의 모델을 앙상블 했으며, 각 모델은 독립적인 파일에서 학습 및 테스트 진행이 필요합니다.

| Model | agumentation | Notes | Accuracy |
|-------|--------------|-------|----------|
| Model 1 | Yes | - | 92.3% |
| Model 2 | No | - | 90.5% |
| Model 3 | Yes | Improved data handling | 93.1% |
| Model 4 | No | - | 89.9% |
| Model 5 | Yes | Uses advanced techniques | 94.2% |

## Usage
------------------------  

### Training
1. 캐글에서 각 모델의 train 파일을 실행 후 `pth` 파일을 저장합니다.
2. 생성된 `pth` 파일로 각 모델의 테스트를 돌린 후 submission 파일을 저장합니다.
3. 모델 5개를 각각 독립적으로 실행합니다.
4. voting 파일과 같은 경로에 submission 파일 5개를 위치시킵니다.
5. voting 파일을 실행하면 앙상블 결과 파일이 생성됩니다.
