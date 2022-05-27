# [上游仓库](https://github.com/sirodeneko/genshin-sign)

# 使用方法
## 方案一（推荐，常驻内存）
```
docker run \
--network bridge \
--env CRON_SIGNIN='30 9 * * *' \
--env TZ=Asia/Shanghai \
--env COOKIE='your cookie str' \
vincent5/genshin-sign:latest
```

## 方案二（不常驻内存，更节省系统资源）
```
# 单次运行
docker run \
--network bridge \
--name genshin-sign \
--env TZ=Asia/Shanghai \
--env COOKIE='your cookie str' \
vincent5/genshin-sign:latest  python3 ./genshin.py

# 每日9:30签到
echo "30 9 * * * root docker restart genshin-sign" >> /etc/crontab

# 每周三自动更新容器
echo "30 9 * * 3 root docker run --rm  -v /var/run/docker.sock:/var/run/docker.sock containrrr/watchtower --run-once  -c genshin-sign" >> /etc/crontab
```