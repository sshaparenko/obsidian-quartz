---
date: 2024-08-18T13:32
tags:
  - linux
  - falcon
cssclasses:
  - page-grid
  - center-images
---
### .service file
To configure a daemon, we should create a .service file under the `/etc/systemd/system/` directory

For example `/etc/systemd/system/falcon.service`

Content of this file should be as follows:
```
[Unit]
Description=<description>
ConditionPathExists=/home/sshaparenkos/go/falcon
After=network.target

[Service]
Type=simple
User=<username>
Group=<groupname>
WorkingDirectory=/home/sshaparenkos/go/falcon
ExecStart=/usr/local/go/bin/go run .

Restart=on-failure
RestartSec=10
StandardOutput=syslog
StandardError=syslog
SyslogIdentifier=falconservice

[Install]
WantedBy=multi-user.target
```

