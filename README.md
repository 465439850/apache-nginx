# apache-nginx


二级域名配置 
1.在host中加入： 127.0.0.1    static.website2016.com
2.在apache的 http.conf中加上：
<VirtualHost 127.0.0.1:80> 
ServerAdmin administrator 
DocumentRoot "E:\phpStudy\WWW"
ServerName locahost
</VirtualHost>
<VirtualHost 127.0.0.1:80> 

ServerAdmin administrator 
DocumentRoot "E:\phpStudy\WWW\fe\static\website2016"
ServerName static.website2016.com
</VirtualHost>


nginx apache解决跨域的问题：
参考链接  http://blog.csdn.net/nlwangxin/article/details/46681299
修改httpd.conf,windows中对应的目录是:C:\wamp\bin\apache\Apache2.4.4\conf\httpd.conf
把LoadModule headers_module modules/mod_headers.so 前面的注释删除
修改  加上  Header set Access-Control-Allow-Origin *
<Directory />
    Options +Indexes +FollowSymLinks +ExecCGI
    AllowOverride All
    Order deny,allow
    Allow from all
	Header set Access-Control-Allow-Origin *
</Directory>

