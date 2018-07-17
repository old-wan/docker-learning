# elasticsearch单节点

### 部署命令
```
docker stop single-elasticsearch
docker rm single-elasticsearch
docker network rm elasticsearch-network
docker network create --subnet=10.101.57.0/24 elasticsearch-network
docker run -itd --restart always --net elasticsearch-network --ip 10.101.57.101 -e ES_JAVA_OPTS="-Xms256m -Xmx256m" --name single-elasticsearch elasticsearch:5.6.10-alpine
# 访问URL
curl http://10.101.57.101:9200
```