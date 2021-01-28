# 初始化安装

在云服务器上部署 RocketMQ 预装包之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 在云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:80** 端口是否开启
3. 若想用域名访问 RocketMQ，请先到 **域名控制台** 完成一个域名解析

## RocketMQ 安装向导

1. 使用本地电脑的 Chrome 或 Firefox 浏览器访问网址：*http://域名* 或 *http://服务器公网IP*, 进入登陆页面
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-login-websoft9.png)

2. 输入账号密码（[不知道账号密码？](/zh/stack-accounts.md#rocketmq)），成功登录到 RocketMQ 后台  
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-bk-websoft9.png)

> 需要了解更多 RocketMQ 的使用，请参考官方文档：[RocketMQ Documentation](http://rocketmq.apache.org/docs/quick-start/)

## RocketMQ 入门向导

现在开始针对于如何使用 RocketMQ 传输数据，进行完整的说明：

## 常见问题

#### 浏览器打开IP地址，无法访问 RocketMQ（白屏没有结果）？

您的服务器对应的安全组80端口没有开启（入规则），导致浏览器无法访问到服务器的任何内容

#### RocketMQ 服务启动失败？

暂无
