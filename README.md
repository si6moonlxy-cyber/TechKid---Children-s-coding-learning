# TechKids

TechKids is a technology learning app demo for children aged 5 to 12. It combines game-based coding, an AI learning companion, creative project making, and a parent dashboard into a child-friendly product prototype.

The current repository represents the **V1.0.4 product demo**. The main experience runs from a single HTML file, while the PRD already defines the backend proxy, child-safe prompt strategy, few-shot direction, and Creative Workshop enhancements. The V1.0.5 roadmap analysis is available at [GIt TechKid/v1.0.5需求分析.md](./GIt%20TechKid/v1.0.5需求分析.md).

[English](README.md) | [简体中文](README_CN.md) | [繁體中文](README_TW.md)

📖 Table of Contents
- [Highlights](#highlights)
- [Stack](#stack)
- [Quick Start](#quick-start)
  - [Open directly](#open-directly)
  - [Run with a local server](#run-with-a-local-server)
  - [AI proxy note](#ai-proxy-note)
- [Repository Structure](#repository-structure)
- [Version History](#version-history)
- [Documentation](#documentation)
- [Safety Principles](#safety-principles)
- [License](#license)

## Highlights

| Area | Current capability |
|---|---|
| Coding Adventure Island | Grid-based levels, forward/left/right commands, execution logs, star rewards, rewarded-ad demo |
| AI Companion Lab | XiaoZhi Bot, child-safety filters, DeepSeek proxy endpoint config, fallback replies, ML classification mini game |
| Creative Workshop | My Projects, templates, weekly challenges, project detail pages, animated previews, localStorage drafts |
| Parent Center | Learning time, level progress, module progress, ad and screen-time control toggles |
| Profile and Ranking | Level, coins, stars, achievements entry, Top 3 podium, leaderboard list |

## Stack

| Technology | Purpose |
|---|---|
| HTML5 | Single-file demo structure |
| CSS3 | iPad frame, layout, animation, theme styling |
| Vanilla JavaScript | Routing, game logic, AI chat, draft persistence, challenge progress |
| localStorage | Draft projects and challenge progress |
| DeepSeek proxy config | Browser calls a local proxy endpoint so API keys do not appear in frontend code |

## Quick Start

### Open directly

Open `TechKids_Demo.html` in a modern browser. If the local AI proxy is not running, the chat feature falls back to built-in safe responses.

### Run with a local server

```bash
python -m http.server 8080
```

Then open:

```text
http://localhost:8080/TechKids_Demo.html
```

### AI proxy note

The demo currently points AI requests to:

```javascript
endpoint: 'http://127.0.0.1:8765/chat'
```

The V1.0.4 PRD defines a `server.py` backend proxy, but the current repository does not yet include the actual Python proxy files. V1.0.5 should add `server.py`, `.env.example`, `start_proxy.bat`, and `README_PROXY.md`, with the DeepSeek API key stored only in server-side environment variables.

## Repository Structure

```text
TechKid/
├── TechKids_Demo.html                 # Main demo with HTML/CSS/JS
├── TechKids_PRD_V1.0.4.md             # Current product requirements document
├── README_CN.md                       # Simplified Chinese README
├── README_TW.md                       # Traditional Chinese README
├── README_EN.md                       # English README
├── LICENSE
└── GIt TechKid/
    ├── 海外市场App投资价值分析报告.md
    ├── 部分要求.md
    └── v1.0.5需求分析.md
```

## Version History

| Version | Status | Main scope |
|---|---|---|
| V1.0.1 | Done | Leaderboard, profile center, basic UI and back navigation |
| V1.0.2 | Done | Grid alignment, sticky Bot layout, execution log |
| V1.0.3 | Done | DeepSeek chat, content filtering, Creative Workshop enhancements |
| V1.0.4 | PRD complete / partially reflected in demo | Backend proxy architecture, prompt hardening, safe initialization |
| V1.0.5 | Planned | Proxy delivery package, explicit few-shot examples, learning path, parent report, creative workflow, overseas readiness |

## Documentation

- PRD: [TechKids_PRD_V1.0.4.md](./TechKids_PRD_V1.0.4.md)
- Overseas market analysis: [GIt TechKid/海外市场App投资价值分析报告.md](./GIt%20TechKid/%E6%B5%B7%E5%A4%96%E5%B8%82%E5%9C%BAApp%E6%8A%95%E8%B5%84%E4%BB%B7%E5%80%BC%E5%88%86%E6%9E%90%E6%8A%A5%E5%91%8A.md)
- V1.0.5 analysis: [GIt TechKid/v1.0.5需求分析.md](./GIt%20TechKid/v1.0.5%E9%9C%80%E6%B1%82%E5%88%86%E6%9E%90.md)

## Safety Principles

- Never store real API keys in frontend code.
- Filter AI chat for prompt injection, privacy requests, adult or sensitive content, and off-topic input.
- Do not ask children for real names, schools, addresses, phone numbers, photos, passwords, or account credentials.
- Ads, sharing, ranking, and parent controls should use parent gates and child-safety messaging.
- Before an overseas launch, add COPPA/GDPR-K style parent consent, data export, and deletion flows.

## License

MIT License. See [LICENSE](./LICENSE).
