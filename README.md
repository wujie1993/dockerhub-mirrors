# mirrors

## 同步 Docker 镜像

利用 Github Actions 拉取外网(如：gcr.io)镜像并推送至本地仓库

1. 下载脚本

```
git clone git@github.com:wujie1993/mirrors.git
```

2. 编辑 docker-images.list 文件，填入需要同步的镜像列表，每条镜像记录一行

```
vim docker-images.list
```

> 可通过 # 前缀注释不需要同步的镜像记录，节约镜像同步时间

3. 提交 docker-images.list 文件更新内容至本仓库

```
git add docker-images.list
git commit -s -m"update docker image list"
git push origin
```

4. 等待 Github Action 运行完毕

5. 拉取镜像并推送至本地仓库

```
sh ./docker-sync <127.0.0.1:5000>
```
