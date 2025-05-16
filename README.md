# 🚀 Xianyu AutoAgent - 智能闲鱼客服机器人系统

[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/) [![Python Version](https://img.shields.io/badge/nodejs-18%2B-blue)](https://nodejs.org/zh-cn/) [![LLM Powered](https://img.shields.io/badge/LLM-powered-FF6F61)](https://platform.openai.com/)

专为闲鱼平台打造的AI值守解决方案，实现闲鱼平台7×24小时自动化值守，支持多专家协同决策、智能议价和上下文感知对话。 


## 🌟 核心特性

### 智能对话引擎
| 功能模块   | 技术实现            | 关键特性                                                     |
| ---------- | ------------------- | ------------------------------------------------------------ |
| 上下文感知 | 会话历史存储        | 轻量级对话记忆管理，完整对话历史作为LLM上下文输入            |
| 专家路由   | LLM prompt+规则路由 | 基于提示工程的意图识别 → 专家Agent动态分发，支持议价/技术/客服多场景切换 |

### 业务功能矩阵
| 模块     | 已实现                        | 规划中                       |
| -------- | ----------------------------- | ---------------------------- |
| 核心引擎 | ✅ LLM自动回复<br>✅ 上下文管理 | 🔄 情感分析增强               |
| 议价系统 | ✅ 阶梯降价策略                | 🔄 市场比价功能               |
| 技术支持 | ✅ 网络搜索整合                | 🔄 RAG知识库增强              |
| 运维监控 | ✅ 基础日志                    | 🔄 钉钉集成<br>🔄  Web管理界面 |

## 🎨效果图
<div align="center">
  <img src="./images/demo1.png" width="600" alt="客服">
  <br>
  <em>图1: 客服随叫随到</em>
</div>


<div align="center">
  <img src="./images/demo2.png" width="600" alt="议价专家">
  <br>
  <em>图2: 阶梯式议价</em>
</div>

<div align="center">
  <img src="./images/demo3.png" width="600" alt="技术专家"> 
  <br>
  <em>图3: 技术专家上场</em>
</div>

<div align="center">
  <img src="./images/log.png" width="600" alt="后台log"> 
  <br>
  <em>图4: 后台log</em>
</div>


## 🚴 快速开始

### 环境要求
- Python 3.8+
- NodeJS 18+

### 源码部署
```bash
1. 克隆仓库
git clone https://github.com/lgy1027/XianyuAutoAgent.git
cd xianyu-autoagent

2. 安装依赖
pip install -r requirements.txt

3. 配置环境变量
创建一个 `.env` 文件，包含以下内容，也可直接重命名 `.env.example` ：

OPENAI_API_KEY=your_api_key_here
COOKIES_STR=your_cookies_here
OPEN_URL=地址，不需要带/v1
MODEL_NAME=模型ID

COOKIES_STR自行在闲鱼网页端获取cookies

4. 创建提示词文件prompts/*_prompt.txt
默认提供四个模板，可自行修改

5. 运行主程序：
python main.py
```

### docker部署
docker镜像目前支持amd和arm架构

0、可直接使用镜像：liguoyu3564/xianyu:latest 或者通过下面步骤构建景象

1、构建镜像：docker build -t xianyu-agent:latest -f dockerfile .

3、创建.env文件，添加如下信息：
```
COOKIES_STR=
OPENAI_API_KEY=
OPEN_URL=地址，不需要带/v1
MODEL_NAME=模型ID
```
4、启动容器：docker compose up -d

### 自定义提示词

可以通过编辑 `prompts` 目录下的文件来自定义各个专家的提示词：

- `classify_prompt.txt`: 意图分类提示词
- `price_prompt.txt`: 价格专家提示词
- `tech_prompt.txt`: 技术专家提示词
- `default_prompt.txt`: 默认回复提示词

## 🤝 参与贡献

欢迎通过 Issue 提交建议或 PR 贡献代码，请遵循 [贡献指南](https://contributing.md/)


## 🧸特别鸣谢
本项目基于以下开源项目修改：
https://github.com/shaxiu/XianyuAutoAgent

感谢<a href="https://github.com/shaxiu/XianyuAutoAgent">@shaxiu</a>的技术支持


