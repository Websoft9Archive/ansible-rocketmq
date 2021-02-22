# 初始化安装

在云服务器上部署 RocketMQ 预装包之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 在云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:9003** 端口是否开启
3. 若想用域名访问 RocketMQ，请先到 **域名控制台** 完成一个域名解析

## RocketMQ 验证向导

1. 使用 SSH 登录到 RocketMQ 所在服务器后，运行如下命令，检查 RocketMQ 服务状态
   ```
   sudo systemctl status mqnamesrv
   sudo systemctl status mqbroker
   ```
2. 使用本地浏览器访问可视化工具 [RocketMQ-Console](/zh/solution-gui.md)，进一步验证。
   ![RocketMQ-Console](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-console-websoft9.png)

## RocketMQ 入门向导

现在开始针对于如何使用 RocketMQ 发送（生产者）和接受消息（消费者），进行完整的实验说明。  

> 建议开始下面的步骤之前，先花5分钟时间阅读由通俗易懂的 [RocketMQ 知识要点](/zh/solution-study.md) 

1. 对实验所需准备的工具或程序做出说明

   * 发送人（本实验对应的是一个程序）：*/data/rocketmq/bin/tools.sh*
   * 接收人（本实验对应的是一个程序）：*/data/rocketmq/bin/tools.sh*
   * 消息信件：示例代码生成 `org.apache.rocketmq.example.quickstart.Producer` （Java 类）
   * 消息存储地： **RabbitMQ Broker**
   * 消息订单处理中心：**NAMESRV_ADDR** 用于根据消息存储地资源情况进行消息的动态分配

2. 使用 SSH 登录到 RocketMQ 服务器，运行下面命令，以发件人的身份发送消息
   ```
   export NAMESRV_ADDR=localhost:9876
   cd /data/rocketmq/bin
   sh tools.sh org.apache.rocketmq.example.quickstart.Producer
   ```

3. 发送成功会收到 *SendResult [sendStatus=SEND_OK, msgId= ...* 之类的反馈结果

4. 在运行下面的命令，以收件人的身份接受消息
   ```
   cd /data/rocketmq/bin
   sh tools.sh org.apache.rocketmq.example.quickstart.Consumer
   ```
5. 接受成功会收到 *ConsumeMessageThread_%d Receive New Messages: [MessageExt...* 之类的反馈结果

6. 登录到可视化界面 [RocketMQ-Console](/zh/solution-gui.md) 中可更直观的查看运行结果
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-send-websoft9.png)

> 需要了解更多 RocketMQ 的使用，请参考官方文档：[RocketMQ Documentation](http://rocketmq.apache.org/docs/quick-start/)

## 常见问题

#### 浏览器打开IP地址，无法访问 RocketMQ（白屏没有结果）？

您的服务器对应的安全组9003端口没有开启（入规则），导致浏览器无法访问到服务器的任何内容
