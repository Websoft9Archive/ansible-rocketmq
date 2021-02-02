# Initial Installation

If you have completed the RocketMQ deployment, follow the steps below to start a quick use.

## Preparation

1. Get the **Server's Internet IP** of Server on your Cloud Platform.
2. Check your **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the **TCP:9003** is allowed.
3. Make a domain resolution on your Cloud Console if you want to use domain for RocketMQ.

## RocketMQ install verification

1. Use **SSH** to connect RocketMQ and run the following commands to check for the status of RocketMQ
   ```
   sudo systemctl status mqnamesrv
   sudo systemctl status mqbroker
   ```
2. Use local Chrome or Firefox to access [RocketMQ-Console](/zh/solution-gui.md) to verify more
   ![RocketMQ-Console](https://libs.websoft9.com/Websoft9/DocsPicture/en/rocketmq/rocketmq-console-websoft9.png)


## RocketMQ Setup wizard

This chapter we will introduce a details for you how to use RocketMQ to send messages (producer) and consume messages(consumer)  

1. Explain the tools or procedures required for the experiment

   * producer: */data/rocketmq/bin/tools.sh*
   * consumer：*/data/rocketmq/bin/tools.sh*
   * Messages：produce from the Java Class `org.apache.rocketmq.example.quickstart.Producer`  
   * Messages storage:  **RabbitMQ Broker**
   * Message order management: **NAMESRV_ADDR** 

2. Use **SSH** to connect RocketMQ Server, run the following command to send message as producer.
   ```
   export NAMESRV_ADDR=localhost:9876
   sh bin/tools.sh org.apache.rocketmq.example.quickstart.Producer
   ```

3. You can see the feedback message *SendResult [sendStatus=SEND_OK, msgId= ...* when send successfully

4. Run the following command to send message as consumer.
   ```
   sh bin/tools.sh org.apache.rocketmq.example.quickstart.Consumer
   ```
5. You can see the feedback message *ConsumeMessageThread_%d Receive New Messages: [MessageExt...* when receive successfully

6. Login to GUI tool [RocketMQ-Console](/zh/solution-gui.md) to query more information
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/rocketmq/rocketmq-send-websoft9.png)

> More guide about RocketMQ, please refer to [RocketMQ Documentation](http://rocketmq.apache.org/docs/quick-start/).

## Q&A

#### Can't visit the start page of RocketMQ?

Your TCP:9003 of Security Group Rules is not allowed, so there is no response from Chrome or Firefox.
