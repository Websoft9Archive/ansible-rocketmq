# 更多...

下面每一个方案，都经过实践证明行之有效，希望能够对你有帮助

## 消息示例

对于如何发送消息以及接受消息，本文档章节：[RocketMQ 入门向导](zh/stack-installation.md#rocketmq-入门向导) 中有详细的讲解。

## RocketMQ-Console 密码

RocketMQ-Console 工具默认没有提供账号管理功能，但部署方案中通过在 Nginx 的密码功能实现。  
 
需修改密码，请修改 */etc/nginx/.htpasswd/htpasswd.conf* 后，然后重启 Nginx 服务。