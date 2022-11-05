# docker-images

Docker 镜像库，基于官方镜像进行调整，以满足特定需求，方便日常开发、测试等使用。

## test

基于 [busybox](https://hub.docker.com/_/busybox)镜像，用于测试、验证镜像的制作。

## go-builder

基于 [golang](https://hub.docker.com/_/golang) 镜像构建，可作为 golang 的基础镜像使用。

镜像地址：`xcbeyond/go-build:1.16`

### 特性

* 添加了 `GOPROXY` 国内代理（https://goproxy.cn），可加速 go 依赖包的下载。

### 使用说明

直接在 go 应用的 Dockerfile 文件第一行添加 `FROM xcbeyond/go-build:1.16` 作为基础镜像。

## gitbook-builder

基于 node:6.14 镜像构建，并安装 gitbook CLI，满足 gitbook 的编译环境。

相关版本情况如下：

```sh
$ npm -v 
3.10.10
$ gitbook -V
CLI version: 2.3.2
GitBook version: 3.2.3
```

镜像地址：`xcbeyond/gitbook-builder:latest`

## prometheus

基于 `prom/prometheus` 镜像构建。

## prometheus-operator

基于 `quay.io/coreos/prometheus-operator` 镜像构建。

## kube-apiserver

基于 `k8s.gcr.io/kube-apiserver` 镜像构建。

## cloudnative-terminal

云原生 terminal 容器，包含常用命令工具：kubectl、istioctl、helm 等。
