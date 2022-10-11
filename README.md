# mirrors

利用 Github Actions 拉取外网镜像并推送至本地仓库

## 拉取镜像

1. 下载拉取脚本

```
wget https://raw.githubusercontent.com/wujie1993/mirrors/main/docker-pull && chmod +x docker-pull
```

2. 拉取镜像

```
./docker-pull gcr.io/ml-pipeline/visualization-server:2.0.0-alpha.3
```

> 如果镜像不存在，可将待同步的镜像列表提交到 docker-images.list 文件中，触发 docker.io 镜像同步

## 推送镜像

1. 下载推送脚本

```
wget https://raw.githubusercontent.com/wujie1993/mirrors/main/docker-push && chmod +x docker-push
```

2. 推送镜像至本地仓库

```
./docker-push <127.0.0.1:5000>
```
