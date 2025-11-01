# redis-cluster
rediscluster

```
外网             内网
43.160.251.69   10.3.4.6
43.163.101.236  10.3.0.2
43.160.254.183  10.3.0.10
43.160.197.10   10.3.0.14
43.160.192.124  10.3.0.7
43.160.254.91   10.3.0.3
```

服务器动命令模版
```
docker run -d \
  --name redis-node-$NODE_ID \
  -p 7000:7000 \
  -p 17000:17000 \
  -v /data/redis/node-$NODE_ID:/data \
  redis:7-alpine \
  redis-server \
    --port 7000 \
    --bind 0.0.0.0 \
    --cluster-enabled yes \
    --cluster-node-timeout 5000 \
    --appendonly yes \
    --protected-mode no \
    --cluster-announce-ip $OUTER_IP \
    --cluster-announce-port 7000 \
    --cluster-announce-bus-port 17000 \
    --requirepass MyStrongPassword123 \
    --masterauth MyStrongPassword123
```
第一台
```

```
第二台
```
```
第三台
```
```
第四台
```
```
第五台
```
```
第六台
```
```