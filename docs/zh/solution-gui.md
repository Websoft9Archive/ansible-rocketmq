# 可视化工具

RocketMQ 扩展项目中提供了管理和监控 RocketMQ 的可视化工具：[RocketMQ-Console-NG ](https://github.com/apache/rocketmq-externals/tree/master/rocketmq-console). 本部署方案默认安装了它，参考下面的步骤即可使用：  

## 连接

1. 使用本地电脑的 Chrome 或 Firefox 浏览器访问网址：*http://服务器公网IP:9003*, 进入登陆页面

   ![RocketMQ-Console-NG 登录页面](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-loginonly-websoft9.png)

2. 输入账号密码（[不知道账号密码？](/zh/stack-accounts.md#rocketmq)），成功登录到 RocketMQ 后台

   ![RocketMQ-Console](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-console-websoft9.png)

3. 设置自己喜欢的语言

   ![RocketMQ-Console 语言设置](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-language-websoft9.png)

3. 接下来便可以在可视化界面查看驾驶舱、集群、消费者等信息（[参考](https://github.com/apache/rocketmq-externals/blob/master/docs/connect/cn/README.md)官网文档）


## 常见问题

#### 这个可视化工具是如何安装的？

基于 Docker 安装。

#### 如何修改可视化工具的密码？

可视化工具默认没有提供账号管理功能，我们的部署方案中通过在 Nginx 的密码功能实现。需修改密码，请修改 */etc/nginx/.htpasswd/htpasswd.conf* 后，然后重启 Nginx 服务。

#### 连接失败，右上角出现如下错误信息？
![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-error-websoft9.png)

问题原因：可视化工具的 docker-compose 文件中 RocketMQ 服务的地址错误。  
解决方案：修改 RocketMQ 服务地址
