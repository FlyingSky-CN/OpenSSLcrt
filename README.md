# OpenSSL自签发证书(CA, Server, Client)生成脚本

## 使用

1. 生成根证书:  
    - 打开脚本, 按自己需求修改字段值
    - `./ff.crt.ca.sh`
2. 生成服务端证书(Web服务使用):  
    - `./ff.crt.server.sh '*.fufuok.com' 7777 server`
    - `./ff.crt.server.sh '*.fufuok.com'`
3. 生成用户证书(如果需要):  
    - `./ff.crt.client.sh fufu中`
    - `./ff.crt.client.sh fufu中 7777 fufu 123456`
4. 一句命令生成 crt 和 key:  
    - `openssl req -x509 -sha256 -nodes -days 824 -newkey rsa:2048 -keyout server.key -out server.crt -subj "/C=CN/ST=SC/L=CD/O=XY/OU=FF/CN=*.fufuok.com"`
    - 需要支持 IOS13 (使用者可选名称), 则在命令后加上 ` -config ./ff.ssl.demo.cnf`
