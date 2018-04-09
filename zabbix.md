### Systemd file

**/usr/lib/systemd/system/zabbix-server.service:**

```

Unit]
Description=Zabbix Server
After=syslog.target
After=network.target

[Service]
Environment="CONFFILE=/etc/zabbix/zabbix_server.conf"
EnvironmentFile=-/etc/sysconfig/zabbix-server
Type=forking
Restart=on-failure
PIDFile=/run/zabbix/zabbix_server.pid
KillMode=control-group
ExecStart=/usr/sbin/zabbix_server -c $CONFFILE
ExecStop=/bin/kill -SIGTERM $MAINPID
RestartSec=10s
TimeoutSec=0

[Install]
WantedBy=multi-user.target


```


**/usr/lib/systemd/system/zabbix-agent.service:**

```

[Unit]
Description=Zabbix Agent
After=syslog.target
After=network.target

[Service]
Environment="CONFFILE=/etc/zabbix/zabbix_agentd.conf"
EnvironmentFile=-/etc/sysconfig/zabbix-agent
Type=forking
Restart=on-failure
PIDFile=/run/zabbix/zabbix_agentd.pid
KillMode=control-group
ExecStart=/usr/sbin/zabbix_agentd -c $CONFFILE
ExecStop=/bin/kill -SIGTERM $MAINPID
RestartSec=10s

[Install]
WantedBy=multi-user.target


```

