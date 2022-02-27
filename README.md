# nginx 的入门操作
查看防火墙的开发端口
firewall-cmd --list-all
iptables -nxvL

增加防火墙开放端口
firewall-cmd --add-port=8080/tcp --permanent 

启动nginx         ./nginx
关闭nginx         ./nginx -s stop
重新加载nginx      ./nginx -s reload

>/usr/local/webserver/nginx/sbin/nginx -s reload            # 重新载入配置文件
/usr/local/webserver/nginx/sbin/nginx -s reopen            # 重启 Nginx
/usr/local/webserver/nginx/sbin/nginx -s stop              # 停止 Nginx

测试 nginx 配置文件是否正确 /usr/local/nginx/sbin/nginx  -t -c  /usr/local/nginx/conf/nginx.conf  
> 注意 -t 要放在 -c 参数的前面，否则会出现 “nginx: invalid option” 的错误

以指定的配置文件重启nginx  ： /usr/local/nginx/sbin/nginx  -s reload  -c  /usr/local/nginx/conf/nginx.conf

* location 命令的匹配规则
    * "="号：用于不含正则表达式的 uri 前，要求请求字符串与 uri 严格匹配，如果匹配成功，就停止继续向下搜索并立即处理该请求
    * "~"号：用于表示 uri 包含正则表达式，并且区分大小写
    * "~*"号：用于表示 uri 包含正则表达式，并且不区分大小写
    * "^~"号：用于不含正则表达式的 uri 前。要求 Nginx 服务器找到表示 uri 和请求字符串匹配度最高的 location 后，
      立即使用此 location 处理请求，而不再使用 location 块中的正则 uri 和请求字符串做匹配
      >注意：如果 uri 包含正则表达式，则必须要有 ~ 或者 ~* 的标识


      