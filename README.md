# WorldCat eBooks Assistant

🚀 **WorldCat eBooks Assistant** 是一款为 WorldCat 详情页深度定制的 Tampermonkey（油猴）用户脚本。它可以自动从全网拉取并在页面无缝植入**豆瓣图书评分**、**高清封面**以及**四大电商（微信读书、京东、当当、多看）+ 喜马拉雅的数字资源直达链接**。

## ✨ 核心功能
*   **豆瓣数据集成**：根据 ISBN 自动查询并展示豆瓣评分，一目了然判断书籍质量。
*   **高清封面替换**：自动爬取 `isbnsearch.org` 或相关 API 的高清书籍封面，替换 WorldCat 默认的模糊占位图。
*   **电子书直达**：精准识别书籍信息，并实时检测各主流平台（微信读书、京东、当当、多看）是否有正版电子书。点亮对应平台图标，一键直达阅读/购买页面。
*   **有声书支持**：额外集成喜马拉雅有声书搜索，一键收听。
*   **优雅的 UI 植入**：采用不破坏原网页排版的方式，通过特征 DOM 选择器和 XPath 双重匹配，稳定地挂载在“外部資源”面板旁边，体验原生顺滑。

## 📥 安装指南

### 步骤 1：安装 Tampermonkey 插件
在安装脚本前，请确保您的浏览器已安装 Tampermonkey 插件：
- [Chrome 扩展商店](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo)
- [Edge 扩展商店](https://microsoftedge.microsoft.com/addons/detail/tampermonkey/iikmkjmpaadaobahmlepeloendndfphd)
- [Firefox 扩展商店](https://addons.mozilla.org/zh-CN/firefox/addon/tampermonkey/)

### 步骤 2：安装本脚本
点击下方链接，Tampermonkey 会自动弹出安装提示：
👉 **[点击这里安装 WorldCat eBooks Assistant](https://greasyfork.org/zh-CN/scripts/578724-worldcat-ebooks-assistant-api-v2-1)**
> *注意：请在发布后将上述链接替换为您仓库的真实 Raw 链接。*

## 🛠️ 技术原理
本脚本在页面加载完毕后：
1.  首先通过正则精准提取目标书籍的 `13位 / 10位 ISBN`。
2.  利用 `GM_xmlhttpRequest` 并发请求独立的数据代理 API (`api.youdianzishu.com`) 获取聚合的豆瓣/电子书数据。
3.  通过原生的 `DOMParser` 直接解析 `isbnsearch.org` 爬取全网最新高清封面，自动过滤坏链与 404 图片。
4.  根据检测结果动态渲染微件 UI（包含 Base64 加密的内联高品质图标）。

## 🌐 跨域请求许可说明
出于安全性考虑，首次运行时油猴可能会弹窗请求允许跨域连接 `api.youdianzishu.com` 和 `isbnsearch.org`。请点击**“总是允许”**，这是拉取外部评分和封面所必需的正常行为。

## 🤝 贡献与反馈
欢迎在 Issues 中提出您在使用中遇到的 BUG，或者提交 PR 优化逻辑。

## 📜 开源协议
MIT License
