# 문장 간 유사도 측정
본 프로젝트는 의미 유사도 판별(Semantic Text Similarity, STS)이란 두 문장이 의미적으로 얼마나 유사한지를 수치화하는 자연어처리 태스크입니다.

## 1. Overview

### 🚩 Semantic Text Similarity Project
두 개의 문장과 유사도 라벨이 붙어있는 데이터를 학습하고, 테스트 데이터의 유사도를 측정하는 Task를 진행하는 Project입니다.

1. 두 개의 문장이 주어집니다
2. 두 문장간의 문맥적 유사도를 0 ~ 5 사이의 숫자로 측정합니다

<br>

## 2. 프로젝트 구성

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

### EDA
데이터의 분포와 특성을 파악하고, Data preprocessing의 방향성을 설정하기 위한 단계입니다.
1. Label별 분포 확인
- Label 0에서의 분포가 약 2배 이상 많고, Label 5에서의 분포는 다른 라벨에서보다 확연히 적은 개수를 보였습니다.
2. 중복 데이터 및 문장
- Train 데이터셋에서 sentence 1과 sentence 2에서 중복되는 문장들이 약 13,000개 정도가 있었습니다.
3. 데이터 특성 확인
- Label 5를 제외한 다른 Label의 평가 기준에 대해서 판단하기에 주관성이 들어가 학습이 제대로 이루어지지 않을 것 같아서, Label 5에 대해서만 특성을 확인하였습니다.
- 띄어쓰기, 맞춤법, 특수기호 등의 차이로 동일한 문장이라고 판단하였습니다.

<br>

## 3. 프로젝트 결과

|      | Pearson (Public) | Pearson (Private) | 사용 기법 | Loss | Model | Epoch | Learning Rate |
|------|------------------|-------------------|-------------|------|-------------|-------|---------------|
| 1    | 0.9331           | 0.9372            | Ensemble    | MSE  | upskyy/bge-m3-korean, klue/roberta-large, beomi/KcELECTRA-base-v2022 | 3     | 2e-5 (첫 10% 동안 warmup 후 선형 감소) |
| 2    | 0.9315           | 0.9352            | Ensemble    | MSE  | snunlp/KR-ELECTRA-discriminator, beomi/KcELECTRA-base-v2022, monologg/koelectra-base-v3-discriminator | 12    | 2e-5            |



<br>

---

## 4. Team
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
모델 앙상블을 위해 사용했던 HuggingFace 모델들
1. Alibaba-NLP/gte-multilingual-base (https://huggingface.co/Alibaba-NLP/gte-multilingual-base)
2. beomi/KcELECTRA-base-v2022 (https://huggingface.co/beomi/KcELECTRA-base-v2022)
3. jhgan/ko-sroberta-multitask (https://huggingface.co/jhgan/ko-sroberta-multitask)
4. klue/bert-base (https://huggingface.co/klue/bert-base)
5. klue/roberta-small (https://huggingface.co/klue/roberta-small)
6. klue/roberta-base (https://huggingface.co/klue/roberta-base)
7. klue/roberta-large (https://huggingface.co/klue/roberta-large)
8. kykim/bert-kor-base (https://huggingface.co/kykim/bert-kor-base)
9. monologg/koelectra-base-v3-discriminator (https://huggingface.co/monologg/koelectra-base-v3-discriminator)
10. sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2 (https://huggingface.co/sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2)
11. snunlp/KR-SBERT-Medium-extended-klueNLItriplet_PARpair_QApair-klueSTS (https://huggingface.co/snunlp/KR-SBERT-Medium-extended-klueNLItriplet_PARpair_QApair-klueSTS)
12. snunlp/KR-SBERT-Medium-klueNLItriplet_PARpair-klueSTS (https://huggingface.co/snunlp/KR-SBERT-Medium-klueNLItriplet_PARpair-klueSTS)
13. upskyy/bge-m3-korean (https://huggingface.co/upskyy/bge-m3-korean)
