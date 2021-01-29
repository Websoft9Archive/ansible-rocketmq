# 更多...

下面每一个方案，都经过实践证明行之有效，希望能够对你有帮助

## 发送消息和接受消息

RocketMQ Name Server，Broker 都正常启动后，怎么来验证能否正常发送消息和接受消息呢？在发送/接收消息之前，我们需要告诉客户端名称服务器的位置。RocketMQ提供了多种方法来实现这一目标。为简单起见，我们使用环境变量`NAMESRV_ADDR`，实现流程如下：
```
 > export NAMESRV_ADDR=localhost:9876
 > sh bin/tools.sh org.apache.rocketmq.example.quickstart.Producer
 SendResult [sendStatus=SEND_OK, msgId= ...

 > sh bin/tools.sh org.apache.rocketmq.example.quickstart.Consumer
 ConsumeMessageThread_%d Receive New Messages: [MessageExt...
```
>完成后发现RocketMQ-Console-Ng 界面产生变化：
 ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-send-websoft9.png)