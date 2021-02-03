# 服务启停

使用由 Websoft9 提供的 RocketMQ 部署方案，可能需要用到的服务如下：

### RocketMQ

```shell
sudo systemctl start mqnamesrv
sudo systemctl stop mqnamesrv
sudo systemctl restart mqnamesrv
sudo systemctl status mqnamesrv
```

```shell
sudo systemctl start mqbroker
sudo systemctl stop mqbroker
sudo systemctl restart mqbroker
sudo systemctl status mqbroker
```

### Docker

```shell
systemctl start docker
systemctl stop docker
systemctl restart docker
systemctl status docker
```

### Nginx

```shell
systemctl start nginx
systemctl stop nginx
systemctl restart nginx
systemctl status nginx
```

