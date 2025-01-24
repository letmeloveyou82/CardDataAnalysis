# 💳 CardDataAnalysis
> ElasticSearch, Kibana를 활용한 카드사의 실데이터 시각화

## 🤝 팀원
|<img src="https://avatars.githubusercontent.com/u/98368034?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/49242646?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/103468518?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/103871252?v=4" width="150" height="150"/>|
|:-:|:-:|:-:|:-:|
|장수현<br/>[@Aunsxm](https://github.com/Aunsxm)|최윤정<br/>[@letmeloveyou82](https://github.com/letmeloveyou82)|김창성<br/>[@kcs19](https://github.com/kcs19)|김우현<br/>[@woody6624](https://github.com/woody6624)|

<br>

---

<br>

## 📒 프로젝트 개요
본 프로젝트는 카드사의 실제 소비 데이터를 활용하여, 연령대별 소비 패턴과 회원 등급 분포를 분석하고 시각화한 것입니다. 주요 분석 항목으로는 연령대별 총 이용금액 평균, 연령대별 업종별 이용 평균, 그리고 연령대별 회원 등급 비율을 포함하고 있습니다. 이를 통해 소비자들의 연령대별 카드 사용 트렌드를 파악하고, 다양한 업종에서의 소비 경향과 회원 등급에 따른 카드 사용 특성을 분석하였습니다.

### **분석 목표**:
1. 연령대별 평균 이용금액을 도출하여 소비 패턴을 이해.

2. 업종별로 연령대별 이용금액 평균을 비교하여 각 연령대의 선호 업종 파악.
3. 연령대별로 회원 등급 비율을 분석하여 고객층의 특성 및 트렌드 분석.

### **분석 방법**:
- 카드 거래 데이터를 기반으로 연령대별, 업종별, 회원 등급별로 데이터를 그룹화하고, 각 그룹의 평균값을 계산하였습니다.

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
#### 1️⃣ [Ubuntu에 기존에 설치했던 ElasticSearch 8 버전 삭제](1.%20Uninstall-ElasticSearch-8-from-Ubuntu.md)
#### 2️⃣ [Ubuntu에 ELK 스택 (Elasticsearch, Logstash, Kibana) 7.17.27 버전 설치](2.%20Install-ELK-7.17.27-on-Ubuntu.md)
#### 3️⃣ [Ubuntu에 설치한 Elasticsearch, Kibana를 Windows로 접속하기 위한 수정사항](3.%20Configure-Elasticsearch-Kibana-Access-from-Windows.md)

## 🌠트러블 슈팅
### 문제 발생 
elasticsearch.yml 파일에서 network.host의 값을 0.0.0.0으로 수정하고 elasticsearch 실행시 에러 발생
![Image](https://github.com/user-attachments/assets/6d2b5c7d-a43d-4dd8-b1db-f71ab0e0ce9a)

### 문제 원인 분석
sudo journalctl -xeu elasticsearch.service 명령어를 통해서 로그 분석
<br>

**에러메시지** 
``` 
Jan 24 16:04:21 myserver1 systemd-entrypoint[7102]: Jan 24, 2025 7:04:21 AM sun.util.locale.provider.LocaleProviderAdapter <clinit>
Jan 24 16:04:21 myserver1 systemd-entrypoint[7102]: WARNING: COMPAT locale provider will be removed in a future release
Jan 24 16:04:32 myserver1 systemd-entrypoint[7102]: ERROR: [1] bootstrap checks failed. You must address the points described in the following [1] lines befo>
Jan 24 16:04:32 myserver1 systemd-entrypoint[7102]: bootstrap check failure [1] of [1]: the default discovery settings are unsuitable for production use; at >
Jan 24 16:04:32 myserver1 systemd-entrypoint[7102]: ERROR: Elasticsearch did not exit normally - check the logs at /var/log/elasticsearch/elasticsearch.log
Jan 24 16:04:32 myserver1 systemd[1]: elasticsearch.service: Main process exited, code=exited, status=78/CONFIG
```
<br> 


### 문제 해결 방법
테스트 환경에서는 discovery.type을 single-node로 설정하여 클러스터 설정을 간소화 -> elasticsearch.yml에 해당 설정 추가
<br>
![Image](https://github.com/user-attachments/assets/be709eb0-c49d-450a-8727-28372d90c4c5)

### 해결 결과
![Image](https://github.com/user-attachments/assets/df315d16-7b8f-4f8a-b58b-921f3a00d444)
