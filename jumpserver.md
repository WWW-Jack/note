## 使用docker安裝jumpserver
```
curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

chmod +x /usr/local/bin/docker-compose

git clone --depth=1 https://github.com/wojiushixiaobai/Dockerfile.git

cd Dockerfile

cp config_example.conf .env

gedit .env    # ip：172.20.0.0/16

docker-compose -f docker-compose-redis.yml -f docker-compose-mariadb.yml -f docker-compose.yml up    # 讓docker之間相互通信
```