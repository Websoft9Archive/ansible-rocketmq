# FAQ

#### RocketMQ-Console-Ng 是否支持多语言？

目前支持英文和简体中文，可以登陆后设置
![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-language-websoft9.png)

#### 本项目中 RocketMQ 采用何种安装方式？

采用二进制包解压的安装方式

#### RocketMQ-Console-Ng 管理员用户对应的密码是多少？

密码存放在服务器相关文件中：`/credentials/password.txt`

#### RocketMQ 的消息保存多久？

消息将最多保存3天，未使用超过3天的消息将被删除。

#### 是否有可视化的管理工具？

有，内置RocketMQ-Console-Ng，访问地址：*http://服务器公网IP:9095*

#### 是否可以修改RocketMQ的源码路径？

不可以

#### 如何修改上传的文件权限?

```shell
# 拥有者
chown -R apache.apache /data/wwwroot/
# 读写执行权限
find /data/wwwroot/ -type d -exec chmod 750 {} \;
find /data/wwwroot/ -type f -exec chmod 640 {} \;
```

#### 部署和安装有什么区别？

部署是将一序列软件按照不同顺序，先后安装并配置到服务器的过程，是一个复杂的系统工程。  
安装是将单一的软件拷贝到服务器之后，启动安装向导完成初始化配置的过程。  
安装相对于部署来说更简单一些。 

#### 云平台是什么意思？

云平台指提供云计算服务的平台厂家，例如：Azure,AWS,阿里云,华为云,腾讯云等

#### 实例，云服务器，虚拟机，ECS，EC2，CVM，VM有什么区别？

没有区别，只是不同厂家所采用的专业术语，实际上都是云服务器
