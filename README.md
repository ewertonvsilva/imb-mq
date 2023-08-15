# imb-mq
arm64 build on a intel:

```
git clone https://github.com/ibm-messaging/mq-container.git`
cd mq-container
ARCH=arm64 make build-devserver
```
import image:

```
docker load -i ibm-mq-arm64.tar
```

to test image:
```
docker run \     
  --env LICENSE=accept \
  --env MQ_QMGR_NAME=QM1 \
  --publish 1414:1414 \
  --publish 9443:9443 \
  --detach \
  --platform linux/arm64 \
  ibm-mqadvanced-server-dev:9.3.3.0-arm64
```
