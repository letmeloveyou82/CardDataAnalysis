# 1️⃣ Ubuntu에 기존에 설치했던 ElasticSearch 8 버전 삭제

---

### **1. Elasticsearch 패키지 삭제**

```bash
sudo apt remove --purge elasticsearch -y
```

---

### **2. Elasticsearch 관련 디렉토리 삭제**

Elasticsearch 설정 파일, 데이터, 로그를 완전히 제거하려면 관련 디렉토리를 삭제하세요.

```bash
sudo rm -rf /etc/elasticsearch /var/lib/elasticsearch /var/log/elasticsearch
```

---

### **3. 자동으로 설치된 패키지 제거 (선택 사항)**

불필요한 패키지를 정리하려면:

```bash
sudo apt autoremove -y
```

---

### **4. 확인**

삭제되었는지 확인하려면:

```bash
dpkg -l | grep elasticsearch
```

- 결과가 없다면 Elasticsearch가 정상적으로 삭제된 것입니다.

---

GPG 키도 함께 삭제하려면 다음 단계를 따르세요.

---

### **1. Elasticsearch GPG 키 확인**

현재 등록된 GPG 키 목록에서 Elasticsearch 관련 키를 확인하세요.

```bash
apt-key list
```

Elasticsearch GPG 키는 일반적으로 다음과 같이 표시됩니다:

```
pub   rsa4096 2015-11-02 [SC]
      D27D666CD88E42B4
uid           [ unknown] Elasticsearch (Elasticsearch Signing Key) <info@elastic.co>
```

---

### **2. Elasticsearch GPG 키 삭제**

GPG 키 ID를 확인한 후 삭제합니다. 위 예시에서 키 ID는 `D27D666CD88E42B4`입니다.

```bash
sudo apt-key del D88E42B4
```

---

### **3. APT 소스 리스트에서 Elastic 저장소 제거**

Elastic 저장소를 더 이상 사용하지 않을 경우, APT 소스 리스트에서 제거하세요.

```bash
sudo rm /etc/apt/sources.list.d/elastic-*.list
```

---

### **4. APT 캐시 업데이트**

저장소 및 키 삭제 후 패키지 목록을 업데이트하세요.

```bash
sudo apt update
```

---

### **5. 확인**

키와 저장소가 삭제되었는지 다시 확인:

```bash
apt-key list
ls /etc/apt/sources.list.d/
```

---