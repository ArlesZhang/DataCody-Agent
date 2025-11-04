# DataCody Agent  
>**The Data Workflow Compiler for Data Engineers**

---

## Overview
**DataCody Agent** is an intelligent agent that automates and optimizes data workflows — from raw data ingestion to transformation and deployment — acting like a **compiler** for data engineering tasks.  
It converts high-level workflow descriptions into executable, efficient pipelines.

---

## Core Features
- **Workflow Compiler** — Translates data flow definitions into optimized DAGs (Directed Acyclic Graphs).  
- **AI-assisted Optimization** — Uses AI heuristics to suggest pipeline improvements.  
- **Multi-backend Support** — Integrates with Spark, Airflow, and DVC pipelines.  
- **Reproducible Builds** — Every data transformation is versioned and trackable.  
- **Declarative DSL** — Describe what you want, not how to run it.

## Tech stack

* **Core Languages:** Python, TypeScript/JavaScript
* **Agent Frameworks:** LangChain / LlamaIndex
* **Backend Services:** FastAPI, Uvicorn
* **Deployment/Containerization:** Docker
* **Frontend Interaction:** VS Code Extension API
* **Target Ecosystem:** dbt-core, Apache Airflow / Dagster

---

## Project Structure
```bash
datacody-agent/
├── src/                          # Agent 后端核心代码
│   ├── compiler/                 # 核心编译逻辑（Workflow Compiler Engine）
│   ├── dsl/                      # 编译后的领域特定语言/IR (例如：抽象的 dbt Task)
│   ├── agents/                   # AI 智能体推理与优化模块 (RAG 检索、LLM 工具调用逻辑)
│   ├── tools/                    # MCP 工具调度（如 dbt-core 解析器、Great Expectations 集成）
│   └── main.py                   # FastAPI 应用的启动入口
├── vsc_extension/                # VS Code 插件前端代码 (TypeScript/JavaScript) - 关键的 MVP 交付物
├── tests/                        # 单元测试与集成测试
├── configs/                      # 配置文件 (.env, LLM 参数, YAML 模板等) - 关键的工程化实践
├── data/                         # 示例 dbt 项目或测试数据
└── requirements.txt
└── README.md
````

## 快速启动 (待完成)

1.  **环境：** Clone 仓库，创建 Python 虚拟环境。
2.  **API Key：** 配置 LLM API Key 到 `.env` 文件。
3.  **运行后端：** `docker-compose up` (待编写) 或 `uvicorn src.main:app --reload`
4.  **安装插件：** 编译 `vsc_extension` 并安装到本地 VS Code。
5.  **Enjoy!** (待实现)  

---

## Installation

```bash
git clone https://github.com/ArlesZhang/DataCody-Agent.git
cd DataCody-Agent
pip install -r requirements.txt
```

---

## ▶️ Run Example

```bash
python src/main.py --config examples/sample_workflow.yaml
```

---

## Roadmap

* [ ] Define DSL for workflow description
* [ ] Implement core compiler engine
* [ ] Integrate AI optimization agent
* [ ] Add Airflow backend
* [ ] Release v0.1.0

---

## Author

**Arles Zhang**

> Building AI-powered compiler systems for data engineers.
> GitHub: [@arleszhang](https://github.com/arleszhang)

---

### **requirements.txt**

```txt
# Core dependencies By GPT5 
fastapi==0.115.0
uvicorn==0.30.0

# Data workflow & orchestration
pandas==2.2.3
pydantic==2.9.0
networkx==3.3

# ML & optimization
scikit-learn==1.5.2

# Version control & reproducibility
dvc==3.50.0

# Testing & linting
pytest==8.3.3
black==24.10.0
````

```txt
# DataCody Agent Backend Dependencies By Gemini

# Web Framework and Server
fastapi==0.110.0
uvicorn[standard]==0.27.1

# LLM & Agent Framework
langchain==0.1.13  # 或者 llama-index，选择其一
pydantic==2.6.4    # 用于结构化输出 (JSON Schema)

# LLM Provider (假设使用 OpenAI)
openai==1.14.3
# 如果使用其他模型，例如 Claude:
# anthropic==0.23.1

# Data Engineering Tooling (用于解析 dbt 相关文件)
pyyaml==6.0.1
dbt-core==1.7.0  # 用于理解 dbt 的依赖结构和解析器

# 环境和调试
python-dotenv==1.0.1

# ------------------------------
# 可选依赖 (后续迭代时加入)
# ------------------------------
# 数据库/向量库 (用于 RAG 记忆)
# chromadb==0.4.24
# duckdb==0.10.1

# 分布式计算 (Spark集成)
# pyspark==3.5.0

# 文件操作/AST解析
# typed-ast==1.5.5

