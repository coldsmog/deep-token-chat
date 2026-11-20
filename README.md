# deep-token-chat

当 DeepSeek 网页端（C 端）触发额度限制时，本项目允许你填入自己的开发者 API Token，在熟悉的网页对话界面中继续与模型对话。

本项目是一个**纯前端、本地运行**的轻量工具：不依赖后端、不上传你的密钥到任何第三方服务器，所有请求由你的浏览器直接发往 DeepSeek API。

当然，理论上也适用于兼容DeepSeek API的其他模型，请自行尝试。

---

## 🚀 快速开始

本项目是单个 HTML 文件，无需构建、无需安装依赖。

1. 下载或克隆仓库，获取deekseek-chat.html
2. 直接双击打开html, 应该会跳转浏览器打开。若无，请使用你喜欢的浏览器打开。
3. 点击右上角 **设置**，填入你的 DeepSeek 开发者 API Token（`sk-` 开头）
4. 开始对话
   
<img width="1036" height="510" alt="主页面" src="https://github.com/user-attachments/assets/26d85148-b72e-4087-b243-f1356154a92e" />
<img width="1059" height="513" alt="API 设置" src="https://github.com/user-attachments/assets/3d14b736-0f6b-484e-8b34-80fae6646a8d" />

> API Token 可以在 [DeepSeek 开放平台](https://platform.deepseek.com/)
> 获取与充值。用量与扣费以平台账单为准。

---

## ⚠️ 重要警告（请务必阅读）

1. **API Key 会暴露在前端。**
   本项目为纯前端架构，你的 API Key 会存在于浏览器中（内存 / localStorage / 网络请求），任何能访问该页面的人都可以通过开发者工具读取到它。
2. **请勿将本项目部署到公网**
3. **仅限个人学习与研究使用。**
   若你需要一个可公开访问、多用户可用的服务，请使用 DeepSeek官方 API 并自行搭建带鉴权与密钥托管的后端。
4. **请遵守 DeepSeek 的服务条款。**
   API 使用与网页端使用适用不同的条款，使用者需自行确保使用方式合规，并自行承担相关风险（包括账号限制、扣费等）。
5. **本项目与 DeepSeek 官方无关。**
   项目名称、界面与官方产品无任何关联，不代表官方立场。
6. 作者不对因使用本项目导致的任何直接或间接损失负责。

---

## 📖 功能

- 🖥️ **纯前端**：单个 HTML 即可运行，无需后端服务
- 🔑 **自带密钥**：Token 仅保存在你的浏览器本地（localStorage）
- 💬 **多会话**：左侧会话列表，可切换 / 删除 / 新建
- 🧠 **深度思考**：可切换是否先输出思维链（reasoning）
- 🌐 **智能搜索**：可开启联网搜索与链接阅读工具
- 🎨 **Markdown 渲染**：代码块、表格、引用等（marked + DOMPurify 净化）
- 📱 **响应式布局**：窄屏自动收起侧边栏

---

## ⚙️ 设置项说明

| 设置项 | 说明 |
| --- | --- |
| API Key | 你的 DeepSeek 开发者 Token，仅保存在本地浏览器 |
| 模型 | 可选的 DeepSeek 模型（详见下方「已知限制」） |
| Base URL | 默认 `https://api.deepseek.com`，可修改为兼容端点 |
| 思考模式 | 启用后先输出思维链；关闭则直接回答 |
| 思考强度 | `high`（默认）/ `max`（复杂 Agent 场景） |
| temperature | 仅关闭思考模式时生效 |
| 最大输出 tokens | 输出长度上限 |
| 联网搜索 | 声明联网搜索 / 链接阅读工具 |
| 系统提示词 | 可选的 system prompt |

以上参数依据 **DeepSeek 官方 API 文档 2026年11月 版**
（[链接](https://api-docs.deepseek.com/)）。若官方后续调整字段名
或取值，本项目可能失效，需自行适配。

---

## 🧱 已知限制

- **模型名随官方版本变化。** 代码中的模型下拉项仅作为示例，
  请以 [DeepSeek 官方文档](https://api-docs.deepseek.com/) 当前
  提供的模型名为准；填错会返回 `400` 或 `404`。
- **参数名可能随官方版本变化。** 诸如 `thinking`、`reasoning_effort`、
  `server_tool_calls` 等字段依赖官方实现，官方变更后可能失效。
- **无「停止生成」按钮（当前版本）。** 如需中止回复，请刷新页面。
  欢迎提 PR 补充。
- **无持久化加密。** localStorage 中的 Key 与对话均为明文，请勿在
  公共设备上使用。

---

## 🔒 隐私

- 你的 API Key 仅保存在浏览器 localStorage 中，**不会上传到
  本项目作者的任何服务器**（本项目没有服务器）。
- 对话内容会发送至你填写的 Base URL（默认 DeepSeek API）以生成回复。
- 本项目不收集任何遥测数据、不使用任何分析脚本。

---

## 📄 License

[MIT](./LICENSE)

---

## 🙏 致谢

- 感谢 [DeepSeek](https://www.deepseek.com/) 提供优秀的模型与 API

**本项目与 DeepSeek 官方无关，仅为个人研究使用。**
