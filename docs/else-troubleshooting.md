# Troubleshooting

If you're having trouble with running RocketMQ, here is a quick guide to solve most common problems.

> Most faults about the Instance is closely related to the Instance provider, Cloud Platform. Provided you're sure the fault is caused by Cloud Platform, refer to [Cloud Platform Documentation](https://support.websoft9.com/docs/faq/tech-instance.html).

#### How can I check the error logs?

You can find the keywords **Failed** or **error** from the logs directory: `/data/logs`

#### Can't start RocketMQ service?

Insufficient disk space and memory, incorrect configuration file may cause the failure to start the service. 

It is recommended to first check through the command.

```shell
# restart RocketMQ service
systemctl status mqnamesrv
journalctl -u mqnamesrv

systemctl status mqbroker
journalctl -u mqbroker

# view disk space
df -lh

# view memory rate
free -lh
```

>Please refer to [official document](http://rocketmq.apache.org/docs/faq/) for more trouble shooting

