---
layout: default
title: Domain-Aware Neurosymbolic Agent (DANA) Architecture for Industrial AI
nav_order: 80
parent: Exploring AI System Design
---

<!-- markdownlint-disable MD013 MD025 MD043 MD050 -->

# Domain-Aware Neurosymbolic Agent (DANA) Architecture for Industrial AI

> _arXiv Paper:_ [__DANA: Domain-Aware Neurosymbolic Agents for Consistency and Accuracy__](https://arxiv.org/abs/2410.02823)
>
> _Open-Source Implementation:_ Aitomatic's [__OpenSSA__](https://github.com/aitomatic/openssa) framework for small specialist agents

DANA is Aitomatic's agentic-AI architecture for solving complex, high-stakes problems
in industries like semiconductor, energy and finance,
where consistency, accuracy and deterministic outcomes are paramount.

DANA agents capture domain knowledge from experts and apply such knowledge to solve problems:

![DANA Architecture](DANA-Architecture.png)

By integrating domain-specific knowledge with neural and symbolic planning and reasoning,
DANA agents consistently deliver accurate solutions, often using much smaller models.

## Key Benefits of DANA

- __Consistent and Accurate Results__ for complex industrial problems
- __Scalable Expertise__ through AI agents incorporating deep domain knowledge from human experts
- __Economical and Efficient Computation__ thanks to usage of small models

## Performance Benchmarking on FinanceBench

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

![DANA Outperforms Current Agent Tools](DANA-Outperforms-Current-Agent-Tools.png)

## Industrial Use: Semiconductor Etching Advisor Example

Thanks to its consistency and accuracy, DANA is highly applicable to physical-industry workflows requiring that AI provide precise analyses and recommendations.

The semiconductor industry has many complex design and manufacturing processes which need careful calibration to achieve optimal technical and economic outcomes. Etching recipe formulation is one such intricate task: it involves dozens of machine parameters that affect key physical operations and chemical reactions. A recipe lacking in rigor would result in inefficient cycle times or expensive reliability and quality problems such as etch rate anomalies, mask erosion, pattern distortion, plasma instability and non-uniformity, which negatively impact yield. Hence, the formulation of feasible and optimal etching recipes requires deep domain expertise and time-consuming expert analyses. There is consequently a great need for scaling up and making more available the knowledge of scarce experts in this domain.

An Etching Advisor AI agent constructed with the DANA architecture and integrating [SemiKong](https://SemiKong.ai), a semiconductor industry-specific LLM pioneered by members of the AI Alliance's Foundation Models workgroup, is capable of high precision and relevance in etching recipe analyses and recommendations. This DANA-and-SemiKong-based Etching Advisor can provide operationally sound etching recipes, including pros-and-cons comparisons among feasible alternatives, thus helping process engineers save much analysis time and arrive at their final recipes more quickly. An example recommendation is presented below:

![Typical Recipe Analysis & Recommendation from DANA-and-SemiKong-based Semiconductor Etching Advisor](DANA-and-SemiKong-based-Semiconductor-Etching-Advisor-Recommendation.png)

A presentation on this is available on [YouTube](https://www.youtube.com/watch?v=1pUaIwyky9Y).

## Open-Source Implementation

Aitomatic's [OpenSSA](https://github.com/aitomatic/openssa) framework for small specialist agents
implements a variant of the DANA architecture,
employing Hierarchical Task Planning (HTP) for structuring programs
and Observe-Orient-Decide-Act Reasoning (OODAR) for executing such programs.

OpenSSA supports using [Llama](https://llama.com) as its primary open-source LM backend.
