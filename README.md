# docker-images

Docker 镜像库，基于官方镜像进行调整，以满足特定需求，方便日常开发、测试等使用。

## test

基于 [busybox](https://hub.docker.com/_/busybox)镜像，用于测试、验证镜像的制作。

## go-builder

基于 [golang](https://hub.docker.com/_/golang) 镜像构建，可作为 golang 的基础镜像使用。

镜像地址：xcbeyond/go-build:1.16

### 特性

* 添加了 `GOPROXY` 国内代理（https://goproxy.cn），可加速 go 依赖包的下载。

### 使用说明

直接在 go 应用的 Dockerfile 文件第一行添加 `FROM xcbeyond/go-build:1.16` 作为基础镜像。

## prometheus

基于 `prom/prometheus` 镜像构建。

## prometheus-operator

基于 `quay.io/coreos/prometheus-operator` 镜像构建。

## kube-apiserver

基于 `k8s.gcr.io/kube-apiserver` 镜像构建。
