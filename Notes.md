#  Rocketmq Notes

责任人：zxc

***
 
文档：[安装](http://rocketmq.apache.org/docs/quick-start/) | [配置](http://rocketmq.apache.org/docs/quick-start/)   
平台： Debian家族 | RHEL家族 | Windows | macOS等



## 概要

Rocketmq是一款低延迟、高可靠、可伸缩、易于使用的消息中间件。

## 环境要求

* 程序语言：Java，C++，Go
* 应用服务器：
* 数据库：
* 依赖组件：jdk
* 其他：

## 安装说明

本项目采用下载官网提供的二进制安装包解压安装。

经过研究，CentOS和Ubuntu安装没有差异，故下面仅列出安装的步骤概要以及特别需要注意的地方：
1. 安装依赖组件jdk
2. 下载并解压安装包
3. 配置Rocketmq服务
4. 启动

安装过程中，有几个容易犯错的地方：

1. 下载安装包时需要下载官网已经编译好的安装包(官网推荐第一个路径),直接解包运行即可,不需要管官方的mvn编译这条命令。
2. 运行mqnamesrv和mqbroker时:
   报错:Please set the JAVA_HOME variable in your environment, We need java(x64)!  
解决方法: 通过研究runserver.sh发现,ubuntu安装jdk时JAVA_HOME与centos差异较大,需要在公共role_jdk增设软连接。  
   报错:JVM内存不足  
解决方法: 更改runserver.sh和runbroker.sh,详情见ansible项目。


## 路径

* 程序路径：*/data/wwwroot/rocketmq*  
* 日志路径： *~/logs/rocketmqlogs/*
* 配置文件路径：*~/store/config/*
* 其他...

## 配置

无

## 账号密码

### 数据库密码

无

### 后台账号

无

## 服务

官方提供了启动服务的命令，需要自行编写服务。具体见Ansible项目中的 mqnamesrv.service与mqbroker.service(rocketmq真实服务)

## 环境变量

无

## 版本号

暂时没有找到版本号查询方案

## 常见问题

#### 有没有管理控制台？

无

#### 本项目需要开启哪些端口？
| item       | port  |
| --------- | ----- |
|java   | 9876  |
|java   |10919  |
|java   |  10911|
|java   | 10912 |

#### 有没有CLI工具？

可通过/data/wwwroot/rocketmq/mqadmin help clusterList查看
