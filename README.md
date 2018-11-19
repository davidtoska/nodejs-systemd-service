# Use systemd to run a node-application as a service

File: /lib/systemd/system/hello_env.service
```
[Unit]
Description=hello_env.js - making your environment variables rad
Documentation=https://example.com
After=network.target

[Service]
Environment=NODE_PORT=3001
Type=simple
User=ubuntu
ExecStart=/usr/bin/node /home/ubuntu/hello_env.js
Restart=on-failure

[Install]
WantedBy=multi-user.target
```

- sudo systemctl daemon-reload
- sudo systemctl start hello_env
- sudo systemctl enable hello_env
- sudo systemctl stop hallo_evn