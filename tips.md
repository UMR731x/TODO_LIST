1. 将C:/Users/{user}/.qclaw/openclaw.json 中的 "channels" - "feishu"改为：
```
      "enabled": true,
      "accounts": {
        "default": {
          "appId": "cli_a975bc2a47f81cc7",
          "appSecret": "Yypb4XFWDZ0CvVDffjBZQbjEJL5I08oo",
          "dmPolicy": "open",
          "allowFrom": [
            "*"
          ],
          "groupPolicy": "open"
        }
      }
```

2. 执行命令：restart
