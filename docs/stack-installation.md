# Initial Installation

If you have completed the RocketMQ deployment, follow the steps below to start a quick use.

## Preparation

1. Get the **Server's Internet IP** of Server on your Cloud Platform.
2. Check your **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the **TCP:9003** is allowed.
3. Make a domain resolution on your Cloud Console if you want to use domain for RocketMQ.

## RocketMQ install verification

### Verification by shell command

After logging in to the server with SSH, run the following commands to check whether rocketmq is installed correctly.
```
sudo systemctl status mqnamesrv
sudo systemctl status mqbroker

```

### Verified by visual tools

1. Use local Chrome or Firefox to access the URL *http://DNS:9003* or *http://Server's Server's Internet IP:9003*. Enter the login page.
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/rocketmq/rocketmq-login-websoft9.png)

2. Log in RocketMQ-Console-Ng console. ([Don't have password?](/stack-accounts.md#rocketmq)), no pop-up error indicates normal connection 
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/rocketmq/rocketmq-console-websoft9.png)

3. When the verification fails, the following error message appears in the upper right corner of web page
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/rocketmq/rocketmq-error-websoft9.png)

 > More guide about RocketMQ, please refer to [RocketMQ Documentation](http://rocketmq.apache.org/docs/quick-start/).

## RocketMQ Setup wizard

RocketMQ Name Server，Broker after service startup, how to verify whether messages can be sent and received normally?  
Before sending/receiving messages, we need to tell client the location of the name server. It provides a variety of ways to achieve this. For simplicity, we use the environment variable `NAMESRV_ADDR`, the implementation process is as follows:
```
 > export NAMESRV_ADDR=localhost:9876
 > sh bin/tools.sh org.apache.rocketmq.example.quickstart.Producer
 SendResult [sendStatus=SEND_OK, msgId= ...

 > sh bin/tools.sh org.apache.rocketmq.example.quickstart.Consumer
 ConsumeMessageThread_%d Receive New Messages: [MessageExt...
```
 >After completion, the rocketmq console ng interface changes:
 ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/rocketmq/rocketmq-send-websoft9.png)

## Q&A

#### Can't visit the start page of RocketMQ?

Your TCP:9003 of Security Group Rules is not allowed, so there is no response from Chrome or Firefox.
