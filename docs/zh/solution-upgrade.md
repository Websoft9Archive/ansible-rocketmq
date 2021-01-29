# 更新升级

网站技术日新月异，**更新升级**是维护工作之一，长时间不升级的程序，就如长时间不维护的建筑物一样，会加速老化、功能逐渐缺失直至无法使用。  

这里注意更新与升级这两词的差异（[延伸阅读](https://support.websoft9.com/docs/faq/zh/tech-upgrade.html#更新-vs-升级)），例如：
- 操作系统打个补丁常称之为**更新**，Ubuntu16.04 变更为 Ubuntu18.04，称之为**升级**
- MySQL5.6.25-->MySQL5.6.30 常称之为**更新**，MySQL5.6->MySQL5.7 称之为**升级**

RocketMQ 完整的更新升级包括：系统级更新（操作系统和运行环境）和 RocketMQ 程序升级两种类型

## 系统级更新

运行一条更新命令，即可完成系统级（包含RocketMQ小版本更新）更新：

``` shell
#For Ubuntu&Debian
apt update && apt upgrade -y

#For Centos&Redhat
yum update -y --skip-broken
```
> 本部署包已预配置一个用于自动更新的计划任务。如果希望去掉自动更新，请删除对应的Cron

## RocketMQ 升级

### 升级前提
升级前，请查看官方JDK是否满足新版本需求，不满足需要安装符合要求的JDK

### 升级步骤

1. 停止当前RocketMQ服务
```
sudo systemctl stop mqnamesrv
sudo systemctl stop mqbroker
```

2. 将目录（*/data/wwwroot/*）**压缩后**备份

3. 删除/data/wwwroot/下所有文件以及文件夹

4. 下载需要的RocketMQ版本，并解压到/data/wwwroot/目录下

5. 修改/data/wwwroot/rocketmq/bin/runserver.sh的JAVA_OPT配置，使其能正常运行

6. 重新启动服务，其状态正常就代表升级成功
```
sudo systemctl start mqnamesrv
sudo systemctl start mqbroker
systemctl status mqnamesrv
systemctl status mqbroker

```

