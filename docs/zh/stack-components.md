---
sidebarDepth: 3
---

# 参数

RocketMQ 预装包包含 RocketMQ 运行所需一序列支撑软件（简称为“组件”），下面列出主要组件名称、安装路径、配置文件地址、端口、版本等重要的信息。

## 路径

### RocketMQ

RocketMQ 安装目录： */data/wwwroot/rocketmq*  
RocketMQ 日志目录： */data/logs/rocketmq*  
RocketMQ 配置文件： */data/config/rocketmq*

### RocketMQ-Console-Ng

RocketMQ-Console-Ng 是一款可视化 RocketMQ 管理工具，在本项目中它基于 Docker 安装。  

安装目录：*/data/apps/rocketmq-console-ng*  
Compose文件：*/data/apps/rocketmq-console-ng/docker-compose.yml* 

### Docker

Docker 根目录: */var/lib/docker*  
Docker 镜像目录: */var/lib/docker/image*   
Docker daemon.json 文件：默认没有创建，请到 */etc/docker* 目录下根据需要自行创建   

## 端口号

在云服务器中，通过 **[安全组设置](https://support.websoft9.com/docs/faq/zh/tech-instance.html)** 来控制（开启或关闭）端口是否可以被外部访问。 

通过命令`netstat -tunlp` 看查看相关端口，下面列出可能要用到的端口：

| 名称 | 端口号 | 用途 |  必要性 |
| --- | --- | --- | --- |
| TCP | 9876 | 通过 HTTP 访问 RocketMQ Broker Server | 必须 |
| TCP | 9003 | 通过 HTTP 访问 RocketMQ-Console-Ng    | 可选 |

## 版本号

组件版本号可以通过云市场商品页面查看。但部署到您的服务器之后，组件会自动进行更新导致版本号有一定的变化，故精准的版本号请通过在服务器上运行命令查看：

```shell
# Check all components version
sudo cat /data/logs/install_version.txt

# Linux Version
lsb_release -a

# Java version
java -v

# Docker Version
docker -v

```
