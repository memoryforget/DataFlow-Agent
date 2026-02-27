# DataFlow-Agent

<div align="center">

<img src="static/new_logo_bgrm.png" alt="DataFlow-Agent Logo" width="180"/>

[![DataFlow](https://img.shields.io/badge/DataFlow-OpenDCAI%2FDataFlow-0F9D58?style=flat-square&logo=github&logoColor=white)](https://github.com/OpenDCAI/DataFlow)
[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-Apache_2.0-2F80ED?style=flat-square&logo=apache&logoColor=white)](LICENSE)
[![GitHub Repo](https://img.shields.io/badge/GitHub-OpenDCAI%2FDataFlow--Agent-24292F?style=flat-square&logo=github&logoColor=white)](https://github.com/OpenDCAI/DataFlow-Agent)
[![Stars](https://img.shields.io/github/stars/OpenDCAI/DataFlow-Agent?style=flat-square&logo=github&label=Stars&color=F2C94C)](https://github.com/OpenDCAI/DataFlow-Agent/stargazers)

[Chinese](README-zh.md) | English

<a href="#-quickstart">
  <img alt="Quickstart" src="https://img.shields.io/badge/🚀-Quickstart-2F80ED?style=for-the-badge" />
</a>
<a href="https://OpenDCAI.github.io/DataFlow-Doc/">
  <img alt="Docs" src="https://img.shields.io/badge/📚-Docs-2D9CDB?style=for-the-badge" />
</a>
<a href="docs/contributing.md">
  <img alt="Contributing" src="https://img.shields.io/badge/🤝-Contributing-27AE60?style=for-the-badge" />
</a>

</div>

---

## 🔍 Project Overview

【Core Component of the <a href="https://github.com/OpenDCAI/DataFlow">DataFlow</a> Ecosystem】A state-driven, modular AI Agent framework that provides an extensible `Agent / Workflow / Tool` system for <a href="https://github.com/OpenDCAI/DataFlow">DataFlow</a>. It comes with a built-in CLI scaffold and visual pages, targeting "dataflow/operator orchestration" tasks (operator recommendation, pipeline generation/debugging, operator Q&A, web data collection, etc.).

---

## 🛠️ Feature Overview
The DataFlow Agent multi-functional platform (Gradio) includes 6 core feature modules:

- **PromptAgent Frontend**: Generate/optimize operator Prompt Templates for easy accumulation of reusable prompt repositories.
- **Op Assemble Line**: Quickly assemble Pipelines by selecting operators from the operator library, supporting debug and run.
- **Operator QA**: A dedicated Q&A assistant for operators/tools to quickly answer questions about usage, parameters, examples, etc.
- **Operator Write**: Generate custom operator code from natural language requirements, supporting in-page testing/debugging closed-loop.
- **Pipeline Rec**: Automatically generate executable Pipelines from task descriptions, supporting multi-round iterative optimization.
- **Web Collection**: Web data collection and structured transformation for the "data production → data governance/training data" link.

---

## 📋 Feature Details

### PromptAgent Frontend
Reuse existing operators to generate and iteratively optimize "operator Prompt Templates":
- Inputs: Support passing task descriptions, operator names (`op-name`), parameter lists, output formats, etc. (optional)
- Outputs: Generate directly reusable Prompt Templates or provide rewrite suggestions for easy accumulation in the prompt repository

### Op Assemble Line
Filter suitable operators from the operator library, quickly assemble them into executable Pipelines, and support end-to-end debugging and running:
- Operator Selection: Filter target operators by category to accurately match business requirements
- Parameter Configuration: Configure operator parameters in JSON format and add to the Pipeline queue
- One-click Run: Quickly execute the assembled Pipeline and support end-to-end effect verification

### Operator QA
A dedicated Q&A assistant for operators/tools to help quickly understand "how to use / what to use / what to note":
- Operator Recommendation: Intelligently recommend suitable operators based on user requirements
- Parameter Interpretation: Clearly explain operator input/output rules and the meaning of key parameters
- Usage Examples: Provide directly reusable code snippets and scenario-based usage cases

### Operator Write
Automatically generate DataFlow operator code from natural language requirements, supporting in-page testing/debugging closed-loop:
- Code Generation: Generate standard-compliant operator implementation code based on target descriptions and constraints
- Operator Matching: Align with existing operator specifications to facilitate inclusion of generated operators into the operator library
- Debug Verification: Execute operators directly in the page and view execution results, debugging information, and running logs

### Pipeline Rec
Automatically generate executable Pipelines from natural language task descriptions, supporting multi-round refinement:
- Pipeline Generation: Map natural language tasks to operator combinations and execution sequences, outputting Pipeline code/JSON
- Iterative Optimization: Perform secondary refinement based on the initial Pipeline to continuously improve pipeline adaptability
- Artifact Output: Full artifacts such as Pipeline code, JSON configuration, and execution logs

### Web Collection
Web data collection and structured transformation for the "data production → data governance/training data" link:
- Collection Configuration: Customize collection targets, data types, and collection scale
- Structured Transformation: Automatically collect and output structured results
- Result Viewing: Support viewing execution logs, data summaries, and structured output results

---

## 📊 Core Design

- **Unified State Model**: Organize multi-agent execution processes around state objects such as `MainState / DFState`, with traceable and reusable state transitions.
- **Agent Plug-inization**: Automatically discover/load Agents through a registration mechanism, enabling expansion of agent capabilities without modifying core code.
- **Workflow Orchestration**: Orchestrate nodes based on graph structures (GraphBuilder), supporting complex process nesting and tool call links.
- **Tool Management**: Uniquely inject pre-tools/post-tools through `ToolManager` to control tool permissions and execution boundaries.
- **Visual Pages**: Built-in Gradio multi-page interface covering high-frequency scenarios such as operators/pipelines/prompts/web collection, ready to use out of the box.
- **CLI Scaffold**: `dfa create` one-click generates templates for workflow/agent/gradio page/prompt/state, reducing development costs.

---

## 🚀 Quickstart

### 🔥 Quickstart with Google Colab
| Feature Name             | Colab Tutorial Link                                               |
| ------------------------ | ----------------------------------------------------------------- |
| PromptAgent Frontend     | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1cU5Eg6tuc7WVDG33tU9Wplza52e54kts?usp=sharing) |
| Op Assemble Line         | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1W3Wb1sTyea1xDAGmVu3Tyn7fcvrsppAp?usp=sharing) |
| Operator QA              | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1maDKWp-3zEQNScmL_S7MHUdUC1xyCIcK?usp=sharing) |
| Operator Write           | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1oTkwMNwxMFGAe9rNtYCC47CQ9HxsA0uH?usp=sharing) |
| Pipeline Rec             | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1MMJxRpfYi7Zd-jc_pyhvM1Y2WoQXOFcu?usp=sharing) |

### 🛠️ Environment Configuration and Installation

#### 1) Clone the Repository
```bash
git clone https://github.com/OpenDCAI/DataFlow-Agent
cd DataFlow-Agent
```

#### 2) Create a Virtual Environment
```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\\Scripts\\activate

# Or use conda
conda create -n myenv python=3.11
conda activate myenv
```

#### 3) Install Dependencies
Recommended for development/local debugging:
```bash
pip install -r requirements-data.txt
pip install -e .
```

### Launch UI (Gradio)
Load only the dataflow-related page set (recommended):
```bash
python gradio_app/app.py --page_set data
```

#### Page Entries
PromptAgent Frontend / Op Assemble Line / Operator QA / Operator Write / Pipeline Rec / Web Collection

#### Port and Address Configuration
- Port: Set via the environment variable `GRADIO_SERVER_PORT` or command line `--server_port` (default 7860)
- Listening Address: Set via `GRADIO_SERVER_NAME` (default `0.0.0.0`)

---

### CLI Usage
View CLI help:
```bash
dfa --help
```

#### Common Scaffold Commands
```bash
dfa create --agent_name my_agent   
dfa create --wf_name my_workflow   
dfa create --gradio_name my_page   
dfa create --prompt_name my_prompt  
dfa create --state_name my_state       
```

#### Generated File Locations (Convention)
- Workflow：`dataflow_agent/workflow/wf_<name>.py`
- Agent：`dataflow_agent/agentroles/common_agents/<name>_agent.py`
- Gradio Page：`gradio_app/pages/page_<name>.py`
- Prompt Template：`dataflow_agent/promptstemplates/resources/pt_<name>_repo.py`
- State：`dataflow_agent/states/<name>_state.py`

---

## Workflows
Workflows are located in `dataflow_agent/workflow/` with the filename convention `wf_*.py`. During system startup, it will attempt to automatically import and register workflows; if a workflow depends on missing external environments/packages, it will prompt in the log and skip the import.

View currently successfully registered workflows:
```bash
python - <<'PY'
from dataflow_agent.workflow import list_workflows
print(sorted(list_workflows()))
PY
```

Running Method (taking run_workflow as an example):
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

## Configuration and Environment Variables

### LLM Related
- `DF_API_URL`：LLM API Base URL (default `test`)
- `DF_API_KEY`：API Key (default `test`)
- `DATAFLOW_LOG_LEVEL`：Log level (default `INFO`)
- `DATAFLOW_LOG_FILE`：Log file (default `dataflow_agent.log`)

### Path Related (Optional)
`dataflow_agent/state.py` prioritizes obtaining paths through `dataflow.cli_funcs.paths.DataFlowPath`; if the external package is unavailable, it falls back to environment variables:
- `DATAFLOW_DIR`：Root path of the data directory (default repository root path)
- `DATAFLOW_STATICS_DIR`：Statics directory (default `./statics`)

---

## Documentation
### Online Documentation (Feature Overview)
Quickly learn about the 5 core feature modules of the DataFlow Agent platform by visiting:
[DataFlow Agent Official Documentation](https://OpenDCAI.github.io/DataFlow-Doc/)

### Development Documentation (Local Development)
To learn about the DataFlow Agent design architecture or conduct local development based on DataFlow Agent (e.g., developing custom `workflow`, `agent`, etc.), launch the local documentation site to view development guidelines:
```bash
mkdocs serve
```
Local Access Address: `http://127.0.0.1:8000/`

Documentation Configuration File: `mkdocs.yml`

---

## Project Structure
```
DataFlow-Agent/
├── dataflow_agent/          # Core framework code
├── gradio_app/              # Gradio Web interface
├── docs/                    # Documentation
├── static/                  # Static resources (README images, etc.)
├── script/                  # Script tools
└── tests/                   # Test cases
```

---

## Roadmap
| Feature | Status | Subfeatures |
| --- | --- | --- |
| 🔄 Easy-DataFlow (Data Governance Pipeline) | ✅ Done | Pipeline recommendation / Operator writing / Visual orchestration / Prompt optimization / Web collection |
| 🎨 Workflow Visual Editor (Drag-and-Drop) | 🚧 In Progress | Drag-and-drop interface / 5 Agent modes / 20+ preset nodes |
| 💾 Trace Data Export (Training Data) | 🚧 In Progress | JSON/JSONL format / SFT format / DPO format |

---

## Contributing
We welcome contributions in all forms!
- Submit Bugs / Feature Requests: https://github.com/OpenDCAI/DataFlow-Agent/issues
- Participate in Discussions: https://github.com/OpenDCAI/DataFlow-Agent/discussions
- Submit Code: https://github.com/OpenDCAI/DataFlow-Agent/pulls
- Contribution Guide: `docs/contributing.md`

---

## License
Apache-2.0, see `LICENSE`.

---

## Join the Community
- 📮 GitHub Issues：https://github.com/OpenDCAI/DataFlow-Agent/issues
- 🔧 GitHub Pull Requests：https://github.com/OpenDCAI/DataFlow-Agent/pulls
- 💬 Community Chat Group：Real-time communication with developers and contributors

<div align="center">
  <img src="static/team_wechat.png" alt="DataFlow-Agent Community WeChat Group" width="560"/>
  <br>
  <sub>Scan the QR code to join the DataFlow-Agent Community WeChat Group</sub>
</div>