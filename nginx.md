# Настройки nginx

**/etc/sysconfig/nginx**:

```
# Configuration file for the nginx service.

NGINX=/usr/local/sbin/nginx
CONFFILE=/usr/local/nginx/conf/nginx.conf

```

**/usr/lib/systemd/system**:

```
[Unit]
Description=nginx - high performance web server
Documentation=http://nginx.org/en/docs/
After=network-online.target remote-fs.target nss-lookup.target
#Wants=network-online.target

[Service]
Type=forking
PIDFile=/var/run/nginx.pid
ExecStartPre=/usr/local/nginx/sbin/nginx -t -c /usr/local/nginx/conf/nginx.conf
ExecStart=/usr/local/nginx/sbin/nginx -c /usr/local/nginx/conf/nginx.conf
ExecReload=/bin/kill -s HUP $MAINPID
ExecStop=/bin/kill -s QUIT $MAINPID
#PrivateTmp=true

[Install]
WantedBy=multi-user.target
```
