# 原仓库：[Womsxd/AutoMihoyoBBS](https://github.com/Womsxd/AutoMihoyoBBS)

# 使用方法
```
docker run \
--network bridge \
--env CRON_SIGNIN='30 9 * * *' \
--env TZ=Asia/Shanghai \
-v /your/config/path:/app/config \
vincent5/AutoMihoyoBBS:latest
```

# 参数配置

参见https://github.com/Womsxd/AutoMihoyoBBS/tree/master/config

