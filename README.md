# 搭趣 SpotPal · 项目文档与高保真原型

基于**兴趣 + 位置**的搭子匹配轻社交产品。核心差异化：**AI 代协商**——把「约人时最难的沟通」交给 AI，用户只需上推一个意图。

本仓承载产品设计全流程交付物：技术架构文档、客户端/服务端详细设计、高保真交互原型。

## 目录

| 文件 | 说明 |
|---|---|
| `技术设计文档.md` | 总体架构：模块化单体、状态机、事件总线、outbox 模式、WS 网关契约 |
| `详细设计-服务端.md` | Go 服务端 8 模块详设（user/match/squad/negotiate/im/pay/credit/risk） |
| `详细设计-客户端.md` | Android 客户端详设（MVI、上推托付手势、WsClient、Room 三表） |
| `spotpal-app.html` | 高保真交互原型（7 屏，严格还原设计稿，可直接浏览器打开） |
| `搭趣SpotPal-演示版.html` | 演示版原型 |
| `index.html` | 原型入口页 |

## 相关仓库

- [`spotpal-server`](../spotpal-server)：Go + SQLite 单二进制服务端实现
- [`spotpal-android`](../spotpal-android)：Kotlin + Compose 客户端实现

## 核心概念速览

```text
发现搭子 ──上推托付──▶ 候选池 ──释放委托──▶ AI 代协商（≤5 轮 / 48h）
                                                   │
                                       双方确认 ◀──┘
                                                   ▼
                                       搭局成局 ──打卡结算（纯记账，线下自理）
```

## 许可

MIT（见仓库根目录 LICENSE）。