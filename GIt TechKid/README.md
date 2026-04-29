# 🎮 TechKids — 儿童技术学习教育 App Demo

> **面向 5~12 岁儿童的游戏化编程 + AI 互动 + 创意创作平台**  
> 单文件 HTML Demo，开箱即用，无需构建工具
> 

![TechKids Preview|106](https://img.shields.io/badge/TechKids-V1.0.3-blue) ![HTML](https://img.shields.io/badge/HTML5-Single--File-green) ![License](https://img.shields.io/badge/License-MIT-yellow)

---

## 📖 项目背景

TechKids 是一款 **iOS 儿童技术学习教育应用**的产品演示（Demo），完整模拟了 App 的核心交互流程和视觉设计。

在当前教育科技赛道中，**儿童编程启蒙市场**正处于高速增长期（CAGR ~15%），但现有产品普遍存在以下痛点：

| 痛点 | TechKids 的解法 |
|------|----------------|
| 编程门槛高、抽象枯燥 | 🎮 **游戏化拖拽编程** — 用「前进/左转/右转」指挥角色闯关 |
| AI 产品缺乏儿童适配 | 🤖 **AI 小伙伴「小智Bot」** — 多层安全过滤 + DeepSeek API 对话 |
| 创作工具复杂难上手 | 🎨 **创意工坊模板库** — 一键从模板创建动画/游戏/音乐作品 |
| 家长无法了解学习效果 | 📊 **家长数据看板** — 学习时长、关卡进度、使用控制 |

### 目标用户

- **核心用户**：5~12 岁儿童
- **决策用户**：家长（通过家长中心管控使用）
- **变现模式**：IAA（In-App Advertising，激励视频广告）

---

## ✨ 核心功能

### 🏠 首页 — 四大模块入口
- 每日签到奖励系统
- 四大功能模块卡片：编程探险 / AI实验室 / 创意工坊 / 家长中心
- iPad 设备框架仿真（刘海屏 + 状态栏 + Home Indicator）

### 🎮 编程探险岛（Adventure Island）
- **6 个渐进式关卡**：出发 → 转弯 → 躲避 → 迷宫 → 循环 → 海洋深处
- **拖拽代码块编程**：前进 / 左转 / 右转 三种基础指令
- **统一网格坐标系**：角色与目标严格对齐到 50×50px 网格
- **实时执行日志**：终端风格的指令执行可视化
- **星星评价系统**：1~3 星根据路径效率动态计算
- **IAA 激励广告**：观看广告获取双倍奖励

### 🤖 AI 实验室（AI Lab）
- **AI 宠物养成**：喂数据📊 / 和它玩🎾 / 训练它🧠 — 影响IQ和心情
- **DeepSeek AI 对话**：
  - 多层内容过滤（越狱 → 隐私 → 成人 → 编程白名单）
  - 打字动画 + 思考状态联动宠物表情
  - 快捷建议按钮引导首次交互
- **ML 分类小游戏**：猫/狗/苹果/车 图像分类体验
- **粘滞定位 Bot 区域**：滚动时始终可见

### 🎨 创意工坊（Creative Workshop）
- **项目库管理**：新建 / 编辑 / 分享 / 删除项目
- **6 类模板库**：动画故事 / 小游戏 / 音乐创作 / 贺卡海报 / 漫漫画格 / 拼图游戏
- **每周挑战赛**：参与进度追踪 + 往期挑战展示
- **项目详情页**：3 种项目预览画布（彩虹音乐盒 / 太空赛车 / 海洋大冒险）
- **localStorage 草稿保存**：本地持久化存储

### 📊 排行天梯榜
- **Top3 领奖台**：金银铜牌 + 头像 + 等级徽章
- **4~50 名列表**：排名 / 头像 / 昵称 / 积分 / 等级
- **动态数据渲染**

### 👤 个人中心
- 用户头像 / 昵称 / 等级显示
- 数据统计卡片：学习时长 / 完成关卡 / 获得星星 / 拥有金币
- 功能菜单：我的作品集 / 积分商城 / 设置 / 帮助反馈 / 关于

### 🔐 家长中心
- 数据看板：本周学习时长 / 完成关卡数
- 使用控制开关：广告管理 / 聊天过滤 / 使用时长限制
- 内容过滤设置

---

## 🛠 技术栈

| 技术 | 用途 |
|------|------|
| **HTML5** | 单文件架构，零依赖 |
| **CSS3** | Grid/Flexbox 布局、CSS 变量、Keyframe 动画、渐变/阴影 |
| **Vanilla JavaScript (ES6+)** | 页面路由、事件绑定、状态管理、localStorage |
| **DeepSeek API** | AI 对话后端（可配置为 Demo 模式） |
| **CSS Device Frame** | iPad 仿真框架（圆角/刘海/Home Indicator） |

### 架构特点

```
TechKids_Demo.html  (单文件 ~3300 行)
├── <style>          (~1400行) CSS变量 + 全部页面样式
├── <body>           (~700行) HTML结构（8个页面区域）
│   ├── Core Init    安全初始化脚本（函数兜底机制）
│   └── Pages         homePage / adventurePage / gameScreen / aiLabPage 
│                     creativePage / projectDetailView / rankPage / profilePage / parentPage
└── <script>         (~1200行) 主逻辑脚本
    ├── showPage()   SPA 页面切换引擎
    ├── 游戏引擎     网格坐标系 + 角色移动 + 碰撞检测
    ├── 过滤链路     jailbreak→privacy→adult→whitelist
    ├── DS API       fetch() 调用 DeepSeek chat/completions
    └── UI组件       Toast提示/模态框/排行榜/草稿管理
```

---

## 🚀 快速开始

### 方式一：直接打开
双击 `TechKids_Demo.html` 文件，即可在现代浏览器中运行。

### 方式二：本地服务器（推荐）
```bash
# Python 3
python -m http.server 8080

# Node.js
npx serve .

# VS Code Live Server 插件
# 右键 → Open with Live Server
```
然后访问 `http://localhost:8080/TechKids_Demo.html`

### 方式三：接入真实 DeepSeek API
编辑 `TechKids_Demo.html`，找到 `DS_CONFIG` 配置块：
```javascript
const DS_CONFIG = {
    endpoint: 'https://api.deepseek.com/chat/completions',  // API 地址
    apiKey: 'your-api-key-here',                            // 替换为你的 Key
    model: 'deepseek-v4-flash'                              // 推荐快速模型
};
```

---

## 📁 项目文件

```
TechKids/
├── TechKids_Demo.html      # ⭐ 主文件 — 完整的 App Demo
├── TechKids_PRD_V1.0.2.md  # 📋 产品需求文档（V1.0.3 已合入）
├── TechKids需求历史.md      # 📜 需求演进记录
├── README.md               # 📖 本文档
└── 部分要求.md             # 📝 原始产品要求说明
```

---

## 🎯 版本历史

| 版本 | 日期 | 主要更新 |
|------|------|---------|
| **V1.0.3** | 2026-04-28 | DeepSeek AI 对话系统 + 创意工坊增强（模板库/挑战赛/项目详情）+ Prompt 多层过滤 |
| **V1.0.2** | 2026-04-23 | 网格坐标重构 + Bot 粘滞布局 + 执行日志可视化 + 关键卡系统完善 |
| **V1.0.1** | 2026-04-23 | 基础功能补全：排行天梯榜 / 个人中心 / 返回按钮优化 |

---

## 📸 页面截图导航

| 页面 | 说明 |
|------|------|
| **首页** | 四大模块入口 + 每日签到 + 底部 Tab 导航 |
| **编程探险岛** | 关卡网格列表 → 选择关卡进入游戏界面 |
| **游戏界面** | 代码块编辑区 + 网格画布 + 执行日志终端 |
| **AI 实验室** | 小智Bot + 聊天区 + ML分类游戏 + 宠物互动 |
| **创意工坊** | 作品列表 + Tab切换(作品/模板/挑战) + 新建模态框 |
| **项目详情** | 预览画布 + 操作按钮(编辑/分享/返回) |
| **排行天梯** | Top3领奖台 + 50名积分列表 |
| **个人中心** | 头像信息 + 统计卡片 + 功能菜单 |
| **家长中心** | 数据看板 + 设置开关 |

---

## 📝 开发说明

### 设计原则
- **单文件架构**：所有 HTML/CSS/JS 内联在一个文件中，方便分发和展示
- **安全兜底机制**：Core Init 脚本确保即使主脚本部分失败，基础交互仍可用
- **渐进增强**：Demo 模式下所有 API 调用有 fallback 响应，不依赖外部服务即可体验全部流程
- **儿童友好**：大按钮、圆角设计、Emoji 引导、温和的色彩体系（Teal 主色调）

### 浏览器兼容性
- ✅ Chrome 90+
- ✅ Edge 90+
- ✅ Safari 14+
- ✅ Firefox 88+

---


<div align="center">

**🌟 如果这个项目对你有帮助，欢迎 Star！**

Made with ❤️ for young tech explorers

</div>
