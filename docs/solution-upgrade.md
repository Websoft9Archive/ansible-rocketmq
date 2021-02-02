# Update & Upgrade

To update and upgrade is one of the main task for system maintenance. Like buildings without maintenance for a long time, programs without upgrading will age faster, lose functionality until they are unavailable.

Get to know the differences between the terms **Update** and **Upgrade**([Extended reading](https://support.websoft9.com/docs/faq/tech-upgrade.html#update-vs-upgrade))
- Patching operating system is **Updating**, while Ubuntu16.04 to Ubuntu18.04 means **Upgrading**.
- MySQL5.6.25 to MySQL5.6.30 means **Updating**, yet MySQL5.6 to MySQL5.7 means **Upgrading**.

Maintenance for RocketMQ includes the following two tasks.

- Update system (Operating System and Runtime) 
- Upgrade RocketMQ

## Update System 

Run a command to complete updating the system:

``` shell
#For Ubuntu&Debian
apt update && apt upgrade -y

#For CentOS&Redhat
yum update -y --skip-broken
```
> This deployment package is pre-configured with a scheduled task for automatic updating. If you want to remove the automatic updating, please delete the corresponding Cron.

## RocketMQ Upgrade

RocketMQ upgrade is the same with install a new version, you must completed all resource and data before upgrade.

The following is the step for upgrade:

1. Visit RocketMQ [Download](http://rocketmq.apache.org/docs/quick-start/) to check for the installation requirement

2. Stop RocketMQ service
    ```
    sudo systemctl stop mqnamesrv
    sudo systemctl stop mqbroker
    ```
3. Delete all files in the directory of RocketMQ 
   ```
   rm -rf /data/rocketmq/*
   ```
4. Download the new RocketMQ and unzip it to */data/rocketmq*

5. Modify java runtime memory in the file: *rocketmq/bin/runserver.sh* (Optional)

   > set Xms4g -Xmx4g -Xmn2g to Xms400M -Xmx400M -Xmn200M means reduce the memory limit

6. Modify java runtime memory in the file: *rocketmq/bin/runbroker.sh* (Optional)

7. Restart the RocketMQ and check the status
    ```
    sudo systemctl start mqnamesrv
    sudo systemctl start mqbroker
    systemctl status mqnamesrv
    systemctl status mqbroker
    ```