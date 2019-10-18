# Serverless Kubernetes

用于创建弹性容器

## 创建 Kubernetes 集群

https://cs4service.console.aliyun.com/#/k8s/cluster/create/serverless

> 注意专有网络访问，需要跟其他服务使用同一交换机

## 创建命名空间

可以选择[配置资源额度](https://help.aliyun.com/document_detail/89241.html)


## 创建无状态应用

https://cs4service.console.aliyun.com/#/k8s/deployment/list

1. 点击「使用镜像创建」
2. 输入应用名称，选择响应的命名空间
3. 镜像源需要跟集群同一个地域才能生效，也可以[手动上传](https://cs4service.console.aliyun.com/#/k8s/repo/list)
4. 在第三步，高级配置处可以开启「容器组水平伸缩」，副本数对应的是自动创建容器服务数量。可以根据触发条件，自动加机器。

## 创建服务

https://cs4service.console.aliyun.com/#/k8s/service/list

通过服务可以访问容器开放的端口，支持内网访问跟外网访问。功能相当于负载均衡。



