# 初始化安装

在云服务器上部署 RocketMQ 预装包之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 在云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:9003** 端口是否开启
3. 若想用域名访问 RocketMQ，请先到 **域名控制台** 完成一个域名解析

## RocketMQ 验证

### 通过shell命令验证
使用SSH登录到服务器后，运行如下几个命令，检查RocketMQ是否正确安装

```
sudo systemctl status mqnamesrv
sudo systemctl status mqbroker

```

### 通过可视化工具验证
1. 使用本地电脑的 Chrome 或 Firefox 浏览器访问网址：*http://域名:9003* 或 *http://服务器公网IP:9003*, 进入登陆页面
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-loginonly-websoft9.png)

2. 输入账号密码（[不知道账号密码？](/zh/stack-accounts.md#rocketmq)），成功登录到 RocketMQ 后台，没有弹出错误表示连接正常 
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-console-websoft9.png)

3. 验证失败时，右上角出现如下错误信息
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-error-websoft9.png)

> 需要了解更多 RocketMQ 的使用，请参考官方文档：[RocketMQ Documentation](http://rocketmq.apache.org/docs/quick-start/)

## RocketMQ 入门向导

现在开始针对于如何使用 RocketMQ 发送和接受消息，进行完整的说明：
在发送/接收消息之前，我们需要告诉客户端名称服务器的位置。RocketMQ提供了多种方法来实现这一目标。为简单起见，我们使用环境变量`NAMESRV_ADDR`，实现流程如下：
```
 > export NAMESRV_ADDR=localhost:9876
 > sh bin/tools.sh org.apache.rocketmq.example.quickstart.Producer
 SendResult [sendStatus=SEND_OK, msgId= ...

 > sh bin/tools.sh org.apache.rocketmq.example.quickstart.Consumer
 ConsumeMessageThread_%d Receive New Messages: [MessageExt...
```
 >完成后发现RocketMQ-Console-Ng 界面产生变化：
 ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-send-websoft9.png)


## 常见问题

#### 浏览器打开IP地址，无法访问 RocketMQ（白屏没有结果）？

您的服务器对应的安全组9003端口没有开启（入规则），导致浏览器无法访问到服务器的任何内容
