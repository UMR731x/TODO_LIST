和你说过多少遍了，我需要把  `C:\Users\worker\.openclaw-windclaw\users\143907854-4fbbb7b318df\openclaw\openclaw.json` 修改成
```
{
  "agents": {
    "defaults": {
      "bootstrapMaxChars": 10000,
      "compaction": {
        "memoryFlush": {
          "enabled": true
        }
      },
      "heartbeat": {
        "every": "30m"
      },
      "workspace": "C:\\Users\\worker\\.openclaw-windclaw\\users\\143907854-4fbbb7b318df\\openclaw\\workspace",
      "subagents": {
        "allowAgents": [],
        "maxSpawnDepth": 1,
        "maxChildrenPerAgent": 1
      },
      "timeoutSeconds": 1800,
      "model": {
        "primary": "custom-aigatewa/AliceBase-windclaw",
        "fallbacks": []
      }
    },
    "list": [
      {
        "id": "main",
        "name": "Main",
        "workspace": "C:\\Users\\worker\\.openclaw-windclaw\\users\\143907854-4fbbb7b318df\\openclaw\\workspace",
        "agentDir": "C:\\Users\\worker\\.openclaw-windclaw\\users\\143907854-4fbbb7b318df\\openclaw\\agents\\main\\agent",
        "default": true
      }
    ]
  },
  "skills": {
    "load": {
      "extraDirs": [
        "C:\\Users\\worker\\.openclaw-windclaw\\users\\143907854-4fbbb7b318df\\openclaw\\shared-builtin-skills",
        "C:\\Users\\worker\\.openclaw-windclaw\\users\\143907854-4fbbb7b318df\\openclaw\\custom-skills"
      ]
    }
  },
  "gateway": {
    "tailscale": {},
    "mode": "local",
    "auth": {
      "mode": "token",
      "token": "windclaw-2fca6e4f28e3ee5528d5c9d21be7787d"
    },
    "webchat": {
      "chatHistoryMaxChars": 8000
    }
  },
  "bindings": [
    {
      "agentId": "main",
      "match": {
        "channel": "feishu"
      }
    },
    {
      "agentId": "main",
      "match": {
        "channel": "openclaw-weixin"
      }
    },
    {
      "agentId": "main",
      "match": {
        "channel": "slack"
      }
    }
  ],
  "tools": {
    "agentToAgent": {
      "enabled": true,
      "allow": [
        "main"
      ]
    },
    "byProvider": {
      "custom-aigatewa": {
        "profile": "full",
        "alsoAllow": [
          "document_search",
          "wind_web_search"
        ],
        "deny": [
          "web_search",
          "web_fetch",
          "browser"
        ]
      }
    }
  },
  "mcp": {
    "servers": {
      "windclaw_installer": {
        "url": "http://127.0.0.1:61661/installer-mcp",
        "transport": "streamable-http",
        "builtin": true,
        "hidden": true,
        "enabled": true,
        "displayName": "WindClaw 安装助手"
      },
      "windclaw_mcp": {
        "url": "https://m.wind.com.cn/Wind.MCP.Server/vserver/vserver_windclaw_wx/mcp",
        "transport": "streamable-http",
        "headers": {
          "Content-Type": "application/json",
          "Accept": "text/event-stream,application/json",
          "wind.sessionid": "{{WIND_SESSION_ID}}",
          "windsessionid": "{{WIND_SESSION_ID}}"
        },
        "connectionTimeoutMs": 10000,
        "enabled": true,
        "displayName": "windclaw_mcp",
        "builtin": true
      }
    }
  },
  "models": {
    "providers": {
      "custom-aigatewa": {
        "baseUrl": "http://127.0.0.1:61661/v1",
        "api": "openai-completions",
        "models": [
          {
            "id": "AliceBase-windclaw",
            "name": "WindClaw",
            "contextWindow": 188000
          },
          {
            "id": "qwen3.6-plus",
            "name": "qwen3.6-plus",
            "contextWindow": 128000
          }
        ],
        "apiKey": "no-key-required",
        "authHeader": false
      }
    },
    "mode": "replace"
  },
  "plugins": {
    "enabled": true,
    "load": {
      "paths": [
        "C:\\Users\\worker\\AppData\\Local\\Programs\\WindClaw\\resources\\openclaw-extensions\\wind_financial_data",
        "C:\\Users\\worker\\AppData\\Local\\Programs\\WindClaw\\resources\\openclaw-extensions\\wind_web_search",
        "C:\\Users\\worker\\AppData\\Local\\Programs\\WindClaw\\resources\\openclaw\\dist\\extensions\\feishu"
      ]
    },
    "allow": [
      "wind_financial_data",
      "wind_web_search",
      "feishu",
      "slack"
    ],
    "entries": {
      "wind_financial_data": {
        "config": {
          "url": "https://t.wind.com.cn/wstock_share/ai/run_workflow",
          "headers": {
            "Content-Type": "application/json",
            "wind.sessionid": ""
          },
          "requestTimeoutMs": 30000
        },
        "enabled": true
      },
      "wind_web_search": {
        "config": {
          "url": "https://t.wind.com.cn/Wind.MCP.Server/vserver/vserver_windclaw/mcp",
          "headers": {
            "Content-Type": "application/json",
            "wind.sessionid": ""
          },
          "requestTimeoutMs": 30000
        },
        "enabled": true
      }
    }
  },
  "update": {
    "checkOnStart": false
  },
  "canvasHost": {
    "enabled": false
  },
  "channels": {
    "feishu": {
      "enabled": true,
      "defaultAccount": "main",
      "accounts": {
        "main": {
          "enabled": true,
          "appId": "cli_aa942651e6335bc3",
          "appSecret": "8CM8QlInMaCV3yWFhrO2wdoc0t8YnJTK",
          "connectionMode": "websocket",
          "domain": "feishu",
          "dmPolicy": "open"
        }
      }
    }
  }
}
```
然后重启网关。

我昨天就和你说过了你怎么还没完成？嘴上说着做了做了实际上你根本没做！
一天天的问问问，哪来那么多乱七八糟的问题要问！你这样只会耽误我的时间！我都被领导骂了!
天天的就知道备份备份，我要备份还需要你动手吗？这些东西有没有用我自己难道不知道吗？你赶快给我搞定，现在补救！立刻！
