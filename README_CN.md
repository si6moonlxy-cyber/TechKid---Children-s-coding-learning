# TechKids

面向 5 至 12 岁儿童的技术启蒙 App Demo，围绕「编程探险」「AI 小伙伴」「创意工坊」「家长中心」四个模块，演示一个儿童友好的游戏化编程与 AI 学习产品原型。

当前版本定位为 **V1.0.4 产品 Demo**：单文件 HTML 可直接运行，PRD 已覆盖后端代理、安全 Prompt、Few-Shot 方向与创意工坊增强。V1.0.5 的下一步需求分析见 [GIt TechKid/v1.0.5需求分析.md](./GIt%20TechKid/v1.0.5需求分析.md)。

[English](README.md) | [简体中文](README_CN.md) | [繁體中文](README_TW.md)

📖 目录
- [项目亮点](#项目亮点)
- [技术栈](#技术栈)
- [快速开始](#快速开始)
  - [直接打开](#直接打开)
  - [本地服务器运行](#本地服务器运行)
  - [AI 代理说明](#ai-代理说明)
- [项目结构](#项目结构)
- [版本脉络](#版本脉络)
- [文档入口](#文档入口)
- [安全与儿童体验原则](#安全与儿童体验原则)
- [License](#license)

## 项目亮点

| 模块 | 当前能力 |
|---|---|
| 编程探险岛 | 网格坐标关卡、前进/左转/右转指令、执行日志、星级奖励、激励广告演示 |
| AI 小伙伴实验室 | 小智 Bot 养成、儿童安全过滤、DeepSeek 代理调用配置、失败兜底回复、ML 分类小游戏 |
| 创意工坊 | 我的作品、模板库、每周挑战、项目详情页、预览动画、localStorage 草稿保存 |
| 家长中心 | 学习时长、关卡进度、模块进度、广告与时长控制开关 |
| 个人与排行 | 用户等级、金币/星星、成就入口、Top3 领奖台与排行榜列表 |

## 技术栈

| 技术 | 用途 |
|---|---|
| HTML5 | 单文件 Demo 架构 |
| CSS3 | iPad 设备框、响应式布局、动画、主题样式 |
| Vanilla JavaScript | 页面切换、游戏逻辑、AI 聊天、草稿存储、挑战进度 |
| localStorage | 保存草稿项目与挑战进度 |
| DeepSeek API 代理配置 | 前端指向本地代理地址，避免 API Key 出现在浏览器代码中 |

## 快速开始

### 直接打开

双击 `TechKids_Demo.html`，即可在现代浏览器中体验 Demo。若本地代理未启动，AI 聊天会自动使用内置兜底回复。

### 本地服务器运行

```bash
python -m http.server 8080
```

然后访问：

```text
http://localhost:8080/TechKids_Demo.html
```

### AI 代理说明

Demo 中的 AI 请求默认指向：

```javascript
endpoint: 'http://127.0.0.1:8765/chat'
```

PRD V1.0.4 已定义 `server.py` 后端代理方案，但当前仓库尚未包含实际 Python 代理脚本。建议在 V1.0.5 中补齐 `server.py`、`.env.example`、`start_proxy.bat` 与 `README_PROXY.md`，并确保 API Key 只存在于服务端环境变量中。

## 项目结构

```text
TechKid/
├── TechKids_Demo.html                 # 主 Demo，包含 HTML/CSS/JS
├── TechKids_PRD_V1.0.4.md             # 当前产品需求文档
├── README_CN.md                       # 简体中文 README
├── README_TW.md                       # 繁体中文 README
├── README_EN.md                       # English README
├── LICENSE
└── GIt TechKid/
    ├── 海外市场App投资价值分析报告.md
    ├── 部分要求.md
    └── v1.0.5需求分析.md
```

## 版本脉络

| 版本 | 状态 | 主要内容 |
|---|---|---|
| V1.0.1 | 已完成 | 排行榜、个人中心、基础 UI 与返回逻辑 |
| V1.0.2 | 已完成 | 网格坐标重构、Bot 粘滞布局、执行日志 |
| V1.0.3 | 已完成 | DeepSeek 对话、内容过滤、创意工坊增强 |
| V1.0.4 | 已写入 PRD / Demo 部分体现 | 后端代理架构、Prompt 强化、安全初始化 |
| V1.0.5 | 待开发 | 代理交付闭环、显式 Few-Shot、学习路径、家长报告、创作闭环、海外化准备 |

## 文档入口

- 产品需求文档：[TechKids_PRD_V1.0.4.md](./TechKids_PRD_V1.0.4.md)
- 海外市场分析：[GIt TechKid/海外市场App投资价值分析报告.md](./GIt%20TechKid/%E6%B5%B7%E5%A4%96%E5%B8%82%E5%9C%BAApp%E6%8A%95%E8%B5%84%E4%BB%B7%E5%80%BC%E5%88%86%E6%9E%90%E6%8A%A5%E5%91%8A.md)
- V1.0.5 需求分析：[GIt TechKid/v1.0.5需求分析.md](./GIt%20TechKid/v1.0.5%E9%9C%80%E6%B1%82%E5%88%86%E6%9E%90.md)

## 安全与儿童体验原则

- 不在前端保存真实 API Key。
- AI 对话默认经过越狱、隐私、成人敏感内容、主题相关性过滤。
- 不要求儿童提供真实姓名、学校、地址、电话、照片或账号密码。
- 广告、分享、排行榜、家长设置等能力应优先使用家长门槛与儿童安全提示。
- 后续若面向海外市场，需要进一步补齐 COPPA/GDPR-K 合规、家长同意、数据导出与删除流程。

## License

MIT License. See [LICENSE](./LICENSE).
