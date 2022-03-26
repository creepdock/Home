# CreepDock : Some homemade docker Images

## Uptime-Kuma

<img src="https://raw.githubusercontent.com/louislam/uptime-kuma/master/public/icon.svg" style="zoom:25%;" />

This image is automatically updated everytime there is a new commit on the main branch of [Uptime-Kuma's repo](https://github.com/louislam/uptime-kuma)
Also, it is compatible **armhf,arm64** and **amd64** !

### **docker-compose.yml :**

```yaml
version: '3'
services:
    uptimekuma:
        restart: unless-stopped
        container_name: uptimekuma
        image: ghcr.io/creepdock/latestkuma
        ports:
            - 3001:3001
        volumes:
            - ./data/:/app/data/
```

### **docker run :**

```bash
docker run --detached -v /data/:/app/data/ -p 3001:3001 ghcr.io/creepdock/latestkuma:latest
```


----
## ApIndex

<img src="https://camo.githubusercontent.com/696065fcbb8dae237206d243c9f75c8f617cefca82a487da414df7a154a30f70/68747470733a2f2f692e696d6775722e636f6d2f6d3861586647752e706e67" style="zoom: 67%;" />

This image is not auto-updated, as there are no more commit on the [main repository](https://github.com/jayanta525/apindex-v2).

### **docker run :**

```bash
docker run -v /localfolder-to-index/:/to-index/ ghcr.io/creepdock/apindex:latest
```

----
## AreWeDown

![](https://raw.githubusercontent.com/MichelBaie/arewedown/master/docassets/image-20211218234259624.png)

This image is not auto-updated, as there are no more commit on the [main repository](https://github.com/shukriadams/arewedown).

**Config file is needed ! Please, git clone the repo or add manually** `settings.yml`.

```bash
git clone https://github.com/creepdock/arewedown.git
```

### **docker-compose.yml :**

```yaml
version: '3'
services:
    arewedown:
        restart: unless-stopped
        container_name: arewedown
        image: ghcr.io/creepdock/arewedown:latest
        ports:
            - 3000:3000
        volumes:
            - ./config/:/app/config/
            - ./logs/:/app/logs/
```

### **docker run :**

```bash
docker run --detached -v /config/:/app/config/ -v /logs/:/app/logs/ -p 3000:3000 ghcr.io/creepdock/arewedown:latest
```
