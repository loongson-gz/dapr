# dapr 构建

系统环境: loongnix server 1.7 


## 安装基础库
```
yum install epel-release

yum group install "Development Tools"

yum install golang			//编译 dapr-1.0.0 需要 golang-1.14，而系统默认安装的是 go-1.13，所以需要手动升go 版本

yum install docker-ce

```

## 从龙芯私有仓库拉取最新的alpine:latest 镜像
```
docker pull docker.loongnix.org:8080/cncf-containeros/alpine:3.11.7
docker tag docker.loongnix.org:8080/cncf-containeros/alpine:3.11.7 alpine:latest
```

## 设置 Go Proxy
当 Go 下载第三方包时，由于网络环境的不同，可能会出现失败的情况。可以用设置环境变量的方式临时设置 Go Proxy ：

`export GOPROXY="https://goproxy.io"`

## 编译
`make -f .loongson/Makefile`

## 编译成功后，可查看构建好的镜像
`docker image ls`