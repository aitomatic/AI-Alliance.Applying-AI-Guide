---
layout: default
title: Domain-Aware Neurosymbolic Agent (DANA) Architecture for Industrial AI
nav_order: 80
parent: Exploring AI System Design
---

<!-- markdownlint-disable MD013 MD025 MD043 MD050 -->

# Domain-Aware Neurosymbolic Agent (DANA) Architecture for Industrial AI

> _arXiv Paper:_ __DANA: Domain-Aware Neurosymbolic Agents for Consistency and Accuracy__
>
> _Open-Source Implementation:_ Aitomatic's [__OpenSSA__](https://github.com/aitomatic/openssa) framework for small specialist agents

DANA is Aitomatic's agentic-AI architecture for solving complex, high-stakes problems
in industries like semiconductor, manufacturing and finance,
where consistency, accuracy and deterministic outcomes are essential.

DANA agents capture domain knowledge from experts and apply such knowledge to solve problems.

![DANA Architecture](DANA-Architecture.png)

By integrating domain-specific knowledge with neural and symbolic planning and reasoning,
DANA agents consistently deliver accurate solutions, often using much smaller models.

## Key Benefits of DANA

- __Consistent and Accurate Results__ for complex industrial problems
- __Scalable Expertise__ through AI agents incorporating deep domain knowledge from human experts
- __Economical and Efficient Computation__ thanks to usage of small models

## Performance Benchmarking

[FinanceBench](https://arxiv.org/abs/2311.11944) is a well-known financial-analysis benchmark dataset,
150 questions from which are [publicly available](https://github.com/patronus-ai/financebench)
and classified by Aitomatic into the following increasing difficulty levels:

- `0-RETRIEVE`: retrieve a single data point
- `1-COMPARE`: compare a small number of retrievable data points of the same type
- `2-CALC-CHANGE`: calculate relative change in same retrievable data point over time
- `3-CALC-COMPLEX`: calculate complex financial metrics involving multiple data points of different types
- `4-CALC-AND-JUDGE`: calculate complex financial metrics and judge their goodness/healthiness
- `5-EXPLAIN-FACTORS`: explain major driving factors behind a change
- `6-OTHER-ADVANCED`: answer an unusually tricky financial question

Armed with a first-class incorporation of domain expert knowledge and with powerful neurosymbolic planning and reasoning,
DANA agents achieve over-90% accuracy on FinanceBench, outperforming existing agent tools such as LangChain ReAct and OpenAI Assistant
in both accuracy and consistency:

![alt text](DANA-Outperforms-Current-Agent-Tools.png)

## Open-Source Implementation

Aitomatic's [OpenSSA](https://github.com/aitomatic/openssa) framework for small specialist agents
implements a variant of the DANA architecture,
employing Hierarchical Task Planning (HTP) for structuring programs
and Observe-Orient-Decide-Act Reasoning (OODAR) for executing such programs.

OpenSSA supports using [Llama](https://llama.com) as its primary open-source LM backend.
