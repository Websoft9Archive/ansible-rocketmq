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

升级之前请做好备份。  

RocketMQ 升级等同于重新安装，下面介绍升级步骤：

1. 访问 RocketMQ [下载页面](http://rocketmq.apache.org/docs/quick-start/)，检查服务器环境是否匹配安装要求

2. 停止 RocketMQ 服务，删除
    ```
    sudo systemctl stop mqnamesrv
    sudo systemctl stop mqbroker
    ```
3. 删除 RocketMQ 文件夹下所有的文件
   ```
   rm -rf /data/rocketmq/*
   ```
4. 下载新的 RocketMQ，并解压到 /data/rocketmq 目录下

5. 修改 *rocketmq/bin/runserver.sh* 文件中 Java 启动内存大小（非必要）

   > Xms4g -Xmx4g -Xmn2g 改成 Xms400M -Xmx400M -Xmn200M 表示降低了内存下限。

6. 修改 */data/rocketmq/bin/runbroker.sh* 文件中 Java 启动内存大小（非必要）

7. 重新启动服务，其状态正常就代表升级成功
    ```
    sudo systemctl start mqnamesrv
    sudo systemctl start mqbroker
    systemctl status mqnamesrv
    systemctl status mqbroker
    ```