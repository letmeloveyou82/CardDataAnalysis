# 2️⃣ Ubuntu에 ELK 스택 (Elasticsearch, Logstash, Kibana) 7.17.27 버전 설치

## 1. **Elasticsearch 설치**

- **Elasticsearch 7.17.27 다운로드**:
  공식 Elastic 웹사이트에서 `.deb` 패키지를 다운로드합니다.
  ```bash
  wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.17.27-amd64.deb
  ```

- **다운로드한 파일 설치**:
  `dpkg` 명령어를 사용하여 `.deb` 패키지를 설치합니다.
  ```bash
  sudo dpkg -i elasticsearch-7.17.27-amd64.deb
  ```

- **Elasticsearch 서비스 활성화 및 시작**:
  1. 서비스 활성화:
     ```bash
     sudo systemctl enable elasticsearch
     ```
  2. 서비스 시작:
     ```bash
     sudo systemctl start elasticsearch
     ```
  3. 상태 확인:
     ```bash
     sudo systemctl status elasticsearch
     ```

- **Elasticsearch 동작 확인**:
  ```bash
  curl -X GET "localhost:9200"
  ```

## 2. **Logstash 설치**

- **Logstash 7.17.27 다운로드 및 설치**:
  ```bash
  wget https://artifacts.elastic.co/downloads/logstash/logstash-7.17.27-amd64.deb
  sudo dpkg -i logstash-7.17.27-amd64.deb
  ```

- **Logstash 서비스 활성화 및 시작**:
  1. 서비스 활성화:
     ```bash
     sudo systemctl enable Logstash
     ```
  2. 서비스 시작:
     ```bash
     sudo systemctl start Logstash
     ```
  3. 상태 확인:
     ```bash
     sudo systemctl status Logstash
     ```

## 3. **Kibana 설치**

- **Kibana 7.17.27 다운로드 및 설치**:
  ```bash
  wget https://artifacts.elastic.co/downloads/kibana/kibana-7.17.27-amd64.deb
  sudo dpkg -i kibana-7.17.27-amd64.deb
  ```

- **kibana 서비스 활성화 및 시작**:
  1. 서비스 활성화:
     ```bash
     sudo systemctl enable kibana
     ```
  2. 서비스 시작:
     ```bash
     sudo systemctl start kibana
     ```
  3. 상태 확인:
     ```bash
     sudo systemctl status kibana
     ```