# FAQ

#### RocketMQ-Console-Ng is multilingual supported?

At present, it supports English and simplified Chinese, which can be set after login
![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-language-websoft9.png)

#### How to install RocketMQ in this project?

Installed by binary package.

#### How long do RocketMQ messages last?

Messages will be saved for up to 3 days, and messages not used for more than 3 days will be deleted.

#### What is the password for the admin user?

The password is stored in the server related file `/credentials/password.txt`.

#### Is there a web-base GUI management tool?

Yes, RocketMQ-Console-Ng is included. Visit by *http://Server's Internet IP*.

#### Is it possible to modify the source path of RocketMQ?

No.

#### How to change the permissions of filesystem?

Change owner(group) or permissions as below:

```shell
chown -R nginx.nginx /data/wwwroot
find /data/wwwroot -type d -exec chmod 750 {} \;
find /data/wwwroot -type f -exec chmod 640 {} \;
```

#### What's the difference between Deployment and Installation?

- Deployment is a process of installing and configuring a series of software to the server in a different order, which is a complex system engineering.  
- Installation is the process of starting the initial wizard after the application is prepared.  
- Installation is simpler than deployment. 

#### What's Cloud Platform?

Cloud platform refers to platform manufacturers that provide cloud computing services, such as: **Azure, AWS, Alibaba Cloud, HUAWEI CLOUD, Tencent Cloud**, etc.

#### What is the difference between Instance, Cloud Server, Virtual Machine, ECS, EC2, CVM, and VM?

No difference. All refer to cloud servers. They are the different terminology used by manufacturers.
