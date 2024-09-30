# 문장 간 유사도 측정
본 프로젝트는 의미 유사도 판별(Semantic Text Similarity, STS)이란 두 문장이 의미적으로 얼마나 유사한지를 수치화하는 자연어처리 태스크입니다.

## 1. Overview

### 🚩 Semantic Text Similarity Project
두 개의 문장과 유사도 라벨이 붙어있는 데이터를 학습하고, 테스트 데이터의 유사도를 측정하는 Task를 진행하는 Project입니다.

1. 두 개의 문장이 주어집니다
2. 두 문장간의 문맥적 유사도를 0 ~ 5 사이의 숫자로 측정합니다

<br>

### ⏰ 개발 기간
- 2024년 09월 10일(화) 10:00 ~ 2024년 09월 26일(목) 19:00
- 부스트캠프 AI Tech NLP 트랙 6-7주차

<br>

### ✨ 분석 환경
- Upstage AI Stages 제공 V100 GPU Server 활용

<br>

### 💡 구현 기능
- **STSDataset Class** : 데이터 셋 클래스
  - 데이터를 가져오는 getitem method와 길이를 출력하는 len method 포함
- **RegressionModel**
  - 모델 구조
    - Forward
    - Train(90%) : 모델 훈련 수행
    - Evaluate(10%) : 모델 평가
  - Parameters
    - Tokenizer max len : 128
    - batch size : 32
    - Learning rate : 2e-5
    - Epochs : 12
    - Loss : MSE
- **Ensemble** : 도출된 예측 값들을 평균내어 결과 값 도출

<br>

### 🎈 결과 모델 Specification
- Pearson(Public) : 0.9315
- Pearson(Private) : 0.9352
- 앙상블에 활용한 모델
  - snunlp/KR-ELECTRA-discriminator
  - beomi/KcELECTRA-base-v2022
  - monologg/koelectra-base-v3-discriminator

<br>

---

## 2. Team
<table>
    <tbody>
        <tr>
            <td align="center">
                <a href="https://github.com/Kimyongari">
                    <img src="https://github.com/Kimyongari.png" width="100px;" alt=""/><br />
                    <sub><b>Kimyongari</b></sub>
                </a><br />
                <sub>김용준</sub>
            </td>
            <td align="center">
                <a href="https://github.com/son0179">
                    <img src="https://github.com/son0179.png" width="100px;" alt=""/><br />
                    <sub><b>son0179</b></sub>
                </a><br />
                <sub>손익준</sub>
            </td>
            <td align="center">
                <a href="https://github.com/P-oong">
                    <img src="https://github.com/P-oong.png" width="100px;" alt=""/><br />
                    <sub><b>P-oong</b></sub>
                </a><br />
                <sub>이현풍</sub>
            </td>
            <td align="center">
                <a href="https://github.com/Aitoast">
                    <img src="https://github.com/Aitoast.png" width="100px;" alt=""/><br />
                    <sub><b>Aitoast</b></sub>
                </a><br />
                <sub>정석현</sub>
            </td>
            <td align="center">
                <a href="https://github.com/uzlnee">
                    <img src="https://github.com/uzlnee.png" width="100px;" alt=""/><br />
                    <sub><b>uzlnee</b></sub>
                </a><br />
                <sub>정유진</sub>
            </td>
            <td align="center">
                <a href="https://github.com/hayoung180">
                    <img src="https://github.com/hayoung180.png" width="100px;" alt=""/><br />
                    <sub><b>hayoung180</b></sub>
                </a><br />
                <sub>정하영</sub>
            </td>
        </tr>
    </tbody>
</table>



## Reference
