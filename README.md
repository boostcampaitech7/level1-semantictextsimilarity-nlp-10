# Open-Domain Question Answering
본 프로젝트는 MRC(기계독해)란 주어진 지문을 이해하고, 주어진 질의의 답변을 추론하는 태스크입니다. => pui 추가중 (pui pui pui)

<br><br>

## 1. Overview

### 🚩 Open-Domain Question Answering(ODQA) Project
`Context` 에서 `Question`에 대한 `Answer`을 찾는 Project입니다.
ODQA는 2 Step을 거쳐 답을 도출하게 됩니다.

<br>

** ODQA 2Steps **
1. `MRC` : `Context` 내에서 `Question`에 대한 `Answer`를 도출하는 방법 학습
(*MRC : Machine Reading Comprehension)
2. `Retrieval` : 문서를 검색하고 해당 문서 내에서 정답 탐색 후 도출

<br>

** 모델 성능 평가 지표(Metrics) **
- EM (Exact Match) : 정답과 예측이 정확히 일치하는 샘플의 비율
- F1 score : 기준 값과 overlap 되는 정도를 F1으로 계산

<br><br>

## 2. 프로젝트 구성

### ⏰ 개발 기간
- 2024년 09월 30일(월) 10:00 ~ 2024년 10월 24일(목) 19:00
- 부스트캠프 AI Tech NLP 트랙 8-10주차

<br>

### ✨ 분석 환경
- Upstage AI Stages 제공 V100 GPU Server 활용

<br>

### 📚 EDA Summary


<br>

### 💡 구현 기능
- MRC
    - Extraction based MRC
    - Generation based MRC
- Retrieval
    - TF IDF Retrieval
    - BM25 Retrieval
    - Dense search Retrieval


<br><br>

## 3. 프로젝트 결과
|Idx  |Public EM|Public F1|Private EM|Private F1|Model|Retrieval|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|1|||||||
|2|||||||


<br><br>


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

<br><br>

---

<br>

## Reference
![My Image](https://upload3.inven.co.kr/upload/2021/03/13/bbs/i013687510742.gif)
