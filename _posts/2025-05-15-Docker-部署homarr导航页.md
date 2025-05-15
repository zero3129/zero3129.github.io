# 部署homarr导航页

2025年5月15日17点11分

## 1 创建挂载目录

- **创建挂载目录**

```
mkdir -p /data/homarr/configs && mkdir -p /data/homarr/icons
```

## 2 创建homarr容器

> 使用docker run快速创建homarr容器

```
docker run \  
--name homarr \
--restart unless-stopped \
-p 7666:7575 \
-v /data/homarr/configs:/app/data/configs \
-v /data/homarr/icons:/app/public/icons \
-v /var/run/docker.sock:/var/run/docker.sock \
-d ghcr.io/ajnart/homarr:latest
```

## 3 检查homarr容器状态

> 检查homarr容器运行状态

```
[root@jeven homarr]# docker ps CONTAINER ID   IMAGE                          COMMAND                  CREATED          STATUS          PORTS                                       NAMES f0dfb29fd905   ghcr.io/ajnart/homarr:latest   "docker-entrypoint.s…"   20 seconds ago   Up 19 seconds   0.0.0.0:7666->7575/tcp, :::7666->7575/tcp   homarr 
```

## 4 检查容器运行日志

> 检查容器运行日志

```
[root@jeven homarr]# docker logs homarr Listening on port 7575 url: http://f0dfb29fd905:7575 
```

## 六、访问homarr首页

> 访问地址：http://172.245.240.190:7666 将IP地址改为自己服务器的IP地址。

[![Docker实践：使用Docker部署homarr个人导航页](https://am.zdmimg.com/202503/06/67c9ba378ebf32071.png_e1080.jpg)](https://post.smzdm.com/p/anm455q7/pic_3/)