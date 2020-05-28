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
$MYSQL_USER | MYSQL用户名 | MYSQL_USER='root'
$MYSQL_PASSWORD | MYSQL密码| MYSQL_PASSWORD='kingfisher'
$MYSQL_HOST | MYSQL主机 | MYSQL_HOST='mysql'
$MYSQL_PORT | MYSQL端口 | PORT="3306"
$MYSQL_DB | 数据库名 | DB="kingfisher"
$DB_URL | 完整MYSQL请求地址（注：选填以该参数为最高优先级） | DB_URL="${MYSQL_USER}:${MYSQL_PASSWORD}@tcp(${MYSQL_HOST}:${MYSQL_PORT})/${MYSQL_DB}"
$MQ_USER | RabbiMQ用户名 | MQ_USER=kingfisher
$MQ_PASSWORD | RabbiMQ密码 | MQ_PASSWORD=kingfisher
$MQ_HOST | RabbiMQ主机 | MQ_HOST=king-rabbitmq
$MQ_PORT | RabbiMQ端口 | MQ_PORT=5672
$RABBITMQ_URL | RabbiMQ请求地址（注：选填以该参数为最高优先级） | RABBITMQ_URL="amqp://${MQ_USER}:${MQ_PASSWORD}@${MQ_HOST}:${MQ_PORT}/"
$LISTEN | 监听地址 | 0.0.0.0
$PORT | 监听端口 | 8080

### king-k8s
变量名 | 描述 | 默认值
------------ | ------------- | -------------
$MYSQL_USER | MYSQL用户名 | MYSQL_USER='root'
$MYSQL_PASSWORD | MYSQL密码| MYSQL_PASSWORD='kingfisher'
$MYSQL_HOST | MYSQL主机 | MYSQL_HOST='mysql'
$MYSQL_PORT | MYSQL端口 | PORT="3306"
$MYSQL_DB | 数据库名 | DB="kingfisher"
$DB_URL | 完整MYSQL请求地址（注：选填以该参数为最高优先级） | DB_URL="${MYSQL_USER}:${MYSQL_PASSWORD}@tcp(${MYSQL_HOST}:${MYSQL_PORT})/
${MYSQL_DB}"
$MQ_USER | RabbiMQ用户名 | MQ_USER=kingfisher
$MQ_PASSWORD | RabbiMQ密码 | MQ_PASSWORD=kingfisher
$MQ_HOST | RabbiMQ主机 | MQ_HOST=king-rabbitmq
$MQ_PORT | RabbiMQ端口 | MQ_PORT=5672
$RABBITMQ_URL | RabbiMQ请求地址（注：选填以该参数为最高优先级） | RABBITMQ_URL="amqp://${MQ_USER}:${MQ_PASSWORD}@${MQ_HOST}:${MQ_PORT}/
"
$LISTEN | 监听地址 | 0.0.0.0
$PORT | http监听端口 | 8080
$RPCPORT | GRPC监听端口 | 50000

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
$MYSQL_USER | MYSQL用户名 | MYSQL_USER='root'
$MYSQL_PASSWORD | MYSQL密码| MYSQL_PASSWORD='kingfisher'
$MYSQL_HOST | MYSQL主机 | MYSQL_HOST='mysql'
$MYSQL_PORT | MYSQL端口 | PORT="3306"
$MYSQL_DB | 数据库名 | DB="kingfisher"
$DB_URL | 完整MYSQL请求地址（注：选填以该参数为最高优先级） | DB_URL="${MYSQL_USER}:${MYSQL_PASSWORD}@tcp(${MYSQL_HOST}:${MYSQL_PORT})/
${MYSQL_DB}"
$MQ_USER | RabbiMQ用户名 | MQ_USER=kingfisher
$MQ_PASSWORD | RabbiMQ密码 | MQ_PASSWORD=kingfisher
$MQ_HOST | RabbiMQ主机 | MQ_HOST=king-rabbitmq
$MQ_PORT | RabbiMQ端口 | MQ_PORT=5672
$RABBITMQ_URL | RabbiMQ请求地址（注：选填以该参数为最高优先级） | RABBITMQ_URL="amqp://${MQ_USER}:${MQ_PASSWORD}@${MQ_HOST}:${MQ_PORT}/
"
$LISTEN | 监听地址 | 0.0.0.0
$PORT | 监听端口 | 8080

### king-kf

变量名 | 描述 | 默认值
------------ | ------------- | -------------
$MYSQL_USER | MYSQL用户名 | MYSQL_USER='root'
$MYSQL_PASSWORD | MYSQL密码| MYSQL_PASSWORD='kingfisher'
$MYSQL_HOST | MYSQL主机 | MYSQL_HOST='mysql'
$MYSQL_PORT | MYSQL端口 | PORT="3306"
$MYSQL_DB | 数据库名 | DB="kingfisher"
$DB_URL | 完整MYSQL请求地址（注：选填以该参数为最高优先级） | DB_URL="${MYSQL_USER}:${MYSQL_PASSWORD}@tcp(${MYSQL_HOST}:${MYSQL_PORT})/
${MYSQL_DB}"
$MQ_USER | RabbiMQ用户名 | MQ_USER=kingfisher
$MQ_PASSWORD | RabbiMQ密码 | MQ_PASSWORD=kingfisher
$MQ_HOST | RabbiMQ主机 | MQ_HOST=king-rabbitmq
$MQ_PORT | RabbiMQ端口 | MQ_PORT=5672
$RABBITMQ_URL | RabbiMQ请求地址（注：选填以该参数为最高优先级） | RABBITMQ_URL="amqp://${MQ_USER}:${MQ_PASSWORD}@${MQ_HOST}:${MQ_PORT}/
"
$LISTEN | 监听地址 | 0.0.0.0
$PORT | 监听端口 | 8080

### king-preset 

无

