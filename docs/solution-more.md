# More

Each of the following solutions has been proved to be effective and we hope it can give you help.

## Send & Receive Messages

RocketMQ Name Server，Broker after service startup, how to verify whether messages can be sent and received normally? Before sending/receiving messages, we need to tell client the location of the name server. It provides a variety of ways to achieve this. For simplicity, we use the environment variable `NAMESRV_ADDR`, the implementation process is as follows:
```
 > export NAMESRV_ADDR=localhost:9876
 > sh bin/tools.sh org.apache.rocketmq.example.quickstart.Producer
 SendResult [sendStatus=SEND_OK, msgId= ...

 > sh bin/tools.sh org.apache.rocketmq.example.quickstart.Consumer
 ConsumeMessageThread_%d Receive New Messages: [MessageExt...
```
>After completion, the rocketmq console ng interface changes:
 ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/rocketmq/rocketmq-send-websoft9.png)