# SLM Agentic Software Engineering
## Evaluating Multi-Agent LLM Workflows for Software Maintenance
## Overview

This project investigates whether a modular Multi-Agent Large Language Model (LLM) workflow can improve software maintenance tasks compared to a traditional single-LLM approach.
The work was completed as part of the **LLMs** course offered by **CCE, Indian Institute of Science**.

The project evaluates three different approaches:

- Baseline LLM
- Multi-Agent Workflow
- LoRA Fine-Tuned Model

using the same benchmark derived from real-world SWE-bench software maintenance tasks.

---

# Research Question

Can a modular Multi-Agent LLM system outperform a traditional single-LLM workflow for software maintenance tasks such as:

- Bug understanding
- Repository reasoning
- Code analysis
- Documentation generation
- Developer assistance

---

# Project Architecture

```

GitHub Issue
│
▼

Planner Agent

│

▼

Code Analysis Agent

│

▼

Reviewer Agent

│

▼

Documentation Agent

│

▼

Final Software Engineering Report

```

The project evaluates whether decomposing software maintenance into specialized collaborating agents produces higher-quality results than a single LLM prompt.

---

# Experimental Workflow

The complete workflow consists of eight Google Colab notebooks.

| Notebook | Description |
|-----------|-------------|
| Notebook 01 | SWE-bench exploration and repository analysis |
| Notebook 02 | Dataset preparation |
| Notebook 03 | Baseline LLM evaluation |
| Notebook 04 | Multi-Agent workflow implementation |
| Notebook 05 | Agent trace generation |
| Notebook 06 | LoRA fine-tuning using Unsloth |
| Notebook 07 | Model evaluation |
| Notebook 08 | Final 20-task comparative experiment |

---

# Technologies

- Python
- Google Colab
- Unsloth
- Hugging Face Transformers
- PEFT (LoRA)
- TRL
- Qwen 2.5 1.5B Instruct
- Pandas
- Matplotlib

---

# Dataset

The benchmark is derived from **SWE-bench** software engineering tasks.

Each evaluation instance contains:

- Repository
- GitHub Issue
- Base Commit
- Problem Statement

Training traces were generated using the Multi-Agent workflow.

---

# Models Evaluated

## 1. Baseline

Single prompt using Qwen 2.5 1.5B Instruct.

---

## 2. Multi-Agent Workflow

Four specialized agents collaborate sequentially.

- Planner Agent
- Code Analysis Agent
- Reviewer Agent
- Documentation Agent

---

## 3. Fine-Tuned Model

LoRA fine-tuned Qwen 2.5 1.5B model trained on generated software engineering traces.

---

# Experimental Results

| Model | Tasks | Avg Time (s) | Success | Keyword Coverage |
|-------|------:|-------------:|--------:|-----------------:|
| Baseline | 20 | 10.94 | 100% | 0.619 |
| Multi-Agent | 20 | 53.03 | 100% | **0.656** |
| Fine-Tuned | 20 | 11.51 | 100% | 0.525 |

## Key Findings

- Multi-Agent workflow generated the most comprehensive software engineering analyses.
- Multi-Agent achieved the highest keyword coverage among all evaluated systems.
- Fine-tuning maintained inference efficiency while producing consistent outputs.
- The Baseline model remained the fastest approach.
- The project demonstrates that modular task decomposition can improve software engineering reasoning at the cost of increased inference time.

---

# Repository Structure

```

notebooks/
outputs/
data/
fine_tuned_model/

```

---

# Reproducibility

Clone the repository:

```bash
git clone https://github.com/<username>/agentic-software-engineering-assistant.git
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run notebooks sequentially:

```
01 → 02 → 03 → 04 → 05 → 06 → 07 → 08
```

---

# Outputs

The project automatically generates:

- Baseline evaluation
- Multi-Agent evaluation
- Fine-Tuned evaluation
- Training history
- Comparison metrics
- Charts
- Final experiment report

---

# Future Work

Potential extensions include:

- Larger open-source language models (7B–14B)
- Automatic code retrieval with Retrieval-Augmented Generation (RAG)
- Repository embedding using FAISS
- Human evaluation with software developers
- SWE-bench Verified benchmark evaluation
- Automated pull request generation and validation
- Additional specialized agents (e.g., Test Generation, Security Review, Performance Analysis)

---

# Author

**GitHub:** CuriousTechNomad

---

# License

This project is released under the MIT License.
