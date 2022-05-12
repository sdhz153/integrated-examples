介绍：

利用 caddy 支持 H2C 代理，实现 Xray 或 v2ray 的 trojan+h2c+tls 反向代理应用，TLS 由 caddy 提供及处理。

原理：

默认流程：WEB client <----------- HTTPS（HTTP/2） ----------> caddy（WEB server）  
匹配流程：Xray/v2ray client <----- H2C+TLS（HTTP/2） ------> caddy <-- H2C --> Xray/v2ray server

注意：

1、v2ray 版本不小于 v4.31.0 才支持 trojan 协议。

2、caddy 版本不小于 v2.2.0-rc.1 才支持 H2C proxy，即支持 Xray 或 v2ray 的 H2C 反向代理。

3、本示例 caddy 的 Caddyfile 格式配置与 json 格式配置二选一即可（完全等同）。支持自动 HTTPS，即自动申请与更新证书与私钥，自动 HTTP 重定向到 HTTPS。
