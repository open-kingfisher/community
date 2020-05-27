# kubernetes一键部署

`注意：需要自己准备mysql资源`

## 安装方法

/bin/bash webhook-create-signed-cert.sh
/bin/bash  webhook-patch-ca-bundle.sh
kubectl apply -f . 

## 标准环境变量

[ "$ALPINE_REPO" ] || ALPINE_REPO="mirrors.aliyun.com"
[ "$TIME_ZONE" ] || TIME_ZONE="Asia/Shanghai"

## 特殊环境变量

### king-inspect 

[ "$DB_URL" ] || DB_URL='user:password@tcp(192.168.10.100:3306)/kingfisher'
[ "$LISTEN" ] || LISTEN=0.0.0.0
[ "$PORT" ] || PORT=8080
[ "$RABBITMQ_URL" ] || RABBITMQ_URL='amqp://user:password@king-rabbitmq:5672/'

### king-k8s

[ "$DB_URL" ] || DB_URL='user:password@tcp(192.168.10.100:3306)/kingfisher'
[ "$LISTEN" ] || LISTEN=0.0.0.0
[ "$PORT" ] || PORT=8080
[ "$RPCPORT" ] || RPCPORT=50000
[ "$RABBITMQ_URL" ] || RABBITMQ_URL='amqp://user:password@king-rabbitmq:5672/'

### king-kubectl 

[ "$KUBECTL_URL" ] || https://storage.googleapis.com/kubernetes-release/release/$KUBECTL_VERSION/bin/linux/amd64/kubectl

### king-frontend 

[ "$DOMAIN" ] || DOMAIN="kingfisher.com"

### king-istio

[ "$DB_URL" ] || DB_URL='user:password@tcp(192.168.10.100:3306)/kingfisher'
[ "$LISTEN" ] || LISTEN=0.0.0.0
[ "$PORT" ] || PORT=8080
[ "$RABBITMQ_URL" ] || RABBITMQ_URL='amqp://user:password@king-rabbitmq:5672/'

### king-kf

[ "$DB_URL" ] || DB_URL='user:password@tcp(192.168.10.100:3306)/kingfisher'
[ "$LISTEN" ] || LISTEN=0.0.0.0
[ "$PORT" ] || PORT=8080
[ "$RABBITMQ_URL" ] || RABBITMQ_URL='amqp://user:password@king-rabbitmq:5672/'

### king-preset 

无

