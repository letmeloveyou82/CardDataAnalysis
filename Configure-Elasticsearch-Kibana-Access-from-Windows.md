# 3️⃣ Ubuntu에 설치한 Elasticsearch, Kibana를 Windows로 접속하기 위한 수정사항

## 1. **Elasticsearch 설정**

- Elasticsearch가 외부에서 접근할 수 있도록 설정하려면 `elasticsearch.yml` 파일을 수정해야 합니다.

1. **Elasticsearch 설정 파일 수정**
    
    `/etc/elasticsearch/elasticsearch.yml` 파일을 엽니다:
    
    ```bash
    sudo vi /etc/elasticsearch/elasticsearch.yml
    ```
    
2. **클러스터 검색 유형 설정**
    
    단일 노드 환경에서 실행하려면 아래 설정을 추가합니다:
    
    ```yaml
    discovery.type: single-node
    ```
    
3. **네트워크 호스트 설정**
    
    Elasticsearch를 `localhost` 외부에서 접근 가능하도록 설정하려면 아래 항목을 수정하고 주석 해제합니다:
    
    ```yaml
    network.host: 0.0.0.0
    ```
    
4. **파일 저장 및 종료**
    
    변경사항을 저장하고 편집기를 종료합니다 (`vi`의 경우 `:wq!`).
    
5. **Elasticsearch 서비스 재시작**
    
    변경사항을 반영하기 위해 Elasticsearch 서비스를 재시작합니다:
    
    ```bash
    sudo systemctl restart elasticsearch
    ```
    
6. **Elasticsearch 상태 확인**
    
    서비스가 정상적으로 실행 중인지 확인합니다:
    
    ```bash
    sudo systemctl status elasticsearch
    ```

## 2. **Kibana 설정**

- Kibana를 외부에서 접근할 수 있도록 설정하려면 `kibana.yml` 파일을 수정해야 합니다.

1. **Kibana 설정 파일 수정**  

   `/etc/kibana/kibana.yml` 파일을 엽니다:  

   ```bash
   sudo vi /etc/kibana/kibana.yml
   ```

2. **서버 호스트 설정**  

   Kibana를 외부에서 접근 가능하도록 설정하려면 아래 내용을 추가하거나 주석을 해제하고 수정합니다:  

   ```yaml
   server.host: "0.0.0.0"
   ```

3. **파일 저장 및 종료**  

   변경사항을 저장하고 편집기를 종료합니다 (`vi`의 경우 `:wq!`).  

4. **Kibana 서비스 재시작**  

   변경사항을 반영하기 위해 Kibana 서비스를 재시작합니다:  

   ```bash
   sudo systemctl restart kibana
   ```

5. **Kibana 상태 확인**  

   서비스가 정상적으로 실행 중인지 확인합니다:  

   ```bash
   sudo systemctl status kibana
   ```

## 3. Ubuntu <-> Windows 포트 포워딩 설정

![Image](https://github.com/user-attachments/assets/79577a51-28ff-4f9f-bd6f-40edede952e9)

Ubuntu에서 실행 중인 Elasticsearch와 Kibana를 Windows에서 접근할 수 있도록 포트 포워딩을 설정해야 합니다. 기본적으로 Elasticsearch는 9200 포트, Kibana는 5601 포트를 사용합니다.

## 4. **Windows에서 접속**

- 이제 Windows에서 Elasticsearch와 Kibana에 접속할 수 있습니다.
- **Elasticsearch**:
  브라우저에서 아래 주소로 접속하여 Elasticsearch 상태를 확인할 수 있습니다.
  ```
  http://127.0.0.1:9200
  ```
  
- **Kibana**:
  브라우저에서 아래 주소로 접속하여 Kibana UI에 접근할 수 있습니다.
  ```
  http://127.0.0.1:5601
  ```

---


위의 설정들을 통해 Windows에서 Ubuntu에 설치한 Elasticsearch와 Kibana에 원활하게 접속할 수 있습니다.