# 💳 CardDataAnalysis
> ElasticSearch, Kibana를 활용한 우리 카드 데이터 시각화

## 📒 프로젝트 개요
본 프로젝트는 우리카드의 거래 데이터를 활용하여, 연령대별 소비 패턴과 회원 등급 분포를 분석하고 시각화한 것입니다. 주요 분석 항목으로는 연령대별 총 이용금액 평균, 연령대별 업종별 이용 평균, 그리고 연령대별 회원 등급 비율을 포함하고 있습니다. 이를 통해 소비자들의 연령대별 카드 사용 트렌드를 파악하고, 다양한 업종에서의 소비 경향과 회원 등급에 따른 카드 사용 특성을 분석하였습니다.

### **분석 목표**:
1. 연령대별 평균 이용금액을 도출하여 소비 패턴을 이해.

2. 업종별로 연령대별 이용금액 평균을 비교하여 각 연령대의 선호 업종 파악.
3. 연령대별로 회원 등급 비율을 분석하여 고객층의 특성 및 트렌드 분석.

### **분석 방법**:
- 우리카드 거래 데이터를 기반으로 연령대별, 업종별, 회원 등급별로 데이터를 그룹화하고, 각 그룹의 평균값을 계산하였습니다.

- 이후, 분석 결과를 시각화하여, 각 연령대별 소비 경향과 업종별 선호도를 직관적으로 보여주기 위해 다양한 차트를 사용하였습니다.

<br>

---

<br>

## 🔧 기술 스택

| **역할**            | **종류**                                                                                                              |
|----------------------|-----------------------------------------------------------------------------------------------------------------------|
| 🤝 협업 도구         | ![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white) <br> ![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white) |
| 💬 커뮤니케이션 도구 | ![Notion](https://img.shields.io/badge/Notion-%23000000.svg?style=for-the-badge&logo=notion&logoColor=white)<br> ![Discord](https://img.shields.io/badge/Discord-%235865F2.svg?style=for-the-badge&logo=discord&logoColor=white)|
| 🛠️ 개발 및 관리 도구 | ![MobaXterm](https://img.shields.io/badge/mobaxterm-2C2E34.svg?style=for-the-badge&logo=mobaxterm&logoColor=white) <br> ![Elasticsearch](https://img.shields.io/badge/elasticsearch-%230377CC.svg?style=for-the-badge&logo=elasticsearch&logoColor=white)|
| :eyes: 시각화 도구 | ![Kibana](https://img.shields.io/badge/Kibana-E8478B.svg?&style=for-the-badge&logo=Kibana&logoColor=white)|

<br>

---

<br>

## ⚙️ ELK 설치 과정 및 설정
> 링크를 클릭하시면, 명령어 정리된 Markdown 파일을 확인하실 수 있어요😊
#### 1️⃣ [Ubuntu에 기존에 설치했던 ElasticSearch 8 버전 삭제](Uninstall-ElasticSearch-8-from-Ubuntu.md)
#### 2️⃣ [Ubuntu에 ELK 스택 (Elasticsearch, Logstash, Kibana) 7.17.27 버전 설치](Install-ELK-7.17.27-on-Ubuntu.md)
