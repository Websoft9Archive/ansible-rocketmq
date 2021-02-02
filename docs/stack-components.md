# Parameters

The RocketMQ deployment package contains a sequence of software (referred to as "components") required for RocketMQ to run. Below list the important information, the component name, installation directory path, configuration file path, port, version, etc.

## Path

### RocketMQ

RocketMQ installation directory: */data/wwwroot/rocketmq*  
RocketMQ  logs directory: */data/logs/rocketmq*  
RocketMQ configuration file: */data/config/rocketmq* 

### Nginx

Nginx vhost configuration file: */etc/nginx/conf.d/default.conf*    
Nginx main configuration file: */etc/nginx/nginx.conf*   
Nginx logs file: */var/log/nginx*  
Nginx rewrite rules directory: */etc/nginx/conf.d/rewrite* 

### Docker

Docker root directory: */var/lib/docker*  
Docker image directory: */var/lib/docker/image*   
Docker daemon.json: please create it when you need and save to to the directory */etc/docker*  

## Ports

Open or close ports by **[Security Group Setting](https://support.websoft9.com/docs/faq/tech-instance.html)** of your Cloud Server to decide whether the port can be accessed from Internet.  

You can run the cmd `netstat -tunlp` to check all related ports.  

The following are the ports you may use:

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| TCP | 9003 | HTTP to access RocketMQ-Console-Ng | Required |
| TCP | 9876 | TCP/HTTP to access  RocketMQ Broker Server | Required |

## Version

You can see the version on product pages at Marketplace. However, after being deployed to your server, the components will be updated automatically, resulting in a certain change in the version number. Therefore, run the command on the server to view the exact version number. 

```shell
# Check all components version
sudo cat /data/logs/install_version.txt

# Linux Version
lsb_release -a

# Nginx  Version
nginx -V

# Java version
java -v

# Docker Version
docker -v

# RocketMQ version
ls /data/wwwroot/rocketmq/lib |grep rocketmq-broker

```
