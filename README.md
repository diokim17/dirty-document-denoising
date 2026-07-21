# 📄 Dirty Document Denoising with AutoEncoder

손상된 문서 이미지(Dirty Document)를 복원하기 위해 전통적인 이미지 처리 기법과 Convolutional AutoEncoder를 비교하고,
피드백을 반영하여 모델을 개선한 프로젝트입니다.

> Codeit AI Engineer Sprint Mission 5

---

## 프로젝트 개요

문서 스캔 과정에서 발생하는 얼룩, 노이즈, 번짐 등의 손상을 제거하여
원본 문서를 최대한 복원하는 것을 목표로 하였습니다.

본 프로젝트에서는

- 이미지 전처리 기반 복원
- Convolutional AutoEncoder를 이용한 문서 복원
- 성능 비교(RMSE, PSNR)
- 피드백을 반영한 모델 개선

을 수행하였습니다.

---

## Dataset

[Dirty Documents Dataset](https://www.kaggle.com/competitions/denoising-dirty-documents)

---

## 프로젝트 기간

2026.07.09 ~ 2026.07.14

---

## 프로젝트 구조

```
dirty-document-denoising
│
├── mission5_original.ipynb
│    
├── mission5_feedback_applied.ipynb
│
└── README.md
```

---

## 개발 환경

|항목|내용|
|---|---|
|Language|Python 3|
|Framework|PyTorch|
|Visualization|Matplotlib|
|Environment|Google Colab|

---

## 수행 과정

- 데이터 확인
- 이미지 시각화
- 이미지 전처리
- Gaussian Blur 기반 복원
- Median Blur 기반 복원
- Convolutional AutoEncoder 구현
- 모델 학습
- RMSE / PSNR 평가
- 결과 비교
- 피드백 반영 및 모델 개선

---

## 모델 개선 (Feedback Applied)

기존 제출본에 대한 피드백을 반영하여 다음과 같은 개선을 진행하였습니다.

### 1. Validation Dataset 추가

기존에는 Train Loss만 확인하며 학습을 진행하였습니다.

이를 개선하기 위해 Train Dataset을 Train / Validation으로 분리하여
Validation Loss를 함께 모니터링하도록 수정하였습니다.

---

### 2. Train / Validation Loss 시각화

기존에는 Train Loss만 그래프로 확인하였습니다.

피드백 반영 후에는

- Train Loss
- Validation Loss

를 동시에 시각화하여 모델의 학습 상태와 과적합 여부를 함께 확인할 수 있도록 개선하였습니다.

---

### 3. Epoch 실험 방식 개선

기존에는

- 10 Epoch 학습
- 이후 추가로 30 Epoch 학습

을 수행하여 실제로는 **40 Epoch 모델**이 생성되는 문제가 있었습니다.

이를 개선하여

- 10 Epoch 모델
- 30 Epoch 모델

을 각각 **새로운 모델로 처음부터 학습**하도록 수정하여 공정한 성능 비교가 가능하도록 변경하였습니다.

---

### 4. 모델 비교 방식 개선

각 실험 결과를 별도의 모델로 저장하여

- 10 Epoch
- 30 Epoch
- Improved Model

간의 성능을 독립적으로 비교할 수 있도록 수정하였습니다.

---

## 주요 결과

- AutoEncoder가 Gaussian Blur, Median Blur보다 높은 복원 성능을 보였다.
- Epoch 증가에 따라 RMSE는 감소하고 PSNR은 향상되었다.
- Validation Loss를 함께 확인하여 모델의 일반화 성능을 평가할 수 있도록 개선하였다.
- 피드백을 반영하여 보다 재현 가능한 실험 구조로 개선하였다.

---

## Blog

프로젝트 분석 과정은 아래 글에서 자세히 확인할 수 있습니다.

Velog

- (작성 예정)

---

# License

Educational Purpose
