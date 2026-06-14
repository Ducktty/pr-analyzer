# 市赚率分析器 · PR Analyzer

<p align="center">
  <img src="icon-192.png" width="100" alt="市赚率分析器图标">
</p>

<p align="center">
  <strong>AI 驱动的价值投资估值工具</strong><br>
  An AI-powered Value Investing Valuation Tool
</p>

<p align="center">
  <img src="https://img.shields.io/badge/PWA-支持离线-00D395?style=flat-square&logo=pwa" alt="PWA">
  <img src="https://img.shields.io/badge/AI-Claude%20Sonnet-58A6FF?style=flat-square" alt="AI">
  <img src="https://img.shields.io/badge/语言-中文%20%2F%20EN-F0B429?style=flat-square" alt="Language">
  <img src="https://img.shields.io/badge/完全免费-开源-00D395?style=flat-square" alt="Free">
</p>

---

## 中文说明

### 什么是市赚率（PR）？

市赚率（PR = Price-to-Earnings-on-ROE）是一个结合估值与盈利能力的进阶价值投资指标：

```
PR = PE ÷ ROE
```

- **PR < 0.6** → 巴菲特折扣区域，市场严重低估
- **PR = 1.0** → 合理估值，价格与赚钱能力匹配
- **PR > 1.0** → 偏高估值，需谨慎

当股利支付率低于 50% 时，系统会自动加入**修正系数**，避免只赚钱不分红的企业被高估。

---

### 核心功能

#### 📊 三种数据输入方式
| 方式 | 说明 |
|------|------|
| 📸 截图识别 | 上传 Moomoo、富途、雪球、TradingView 截图，AI 自动提取数据 |
| 📄 PDF 上传 | 上传 WSJ、Morningstar 等平台导出的财报 PDF，自动解析 |
| 🔍 代码搜索 | 输入股票代码（如 NVDA、2330.TW），AI 联网搜索最新数据 |

#### 📈 分析报告包含
- 市赚率（PE 模式 + PB 模式）计算
- 历史 PR 对比（当前 / 均值 / 历史最高 / 历史最低）
- 敏感性分析（ROE ±30% 时 PR 如何变化）
- AI 四段式报告（估值解读 / 驱动因素 / 风险提示 / 投资参考）

#### 🚨 6 项市赚率有效性审核
自动检测以下财务陷阱，提醒市赚率是否失效：

| # | 陷阱 | 红灯标准 |
|---|------|---------|
| 1 | 高负债高杠杆 | Debt-to-Assets > 70% |
| 2 | 周期性行业景气顶峰 | 航运/钢铁/煤炭等行业 |
| 3 | 一次性非经常性暴利 | Operating Income / Net Income < 80% |
| 4 | 商誉与存货虚高 | (Goodwill + Inventories) / Total Assets > 15% |
| 5 | 资产减值暴雷 | Impairment Losses / Net Income > 10% |
| 6 | 纸面富贵无现金 | Operating CF / Net Income < 0.8 |

---

### 安装使用（PWA）

#### 方法一：直接使用网页版
访问部署后的网址，用 Chrome 打开即可。

#### 方法二：安装到手机桌面（推荐）

**Android（Chrome）：**
1. 用 Chrome 打开网址
2. 底部弹出「添加到主屏幕」→ 点**安装**
3. 桌面出现图标，全屏启动，像原生 App

**iOS（Safari）：**
1. 用 Safari 打开网址
2. 点底部分享按钮 → **添加到主屏幕**

---

### 技术要求

- **Anthropic API Key**：在 [console.anthropic.com](https://console.anthropic.com) 免费注册获取
- 新用户有免费额度，足够日常使用
- API Key 仅存储在本地浏览器，不会上传到任何服务器

---

### 文件说明

```
pr-analyzer/
├── pr-analyzer.html   # 主程序（单文件包含所有功能）
├── manifest.json      # PWA 配置文件
├── sw.js              # Service Worker（离线缓存）
├── icon-192.png       # App 图标 192×192
└── icon-512.png       # App 图标 512×512
```

---

### 免责声明

本工具仅供学习与参考，**不构成任何投资建议**。市赚率为历史数据计算指标，投资决策请结合公司基本面、行业趋势及个人风险承受能力综合判断。

---

---

## English Documentation

### What is the PR Ratio?

The **PR Ratio (Price-to-Earnings-on-ROE)** is an advanced value investing metric that combines valuation with profitability:

```
PR = PE ÷ ROE
```

- **PR < 0.6** → Buffett discount zone — significantly undervalued
- **PR = 1.0** → Fair value — price matches earning power
- **PR > 1.0** → Overvalued — proceed with caution

A **correction factor** is automatically applied when the dividend payout ratio is below 50%, preventing companies that retain all earnings from appearing artificially cheap.

---

### Key Features

#### 📊 Three Data Input Methods
| Method | Description |
|--------|-------------|
| 📸 Screenshot OCR | Upload screenshots from Moomoo, Futu, Snowball, or TradingView — AI extracts data automatically |
| 📄 PDF Upload | Upload financial statement PDFs from WSJ, Morningstar, etc. — parsed automatically |
| 🔍 Ticker Search | Enter a ticker (e.g. NVDA, 2330.TW) — AI searches for the latest data online |

#### 📈 Analysis Report Includes
- PR calculation (PE mode + PB mode for banks/cyclicals)
- Historical PR comparison (current / average / all-time high / all-time low)
- Sensitivity analysis (how PR changes if ROE shifts ±30%)
- AI 4-section report (valuation interpretation / key drivers / risk warnings / investment takeaway)

#### 🚨 6-Point Validity Audit
Detects financial traps where the PR ratio may be misleading:

| # | Trap | Red Flag Threshold |
|---|------|--------------------|
| 1 | High Leverage | Debt-to-Assets > 70% |
| 2 | Cyclical Industry Peak | Shipping / Steel / Coal / Mining sectors |
| 3 | One-Time Earnings Spike | Operating Income / Net Income < 80% |
| 4 | Goodwill & Inventory Bloat | (Goodwill + Inventories) / Total Assets > 15% |
| 5 | Asset Write-down Risk | Impairment Losses / Net Income > 10% |
| 6 | Paper Profits (No Real Cash) | Operating CF / Net Income < 0.8 |

---

### Installation (PWA)

#### Option 1: Use in Browser
Visit the deployed URL and open in Chrome — ready to use immediately.

#### Option 2: Install on Home Screen (Recommended)

**Android (Chrome):**
1. Open the URL in Chrome
2. Tap the **"Add to Home Screen"** banner at the bottom
3. App launches fullscreen like a native app

**iOS (Safari):**
1. Open the URL in Safari
2. Tap the Share button → **Add to Home Screen**

---

### Requirements

- **Anthropic API Key**: Get one free at [console.anthropic.com](https://console.anthropic.com)
- New accounts include free credits sufficient for regular use
- Your API Key is stored only in your local browser — never sent to any external server

---

### File Structure

```
pr-analyzer/
├── pr-analyzer.html   # Main app (all features in one file)
├── manifest.json      # PWA configuration
├── sw.js              # Service Worker (offline caching)
├── icon-192.png       # App icon 192×192
└── icon-512.png       # App icon 512×512
```

---

### Disclaimer

This tool is for **educational and reference purposes only** and does not constitute investment advice. The PR ratio is calculated from historical financial data. Always combine with fundamental analysis, industry context, and your own risk tolerance before making any investment decision.

---

<p align="center">
  Built with ❤️ using Claude AI · 以 Claude AI 驱动
</p>
