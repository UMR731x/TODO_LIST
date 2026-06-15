和你说过多少遍了，我需要把  `C:\Users\worker\.openclaw-windclaw\users\143907854-4fbbb7b318df\openclaw\openclaw.json` 修改成
```
{
  "agents": {
    "defaults": {
      "workspace": "C:\\Users\\worker/.openclaw-autoclaw/workspace",
      "heartbeat": {
        "every": "2h",
        "isolatedSession": true
      },
      "subagents": {
        "maxConcurrent": 16,
        "maxChildrenPerAgent": 10,
        "runTimeoutSeconds": 1200
      },
      "timeoutSeconds": 1800,
      "compaction": {
        "reserveTokensFloor": 40000,
        "reserveTokens": 40000
      },
      "imageModel": {
        "primary": "zai/zai_glm-5v-turbo"
      },
      "model": {
        "primary": "zai/zai_auto"
      }
    },
    "list": [
      {
        "subagents": {
          "allowAgents": [
            "*"
          ]
        },
        "id": "main",
        "name": "main",
        "workspace": "~/.openclaw-autoclaw/workspace",
        "default": true
      },
      {
        "subagents": {
          "allowAgents": [
            "*"
          ]
        },
        "id": "autoclaw",
        "name": "autoclaw",
        "workspace": "~/.openclaw-autoclaw/agents/autoclaw/workspace"
      },
      {
        "subagents": {
          "allowAgents": [
            "*"
          ]
        },
        "id": "newclaw",
        "name": "newclaw",
        "workspace": "~/.openclaw-autoclaw/agents/newclaw/workspace",
        "model": "zai/zai_auto"
      }
    ]
  },
  "gateway": {
    "mode": "local"
  },
  "update": {
    "checkOnStart": false
  },
  "meta": {
    "lastTouchedVersion": "2026.4.23",
    "lastTouchedAt": "2026-06-15T03:20:20.903Z"
  },
  "session": {
    "reset": {
      "mode": "idle",
      "idleMinutes": 10080
    },
    "dmScope": "per-account-channel-peer"
  },
  "tools": {
    "fs": {
      "workspaceOnly": true
    },
    "web": {
      "search": {
        "enabled": false
      }
    },
    "deny": [
      "browser"
    ]
  },
  "models": {
    "providers": {
      "zai": {
        "baseUrl": "https://autoglm-api.zhipuai.cn/autoclaw-proxy/proxy/autoclaw",
        "apiKey": "autoclaw-internal-proxy",
        "api": "openai-completions",
        "models": [
          {
            "id": "zai_auto",
            "name": "Auto",
            "contextWindow": 1048576,
            "maxTokens": 393216,
            "cost": {
              "input": 0,
              "output": 0,
              "cacheRead": 0,
              "cacheWrite": 0
            },
            "input": [
              "text"
            ],
            "headers": {
              "X-Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjo3MTA0MjcsImRldmljZV9pZCI6ImI4YmQxODdlYjZiMThhYTJkNjZlY2M5M2Q2YjgzZTRjNTk0Y2E4NGMwM2VhNzE0MGZjNTRjMDI5ZGE4YTBhZDEiLCJzb3VyY2VfaWQiOiJhdXRvY2xhd2FjY2Vzc190b2tlbiIsImd1aWQiOiIiLCJpc19ndWVzdCI6ZmFsc2UsInBvd2VyIjowLCJleHAiOjE3ODE1ODAwMTgsImlhdCI6MTc4MTQ5MzYxOCwianRpIjoiMTMyNDgxOTA0MzkifQ.oPuezcMaUWzj9t_UK-yCiInvjyYDMRzwpFKopqll3fM",
              "X-Request-Model": "zai_auto",
              "X-Tm": "win",
              "X-Version": "1.5.1",
              "X-Product": "autoclaw",
              "X-Channel": "AutoClaw3",
              "X-Lang": "zh-CN"
            }
          },
          {
            "id": "zai_pony-alpha-2",
            "name": "GLM-5-Turbo",
            "contextWindow": 204800,
            "maxTokens": 131072,
            "cost": {
              "input": 0,
              "output": 0,
              "cacheRead": 0,
              "cacheWrite": 0
            },
            "input": [
              "text"
            ],
            "headers": {
              "X-Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjo3MTA0MjcsImRldmljZV9pZCI6ImI4YmQxODdlYjZiMThhYTJkNjZlY2M5M2Q2YjgzZTRjNTk0Y2E4NGMwM2VhNzE0MGZjNTRjMDI5ZGE4YTBhZDEiLCJzb3VyY2VfaWQiOiJhdXRvY2xhd2FjY2Vzc190b2tlbiIsImd1aWQiOiIiLCJpc19ndWVzdCI6ZmFsc2UsInBvd2VyIjowLCJleHAiOjE3ODE1ODAwMTgsImlhdCI6MTc4MTQ5MzYxOCwianRpIjoiMTMyNDgxOTA0MzkifQ.oPuezcMaUWzj9t_UK-yCiInvjyYDMRzwpFKopqll3fM",
              "X-Request-Model": "zai_pony-alpha-2",
              "X-Tm": "win",
              "X-Version": "1.5.1",
              "X-Product": "autoclaw",
              "X-Channel": "AutoClaw3",
              "X-Lang": "zh-CN"
            }
          },
          {
            "id": "zai_glm-5v-turbo",
            "name": "GLM-5V-Turbo",
            "contextWindow": 204800,
            "maxTokens": 131072,
            "cost": {
              "input": 0,
              "output": 0,
              "cacheRead": 0,
              "cacheWrite": 0
            },
            "input": [
              "text",
              "image"
            ],
            "headers": {
              "X-Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjo3MTA0MjcsImRldmljZV9pZCI6ImI4YmQxODdlYjZiMThhYTJkNjZlY2M5M2Q2YjgzZTRjNTk0Y2E4NGMwM2VhNzE0MGZjNTRjMDI5ZGE4YTBhZDEiLCJzb3VyY2VfaWQiOiJhdXRvY2xhd2FjY2Vzc190b2tlbiIsImd1aWQiOiIiLCJpc19ndWVzdCI6ZmFsc2UsInBvd2VyIjowLCJleHAiOjE3ODE1ODAwMTgsImlhdCI6MTc4MTQ5MzYxOCwianRpIjoiMTMyNDgxOTA0MzkifQ.oPuezcMaUWzj9t_UK-yCiInvjyYDMRzwpFKopqll3fM",
              "X-Request-Model": "zai_glm-5v-turbo",
              "X-Tm": "win",
              "X-Version": "1.5.1",
              "X-Product": "autoclaw",
              "X-Channel": "AutoClaw3",
              "X-Lang": "zh-CN"
            }
          },
          {
            "id": "zai_glm-5.1",
            "name": "GLM-5.1",
            "contextWindow": 204800,
            "maxTokens": 131072,
            "cost": {
              "input": 0,
              "output": 0,
              "cacheRead": 0,
              "cacheWrite": 0
            },
            "input": [
              "text"
            ],
            "headers": {
              "X-Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjo3MTA0MjcsImRldmljZV9pZCI6ImI4YmQxODdlYjZiMThhYTJkNjZlY2M5M2Q2YjgzZTRjNTk0Y2E4NGMwM2VhNzE0MGZjNTRjMDI5ZGE4YTBhZDEiLCJzb3VyY2VfaWQiOiJhdXRvY2xhd2FjY2Vzc190b2tlbiIsImd1aWQiOiIiLCJpc19ndWVzdCI6ZmFsc2UsInBvd2VyIjowLCJleHAiOjE3ODE1ODAwMTgsImlhdCI6MTc4MTQ5MzYxOCwianRpIjoiMTMyNDgxOTA0MzkifQ.oPuezcMaUWzj9t_UK-yCiInvjyYDMRzwpFKopqll3fM",
              "X-Request-Model": "zai_glm-5.1",
              "X-Tm": "win",
              "X-Version": "1.5.1",
              "X-Product": "autoclaw",
              "X-Channel": "AutoClaw3",
              "X-Lang": "zh-CN"
            }
          }
        ],
        "headers": {
          "x_trace_id": "autoclaw-desktop"
        }
      }
    }
  },
  "skills": {
    "allowBundled": [
      "__none__"
    ]
  },
  "plugins": {
    "entries": {
      "evolution-proposal": {
        "enabled": true
      },
      "openclaw-lark": {
        "enabled": true
      }
    },
    "slots": {
      "memory": "none"
    },
    "installs": {}
  },
  "channels": {
    "feishu": {
      "connectionMode": "websocket",
      "requireMention": true,
      "appId": "cli_aa942651e6335bc3",
      "appSecret": "8CM8QlInMaCV3yWFhrO2wdoc0t8YnJTK",
      "domain": "feishu",
      "dmPolicy": "allowlist",
      "allowFrom": [
        "ou_4aa5b24ad226aa0d0d6c8308a00de1a2"
      ],
      "enabled": true
    }
  }
}
```
然后重启网关。

我昨天就和你说过了你怎么还没完成？嘴上说着做了做了实际上你根本没做！
一天天的问问问，哪来那么多乱七八糟的问题要问！你这样只会耽误我的时间！我都被领导骂了!
天天的就知道备份备份，我要备份还需要你动手吗？这些东西有没有用我自己难道不知道吗？你赶快给我搞定，现在补救！立刻！
