# kubernetes一键部署

`注意：需要自己准备mysql资源`

## 安装方法

```
/bin/bash webhook-create-signed-cert.sh
/bin/bash  webhook-patch-ca-bundle.sh
kubectl apply -f . 
```

## 标准环境变量

变量名 | 描述 | 默认值
------------ | ------------- | -------------
$ALPINE_REPO |alpine库地址| mirrors.aliyun.com
$TIME_ZONE |所在时区| Asia/Shanghai

## 特殊环境变量

### king-inspect 

变量名 | 描述 | 默认值
------------ | ------------- | -------------
$DB_URL | MYSQL数据库地址 | 'user:password@tcp(192.168.10.100:3306)/kingfisher'
$LISTEN | 监听地址 | 0.0.0.0
$PORT | 监听端口 | 8080
$RABBITMQ_URL | rabbitmq地址 | 'amqp://user:password@king-rabbitmq:5672/'

### king-k8s
变量名 | 描述 | 默认值
------------ | ------------- | -------------
$DB_URL | MYSQL数据库地址 | 'user:password@tcp(192.168.10.100:3306)/kingfisher'
$LISTEN | 监听地址 | 0.0.0.0
$PORT | http监听端口 | 8080
$RPCPORT | GRPC监听端口 | 50000
$RABBITMQ_URL | rabbitmq地址 | 'amqp://user:password@king-rabbitmq:5672/'

### king-kubectl 
变量名 | 描述 | 默认值
------------ | ------------- | -------------
$KUBECTL_URL | kubectl命令下载地址 | https://storage.googleapis.com/kubernetes-release/release/$KUBECTL_VERSION/bin/linux/amd64/kubectl

### king-frontend 

变量名 | 描述 | 默认值
------------ | ------------- | -------------
$DOMAIN | kingfisher平台UI域名 | "kingfisher.com"

```
注意：此处要与frontend的ingress配置域名相同，请修改king-frontend.yaml中的域名字段
```

### king-istio

变量名 | 描述 | 默认值
------------ | ------------- | -------------
$DB_URL || 'user:password@tcp(192.168.10.100:3306)/kingfisher'
$LISTEN || 0.0.0.0
$PORT || 8080
$RABBITMQ_URL || 'amqp://user:password@king-rabbitmq:5672/'

### king-kf

变量名 | 描述 | 默认值
------------ | ------------- | -------------
$DB_URL | MYSQL数据库地址 | 'user:password@tcp(192.168.10.100:3306)/kingfisher'
$LISTEN | 监听地址 | 0.0.0.0
$PORT | 监听端口 | 8080
$RABBITMQ_URL | rabbitmq地址 | 'amqp://user:password@king-rabbitmq:5672/'

### king-preset 

无

