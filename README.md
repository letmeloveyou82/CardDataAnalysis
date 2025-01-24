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

## 📌 ElasticSearch 7.17 버전 선정 이유

### **1. 대규모 데이터 세트 빠른 검색 용이**

- Elasticsearch 6.x에서 사용되던 `Type` 개념이 `Index`로 변경되었습니다.
- `Index`는 JSON 형태로 여러 `field`와 `value`를 가질 수 있는 구조로, 비정규화된 데이터를 구조적으로 저장할 수 있다는 장점이 있습니다
- 인덱스는 단어 및 숫자의 위치 데이터를 **토큰화**하여 문서를 식별하는 역 인덱스 작업을 통해 빠른 범위 검색과 유사 항목 쿼리를 가능하게 합니다.
- 이를 통해 대규모의 데이터 세트에서 빠른 범위 검색과 유사 항목 쿼리를 허용하여 데이터 분석을 빠르게 수행할 수 있습니다.

<br>

### **2. 가장 최근의 안정된 버전**

- 공식 ElasticSearch 도커 이미지에서 지속적으로 관리되는 버전입니다.
- 가장 최근의 버그를 수정한 가장 최신 버전입니다. <br>

  <img src="https://github.com/user-attachments/assets/8a0fd034-7b7a-4acb-8fe7-50c42e65291b" style="border: 3px solid black; padding: 5px;">

  
<br>

### **3. ubuntu22.04버전 지원 (2024-08-08 기준)**

- 이전 Elasticsearch 버전은 Ubuntu 22.04에서 안정적으로 지원되지 않지만, **7.17 버전**에서는 지원됩니다.
    
    ※ Ubuntu 24.04 버전의 호환 여부는 명시되지 않음
    

    |  | Ubuntu20.04 | Ubuntu22.04 |
    | --- | --- | --- |
    | Elasticsearch 7.11.x | ✔ |  |
    | Elasticsearch 7.17.x | ✔ | ✔ |

<br>

### 참고자료

- https://www.elastic.co/kr/blog/what-is-an-elasticsearch-index
- https://hub.docker.com/layers/library/elasticsearch/7.17.27/images/sha256-07e9262b856006959e384de7ca9587bc5c6da024ca7042216a9ea26efe4c69c1
- https://www.elastic.co/kr/support/matrix/




<br>

---

<br>

## ⚙️ ELK 설치 과정 및 설정
> 링크를 클릭하시면, 명령어 정리된 Markdown 파일을 확인하실 수 있어요😊
#### 1️⃣ [Ubuntu에 기존에 설치했던 ElasticSearch 8 버전 삭제](1.%20Uninstall-ElasticSearch-8-from-Ubuntu.md)
#### 2️⃣ [Ubuntu에 ELK 스택 (Elasticsearch, Logstash, Kibana) 7.17.27 버전 설치](2.%20Install-ELK-7.17.27-on-Ubuntu.md)
#### 3️⃣ [Ubuntu에 설치한 Elasticsearch, Kibana를 Windows로 접속하기 위한 수정사항](3.%20Configure-Elasticsearch-Kibana-Access-from-Windows.md)

<br>

---

<br>

## 📊 Kibana 시각화
<table>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/21707c69-f41b-4ae1-b1d4-df3273348b44" alt="Image"></td>
  </tr>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/e37266b0-f140-40ad-bbe5-b773441f3a8c" alt="Image"></td>
  </tr>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/7e4b0890-6abe-4918-bf33-78a03e39cafc" alt="Image"></td>
  </tr>
</table>

<br>

---

<br>

## 🌠 트러블 슈팅
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

<br>

---

<br>

## 📝 회고

### 👍 배운 점

  - 이번 프로젝트를 통해 데이터 시각화의 중요성과 소비 패턴 분석의 실무적 활용 가능성을 깊이 이해할 수 있었습니다. 특히, 연령대별 소비 트렌드와 회원 등급 분포를 시각적으로 표현하며, 데이터를 단순히 수치로 전달하는 것을 넘어 인사이트를 효과적으로 전달하는 방법에 대해 고민할 수 있었습니다.
  - 분석 과정에서 막대그래프, 파이차트, 히트맵 등 다양한 시각화 도구를 활용하며, 시각적 표현이 분석 결과를 이해하는 데 얼마나 중요한 역할을 하는지 체감했습니다. 이를 통해서 데이터를 더 직관적으로 전달하기 위해 어떤 시각화 방식이 적합한지를 고민하며, 데이터의 가치를 극대화할 수 있었습니다.

### 🥲 아쉬운 점 

  -  데이터의 제한으로 인해 특정 연령대나 업종별 소비 경향에 대해 심화 분석을 하지 못한 점이 아쉬웠습니다. 이를 해결하기 위해서는 외부 데이터와의 결합이나 추가적인 데이터 수집이 필요하다는 점을 느꼈습니다.
  - 한 대의 노트북에서 Kibana(5601 포트)를 구동하는 상황에서 Nginx를 이용하여 리버스 프록시를 설정해 보안을 강화하여 모든 유저(0.0.0.0)가 아닌 허용된  특정IP에서만 Kibana에 접속할 수 있도록 제한하려 했으나 네트워크 계층에 대한 이해도 부족으로 인하여 실패를 하였습니다. 다음에 하게 될 프로젝트에서는 네트워크 지식을 더욱 깊게 길러서 네트워크 계층 문제로 인하여 발생하는 문제를 원활하게 해결할 것입니다.

