# mirrors

利用 Github Actions 将外网仓库(如：registry.k8s.io)镜像同步到 [dockerhub](https://hub.docker.com/repositories/wujie1993)，再将镜像拉取至本地

## 快速拉取镜像到本地

```
curl https://raw.githubusercontent.com/wujie1993/mirrors/main/docker-pull -o docker-pull
sh ./docker-pull <镜像>
```

> 可拉取的镜像清单见 [docker-images.list](https://github.com/wujie1993/mirrors/blob/main/docker-images.list) 文件

## 同步 Docker 镜像到 dockerhub

1. 下载脚本

```
git clone git@github.com:wujie1993/mirrors.git
```

2. 编辑 docker-images.list 文件，填入需要同步的镜像列表，每条镜像记录一行

```
vim docker-images.list
```

> 可通过 # 符号注释不需要同步的镜像记录，节约镜像同步时间

3. 提交 docker-images.list 文件更新内容至本仓库

```
git add docker-images.list
git commit -s -m"update docker image list"
git push origin
```

4. 等待 Github Action 运行完毕

## 拉取单个镜像到本地

```
sh ./docker-pull <image>
```

## 批量拉取镜像到本地

```
# 编辑 docker-images.list 移除所要拉取镜像的注释符号
sh ./docker-pull
```
