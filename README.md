# nginx 的入门操作
查看防火墙的开发端口
firewall-cmd --list-all
iptables -nxvL

增加防火墙开放端口
firewall-cmd --add-port=8080/tcp --permanent 

启动nginx         ./nginx
关闭nginx         ./nginx -s stop
重新加载nginx      ./nginx -s reload

# 注意 -t 要放在 -c 参数的前面，否则会出现 “nginx: invalid option” 的错误
测试 nginx 配置文件是否正确  ：/usr/local/nginx/sbin/nginx  -t -c  /usr/local/nginx/conf/nginx.conf  

以指定的配置文件重启nginx  ： /usr/local/nginx/sbin/nginx  -s reload  -c  /usr/local/nginx/conf/nginx.conf

