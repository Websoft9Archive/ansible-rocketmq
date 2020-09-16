# RocketMQ 自动化安装与部署

本项目是由 [Websoft9](http://www.websoft9.com) 研发的 [RocketMQ](http://rocketmq.apache.org/) 自动化安装程序，开发语言是 Ansible。使用本项目，只需要用户在 Linux 上运行一条命令，即可自动化安装 RocketMQ，让原本复杂的安装过程变得没有任何技术门槛。  

本项目是开源项目，采用 LGPL3.0 开源协议。

## 配置要求

操作系统：目支持 Ubuntu16.x 以上部署此脚本  
硬件配置：测试环境最低1核1G，10G系统盘空间，否则无法安装。生产环境请根据业务情况选择服务器配置

更多要求请参考[官方安装文档](http://rocketmq.apache.org/docs/quick-start/)

## 组件

包含的核心组件为：RocketMQ, Erlang

更多请见[参数表](/docs/zh/stack-components.md)

## 本项目安装的是 RocketMQ 最新版吗？

本项目通过下载 RocketMQ 安装包的方式安装，需要维护 [main.yml](/roles/rocketmq/task/main.yml) 中 src 对应的下载地址

```
- name: Download RocketMQ
      unarchive:
        src: https://mirrors.tuna.tsinghua.edu.cn/apache/rocketmq/4.5.1/rocketmq-all-4.5.1-bin-release.zip
        dest: /opt/
        remote_src: yes
        owner: rocketmq
        group: rocketmq
```


## 安装指南

以 root 用户登录 Linux，运行下面的**命令脚本**即可启动自动化部署，然后耐心等待，直至安装成功。

```
# coming soon
```  

注意：  

1. 如果以非 root 用户身份登录 Linux，请先通过 sudo 或 su 提升权限，再运行脚本。
2. 由于自动化安装过程中有大量下载任务，若网络不通（或速度太慢）会引起下载失败，从而导致安装程序终止运行。此时，请重置服务器后再次尝试安装，若仍然无法完成，请使用我们在公有云上发布的 [RocketMQ 镜像](https://apps.websoft9.com/rocketmq) 的部署方式


## 文档

文档链接：https://support.websoft9.com/docs/rocketmq

## FAQ

- 命令脚本部署与镜像部署有什么区别？请参考[镜像部署-vs-脚本部署](https://support.websoft9.com/docs/faq/zh/bz-product.html#镜像部署-vs-脚本部署)
- 本项目支持在 Ansible Tower 上运行吗？支持