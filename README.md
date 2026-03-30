# 智能客服助手系统

基于 FastAPI + Vue3 打造的现代化智能客服解决方案，支持集成多种主流大语言模型（DeepSeek V3、Qwen2.5、Llama3 等），全面覆盖 Agent 与 RAG 技术在智能客服场景的核心应用需求。

## 核心功能

### 1. 智能对话问答
- **集成 DeepSeek V3 云端 API**
- **通过 Ollama 本地化部署各类模型**（Qwen2.5、Llama3 等）
- **模型热切换机制**

### 2. 深度推理能力
- **接入 DeepSeek R1 云端 API**
- **支持 Ollama 部署 Deepseek R1 系列模型**
- **推理模型灵活配置**

### 3. Ollama 性能压测工具
- 单次请求响应测试
- 高并发负载测试
- 服务器资源实时监控
- 测试报告自动生成

## 快速部署指南

### 步骤一：环境准备


## 快速启动

### 1. 安装依赖

```bash
# 创建虚拟环境
python -m venv .venv

# 激活虚拟环境
# Windows
.venv\Scripts\activate
# Linux/Mac
source .venv/bin/activate

# 安装依赖
pip install -r requirements.txt
```

### 2. 配置环境变量

复制 `env.example` 文件到 `llm_backend/.env` 文件中，并根据实际情况修改配置：

```env
# LLM 服务配置
CHAT_SERVICE=OLLAMA  # 或 DEEPSEEK
REASON_SERVICE=OLLAMA  # 或 DEEPSEEK

# Ollama 配置
OLLAMA_BASE_URL=http://localhost:11434
OLLAMA_CHAT_MODEL=deepseek-coder:6.7b
OLLAMA_REASON_MODEL=deepseek-coder:6.7b

# DeepSeek 配置（如果使用）
DEEPSEEK_API_KEY=your-api-key
DEEPSEEK_BASE_URL=https://api.deepseek.com/v1
DEEPSEEK_MODEL=deepseek-chat
```
### 3. 安装Mysql数据库并在 `.env` 文件中配置数据库连接信息

### 4. 启动服务

```bash
# 进入后端目录
cd llm_backend

# 启动服务（默认端口 9000）
python run.py

# 如果需要修改 IP 和端口，编辑 run.py 中的配置：
uvicorn.run(
    "main:app",
    host="0.0.0.0",  # 修改监听地址
    port=8000,       # 修改端口号
    access_log=False,
    log_level="error",
    reload=True
)
```

服务启动后可以访问：
- API 文档：http://localhost:8000/docs
- 前端界面：http://localhost:8000
