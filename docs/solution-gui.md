# Web-based GUI

RocketMQ external project have Web-based GUI tool [RocketMQ-Console-NG ](https://github.com/apache/rocketmq-externals/tree/master/rocketmq-console) to manage RocketMQ, this deployment solution have installed by default.  

## Access GUI

1. Use local Chrome or Firefox to access the URL: *http://Server's Internet IP:9003* to it
   ![RocketMQ-Console-NG login](https://libs.websoft9.com/Websoft9/DocsPicture/en/rocketmq/rocketmq-loginonly-websoft9.png)

2. Log in RocketMQ-Console-Ng console ([Don't have password?](/stack-accounts.md#rocketmq)) and enter to the console interface.  
   ![RocketMQ-Console-NG](https://libs.websoft9.com/Websoft9/DocsPicture/en/rocketmq/rocketmq-console-websoft9.png)

3. Set your language
   ![RocketMQ-Console language](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-language-websoft9.png)

4. You can refer to official docs [UserGuide](https://github.com/apache/rocketmq-externals/blob/master/README.md) for more experience
   ![RocketMQ-Console-NG](https://libs.websoft9.com/Websoft9/DocsPicture/en/rocketmq/rocketmq-error-websoft9.png)

## FAQ

#### How is this GUI installed?

Based on Docker

#### How can I modify the password of RocketMQ-Console?

Modify the password for the file:*/etc/nginx/.htpasswd/htpasswd.conf* and restart Nginx service

#### RocketMQ-Console display some error?
![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-error-websoft9.png)

Reason: RocketMQ-Console can not connect RocketMQ Server
Solution: Modify the service address of RocketMQ from the docker-compose file
