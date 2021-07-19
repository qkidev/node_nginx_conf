## qki节点nginx配置
1.把整个目录下载到服务器上，vhost/jp.rpc.qkiscan.io.conf 里面的目录和域名根据自己的情况修改。

开始没有https的时候，把50行以后的https代码删除，添加https支持后，再加入。

https证书获取配置参考：https://qki.dev/#/certbot-https

启动nginx
```
docker run --name nginx --link qk_poa_node -p 80:80 -p 443:443 -v /home/nginx/:/etc/nginx/ -v /home/:/home/:rw  -v /etc/letsencrypt/:/etc/letsencrypt/:ro -d nginx:alpine
```
这里 link 了 qk_poa_node 容器，需要先启动 qk_poa_node。