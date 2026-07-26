<div align="center">

# [网腾无限AI - 智能简历优化与精修]

**[一个支持Approved终审盖戳与五种特色润色流派的 AI 简历润色与精修工具，具备深色玻璃拟态自适应交互与微信端 H5 体验]**

[Vue 3] · [TypeScript] · [Vite] · [Vanilla CSS] · [开源协议 MIT]

[![GitHub stars](https://img.shields.io/github/stars/WT-Agent/ai-jianli?style=social)](https://github.com/WT-Agent/ai-jianli)
[![GitHub license](https://img.shields.io/github/license/WT-Agent/ai-jianli)](https://github.com/WT-Agent/ai-jianli/blob/main/LICENSE)

[在线演示](#在线演示) · [快速启动](#快速启动) · [参与贡献](#参与贡献) · [支持一下](#支持一下)

</div>

## 关于我们

团队成员均来自 C9 等顶尖学府，在字节、腾讯、阿里的工程师组成，全职创业研发开源 AI 应用产品，让所有人感受 AI 的魅力。

本项目旨在为求职者、应届生以及有转行需求的人群提供结构化、高竞争力的简历精修方案。用户只需输入目标岗位与个人核心经历，AI 即可根据 STAR 法则（情境-任务-行动-结果）与量化产出思维，自动生成包括简历诊断、润色修改对比、简历金句和面试提警的精修方案。页面内置了支持物理发音的互动“Approved 简历优化印章”，协助求职者在简历优化时快速确认产出与投递落地。

**我们不搞概念，不卖课，只写能跑起来的代码。**

欢迎 Star、Fork、提 Issue，一起让这个项目变得更好用。

核心特性：
- **极简自适应交互**：提供毛玻璃质感的深色玻璃拟态自适应 Web 界面，高度适配移动端 H5 微信浏览器与 PC 体验。
- **Approved 简历终审印章 (Sign-off Stamp)**：基于前端 Web Audio API 动态合成敲击刻章音效，点击印章即可累积精修份数并伴随渐隐上升动画。
- **五大简历润色流派**：
  - **互联网大厂 STAR 风格**：用词犀利，强调增长、ROI、闭环、架构设计、高并发与从0到1的项目量化产出。
  - **传统国企稳健叙事**：文字严谨稳重，侧重多方协调、团队管理、合规规程与项目稳定交付。
  - **外企中英文双语简历**：段落精炼，提供地道精准的外企专业术语及中英对照翻译。
  - **跨行转岗突出优势**：挖掘沟通协作、项目管理等通用底层通用职能迁移能力，削弱行业特异性。
  - **刚毕业应届生零经历**：深挖校内项目、专业实验或社团经历的 STAR 包装，体现快速学习与积极主动性。
- **AI 简历科学度看板**：自动提取 AI 回复中的共识数据，以简洁的单轨进度条在前端直观展示业绩量化、STAR法则、岗位匹配、精炼程度和术语规范系数。
- **演示案例与分享卡片**：内置 30 条不同岗位的简历优化生成精彩演示样例，并支持一键卡片化截图分享。
- **一键零成本部署**：纯前端静态网页结构，支持零成本部署于 Vercel、GitHub Pages 或 CDN/OSS 静态托管服务。
- **安全开发代理**：本地开发支持使用个人 API 密钥发起代理请求，密钥由 Vite 服务器中转，无需担心前端泄露。
- **裂变解锁与留存**：内置微信朋友圈扫码分享拦截与额度重置机制，提升流量转化与留存。

## 快速启动

### 1. 克隆项目
```bash
git clone https://github.com/WT-Agent/ai-jianli.git
cd ai-jianli
```

### 2. 安装依赖
项目强制使用 pnpm 作为包管理器：
```bash
pnpm install
```

### 3. 配置本地开发环境变量
复制并修改环境变量配置文件：
```bash
cp .env.example .env
```
根据微应用的功能类型，在 `.env` 中配置您的开发者密钥：
- `DEEPSEEK_API_KEY`: 您的 DeepSeek 开发者 API 密钥（用于文本生成任务）
- `DASHSCOPE_API_KEY`: 您的通义千问/通义万相开发者 API 密钥（用于多模态与生图任务）

### 4. 启动本地开发服务
```bash
pnpm dev
```
启动成功后在浏览器访问控制台输出的地址即可。

### 5. 生产构建打包
```bash
pnpm build
```
打包后生成的 `dist` 目录即为纯静态网页资源，可直接上传部署。

## 脚手架集成说明

本模板由私有总控仓库 `ai.wuxian.xyz` 中的 `@wuxian/cli` 脚手架统一管理，支持以下批量运维操作：

### 初始化或更新单个子项目

```bash
node bin/cli.js ai-jianli
```

脚手架将自动：
1. 读取子仓库的 `README.md` 首行作为 Prompt 主题。
2. 注入 Vue 3 静态页面结构及标准配置文件。
3. 保留原有的 `.git` 配置与 `README.md`，不覆盖个性化内容。

### 批量同步所有子项目

```bash
node bin/cli.js all
```

将模板的最新变更（如 SSO 逻辑、额度控制）一键同步至全部 31 个子项目。

### Agent 配置维护接口

```bash
# 读取子项目配置
node bin/cli.js get ai-jianli

# 写入/更新配置（支持热更新 prompt、model、title、temperature 等）
node bin/cli.js set ai-jianli prompt "你是一个结合资深猎头、大厂HRD以及简历金牌规划师角色的智能简历优化专家..."
node bin/cli.js set ai-jianli model deepseek-chat
```

## 联系方式

- GitHub Issues: [提交反馈](https://github.com/WT-Agent/ai-jianli/issues)
- 邮箱: us@wuxian.xyz

## 打赏支持

如果本项目对您有帮助，欢迎请作者喝杯咖啡。您的支持是持续维护与更新的动力。

<div align="center">

**微信支付** | **支付宝**
:---:|:---:
<img src="./asset/tenpay.png" width="200" alt="微信支付"> | <img src="./asset/alipay.png" width="200" alt="支付宝">

</div>

## 版权与许可

本项目基于 MIT License 开源协议。

Copyright (c) 2026. All rights reserved.
