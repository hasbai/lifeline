# 人生 K 线 | Life K-Line

<div align="center">

[中文](./README.md) | [English](./README_en.md)

---

**洞悉命运起伏，预见人生轨迹**

一个结合传统八字命理与现代金融数据可视化的 AI 命运分析工具

---

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![React](https://img.shields.io/badge/React-18.3-blue.svg)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.8-blue.svg)](https://www.typescriptlang.org/)

</div>

## 📖 项目简介

人生 K 线是一个创新的命运分析应用，将传统中国八字命理学与现代金融 K 线图可视化技术相结合。通过 AI 驱动的分析，将您的一生运势转化为直观的股票走势图，帮助您：

- 🎯 发现人生的"牛市"时期
- ⚠️ 规避"熊市"风险
- 🔮 把握关键转折点
- 📊 预见 100 年人生轨迹

## 📸 系统展示

<div align="center">

**首页**

<img src="doc/首页.png" alt="首页" width="800"/>

**八字排盘**

<img src="doc/八字排盘.png" alt="八字排盘" width="800"/>

**K线分析**

<img src="doc/k线.png" alt="K线分析" width="800"/>

</div>

## ✨ 核心功能

- **智能八字排盘**：自动计算真太阳时和农历日期
- **AI 命运分析**：基于 Gemini AI 生成详细的人生运势报告
- **可视化 K 线图**：100 年运势以金融 K 线形式展示
- **多维度分析**：
  - 币圈交易运势
  - 性格分析
  - 事业与行业
  - 风水建议
  - 财富层级
  - 婚姻情感
- **多语言支持**：中文/英文界面切换
- **主题模式**：支持亮色/暗色主题
- **PDF 报告导出**：一键保存完整命运分析报告

## 🛠 技术栈

- **框架**: React 18.3 + TypeScript 5.8
- **构建工具**: Vite 6.2
- **UI 组件**:
  - Recharts (图表可视化)
  - Lucide React (图标)
- **AI 服务**:
  - Google Generative AI (原生 Gemini API)
  - OpenAI SDK (第三方转发支持)
- **其他工具**:
  - html2canvas (截图)
  - jsPDF (PDF 生成)

## 🚀 快速开始

### 环境要求

- Node.js 16+
- npm 或 yarn

### 安装步骤

1. **克隆项目**
```bash
git clone https://github.com/XIAOEEN/lifeline-k-.git
cd life-destiny-k-line
```

2. **安装依赖**
```bash
npm install
```

3. **配置环境变量**

在项目根目录创建 `.env.local` 文件：

```env
# Gemini API Key (必填)
VITE_GEMINI_API_KEY=your_api_key_here

# 模型名称 (可选，默认: gemini-2.0-flash-thinking-exp-01-21)
VITE_MODEL_NAME=gemini-2.0-flash-thinking-exp-01-21

# API Base URL (可选)
# 留空使用原生 Gemini API
# 填写 URL 使用第三方转发平台（如: https://api.gpt.ge/v1/）
VITE_BASE_URL=
```

4. **启动开发服务器**
```bash
npm run dev

# 或者使用pm2启动
# 安装pm2
#  npm install -g pm2
 pm2 start ecosystem.config.js --only life-destiny-k-line-prod
```



5. **访问应用**

打开浏览器访问 `http://localhost:5173`

### 构建生产版本

```bash
npm run build
npm run preview
```

## 🔑 API 配置说明

项目支持两种 API 调用方式：

### 方式一：原生 Gemini API
```env
VITE_GEMINI_API_KEY=your_gemini_api_key
VITE_BASE_URL=
```

### 方式二：第三方转发平台
```env
VITE_GEMINI_API_KEY=your_api_key
VITE_BASE_URL=https://api.gpt.ge/v1/
```

## 📁 项目结构

```
life-destiny-k-line/
├── src/
│   ├── components/          # React 组件
│   │   ├── InputForm.tsx    # 输入表单
│   │   ├── BaZiDisplay.tsx  # 八字显示
│   │   ├── BaZiConfirmation.tsx  # 确认页面
│   │   ├── KLineChart.tsx   # K线图表
│   │   └── AnalysisSection.tsx   # 分析报告
│   ├── services/            # 服务层
│   │   └── geminiService.ts # AI API 调用
│   ├── types.ts             # TypeScript 类型定义
│   ├── locales.ts           # 多语言配置
│   ├── constants.ts         # 常量配置
│   ├── App.tsx              # 主应用组件
│   └── index.tsx            # 应用入口
├── public/                  # 静态资源
├── .env.local              # 环境变量（需自行创建）
├── package.json            # 项目配置
├── tsconfig.json           # TypeScript 配置
├── vite.config.ts          # Vite 配置
└── README.md               # 项目文档
```

## 🎨 使用指南

1. **输入出生信息**
   - 姓名（可选）
   - 性别
   - 出生日期（公历）
   - 出生时间
   - 出生地点

2. **确认八字排盘**
   - AI 自动计算真太阳时
   - 生成八字四柱
   - 计算大运起运岁数

3. **查看运势分析**
   - 100 年运势 K 线图
   - 六大维度详细分析
   - 流年详细点评

4. **导出报告**
   - 点击"保存 PDF 报告"按钮
   - 生成包含完整分析的 PDF 文件

## 🌐 支持的模型

- `gemini-2.0-flash-thinking-exp-01-21` (默认)
- `gemini-2.5-flash-thinking`
- `gemini-3-pro-preview-low`
- 其他兼容 Gemini/OpenAI 格式的模型

## 📝 开发说明

- 使用 `npm run dev` 启动开发服务器（支持热更新）
- 使用 `npm run build` 构建生产版本
- 使用 `npm run preview` 预览生产构建

## ⚠️ 注意事项

1. 本项目仅供娱乐和文化研究使用
2. 需要有效的 Gemini API Key 才能使用
3. API 调用会产生费用，请注意用量
4. 真太阳时计算基于地理位置，可能存在误差

## 📄 License

MIT License

## 👨‍💻 作者

@xiaoeen

---

<div align="center">

**Made with ❤️ by @xiaoeen**

⭐ Star this repo if you find it helpful!

</div>
