# DataFlow-Agent

<div align="center">

<img src="static/new_logo_bgrm.png" alt="DataFlow-Agent Logo" width="180"/>

[![DataFlow](https://img.shields.io/badge/DataFlow-OpenDCAI%2FDataFlow-0F9D58?style=flat-square&logo=github&logoColor=white)](https://github.com/OpenDCAI/DataFlow)
[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-Apache_2.0-2F80ED?style=flat-square&logo=apache&logoColor=white)](LICENSE)
[![GitHub Repo](https://img.shields.io/badge/GitHub-OpenDCAI%2FDataFlow--Agent-24292F?style=flat-square&logo=github&logoColor=white)](https://github.com/OpenDCAI/DataFlow-Agent)
[![Stars](https://img.shields.io/github/stars/OpenDCAI/DataFlow-Agent?style=flat-square&logo=github&label=Stars&color=F2C94C)](https://github.com/OpenDCAI/DataFlow-Agent/stargazers)

中文 | [English](README.md)

<a href="#-快速开始">
  <img alt="Quickstart" src="https://img.shields.io/badge/🚀-快速开始-2F80ED?style=for-the-badge" />
</a>
<a href="https://OpenDCAI.github.io/DataFlow-Doc/">
  <img alt="Docs" src="https://img.shields.io/badge/📚-文档-2D9CDB?style=for-the-badge" />
</a>
<a href="docs/contributing.md">
  <img alt="Contributing" src="https://img.shields.io/badge/🤝-参与贡献-27AE60?style=for-the-badge" />
</a>

</div>

---

## 🔍 项目概述

【<a href="https://github.com/OpenDCAI/DataFlow">DataFlow</a> 生态核心组件】一个基于状态驱动（State-driven）的模块化 AI Agent 框架，为 <a href="https://github.com/OpenDCAI/DataFlow">DataFlow</a> 提供可扩展的 `Agent / Workflow / Tool` 体系，并内置 CLI 脚手架与可视化页面，面向“数据流/算子编排”类任务（算子推荐、管线生成/调试、算子问答、网页采集等）。

---

## 🛠️功能概览
DataFlow Agent 多功能平台（Gradio）包含 6 个核心功能模块：

- **PromptAgent Frontend**：生成/优化算子 Prompt Template，便于沉淀可复用的提示词仓库。
- **Op Assemble Line**：从算子库选择算子快速拼装 Pipeline，支持调试运行。
- **Operator QA**：算子/工具专属问答助手，快速解答用法、参数、示例等问题。
- **Operator Write**：从自然语言需求生成自定义算子代码，支持页面内测试/调试闭环。
- **Pipeline Rec**：从任务描述自动生成可执行 Pipeline，支持多轮迭代优化。
- **Web Collection**：网页数据采集与结构化转换，面向数据生产/治理链路。

---

## 📋 功能详情

### PromptAgent Frontend
复用现有算子，面向“算子 Prompt Template”开展生成与迭代优化：
- 输入：支持传入任务描述、算子名称（op-name）、参数列表、输出格式等（可选）
- 输出：生成可直接复用的 Prompt Template，或提供改写建议，便于沉淀到提示词仓库中

### Op Assemble Line
从算子库中筛选适配算子，快速拼装为可执行 Pipeline，并支持全流程调试运行：
- 算子选择：按分类筛选目标算子，精准匹配业务需求
- 参数配置：以 JSON 格式配置算子参数，并加入 Pipeline 队列
- 一键运行：快速执行拼装后的 Pipeline，支持端到端效果验证

### Operator QA
面向算子/工具的专属问答助手，帮助快速理解“怎么用 / 用什么 / 注意什么”：
- 算子推荐：根据用户需求智能推荐适配的算子
- 参数解读：清晰解释算子输入/输出规则及关键参数含义
- 用法示例：提供可直接复用的代码片段与场景化使用案例

### Operator Write
从自然语言需求自动生成 DataFlow 算子代码，支持页面内测试/调试闭环：
- 代码生成：基于目标描述与约束条件，生成符合规范的算子实现代码
- 算子匹配：对齐已有算子规范，便于生成的算子纳入算子库
- 调试验证：在页面内直接执行算子，查看执行结果、调试信息与运行日志

### Pipeline Rec
从自然语言任务描述自动生成可执行 Pipeline，并支持多轮 refine：
- 管线生成：将自然语言任务映射为算子组合与执行顺序，输出 Pipeline 代码/JSON
- 迭代优化：基于初始 Pipeline 做二次 refine，持续提升管线适配性
- 产物输出： Pipeline 代码、JSON 配置、执行日志等全量产物

### Web Collection
网页数据采集与结构化转换，面向“数据生产 → 数据治理/训练数据”链路：
- 采集配置：自定义采集目标、数据类型与采集规模
- 结构化转换：自动采集并输出结构化结果
- 结果查看：支持查看执行日志、数据摘要与结构化输出结果

---

## 📊核心设计

- **统一状态模型**：围绕 `MainState / DFState` 等状态对象组织多智能体执行过程，状态流转可追溯、可复用。
- **Agent 插件化**：通过注册机制自动发现/加载 Agent，无需修改核心代码即可扩展智能体能力。
- **Workflow 编排**：基于图结构（GraphBuilder）编排节点，支持复杂流程嵌套与工具调用链路。
- **工具管理**：通过 `ToolManager` 统一注入 pre-tools/post-tools，管控工具权限与执行边界。
- **可视化页面**：内置 Gradio 多页面，覆盖算子/管线/提示词/网页采集等高频场景，开箱即用。
- **CLI 脚手架**：`dfa create` 一键生成 workflow/agent/gradio page/prompt/state 等模板，降低开发成本。

---

## 🚀 快速开始

### 🔥 用Google Colab快速开始
| 功能名称             | Colab 教程链接                                               |
| -------------------- | ------------------------------------------------------------ |
| PromptAgent Frontend | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1cU5Eg6tuc7WVDG33tU9Wplza52e54kts?usp=sharing) |
| Op Assemble Line     | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1W3Wb1sTyea1xDAGmVu3Tyn7fcvrsppAp?usp=sharing) |
| Operator QA          | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1maDKWp-3zEQNScmL_S7MHUdUC1xyCIcK?usp=sharing) |
| Operator Write       | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1oTkwMNwxMFGAe9rNtYCC47CQ9HxsA0uH?usp=sharing) |
| Pipeline Rec         | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1MMJxRpfYi7Zd-jc_pyhvM1Y2WoQXOFcu?usp=sharing) |

### 🛠️环境配置和安装

#### 1) 克隆仓库
```bash
git clone https://github.com/OpenDCAI/DataFlow-Agent
cd DataFlow-Agent
```

#### 2) 创建虚拟环境
```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\\Scripts\\activate

# 或使用 conda
conda create -n myenv python=3.11
conda activate myenv
```

#### 3) 安装依赖
开发/本地调试推荐：
```bash
pip install -r requirements-data.txt
pip install -e .
```


### 启动 UI（Gradio）
只加载数据流相关页面集合（推荐）：
```bash
python gradio_app/app.py --page_set data
```

#### 页面入口
PromptAgent Frontend / Op Assemble Line / Operator QA / Operator Write / Pipeline Rec / Web Collection

#### 端口与地址配置
- 端口：通过环境变量 `GRADIO_SERVER_PORT` 或命令行 `--server_port` 设置（默认 7860）
- 监听地址：通过 `GRADIO_SERVER_NAME` 设置（默认 `0.0.0.0`）

---

### CLI 使用
查看 CLI 帮助：
```bash
dfa --help
```

#### 常用脚手架命令
```bash
dfa create --agent_name my_agent   
dfa create --wf_name my_workflow   
dfa create --gradio_name my_page   
dfa create --prompt_name my_prompt  
dfa create --state_name my_state       
```

#### 生成文件位置（约定）
- Workflow：`dataflow_agent/workflow/wf_<name>.py`
- Agent：`dataflow_agent/agentroles/common_agents/<name>_agent.py`
- Gradio Page：`gradio_app/pages/page_<name>.py`
- Prompt Template：`dataflow_agent/promptstemplates/resources/pt_<name>_repo.py`
- State：`dataflow_agent/states/<name>_state.py`

---

## 工作流（Workflows）
工作流位于 `dataflow_agent/workflow/`，文件名约定 `wf_*.py`。系统启动时会尝试自动导入并注册工作流；若某个工作流依赖的外部环境/包缺失，会在日志中提示并跳过导入。

查看当前成功注册的工作流：
```bash
python - <<'PY'
from dataflow_agent.workflow import list_workflows
print(sorted(list_workflows()))
PY
```

运行方式（以 run_workflow 为例）：
```bash
python - <<'PY'
import asyncio
from dataflow_agent.workflow import run_workflow
from dataflow_agent.state import MainState

async def main():
    state = MainState()
    out = await run_workflow("operator_qa", state)
    print(out)

asyncio.run(main())
PY
```

---

## 配置与环境变量

### LLM 相关
- `DF_API_URL`：LLM API Base URL（默认 `test`）
- `DF_API_KEY`：API Key（默认 `test`）
- `DATAFLOW_LOG_LEVEL`：日志级别（默认 `INFO`）
- `DATAFLOW_LOG_FILE`：日志文件（默认 `dataflow_agent.log`）

### 路径相关（可选）
`dataflow_agent/state.py` 优先通过 `dataflow.cli_funcs.paths.DataFlowPath` 获取路径；若外部包不可用，回退到环境变量：
- `DATAFLOW_DIR`：数据目录根路径（默认仓库根路径）
- `DATAFLOW_STATICS_DIR`：静态目录（默认 `./statics`）

---

## 文档
### 线上文档（功能速览）
快速了解 DataFlow Agent 平台的核心功能模块，可直接访问：  
[DataFlow Agent 官方文档](https://OpenDCAI.github.io/DataFlow-Doc/)

### 开发文档（本地开发）
若需了解DataFlow Agent 设计架构或基于 DataFlow Agent 进行本地开发（如开发自定义 `workflow`、`agent` 等），可启动本地文档站点查看开发指南：
```bash
mkdocs serve
```
本地访问地址：`http://127.0.0.1:8000/`

文档配置文件：`mkdocs.yml`

---

## 项目结构
```
DataFlow-Agent/
├── dataflow_agent/          # 核心框架代码
├── gradio_app/              # Gradio Web 界面
├── docs/                    # 文档
├── static/                  # 静态资源（README 图片等）
├── script/                  # 脚本工具
└── tests/                   # 测试用例
```

---

## Roadmap
| 功能 | 状态 | 子功能 |
| --- | --- | --- |
| 🔄 Easy-DataFlow（数据治理管线） | ✅ 已完成 | 管线推荐 / 算子编写 / 可视化编排 / Prompt 优化 / Web 采集 |
| 🎨 Workflow 可视化编辑器（拖拽式） | 🚧 开发中 | 拖拽界面 / 5 种 Agent 模式 / 20+ 预设节点 |
| 💾 轨迹数据导出（训练数据） | 🚧 开发中 | JSON/JSONL 格式 / SFT 格式 / DPO 格式 |

---

## 贡献
我们欢迎所有形式的贡献！
- 提交 Bug / 功能建议：https://github.com/OpenDCAI/DataFlow-Agent/issues
- 参与讨论：https://github.com/OpenDCAI/DataFlow-Agent/discussions
- 提交代码：https://github.com/OpenDCAI/DataFlow-Agent/pulls
- 贡献指南：`docs/contributing.md`

---

## License
Apache-2.0，见 `LICENSE` 。

---

## 加入社区
- 📮 GitHub Issues：https://github.com/OpenDCAI/DataFlow-Agent/issues
- 🔧 GitHub Pull Requests：https://github.com/OpenDCAI/DataFlow-Agent/pulls
- 💬 社区交流群：与开发者和贡献者实时交流

<div align="center">
  <img src="static/team_wechat.png" alt="DataFlow-Agent 社区微信群" width="560"/>
  <br>
  <sub>扫码加入 DataFlow-Agent 社区微信群</sub>
</div>
