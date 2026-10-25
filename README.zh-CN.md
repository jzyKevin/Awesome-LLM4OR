# Awesome LLM4OR

![LLM4OR — Language Models × Operations Research](assets/llm4or-banner.png)

[English](README.md) | **简体中文**

面向**大语言模型与运筹优化（LLM4OR）**的论文、基准、数据、模型与工具合集。

**更新：2026-10-25 · 收录 235 篇论文。**

[综述](#surveys) · [入门路线](#start-here) · [研究方法](#research) · [基准评测](#benchmarks) · [开放资源](#resources)

<a id="contents"></a>

## 目录

- [综述（Surveys）](#surveys)（10 篇）
- [入门阅读路线](#start-here)
- [研究主线](#research)
  - [优化建模与代码生成](#modeling)（83 篇）
  - [模型验证、诊断与修复](#verification)（21 篇）
  - [直接解生成与优化决策](#direct-solving)（15 篇）
  - [启发式与算法自动设计](#algorithms)（54 篇）
  - [求解器组件增强与配置](#solver-enhancement)（17 篇）
- [Benchmarks 与评测](#benchmarks)（86 篇）
- [模型、数据与工具资源](#resources)
- [技术标签与专题索引](#techniques)
- [应用场景索引](#applications)
- [邻近研究](#adjacent)（9 篇）
- [作者与版本](#paper-info)
- [分类与阅读说明](#classification)
- [收录与贡献](#contributing)

<a id="surveys"></a>

## 综述（Surveys）

综述、系统性回顾、教程与研究框架。

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · ACM Computing Surveys | <a id="entry-lco2026review"></a>**Combinatorial Optimization Systematic Review**<br>Large Language Models for Combinatorial Optimization: A Systematic Review | 按 PRISMA 流程筛选 LLM 组合优化研究，归纳任务、模型架构、评测数据与应用领域。 | 综述 | <span title="DOI">[![DOI][badge-001]][resource-001]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-002]</span><br>[详情](#paper-lco2026review) |
| 2026 · ACM Computing Surveys | <a id="entry-liu2024systematic"></a>**LLM4AD Survey**<br>A Systematic Survey on Large Language Models for Algorithm Design | 从优化器、预测器、抽取器和设计器四种角色综述 LLM 算法设计。 | 综述 | <span title="arXiv">[![arXiv][badge-002]][resource-003]</span><br><span title="DOI">[![DOI][badge-001]][resource-004]</span><br><span title="官方资源库（相关）">[![官方资源库（相关）][badge-003]][resource-005]</span><br>[详情](#paper-liu2024systematic) |
| 2026 · MIPRO 2026 | <a id="entry-llmasopt2026"></a>**LLMs as Optimizers Survey**<br>Large Language Models as Optimizers: A Survey of Direct vs. Tool-Augmented Approaches and Their Performance Frontiers | 区分直接优化、调用工具优化和创造可复用工具三种范式，比较文献中的性能边界。 | 综述 | <span title="DOI">[![DOI][badge-001]][resource-006]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-007]</span><br>[详情](#paper-llmasopt2026) |
| 2026 · IEEE CIM（期刊记录） | <a id="entry-sysevo2025"></a>**LLMs for Evolutionary Optimization Survey**<br>A Systematic Survey on Large Language Models for Evolutionary Optimization: From Modeling to Solving | 从建模到求解梳理 LLM 与进化优化，区分直接优化、算法内部辅助与高层算法设计。 | 综述 | <span title="DOI">[![DOI][badge-001]][resource-008]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-009]</span><br><span title="Literature Collection（相关）">[![Literature Collection（相关）][badge-003]][resource-010]</span><br>[详情](#paper-sysevo2025) |
| 2026 · arXiv preprint | <a id="entry-smartgrid2026"></a>**Smart Grids Agentic AI Tutorial**<br>LLMs and Agentic AI Systems for Smart Grids: A Tutorial on Architectures and Applications | 综述智能电网 Agent 架构，并以充电、潮流和故障诊断等案例演示可信工具与显式检查。 | 综述 · 应用 | <span title="arXiv">[![arXiv][badge-002]][resource-011]</span><br><span title="Case-study Code">[![Case-study Code][badge-004]][resource-012]</span><br>[详情](#paper-smartgrid2026) |
| 2025 · AAAI 2025 | <a id="entry-wasserkrug2024manifesto"></a>**DOCP Research Manifesto**<br>Enhancing Decision Making Through the Integration of Large Language Models and Operations Research Optimization | 提出面向业务用户的优化 Copilot 愿景，梳理需求澄清、模型核验和求解效率等研究要求。 | 综述 · 基础 | <span title="Proceedings">[![Proceedings][badge-005]][resource-013]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-014]</span><br>[详情](#paper-wasserkrug2024manifesto) |
| 2025 · IJCAI 2025 Survey Track | <a id="entry-xiao2025survey"></a>**LLM4OR Survey**<br>A Survey of Optimization Modeling Meets LLMs: Progress and Future Directions | 综述优化建模全流程，分析并标记基准错误，提供清洗数据与评测门户。 | 综述 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-015]</span><br><span title="官方资源库（相关）">[![官方资源库（相关）][badge-003]][resource-016]</span><br><span title="Cleaned Benchmarks">[![Cleaned Benchmarks][badge-006]][resource-017]</span><br>[详情](#paper-xiao2025survey) |
| 2025 · arXiv preprint | <a id="entry-wang2025lor"></a>**LLMs in OR: Methods & Challenges**<br>Large Language Models in Operations Research: Methods, Applications, and Challenges | 按自动建模、辅助优化和直接求解梳理 LLM 在运筹学中的方法与应用。 | 综述 | <span title="arXiv">[![arXiv][badge-002]][resource-018]</span><br>[详情](#paper-wang2025lor) |
| 2025 · arXiv preprint | <a id="entry-abedi2025thinkmath"></a>**Teaching LLMs to Think Mathematically**<br>Teaching LLMs to Think Mathematically: A Critical Study of Decision-Making via Optimization | 结合系统综述与元分析，在新构造的计算机网络优化题中比较三种提示策略。 | 综述 · 评测分析 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-019]</span><br>[详情](#paper-abedi2025thinkmath) |
| 2024 · arXiv preprint | <a id="entry-yu2024deep"></a>**LLM–EA Automated Optimization Insights**<br>Deep Insights into Automated Optimization with Large Language Models and Evolutionary Algorithms | 梳理 LLM 与进化算法的自动优化框架，分析表示、变异、适应度和提示设计。 | 综述 | <span title="arXiv">[![arXiv][badge-002]][resource-020]</span><br>[详情](#paper-yu2024deep) |

[返回目录](#contents)

<a id="start-here"></a>

## 入门阅读路线

| 阅读目的 | 代表工作 | 阅读重点 |
|---|---|---|
| 了解领域全貌 | [LLM4OR Survey](#entry-xiao2025survey) → [LLM4AD Survey](#entry-liu2024systematic) | 分别了解优化建模全流程与自动算法设计的研究脉络。 |
| 理解任务与评测 | [NL4Opt](#entry-ramamonjison2023nl4opt) → [Mamo](#entry-huang2024mamo) → [EquivaMap](#entry-zhai2025equivamap) | 从实体抽取与形式化，到过程评价，再到变量映射与等价性检查。 |
| 从描述到模型与求解器 | [Chain-of-Experts](#entry-xiao2024coe) → [OptiMUS](#entry-teshnizi2024optimus) → [OptiGuide](#entry-li2023optiguide) | 比较专家协作、建模执行闭环和面向用户的交互式决策支持。 |
| 模型验证、诊断与修复 | [EquivaMap](#entry-zhai2025equivamap) → [SOVER / NLEquiv-150](#entry-bhattacharyya2026sover) → [ReLoop / RetailOpt-190](#entry-lian2026reloop) | 比较变量映射、形式化核验与扰动诊断，理解等价性检查和静默错误修复的适用条件。 |
| 直接解生成与优化决策 | [LLMCoSolver / E2E CO Solver](#entry-jiang2025e2eco) → [Starjob](#entry-abgaryan2025starjob) → [OPRO](#entry-yang2024opro) | 比较组合解生成、调度模型训练和基于反馈的候选决策搜索。 |
| 算法与启发式自动设计 | [FunSearch](#entry-romera2023funsearch) → [EoH](#entry-liu2024eoh) → [ReEvo](#entry-ye2024reevo) | 理解程序搜索、思路与代码协同演化，以及语言反思的作用。 |
| 求解器组件增强与配置 | [Cold-Start Separator Configuration](#entry-lawless2024cuts) → [SAGE / 原 EvoCut](#entry-yazdani2025evocut) → [AutoSAT](#entry-sun2024autosat) | 比较分离器配置、MILP 加速不等式发现与 SAT 启发式替换，理解组件改进如何接入既有求解器。 |

<a id="research"></a>

## 研究主线

按主要研究目标组织；跨任务条目须对相应任务有独立贡献。

<a id="code"></a>

<a id="modeling"></a>

### 优化建模与代码生成

从需求得到数学模型、结构化表示或求解器程序，包括交互建模、CP 与动态规划建模。

#### 数学形式化与建模要素抽取

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · ICML 2026 RLxF Workshop / arXiv | <a id="entry-autoor2026"></a>**AutoOR**<br>AutoOR: Scalably Post-training LLMs to Autoformulate Operations Research Problems | 从标准优化形式合成训练样本，并以执行反馈和课程式 RL 训练自然语言到模型的能力。 | 方法 · 数据 · 模型 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Paper">[![Paper][badge-007]][resource-021]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-022]</span><br>[详情](#paper-autoor2026) |
| 2026 · arXiv preprint | <a id="entry-coopa2026"></a>**COOPA**<br>COOPA: A Modular LLM Agent Architecture for Operations Research Problems | 迭代比较候选公式的置信度，追踪建模元素的来源，再路由至适用求解器 Agent。 | 方法 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | <span title="arXiv">[![arXiv][badge-002]][resource-023]</span><br><span title="Code">[![Code][badge-008]][resource-024]</span><br>[详情](#paper-coopa2026) |
| 2026 · AAAI 2026 | <a id="entry-xiao2026deepor"></a>**DeepOR**<br>DeepOR: A Deep Reasoning Foundation Model for Optimization Modeling | 以流程图引导长思维链合成和监督微调，再用求解器反馈构造奖励进行强化学习。 | 方法 · 数据 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) · [CoT / structured reasoning](#tech-cot) | <span title="Proceedings">[![Proceedings][badge-005]][resource-025]</span><br><span title="Code">[![Code][badge-008]][resource-026]</span><br><span title="官方种子与样例数据">[![官方种子与样例数据][badge-009]][resource-027]</span><br>[详情](#paper-xiao2026deepor) |
| 2026 · arXiv preprint | <a id="entry-zhang2026dschellm"></a>**DScheLLM**<br>DScheLLM: Enabling Dynamic Scheduling through a Fine-Tuned Dual-System Large language Model | 用求解器排程合成快／慢思考示范，LoRA 微调双系统 LLM 应对动态扰动。 | 方法 · 数据 · 模型 · 应用 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) · [CoT / structured reasoning](#tech-cot) | <span title="arXiv">[![arXiv][badge-002]][resource-028]</span><br>[详情](#paper-zhang2026dschellm) |
| 2026 · arXiv preprint | <a id="entry-he2026evoopt"></a>**EvoOpt-LLM**<br>EvoOpt-LLM: Evolving industrial optimization models with large language models | 以 7B 模型和 LoRA 支持工业 MILP 的模型构建、新业务约束注入与变量剪枝。 | 方法 · 模型 | [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-029]</span><br><span title="Code">[![Code][badge-008]][resource-030]</span><br>[详情](#paper-he2026evoopt) |
| 2026 · NeurIPS 2026（已接收，待出版） | <a id="entry-evooptigraph2026"></a>**EvoOptiGraph**<br>EvoOptiGraph: Weakness-Driven Coevolution via Graph-Based Structural Generation for Optimization Modeling | 以属性二部图演化结构多样的 MILP，结合编译、回译、SFT 与 RLVR 针对模型弱点更新训练分布。 | 方法 · 数据 · 模型 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Paper">[![Paper][badge-007]][resource-031]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-032]</span><br>[详情](#paper-evooptigraph2026) |
| 2026 · arXiv preprint | <a id="entry-mind2026"></a>**MIND**<br>Automated Optimization Modeling via a Localizable Error-Driven Perspective | 依据建模错误的局部性合成针对性训练问题，并用 DFPO 对困难样本做局部修订。 | 方法 · 数据 · 模型 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Preference optimization](#tech-preference) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-033]</span><br>[详情](#paper-mind2026) |
| 2026 · ICML 2026 | <a id="entry-optminer2026"></a>**Opt-Miner**<br>Opt-Miner: Empowering Information-Seeking Agent with Tree-Guided Data Synthesis for Optimization Modeling | 用树结构合成带知识缺口的优化任务，并以 R-GRPO 训练主动检索知识的建模 Agent。 | 方法 · 数据 · 模型 | [Agent](#tech-agent) · [RAG](#tech-rag) · [Data synthesis](#tech-data-synthesis) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-034]</span><br><span title="Reproduction Code（第三方）">[![Reproduction Code（第三方）][badge-008]][resource-035]</span><br><span title="Reproduction Results（第三方）">[![Reproduction Results（第三方）][badge-010]][resource-036]</span><br><span title="Demo（第三方）">[![Demo（第三方）][badge-011]][resource-037]</span><br>[详情](#paper-optminer2026) |
| 2026 · arXiv preprint | <a id="entry-optiagent2026"></a>**OptiAgent**<br>OptiAgent: End-to-End Optimization Modeling via Multi-Agent Iterative Refinement | 通过专门建模 Agent 与多层反馈循环，提取变量和约束并修正公式及可执行代码。 | 方法 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-038]</span><br>[详情](#paper-optiagent2026) |
| 2026 · ICLR 2026 | <a id="entry-wang2026orprm"></a>**OR-PRM**<br>OR-PRM: A Process Reward Model for Algorithmic Problem in Operations Research | 先清洗已有合成数据，基于 MCTS 和逐步检查构建 OR-ProcessQA，再训练用于建模推理的过程奖励模型。 | 方法 · 数据 · 模型 | [Data synthesis](#tech-data-synthesis) · [MCTS](#tech-mcts) · [SFT / distillation](#tech-sft) · [Preference optimization](#tech-preference) · [Process rewards](#tech-prm) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-039]</span><br>[详情](#paper-wang2026orprm) |
| 2026 · AAAI 2026 | <a id="entry-ding2026orr1"></a>**OR-R1**<br>OR-R1: Automating Modeling and Solving of Operations Research Optimization Problem via Test-Time Reinforcement Learning | 先用少量有标签数据 SFT，再以测试时 TGRPO 从未标注问题和求解一致性中学习。 | 方法 · 模型 | [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-040]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-041]</span><br><span title="Code">[![Code][badge-008]][resource-042]</span><br>[详情](#paper-ding2026orr1) |
| 2026 · Artificial Intelligence for Transportation | <a id="entry-yang2025orthought"></a>**ORThought / LogiOR**<br>ORThought: Benchmarking and automating logistics optimization modeling via structured LLM reasoning | 以专家建模原则指导结构化双 Agent 推理，并发布物流建模基准 LogiOR。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [CoT / structured reasoning](#tech-cot) | <span title="DOI">[![DOI][badge-001]][resource-043]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-044]</span><br><span title="Code">[![Code][badge-008]][resource-045]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-046]</span><br>[详情](#paper-yang2025orthought) |
| 2026 · ICML 2026 | <a id="entry-strategyaware2026"></a>**SAGE (Strategy-Aware Modeling)**<br>Strategy-Aware Optimization Modeling with Reasoning LLMs | 生成并筛选多策略建模示范，经 SFT 与 Segment-Weighted GRPO 兼顾公式正确性和求解效率。 | 方法 · 数据 · 模型 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-047]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-048]</span><br><span title="Code">[![Code][badge-008]][resource-049]</span><br><span title="SAGE SFT 100K">[![SAGE SFT 100K][badge-013]][resource-050]</span><br>[详情](#paper-strategyaware2026) |
| 2026 · International Journal of Production Research（2026 在线） | <a id="entry-li2025smilo"></a>**SMILO**<br>An LLM-powered MILP modelling engine for workforce scheduling guided by expert knowledge | 结合专家建模图、LLM 信息抽取与模板生成劳动力排班 MILP。 | 方法 · 应用 |  | <span title="DOI">[![DOI][badge-001]][resource-051]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-052]</span><br>[详情](#paper-li2025smilo) |
| 2025 · NeurIPS 2025 ScaleOpt Workshop / arXiv | <a id="entry-kong2025alphaopt"></a>**AlphaOPT**<br>AlphaOPT: Formulating Optimization Programs with Self-Improving LLM Experience Library | 通过求解器反馈提炼并演化可检索的建模经验库，无需更新 LLM 参数。 | 方法 | [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Paper">[![Paper][badge-007]][resource-053]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-054]</span><br><span title="Code">[![Code][badge-008]][resource-055]</span><br>[详情](#paper-kong2025alphaopt) |
| 2025 · ICML 2025 | <a id="entry-astorga2025autoformulation"></a>**Autoformulation**<br>Autoformulation of Mathematical Optimization Models Using LLMs | 使用 MCTS 搜索候选优化模型，通过符号剪枝与 LLM 部分模型估值引导探索。 | 方法 | [MCTS](#tech-mcts) | <span title="Proceedings">[![Proceedings][badge-005]][resource-056]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-057]</span><br><span title="Code">[![Code][badge-008]][resource-058]</span><br>[详情](#paper-astorga2025autoformulation) |
| 2025 · ACL 2025 | <a id="entry-wang2025bppsearch"></a>**BPP-Search / StructuredOR**<br>BPP-Search: Enhancing Tree of Thought Reasoning for Mathematical Modeling Problem Solving | 提出 BPP-Search，将束搜索、过程奖励模型和成对偏好机制结合到思维树推理中。 | 方法 · 基准 · 数据 | [Tree / beam search](#tech-tree-search) · [Preference optimization](#tech-preference) · [Process rewards](#tech-prm) · [CoT / structured reasoning](#tech-cot) | <span title="Proceedings">[![Proceedings][badge-005]][resource-059]</span><br><span title="Code">[![Code][badge-008]][resource-060]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-061]</span><br>[详情](#paper-wang2025bppsearch) |
| 2025 · arXiv preprint | <a id="entry-calm2025storm"></a>**CALM / STORM**<br>CALM Before the STORM: Unlocking Native Reasoning for Optimization Modeling | 用少量纠正提示修订推理轨迹，再经 SFT 与强化学习训练优化建模模型 STORM。 | 方法 · 数据 · 模型 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-062]</span><br>[详情](#paper-calm2025storm) |
| 2025 · arXiv preprint | <a id="entry-zhang2025optimind"></a>**OptiMind**<br>OptiMind: Teaching LLMs to Think Like Optimization Experts | 用按优化问题类别组织的专家错误分析指导训练与推理，减少 MILP 形式化常见错误。 | 方法 · 模型 | [SFT / distillation](#tech-sft) | <span title="arXiv">[![arXiv][badge-002]][resource-063]</span><br><span title="Code">[![Code][badge-008]][resource-064]</span><br><span title="Model">[![Model][badge-014]][resource-065]</span><br>[详情](#paper-zhang2025optimind) |
| 2025 · NeurIPS 2025 | <a id="entry-liu2025optitree"></a>**OptiTree**<br>OptiTree: Hierarchical Thoughts Generation with Tree Search for LLM Optimization Modeling | 利用层级建模树搜索，将复杂优化问题自适应分解为可复用的简单建模思路。 | 方法 | [Tree / beam search](#tech-tree-search) · [Memory](#tech-memory) | <span title="Proceedings">[![Proceedings][badge-005]][resource-066]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-067]</span><br><span title="Code">[![Code][badge-008]][resource-068]</span><br>[详情](#paper-liu2025optitree) |
| 2025 · arXiv preprint | <a id="entry-lima2025optitrust"></a>**OptiTrust**<br>Toward a Trustworthy Optimization Modeling Agent via Verifiable Synthetic Data Generation | 从带已知最优解的符号问题合成示范，用跨建模语言投票和分步推理训练建模 Agent。 | 方法 · 数据 · 模型 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-069]</span><br>[详情](#paper-lima2025optitrust) |
| 2025 · ICML 2025 | <a id="entry-lu2025optmath"></a>**OptMATH**<br>OptMATH: A Scalable Bidirectional Data Synthesis Framework for Optimization Modeling | 通过数学模型到问题数据再到自然语言的双向合成流程生成优化建模数据，并用正向建模和拒绝采样筛选。 | 方法 · 基准 · 数据 · 模型 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-070]</span><br><span title="Code">[![Code][badge-008]][resource-071]</span><br><span title="Model 7B">[![Model 7B][badge-015]][resource-072]</span><br><span title="Model 32B">[![Model 32B][badge-016]][resource-073]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-074]</span><br>[详情](#paper-lu2025optmath) |
| 2025 · Operations Research | <a id="entry-huang2025orlm"></a>**ORLM**<br>ORLM: A Customizable Framework in Training Large Models for Automated Optimization Modeling | 通过 OR-Instruct 合成数据训练优化领域模型，并提出工业基准 IndustryOR。 | 方法 · 基准 · 数据 · 模型 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-075]</span><br><span title="Journal">[![Journal][badge-017]][resource-076]</span><br><span title="Code">[![Code][badge-008]][resource-077]</span><br><span title="Model">[![Model][badge-014]][resource-078]</span><br><span title="IndustryOR">[![IndustryOR][badge-018]][resource-079]</span><br><span title="OR-Instruct-3K">[![OR-Instruct-3K][badge-019]][resource-080]</span><br>[详情](#paper-huang2025orlm) |
| 2025 · ICLR 2025 | <a id="entry-yang2025resocratic"></a>**ReSocratic / OptiBench**<br>OptiBench Meets ReSocratic: Measure and Improve LLMs for Optimization Modeling | 先合成数学形式与求解示范再逆向生成问题，配套 OptiBench 与 ReSocratic-29k。 | 方法 · 基准 · 数据 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-081]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-082]</span><br><span title="Code">[![Code][badge-008]][resource-083]</span><br>[详情](#paper-yang2025resocratic) |
| 2025 · Findings of EMNLP 2025 | <a id="entry-wu2025stepopt"></a>**Step-Opt**<br>Training LLMs for Optimization Modeling via Iterative Data Synthesis and Structured Validation | 逐步提高合成问题复杂度并结构化校验训练数据，再微调优化建模模型。 | 方法 · 数据 · 模型 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-084]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-085]</span><br><span title="Code">[![Code][badge-008]][resource-086]</span><br>[详情](#paper-wu2025stepopt) |
| 2024 · ICLR 2024 | <a id="entry-xiao2024coe"></a>**Chain-of-Experts**<br>Chain-of-Experts: When LLMs Meet Complex Operations Research Problems | 为不同 Agent 配置 OR 专长，由 conductor 组织前向思维构造与反向反思，完成复杂建模和编程。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) · [CoT / structured reasoning](#tech-cot) | <span title="Proceedings">[![Proceedings][badge-005]][resource-087]</span><br><span title="Code">[![Code][badge-008]][resource-088]</span><br>[详情](#paper-xiao2024coe) |
| 2024 · INFOR | <a id="entry-ahmed2024lm4opt"></a>**LM4OPT**<br>LM4OPT: Unveiling the potential of Large Language Models in formulating mathematical optimization problems | 先适配数学语料再微调 LP 建模任务，以带噪嵌入训练小模型，并比较零样本与单样本提示。 | 方法 · 模型 · 评测分析 | [SFT / distillation](#tech-sft) | <span title="DOI">[![DOI][badge-001]][resource-089]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-090]</span><br>[详情](#paper-ahmed2024lm4opt) |
| 2024 · Constraints | <a id="entry-dakle2023ner4opt"></a>**Ner4Opt**<br>Ner4Opt: named entity recognition for optimization modelling from natural language | 从优化问题文本识别变量、参数、目标和约束等实体，比较词法、语义、微调及语言模型方案。 | 方法 · 模型 · 基础 | [SFT / distillation](#tech-sft) | <span title="DOI">[![DOI][badge-001]][resource-091]</span><br><span title="Code">[![Code][badge-008]][resource-092]</span><br><span title="ner4opt-roberta-v1">[![ner4opt-roberta-v1][badge-020]][resource-093]</span><br><span title="ner4opt-roberta-v2">[![ner4opt-roberta-v2][badge-021]][resource-094]</span><br><span title="HF Demo（相关）">[![HF Demo（相关）][badge-011]][resource-095]</span><br>[详情](#paper-dakle2023ner4opt) |
| 2024 · EMNLP 2024 System Demonstrations | <a id="entry-ju2024ttg"></a>**To the Globe / TTG**<br>To the Globe (TTG): Towards Language-Driven Guaranteed Travel Planning | 将旅行需求译为符号表示，再由 MILP 求解器生成满足已编码约束的行程。 | 方法 · 应用 · 模型 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-096]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-097]</span><br>[详情](#paper-ju2024ttg) |
| 2023 · arXiv preprint | <a id="entry-alahakoon2023copilot"></a>**AI-Copilot for Business Optimisation**<br>Language Models for Business Optimisation with a Real World Case Study in Production Scheduling | 微调成本较低的 LLM 生成优化公式，并在真实生产排程案例中评估。 | 方法 · 数据 · 模型 · 应用 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-098]</span><br><span title="Training Data">[![Training Data][badge-022]][resource-099]</span><br><span title="Generated Formulations（相关）">[![Generated Formulations（相关）][badge-023]][resource-100]</span><br><span title="Industrial Case Data">[![Industrial Case Data][badge-024]][resource-101]</span><br><span title="Industrial Outputs（相关）">[![Industrial Outputs（相关）][badge-025]][resource-102]</span><br><span title="LPWP Evaluation Data（相关）">[![LPWP Evaluation Data（相关）][badge-026]][resource-103]</span><br>[详情](#paper-alahakoon2023copilot) |
| 2023 · ICLR 2023 DL4C Workshop / arXiv | <a id="entry-synth2023"></a>**CodeT5 Mathematical Program Synthesis**<br>Synthesis of Mathematical programs from Natural Language Specifications | 用 GPT-3 反向翻译扩充训练样本，微调 CodeT5，并依据 LP 规则重评和修正候选输出。 | 方法 · 模型 · 基础 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-104]</span><br>[详情](#paper-synth2023) |
| 2023 · arXiv preprint | <a id="entry-li2023synthesizing"></a>**Multi-stage MILP Synthesis**<br>Synthesizing mixed-integer linear programming models from natural language descriptions | 以变量识别、约束／目标分类和模板构建合成 MILP，并扩展 NL4Opt 的逻辑约束与二元变量问题。 | 方法 · 数据 | [SFT / distillation](#tech-sft) | <span title="arXiv">[![arXiv][badge-002]][resource-105]</span><br><span title="Modeling Data">[![Modeling Data][badge-027]][resource-106]</span><br>[详情](#paper-li2023synthesizing) |
| 2023 · arXiv preprint | <a id="entry-iflytek2023autoformulation"></a>**NL4Opt: Auto-Formulation Approach**<br>A Novel Approach for Auto-Formulation of Optimization Problems | 在 NL4Opt 竞赛的实体识别和公式生成两任务中，结合预训练、对抗训练、提示和模型集成。 | 方法 · 基础 | [SFT / distillation](#tech-sft) | <span title="arXiv">[![arXiv][badge-002]][resource-107]</span><br><span title="Code">[![Code][badge-008]][resource-108]</span><br>[详情](#paper-iflytek2023autoformulation) |
| 2023 · arXiv preprint; NL4Opt competition system | <a id="entry-wang2023opdnl4opt"></a>**OPD@NL4Opt**<br>OPD@NL4Opt: An ensemble approach for the NER task of the optimization problem | 对预训练语言模型使用差分学习率、对抗训练与集成，完成优化问题描述中的命名实体识别。 | 方法 · 基础 | [SFT / distillation](#tech-sft) | <span title="arXiv">[![arXiv][badge-002]][resource-109]</span><br><span title="竞赛结果（相关）">[![竞赛结果（相关）][badge-028]][resource-110]</span><br>[详情](#paper-wang2023opdnl4opt) |
| 2022 · EMNLP 2022 Industry | <a id="entry-ramamonjison2022augmenting"></a>**Auto-formulation (2022)**<br>Augmenting Operations Research with Auto-Formulation of Optimization Models From Problem Descriptions | 以受控生成从问题描述建议优化模型，并通过交互界面供用户校验与修改。 | 方法 · 基准 · 数据 · 基础 |  | <span title="Proceedings">[![Proceedings][badge-005]][resource-111]</span><br><span title="Code &amp; Data（NL4Opt）">[![Code & Data（NL4Opt）][badge-029]][resource-112]</span><br>[详情](#paper-ramamonjison2022augmenting) |

#### 求解器代码与领域语言

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-soliloquy2026"></a>**Agora-Opt**<br>From Soliloquy to Agora: Memory-Enhanced LLM Agents with Decentralized Debate for Optimization Modeling | 由多个 Agent 团队独立建模并开展结果驱动辩论，以读写记忆复用求解经验和分歧修订。 | 方法 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-113]</span><br><span title="Code &amp; Cleaned Data">[![Code & Cleaned Data][badge-029]][resource-114]</span><br>[详情](#paper-soliloquy2026) |
| 2026 · LION 19 / LNCS 15745（2026 出版） | <a id="entry-lporch2025"></a>**CHORUS**<br>CHORUS: Zero-shot Hierarchical Retrieval and Orchestration for Generating Linear Programming Code | 用分层文档切分、元数据检索和重排，为 LLM 生成 Gurobi LP 代码提供相关知识。 | 方法 · 基准 · 数据 | [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-115]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-116]</span><br>[详情](#paper-lporch2025) |
| 2026 · arXiv preprint | <a id="entry-canonicalir2026"></a>**CIR / R2C**<br>Canonical Intermediate Representation for LLM-based optimization problem formulation and code generation | 以规范中间表示编码复杂规则，再检索知识并生成约束实现。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-117]</span><br>[详情](#paper-canonicalir2026) |
| 2026 · arXiv preprint | <a id="entry-guan2026evom"></a>**EVOM**<br>Execution-Verified Reinforcement Learning for Optimization Modeling | 以求解器执行结果训练建模 LLM，并研究 Gurobi、OR-Tools 与 COPT 间的迁移。 | 方法 · 模型 | [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-118]</span><br>[详情](#paper-guan2026evom) |
| 2026 · arXiv preprint | <a id="entry-coevolve2026"></a>**EvoOR-Agent**<br>Co-evolving Agent Architectures and Interpretable Reasoning for Automated Optimization | 以 AOE 图表示建模—求解工作流，共同演化 Agent 架构与可解释推理路径。 | 方法 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-119]</span><br>[详情](#paper-coevolve2026) |
| 2026 · arXiv preprint | <a id="entry-liang2026leanllmopt"></a>**LEAN-LLM-OPT**<br>Large-Scale Optimization Model Auto-Formulation: Harnessing LLM Flexibility via Structured Workflow | 动态构建建模工作流并将数据处理交给工具，面向大规模优化和航空收入管理。 | 方法 · 基准 · 数据 · 应用 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-120]</span><br><span title="Code">[![Code][badge-008]][resource-121]</span><br>[详情](#paper-liang2026leanllmopt) |
| 2026 · arXiv preprint | <a id="entry-zhao2026miniopt"></a>**MiniOpt**<br>MiniOpt: Reasoning to Model and Solve General Optimization Problems with Limited Resources | 以结构化推理连接建模和代码生成，用分层 OptReward 同时反馈公式与解的质量。 | 方法 · 模型 | [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) · [CoT / structured reasoning](#tech-cot) | <span title="arXiv">[![arXiv][badge-002]][resource-122]</span><br><span title="Code">[![Code][badge-008]][resource-123]</span><br>[详情](#paper-zhao2026miniopt) |
| 2026 · ICML 2026 | <a id="entry-nemo2026"></a>**NEMO**<br>NEMO: Execution-Aware Optimization Modeling via Autonomous Coding Agents | 用自主编码 Agent 生成优化器与模拟器，再以交叉执行、经验复用和候选一致性改进建模。 | 方法 | [Agent](#tech-agent) · [Memory](#tech-memory) · [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-124]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-125]</span><br><span title="Evaluation Artifacts">[![Evaluation Artifacts][badge-030]][resource-126]</span><br>[详情](#paper-nemo2026) |
| 2026 · arXiv preprint | <a id="entry-xiu2026optgraph"></a>**OptGraph**<br>OptGraph: Large Language Models Enhanced Evolutionary Optimization Via Graph Retrieval-Augmented Generation | 将建模模式、公式、实现和错误修订组织成类型图，以邻域检索和运行轨迹更新支持优化建模。 | 方法 | [Agent](#tech-agent) · [Memory](#tech-memory) · [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-127]</span><br><span title="Code">[![Code][badge-008]][resource-128]</span><br>[详情](#paper-xiu2026optgraph) |
| 2026 · arXiv preprint | <a id="entry-dslmilp2026"></a>**OptiDSL**<br>Not All Problems Are Best Modeled as MILP: A DSL-Centric Framework for Flexible and Accurate Optimization Modeling | 将自然语言映射为领域 DSL，再接入专用求解器，避免所有问题强制采用 MILP。 | 方法 · 基准 · 数据 | [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-129]</span><br>[详情](#paper-dslmilp2026) |
| 2026 · Findings of EMNLP 2026 | <a id="entry-yang2026optskills"></a>**OptSkills**<br>OptSkills: Learning Generalizable Optimization Skills from Problem Archetypes via Cluster-Based Distillation | 按问题原型聚类，从成功建模轨迹提炼、检索并更新可复用的工作流技能。 | 方法 | [Agent](#tech-agent) · [Memory](#tech-memory) · [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-130]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-131]</span><br><span title="Code 1">[![Code 1][badge-031]][resource-132]</span><br><span title="Code 2">[![Code 2][badge-032]][resource-133]</span><br><span title="官方技能库（相关）">[![官方技能库（相关）][badge-033]][resource-134]</span><br>[详情](#paper-yang2026optskills) |
| 2026 · NeurIPS 2026（已接收，待出版） | <a id="entry-lu2026pearl"></a>**PEARL**<br>PEARL: Solver-in-the-Loop Interactive Optimization Modeling from Natural Language | 在多轮工具调用中执行、调试和修订优化模型，用求解器反馈训练交互建模策略。 | 方法 · 模型 | [Agent](#tech-agent) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-135]</span><br><span title="Proceedings">[![Proceedings][badge-005]][resource-136]</span><br><span title="Code">[![Code][badge-008]][resource-137]</span><br><span title="Model">[![Model][badge-014]][resource-138]</span><br>[详情](#paper-lu2026pearl) |
| 2026 · arXiv preprint | <a id="entry-rlvrpagents2026"></a>**RLEA**<br>Reinforcement Learning Enhanced LLM Agents for Complex Vehicle Routing Problems | 以 Soft Q-learning 训练轻量 Planner 调度 LLM Agent，结合记忆与检索完成复杂 VRP 建模。 | 方法 · 应用 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Memory](#tech-memory) · [RAG](#tech-rag) · [Auxiliary / NCO learning](#tech-auxiliary-learning) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-139]</span><br><span title="Appendix（相关）">[![Appendix（相关）][badge-034]][resource-140]</span><br>[详情](#paper-rlvrpagents2026) |
| 2026 · arXiv preprint | <a id="entry-sdrl2026"></a>**SDRL**<br>LLMs as Adaptive Meta-Solvers: Strategy-Diverse RL for Industrial-Scale Optimization | 用正确性门控的层次多样性奖励，训练模型在求解器、精确组合算法和启发式之间适配策略。 | 方法 · 数据 · 模型 | [Data synthesis](#tech-data-synthesis) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-141]</span><br><span title="Benchmark Inference">[![Benchmark Inference][badge-035]][resource-142]</span><br><span title="SDRL Qwen3 4B">[![SDRL Qwen3 4B][badge-036]][resource-143]</span><br>[详情](#paper-sdrl2026) |
| 2026 · arXiv preprint | <a id="entry-solid2026"></a>**SOLID**<br>Beyond Verified Answers: Solver-Informed Self-Distillation for Bootstrapping Operations Research Language Models | 从多次求解 rollout 的目标聚类构建伪参考，以求解器产物做无真值的自蒸馏后训练。 | 方法 · 模型 | [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-144]</span><br><span title="Code">[![Code][badge-008]][resource-145]</span><br><span title="SOLID-Qwen3">[![SOLID-Qwen3][badge-037]][resource-146]</span><br><span title="SOLID-StepORLM">[![SOLID-StepORLM][badge-038]][resource-147]</span><br>[详情](#paper-solid2026) |
| 2026 · ICLR 2026 | <a id="entry-zhou2026steporlm"></a>**StepORLM**<br>StepORLM: A Self-Evolving Framework With Generative Process Supervision For Operations Research Language Models | 让策略模型与生成式过程奖励模型共同演化，融合求解器结果反馈和全程评价。 | 方法 · 模型 | [LLM RL](#tech-llm-rl) · [Process rewards](#tech-prm) · [Execution / solver feedback](#tech-solver-feedback) · [CoT / structured reasoning](#tech-cot) | <span title="Proceedings">[![Proceedings][badge-005]][resource-148]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-149]</span><br><span title="Code">[![Code][badge-008]][resource-150]</span><br><span title="Policy 8B">[![Policy 8B][badge-039]][resource-151]</span><br><span title="GenPRM 8B">[![GenPRM 8B][badge-040]][resource-152]</span><br>[详情](#paper-zhou2026steporlm) |
| 2025 · ICLR 2025 | <a id="entry-jiang2025droc"></a>**DRoC**<br>DRoC: Elevating Large Language Models for Complex Vehicle Routing via Decomposed Retrieval of Constraints | 分解复杂 VRP 的约束并分别检索文档，动态选择 RAG 或自调试生成求解器程序。 | 方法 · 数据 · 应用 | [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-153]</span><br><span title="Proceedings">[![Proceedings][badge-005]][resource-154]</span><br><span title="Code">[![Code][badge-008]][resource-155]</span><br>[详情](#paper-jiang2025droc) |
| 2025 · ICLR 2025 | <a id="entry-jiang2025llmopt"></a>**LLMOPT**<br>LLMOPT: Learning to Define and Solve General Optimization Problems from Scratch | 通过五要素形式化、多指令微调与自纠错，提高多类优化问题的建模与代码生成泛化。 | 方法 · 模型 | [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-156]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-157]</span><br><span title="Code">[![Code][badge-008]][resource-158]</span><br><span title="Model">[![Model][badge-014]][resource-159]</span><br>[详情](#paper-jiang2025llmopt) |
| 2025 · NeurIPS 2025 | <a id="entry-xie2025murka"></a>**MURKA**<br>MURKA: Multi-Reward Reinforcement Learning with Knowledge Alignment for Optimization Tasks | 用多奖励强化学习与知识蒸馏对齐 Extractor、Solver、Checker 三类 Agent，支持从文本到可执行优化程序。 | 方法 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-160]</span><br>[详情](#paper-xie2025murka) |
| 2025 · arXiv preprint | <a id="entry-thind2025optimai"></a>**OptimAI**<br>OptimAI: Optimization from Natural Language Using LLM-Powered AI Agents | 以建模、规划、编码和代码批评角色协作求解，并用 UCB 调度调试与备选计划。 | 方法 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-161]</span><br>[详情](#paper-thind2025optimai) |
| 2025 · arXiv preprint | <a id="entry-zhang2025bwor"></a>**OR-LLM-Agent / BWOR**<br>OR-LLM-Agent: Automating Modeling and Solving of Operations Research Optimization Problems with Reasoning LLM | 将建模、代码生成与调试分配给推理 Agent，并提出 BWOR 评测集。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-162]</span><br><span title="Code">[![Code][badge-008]][resource-163]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-164]</span><br>[详情](#paper-zhang2025bwor) |
| 2025 · ACL 2025 Industry Track | <a id="entry-ormind2025"></a>**ORMind**<br>ORMind: A Cognitive-Inspired End-to-End Reasoning Framework for Operations Research | 以认知启发的角色协作、执行修复和反事实检查完成优化建模。 | 方法 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-165]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-166]</span><br><span title="Code">[![Code][badge-008]][resource-167]</span><br>[详情](#paper-ormind2025) |
| 2025 · NeurIPS 2025 | <a id="entry-chen2025sirl"></a>**SIRL**<br>Solver-Informed RL: Grounding Large Language Models for Authentic Optimization Modeling | 用求解器检查代码及 LP 实例，构造 RL 可验证奖励，并发布模型与修订评测数据。 | 方法 · 数据 · 模型 | [Data synthesis](#tech-data-synthesis) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-168]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-169]</span><br><span title="Code">[![Code][badge-008]][resource-170]</span><br><span title="Model Gurobi-7B">[![Model Gurobi-7B][badge-041]][resource-171]</span><br><span title="Model COPT-7B">[![Model COPT-7B][badge-042]][resource-172]</span><br><span title="Model Gurobi-32B">[![Model Gurobi-32B][badge-043]][resource-173]</span><br><span title="Model COPT-32B">[![Model COPT-32B][badge-044]][resource-174]</span><br><span title="修订评测集">[![修订评测集][badge-045]][resource-175]</span><br>[详情](#paper-chen2025sirl) |
| 2025 · NeurIPS 2025 | <a id="entry-solverllm2025"></a>**SolverLLM**<br>SolverLLM: Leveraging Test-Time Scaling for Optimization Problem via LLM-Guided Search | 用动态扩展的 MCTS 搜索公式和求解器代码，以提示和不确定性回传指导测试时探索。 | 方法 | [MCTS](#tech-mcts) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-176]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-177]</span><br>[详情](#paper-solverllm2025) |
| 2025 · arXiv preprint | <a id="entry-nl2ps2025"></a>**Validation-in-the-Loop Power Modeling**<br>From Natural Language to Solver-Ready Power System Optimization: An LLM-Assisted, Validation-in-the-Loop Framework | 通过领域提示、结构化 schema、可行性校验与迭代修复生成电力优化模型。 | 方法 · 应用 | [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-178]</span><br>[详情](#paper-nl2ps2025) |
| 2024 · NeurIPS 2024 MATH-AI Workshop | <a id="entry-deng2024cafa"></a>**CAFA**<br>CAFA: Coding as Auto-Formulation Can Boost Large Language Models in Solving Linear Programming Problem | 用紧凑提示直接生成调用优化求解器的 Python 程序，执行求解线性规划问题。 | 方法 | [Execution / solver feedback](#tech-solver-feedback) | <span title="Paper">[![Paper][badge-007]][resource-179]</span><br><span title="Code">[![Code][badge-008]][resource-180]</span><br>[详情](#paper-deng2024cafa) |
| 2024 · INFOR | <a id="entry-mostajabdaveh2024multiagent"></a>**Multi-Stage Modeling & Verification**<br>Optimization modeling and verification from problem specifications using a multi-agent multi-stage LLM framework | 分阶段从问题规格生成数学模型与 Zimpl 代码，并由多个 LLM Agent 交叉检查。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-181]</span><br>[详情](#paper-mostajabdaveh2024multiagent) |
| 2024 · ICML 2024 | <a id="entry-teshnizi2024optimus"></a>**OptiMUS**<br>OptiMUS: Scalable Optimization Modeling with (MI)LP Solvers and Large Language Models | 用模块化 Agent 完成 MILP 建模、代码生成、调试与评估，同时发布 NLP4LP。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-182]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-183]</span><br><span title="Code">[![Code][badge-008]][resource-184]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-185]</span><br>[详情](#paper-teshnizi2024optimus) |
| 2023 · arXiv preprint | <a id="entry-li2023power"></a>**LLMs for Power Engineering**<br>LLM-based Frameworks for Power Engineering from Routine to Novel Tasks | 对常规电力优化编程采用端到端流程，对新任务采用工程师参与的分解与代码合成。 | 方法 · 应用 | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-186]</span><br>[详情](#paper-li2023power) |

**相关工作：** [OptLLM](#entry-zhang2024optllm)

#### 交互建模与需求修改

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-conversation2026"></a>**Interactive Optimization Conversations**<br>Let's Have a Conversation: Designing and Evaluating LLM Agents for Interactive Optimization | 用带内部效用函数的决策 Agent 扮演利益相关者，评测多轮交互优化而非只看单次答案。 | 方法 · 数据 · 应用 | [Agent](#tech-agent) | <span title="arXiv">[![arXiv][badge-002]][resource-187]</span><br><span title="Code">[![Code][badge-008]][resource-188]</span><br>[详情](#paper-conversation2026) |
| 2026 · INFORMS Journal on Data Science | <a id="entry-chen2025optichat"></a>**OptiChat**<br>OptiChat: Bridging Optimization Models and Practitioners with Large Language Models | 用自然语言查询已有优化模型，支持不可行诊断、敏感性、what-if 和反事实解释。 | 方法 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-189]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-190]</span><br><span title="Code">[![Code][badge-008]][resource-191]</span><br>[详情](#paper-chen2025optichat) |
| 2025 · arXiv preprint | <a id="entry-askclarify2026"></a>**Ask, Clarify, Optimize**<br>Ask, Clarify, Optimize: Human-LLM Agent Collaboration for Smarter Inventory Control | 由 LLM 澄清库存需求并解释结果，把随机优化计算交给算法，以模拟经理测试交互。 | 方法 · 模型 · 应用 | [Agent](#tech-agent) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-192]</span><br>[详情](#paper-askclarify2026) |
| 2025 · FedCSIS 2025 · ACSIS 43 | <a id="entry-kaleta2025cdss"></a>**C-DSS**<br>Toward Conversational Decision Support Systems: Integrating LLMs in the Operations Research Methodology | 提出对话式决策支持架构，比较建模、AMPL 编码、RAG 和验证角色的不同组合。 | 方法 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-193]</span><br><span title="Proceedings">[![Proceedings][badge-005]][resource-194]</span><br>[详情](#paper-kaleta2025cdss) |
| 2024 · arXiv preprint | <a id="entry-jiao2024cityleo"></a>**City-LEO**<br>City-LEO: Toward Transparent City Management Using LLM with End-to-End Optimization | 通过对话限定优化范围，并结合预测与优化管理共享电动自行车运营。 | 方法 · 应用 | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-195]</span><br><span title="Data &amp; Code">[![Data & Code][badge-046]][resource-196]</span><br>[详情](#paper-jiao2024cityleo) |
| 2024 · NAACL 2024 Industry Track | <a id="entry-zhang2024optllm"></a>**OptLLM**<br>Solving General Natural-Language-Description Optimization Problems with Large Language Models | 通过多轮澄清、公式与代码转换、外部求解器和结果解释支持自然语言优化，并微调 Qwen。 | 方法 · 数据 · 模型 | [Agent](#tech-agent) · [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-197]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-198]</span><br><span title="MindOpt Trial (International)（相关）">[![MindOpt Trial (International)（相关）][badge-047]][resource-199]</span><br><span title="MindOpt Trial (CN)（相关）">[![MindOpt Trial (CN)（相关）][badge-048]][resource-200]</span><br>[详情](#paper-zhang2024optllm) |
| 2024 · arXiv preprint | <a id="entry-tang2024ragdys"></a>**RAGDyS**<br>Automated Conversion of Static to Dynamic Scheduler via Natural Language | 从既有静态排程模型出发，用检索增强生成按自然语言约束实施动态排程修改。 | 方法 · 应用 | [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-201]</span><br>[详情](#paper-tang2024ragdys) |
| 2023 · arXiv preprint | <a id="entry-li2023optiguide"></a>**OptiGuide**<br>Large Language Models for Supply Chain Optimization | OptiGuide 将自然语言 what-if 查询转成对现有优化程序的分析，解释供应链决策结果。 | 方法 · 应用 | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-202]</span><br><span title="Code">[![Code][badge-008]][resource-064]</span><br>[详情](#paper-li2023optiguide) |

#### 随机与鲁棒优化建模

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-robustreform2026"></a>**AutoREM / AutoRO-Bench**<br>Automated Reformulation of Robust Optimization via Memory-Augmented Large Language Models | 以失败经验记忆辅助鲁棒优化的确定性重构，并提出 AutoRO-Bench。 | 方法 · 基准 · 数据 | [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-203]</span><br>[详情](#paper-robustreform2026) |
| 2025 · arXiv preprint | <a id="entry-daopt2025"></a>**DAOpt / OptU**<br>DAOpt: Modeling and Evaluation of Data-Driven Optimization under Uncertainty with LLMs | 结合不确定性建模、多 Agent 与仿真环境，评估样本外可行性和稳健性。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-204]</span><br>[详情](#paper-daopt2025) |
| 2025 · arXiv preprint | <a id="entry-llmsuc2025"></a>**LLM-SUC**<br>Can Large Language Model Agents Balance Energy Systems? | 将 LLM Agent 与多场景随机机组组合结合，辅助高风电不确定性下的运行决策。 | 方法 · 应用 | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-205]</span><br><span title="Code">[![Code][badge-008]][resource-206]</span><br>[详情](#paper-llmsuc2025) |
| 2025 · arXiv preprint | <a id="entry-talebi2025stochastic"></a>**LLMs for Stochastic Modeling**<br>Large Language Model-Based Automatic Formulation for Stochastic Optimization Models | 以结构化提示生成机会约束与两阶段随机规划，并用软评分检查模型结构。 | 方法 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-207]</span><br><span title="Code">[![Code][badge-008]][resource-208]</span><br>[详情](#paper-talebi2025stochastic) |

#### 约束规划建模

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · LLM4Code 2026 Workshop @ ICSE | <a id="entry-cpagent2025"></a>**CP-Agent**<br>CP-Agent: Agentic Constraint Programming | 通过持久 IPython 内核和简短领域提示，执行并迭代修正约束模型。 | 方法 · 数据 | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-209]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-210]</span><br><span title="Author Coding Agent（相关）">[![Author Coding Agent（相关）][badge-049]][resource-211]</span><br><span title="Evaluation Archive v2">[![Evaluation Archive v2][badge-050]][resource-212]</span><br>[详情](#paper-cpagent2025) |
| 2026 · arXiv preprint | <a id="entry-cpsync2026"></a>**CP-SynC**<br>CP-SynC: Multi-Agent Zero-Shot Constraint Modeling in MiniZinc with Synthesized Checkers | 由建模、检查与选择 Agent 并行探索 MiniZinc 模型，并合成语义检查器聚合证据。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-213]</span><br><span title="Benchmark &amp; Evaluation">[![Benchmark & Evaluation][badge-051]][resource-214]</span><br>[详情](#paper-cpsync2026) |
| 2026 · arXiv preprint | <a id="entry-roy2026rag"></a>**RAG for Optimization & CP Modeling**<br>Optimization and Constraint Modeling using LLMs with a Retrieval Augmented Generation Process | 从 Text2Zinc 种子和角色描述合成 500 个问题，以检索示例辅助 LLM 生成优化与约束模型代码。 | 方法 · 数据 | [Data synthesis](#tech-data-synthesis) · [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-215]</span><br>[详情](#paper-roy2026rag) |
| 2026 · arXiv preprint | <a id="entry-text2model2026"></a>**Text2Model**<br>Text2Model: Modeling Copilots for Text-to-Model Translation | 提供面向 MiniZinc 的多种建模 Copilot、交互编辑器与在线排行榜。 | 方法 · 平台 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | <span title="arXiv">[![arXiv][badge-002]][resource-216]</span><br><span title="Code">[![Code][badge-008]][resource-217]</span><br><span title="Text2Zinc（复用）">[![Text2Zinc（复用）][badge-052]][resource-218]</span><br><span title="Editor（相关）">[![Editor（相关）][badge-053]][resource-219]</span><br><span title="Leaderboard（相关）">[![Leaderboard（相关）][badge-054]][resource-220]</span><br><span title="Python Package（相关）">[![Python Package（相关）][badge-055]][resource-221]</span><br>[详情](#paper-text2model2026) |
| 2025 · arXiv preprint | <a id="entry-globalconstraint2025"></a>**Gala**<br>Gala: Global LLM Agents for Text-to-Model Translation | 按全局约束类型分工 Agent，再由组装 Agent 合成完整 MiniZinc 模型。 | 方法 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | <span title="arXiv">[![arXiv][badge-002]][resource-222]</span><br><span title="Gala in Text2Model">[![Gala in Text2Model][badge-056]][resource-217]</span><br><span title="Author Project（相关）">[![Author Project（相关）][badge-057]][resource-223]</span><br>[详情](#paper-globalconstraint2025) |
| 2023 · arXiv preprint | <a id="entry-kadioglu2023holygrail"></a>**Holy Grail 2.0**<br>Holy Grail 2.0: From Natural Language to Constraint Models | 讨论把自然语言转为约束模型的分解式提示流程，并报告 GPT 模型的早期结果。 | 方法 · 基础 |  | <span title="arXiv">[![arXiv][badge-002]][resource-224]</span><br>[详情](#paper-kadioglu2023holygrail) |

#### 动态规划建模

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2025 · arXiv preprint | <a id="entry-dpdlm2025"></a>**DPLM / DP-Bench**<br>Auto-Formulating Dynamic Programming Problems with Large Language Models | 提出 DP-Bench，并用双向反思合成训练数据，训练从自然语言构造动态规划模型的 DPLM。 | 方法 · 基准 · 数据 · 模型 | [Data synthesis](#tech-data-synthesis) · [Reflection](#tech-reflection) · [SFT / distillation](#tech-sft) · [CoT / structured reasoning](#tech-cot) | <span title="arXiv">[![arXiv][badge-002]][resource-225]</span><br>[详情](#paper-dpdlm2025) |


[返回目录](#contents)

<a id="verification"></a>

### 模型验证、诊断与修复

将核验、解释或修复作为研究目标，区分执行错误、不可行性、数学等价与行为诊断。

#### 执行调试与代码修复

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-mirror2026"></a>**MIRROR**<br>MIRROR: A Multi-Agent Framework with Iterative Adaptive Revision and Hierarchical Retrieval for Optimization Modeling in Operations Research | 通过执行驱动的迭代修订与分层检索，获取建模和代码示例来修复优化模型。 | 方法 | [Agent](#tech-agent) · [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-226]</span><br>[详情](#paper-mirror2026) |

**相关工作：** [OptiLoop](#entry-optiloop2026) · [ReLoop / RetailOpt-190](#entry-lian2026reloop) · [SAC-Opt](#entry-ma2025sacopt)

#### 不可行诊断与优化解释

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · INFORMS Journal on Data Science | **OptiChat**<br>OptiChat: Bridging Optimization Models and Practitioners with Large Language Models | 用自然语言查询已有优化模型，支持不可行诊断、敏感性、what-if 和反事实解释。 | 方法 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-189]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-190]</span><br><span title="Code">[![Code][badge-008]][resource-191]</span><br>[详情](#paper-chen2025optichat) |
| 2026 · arXiv preprint | <a id="entry-optirepair2026"></a>**OptiRepair**<br>OptiRepair: Closed-Loop Diagnosis and Repair of Supply Chain Optimization Models with LLM Agents | 以 IIS 与运营合理性检查构建两阶段供应链修复闭环，提出 OptiRepair-SC 并训练 P1 / P2 模型。 | 方法 · 基准 · 数据 · 模型 · 应用 | [Agent](#tech-agent) · [LLM RL](#tech-llm-rl) · [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-227]</span><br>[详情](#paper-optirepair2026) |
| 2026 · ICML 2026 | <a id="entry-ao2026orloopbench"></a>**ORLoopBench**<br>ORLoopBench: Solver-in-the-Loop Benchmarks for Self-Correction and Behavioral Rationality in Operations Research | 以 IIS 和求解器重执行定义不可行模型修复闭环，配套 ORDebug 与 ORBias 评测。 | 方法 · 基准 · 数据 · 模型 | [LLM RL](#tech-llm-rl) · [Process rewards](#tech-prm) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-228]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-229]</span><br><span title="数据与校验代码">[![数据与校验代码][badge-058]][resource-230]</span><br>[详情](#paper-ao2026orloopbench) |
| 2025 · ICLR 2025 | <a id="entry-zhang2025decisioninfo"></a>**EOR / Decision Information**<br>Decision Information Meets Large Language Models: The Future of Explainable Operations Research | 用 what-if 决策信息与二部图比较模型变化，生成可操作的优化解释。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) | <span title="Proceedings">[![Proceedings][badge-005]][resource-231]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-232]</span><br><span title="Code">[![Code][badge-008]][resource-233]</span><br>[详情](#paper-zhang2025decisioninfo) |
| 2025 · arXiv preprint | <a id="entry-moid2025"></a>**MOID**<br>Multi-Objective Infeasibility Diagnosis for Routing Problems Using Large Language Models | 联合路径成本与约束违反量做多目标优化，再由 LLM 分析一组可恢复可行性的调整建议。 | 方法 · 数据 · 应用 | [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-234]</span><br><span title="Diagnosis Data">[![Diagnosis Data][badge-059]][resource-235]</span><br>[详情](#paper-moid2025) |
| 2024 · INFOR 2024 | <a id="entry-chen2023diagnosing"></a>**OptiChat / Infeasibility Diagnosis**<br>Diagnosing Infeasible Optimization Problems Using Large Language Models | 通过 GPT-4、求解器 IIS 与对话界面解释不可行原因，并建议模型修复。 | 方法 | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-236]</span><br><span title="DOI">[![DOI][badge-001]][resource-237]</span><br><span title="Code">[![Code][badge-008]][resource-191]</span><br>[详情](#paper-chen2023diagnosing) |

#### 等价性与题意核验

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | **CP-SynC**<br>CP-SynC: Multi-Agent Zero-Shot Constraint Modeling in MiniZinc with Synthesized Checkers | 由建模、检查与选择 Agent 并行探索 MiniZinc 模型，并合成语义检查器聚合证据。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-213]</span><br><span title="Benchmark &amp; Evaluation">[![Benchmark & Evaluation][badge-051]][resource-214]</span><br>[详情](#paper-cpsync2026) |
| 2026 · arXiv preprint | <a id="entry-optarcus2026"></a>**OptArgus**<br>OptArgus: A Multi-Agent System to Detect Hallucinations in LLM-based Optimization Modeling | 用幻觉分类法和专家 Agent 审计问题描述、数学模型与求解器实现的一致性。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | <span title="arXiv">[![arXiv][badge-002]][resource-238]</span><br>[详情](#paper-optarcus2026) |
| 2026 · Findings of ACL 2026 | <a id="entry-optiverse2026"></a>**OptiVerse / DVA-Agent**<br>OptiVerse: A Comprehensive Benchmark towards Optimization Problem Solving | 以 1,000 道多范式优化题评测建模与求解，并用双视角审核 Agent 对照需求与代码语义。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | <span title="Proceedings">[![Proceedings][badge-005]][resource-239]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-240]</span><br><span title="Inference, Auditor &amp; Evaluation">[![Inference, Auditor & Evaluation][badge-060]][resource-241]</span><br><span title="OptiVerse 1K">[![OptiVerse 1K][badge-061]][resource-242]</span><br>[详情](#paper-optiverse2026) |
| 2026 · ICML 2026 | <a id="entry-ma2025sacopt"></a>**SAC-Opt**<br>SAC-Opt: Semantic Anchors for Iterative Correction in Optimization Modeling | 把生成代码回译为语义锚点，与原始需求对齐后定点修正约束和目标。 | 方法 | [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-243]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-244]</span><br><span title="Code">[![Code][badge-008]][resource-245]</span><br>[详情](#paper-ma2025sacopt) |
| 2026 · Findings of EMNLP 2026 | <a id="entry-bhattacharyya2026sover"></a>**SOVER / NLEquiv-150**<br>SOVER: Formal Certification of Optimization Reformulations via LLM-Assisted SMT Verification | 由 LLM 提取重构映射，再用 Z3 或 dReal 核验公式之间的可行性及目标关系。 | 方法 · 基准 · 数据 | [Formal verification](#tech-formal) | <span title="Proceedings">[![Proceedings][badge-005]][resource-246]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-247]</span><br><span title="Code">[![Code][badge-008]][resource-248]</span><br><span title="EquivaFormulation（使用）（相关）">[![EquivaFormulation（使用）（相关）][badge-062]][resource-249]</span><br><span title="NLP4LP（使用）（相关）">[![NLP4LP（使用）（相关）][badge-063]][resource-185]</span><br>[详情](#paper-bhattacharyya2026sover) |
| 2026 · ICML 2026 | <a id="entry-verisimpl2026"></a>**VeriSimpl**<br>VeriSimpl: Robust Optimization Modeling from Natural Language using Simplification-based Verification | 用求解器构造简化诊断问题，帮助 LLM 检查模型是否符合自然语言题意。 | 方法 | [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-250]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-251]</span><br><span title="Proceedings">[![Proceedings][badge-005]][resource-252]</span><br><span title="Project（相关）">[![Project（相关）][badge-064]][resource-253]</span><br>[详情](#paper-verisimpl2026) |
| 2025 · ICML 2025 | <a id="entry-zhai2025equivamap"></a>**EquivaMap**<br>EquivaMap: Leveraging LLMs for Automatic Equivalence Checking of Optimization Formulations | 用 LLM 寻找决策变量映射来检查 Quasi-Karp 等价，并构建 EquivaFormulation。 | 方法 · 基准 · 数据 |  | <span title="Proceedings">[![Proceedings][badge-005]][resource-254]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-255]</span><br><span title="Code">[![Code][badge-008]][resource-256]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-249]</span><br>[详情](#paper-zhai2025equivamap) |
| 2025 · arXiv；相关 ICML 2026 Workshop 版本 | <a id="entry-ding2026orgeval"></a>**ORGEval / Bench4Opt**<br>ORGEval: Graph-Theoretic Evaluation of LLMs in Optimization Modeling | 将优化形式化表示为图，通过图同构及对称可分解条件下的 WL 测试评价结构等价性。 | 方法 · 基准 · 数据 |  | <span title="arXiv">[![arXiv][badge-002]][resource-257]</span><br><span title="ICML workshop poster（相关）">[![ICML workshop poster（相关）][badge-065]][resource-258]</span><br>[详情](#paper-ding2026orgeval) |

**相关工作：** [Falsification-Based Verification](#entry-li2026falsification)

#### 行为审计与扰动诊断

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · Findings of EMNLP 2026 | <a id="entry-constraintinjection2026"></a>**Constraint Injection / VRPCoder**<br>Beyond Objective Equivalence: Constraint Injection for LLM-Based Optimization Modeling on Vehicle Routing Problems | 用可行解和单约束违反解测试 VRP 代码，补充最优值相同仍可能漏约束的检查。 | 方法 · 基准 · 数据 · 模型 · 应用 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-259]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-260]</span><br><span title="Benchmark Data">[![Benchmark Data][badge-066]][resource-261]</span><br>[详情](#paper-constraintinjection2026) |
| 2026 · arXiv preprint | <a id="entry-li2026falsification"></a>**Falsification-Based Verification**<br>Falsification-Based Verification of LLM-Generated Optimization Models: Sound Test Batteries and Their Detection Limits | 通过数值角色扰动、对偶与敏感性关系测试生成模型，并刻画可检测错误与盲区。 | 方法 | [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-262]</span><br>[详情](#paper-li2026falsification) |
| 2026 · ICML 2026 | **NEMO**<br>NEMO: Execution-Aware Optimization Modeling via Autonomous Coding Agents | 用自主编码 Agent 生成优化器与模拟器，再以交叉执行、经验复用和候选一致性改进建模。 | 方法 | [Agent](#tech-agent) · [Memory](#tech-memory) · [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-124]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-125]</span><br><span title="Evaluation Artifacts">[![Evaluation Artifacts][badge-030]][resource-126]</span><br>[详情](#paper-nemo2026) |
| 2026 · arXiv preprint | <a id="entry-optiloop2026"></a>**OptiLoop**<br>OptiLoop: Coordination-in-the-Loop Verification and Repair for LLM-Generated Optimization Agents | 在有限轮 ADMM 式协同中测试本地优化 Agent，利用行为与静态证据修复实现或公式。 | 方法 | [Agent](#tech-agent) · [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-263]</span><br>[详情](#paper-optiloop2026) |
| 2026 · NeurIPS 2026（已接收，待出版） | <a id="entry-lian2026reloop"></a>**ReLoop / RetailOpt-190**<br>ReLoop: Structured Modeling and Behavioral Verification for Reliable LLM-Based Optimization | 结合结构化建模链与求解器参数扰动检查，定位静默错误并实施诊断引导修复。 | 方法 · 基准 · 数据 | [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-264]</span><br><span title="Proceedings">[![Proceedings][badge-005]][resource-265]</span><br><span title="Code">[![Code][badge-008]][resource-266]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-267]</span><br>[详情](#paper-lian2026reloop) |
| 2025 · ACL 2025 Industry Track | **ORMind**<br>ORMind: A Cognitive-Inspired End-to-End Reasoning Framework for Operations Research | 以认知启发的角色协作、执行修复和反事实检查完成优化建模。 | 方法 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-165]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-166]</span><br><span title="Code">[![Code][badge-008]][resource-167]</span><br>[详情](#paper-ormind2025) |

**相关工作：** [OptiRepair](#entry-optirepair2026) · [ORLoopBench](#entry-ao2026orloopbench)


[返回目录](#contents)

<a id="direct-solving"></a>

### 直接解生成与优化决策

由 LLM 直接产生候选解、调度、数值决策或运营策略；生成求解器程序另见建模。

#### 离散解与调度生成

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | **DScheLLM**<br>DScheLLM: Enabling Dynamic Scheduling through a Fine-Tuned Dual-System Large language Model | 用求解器排程合成快／慢思考示范，LoRA 微调双系统 LLM 应对动态扰动。 | 方法 · 数据 · 模型 · 应用 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) · [CoT / structured reasoning](#tech-cot) | <span title="arXiv">[![arXiv][badge-002]][resource-028]</span><br>[详情](#paper-zhang2026dschellm) |
| 2026 · arXiv preprint | <a id="entry-infeasibilityaware2026"></a>**Infeasibility-Aware CO Models**<br>Infeasibility Aware Large Language Models for Combinatorial Optimization | 用精确优化与可认证筛选构建可行／不可行训练样本，微调模型输出解或不可行判断，再辅助局部搜索。 | 方法 · 数据 · 模型 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-268]</span><br><span title="Author Code / Data Archive（相关）">[![Author Code / Data Archive（相关）][badge-067]][resource-269]</span><br>[详情](#paper-infeasibilityaware2026) |
| 2026 · arXiv preprint | <a id="entry-jiang2026poweratlas"></a>**PowerAtlas / ECBench**<br>PowerAtlas: Feasibility-Aware Language Models for Electricity-Computing Co-Scheduling | 以可行性反馈训练 LLM 直接生成电力—计算联合排程，并提出 ECBench 与确定性评分。 | 方法 · 基准 · 数据 · 模型 · 应用 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-270]</span><br><span title="Code &amp; Sample Data">[![Code & Sample Data][badge-068]][resource-271]</span><br>[详情](#paper-jiang2026poweratlas) |
| 2025 · NeurIPS 2025 | <a id="entry-jiang2025e2eco"></a>**LLMCoSolver / E2E CO Solver**<br>Large Language Models as End-to-end Combinatorial Optimization Solvers | 经 SFT 与可行性／最优性感知的 FOARL，训练 LLM 从问题描述直接输出组合优化解。 | 方法 · 模型 · 数据 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-272]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-273]</span><br><span title="Code">[![Code][badge-008]][resource-274]</span><br><span title="SFT Data">[![SFT Data][badge-069]][resource-275]</span><br><span title="RL Data">[![RL Data][badge-070]][resource-276]</span><br>[详情](#paper-jiang2025e2eco) |
| 2025 · Proceedings of the Design Society 5 · ICED25（2025） | <a id="entry-dsmco2024"></a>**LLMs for DSM Sequencing**<br>Large language models for combinatorial optimization of design structure matrix | 把网络拓扑和领域知识共同提供给 LLM，迭代搜索设计结构矩阵的排序方案。 | 方法 · 应用 |  | <span title="DOI">[![DOI][badge-001]][resource-277]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-278]</span><br>[详情](#paper-dsmco2024) |
| 2025 · arXiv preprint | <a id="entry-abgaryan2025starjob"></a>**Starjob**<br>Starjob: Dataset for LLM-Driven Job Shop Scheduling | 发布作业车间调度训练数据，用 LoRA 微调 LLM 直接输出调度解。 | 方法 · 数据 · 模型 · 应用 | [SFT / distillation](#tech-sft) | <span title="arXiv">[![arXiv][badge-002]][resource-279]</span><br><span title="Code">[![Code][badge-008]][resource-280]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-281]</span><br>[详情](#paper-abgaryan2025starjob) |
| 2025 · arXiv preprint | <a id="entry-bridgingviz2025"></a>**Visual Graph Optimization with MLLMs**<br>Bridging Visualization and Optimization: Multimodal Large Language Models on Graph-Structured Combinatorial Optimization | 把图结构呈现为图像，结合多模态 LLM 与简单搜索处理影响最大化、网络拆解和图任务。 | 方法 · 评测分析 | [Multimodal input](#tech-multimodal) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-282]</span><br>[详情](#paper-bridgingviz2025) |
| 2024 · arXiv preprint | <a id="entry-wang2024raremip"></a>**Rare MIP Challenges**<br>Leveraging Large Language Models for Solving Rare MIP Challenges | 结合微调、思维链与递归动态温度生成罕见 MIP 场景的可行解。 | 方法 | [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) · [CoT / structured reasoning](#tech-cot) | <span title="arXiv">[![arXiv][badge-002]][resource-283]</span><br>[详情](#paper-wang2024raremip) |

#### 运营策略与交互决策

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-beergame2026"></a>**GenAI Beer Game Reliability**<br>Reliability and Effectiveness of Autonomous AI Agents in Supply Chain Management | 在多级 Beer Game 中研究 Agent 决策波动，并比较强化学习后训练与运营护栏的可靠性。 | 方法 · 评测分析 · 应用 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [LLM RL](#tech-llm-rl) | <span title="arXiv">[![arXiv][badge-002]][resource-284]</span><br>[详情](#paper-beergame2026) |
| 2025 · arXiv preprint | <a id="entry-alas2025"></a>**ALAS**<br>ALAS: A Stateful Multi-LLM Agent Framework for Disruption-Aware Planning | 用角色化 Agent、持久状态与历史感知的局部补偿，处理调度计划中的运行扰动。 | 方法 · 应用 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Memory](#tech-memory) | <span title="arXiv">[![arXiv][badge-002]][resource-285]</span><br>[详情](#paper-alas2025) |
| 2025 · arXiv（2026 修订） | <a id="entry-cao2025reflecsched"></a>**ReflecSched**<br>ReflecSched: Solving Dynamic Flexible Job-Shop Scheduling via LLM-Powered Hierarchical Reflection | 从多规划时域的启发式仿真中提炼战略经验，指导动态柔性作业车间调度决策。 | 方法 · 应用 | [Memory](#tech-memory) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-286]</span><br>[详情](#paper-cao2025reflecsched) |
| 2024 · arXiv preprint | <a id="entry-quan2024invagent"></a>**InvAgent**<br>InvAgent: A Large Language Model based Multi-Agent System for Inventory Management in Supply Chains | 让多个 LLM Agent 通过零样本推理管理供应链库存并适应需求变化。 | 方法 · 应用 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | <span title="arXiv">[![arXiv][badge-002]][resource-287]</span><br><span title="Code">[![Code][badge-008]][resource-288]</span><br>[详情](#paper-quan2024invagent) |
| 2024 · EMNLP 2024 Industry Track | <a id="entry-tang2024itinerary"></a>**ITINERA**<br>ItiNera: Integrating Spatial Optimization with Large Language Models for Open-domain Urban Itinerary Planning | 分解城市漫步需求、选择兴趣点，并用聚类感知的空间优化排序与生成个性化行程。 | 方法 · 应用 | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-289]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-290]</span><br><span title="Code">[![Code][badge-008]][resource-291]</span><br>[详情](#paper-tang2024itinerary) |

#### 数值优化与参数决策

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · Findings of ACL 2026 | <a id="entry-li2026optbench"></a>**OPT-BENCH / OPT-Agent**<br>OPT-BENCH: Evaluating the Iterative Self-Optimization of LLM Agents in Large-Scale Search Spaces | 在机器学习调优与 NP 问题中评测迭代自优化，并用 OPT-Agent 复用历史反馈修订方案。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) · [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-292]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-293]</span><br><span title="Revised Preprint">[![Revised Preprint][badge-071]][resource-294]</span><br><span title="Code">[![Code][badge-008]][resource-295]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-296]</span><br>[详情](#paper-li2026optbench) |
| 2024 · ICLR 2024 | <a id="entry-yang2024opro"></a>**OPRO**<br>Large Language Models as Optimizers | 根据历史候选及其数值评价提示 LLM 生成新解，研究直接优化与提示优化。 | 方法 · 基础 |  | <span title="Proceedings">[![Proceedings][badge-005]][resource-297]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-298]</span><br><span title="Code">[![Code][badge-008]][resource-299]</span><br>[详情](#paper-yang2024opro) |


[返回目录](#contents)

<a id="algorithms"></a>

### 启发式与算法自动设计

生成和改进完整算法、启发式程序、邻域算子或优化方法。

#### 启发式程序发现

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · ICML 2026 | <a id="entry-chen2026a2dept"></a>**A2DEPT**<br>A2DEPT: Large Language Model-Driven Automated Algorithm Design via Evolutionary Program Trees | 以树结构演化、混合选择和分层操作搜索完整算法，并通过执行反馈修复程序。 | 方法 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-300]</span><br><span title="Proceedings">[![Proceedings][badge-005]][resource-301]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-302]</span><br>[详情](#paper-chen2026a2dept) |
| 2026 · ICLR 2026 | <a id="entry-zhang2026afl"></a>**AFL**<br>An Agentic Framework with LLMs for Solving Complex Vehicle Routing Problems | 由四个专门 Agent 从原始 VRP 输入自主生成并协调修正求解程序。 | 方法 · 应用 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-303]</span><br><span title="Proceedings">[![Proceedings][badge-005]][resource-304]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-305]</span><br><span title="Code">[![Code][badge-008]][resource-306]</span><br>[详情](#paper-zhang2026afl) |
| 2026 · arXiv preprint | <a id="entry-invpolicy2026"></a>**Automated Inventory Policy Design**<br>Automated Design of Inventory Policy with Large Language Models: An Exploratory Study | 让 LLM 迭代生成库存策略函数类，再由外部优化器在类内调参并反馈成本。 | 方法 · 应用 | [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-307]</span><br>[详情](#paper-invpolicy2026) |
| 2026 · ICLR 2026 | <a id="entry-huang2025calm"></a>**CALM (Algorithm–LM Co-evolution)**<br>CALM: Co-evolution of Algorithms and Language Model for Automatic Heuristic Design | 用生成启发式的质量作 RL 信号，共同演化候选算法与底层语言模型。 | 方法 · 模型 | [Program evolution](#tech-evolution) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-308]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-309]</span><br><span title="Code">[![Code][badge-008]][resource-310]</span><br>[详情](#paper-huang2025calm) |
| 2026 · Inteligencia Artificial | <a id="entry-co4all2025"></a>**Combinatorial Optimization for All**<br>Combinatorial Optimization for All: Using LLMs to Aid Non-Experts in Improving Optimization Algorithms | 以较少专业知识的提示改进十种已有 TSP 算法，比较解质量、运行时间和代码复杂度。 | 方法 · 评测分析 | [Execution / solver feedback](#tech-solver-feedback) | <span title="Journal">[![Journal][badge-017]][resource-311]</span><br><span title="DOI">[![DOI][badge-001]][resource-312]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-313]</span><br><span title="Prompts &amp; Algorithms">[![Prompts & Algorithms][badge-072]][resource-314]</span><br><span title="Project（相关）">[![Project（相关）][badge-057]][resource-315]</span><br>[详情](#paper-co4all2025) |
| 2026 · arXiv preprint | <a id="entry-dsevolve2026"></a>**DSevolve**<br>DSevolve: Enabling Real-Time Adaptive Scheduling on Dynamic Flexible Job Shop with LLM-Evolved Heuristic Portfolios | 离线演化互补排程规则库，再用状态条件神经选择器在线响应柔性车间扰动。 | 方法 · 应用 | [Program evolution](#tech-evolution) · [Auxiliary / NCO learning](#tech-auxiliary-learning) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-316]</span><br>[详情](#paper-dsevolve2026) |
| 2026 · arXiv preprint | <a id="entry-epoch2026"></a>**EPOCH**<br>EPOCH: Coverage-Aware Evolution with Experiential Preference Optimization for LLM-based Automated Heuristic Design | 以实例覆盖选择互补启发式，并用教师反思形成偏好对，通过 DPO 与反思自蒸馏更新生成器。 | 方法 · 模型 | [Program evolution](#tech-evolution) · [Reflection](#tech-reflection) · [Preference optimization](#tech-preference) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-317]</span><br>[详情](#paper-epoch2026) |
| 2026 · ICIST 2026（已接收） | <a id="entry-es2026ahd"></a>**ES-AHD**<br>ES-AHD: An Evolution Strategy Framework for Automatic Heuristic Design | 让 LLM 从精英程序提取语义中心，并通过带动量的温度采样调节搜索范围。 | 方法 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-318]</span><br><span title="PDF">[![PDF][badge-073]][resource-319]</span><br><span title="Code">[![Code][badge-008]][resource-320]</span><br>[详情](#paper-es2026ahd) |
| 2026 · ICLR 2026 | <a id="entry-chen2025hifoprompt"></a>**HiFo-Prompt**<br>HiFo-Prompt: Prompting with Hindsight and Foresight for LLM-based Automatic Heuristic Design | 用事后知识池积累启发式设计原则，并依群体动态选择面向未来的搜索提示。 | 方法 | [Program evolution](#tech-evolution) · [Memory](#tech-memory) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-321]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-322]</span><br><span title="Code">[![Code][badge-008]][resource-323]</span><br>[详情](#paper-chen2025hifoprompt) |
| 2026 · arXiv preprint | <a id="entry-invevolve2026"></a>**InvEvolve**<br>InvEvolve: Evolving White-Box Inventory Policies via Large Language Models with Performance Guarantees | 用 LLM 演化白盒库存策略，并以置信区间认证框架研究部署安全与性能改进。 | 方法 · 应用 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-324]</span><br>[详情](#paper-invevolve2026) |
| 2026 · arXiv preprint | <a id="entry-hsplo2026"></a>**LaGO**<br>Heuristic Search as Language-Guided Program Optimization | 将启发式发现拆为执行评价、语言分析反馈和程序更新三个模块，支持独立改进组件。 | 方法 | [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-325]</span><br>[详情](#paper-hsplo2026) |
| 2026 · LION 20 / 2026（已接收） | <a id="entry-latentheuristic2026"></a>**Latent Heuristic Search**<br>Latent Heuristic Search: Continuous Optimization for Automated Algorithm Design | 学习程序编码、性能代理、可逆流和软提示映射，在连续潜空间中优化并解码为启发式。 | 方法 | [Auxiliary / NCO learning](#tech-auxiliary-learning) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-326]</span><br><span title="Proceedings">[![Proceedings][badge-005]][resource-327]</span><br><span title="Code">[![Code][badge-008]][resource-328]</span><br>[详情](#paper-latentheuristic2026) |
| 2026 · IEEE TEVC | <a id="entry-ma2024llamoco"></a>**LLaMoCo**<br>LLaMoCo: Instruction Tuning of Large Language Models for Optimization Code Generation | 构造问题—优化代码指令集，以对比学习预热和指令微调训练从问题代码生成优化程序的模型。 | 方法 · 模型 · 数据 | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-329]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-330]</span><br><span title="LLaMoCo-S Example">[![LLaMoCo-S Example][badge-074]][resource-331]</span><br><span title="LLaMoCo-S">[![LLaMoCo-S][badge-075]][resource-332]</span><br>[详情](#paper-ma2024llamoco) |
| 2026 · arXiv preprint | <a id="entry-efficientfrontier2026"></a>**LLM Agents for Efficient Frontiers**<br>LLM Agents for Combinatorial Efficient Frontiers: Investment Portfolio Optimization | 用 Agent 自动化基数约束均值—方差投资组合的启发式开发及有效前沿构建。 | 方法 · 应用 | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-333]</span><br>[详情](#paper-efficientfrontier2026) |
| 2026 · arXiv preprint | <a id="entry-meevo2026"></a>**MeEvo**<br>MeEvo: Metacognitive Evolution Combined with Natural Evolution for Automatic Heuristic Design | 交替执行代码重组／变异和基于推理历史的元认知反思，把两阶段结果反馈到下一轮。 | 方法 | [Program evolution](#tech-evolution) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-334]</span><br><span title="Code">[![Code][badge-008]][resource-335]</span><br>[详情](#paper-meevo2026) |
| 2026 · Expert Systems with Applications 330（2026-12 编期） | <a id="entry-chen2025mela"></a>**MeLA**<br>MeLA: A metacognitive LLM-driven architecture for automatic heuristic design | 通过问题分析、错误诊断和元认知搜索演化生成启发式的提示，而非仅对代码做变异。 | 方法 | [Program evolution](#tech-evolution) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-336]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-337]</span><br>[详情](#paper-chen2025mela) |
| 2026 · AAAI 2026 | <a id="entry-ha2025paretogrid"></a>**MPaGE**<br>Pareto-Grid-Guided Large Language Models for Fast and High-Quality Heuristics Design in Multi-Objective Combinatorial Optimization | 用 Pareto 前沿网格和语义聚类指导 LLM 启发式演化，兼顾多目标质量、速度与多样性。 | 方法 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-338]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-339]</span><br><span title="Code">[![Code][badge-008]][resource-340]</span><br>[详情](#paper-ha2025paretogrid) |
| 2026 · ICML 2026 | <a id="entry-pathwise2026"></a>**PathWise**<br>PathWise: Planning through World Model for Automated Heuristic Design via Self-Evolving LLMs | 在保存搜索历史的蕴含图上规划演化动作，由策略、世界模型和评论 Agent 协作生成启发式。 | 方法 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-341]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-342]</span><br><span title="Code">[![Code][badge-008]][resource-343]</span><br>[详情](#paper-pathwise2026) |
| 2026 · ICLR 2026 | <a id="entry-lange2026shinka"></a>**ShinkaEvolve**<br>ShinkaEvolve: Towards Open-Ended and Sample-Efficient Program Evolution | 结合父代采样、代码新颖性拒绝采样和 bandit 模型选择，提高程序演化的样本效率。 | 方法 · 平台 | [Program evolution](#tech-evolution) · [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-344]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-345]</span><br><span title="Code">[![Code][badge-008]][resource-346]</span><br>[详情](#paper-lange2026shinka) |
| 2026 · arXiv preprint | <a id="entry-chen2026tide"></a>**TIDE**<br>TIDE: Tuning-Integrated Dynamic Evolution for LLM-Based Automated Heuristic Design | 用外层岛模型搜索程序结构，内层差分变异调整数值参数，再由 UCB 调度提示策略。 | 方法 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-347]</span><br>[详情](#paper-chen2026tide) |
| 2025 · arXiv preprint | <a id="entry-li2025ars"></a>**ARS / RoutBench**<br>ARS: Automatic Routing Solver with Large Language Models | 根据问题描述生成约束感知的路由启发式，配套多变体 VRP 基准 RoutBench。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-348]</span><br><span title="Code">[![Code][badge-008]][resource-349]</span><br>[详情](#paper-li2025ars) |
| 2025 · arXiv preprint | <a id="entry-bomer2025emerging"></a>**CEoH**<br>Leveraging Large Language Models to Develop Heuristics for Emerging Optimization Problems | 在 EoH 提示中加入问题上下文，为仓储单元载荷预翻垛等较少研究的任务发现启发式。 | 方法 · 应用 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-350]</span><br><span title="Code">[![Code][badge-008]][resource-351]</span><br>[详情](#paper-bomer2025emerging) |
| 2025 · arXiv preprint | <a id="entry-viktorin2025ease"></a>**EASE**<br>Solve it with EASE | 以模块化生成、测试、分析和评价循环支持算法方案演化，允许多个 LLM 承担互补角色。 | 方法 · 平台 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-352]</span><br><span title="Framework">[![Framework][badge-076]][resource-353]</span><br><span title="Frontend">[![Frontend][badge-077]][resource-354]</span><br>[详情](#paper-viktorin2025ease) |
| 2025 · arXiv preprint | <a id="entry-luo2025efs"></a>**EFS**<br>Evolutionary Factor Searching for Sparse Portfolio Optimization Using Large Language Models | 用 LLM 与进化搜索产生排序因子，并结合去冗余权重分配构建稀疏投资组合。 | 方法 · 应用 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-355]</span><br>[详情](#paper-luo2025efs) |
| 2025 · arXiv preprint | <a id="entry-ucfunsearch2025"></a>**FunSearch for Unit Commitment**<br>Automated Heuristic Design for Unit Commitment Using Large Language Models | 将 LLM 程序搜索与评估器用于机组组合启发式自动设计。 | 方法 · 应用 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-356]</span><br>[详情](#paper-ucfunsearch2025) |
| 2025 · arXiv preprint | <a id="entry-yang2025heuragenix"></a>**HeurAgenix**<br>HeurAgenix: Leveraging LLMs for Solving Complex Combinatorial Optimization Challenges | 先生成与演化启发式库，再按问题状态选择算子；选择器可采用通用 LLM 或领域微调模型。 | 方法 · 模型 | [Program evolution](#tech-evolution) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-357]</span><br><span title="Code">[![Code][badge-008]][resource-358]</span><br><span title="CO Instances">[![CO Instances][badge-078]][resource-359]</span><br>[详情](#paper-yang2025heuragenix) |
| 2025 · AAAI 2025 | <a id="entry-dat2024hsevo"></a>**HSEvo**<br>HSEvo: Elevating Automatic Heuristic Design with Diversity-Driven Harmony Search and Genetic Algorithm Using LLMs | 以多样性指标分析启发式演化，并将和声搜索与遗传搜索结合改善探索。 | 方法 · 评测分析 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-360]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-361]</span><br><span title="Code">[![Code][badge-008]][resource-362]</span><br>[详情](#paper-dat2024hsevo) |
| 2025 · arXiv preprint | <a id="entry-zhang2025instspechh"></a>**InstSpecHH**<br>LLM-Driven Instance-Specific Heuristic Generation and Selection | 按实例特征划分子类，离线演化专门启发式，并通过 LLM 或轻量分类器选择适用算法。 | 方法 | [Program evolution](#tech-evolution) · [Auxiliary / NCO learning](#tech-auxiliary-learning) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-363]</span><br>[详情](#paper-zhang2025instspechh) |
| 2025 · IEEE CEC 2025 | <a id="entry-xie2025llmns"></a>**LHNS**<br>LLM-Driven Neighborhood Search for Efficient Heuristic Design | 以启发式程序的邻域搜索组织 LLM 改写，设计三种搜索方式以降低发现成本。 | 方法 | [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-364]</span><br><span title="Proceedings">[![Proceedings][badge-005]][resource-365]</span><br><span title="LLM4AD: LHNS">[![LLM4AD: LHNS][badge-079]][resource-366]</span><br>[详情](#paper-xie2025llmns) |
| 2025 · IEEE TEVC | <a id="entry-vanstein2024llamea"></a>**LLaMEA**<br>LLaMEA: A Large Language Model Evolutionary Algorithm for Automatically Generating Metaheuristics | 通过 LLM 自动生成、变异及选择元启发式，用运行评价反馈持续改进算法。 | 方法 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-367]</span><br><span title="Code">[![Code][badge-008]][resource-368]</span><br>[详情](#paper-vanstein2024llamea) |
| 2025 · arXiv preprint | <a id="entry-cetinkaya2025mipsmtt"></a>**LLM-discovered EDDC / MDDC**<br>Discovering Heuristics with Large Language Models (LLMs) for Mixed-Integer Programs: Single-Machine Scheduling | 用 LLM 与进化流程发现单机总拖期启发式 EDDC 和 MDDC，按解质量与时间比较经典规则。 | 方法 · 应用 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-369]</span><br><span title="Code">[![Code][badge-008]][resource-370]</span><br>[详情](#paper-cetinkaya2025mipsmtt) |
| 2025 · ICML 2025 | <a id="entry-zheng2025mctsahd"></a>**MCTS-AHD**<br>Monte Carlo Tree Search for Comprehensive Exploration in LLM-Based Automatic Heuristic Design | 将生成的启发式组织为 MCTS 搜索树，继续探索暂时低分候选的潜力。 | 方法 | [MCTS](#tech-mcts) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-371]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-372]</span><br><span title="Code">[![Code][badge-008]][resource-373]</span><br>[详情](#paper-zheng2025mctsahd) |
| 2025 · AAAI 2025 | <a id="entry-yao2025meoh"></a>**MEoH**<br>Multi-Objective Evolution of Heuristic Using Large Language Model | 在解质量、计算效率和可扩展性之间搜索 Pareto 启发式，并以支配关系和差异性选择候选。 | 方法 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-374]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-375]</span><br><span title="LLM4AD: MEoH">[![LLM4AD: MEoH][badge-080]][resource-376]</span><br>[详情](#paper-yao2025meoh) |
| 2025 · ICLR 2025 Agentic AI Workshop | <a id="entry-tran2025llmneural"></a>**NCO-LLM for VRP**<br>Large Language Models powered Neural Solvers for Generalized Vehicle Routing Problems | 演化 LLM 生成的结构偏置并注入注意力分数，再微调 LEHD / POMO 神经路由策略。 | 方法 · 模型 · 应用 | [Program evolution](#tech-evolution) · [Auxiliary / NCO learning](#tech-auxiliary-learning) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Paper">[![Paper][badge-007]][resource-377]</span><br><span title="Code">[![Code][badge-008]][resource-378]</span><br>[详情](#paper-tran2025llmneural) |
| 2025 · arXiv preprint | <a id="entry-thach2025redahd"></a>**RedAHD**<br>RedAHD: Reduction-Based End-to-End Automatic Heuristic Design with Large Language Models | 让 LLM 设计问题与解的归约，将原组合问题变为更熟悉的问题，再演化求解启发式。 | 方法 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-379]</span><br>[详情](#paper-thach2025redahd) |
| 2025 · arXiv preprint | <a id="entry-xu2025roco"></a>**RoCo**<br>RoCo: Role-Based LLMs Collaboration for Automatic Heuristic Design | 用探索者、开发者、批评者和整合者四个角色协作生成、审查和修订启发式。 | 方法 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-380]</span><br>[详情](#paper-xu2025roco) |
| 2025 · NeurIPS 2025 | <a id="entry-li2025strcmp"></a>**STRCMP**<br>STRCMP: Integrating Graph Structural Priors with Language Models for Combinatorial Optimization | 将图神经网络的结构先验接入语言模型，通过训练和演化生成求解器专用算法代码。 | 方法 · 模型 | [Program evolution](#tech-evolution) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Auxiliary / NCO learning](#tech-auxiliary-learning) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-381]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-382]</span><br><span title="Code">[![Code][badge-008]][resource-383]</span><br>[详情](#paper-li2025strcmp) |
| 2024 · ICML 2024 | <a id="entry-liu2024eoh"></a>**EoH**<br>Evolution of Heuristics: Towards Efficient Automatic Algorithm Design Using Large Language Model | 同步演化自然语言启发式思路和可执行代码，以性能反馈驱动自动算法设计。 | 方法 · 基础 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-384]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-385]</span><br><span title="Code">[![Code][badge-008]][resource-386]</span><br>[详情](#paper-liu2024eoh) |
| 2024 · NeurIPS 2024 | <a id="entry-ye2024reevo"></a>**ReEvo**<br>ReEvo: Large Language Models as Hyper-Heuristics with Reflective Evolution | 结合进化搜索与 LLM 反思，用语言反馈指导超启发式程序改进。 | 方法 | [Program evolution](#tech-evolution) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-387]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-388]</span><br><span title="Code">[![Code][badge-008]][resource-389]</span><br>[详情](#paper-ye2024reevo) |
| 2023 · arXiv preprint | <a id="entry-liu2023ael"></a>**AEL**<br>Algorithm Evolution Using Large Language Model | 让 LLM 生成算法并在进化循环中选择改写，以 TSP 构造启发式展示算法级演化。 | 方法 · 基础 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-390]</span><br>[详情](#paper-liu2023ael) |
| 2023 · Nature（2023 在线发表） | <a id="entry-romera2023funsearch"></a>**FunSearch**<br>Mathematical discoveries from program search with large language models | 结合 LLM 程序生成、进化搜索和自动评估，发现数学构造与装箱启发式。 | 方法 · 基础 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-391]</span><br><span title="Code">[![Code][badge-008]][resource-392]</span><br>[详情](#paper-romera2023funsearch) |

#### 邻域与算子设计

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-xie2026ailsahd"></a>**AILS-AHD**<br>Enhancing CVRP Solver through LLM-driven Automatic Heuristic Design | 在自适应迭代局部搜索中演化 ruin 启发式，并结合 LLM 辅助加速改善 CVRP 求解。 | 方法 · 应用 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-393]</span><br>[详情](#paper-xie2026ailsahd) |
| 2026 · arXiv preprint | <a id="entry-yu2026alns"></a>**Full-Component ALNS Evolution**<br>Large Language Model-Driven Full-Component Evolution of Adaptive Large Neighborhood Search | 拆分并演化 ALNS 的七类组件，以多维精英档案兼顾解质量和策略多样性。 | 方法 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-394]</span><br><span title="Evolved ALNS（相关）">[![Evolved ALNS（相关）][badge-081]][resource-395]</span><br>[详情](#paper-yu2026alns) |
| 2026 · arXiv preprint | <a id="entry-zhao2026glns"></a>**G-LNS**<br>G-LNS: Generative Large Neighborhood Search for LLM-Based Automatic Heuristic Design | 共同演化 LNS 的 destroy／repair 算子对，以协作评估捕捉破坏与修复的互补关系。 | 方法 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-396]</span><br><span title="Code">[![Code][badge-008]][resource-397]</span><br>[详情](#paper-zhao2026glns) |
| 2026 · NeurIPS 2026（已接收，待出版） | <a id="entry-yan2026pall"></a>**PALL**<br>Process-Aware LNS for Large-Scale MILP via Context-Enhanced Fine-Tuned LLM-driven Selector | 离线演化 LNS 算子组合，以 hindsight oracle 轨迹微调 8B LLM 在线选择器。 | 方法 · 模型 | [Program evolution](#tech-evolution) · [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Paper">[![Paper][badge-007]][resource-398]</span><br>[详情](#paper-yan2026pall) |
| 2026 · AAMAS 2026 | <a id="entry-pyvrpplus2026"></a>**PyVRP+ / MEP**<br>PyVRP+: LLM-Driven Metacognitive Heuristic Evolution for Hybrid Genetic Search in Vehicle Routing Problems | 通过 Reason–Act–Reflect 诊断和设计假设，演化 HGS 中的路由启发式组件。 | 方法 · 应用 | [Reflection](#tech-reflection) · [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-399]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-400]</span><br><span title="Proceedings">[![Proceedings][badge-005]][resource-401]</span><br>[详情](#paper-pyvrpplus2026) |
| 2026 · arXiv preprint | <a id="entry-lai2026specahd"></a>**SpecAHD**<br>SpecAHD: Localize to Specialize for Automated Heuristic Design in Large-Scale Routing Problems | 以双层搜索共同选择局部修复区域，并演化适配区域差异的互补启发式库。 | 方法 · 应用 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-402]</span><br>[详情](#paper-lai2026specahd) |
| 2026 · arXiv preprint | <a id="entry-spo2026"></a>**SPO**<br>SPO: Discovering Adaptive Large Neighborhood Search Operators via Stackelberg Program Optimization | 按 Stackelberg 主从关系发现状态依赖的 destroy / repair 程序，并共同更新程序种群与生成器。 | 方法 · 模型 · 应用 | [LLM RL](#tech-llm-rl) · [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-403]</span><br>[详情](#paper-spo2026) |
| 2026 · Transactions on Machine Learning Research（2026） | <a id="entry-vrpagent2025"></a>**VRPAgent**<br>VRPAgent: LLM-Driven Discovery of Heuristic Operators for Vehicle Routing Problems | 将 LLM 生成的路由算子嵌入共享 LNS 框架，以带代码长度惩罚的遗传搜索改进候选。 | 方法 · 应用 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="OpenReview">[![OpenReview][badge-082]][resource-404]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-405]</span><br><span title="Generated Operators（相关）">[![Generated Operators（相关）][badge-083]][resource-406]</span><br>[详情](#paper-vrpagent2025) |
| 2025 · ICML 2025 | <a id="entry-ye2025llmlns"></a>**LLM-LNS**<br>Large Language Model-driven Large Neighborhood Search for Large-Scale MILP Problems | 通过双层自演化 LLM Agent 设计 LNS 邻域策略，研究向大规模 MILP 的迁移。 | 方法 | [Agent](#tech-agent) · [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-407]</span><br><span title="Code">[![Code][badge-008]][resource-408]</span><br>[详情](#paper-ye2025llmlns) |
| 2025 · arXiv preprint | <a id="entry-ali2025pair"></a>**PAIR**<br>PAIR: A Novel Large Language Model-Guided Selection Strategy for Evolutionary Algorithms | 通过适应度、多样性与交叉兼容性提示 LLM 选择进化算法中的配对个体，并在 TSP 上评测。 | 方法 |  | <span title="arXiv">[![arXiv][badge-002]][resource-409]</span><br><span title="Code">[![Code][badge-008]][resource-410]</span><br>[详情](#paper-ali2025pair) |

#### 通用优化算法设计

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-autoopt2026"></a>**AutoOPT**<br>A Domain-Specific Harness for End-to-End Automation of Optimization Research | 连接数值方法设计、LLM 符号推导、Lean 4 验证和人工解释，研究最优一阶优化算法。 | 方法 · 平台 | [Agent](#tech-agent) · [Formal verification](#tech-formal) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-411]</span><br><span title="Code">[![Code][badge-008]][resource-412]</span><br><span title="Skills">[![Skills][badge-033]][resource-413]</span><br><span title="Lean Proofs">[![Lean Proofs][badge-084]][resource-414]</span><br>[详情](#paper-autoopt2026) |
| 2026 · ICLR 2026 | <a id="entry-moh2025"></a>**MoH**<br>Generalizable Heuristic Generation Through LLMs with Meta-Optimization | 演化可自调用的元优化程序，让其构造启发式优化器，再为多个下游问题演化启发式。 | 方法 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-415]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-416]</span><br><span title="Code">[![Code][badge-008]][resource-417]</span><br><span title="CO Task Data">[![CO Task Data][badge-085]][resource-418]</span><br>[详情](#paper-moh2025) |
| 2025 · Technical report | <a id="entry-novikov2025alphaevolve"></a>**AlphaEvolve**<br>AlphaEvolve: A coding agent for scientific and algorithmic discovery | 用 LLM 与进化式代码修改闭环改进算法，覆盖科学问题及计算基础设施优化。 | 方法 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-419]</span><br><span title="官方结果（相关）">[![官方结果（相关）][badge-086]][resource-420]</span><br><span title="官方问题集（相关）">[![官方问题集（相关）][badge-087]][resource-421]</span><br>[详情](#paper-novikov2025alphaevolve) |


[返回目录](#contents)

<a id="solver-enhancement"></a>

### 求解器组件增强与配置

改进割平面、分支与节点选择、传播、求解器配置及既有模型的求解效率。

#### 割平面

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · IJCAI 2026 · AI4Tech | <a id="entry-zheng2026cutmgmt"></a>**LLM-guided Cutting-plane Management**<br>LLM-guided Cutting-plane Management for Mixed-integer Linear Programming | 结合实例级分离器配置与求解阶段感知的割选择，减少 MILP 求解中的人工调参。 | 方法 | [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-422]</span><br><span title="Code">[![Code][badge-008]][resource-423]</span><br>[详情](#paper-zheng2026cutmgmt) |
| 2026 · arXiv preprint | <a id="entry-milpevo2026"></a>**MILP-Evo**<br>MILP-Evo: Closed-Loop Fully Automatic Design of MILP Solvers | 在 PySCIPOpt 中联合演化割选择与分支回调，结合执行修复、诊断反思和多样性维护。 | 方法 | [Program evolution](#tech-evolution) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-424]</span><br>[详情](#paper-milpevo2026) |
| 2025 · arXiv（SAGE 修订版 2026） | <a id="entry-yazdani2025evocut"></a>**SAGE / 原 EvoCut**<br>LLM-Guided Evolution of Symbolic Acceleration Inequality Families for MILP | 用 LLM 与演化搜索发现可复用的 MILP 加速不等式，并按经验可接受性及性能筛选。 | 方法 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-425]</span><br><span title="Code（EvoCut 旧版）">[![Code（EvoCut 旧版）][badge-088]][resource-426]</span><br><span title="Code（SAGE v3）">[![Code（SAGE v3）][badge-089]][resource-427]</span><br>[详情](#paper-yazdani2025evocut) |

**相关工作：** [Cold-Start Separator Configuration](#entry-lawless2024cuts)

#### 分支与节点选择

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-bife2026"></a>**BiFE**<br>BiFE: Search-Efficient Discovery of CPU-Only Branching Policies via LLM-based Bi-Fidelity Evolution | 用低保真模仿评分预筛分支规则，再对精英候选运行高保真 B&B 评估。 | 方法 | [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-428]</span><br>[详情](#paper-bife2026) |
| 2026 · arXiv preprint | <a id="entry-chen2026evobb"></a>**Evo-B&B**<br>Evo-B&B: Behavior-Aware LLM-Guided Joint Evolution of Branching and Node Selection Policies for MILP | 用 SCIP 端到端反馈联合演化分支与节点选择策略，并按行为相似性维护多样性。 | 方法 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-429]</span><br>[详情](#paper-chen2026evobb) |
| 2026 · ICML 2026 | <a id="entry-llm4branch2026"></a>**LLM4Branch**<br>LLM4Branch: Large Language Model for Discovering Efficient Branching Policies of Integer Programs | 让 LLM 生成分支策略程序骨架，再用端到端求解反馈优化参数。 | 方法 | [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-430]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-431]</span><br><span title="Code">[![Code][badge-008]][resource-432]</span><br>[详情](#paper-llm4branch2026) |

**相关工作：** [MILP-Evo](#entry-milpevo2026)

#### 求解器配置与算法选择

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-luo2026grimip"></a>**GRIMIP**<br>GRIMIP: A General Framework for Instance-Specific Configuration of MIP Solvers Using LLMs | 将 LLM 作为贝叶斯优化中的概率代理，为具体 MIP 实例搜索求解器配置。 | 方法 | [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-433]</span><br>[详情](#paper-luo2026grimip) |
| 2026 · NeurIPS 2026 MLxOR Workshop（已接收，待召开） | <a id="entry-zhang2026autoconfig"></a>**LLM MIP Configuration**<br>Automating MIP Solver Configuration with Large Language Models | 根据求解器反馈迭代提出 MIP 参数设置，并聚合为问题类级别配置。 | 方法 | [Execution / solver feedback](#tech-solver-feedback) | <span title="Paper">[![Paper][badge-007]][resource-434]</span><br>[详情](#paper-zhang2026autoconfig) |
| 2026 · arXiv preprint | <a id="entry-warehouseformsel2026"></a>**Multi-Warehouse Formulation Selection**<br>Large Language Model for Operations Research Formulation Selection in Multi-Warehouse Inventory Allocation | 在多仓库存分配中选择适合实例的 MIP 公式专家，并用求解质量反馈训练选择器。 | 方法 · 模型 · 应用 | [SFT / distillation](#tech-sft) · [Preference optimization](#tech-preference) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-435]</span><br>[详情](#paper-warehouseformsel2026) |
| 2025 · CPAIOR 2025 | <a id="entry-lawless2024cuts"></a>**Cold-Start Separator Configuration**<br>LLMs for Cold-Start Cutting Plane Separator Configuration | 根据问题描述及分离器文档生成配置，再聚类集成为小规模配置组合。 | 方法 | [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-436]</span><br><span title="DOI">[![DOI][badge-001]][resource-437]</span><br><span title="Code">[![Code][badge-008]][resource-438]</span><br>[详情](#paper-lawless2024cuts) |
| 2025 · EMNLP 2025 | <a id="entry-yuan2025magts"></a>**MA-GTS / G-REAL**<br>MA-GTS: A Multi-Agent Framework for Solving Complex Graph Problems in Real-World Applications | 从隐式文本图信息恢复结构化图，并用多 Agent 根据问题约束及规模选择算法。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | <span title="arXiv">[![arXiv][badge-002]][resource-439]</span><br><span title="Proceedings">[![Proceedings][badge-005]][resource-440]</span><br><span title="Code">[![Code][badge-008]][resource-441]</span><br>[详情](#paper-yuan2025magts) |

**相关工作：** [LLM-guided Cutting-plane Management](#entry-zheng2026cutmgmt)

#### 模型重构与预处理

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | **EvoOpt-LLM**<br>EvoOpt-LLM: Evolving industrial optimization models with large language models | 以 7B 模型和 LoRA 支持工业 MILP 的模型构建、新业务约束注入与变量剪枝。 | 方法 · 模型 | [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-029]</span><br><span title="Code">[![Code][badge-008]][resource-030]</span><br>[详情](#paper-he2026evoopt) |
| 2026 · EMNLP 2026 | <a id="entry-yuan2026formuevo"></a>**FormuEvo**<br>FormuEvo: LLM-Guided Evolution for Discovering Solver-Efficient Mixed-Integer Programming Formulations | 在建模程序空间演化更强的 MIP 表达，以求解器统计诊断和结构化记忆指导改写。 | 方法 | [Program evolution](#tech-evolution) · [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-442]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-443]</span><br><span title="Code">[![Code][badge-008]][resource-444]</span><br>[详情](#paper-yuan2026formuevo) |

#### 传播与其他求解组件

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-xu2026agenticmip"></a>**Agentic MIP Research**<br>Agentic MIP Research: Accelerated Constraint Handler Generation | 用求解器感知的 Agent 工作环境恢复全局约束结构，并生成 SCIP 传播型约束处理器。 | 方法 | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-445]</span><br>[详情](#paper-xu2026agenticmip) |
| 2026 · Nature Communications（2026） | <a id="entry-sun2025satheur"></a>**AutoModSAT**<br>Discovering heuristics in a complex SAT solver with large language models | 结合模块化 SAT 求解器、提示优化和进化搜索，发现复杂求解器中的有效启发式。 | 方法 · 数据 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Journal">[![Journal][badge-017]][resource-446]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-447]</span><br><span title="Code Archive">[![Code Archive][badge-090]][resource-448]</span><br><span title="Evaluation Data">[![Evaluation Data][badge-091]][resource-449]</span><br>[详情](#paper-sun2025satheur) |
| 2026 · JAIR | <a id="entry-sun2024autosat"></a>**AutoSAT**<br>AutoSAT: Automatically Optimize SAT Solvers via Large Language Models | 在模块化 CDCL 求解器中搜索并替换启发式，以 LLM 生成代码并迭代评估。 | 方法 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-450]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-451]</span><br><span title="Code">[![Code][badge-008]][resource-452]</span><br>[详情](#paper-sun2024autosat) |
| 2025 · arXiv preprint | <a id="entry-dheevo2025"></a>**DHEvo**<br>DHEvo: Data-Algorithm Based Heuristic Evolution for Generalizable MILP Solving | 共同演化代表性实例与 diving 启发式，提高同类 MILP 实例内的泛化能力。 | 方法 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-453]</span><br>[详情](#paper-dheevo2025) |


[返回目录](#contents)

<a id="benchmarks"></a>

## Benchmarks 与评测

引入基准、评测数据、评分协议或系统性评测分析；按评测对象细分。

### 建模与代码生成评测

| 年份 / Venue | 论文 | 评测内容 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · arXiv preprint | **AutoREM / AutoRO-Bench**<br>Automated Reformulation of Robust Optimization via Memory-Augmented Large Language Models | AutoRO-Bench 覆盖鲁棒优化的核心变换和应用问题，评测不确定模型到确定性形式的重构。 | 方法 · 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-203]</span><br>[详情](#paper-robustreform2026) |
| 2026 · LION 19 / LNCS 15745（2026 出版） | **CHORUS**<br>CHORUS: Zero-shot Hierarchical Retrieval and Orchestration for Generating Linear Programming Code | NL4Opt-Code 为 NL4Opt 扩展 Gurobi 代码标注，以执行目标值和代码指标评测 LP 程序生成。 | 方法 · 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-115]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-116]</span><br>[详情](#paper-lporch2025) |
| 2026 · arXiv preprint | **CIR / R2C**<br>Canonical Intermediate Representation for LLM-based optimization problem formulation and code generation | 规则密集的建模评测集检验复杂业务规则的表示及约束实现，比较直接生成与中间表示流程。 | 方法 · 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-117]</span><br>[详情](#paper-canonicalir2026) |
| 2026 · Findings of EMNLP 2026 | **Constraint Injection / VRPCoder**<br>Beyond Objective Equivalence: Constraint Injection for LLM-Based Optimization Modeling on Vehicle Routing Problems | VRPBench 用可行解与单约束违反解检查 VRP 代码，检验目标值匹配难以发现的漏约束。 | 方法 · 基准 · 数据 · 模型 · 应用 | <span title="Proceedings">[![Proceedings][badge-005]][resource-259]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-260]</span><br><span title="Benchmark Data">[![Benchmark Data][badge-066]][resource-261]</span><br>[详情](#paper-constraintinjection2026) |
| 2026 · arXiv preprint | **CP-SynC**<br>CP-SynC: Multi-Agent Zero-Shot Constraint Modeling in MiniZinc with Synthesized Checkers | CP-SynC Benchmark 评测自然语言到 MiniZinc 的约束建模，以执行及合成语义检查器提供反馈。 | 方法 · 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-213]</span><br><span title="Benchmark &amp; Evaluation">[![Benchmark & Evaluation][badge-051]][resource-214]</span><br>[详情](#paper-cpsync2026) |
| 2026 · arXiv；NeurIPS 2026 Workshop 版本 | <a id="entry-wang2026formalize"></a>**Formalize, Don't Optimize**<br>Formalize, Don't Optimize: The Heuristic Trap in LLM-Generated Combinatorial Solvers | CP-SynC-XL 比较原生搜索、Python 求解器 API 与 MiniZinc，并审计搜索优化造成的正确性损失。 | 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-454]</span><br><span title="Workshop">[![Workshop][badge-092]][resource-455]</span><br>[详情](#paper-wang2026formalize) |
| 2026 · arXiv preprint | <a id="entry-jorbench2026"></a>**JOR-Bench**<br>JOR-Bench: Japanese Operations Research Benchmarks for Large Language Models | JOR-Bench 将五组既有英文 OR 评测译为日文，在统一执行设置下比较跨语言建模与求解。 | 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-456]</span><br><span title="Japanese / English OR Data">[![Japanese / English OR Data][badge-093]][resource-457]</span><br>[详情](#paper-jorbench2026) |
| 2026 · arXiv preprint | **LEAN-LLM-OPT**<br>Large-Scale Optimization Model Auto-Formulation: Harnessing LLM Flexibility via Structured Workflow | Large-Scale-OR 与 Air-NRM 分别面向大规模优化和航空收入管理，检验数据处理、建模与求解工作流。 | 方法 · 基准 · 数据 · 应用 | <span title="arXiv">[![arXiv][badge-002]][resource-120]</span><br><span title="Code">[![Code][badge-008]][resource-121]</span><br>[详情](#paper-liang2026leanllmopt) |
| 2026 · ICML 2026 | <a id="entry-li2026miplibnl"></a>**MIPLIB-NL**<br>Constructing Industrial-Scale Optimization Modeling Benchmark | MIPLIB-NL 从 MIPLIB 2017 恢复工业 MILP 的结构与数据对应关系，评测大规模自然语言建模。 | 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-458]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-459]</span><br><span title="Code">[![Code][badge-008]][resource-460]</span><br><span title="GitHub dataset">[![GitHub dataset][badge-094]][resource-461]</span><br>[详情](#paper-li2026miplibnl) |
| 2026 · NeurIPS 2026（已接收，待出版） | <a id="entry-zhu2026mmoptbench"></a>**MM-OptBench**<br>MM-OptBench: A Solver-Grounded Benchmark for Multimodal Optimization Modeling | MM-OptBench 结合文本、表格、图与地图，借助隐藏参考文件诊断信息抽取和约束建模错误。 | 基准 · 数据 | <span title="Paper">[![Paper][badge-007]][resource-462]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-463]</span><br>[详情](#paper-zhu2026mmoptbench) |
| 2026 · ICML 2026 | <a id="entry-chen2026optengine"></a>**OPT-Engine**<br>OPT-Engine: Benchmarking the Limits of LLMs in Optimization Modeling via Complexity Scaling | C³-Bench 覆盖十类典型 OR 问题，控制复杂度并施加语言与参数扰动，比较推理、工具与求解器策略。 | 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-464]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-465]</span><br><span title="Code">[![Code][badge-008]][resource-466]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-467]</span><br>[详情](#paper-chen2026optengine) |
| 2026 · arXiv preprint | **OptiDSL**<br>Not All Problems Are Best Modeled as MILP: A DSL-Centric Framework for Flexible and Accurate Optimization Modeling | 覆盖 44 类 COP 的评测集比较自然语言建模与执行，考察 DSL 及不同求解器范式的适用性。 | 方法 · 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-129]</span><br>[详情](#paper-dslmilp2026) |
| 2026 · Findings of ACL 2026 | **OptiVerse / DVA-Agent**<br>OptiVerse: A Comprehensive Benchmark towards Optimization Problem Solving | OptiVerse 覆盖随机、动态、控制和博弈等多范式任务，评测建模求解及需求—代码语义一致性。 | 方法 · 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-239]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-240]</span><br><span title="Inference, Auditor &amp; Evaluation">[![Inference, Auditor & Evaluation][badge-060]][resource-241]</span><br><span title="OptiVerse 1K">[![OptiVerse 1K][badge-061]][resource-242]</span><br>[详情](#paper-optiverse2026) |
| 2026 · Artificial Intelligence for Transportation | **ORThought / LogiOR**<br>ORThought: Benchmarking and automating logistics optimization modeling via structured LLM reasoning | LogiOR 提供精细标注的物流建模题，并统一既有数据标注，支持复杂约束、错误类型与 token 效率分析。 | 方法 · 基准 · 数据 | <span title="DOI">[![DOI][badge-001]][resource-043]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-044]</span><br><span title="Code">[![Code][badge-008]][resource-045]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-046]</span><br>[详情](#paper-yang2025orthought) |
| 2026 · ICML 2026 | <a id="entry-shen2026proopf"></a>**ProOPF**<br>ProOPF: Benchmarking and Improving LLMs for Professional-Grade Power Systems Optimization Modeling | ProOPF-B 为最优潮流专家测试集，分别检验参数调整与结构扩展；ProOPF-D 用于训练。 | 基准 · 数据 · 应用 | <span title="Proceedings">[![Proceedings][badge-005]][resource-468]</span><br><span title="Proceedings">[![Proceedings][badge-005]][resource-469]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-470]</span><br><span title="Evaluation Code &amp; Data">[![Evaluation Code & Data][badge-029]][resource-471]</span><br>[详情](#paper-shen2026proopf) |
| 2026 · NeurIPS 2026（已接收，待出版） | **ReLoop / RetailOpt-190**<br>ReLoop: Structured Modeling and Behavioral Verification for Reliable LLM-Based Optimization | RetailOpt-190 用于静默建模错误诊断与修复；参数扰动检查关注行为响应而非仅执行成功。 | 方法 · 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-264]</span><br><span title="Proceedings">[![Proceedings][badge-005]][resource-265]</span><br><span title="Code">[![Code][badge-008]][resource-266]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-267]</span><br>[详情](#paper-lian2026reloop) |
| 2025 · ACL 2025 | **BPP-Search / StructuredOR**<br>BPP-Search: Enhancing Tree of Thought Reasoning for Mathematical Modeling Problem Solving | StructuredOR 包含建模过程标注，支持逐步推理、过程奖励与最终建模结果的评测。 | 方法 · 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-059]</span><br><span title="Code">[![Code][badge-008]][resource-060]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-061]</span><br>[详情](#paper-wang2025bppsearch) |
| 2025 · ECAI 2025 | <a id="entry-michailidis2025cpbench"></a>**CP-Bench / DCP-Bench-Open**<br>CP-Bench: Evaluating Large Language Models for Constraint Modelling | CP-Bench 原版与 DCP-Bench-Open 扩展版评测多领域离散约束建模；题目与评测结果按各版本区分。 | 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-472]</span><br><span title="Related version">[![Related version][badge-095]][resource-473]</span><br><span title="DOI">[![DOI][badge-001]][resource-474]</span><br><span title="Code（当前扩展版）">[![Code（当前扩展版）][badge-096]][resource-475]</span><br><span title="Dataset（原版归档）">[![Dataset（原版归档）][badge-097]][resource-476]</span><br><span title="CP-Bench 原版归档">[![CP-Bench 原版归档][badge-098]][resource-477]</span><br>[详情](#paper-michailidis2025cpbench) |
| 2025 · arXiv preprint | **DAOpt / OptU**<br>DAOpt: Modeling and Evaluation of Data-Driven Optimization under Uncertainty with LLMs | OptU 结合不确定性问题与仿真环境，以样本外可行性和稳健性补充确定性目标值评价。 | 方法 · 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-204]</span><br>[详情](#paper-daopt2025) |
| 2025 · arXiv preprint | **DPLM / DP-Bench**<br>Auto-Formulating Dynamic Programming Problems with Large Language Models | DP-Bench 评测自然语言到动态规划模型的构造，关注状态、转移与递推等建模要素。 | 方法 · 基准 · 数据 · 模型 | <span title="arXiv">[![arXiv][badge-002]][resource-225]</span><br>[详情](#paper-dpdlm2025) |
| 2025 · ICLR 2025 | **DRoC**<br>DRoC: Elevating Large Language Models for Complex Vehicle Routing via Decomposed Retrieval of Constraints | 发布复杂 VRP 评测实例，用于比较含多种约束的求解器程序生成与求解表现。 | 方法 · 数据 · 应用 | <span title="Proceedings">[![Proceedings][badge-005]][resource-153]</span><br><span title="Proceedings">[![Proceedings][badge-005]][resource-154]</span><br><span title="Code">[![Code][badge-008]][resource-155]</span><br>[详情](#paper-jiang2025droc) |
| 2025 · Findings NAACL 2025 | <a id="entry-huang2024mamo"></a>**Mamo**<br>LLMs for Mathematical Modeling: Towards Bridging the Gap between Natural and Mathematical Languages | Mamo 以求解器输出对照参考结果，评测 LP、MILP 与 ODE 的数学建模；ODE 部分属于邻近数学任务。 | 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-478]</span><br><span title="Proceedings">[![Proceedings][badge-005]][resource-479]</span><br><span title="Code">[![Code][badge-008]][resource-480]</span><br><span title="Dataset（第三方镜像）">[![Dataset（第三方镜像）][badge-012]][resource-481]</span><br>[详情](#paper-huang2024mamo) |
| 2025 · ICML 2025 | **OptMATH**<br>OptMATH: A Scalable Bidirectional Data Synthesis Framework for Optimization Modeling | OptMATH-Bench 从合成流程中筛出困难建模题，包含比 NL4Opt、Mamo 更长的问题描述。 | 方法 · 基准 · 数据 · 模型 | <span title="Proceedings">[![Proceedings][badge-005]][resource-070]</span><br><span title="Code">[![Code][badge-008]][resource-071]</span><br><span title="Model 7B">[![Model 7B][badge-015]][resource-072]</span><br><span title="Model 32B">[![Model 32B][badge-016]][resource-073]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-074]</span><br>[详情](#paper-lu2025optmath) |
| 2025 · arXiv preprint | **OR-LLM-Agent / BWOR**<br>OR-LLM-Agent: Automating Modeling and Solving of Operations Research Optimization Problems with Reasoning LLM | BWOR 面向 OR 建模与求解，重点比较推理模型和非推理模型的能力差异及评测区分度。 | 方法 · 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-162]</span><br><span title="Code">[![Code][badge-008]][resource-163]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-164]</span><br>[详情](#paper-zhang2025bwor) |
| 2025 · Operations Research | **ORLM**<br>ORLM: A Customizable Framework in Training Large Models for Automated Optimization Modeling | IndustryOR 面向实际工业优化问题，补充 NL4Opt、Mamo 等基准对建模与求解能力的评测。 | 方法 · 基准 · 数据 · 模型 | <span title="arXiv">[![arXiv][badge-002]][resource-075]</span><br><span title="Journal">[![Journal][badge-017]][resource-076]</span><br><span title="Code">[![Code][badge-008]][resource-077]</span><br><span title="Model">[![Model][badge-014]][resource-078]</span><br><span title="IndustryOR">[![IndustryOR][badge-018]][resource-079]</span><br><span title="OR-Instruct-3K">[![OR-Instruct-3K][badge-019]][resource-080]</span><br>[详情](#paper-huang2025orlm) |
| 2025 · AAAI 2025 | <a id="entry-mostajabdaveh2025orqa"></a>**ORQA**<br>Evaluating LLM Reasoning in the Operations Research Domain with ORQA | ORQA 用专家设计的优化建模问答评测 OR 知识与多步推理，评测对象为问答而非完整求解器程序。 | 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-482]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-483]</span><br><span title="Code">[![Code][badge-008]][resource-484]</span><br>[详情](#paper-mostajabdaveh2025orqa) |
| 2025 · ICLR 2025 | **ReSocratic / OptiBench**<br>OptiBench Meets ReSocratic: Measure and Improve LLMs for Optimization Modeling | OptiBench 覆盖含或不含表格数据的线性与非线性优化，要求调用代码求解器输出数值答案。 | 方法 · 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-081]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-082]</span><br><span title="Code">[![Code][badge-008]][resource-083]</span><br>[详情](#paper-yang2025resocratic) |
| 2025 · arXiv preprint | **Teaching LLMs to Think Mathematically**<br>Teaching LLMs to Think Mathematically: A Critical Study of Decision-Making via Optimization | 在新构造的计算机网络优化题中比较三种提示策略，同时考察最优性差距、符号表达与编译表现。 | 综述 · 评测分析 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-019]</span><br>[详情](#paper-abedi2025thinkmath) |
| 2025 · arXiv preprint | <a id="entry-singirikonda2025text2zinc"></a>**Text2Zinc**<br>Text2Zinc: A Cross-Domain Dataset for Modeling Optimization and Satisfaction Problems in MiniZinc | Text2Zinc 以 MiniZinc 表示跨领域约束满足与优化任务，评测自然语言到求解器无关模型的转换。 | 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-485]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-218]</span><br><span title="作者项目门户（相关）">[![作者项目门户（相关）][badge-057]][resource-223]</span><br>[详情](#paper-singirikonda2025text2zinc) |
| 2025 · Preprint | <a id="entry-parashar2025wiqor"></a>**WIQOR**<br>WIQOR: A dataset for what-if analysis of Operations Research problems | WIQOR 评测根据 what-if 请求修改既有数学规划模型，任务材料源于 NL4Opt。 | 基准 · 数据 | <span title="PDF">[![PDF][badge-073]][resource-486]</span><br><span title="Institution record">[![Institution record][badge-099]][resource-487]</span><br>[详情](#paper-parashar2025wiqor) |
| 2024 · ICLR 2024 | **Chain-of-Experts**<br>Chain-of-Experts: When LLMs Meet Complex Operations Research Problems | ComplexOR 补充复杂 OR 问题，联合 LPWP 评测从自然语言到数学模型及求解器程序的能力。 | 方法 · 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-087]</span><br><span title="Code">[![Code][badge-008]][resource-088]</span><br>[详情](#paper-xiao2024coe) |
| 2024 · INFOR | **LM4OPT**<br>LM4OPT: Unveiling the potential of Large Language Models in formulating mathematical optimization problems | 基于既有 NL4Opt 比较 LP 建模、零样本与单样本提示，以及渐进微调对不同规模模型的效果。 | 方法 · 模型 · 评测分析 | <span title="DOI">[![DOI][badge-001]][resource-089]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-090]</span><br>[详情](#paper-ahmed2024lm4opt) |
| 2024 · INFOR | **Multi-Stage Modeling & Verification**<br>Optimization modeling and verification from problem specifications using a multi-agent multi-stage LLM framework | 专用评测集以结构化问题规格表示优化任务，支持多阶段建模与细粒度模型评价。 | 方法 · 基准 · 数据 | <span title="DOI">[![DOI][badge-001]][resource-181]</span><br>[详情](#paper-mostajabdaveh2024multiagent) |
| 2024 · ICML 2024 | **OptiMUS**<br>OptiMUS: Scalable Optimization Modeling with (MI)LP Solvers and Large Language Models | NLP4LP 提供长描述、复杂数据的优化问题，评测 MILP 建模、代码执行和求解结果。 | 方法 · 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-182]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-183]</span><br><span title="Code">[![Code][badge-008]][resource-184]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-185]</span><br>[详情](#paper-teshnizi2024optimus) |
| 2023 · NeurIPS 2022 Competition Track / PMLR 220 | <a id="entry-ramamonjison2023nl4opt"></a>**NL4Opt**<br>NL4Opt Competition: Formulating Optimization Problems Based on Their Natural Language Descriptions | NL4Opt 将 LP 文字题分为实体识别和中间形式生成两项任务，分别评测建模要素抽取与形式化能力。 | 基准 · 数据 · 基础 | <span title="Proceedings">[![Proceedings][badge-005]][resource-488]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-489]</span><br><span title="Code">[![Code][badge-008]][resource-112]</span><br>[详情](#paper-ramamonjison2023nl4opt) |
| 2022 · EMNLP 2022 Industry | **Auto-formulation (2022)**<br>Augmenting Operations Research with Auto-Formulation of Optimization Models From Problem Descriptions | LPWP 提供跨领域 LP 文字题，评测从问题描述生成优化模型，并支持用户交互校验与修改。 | 方法 · 基准 · 数据 · 基础 | <span title="Proceedings">[![Proceedings][badge-005]][resource-111]</span><br><span title="Code &amp; Data（NL4Opt）">[![Code & Data（NL4Opt）][badge-029]][resource-112]</span><br>[详情](#paper-ramamonjison2022augmenting) |

### 验证、解释与修复评测

| 年份 / Venue | 论文 | 评测内容 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · arXiv preprint | **OptArgus**<br>OptArgus: A Multi-Agent System to Detect Hallucinations in LLM-based Optimization Modeling | OptArgus 的三部分评测套件检查问题描述、数学模型和代码间的幻觉与不一致。 | 方法 · 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-238]</span><br>[详情](#paper-optarcus2026) |
| 2026 · INFORMS Journal on Data Science | **OptiChat**<br>OptiChat: Bridging Optimization Models and Practitioners with Large Language Models | 模型解释问答集覆盖不可行诊断、敏感性、what-if 与反事实问题，评测已有模型的交互式解释。 | 方法 · 数据 | <span title="DOI">[![DOI][badge-001]][resource-189]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-190]</span><br><span title="Code">[![Code][badge-008]][resource-191]</span><br>[详情](#paper-chen2025optichat) |
| 2026 · arXiv preprint | **OptiRepair**<br>OptiRepair: Closed-Loop Diagnosis and Repair of Supply Chain Optimization Models with LLM Agents | OptiRepair-SC 评测多级供应链模型修复，分别检查可行性恢复与库存理论支持的运营合理性。 | 方法 · 基准 · 数据 · 模型 · 应用 | <span title="arXiv">[![arXiv][badge-002]][resource-227]</span><br>[详情](#paper-optirepair2026) |
| 2026 · ICML 2026 | **ORLoopBench**<br>ORLoopBench: Solver-in-the-Loop Benchmarks for Self-Correction and Behavioral Rationality in Operations Research | ORDebug 与 ORBias 分别检验不可行模型修复与决策合理性，使用 IIS、求解器重执行及校验脚本。 | 方法 · 基准 · 数据 · 模型 | <span title="Proceedings">[![Proceedings][badge-005]][resource-228]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-229]</span><br><span title="数据与校验代码">[![数据与校验代码][badge-058]][resource-230]</span><br>[详情](#paper-ao2026orloopbench) |
| 2026 · Findings of EMNLP 2026 | **SOVER / NLEquiv-150**<br>SOVER: Formal Certification of Optimization Reformulations via LLM-Assisted SMT Verification | NLEquiv-150 包含非线性等价与非等价样本，评测由重构映射及 Z3／dReal 支持的条件性公式核验。 | 方法 · 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-246]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-247]</span><br><span title="Code">[![Code][badge-008]][resource-248]</span><br><span title="EquivaFormulation（使用）（相关）">[![EquivaFormulation（使用）（相关）][badge-062]][resource-249]</span><br><span title="NLP4LP（使用）（相关）">[![NLP4LP（使用）（相关）][badge-063]][resource-185]</span><br>[详情](#paper-bhattacharyya2026sover) |
| 2025 · ICLR 2025 | **EOR / Decision Information**<br>Decision Information Meets Large Language Models: The Future of Explainable Operations Research | 工业解释评测集考察 what-if 模型变更及其决策信息，结合结构变化衡量解释的实用性。 | 方法 · 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-231]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-232]</span><br><span title="Code">[![Code][badge-008]][resource-233]</span><br>[详情](#paper-zhang2025decisioninfo) |
| 2025 · ICML 2025 | **EquivaMap**<br>EquivaMap: Leveraging LLMs for Automatic Equivalence Checking of Optimization Formulations | EquivaFormulation 通过变换构造等价公式，评测变量映射是否保持可行性与最优性。 | 方法 · 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-254]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-255]</span><br><span title="Code">[![Code][badge-008]][resource-256]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-249]</span><br>[详情](#paper-zhai2025equivamap) |
| 2025 · arXiv preprint | **MOID**<br>Multi-Objective Infeasibility Diagnosis for Routing Problems Using Large Language Models | 路由诊断案例联合路径成本与约束违反量，比较不同可行性恢复方案的权衡。 | 方法 · 数据 · 应用 | <span title="arXiv">[![arXiv][badge-002]][resource-234]</span><br><span title="Diagnosis Data">[![Diagnosis Data][badge-059]][resource-235]</span><br>[详情](#paper-moid2025) |
| 2025 · arXiv；相关 ICML 2026 Workshop 版本 | **ORGEval / Bench4Opt**<br>ORGEval: Graph-Theoretic Evaluation of LLMs in Optimization Modeling | Bench4Opt 配套图结构等价性评测；WL 测试的保证限于对称可分解等条件，区别于目标值匹配。 | 方法 · 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-257]</span><br><span title="ICML workshop poster（相关）">[![ICML workshop poster（相关）][badge-065]][resource-258]</span><br>[详情](#paper-ding2026orgeval) |

**相关工作：** [Constraint Injection / VRPCoder](#entry-constraintinjection2026) · [Formalize, Don't Optimize](#entry-wang2026formalize) · [ReLoop / RetailOpt-190](#entry-lian2026reloop)

### 直接求解与决策评测

| 年份 / Venue | 论文 | 评测内容 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-constraintbench2026"></a>**ConstraintBench**<br>ConstraintBench: Benchmarking LLM Constraint Reasoning on Direct Optimization | ConstraintBench 要求直接输出结构化解，以确定性校验器逐约束检查，并与 Gurobi 参考最优解比较。 | 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-490]</span><br>[详情](#paper-constraintbench2026) |
| 2026 · ICML 2026 | <a id="entry-dynaschedbench2026"></a>**DynaSchedBench**<br>DynaSchedBench: Calibrated Dynamic Scheduling Benchmarks and Observability Paradox in LLM-based Scheduling Agents | DynaSchedBench 校准动态柔性车间实例，统一仿真、轨迹评测和不同观测条件下的 Agent 比较。 | 方法 · 基准 · 数据 · 应用 | <span title="Proceedings">[![Proceedings][badge-005]][resource-491]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-492]</span><br><span title="Code">[![Code][badge-008]][resource-493]</span><br><span title="Project（相关）">[![Project（相关）][badge-057]][resource-494]</span><br>[详情](#paper-dynaschedbench2026) |
| 2026 · arXiv preprint | **GenAI Beer Game Reliability**<br>Reliability and Effectiveness of Autonomous AI Agents in Supply Chain Management | 多级 Beer Game 实验考察平均成本、运行间波动与尾部风险，比较后训练和运营护栏的可靠性。 | 方法 · 评测分析 · 应用 | <span title="arXiv">[![arXiv][badge-002]][resource-284]</span><br>[详情](#paper-beergame2026) |
| 2026 · arXiv preprint | <a id="entry-invbench2026"></a>**InventoryBench**<br>AI Agents for Inventory Control: Human-LLM-OR Complementarity | InventoryBench 与人机库存游戏分别提供算法评测和人类实验，研究 OR、LLM 与人工决策的互补性。 | 方法 · 基准 · 数据 · 应用 | <span title="arXiv">[![arXiv][badge-002]][resource-495]</span><br><span title="InventoryBench">[![InventoryBench][badge-100]][resource-496]</span><br><span title="人机实验平台">[![人机实验平台][badge-101]][resource-497]</span><br>[详情](#paper-invbench2026) |
| 2026 · Findings of ACL 2026 | <a id="entry-jiang2026nlco"></a>**NLCO**<br>Reasoning in a Combinatorial and Constrained World: Benchmarking LLMs on Natural-Language Combinatorial Optimization | NLCO 要求从自然语言直接生成离散解，以求解器标注联合衡量可行性、解质量和推理效率。 | 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-498]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-499]</span><br><span title="Code">[![Code][badge-008]][resource-500]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-501]</span><br>[详情](#paper-jiang2026nlco) |
| 2026 · arXiv preprint | <a id="entry-opf2026reason"></a>**OPF Constrained Reasoning Study**<br>Can Large Language Models Reason and Optimize Under Constraints? | 在最优潮流任务中改变推理难度，检验结构化输入理解、算术计算及物理约束下的优化能力。 | 评测分析 | <span title="arXiv">[![arXiv][badge-002]][resource-502]</span><br>[详情](#paper-opf2026reason) |
| 2026 · arXiv preprint | **PowerAtlas / ECBench**<br>PowerAtlas: Feasibility-Aware Language Models for Electricity-Computing Co-Scheduling | ECBench 评测电力—计算联合排程，以确定性评分及 Gurobi 参考区分约束可行性与决策质量。 | 方法 · 基准 · 数据 · 模型 · 应用 | <span title="arXiv">[![arXiv][badge-002]][resource-270]</span><br><span title="Code &amp; Sample Data">[![Code & Sample Data][badge-068]][resource-271]</span><br>[详情](#paper-jiang2026poweratlas) |
| 2026 · arXiv preprint | <a id="entry-zhang2026retailbench"></a>**RetailBench**<br>RetailBench: Evaluating Long-Horizon Autonomous Decision-Making and Strategy Stability of LLM Agents in Realistic Retail Environments | RetailBench 在单店超市仿真中联合考察定价、补货与现金流决策，衡量生存、资产和策略稳定性。 | 基准 · 数据 · 平台 | <span title="arXiv">[![arXiv][badge-002]][resource-503]</span><br><span title="Code">[![Code][badge-008]][resource-504]</span><br>[详情](#paper-zhang2026retailbench) |
| 2025 · arXiv preprint | <a id="entry-zhao2025aimbench"></a>**AIM-Bench**<br>AIM-Bench: Evaluating Decision-making Biases of Agentic LLM as Inventory Manager | AIM-Bench 在不确定库存实验中检验决策偏差、信息共享、向中心偏移与牛鞭效应。 | 基准 · 数据 · 评测分析 | <span title="arXiv">[![arXiv][badge-002]][resource-505]</span><br>[详情](#paper-zhao2025aimbench) |
| 2025 · EMNLP 2025 | **MA-GTS / G-REAL**<br>MA-GTS: A Multi-Agent Framework for Solving Complex Graph Problems in Real-World Applications | G-REAL 以含隐式图信息的真实场景文本评测图恢复、约束理解及算法选择，覆盖较广的图任务。 | 方法 · 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-439]</span><br><span title="Proceedings">[![Proceedings][badge-005]][resource-440]</span><br><span title="Code">[![Code][badge-008]][resource-441]</span><br>[详情](#paper-yuan2025magts) |
| 2025 · arXiv preprint | **Visual Graph Optimization with MLLMs**<br>Bridging Visualization and Optimization: Multimodal Large Language Models on Graph-Structured Combinatorial Optimization | 以图像呈现图结构，比较多模态 LLM 在影响最大化、网络拆解等图优化任务上的表现。 | 方法 · 评测分析 | <span title="arXiv">[![arXiv][badge-002]][resource-282]</span><br>[详情](#paper-bridgingviz2025) |

### 算法与求解器效率评测

| 年份 / Venue | 论文 | 评测内容 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · Nature Communications（2026） | **AutoModSAT**<br>Discovering heuristics in a complex SAT solver with large language models | 在生成实例和工业 EDA 任务上评测演化的 SAT 启发式，考察复杂求解器中的有效性与泛化。 | 方法 · 数据 | <span title="Journal">[![Journal][badge-017]][resource-446]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-447]</span><br><span title="Code Archive">[![Code Archive][badge-090]][resource-448]</span><br><span title="Evaluation Data">[![Evaluation Data][badge-091]][resource-449]</span><br>[详情](#paper-sun2025satheur) |
| 2026 · AAAI 2026 | <a id="entry-sun2026cobench"></a>**CO-Bench**<br>CO-Bench: Benchmarking Language Model Agents in Algorithm Search for Combinatorial Optimization | CO-Bench 提供结构化组合优化问题与数据，比较 LLM Agent 和人工设计算法的求解表现。 | 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-506]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-507]</span><br><span title="Code">[![Code][badge-008]][resource-508]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-509]</span><br>[详情](#paper-sun2026cobench) |
| 2026 · Inteligencia Artificial | **Combinatorial Optimization for All**<br>Combinatorial Optimization for All: Using LLMs to Aid Non-Experts in Improving Optimization Algorithms | 对十种既有 TSP 算法进行提示改写实验，联合比较解质量、运行时间和代码复杂度。 | 方法 · 评测分析 | <span title="Journal">[![Journal][badge-017]][resource-311]</span><br><span title="DOI">[![DOI][badge-001]][resource-312]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-313]</span><br><span title="Prompts &amp; Algorithms">[![Prompts & Algorithms][badge-072]][resource-314]</span><br><span title="Project（相关）">[![Project（相关）][badge-057]][resource-315]</span><br>[详情](#paper-co4all2025) |
| 2026 · NeurIPS 2026（已接收，待出版） | <a id="entry-kong2026frontieror"></a>**FrontierOR**<br>FrontierOR: Benchmarking LLMs' Capacity for Efficient Algorithm Design in Large-Scale Optimization | FrontierOR 提供文献驱动的 OR 任务、实例及 Gurobi 参考，联合评测算法可行性、解质量和运行效率。 | 基准 · 数据 | <span title="Paper">[![Paper][badge-007]][resource-510]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-511]</span><br><span title="Code">[![Code][badge-008]][resource-512]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-513]</span><br>[详情](#paper-kong2026frontieror) |
| 2026 · ICLR 2026 | <a id="entry-chen2025heurigym"></a>**HeuriGym**<br>HeuriGym: An Agentic Benchmark for LLM-Crafted Heuristics in Combinatorial Optimization | HeuriGym 提供九类开放解空间任务，以执行反馈与 QYI 指标联合衡量启发式质量和有效产出。 | 基准 · 平台 | <span title="Proceedings">[![Proceedings][badge-005]][resource-514]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-515]</span><br><span title="Code">[![Code][badge-008]][resource-516]</span><br><span title="Leaderboard（相关）">[![Leaderboard（相关）][badge-102]][resource-517]</span><br>[详情](#paper-chen2025heurigym) |
| 2026 · Computers & Operations Research 196（2026-12 编期） | <a id="entry-behaviorrep2025"></a>**LLM Representations for Algorithm Selection**<br>Behavior and representation in open-weight Large Language Models for combinatorial optimization: From feature extraction to algorithm selection | 在冻结 LLM 上比较显式特征、隐藏层探测及逐实例算法选择，检验表示作为下游描述符的可用性。 | 评测分析 | <span title="DOI">[![DOI][badge-001]][resource-518]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-519]</span><br><span title="Code &amp; Analysis Data">[![Code & Analysis Data][badge-103]][resource-520]</span><br>[详情](#paper-behaviorrep2025) |
| 2026 · Findings of ACL 2026 | **OPT-BENCH / OPT-Agent**<br>OPT-BENCH: Evaluating the Iterative Self-Optimization of LLM Agents in Large-Scale Search Spaces | OPT-BENCH 覆盖机器学习调优和 NP 问题，评测利用历史反馈反复改进候选方案的能力。 | 方法 · 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-292]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-293]</span><br><span title="Revised Preprint">[![Revised Preprint][badge-071]][resource-294]</span><br><span title="Code">[![Code][badge-008]][resource-295]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-296]</span><br>[详情](#paper-li2026optbench) |
| 2025 · arXiv preprint | **ARS / RoutBench**<br>ARS: Automatic Routing Solver with Large Language Models | RoutBench 以多变体 VRP 和可组合实际约束，评测自动生成路由算法的求解能力与泛化。 | 方法 · 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-348]</span><br><span title="Code">[![Code][badge-008]][resource-349]</span><br>[详情](#paper-li2025ars) |
| 2025 · EvoApplications 2025 · LNCS | <a id="entry-sim2025beyondhype"></a>**Beyond the Hype: Bin Packing**<br>Beyond the Hype: Benchmarking LLM-Evolved Heuristics for Bin Packing | 跨广泛装箱实例复评 LLM 演化启发式，结合性能指标与实例空间分析检验泛化和生成成本。 | 评测分析 · 数据 | <span title="DOI">[![DOI][badge-001]][resource-521]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-522]</span><br><span title="Evaluation Data">[![Evaluation Data][badge-091]][resource-523]</span><br>[详情](#paper-sim2025beyondhype) |
| 2025 · GECCO 2025 Workshop / Companion | <a id="entry-vanstein2025blade"></a>**BLADE**<br>BLADE: Benchmark suite for LLM-driven Automated Design and Evolution of iterative optimisation heuristics | BLADE 提供连续黑箱优化实例、标准日志及行为分析，评测算法发现的泛化、专化与信息利用。 | 基准 · 平台 | <span title="DOI">[![DOI][badge-001]][resource-524]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-525]</span><br><span title="Code">[![Code][badge-008]][resource-526]</span><br>[详情](#paper-vanstein2025blade) |
| 2025 · AAAI 2025 | **HSEvo**<br>HSEvo: Elevating Automatic Heuristic Design with Diversity-Driven Harmony Search and Genetic Algorithm Using LLMs | 在既有组合优化任务上分析启发式演化的多样性，比较搜索探索与求解表现。 | 方法 · 评测分析 | <span title="DOI">[![DOI][badge-001]][resource-360]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-361]</span><br><span title="Code">[![Code][badge-008]][resource-362]</span><br>[详情](#paper-dat2024hsevo) |
| 2025 · arXiv preprint | <a id="entry-liu2025fitness"></a>**LLM Algorithm-search Fitness Landscapes**<br>Fitness Landscape of Large Language Model-Assisted Automated Algorithm Search | 以算法为节点、LLM 转换为边分析适应度景观，比较不同任务和模型下的搜索崎岖性及相似性。 | 评测分析 | <span title="arXiv">[![arXiv][badge-002]][resource-527]</span><br>[详情](#paper-liu2025fitness) |
| 2025 · arXiv preprint | <a id="entry-vanstein2025behaviour"></a>**LLM Heuristic Behaviour-space Analysis**<br>Behaviour Space Analysis of LLM-driven Meta-heuristic Discovery | 在既有 BBOB 上比较 LLaMEA 提示变体，以探索、利用、收敛和停滞等指标分析搜索行为。 | 评测分析 | <span title="arXiv">[![arXiv][badge-002]][resource-528]</span><br><span title="Behaviour Metrics Code">[![Behaviour Metrics Code][badge-104]][resource-529]</span><br>[详情](#paper-vanstein2025behaviour) |
| 2025 · arXiv preprint | <a id="entry-quan2025reeval3d"></a>**Re-evaluating Heuristic Search: 3D Packing**<br>Re-evaluating LLM-based Heuristic Search: A Case Study on the 3D Packing Problem | 以 3D 装箱程序生成为案例，检查约束脚手架、自修复、搜索范围与紧约束下的工程局限。 | 评测分析 | <span title="arXiv">[![arXiv][badge-002]][resource-530]</span><br><span title="Study Code">[![Study Code][badge-105]][resource-531]</span><br>[详情](#paper-quan2025reeval3d) |

### 交互与工作流评测

| 年份 / Venue | 论文 | 评测内容 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · arXiv preprint | **Interactive Optimization Conversations**<br>Let's Have a Conversation: Designing and Evaluating LLM Agents for Interactive Optimization | 学校排课实验使用带内部效用函数的利益相关者 Agent，比较多轮交互优化、领域提示与结构化工具。 | 方法 · 数据 · 应用 | <span title="arXiv">[![arXiv][badge-002]][resource-187]</span><br><span title="Code">[![Code][badge-008]][resource-188]</span><br>[详情](#paper-conversation2026) |
| 2026 · arXiv preprint | <a id="entry-optiagentbench2026"></a>**Opti-Agent-Bench**<br>Opti-Agent-Bench: Benchmarking End-to-End Optimization R&D Agents on Real-World Business Problems | Opti-Agent-Bench 评测业务理解到报告的完整流程，借助 ORAC 检查模型、代码与报告的跨模块一致性。 | 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-532]</span><br>[详情](#paper-optiagentbench2026) |
| 2026 · arXiv preprint | <a id="entry-zhou2026orspace"></a>**OR-Space**<br>OR-Space: A Full-Lifecycle Workspace Benchmark for Industrial Optimization Agents | OR-Space 在持久多文件工作区评测模型构建、需求变更与基于证据的解释三类生命周期任务。 | 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-533]</span><br><span title="Code">[![Code][badge-008]][resource-534]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-535]</span><br>[详情](#paper-zhou2026orspace) |
| 2026 · arXiv preprint | <a id="entry-oragentbench2026"></a>**ORAgentBench**<br>ORAgentBench: Can LLM Agents Solve Challenging Operations Research Tasks End to End? | ORAgentBench 从业务说明与多文件材料出发，以隐藏校验器分别检查格式、硬约束和目标质量。 | 基准 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-536]</span><br><span title="Code">[![Code][badge-008]][resource-537]</span><br>[详情](#paper-oragentbench2026) |
| 2025 · NeurIPS 2025 | <a id="entry-liu2025mmagent"></a>**MM-Agent / MM-Bench（数学建模）**<br>MM-Agent: LLM as Agents for Real-world Mathematical Modeling Problem | MM-Bench 收录 MCM/ICM 竞赛问题，评测问题分析、模型构造、计算求解与报告生成的完整流程。 | 方法 · 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-538]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-539]</span><br><span title="DOI">[![DOI][badge-001]][resource-540]</span><br><span title="Code &amp; MM-Bench">[![Code & MM-Bench][badge-029]][resource-541]</span><br><span title="Expert Skills (2026 add-on)">[![Expert Skills (2026 add-on)][badge-106]][resource-542]</span><br><span title="HF Demo（相关）">[![HF Demo（相关）][badge-011]][resource-543]</span><br>[详情](#paper-liu2025mmagent) |
| 2025 · Findings of EMNLP 2025 | <a id="entry-qian2025modelingagent"></a>**ModelingAgent / ModelingBench**<br>ModelingAgent: Bridging LLMs and Mathematical Modeling for Real-World Challenges | ModelingBench 收录开放式建模问题，ModelingJudge 结合专家参与的多视角评审评价建模报告。 | 方法 · 基准 · 数据 | <span title="Proceedings">[![Proceedings][badge-005]][resource-544]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-545]</span><br><span title="Code &amp; ModelingBench">[![Code & ModelingBench][badge-029]][resource-546]</span><br>[详情](#paper-qian2025modelingagent) |

**相关工作：** [DynaSchedBench](#entry-dynaschedbench2026) · [RetailBench](#entry-zhang2026retailbench) · [EOR / Decision Information](#entry-zhang2025decisioninfo)

### 数据质量与评价协议

| 年份 / Venue | 论文 | 评测内容 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · arXiv preprint | **Agora-Opt**<br>From Soliloquy to Agora: Memory-Enhanced LLM Agents with Decentralized Debate for Optimization Modeling | 发布人工核查、统一格式的既有建模基准修订数据，用于多团队建模与结果驱动辩论的比较。 | 方法 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-113]</span><br><span title="Code &amp; Cleaned Data">[![Code & Cleaned Data][badge-029]][resource-114]</span><br>[详情](#paper-soliloquy2026) |
| 2026 · LLM4Code 2026 Workshop @ ICSE | **CP-Agent**<br>CP-Agent: Agentic Constraint Programming | 提供 CP-Bench 的题意澄清与参考模型修订材料，用于检验约束建模及执行结果；保留原版与修订版区别。 | 方法 · 数据 | <span title="DOI">[![DOI][badge-001]][resource-209]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-210]</span><br><span title="Author Coding Agent（相关）">[![Author Coding Agent（相关）][badge-049]][resource-211]</span><br><span title="Evaluation Archive v2">[![Evaluation Archive v2][badge-050]][resource-212]</span><br>[详情](#paper-cpagent2025) |
| 2026 · ICLR 2026 | **OR-PRM**<br>OR-PRM: A Process Reward Model for Algorithmic Problem in Operations Research | 审查合成建模数据的标注噪声，并以 OR-ProcessQA 的逐步检查构建建模推理过程的评价信号。 | 方法 · 数据 · 模型 | <span title="Proceedings">[![Proceedings][badge-005]][resource-039]</span><br>[详情](#paper-wang2026orprm) |
| 2025 · arXiv preprint | <a id="entry-peering2025"></a>**Component-Level Evaluation**<br>Peering Inside the Black Box: Uncovering LLM Errors in Optimization Modelling through Component-Level Evaluation | 按变量、约束、目标的覆盖和数值误差诊断模型，补充最优值与运行时间指标。 | 方法 | <span title="arXiv">[![arXiv][badge-002]][resource-547]</span><br>[详情](#paper-peering2025) |
| 2025 · IEEE PESGM 2025 | <a id="entry-zhou2024elecbench"></a>**ElecBench**<br>ElecBench: a Power Grid Dispatch Evaluation Benchmark for Large Language Models | ElecBench 评测电力知识、监控、调度和黑启动文本任务，关注事实性、逻辑性与稳定性。 | 基准 · 数据 | <span title="DOI">[![DOI][badge-001]][resource-548]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-549]</span><br><span title="Public Test Subset">[![Public Test Subset][badge-107]][resource-550]</span><br>[详情](#paper-zhou2024elecbench) |
| 2025 · IJCAI 2025 Survey Track | **LLM4OR Survey**<br>A Survey of Optimization Modeling Meets LLMs: Progress and Future Directions | 对既有优化建模基准进行错误标注与清洗，提供修订评测材料及门户。 | 综述 · 数据 | <span title="arXiv">[![arXiv][badge-002]][resource-015]</span><br><span title="官方资源库（相关）">[![官方资源库（相关）][badge-003]][resource-016]</span><br><span title="Cleaned Benchmarks">[![Cleaned Benchmarks][badge-006]][resource-017]</span><br>[详情](#paper-xiao2025survey) |
| 2025 · arXiv preprint | **OptiTrust**<br>Toward a Trustworthy Optimization Modeling Agent via Verifiable Synthetic Data Generation | 用已知最优解的符号问题和跨建模语言投票检查合成标签，评测多阶段建模推理的可靠性。 | 方法 · 数据 · 模型 | <span title="arXiv">[![arXiv][badge-002]][resource-069]</span><br>[详情](#paper-lima2025optitrust) |
| 2025 · NeurIPS 2025 | **SIRL**<br>Solver-Informed RL: Grounding Large Language Models for Authentic Optimization Modeling | 发布既有建模基准的修订数据；求解器检查代码、LP 实例的语法、可行性与解质量。 | 方法 · 数据 · 模型 | <span title="Proceedings">[![Proceedings][badge-005]][resource-168]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-169]</span><br><span title="Code">[![Code][badge-008]][resource-170]</span><br><span title="Model Gurobi-7B">[![Model Gurobi-7B][badge-041]][resource-171]</span><br><span title="Model COPT-7B">[![Model COPT-7B][badge-042]][resource-172]</span><br><span title="Model Gurobi-32B">[![Model Gurobi-32B][badge-043]][resource-173]</span><br><span title="Model COPT-32B">[![Model COPT-32B][badge-044]][resource-174]</span><br><span title="修订评测集">[![修订评测集][badge-045]][resource-175]</span><br>[详情](#paper-chen2025sirl) |
| 2025 · Findings of EMNLP 2025 | **Step-Opt**<br>Training LLMs for Optimization Modeling via Iterative Data Synthesis and Structured Validation | 修订 NL4Opt、Mamo 与 IndustryOR 的评测材料，用于比较优化建模准确率及困难问题表现。 | 方法 · 数据 · 模型 | <span title="Proceedings">[![Proceedings][badge-005]][resource-084]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-085]</span><br><span title="Code">[![Code][badge-008]][resource-086]</span><br>[详情](#paper-wu2025stepopt) |
| 2024 · LREC-COLING 2024 | <a id="entry-xing2024lpwp"></a>**Human-aligned LPWP Evaluation**<br>Towards Human-aligned Evaluation for Linear Programming Word Problems | 以图编辑距离比较 LP 模型，并与人工评分对照，检验评价指标对变量排列和表达差异的适应性。 | 方法 · 评测分析 | <span title="Proceedings">[![Proceedings][badge-005]][resource-551]</span><br>[详情](#paper-xing2024lpwp) |

**相关工作：** [ConstraintBench](#entry-constraintbench2026) · [GenAI Beer Game Reliability](#entry-beergame2026) · [JOR-Bench](#entry-jorbench2026) · [NLCO](#entry-jiang2026nlco) · [OPF Constrained Reasoning Study](#entry-opf2026reason) · [OPT-Engine](#entry-chen2026optengine) · [Opti-Agent-Bench](#entry-optiagentbench2026) · [AIM-Bench](#entry-zhao2025aimbench) · [ORGEval / Bench4Opt](#entry-ding2026orgeval) · [Teaching LLMs to Think Mathematically](#entry-abedi2025thinkmath)


[返回目录](#contents)

<a id="foundational-resources"></a>

<a id="resources"></a>

## 模型、数据与工具资源

资源按实际产物类型汇总，论文方法与资源贡献可以同时出现。

### 资源与平台论文

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | **Text2Model**<br>Text2Model: Modeling Copilots for Text-to-Model Translation | 提供面向 MiniZinc 的多种建模 Copilot、交互编辑器与在线排行榜。 | 方法 · 平台 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | <span title="arXiv">[![arXiv][badge-002]][resource-216]</span><br><span title="Code">[![Code][badge-008]][resource-217]</span><br><span title="Text2Zinc（复用）">[![Text2Zinc（复用）][badge-052]][resource-218]</span><br><span title="Editor（相关）">[![Editor（相关）][badge-053]][resource-219]</span><br><span title="Leaderboard（相关）">[![Leaderboard（相关）][badge-054]][resource-220]</span><br><span title="Python Package（相关）">[![Python Package（相关）][badge-055]][resource-221]</span><br>[详情](#paper-text2model2026) |
| 2025 · arXiv preprint | **EASE**<br>Solve it with EASE | 以模块化生成、测试、分析和评价循环支持算法方案演化，允许多个 LLM 承担互补角色。 | 方法 · 平台 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-352]</span><br><span title="Framework">[![Framework][badge-076]][resource-353]</span><br><span title="Frontend">[![Frontend][badge-077]][resource-354]</span><br>[详情](#paper-viktorin2025ease) |
| 2025 · ICLR 2025 | <a id="entry-li2025milpevolve"></a>**MILP-Evolve**<br>Towards Foundation Models for Mixed Integer Linear Programming | 用 LLM 演化生成多样 MILP 类与实例，支持间隙预测、学习分支和语言对齐。 | 方法 · 数据 | [Data synthesis](#tech-data-synthesis) · [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-552]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-553]</span><br><span title="Code">[![Code][badge-008]][resource-554]</span><br><span title="Dataset">[![Dataset][badge-012]][resource-555]</span><br><span title="GitHub Data">[![GitHub Data][badge-094]][resource-556]</span><br>[详情](#paper-li2025milpevolve) |
| 2024 · arXiv preprint | <a id="entry-liu2024llm4ad"></a>**LLM4AD**<br>LLM4AD: A Platform for Algorithm Design with Large Language Model | 提供模块化算法设计平台，统一搜索方法、任务、LLM 接口与评估沙箱。 | 平台 |  | <span title="arXiv">[![arXiv][badge-002]][resource-557]</span><br><span title="Code">[![Code][badge-008]][resource-376]</span><br>[详情](#paper-liu2024llm4ad) |

[模型与权重](#model-weights) · [评测基准](#evaluation-benchmarks) · [训练数据](#training-data) · [修订评测数据](#evaluation-data) · [技能库](#skills)

<a id="model-weights"></a>

### 模型与权重

| 资源名称 | 关联论文 | 获取入口 |
|---|---|---|
| LLaMoCo-S（CodeGen 350M） | [LLaMoCo](#entry-ma2024llamoco) | <span title="HF Weights">[![HF Weights][badge-108]][resource-332]</span> |
| LLMOPT-Qwen2.5-14B | [LLMOPT](#entry-jiang2025llmopt) | <span title="HF Model">[![HF Model][badge-014]][resource-159]</span> |
| ner4opt-roberta-v1 | [Ner4Opt](#entry-dakle2023ner4opt) | <span title="HF Model">[![HF Model][badge-014]][resource-093]</span> |
| ner4opt-roberta-v2 | [Ner4Opt](#entry-dakle2023ner4opt) | <span title="HF Model">[![HF Model][badge-014]][resource-094]</span> |
| OptiMind-SFT | [OptiMind](#entry-zhang2025optimind) | <span title="HF Model">[![HF Model][badge-014]][resource-065]</span> |
| OptMATH Qwen2.5 7B / 32B | [OptMATH](#entry-lu2025optmath) | <span title="Model 7B">[![Model 7B][badge-015]][resource-072]</span> · <span title="Model 32B">[![Model 32B][badge-016]][resource-073]</span> |
| ORLM-LLaMA-3-8B | [ORLM](#entry-huang2025orlm) | <span title="HF Model">[![HF Model][badge-014]][resource-078]</span> |
| PEARL-Qwen3-4B-Instruct-2507 | [PEARL](#entry-lu2026pearl) | <span title="HF Model">[![HF Model][badge-014]][resource-138]</span> |
| SDRL-Qwen3-4B | [SDRL](#entry-sdrl2026) | <span title="HF Weights">[![HF Weights][badge-108]][resource-143]</span> |
| SIRL Gurobi / COPT 7B / 32B | [SIRL](#entry-chen2025sirl) | <span title="Model Gurobi-7B">[![Model Gurobi-7B][badge-041]][resource-171]</span> · <span title="Model COPT-7B">[![Model COPT-7B][badge-042]][resource-172]</span> · <span title="Model Gurobi-32B">[![Model Gurobi-32B][badge-043]][resource-173]</span> · <span title="Model COPT-32B">[![Model COPT-32B][badge-044]][resource-174]</span> |
| SOLID-Qwen3 | [SOLID](#entry-solid2026) | <span title="HF Model">[![HF Model][badge-014]][resource-146]</span> |
| SOLID-StepORLM | [SOLID](#entry-solid2026) | <span title="HF Model">[![HF Model][badge-014]][resource-147]</span> |
| StepORLM policy / GenPRM 8B | [StepORLM](#entry-zhou2026steporlm) | <span title="Policy 8B">[![Policy 8B][badge-039]][resource-151]</span> · <span title="GenPRM 8B">[![GenPRM 8B][badge-040]][resource-152]</span> |

<a id="evaluation-benchmarks"></a>

### 评测基准

| 资源名称 | 关联论文 | 获取入口 |
|---|---|---|
| RoutBench | [ARS / RoutBench](#entry-li2025ars) | <span title="GitHub">[![GitHub][badge-109]][resource-349]</span> |
| LPWP / NL4Opt 早期数据（1101 项） | [Auto-formulation (2022)](#entry-ramamonjison2022augmenting) | <span title="GitHub Data">[![GitHub Data][badge-094]][resource-112]</span> |
| BLADE | [BLADE](#entry-vanstein2025blade) | <span title="GitHub Suite">[![GitHub Suite][badge-110]][resource-526]</span> |
| StructuredOR | [BPP-Search / StructuredOR](#entry-wang2025bppsearch) | <span title="HF Data">[![HF Data][badge-111]][resource-061]</span> |
| ComplexOR（仓库原始版） | [Chain-of-Experts](#entry-xiao2024coe) | <span title="GitHub">[![GitHub][badge-109]][resource-088]</span> |
| CO-Bench | [CO-Bench](#entry-sun2026cobench) | <span title="HF Data">[![HF Data][badge-111]][resource-509]</span> |
| VRPBench | [Constraint Injection / VRPCoder](#entry-constraintinjection2026) | <span title="GitHub Data">[![GitHub Data][badge-094]][resource-261]</span> |
| CP-Bench（原版归档） | [CP-Bench / DCP-Bench-Open](#entry-michailidis2025cpbench) | <span title="HF Dataset">[![HF Dataset][badge-111]][resource-476]</span> |
| DCP-Bench-Open（扩展版） | [CP-Bench / DCP-Bench-Open](#entry-michailidis2025cpbench) | <span title="GitHub">[![GitHub][badge-109]][resource-475]</span> |
| CP-SynC Benchmark | [CP-SynC](#entry-cpsync2026) | <span title="GitHub Data &amp; Evaluation">[![GitHub Data & Evaluation][badge-112]][resource-214]</span> |
| DynaSchedBench | [DynaSchedBench](#entry-dynaschedbench2026) | <span title="GitHub Benchmark">[![GitHub Benchmark][badge-051]][resource-493]</span> |
| ElecBench（公开测试子集） | [ElecBench](#entry-zhou2024elecbench) | <span title="GitHub Subset">[![GitHub Subset][badge-113]][resource-550]</span> |
| EOR 工业解释评测集 | [EOR / Decision Information](#entry-zhang2025decisioninfo) | <span title="GitHub">[![GitHub][badge-109]][resource-233]</span> |
| EquivaFormulation | [EquivaMap](#entry-zhai2025equivamap) | <span title="HF Data">[![HF Data][badge-111]][resource-249]</span> |
| FrontierOR-v1（2026-09-27 发布） | [FrontierOR](#entry-kong2026frontieror) | <span title="HF Dataset">[![HF Dataset][badge-111]][resource-513]</span> · <span title="Evaluation code">[![Evaluation code][badge-114]][resource-512]</span> |
| HeuriGym | [HeuriGym](#entry-chen2025heurigym) | <span title="GitHub Benchmark">[![GitHub Benchmark][badge-051]][resource-516]</span> |
| InventoryBench | [InventoryBench](#entry-invbench2026) | <span title="GitHub">[![GitHub][badge-109]][resource-496]</span> |
| JOR-Bench（五组日译与英文对照） | [JOR-Bench](#entry-jorbench2026) | <span title="HF Dataset">[![HF Dataset][badge-111]][resource-457]</span> |
| Large-Scale-OR | [LEAN-LLM-OPT](#entry-liang2026leanllmopt) | <span title="GitHub：Test_Dataset">[![GitHub：Test_Dataset][badge-115]][resource-121]</span> |
| Air-NRM | [LEAN-LLM-OPT](#entry-liang2026leanllmopt) | <span title="GitHub：Test_Dataset">[![GitHub：Test_Dataset][badge-115]][resource-121]</span> |
| G-REAL | [MA-GTS / G-REAL](#entry-yuan2025magts) | <span title="GitHub">[![GitHub][badge-109]][resource-441]</span> |
| Mamo | [Mamo](#entry-huang2024mamo) | <span title="GitHub">[![GitHub][badge-109]][resource-480]</span> · <span title="HF 镜像（第三方字段适配）">[![HF 镜像（第三方字段适配）][badge-116]][resource-481]</span> |
| MIPLIB-NL | [MIPLIB-NL](#entry-li2026miplibnl) | <span title="GitHub">[![GitHub][badge-109]][resource-460]</span> |
| MM-Bench（数学建模竞赛） | [MM-Agent / MM-Bench（数学建模）](#entry-liu2025mmagent) | <span title="GitHub Data">[![GitHub Data][badge-094]][resource-541]</span> |
| ModelingBench | [ModelingAgent / ModelingBench](#entry-qian2025modelingagent) | <span title="GitHub Data">[![GitHub Data][badge-094]][resource-546]</span> |
| NL4Opt | [NL4Opt](#entry-ramamonjison2023nl4opt) | <span title="GitHub">[![GitHub][badge-109]][resource-112]</span> |
| NLCO | [NLCO](#entry-jiang2026nlco) | <span title="HF Dataset">[![HF Dataset][badge-111]][resource-501]</span> · <span title="Code">[![Code][badge-008]][resource-500]</span> |
| OPT-BENCH | [OPT-BENCH / OPT-Agent](#entry-li2026optbench) | <span title="HF Dataset">[![HF Dataset][badge-111]][resource-296]</span> · <span title="Code">[![Code][badge-008]][resource-295]</span> |
| OPT-Engine / C³-Bench | [OPT-Engine](#entry-chen2026optengine) | <span title="HF Dataset">[![HF Dataset][badge-111]][resource-467]</span> · <span title="Evaluation code">[![Evaluation code][badge-114]][resource-466]</span> |
| NLP4LP | [OptiMUS](#entry-teshnizi2024optimus) | <span title="HF Data">[![HF Data][badge-111]][resource-185]</span> |
| OptiVerse | [OptiVerse / DVA-Agent](#entry-optiverse2026) | <span title="HF Dataset">[![HF Dataset][badge-111]][resource-242]</span> · <span title="Evaluation Code">[![Evaluation Code][badge-114]][resource-241]</span> |
| OptMATH-Bench | [OptMATH](#entry-lu2025optmath) | <span title="GitHub">[![GitHub][badge-109]][resource-071]</span> |
| BWOR | [OR-LLM-Agent / BWOR](#entry-zhang2025bwor) | <span title="HF Dataset">[![HF Dataset][badge-111]][resource-164]</span> |
| OR-Space | [OR-Space](#entry-zhou2026orspace) | <span title="HF Dataset">[![HF Dataset][badge-111]][resource-535]</span> · <span title="Evaluation Code">[![Evaluation Code][badge-114]][resource-534]</span> |
| ORAgentBench | [ORAgentBench](#entry-oragentbench2026) | <span title="GitHub Benchmark">[![GitHub Benchmark][badge-051]][resource-537]</span> |
| IndustryOR | [ORLM](#entry-huang2025orlm) | <span title="IndustryOR">[![IndustryOR][badge-018]][resource-079]</span> |
| ORDebug / OR-Debug-Bench | [ORLoopBench](#entry-ao2026orloopbench) | <span title="GitHub">[![GitHub][badge-109]][resource-230]</span> |
| ORBias / OR-Bias-Bench | [ORLoopBench](#entry-ao2026orloopbench) | <span title="GitHub">[![GitHub][badge-109]][resource-230]</span> |
| ORQA | [ORQA](#entry-mostajabdaveh2025orqa) | <span title="GitHub">[![GitHub][badge-109]][resource-484]</span> |
| LogiOR | [ORThought / LogiOR](#entry-yang2025orthought) | <span title="HF Data">[![HF Data][badge-111]][resource-046]</span> |
| ECBench（生成器与公开样例） | [PowerAtlas / ECBench](#entry-jiang2026poweratlas) | <span title="GitHub">[![GitHub][badge-109]][resource-271]</span> |
| ProOPF-B | [ProOPF](#entry-shen2026proopf) | <span title="GitHub：ProOPF_B">[![GitHub：ProOPF_B][badge-115]][resource-471]</span> |
| RetailOpt-190 | [ReLoop / RetailOpt-190](#entry-lian2026reloop) | <span title="HF Dataset">[![HF Dataset][badge-111]][resource-267]</span> |
| OptiBench | [ReSocratic / OptiBench](#entry-yang2025resocratic) | <span title="GitHub">[![GitHub][badge-109]][resource-083]</span> |
| RetailBench | [RetailBench](#entry-zhang2026retailbench) | <span title="GitHub Environment">[![GitHub Environment][badge-117]][resource-504]</span> |
| NLEquiv-150 | [SOVER / NLEquiv-150](#entry-bhattacharyya2026sover) | <span title="GitHub Benchmark">[![GitHub Benchmark][badge-051]][resource-248]</span> |
| Text2Zinc（复用既有基准） | [Text2Model](#entry-text2model2026) | <span title="HF Dataset">[![HF Dataset][badge-111]][resource-218]</span> |
| Text2Zinc | [Text2Zinc](#entry-singirikonda2025text2zinc) | <span title="HF Dataset">[![HF Dataset][badge-111]][resource-218]</span> |

<a id="training-data"></a>

### 训练数据

| 资源名称 | 关联论文 | 获取入口 |
|---|---|---|
| AI-Copilot 排程训练样本 | [AI-Copilot for Business Optimisation](#entry-alahakoon2023copilot) | <span title="GitHub Data">[![GitHub Data][badge-094]][resource-099]</span> |
| AI-Copilot 工业案例训练样本 | [AI-Copilot for Business Optimisation](#entry-alahakoon2023copilot) | <span title="GitHub Case Data">[![GitHub Case Data][badge-024]][resource-101]</span> |
| DeepOR 种子与 SFT/RL 样例 | [DeepOR](#entry-xiao2026deepor) | <span title="官方种子与样例数据">[![官方种子与样例数据][badge-009]][resource-027]</span> |
| 不可行性感知图优化训练数据 | [Infeasibility-Aware CO Models](#entry-infeasibilityaware2026) | <span title="Author Archive（相关）">[![Author Archive（相关）][badge-067]][resource-269]</span> |
| LLMCoSolver SFT Data | [LLMCoSolver / E2E CO Solver](#entry-jiang2025e2eco) | <span title="SFT Data">[![SFT Data][badge-069]][resource-275]</span> |
| LLMCoSolver RL Data | [LLMCoSolver / E2E CO Solver](#entry-jiang2025e2eco) | <span title="RL Data">[![RL Data][badge-070]][resource-276]</span> |
| MILP-Evolve | [MILP-Evolve](#entry-li2025milpevolve) | <span title="HF Data">[![HF Data][badge-111]][resource-555]</span> |
| 扩展 NL4Opt 的 MILP 训练／测试材料 | [Multi-stage MILP Synthesis](#entry-li2023synthesizing) | <span title="GitHub Data">[![GitHub Data][badge-094]][resource-106]</span> |
| OptMATH-Train | [OptMATH](#entry-lu2025optmath) | <span title="HF Data">[![HF Data][badge-111]][resource-074]</span> |
| OR-Instruct-Data-3K（公开子集） | [ORLM](#entry-huang2025orlm) | <span title="OR-Instruct-3K">[![OR-Instruct-3K][badge-019]][resource-080]</span> |
| ProOPF-D（公开 few-shot 示例） | [ProOPF](#entry-shen2026proopf) | <span title="GitHub：ProOPF_D，非全量">[![GitHub：ProOPF_D，非全量][badge-113]][resource-471]</span> |
| ReSocratic-29k | [ReSocratic / OptiBench](#entry-yang2025resocratic) | <span title="GitHub">[![GitHub][badge-109]][resource-083]</span> |
| SAGE 多策略 SFT 数据 | [SAGE (Strategy-Aware Modeling)](#entry-strategyaware2026) | <span title="HF Dataset">[![HF Dataset][badge-111]][resource-050]</span> |
| Starjob 训练集 | [Starjob](#entry-abgaryan2025starjob) | <span title="HF Dataset">[![HF Dataset][badge-111]][resource-281]</span> |
| Step-Opt-Instruct 训练数据 | [Step-Opt](#entry-wu2025stepopt) | <span title="GitHub：Step/Dataset">[![GitHub：Step/Dataset][badge-118]][resource-086]</span> |

<a id="evaluation-data"></a>

### 修订评测数据

| 资源名称 | 关联论文 | 获取入口 |
|---|---|---|
| Agora-Opt 修订并统一格式的既有 OR 评测数据 | [Agora-Opt](#entry-soliloquy2026) | <span title="GitHub Data">[![GitHub Data][badge-094]][resource-114]</span> |
| AutoModSAT 评测数据（含生成与工业 EDA 实例） | [AutoModSAT](#entry-sun2025satheur) | <span title="Zenodo Data">[![Zenodo Data][badge-119]][resource-449]</span> |
| 装箱系统评测数据与演化实例 | [Beyond the Hype: Bin Packing](#entry-sim2025beyondhype) | <span title="Zenodo Data">[![Zenodo Data][badge-119]][resource-523]</span> |
| City-LEO 共享电动自行车数据与代码 | [City-LEO](#entry-jiao2024cityleo) | <span title="HF：Data &amp; Code">[![HF：Data & Code][badge-046]][resource-196]</span> |
| CP-Bench 修订评测材料（CP-Agent，Zenodo v2） | [CP-Agent](#entry-cpagent2025) | <span title="Zenodo v2">[![Zenodo v2][badge-120]][resource-212]</span> |
| DRoC VRP 评测实例 | [DRoC](#entry-jiang2025droc) | <span title="GitHub: problems">[![GitHub: problems][badge-087]][resource-155]</span> |
| HeurAgenix 使用的 CO 实例汇集 | [HeurAgenix](#entry-yang2025heuragenix) | <span title="HF Instances">[![HF Instances][badge-121]][resource-359]</span> |
| 学校排课交互评测与对话材料 | [Interactive Optimization Conversations](#entry-conversation2026) | <span title="GitHub">[![GitHub][badge-109]][resource-188]</span> |
| Representation / Probing 实验材料 | [LLM Representations for Algorithm Selection](#entry-behaviorrep2025) | <span title="Zenodo Archive">[![Zenodo Archive][badge-067]][resource-520]</span> |
| LLM4OR 既有建模基准的清洗 / 错误标注合集 | [LLM4OR Survey](#entry-xiao2025survey) | <span title="GitHub Data">[![GitHub Data][badge-094]][resource-017]</span> |
| 随机优化评测案例（含文献改编） | [LLMs for Stochastic Modeling](#entry-talebi2025stochastic) | <span title="GitHub：dataset.zip">[![GitHub：dataset.zip][badge-094]][resource-208]</span> |
| MoH 使用的 CO 任务数据包 | [MoH](#entry-moh2025) | <span title="Google Drive Data">[![Google Drive Data][badge-122]][resource-418]</span> |
| MOID 路由不可行诊断案例与解 | [MOID](#entry-moid2025) | <span title="GitHub Data">[![GitHub Data][badge-094]][resource-235]</span> |
| NEMO 逐题输出与轨迹（既有基准） | [NEMO](#entry-nemo2026) | <span title="HF Artifacts">[![HF Artifacts][badge-123]][resource-126]</span> |
| Opt-Miner 第三方基座复现实验输出 | [Opt-Miner](#entry-optminer2026) | <span title="HF：第三方结果">[![HF：第三方结果][badge-010]][resource-036]</span> |
| OptiChat 模型解释问答评测 | [OptiChat](#entry-chen2025optichat) | <span title="GitHub">[![GitHub][badge-109]][resource-191]</span> |
| ORLMBenchmark（既有基准修订版） | [SIRL](#entry-chen2025sirl) | <span title="修订评测集">[![修订评测集][badge-045]][resource-175]</span> |
| 修订 NL4Opt / MAMO / IndustryOR 评测数据 | [Step-Opt](#entry-wu2025stepopt) | <span title="GitHub：Step/test">[![GitHub：Step/test][badge-115]][resource-086]</span> |

<a id="skills"></a>

### 技能库

| 资源名称 | 关联论文 | 获取入口 |
|---|---|---|
| AutoOPT 领域研究技能 | [AutoOPT](#entry-autoopt2026) | <span title="GitHub Skills">[![GitHub Skills][badge-033]][resource-413]</span> |
| MM-Agent Expert Skills | [MM-Agent / MM-Bench（数学建模）](#entry-liu2025mmagent) | <span title="GitHub Skills">[![GitHub Skills][badge-033]][resource-542]</span> |
| OptSkills 工作流技能库 | [OptSkills](#entry-yang2026optskills) | <span title="官方技能库（相关）">[![官方技能库（相关）][badge-033]][resource-134]</span> |

[返回目录](#contents)

<a id="agents"></a>

<a id="training"></a>

<a id="techniques"></a>

## 技术标签与专题索引

按明确的方法机制查找；技术标签与研究任务、贡献类型分别记录。

<a id="tech-agent"></a>

<details>
<summary>Agent（62 篇）</summary>

[AFL](#entry-zhang2026afl) · [Agentic MIP Research](#entry-xu2026agenticmip) · [Agora-Opt](#entry-soliloquy2026) · [AutoOPT](#entry-autoopt2026) · [CIR / R2C](#entry-canonicalir2026) · [COOPA](#entry-coopa2026) · [CP-Agent](#entry-cpagent2025) · [CP-SynC](#entry-cpsync2026) · [EvoOR-Agent](#entry-coevolve2026) · [GenAI Beer Game Reliability](#entry-beergame2026) · [HeuriGym](#entry-chen2025heurigym) · [Interactive Optimization Conversations](#entry-conversation2026) · [LEAN-LLM-OPT](#entry-liang2026leanllmopt) · [LLM Agents for Efficient Frontiers](#entry-efficientfrontier2026) · [LLM-MAS for Service Operations](#entry-wang2026llmmas) · [MIRROR](#entry-mirror2026) · [NEMO](#entry-nemo2026) · [OPT-BENCH / OPT-Agent](#entry-li2026optbench) · [Opt-Miner](#entry-optminer2026) · [OptArgus](#entry-optarcus2026) · [OptGraph](#entry-xiu2026optgraph) · [OptiAgent](#entry-optiagent2026) · [OptiChat](#entry-chen2025optichat) · [OptiLoop](#entry-optiloop2026) · [OptiRepair](#entry-optirepair2026) · [OptiVerse / DVA-Agent](#entry-optiverse2026) · [OptSkills](#entry-yang2026optskills) · [ORThought / LogiOR](#entry-yang2025orthought) · [PathWise](#entry-pathwise2026) · [PEARL](#entry-lu2026pearl) · [RLEA](#entry-rlvrpagents2026) · [Text2Model](#entry-text2model2026) · [ALAS](#entry-alas2025) · [ARS / RoutBench](#entry-li2025ars) · [Ask, Clarify, Optimize](#entry-askclarify2026) · [C-DSS](#entry-kaleta2025cdss) · [DAOpt / OptU](#entry-daopt2025) · [EASE](#entry-viktorin2025ease) · [EOR / Decision Information](#entry-zhang2025decisioninfo) · [Gala](#entry-globalconstraint2025) · [LLM-LNS](#entry-ye2025llmlns) · [LLM-SUC](#entry-llmsuc2025) · [LLMs for Stochastic Modeling](#entry-talebi2025stochastic) · [MA-GTS / G-REAL](#entry-yuan2025magts) · [MM-Agent / MM-Bench（数学建模）](#entry-liu2025mmagent) · [ModelingAgent / ModelingBench](#entry-qian2025modelingagent) · [MURKA](#entry-xie2025murka) · [OptimAI](#entry-thind2025optimai) · [OptiTrust](#entry-lima2025optitrust) · [OR-LLM-Agent / BWOR](#entry-zhang2025bwor) · [ORMind](#entry-ormind2025) · [RoCo](#entry-xu2025roco) · [Chain-of-Experts](#entry-xiao2024coe) · [City-LEO](#entry-jiao2024cityleo) · [InvAgent](#entry-quan2024invagent) · [ITINERA](#entry-tang2024itinerary) · [Multi-Stage Modeling & Verification](#entry-mostajabdaveh2024multiagent) · [OptiChat / Infeasibility Diagnosis](#entry-chen2023diagnosing) · [OptiMUS](#entry-teshnizi2024optimus) · [OptLLM](#entry-zhang2024optllm) · [LLMs for Power Engineering](#entry-li2023power) · [OptiGuide](#entry-li2023optiguide)

</details>

<a id="tech-multi-agent"></a>

<details>
<summary>Multi-agent（35 篇）</summary>

[AFL](#entry-zhang2026afl) · [Agora-Opt](#entry-soliloquy2026) · [CIR / R2C](#entry-canonicalir2026) · [COOPA](#entry-coopa2026) · [CP-SynC](#entry-cpsync2026) · [EvoOR-Agent](#entry-coevolve2026) · [GenAI Beer Game Reliability](#entry-beergame2026) · [LEAN-LLM-OPT](#entry-liang2026leanllmopt) · [OptArgus](#entry-optarcus2026) · [OptiAgent](#entry-optiagent2026) · [OptiChat](#entry-chen2025optichat) · [OptiVerse / DVA-Agent](#entry-optiverse2026) · [ORThought / LogiOR](#entry-yang2025orthought) · [PathWise](#entry-pathwise2026) · [RLEA](#entry-rlvrpagents2026) · [Text2Model](#entry-text2model2026) · [ALAS](#entry-alas2025) · [C-DSS](#entry-kaleta2025cdss) · [DAOpt / OptU](#entry-daopt2025) · [EASE](#entry-viktorin2025ease) · [Gala](#entry-globalconstraint2025) · [LLMs for Stochastic Modeling](#entry-talebi2025stochastic) · [MA-GTS / G-REAL](#entry-yuan2025magts) · [MM-Agent / MM-Bench（数学建模）](#entry-liu2025mmagent) · [ModelingAgent / ModelingBench](#entry-qian2025modelingagent) · [MURKA](#entry-xie2025murka) · [OptimAI](#entry-thind2025optimai) · [OptiTrust](#entry-lima2025optitrust) · [OR-LLM-Agent / BWOR](#entry-zhang2025bwor) · [ORMind](#entry-ormind2025) · [RoCo](#entry-xu2025roco) · [Chain-of-Experts](#entry-xiao2024coe) · [InvAgent](#entry-quan2024invagent) · [Multi-Stage Modeling & Verification](#entry-mostajabdaveh2024multiagent) · [OptiMUS](#entry-teshnizi2024optimus)

</details>

<a id="tech-cot"></a>

<details>
<summary>CoT / structured reasoning（9 篇）</summary>

[DeepOR](#entry-xiao2026deepor) · [DScheLLM](#entry-zhang2026dschellm) · [MiniOpt](#entry-zhao2026miniopt) · [ORThought / LogiOR](#entry-yang2025orthought) · [StepORLM](#entry-zhou2026steporlm) · [BPP-Search / StructuredOR](#entry-wang2025bppsearch) · [DPLM / DP-Bench](#entry-dpdlm2025) · [Chain-of-Experts](#entry-xiao2024coe) · [Rare MIP Challenges](#entry-wang2024raremip)

</details>

<a id="tech-rag"></a>

<details>
<summary>RAG（12 篇）</summary>

[CHORUS](#entry-lporch2025) · [CIR / R2C](#entry-canonicalir2026) · [MIRROR](#entry-mirror2026) · [Opt-Miner](#entry-optminer2026) · [OptGraph](#entry-xiu2026optgraph) · [OptSkills](#entry-yang2026optskills) · [RAG for Optimization & CP Modeling](#entry-roy2026rag) · [RLEA](#entry-rlvrpagents2026) · [C-DSS](#entry-kaleta2025cdss) · [Cold-Start Separator Configuration](#entry-lawless2024cuts) · [DRoC](#entry-jiang2025droc) · [RAGDyS](#entry-tang2024ragdys)

</details>

<a id="tech-memory"></a>

<details>
<summary>Memory（16 篇）</summary>

[Agora-Opt](#entry-soliloquy2026) · [AutoREM / AutoRO-Bench](#entry-robustreform2026) · [FormuEvo](#entry-yuan2026formuevo) · [HiFo-Prompt](#entry-chen2025hifoprompt) · [NEMO](#entry-nemo2026) · [OPT-BENCH / OPT-Agent](#entry-li2026optbench) · [OptGraph](#entry-xiu2026optgraph) · [OptSkills](#entry-yang2026optskills) · [PathWise](#entry-pathwise2026) · [RLEA](#entry-rlvrpagents2026) · [SAC-Opt](#entry-ma2025sacopt) · [ShinkaEvolve](#entry-lange2026shinka) · [ALAS](#entry-alas2025) · [AlphaOPT](#entry-kong2025alphaopt) · [OptiTree](#entry-liu2025optitree) · [ReflecSched](#entry-cao2025reflecsched)

</details>

<a id="tech-reflection"></a>

<details>
<summary>Reflection（14 篇）</summary>

[EPOCH](#entry-epoch2026) · [HiFo-Prompt](#entry-chen2025hifoprompt) · [LaGO](#entry-hsplo2026) · [MeEvo](#entry-meevo2026) · [MeLA](#entry-chen2025mela) · [MILP-Evo](#entry-milpevo2026) · [PyVRP+ / MEP](#entry-pyvrpplus2026) · [CALM / STORM](#entry-calm2025storm) · [DPLM / DP-Bench](#entry-dpdlm2025) · [OptimAI](#entry-thind2025optimai) · [ReflecSched](#entry-cao2025reflecsched) · [RoCo](#entry-xu2025roco) · [Chain-of-Experts](#entry-xiao2024coe) · [ReEvo](#entry-ye2024reevo)

</details>

<a id="tech-mcts"></a>

<details>
<summary>MCTS（4 篇）</summary>

[OR-PRM](#entry-wang2026orprm) · [Autoformulation](#entry-astorga2025autoformulation) · [MCTS-AHD](#entry-zheng2025mctsahd) · [SolverLLM](#entry-solverllm2025)

</details>

<a id="tech-tree-search"></a>

<details>
<summary>Tree / beam search（2 篇）</summary>

[BPP-Search / StructuredOR](#entry-wang2025bppsearch) · [OptiTree](#entry-liu2025optitree)

</details>

<a id="tech-evolution"></a>

<details>
<summary>Program evolution（49 篇）</summary>

[A2DEPT](#entry-chen2026a2dept) · [AILS-AHD](#entry-xie2026ailsahd) · [AutoModSAT](#entry-sun2025satheur) · [AutoSAT](#entry-sun2024autosat) · [CALM (Algorithm–LM Co-evolution)](#entry-huang2025calm) · [DSevolve](#entry-dsevolve2026) · [EPOCH](#entry-epoch2026) · [ES-AHD](#entry-es2026ahd) · [Evo-B&B](#entry-chen2026evobb) · [EvoOR-Agent](#entry-coevolve2026) · [FormuEvo](#entry-yuan2026formuevo) · [Full-Component ALNS Evolution](#entry-yu2026alns) · [G-LNS](#entry-zhao2026glns) · [HiFo-Prompt](#entry-chen2025hifoprompt) · [InvEvolve](#entry-invevolve2026) · [MeEvo](#entry-meevo2026) · [MeLA](#entry-chen2025mela) · [MILP-Evo](#entry-milpevo2026) · [MoH](#entry-moh2025) · [MPaGE](#entry-ha2025paretogrid) · [PALL](#entry-yan2026pall) · [PyVRP+ / MEP](#entry-pyvrpplus2026) · [ShinkaEvolve](#entry-lange2026shinka) · [SpecAHD](#entry-lai2026specahd) · [SPO](#entry-spo2026) · [TIDE](#entry-chen2026tide) · [VRPAgent](#entry-vrpagent2025) · [AlphaEvolve](#entry-novikov2025alphaevolve) · [CEoH](#entry-bomer2025emerging) · [DHEvo](#entry-dheevo2025) · [EASE](#entry-viktorin2025ease) · [EFS](#entry-luo2025efs) · [FunSearch for Unit Commitment](#entry-ucfunsearch2025) · [HeurAgenix](#entry-yang2025heuragenix) · [HSEvo](#entry-dat2024hsevo) · [InstSpecHH](#entry-zhang2025instspechh) · [LLaMEA](#entry-vanstein2024llamea) · [LLM-discovered EDDC / MDDC](#entry-cetinkaya2025mipsmtt) · [LLM-LNS](#entry-ye2025llmlns) · [MEoH](#entry-yao2025meoh) · [MILP-Evolve](#entry-li2025milpevolve) · [NCO-LLM for VRP](#entry-tran2025llmneural) · [RedAHD](#entry-thach2025redahd) · [SAGE / 原 EvoCut](#entry-yazdani2025evocut) · [STRCMP](#entry-li2025strcmp) · [EoH](#entry-liu2024eoh) · [ReEvo](#entry-ye2024reevo) · [AEL](#entry-liu2023ael) · [FunSearch](#entry-romera2023funsearch)

</details>

<a id="tech-data-synthesis"></a>

<details>
<summary>Data synthesis（29 篇）</summary>

[AutoOR](#entry-autoor2026) · [Constraint Injection / VRPCoder](#entry-constraintinjection2026) · [DeepOR](#entry-xiao2026deepor) · [DScheLLM](#entry-zhang2026dschellm) · [EvoOptiGraph](#entry-evooptigraph2026) · [Infeasibility-Aware CO Models](#entry-infeasibilityaware2026) · [LLaMoCo](#entry-ma2024llamoco) · [MIND](#entry-mind2026) · [Opt-Miner](#entry-optminer2026) · [OR-PRM](#entry-wang2026orprm) · [PALL](#entry-yan2026pall) · [PowerAtlas / ECBench](#entry-jiang2026poweratlas) · [RAG for Optimization & CP Modeling](#entry-roy2026rag) · [SAGE (Strategy-Aware Modeling)](#entry-strategyaware2026) · [SDRL](#entry-sdrl2026) · [CALM / STORM](#entry-calm2025storm) · [DPLM / DP-Bench](#entry-dpdlm2025) · [LLMCoSolver / E2E CO Solver](#entry-jiang2025e2eco) · [MILP-Evolve](#entry-li2025milpevolve) · [OptiTrust](#entry-lima2025optitrust) · [OptMATH](#entry-lu2025optmath) · [ORLM](#entry-huang2025orlm) · [ReSocratic / OptiBench](#entry-yang2025resocratic) · [SIRL](#entry-chen2025sirl) · [Step-Opt](#entry-wu2025stepopt) · [OptLLM](#entry-zhang2024optllm) · [To the Globe / TTG](#entry-ju2024ttg) · [AI-Copilot for Business Optimisation](#entry-alahakoon2023copilot) · [CodeT5 Mathematical Program Synthesis](#entry-synth2023)

</details>

<a id="tech-sft"></a>

<details>
<summary>SFT / distillation（40 篇）</summary>

[AutoOR](#entry-autoor2026) · [Constraint Injection / VRPCoder](#entry-constraintinjection2026) · [DeepOR](#entry-xiao2026deepor) · [DScheLLM](#entry-zhang2026dschellm) · [EPOCH](#entry-epoch2026) · [EvoOpt-LLM](#entry-he2026evoopt) · [EvoOptiGraph](#entry-evooptigraph2026) · [Infeasibility-Aware CO Models](#entry-infeasibilityaware2026) · [LLaMoCo](#entry-ma2024llamoco) · [MIND](#entry-mind2026) · [Multi-Warehouse Formulation Selection](#entry-warehouseformsel2026) · [OR-PRM](#entry-wang2026orprm) · [OR-R1](#entry-ding2026orr1) · [PALL](#entry-yan2026pall) · [PowerAtlas / ECBench](#entry-jiang2026poweratlas) · [SAGE (Strategy-Aware Modeling)](#entry-strategyaware2026) · [Ask, Clarify, Optimize](#entry-askclarify2026) · [CALM / STORM](#entry-calm2025storm) · [DPLM / DP-Bench](#entry-dpdlm2025) · [LLMCoSolver / E2E CO Solver](#entry-jiang2025e2eco) · [LLMOPT](#entry-jiang2025llmopt) · [MURKA](#entry-xie2025murka) · [OptiMind](#entry-zhang2025optimind) · [OptiTrust](#entry-lima2025optitrust) · [OptMATH](#entry-lu2025optmath) · [ORLM](#entry-huang2025orlm) · [ReSocratic / OptiBench](#entry-yang2025resocratic) · [Starjob](#entry-abgaryan2025starjob) · [Step-Opt](#entry-wu2025stepopt) · [STRCMP](#entry-li2025strcmp) · [LM4OPT](#entry-ahmed2024lm4opt) · [Ner4Opt](#entry-dakle2023ner4opt) · [OptLLM](#entry-zhang2024optllm) · [Rare MIP Challenges](#entry-wang2024raremip) · [To the Globe / TTG](#entry-ju2024ttg) · [AI-Copilot for Business Optimisation](#entry-alahakoon2023copilot) · [CodeT5 Mathematical Program Synthesis](#entry-synth2023) · [Multi-stage MILP Synthesis](#entry-li2023synthesizing) · [NL4Opt: Auto-Formulation Approach](#entry-iflytek2023autoformulation) · [OPD@NL4Opt](#entry-wang2023opdnl4opt)

</details>

<a id="tech-llm-rl"></a>

<details>
<summary>LLM RL（26 篇）</summary>

[AutoOR](#entry-autoor2026) · [CALM (Algorithm–LM Co-evolution)](#entry-huang2025calm) · [Constraint Injection / VRPCoder](#entry-constraintinjection2026) · [DeepOR](#entry-xiao2026deepor) · [EVOM](#entry-guan2026evom) · [EvoOptiGraph](#entry-evooptigraph2026) · [GenAI Beer Game Reliability](#entry-beergame2026) · [MiniOpt](#entry-zhao2026miniopt) · [Multi-Warehouse Formulation Selection](#entry-warehouseformsel2026) · [Opt-Miner](#entry-optminer2026) · [OptiRepair](#entry-optirepair2026) · [OR-R1](#entry-ding2026orr1) · [ORLoopBench](#entry-ao2026orloopbench) · [PEARL](#entry-lu2026pearl) · [PowerAtlas / ECBench](#entry-jiang2026poweratlas) · [SAGE (Strategy-Aware Modeling)](#entry-strategyaware2026) · [SDRL](#entry-sdrl2026) · [SOLID](#entry-solid2026) · [SPO](#entry-spo2026) · [StepORLM](#entry-zhou2026steporlm) · [CALM / STORM](#entry-calm2025storm) · [HeurAgenix](#entry-yang2025heuragenix) · [LLMCoSolver / E2E CO Solver](#entry-jiang2025e2eco) · [MURKA](#entry-xie2025murka) · [SIRL](#entry-chen2025sirl) · [STRCMP](#entry-li2025strcmp)

</details>

<a id="tech-preference"></a>

<details>
<summary>Preference optimization（5 篇）</summary>

[EPOCH](#entry-epoch2026) · [MIND](#entry-mind2026) · [Multi-Warehouse Formulation Selection](#entry-warehouseformsel2026) · [OR-PRM](#entry-wang2026orprm) · [BPP-Search / StructuredOR](#entry-wang2025bppsearch)

</details>

<a id="tech-prm"></a>

<details>
<summary>Process rewards（4 篇）</summary>

[OR-PRM](#entry-wang2026orprm) · [ORLoopBench](#entry-ao2026orloopbench) · [StepORLM](#entry-zhou2026steporlm) · [BPP-Search / StructuredOR](#entry-wang2025bppsearch)

</details>

<a id="tech-solver-feedback"></a>

<details>
<summary>Execution / solver feedback（157 篇）</summary>

[A2DEPT](#entry-chen2026a2dept) · [AFL](#entry-zhang2026afl) · [Agentic MIP Research](#entry-xu2026agenticmip) · [Agora-Opt](#entry-soliloquy2026) · [AILS-AHD](#entry-xie2026ailsahd) · [Automated Inventory Policy Design](#entry-invpolicy2026) · [AutoModSAT](#entry-sun2025satheur) · [AutoOPT](#entry-autoopt2026) · [AutoOR](#entry-autoor2026) · [AutoREM / AutoRO-Bench](#entry-robustreform2026) · [AutoSAT](#entry-sun2024autosat) · [BiFE](#entry-bife2026) · [CALM (Algorithm–LM Co-evolution)](#entry-huang2025calm) · [CHORUS](#entry-lporch2025) · [CIR / R2C](#entry-canonicalir2026) · [Combinatorial Optimization for All](#entry-co4all2025) · [Constraint Injection / VRPCoder](#entry-constraintinjection2026) · [CP-Agent](#entry-cpagent2025) · [CP-SynC](#entry-cpsync2026) · [DeepOR](#entry-xiao2026deepor) · [DScheLLM](#entry-zhang2026dschellm) · [DSevolve](#entry-dsevolve2026) · [EPOCH](#entry-epoch2026) · [ES-AHD](#entry-es2026ahd) · [Evo-B&B](#entry-chen2026evobb) · [EVOM](#entry-guan2026evom) · [EvoOpt-LLM](#entry-he2026evoopt) · [EvoOptiGraph](#entry-evooptigraph2026) · [EvoOR-Agent](#entry-coevolve2026) · [Falsification-Based Verification](#entry-li2026falsification) · [FormuEvo](#entry-yuan2026formuevo) · [Full-Component ALNS Evolution](#entry-yu2026alns) · [G-LNS](#entry-zhao2026glns) · [GRIMIP](#entry-luo2026grimip) · [HeuriGym](#entry-chen2025heurigym) · [HiFo-Prompt](#entry-chen2025hifoprompt) · [Infeasibility-Aware CO Models](#entry-infeasibilityaware2026) · [InvEvolve](#entry-invevolve2026) · [LaGO](#entry-hsplo2026) · [Latent Heuristic Search](#entry-latentheuristic2026) · [LEAN-LLM-OPT](#entry-liang2026leanllmopt) · [LLaMoCo](#entry-ma2024llamoco) · [LLM Agents for Efficient Frontiers](#entry-efficientfrontier2026) · [LLM MIP Configuration](#entry-zhang2026autoconfig) · [LLM-guided Cutting-plane Management](#entry-zheng2026cutmgmt) · [LLM4Branch](#entry-llm4branch2026) · [MeEvo](#entry-meevo2026) · [MeLA](#entry-chen2025mela) · [MILP-Evo](#entry-milpevo2026) · [MIND](#entry-mind2026) · [MiniOpt](#entry-zhao2026miniopt) · [MIRROR](#entry-mirror2026) · [MoH](#entry-moh2025) · [MPaGE](#entry-ha2025paretogrid) · [Multi-Warehouse Formulation Selection](#entry-warehouseformsel2026) · [NEMO](#entry-nemo2026) · [OPT-BENCH / OPT-Agent](#entry-li2026optbench) · [Opt-Miner](#entry-optminer2026) · [OptGraph](#entry-xiu2026optgraph) · [OptiAgent](#entry-optiagent2026) · [OptiChat](#entry-chen2025optichat) · [OptiDSL](#entry-dslmilp2026) · [OptiLoop](#entry-optiloop2026) · [OptiRepair](#entry-optirepair2026) · [OptSkills](#entry-yang2026optskills) · [OR-PRM](#entry-wang2026orprm) · [OR-R1](#entry-ding2026orr1) · [ORLoopBench](#entry-ao2026orloopbench) · [PALL](#entry-yan2026pall) · [PathWise](#entry-pathwise2026) · [PEARL](#entry-lu2026pearl) · [PowerAtlas / ECBench](#entry-jiang2026poweratlas) · [PyVRP+ / MEP](#entry-pyvrpplus2026) · [RAG for Optimization & CP Modeling](#entry-roy2026rag) · [ReLoop / RetailOpt-190](#entry-lian2026reloop) · [RLEA](#entry-rlvrpagents2026) · [SAC-Opt](#entry-ma2025sacopt) · [SAGE (Strategy-Aware Modeling)](#entry-strategyaware2026) · [SDRL](#entry-sdrl2026) · [ShinkaEvolve](#entry-lange2026shinka) · [SOLID](#entry-solid2026) · [SpecAHD](#entry-lai2026specahd) · [SPO](#entry-spo2026) · [StepORLM](#entry-zhou2026steporlm) · [TIDE](#entry-chen2026tide) · [VeriSimpl](#entry-verisimpl2026) · [VRPAgent](#entry-vrpagent2025) · [AlphaEvolve](#entry-novikov2025alphaevolve) · [AlphaOPT](#entry-kong2025alphaopt) · [ARS / RoutBench](#entry-li2025ars) · [Ask, Clarify, Optimize](#entry-askclarify2026) · [C-DSS](#entry-kaleta2025cdss) · [CALM / STORM](#entry-calm2025storm) · [CEoH](#entry-bomer2025emerging) · [Cold-Start Separator Configuration](#entry-lawless2024cuts) · [DAOpt / OptU](#entry-daopt2025) · [DHEvo](#entry-dheevo2025) · [DINN](#entry-dinn2025) · [DRoC](#entry-jiang2025droc) · [EASE](#entry-viktorin2025ease) · [EFS](#entry-luo2025efs) · [FunSearch for Unit Commitment](#entry-ucfunsearch2025) · [HeurAgenix](#entry-yang2025heuragenix) · [HSEvo](#entry-dat2024hsevo) · [InstSpecHH](#entry-zhang2025instspechh) · [LHNS](#entry-xie2025llmns) · [LLaMEA](#entry-vanstein2024llamea) · [LLM-discovered EDDC / MDDC](#entry-cetinkaya2025mipsmtt) · [LLM-LNS](#entry-ye2025llmlns) · [LLM-SUC](#entry-llmsuc2025) · [LLMCoSolver / E2E CO Solver](#entry-jiang2025e2eco) · [LLMOPT](#entry-jiang2025llmopt) · [LLMs for Stochastic Modeling](#entry-talebi2025stochastic) · [MCTS-AHD](#entry-zheng2025mctsahd) · [MEoH](#entry-yao2025meoh) · [MILP-Evolve](#entry-li2025milpevolve) · [MM-Agent / MM-Bench（数学建模）](#entry-liu2025mmagent) · [ModelingAgent / ModelingBench](#entry-qian2025modelingagent) · [MOID](#entry-moid2025) · [MURKA](#entry-xie2025murka) · [NCO-LLM for VRP](#entry-tran2025llmneural) · [OptimAI](#entry-thind2025optimai) · [OptiTrust](#entry-lima2025optitrust) · [OptMATH](#entry-lu2025optmath) · [OR-LLM-Agent / BWOR](#entry-zhang2025bwor) · [ORLM](#entry-huang2025orlm) · [ORMind](#entry-ormind2025) · [RedAHD](#entry-thach2025redahd) · [ReflecSched](#entry-cao2025reflecsched) · [ReSocratic / OptiBench](#entry-yang2025resocratic) · [RoCo](#entry-xu2025roco) · [SAGE / 原 EvoCut](#entry-yazdani2025evocut) · [SIRL](#entry-chen2025sirl) · [SolverLLM](#entry-solverllm2025) · [Step-Opt](#entry-wu2025stepopt) · [STRCMP](#entry-li2025strcmp) · [Validation-in-the-Loop Power Modeling](#entry-nl2ps2025) · [Visual Graph Optimization with MLLMs](#entry-bridgingviz2025) · [CAFA](#entry-deng2024cafa) · [Chain-of-Experts](#entry-xiao2024coe) · [City-LEO](#entry-jiao2024cityleo) · [EoH](#entry-liu2024eoh) · [ITINERA](#entry-tang2024itinerary) · [Multi-Stage Modeling & Verification](#entry-mostajabdaveh2024multiagent) · [OptiChat / Infeasibility Diagnosis](#entry-chen2023diagnosing) · [OptiMUS](#entry-teshnizi2024optimus) · [OptLLM](#entry-zhang2024optllm) · [RAGDyS](#entry-tang2024ragdys) · [Rare MIP Challenges](#entry-wang2024raremip) · [ReEvo](#entry-ye2024reevo) · [To the Globe / TTG](#entry-ju2024ttg) · [AEL](#entry-liu2023ael) · [AI-Copilot for Business Optimisation](#entry-alahakoon2023copilot) · [CodeT5 Mathematical Program Synthesis](#entry-synth2023) · [FunSearch](#entry-romera2023funsearch) · [LLMs for Power Engineering](#entry-li2023power) · [OptiGuide](#entry-li2023optiguide)

</details>

<a id="tech-formal"></a>

<details>
<summary>Formal verification（2 篇）</summary>

[AutoOPT](#entry-autoopt2026) · [SOVER / NLEquiv-150](#entry-bhattacharyya2026sover)

</details>

<a id="tech-behavioral"></a>

<details>
<summary>Behavioral testing（7 篇）</summary>

[Constraint Injection / VRPCoder](#entry-constraintinjection2026) · [Falsification-Based Verification](#entry-li2026falsification) · [NEMO](#entry-nemo2026) · [OptiLoop](#entry-optiloop2026) · [OptiRepair](#entry-optirepair2026) · [ReLoop / RetailOpt-190](#entry-lian2026reloop) · [ORMind](#entry-ormind2025)

</details>

<a id="tech-auxiliary-learning"></a>

<details>
<summary>Auxiliary / NCO learning（9 篇）</summary>

[DSevolve](#entry-dsevolve2026) · [Latent Heuristic Search](#entry-latentheuristic2026) · [LLM Representations for Algorithm Selection](#entry-behaviorrep2025) · [LLM-MAS for Service Operations](#entry-wang2026llmmas) · [RLEA](#entry-rlvrpagents2026) · [DINN](#entry-dinn2025) · [InstSpecHH](#entry-zhang2025instspechh) · [NCO-LLM for VRP](#entry-tran2025llmneural) · [STRCMP](#entry-li2025strcmp)

</details>

<a id="tech-multimodal"></a>

<details>
<summary>Multimodal input（2 篇）</summary>

[MM-OptBench](#entry-zhu2026mmoptbench) · [Visual Graph Optimization with MLLMs](#entry-bridgingviz2025)

</details>


[返回目录](#contents)

<a id="applications"></a>

## 应用场景索引

按论文的核心应用场景跳转到完整条目。

| 应用场景 | 论文数 | 相关论文 |
|---|---|---|
| <a id="app-scheduling"></a>调度与生产 | 12 | [DScheLLM](#entry-zhang2026dschellm) · [DSevolve](#entry-dsevolve2026) · [DynaSchedBench](#entry-dynaschedbench2026) · [Interactive Optimization Conversations](#entry-conversation2026) · [PowerAtlas / ECBench](#entry-jiang2026poweratlas) · [SMILO](#entry-li2025smilo) · [ALAS](#entry-alas2025) · [LLM-discovered EDDC / MDDC](#entry-cetinkaya2025mipsmtt) · [ReflecSched](#entry-cao2025reflecsched) · [Starjob](#entry-abgaryan2025starjob) · [RAGDyS](#entry-tang2024ragdys) · [AI-Copilot for Business Optimisation](#entry-alahakoon2023copilot) |
| <a id="app-routing"></a>路由与物流 | 17 | [AFL](#entry-zhang2026afl) · [AILS-AHD](#entry-xie2026ailsahd) · [Combinatorial Optimization for All](#entry-co4all2025) · [Constraint Injection / VRPCoder](#entry-constraintinjection2026) · [ORThought / LogiOR](#entry-yang2025orthought) · [PyVRP+ / MEP](#entry-pyvrpplus2026) · [RLEA](#entry-rlvrpagents2026) · [SpecAHD](#entry-lai2026specahd) · [SPO](#entry-spo2026) · [VRPAgent](#entry-vrpagent2025) · [ARS / RoutBench](#entry-li2025ars) · [DRoC](#entry-jiang2025droc) · [MOID](#entry-moid2025) · [NCO-LLM for VRP](#entry-tran2025llmneural) · [City-LEO](#entry-jiao2024cityleo) · [ITINERA](#entry-tang2024itinerary) · [To the Globe / TTG](#entry-ju2024ttg) |
| <a id="app-inventory"></a>库存、零售与供应链 | 15 | [Automated Inventory Policy Design](#entry-invpolicy2026) · [GenAI Beer Game Reliability](#entry-beergame2026) · [InventoryBench](#entry-invbench2026) · [InvEvolve](#entry-invevolve2026) · [LLM-MAS for Service Operations](#entry-wang2026llmmas) · [Multi-Warehouse Formulation Selection](#entry-warehouseformsel2026) · [OptiRepair](#entry-optirepair2026) · [ORLoopBench](#entry-ao2026orloopbench) · [ReLoop / RetailOpt-190](#entry-lian2026reloop) · [RetailBench](#entry-zhang2026retailbench) · [AIM-Bench](#entry-zhao2025aimbench) · [Ask, Clarify, Optimize](#entry-askclarify2026) · [EOR / Decision Information](#entry-zhang2025decisioninfo) · [InvAgent](#entry-quan2024invagent) · [OptiGuide](#entry-li2023optiguide) |
| <a id="app-energy"></a>能源与电力 | 9 | [OPF Constrained Reasoning Study](#entry-opf2026reason) · [PowerAtlas / ECBench](#entry-jiang2026poweratlas) · [ProOPF](#entry-shen2026proopf) · [Smart Grids Agentic AI Tutorial](#entry-smartgrid2026) · [ElecBench](#entry-zhou2024elecbench) · [FunSearch for Unit Commitment](#entry-ucfunsearch2025) · [LLM-SUC](#entry-llmsuc2025) · [Validation-in-the-Loop Power Modeling](#entry-nl2ps2025) · [LLMs for Power Engineering](#entry-li2023power) |
| <a id="app-finance"></a>金融与投资组合 | 5 | [LEAN-LLM-OPT](#entry-liang2026leanllmopt) · [LLM Agents for Efficient Frontiers](#entry-efficientfrontier2026) · [DINN](#entry-dinn2025) · [EFS](#entry-luo2025efs) · [LLM–Black-Litterman](#entry-llmbl2025) |
| <a id="app-warehousing"></a>仓储与装载 | 1 | [CEoH](#entry-bomer2025emerging) |
| <a id="app-networks"></a>网络与图优化 | 5 | [Infeasibility-Aware CO Models](#entry-infeasibilityaware2026) · [LLMs for DSM Sequencing](#entry-dsmco2024) · [MA-GTS / G-REAL](#entry-yuan2025magts) · [Teaching LLMs to Think Mathematically](#entry-abedi2025thinkmath) · [Visual Graph Optimization with MLLMs](#entry-bridgingviz2025) |

[返回目录](#contents)

<a id="adjacent"></a>

## 邻近研究

通用程序与科学发现、开放式数学建模，以及预测或行为模拟驱动的决策支持。

### 通用程序与科学发现

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · ICLR 2026 | **ShinkaEvolve**<br>ShinkaEvolve: Towards Open-Ended and Sample-Efficient Program Evolution | 结合父代采样、代码新颖性拒绝采样和 bandit 模型选择，提高程序演化的样本效率。 | 方法 · 平台 | [Program evolution](#tech-evolution) · [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-344]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-345]</span><br><span title="Code">[![Code][badge-008]][resource-346]</span><br>[详情](#paper-lange2026shinka) |
| 2025 · Technical report | **AlphaEvolve**<br>AlphaEvolve: A coding agent for scientific and algorithmic discovery | 用 LLM 与进化式代码修改闭环改进算法，覆盖科学问题及计算基础设施优化。 | 方法 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-419]</span><br><span title="官方结果（相关）">[![官方结果（相关）][badge-086]][resource-420]</span><br><span title="官方问题集（相关）">[![官方问题集（相关）][badge-087]][resource-421]</span><br>[详情](#paper-novikov2025alphaevolve) |
| 2023 · Nature（2023 在线发表） | **FunSearch**<br>Mathematical discoveries from program search with large language models | 结合 LLM 程序生成、进化搜索和自动评估，发现数学构造与装箱启发式。 | 方法 · 基础 | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | <span title="DOI">[![DOI][badge-001]][resource-391]</span><br><span title="Code">[![Code][badge-008]][resource-392]</span><br>[详情](#paper-romera2023funsearch) |

### 开放式数学建模

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2025 · NeurIPS 2025 | **MM-Agent / MM-Bench（数学建模）**<br>MM-Agent: LLM as Agents for Real-world Mathematical Modeling Problem | 将数学建模拆为问题分析、模型构造、计算求解和报告生成，并提供 MCM/ICM 来源的 MM-Bench。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-538]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-539]</span><br><span title="DOI">[![DOI][badge-001]][resource-540]</span><br><span title="Code &amp; MM-Bench">[![Code & MM-Bench][badge-029]][resource-541]</span><br><span title="Expert Skills (2026 add-on)">[![Expert Skills (2026 add-on)][badge-106]][resource-542]</span><br><span title="HF Demo（相关）">[![HF Demo（相关）][badge-011]][resource-543]</span><br>[详情](#paper-liu2025mmagent) |
| 2025 · Findings of EMNLP 2025 | **ModelingAgent / ModelingBench**<br>ModelingAgent: Bridging LLMs and Mathematical Modeling for Real-World Challenges | 用多 Agent 协调工具和迭代修订处理开放式建模，并以 ModelingBench 与 ModelingJudge 评估报告。 | 方法 · 基准 · 数据 | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | <span title="Proceedings">[![Proceedings][badge-005]][resource-544]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-545]</span><br><span title="Code &amp; ModelingBench">[![Code & ModelingBench][badge-029]][resource-546]</span><br>[详情](#paper-qian2025modelingagent) |

### 预测、表征与行为模拟

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 技术标签 | 资源 |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-wang2026llmmas"></a>**LLM-MAS for Service Operations**<br>Optimizing Service Operations via LLM-Powered Multi-Agent Simulation | 用交互 LLM 模拟参与者响应，并以轨迹上的梯度估计和方差缩减优化服务设计。 | 方法 · 应用 | [Agent](#tech-agent) · [Auxiliary / NCO learning](#tech-auxiliary-learning) | <span title="arXiv">[![arXiv][badge-002]][resource-558]</span><br>[详情](#paper-wang2026llmmas) |
| 2025 · arXiv preprint / submitted paper | <a id="entry-dinn2025"></a>**DINN**<br>Decision-informed Neural Networks with Large Language Model Integration for Portfolio Optimization | 将 LLM 表征与决策导向训练结合，通过可微凸优化层直接对齐组合投资目标。 | 方法 · 应用 | [Auxiliary / NCO learning](#tech-auxiliary-learning) · [Execution / solver feedback](#tech-solver-feedback) | <span title="arXiv">[![arXiv][badge-002]][resource-559]</span><br><span title="Code">[![Code][badge-008]][resource-560]</span><br>[详情](#paper-dinn2025) |
| 2025 · IEEE PESGM 2025 | **ElecBench**<br>ElecBench: a Power Grid Dispatch Evaluation Benchmark for Large Language Models | 以电力知识、监控、调度和黑启动文本任务评价事实性、逻辑性及稳定性等维度。 | 基准 · 数据 |  | <span title="DOI">[![DOI][badge-001]][resource-548]</span><br><span title="arXiv">[![arXiv][badge-002]][resource-549]</span><br><span title="Public Test Subset">[![Public Test Subset][badge-107]][resource-550]</span><br>[详情](#paper-zhou2024elecbench) |
| 2025 · CIKM 2025 Financial AI Workshop | <a id="entry-llmbl2025"></a>**LLM–Black-Litterman**<br>LLM-Enhanced Black-Litterman Portfolio Optimization | 将 LLM 收益预测和不确定性转换为 Black–Litterman 投资观点及置信度。 | 方法 · 应用 |  | <span title="arXiv">[![arXiv][badge-002]][resource-561]</span><br><span title="Workshop">[![Workshop][badge-092]][resource-562]</span><br><span title="Code">[![Code][badge-008]][resource-563]</span><br>[详情](#paper-llmbl2025) |


<a id="paper-info"></a>

## 作者与版本

<details>
<summary>2026 · 作者与版本</summary>

| 论文与作者 | 版本与资源说明 |
|---|---|
| <a id="paper-chen2026a2dept"></a>**A2DEPT**<br>Bin Chen; Shouliang Zhu; Beidan Liu; Yong Zhao; Tianle Pu; Huichun Li; Zhengqiu Zhu<br>[返回论文条目](#entry-chen2026a2dept) | 发表信息：2026 · ICML 2026<br>论文版本：2604.24043v1<br>程序树演化与 LLM 参数训练分开归类。 |
| <a id="paper-zhang2026afl"></a>**AFL**<br>Ni Zhang; Zhiguang Cao; Jianan Zhou; Cong Zhang; Yew-Soon Ong<br>[返回论文条目](#entry-zhang2026afl) | 发表信息：2026 · ICLR 2026<br>论文版本：2510.16701v2<br>生成自包含求解代码；DRoC 使用外部求解器与文档检索。 |
| <a id="paper-xu2026agenticmip"></a>**Agentic MIP Research**<br>Liding Xu; Yugeng Zhou; Sebastian Pokutta<br>[返回论文条目](#entry-xu2026agenticmip) | 发表信息：2026 · arXiv preprint<br>论文版本：2605.09186v1<br>生成的 SCIP 传播规则通过框架测试和求解评估；数学有效性需要单独证明。 |
| <a id="paper-soliloquy2026"></a>**Agora-Opt**<br>Jianghao Lin; Zi Ling; Chenyu Zhou; Tianyi Xu; Ruoqing Jiang; Zizhuo Wang; Dongdong Ge<br>[返回论文条目](#entry-soliloquy2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2604.25847v1<br>修订数据沿用七组既有基准；求解一致性与完整题意符合性分开判断。 |
| <a id="paper-xie2026ailsahd"></a>**AILS-AHD**<br>Zhuoliang Xie; Fei Liu; Zhenkun Wang; Qingfu Zhang<br>[返回论文条目](#entry-xie2026ailsahd) | 发表信息：2026 · arXiv preprint<br>论文版本：2602.23092v2<br>AILS-CVRP 与 PyHygese 为基线或底层工具。 |
| <a id="paper-invpolicy2026"></a>**Automated Inventory Policy Design**<br>Fenghua Yang; Preet Baxi; Yi Zhang; Stefanus Jasin; Yanzhe Lei; Mo Liu; Parshan Pakiman<br>[返回论文条目](#entry-invpolicy2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2609.08071v1 |
| <a id="paper-sun2025satheur"></a>**AutoModSAT**<br>Yiwen Sun; Furong Ye; Zhihan Chen; Ke Wei; Shaowei Cai<br>[返回论文条目](#entry-sun2025satheur) | 发表信息：2026 · Nature Communications（2026）<br>论文版本：2507.22876v2<br>Automatically Discovering Heuristics in a Complex SAT Solver with Large Language Models <span title="arXiv">[![arXiv][badge-002]][resource-447]</span>：预印本题名含 Automatically，当前正式版题名不含该词<br>早期题名含 Automatically，期刊版题名改为 Discovering。 |
| <a id="paper-autoopt2026"></a>**AutoOPT**<br>Heechang Kim; Ernest K. Ryu; Shuvomoy Das Gupta<br>[返回论文条目](#entry-autoopt2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2608.07407v1<br>两个形式化案例依赖具体假设，流程包含人工审查。 |
| <a id="paper-autoor2026"></a>**AutoOR**<br>Sumeet Ramesh Motwani; Chuan Du; Aleksander Petrov; Christopher Davis; Philip Torr; Antonio Papania-Davis; Weishi Yan<br>[返回论文条目](#entry-autoor2026) | 发表信息：2026 · ICML 2026 RLxF Workshop / arXiv<br>论文版本：2604.16804v4<br>ICML 2026 页面明确为 RLxF: RL from World Feedback Workshop，不标主会。当前 arXiv 标题为 Autoformulate，会议页面为 Autoformalize；标准 verifiers / TRL 库不当作本方法实现。 |
| <a id="paper-robustreform2026"></a>**AutoREM / AutoRO-Bench**<br>Jinbiao Chen; Shuang Jin; Guoyun Zhang; Junyu Zhang; Guanyi Wang; Hanzhang Qin<br>[返回论文条目](#entry-robustreform2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2605.11813v1 |
| <a id="paper-sun2024autosat"></a>**AutoSAT**<br>Yiwen Sun; Furong Ye; Xianyin Zhang; Shiyu Huang; Bingzhen Zhang; Ke Wei; Shaowei Cai<br>[返回论文条目](#entry-sun2024autosat) | 发表信息：2026 · JAIR 86（2026）<br>论文版本：2402.10705v3<br>期刊版发表于 2026 年，预印本首发于 2024 年。 |
| <a id="paper-bife2026"></a>**BiFE**<br>Ce Zhang; Bin Zhang; Zhiwei Xu; Hao Chen; Xinyue Lu; Shanwei Fan; Yingxuan Teng; Guoliang Fan<br>[返回论文条目](#entry-bife2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2609.36735v1 |
| <a id="paper-huang2025calm"></a>**CALM (Algorithm–LM Co-evolution)**<br>Ziyao Huang; Weiwei Wu; Kui Wu; Wei-Bin Lee; Jianping Wang<br>[返回论文条目](#entry-huang2025calm) | 发表信息：2026 · ICLR 2026<br>论文版本：2505.12285v1<br>CALM: Co-evolution of Algorithms and Language Model for Automatic Heuristic Design <span title="arXiv">[![arXiv][badge-002]][resource-309]</span>：预印本版本；作者：Ziyao Huang; Weiwei Wu; Kui Wu; Jianping Wang; Wei-Bin Lee<br>提供 GRPO 代码；与 CALM Before the STORM 为不同工作。 |
| <a id="paper-lporch2025"></a>**CHORUS**<br>Tasnim Ahmed; Salimur Choudhury<br>[返回论文条目](#entry-lporch2025) | 发表信息：2026 · LION 19 / LNCS 15745（2026 出版）<br>论文版本：2505.01485v1<br>LION 19 为 2025 年会议，章节于 2026-01-02 出版。目标值匹配是该评测的操作性判据。 |
| <a id="paper-canonicalir2026"></a>**CIR / R2C**<br>Zhongyuan Lyu; Shuoyu Hu; Lujie Liu; Hongxia Yang; Ming LI<br>[返回论文条目](#entry-canonicalir2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2602.02029v1<br>原文中间表示用于约束语义与建模范式选择，不自动提供跨求解器正确性保证。 |
| <a id="paper-sun2026cobench"></a>**CO-Bench**<br>Weiwei Sun; Shengyu Feng; Shanda Li; Yiming Yang<br>[返回论文条目](#entry-sun2026cobench) | 发表信息：2026 · AAAI 2026<br>正式发表于 AAAI 2026；HF 数据资源为 CO-Bench/CO-Bench。 |
| <a id="paper-co4all2025"></a>**Combinatorial Optimization for All**<br>Camilo Chacón Sartori; Christian Blum<br>[返回论文条目](#entry-co4all2025) | 发表信息：2026 · Inteligencia Artificial 29（2026）<br>论文版本：2503.10968v1<br>Combinatorial Optimization for All: Using LLMs to Aid Non-Experts in Improving Optimization Algorithms <span title="arXiv">[![arXiv][badge-002]][resource-313]</span>：预印本版本；作者：Camilo Chacón Sartori; Christian Blum<br>作者资源包括提示、生成算法、实例和结果；未将其标为新的通用组合优化基准。 |
| <a id="paper-lco2026review"></a>**Combinatorial Optimization Systematic Review**<br>Francesca Da Ros; Michael Soprano; Luca Di Gaspero; Kevin Roitero<br>[返回论文条目](#entry-lco2026review) | 发表信息：2026 · ACM Computing Surveys 58（2026）<br>论文版本：2507.03637v1<br>Large Language Models for Combinatorial Optimization: A Systematic Review <span title="arXiv">[![arXiv][badge-002]][resource-002]</span>：预印本版本；作者：Francesca Da Ros; Michael Soprano; Luca Di Gaspero; Kevin Roitero |
| <a id="paper-constraintinjection2026"></a>**Constraint Injection / VRPCoder**<br>Xizi Luo; Changhong He; Dongdong Geng; Chenggong Shi; Yu Mei<br>[返回论文条目](#entry-constraintinjection2026) | 发表信息：2026 · Findings of EMNLP 2026<br>论文版本：2606.04816v2<br>VRPBench 仓库提供问题与参考最优值。 |
| <a id="paper-constraintbench2026"></a>**ConstraintBench**<br>Joseph Tso; Preston Schmittou; Quan Huynh; Jibran Hutchins<br>[返回论文条目](#entry-constraintbench2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2602.22465v2 |
| <a id="paper-coopa2026"></a>**COOPA**<br>Chuanhao Li; Xiaoan Xu; Dirk Bergemann; Ethan X. Fang; Yehua Wei; Zhuoran Yang<br>[返回论文条目](#entry-coopa2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2606.27611v1<br>置信度来自模型自评，来源可追溯不等于模型已获形式化正确性或概率校准保证。 |
| <a id="paper-cpagent2025"></a>**CP-Agent**<br>Stefan Szeider<br>[返回论文条目](#entry-cpagent2025) | 发表信息：2026 · LLM4Code 2026 Workshop @ ICSE<br>论文版本：2508.07468v3<br>Zenodo v2（2026-07-14）修正了变异审计发现的验证问题；实验结果按版本区分。<br>Author Coding Agent：通用编码 Agent 与 CPMpy 模板；修订评测材料位于 Zenodo。 |
| <a id="paper-cpsync2026"></a>**CP-SynC**<br>Yuliang Song; Eldan Cohen<br>[返回论文条目](#entry-cpsync2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2605.01675v1<br>官方仓库提供 benchmark 与 eval.py。<br>Benchmark & Evaluation：提供数据与评测代码。 |
| <a id="paper-xiao2026deepor"></a>**DeepOR**<br>Ziyang Xiao; Yuan Jessica Wang; Xiongwei Han; Shisi Guan; Jingyan Zhu; Jingrong Xie; Lilin Xu; Han Wu; Wing Yin Yu; Zehua Liu; Xiaojin Fu; Gang Chen; Dongxiang Zhang<br>[返回论文条目](#entry-xiao2026deepor) | 发表信息：2026 · AAAI 2026<br>官方种子与样例数据：包含种子和 SFT/RL 样例。 |
| <a id="paper-zhang2026dschellm"></a>**DScheLLM**<br>Lixiang Zhang; Chenggong Zhao; Qing Gao; Xiaoke Zhao; Gengyi Bai; Jinhu Lv<br>[返回论文条目](#entry-zhang2026dschellm) | 发表信息：2026 · arXiv preprint<br>论文版本：2601.09100 |
| <a id="paper-dsevolve2026"></a>**DSevolve**<br>XinLei Zhou; Jin Huang; Jie Yang; Xinyu Li; Liang Gao<br>[返回论文条目](#entry-dsevolve2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2603.27628v2<br>训练对象为神经选择器。 |
| <a id="paper-dynaschedbench2026"></a>**DynaSchedBench**<br>Shijie Cao; Yuan Yuan; Jing Liu<br>[返回论文条目](#entry-dynaschedbench2026) | 发表信息：2026 · ICML 2026 · PMLR 306<br>论文版本：2605.27566v1<br>提供实例生成器、数据、仿真与评测代码。 |
| <a id="paper-epoch2026"></a>**EPOCH**<br>Oguzhan Gungordu; Ayse Tursucular; Siheng Xiong; Faramarz Fekri<br>[返回论文条目](#entry-epoch2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2610.17379v1 |
| <a id="paper-es2026ahd"></a>**ES-AHD**<br>Yutao Lai; Kezhao Lai; Hai-Lin Liu; Yuping Wang; Ping Guo<br>[返回论文条目](#entry-es2026ahd) | 发表信息：2026 · ICIST 2026（已接收）<br>论文版本：2609.00023v1<br>实现包含 run_es_ahd.py 与 llm4ad 目录。 |
| <a id="paper-chen2026evobb"></a>**Evo-B&B**<br>Jiayu Chen; Chentong Chen; Yuhan Liu; Ye Fan; Jianyong Sun; Jialong Shi<br>[返回论文条目](#entry-chen2026evobb) | 发表信息：2026 · arXiv preprint<br>论文版本：2610.22861v1 |
| <a id="paper-guan2026evom"></a>**EVOM**<br>Runda Guan; Xiangqing Shen; Jiajun Zhang; Yifan Zhang; Jian Cheng; Rui Xia<br>[返回论文条目](#entry-guan2026evom) | 发表信息：2026 · arXiv preprint<br>论文版本：2604.00442v1<br>执行成功或目标值匹配与题意符合性的数学证明分开。 |
| <a id="paper-he2026evoopt"></a>**EvoOpt-LLM**<br>Yiliu He; Tianle Li; Binghao Ji; Zhiyuan Liu; Di Huang<br>[返回论文条目](#entry-he2026evoopt) | 发表信息：2026 · arXiv preprint<br>论文版本：2602.01082<br>采用 Openpangu-7B；变量剪枝依据经验分类结果。 |
| <a id="paper-evooptigraph2026"></a>**EvoOptiGraph**<br>Qingcan Kang; Mingyang Liu; Xiaojin Fu; Shixiong Kai; Tao Zhong; Mingxuan Yuan<br>[返回论文条目](#entry-evooptigraph2026) | 发表信息：2026 · NeurIPS 2026（已接收，待出版）<br>论文版本：2606.26578v1<br>图操作、编译与回译检查依赖原文设定。 |
| <a id="paper-coevolve2026"></a>**EvoOR-Agent**<br>Jiahao Huang; Peilan Xu; Xiaoya Nan; Wenjian Luo<br>[返回论文条目](#entry-coevolve2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2604.17708v2<br>演化对象是 Agent 架构和推理程序。 |
| <a id="paper-li2026falsification"></a>**Falsification-Based Verification**<br>Haifeng Li; Mo Hai<br>[返回论文条目](#entry-li2026falsification) | 发表信息：2026 · arXiv preprint<br>论文版本：2607.16646v2<br>这是有条件的可证伪审计，适用范围取决于原文假设。 |
| <a id="paper-wang2026formalize"></a>**Formalize, Don't Optimize**<br>Haoyu Wang; Yuliang Song; Tao Li; Zhiwei Deng; Yaqing Wang; Deepak Ramachandran; Eldan Cohen; Dan Roth<br>[返回论文条目](#entry-wang2026formalize) | 发表信息：2026 · arXiv；NeurIPS 2026 Workshop 版本<br>论文版本：2605.12421v1<br>对应 NeurIPS 2026 Who Verifies the Agents? Workshop；提出 CP-SynC-XL 评测。 |
| <a id="paper-yuan2026formuevo"></a>**FormuEvo**<br>Haofeng Yuan; Jianing Peng; Jieyi Bi; Ni Zhang; Shiji Song; Zhiguang Cao<br>[返回论文条目](#entry-yuan2026formuevo) | 发表信息：2026 · EMNLP 2026<br>论文版本：2608.23353v2<br>运行反馈用于经验诊断，形式化等价性需要单独核验。 |
| <a id="paper-kong2026frontieror"></a>**FrontierOR**<br>Minwei Kong; Chonghe Jiang; Ao Qu; Wenbin Ouyang; Zhaoming Zeng; Xiaotong Guo; Zhekai Li; Junyi Li; Yi Fan; Xinshou Zheng; Xi Jing; Yikai Zhang; Zhiwei Liang; Seonghoo Kim; Runqing Yang; Zijian Zhou; Sirui Li; Han Zheng; Wangyang Ying; Ou Zheng; Chonghuan Wang; Jinglong Zhao; Hanzhang Qin; Cathy Wu; Paul Pu Liang; Jinhua Zhao; Hai Wang<br>[返回论文条目](#entry-kong2026frontieror) | 发表信息：2026 · NeurIPS 2026（已接收，待出版）<br>论文版本：2605.25246v3<br>相关版本 <span title="Paper">[![Paper][badge-124]][resource-513]</span>：FrontierOR-v1，180 项；发布日期 2026-09-27<br>相关版本 <span title="Paper">[![Paper][badge-007]][resource-510]</span>：会议版本摘要描述 110 项任务。 |
| <a id="paper-yu2026alns"></a>**Full-Component ALNS Evolution**<br>Shaohua Yu; Tianyu Chen; Linyan Liu; Jakob Puchinger<br>[返回论文条目](#entry-yu2026alns) | 发表信息：2026 · arXiv preprint<br>论文版本：2603.06996v2<br>仓库提供演化生成的 ALNS 程序。<br>Evolved ALNS：演化生成的 ALNS 程序。 |
| <a id="paper-zhao2026glns"></a>**G-LNS**<br>Baoyun Zhao; He Wang; Liang Zeng<br>[返回论文条目](#entry-zhao2026glns) | 发表信息：2026 · arXiv preprint<br>论文版本：2602.08253v1 |
| <a id="paper-beergame2026"></a>**GenAI Beer Game Reliability**<br>Carol Xuan Long; David Simchi-Levi; Feng Zhu; Huangyuan Su; Andre P. Calmon; Flavio P. Calmon<br>[返回论文条目](#entry-beergame2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2605.17036v4<br>实验采用既有 Beer Game，结果依赖具体配置与需求路径。 |
| <a id="paper-luo2026grimip"></a>**GRIMIP**<br>Yidong Luo; Xuemin Chen; Chenguang Wang; Fangzhou Zhu; Tao Zhong; Tianshu Yu<br>[返回论文条目](#entry-luo2026grimip) | 发表信息：2026 · arXiv preprint<br>论文版本：2606.23299v2 |
| <a id="paper-chen2025heurigym"></a>**HeuriGym**<br>Hongzheng Chen; Yingheng Wang; Yaohui Cai; Hins Hu; Jiajie Li; Shirley Huang; Chenhui Deng; Rongjian Liang; Shufeng Kong; Haoxing Ren; Samitha Samaranayake; Carla P. Gomes; Zhiru Zhang<br>[返回论文条目](#entry-chen2025heurigym) | 发表信息：2026 · ICLR 2026<br>论文版本：2506.07972v2 |
| <a id="paper-chen2025hifoprompt"></a>**HiFo-Prompt**<br>Chentong Chen; Mengyuan Zhong; Jialong Shi; Jianyong Sun; Ye Fan<br>[返回论文条目](#entry-chen2025hifoprompt) | 发表信息：2026 · ICLR 2026<br>论文版本：2508.13333v2<br>HiFo-Prompt: Prompting with Hindsight and Foresight for LLM-based Automatic Heuristic Design <span title="arXiv">[![arXiv][badge-002]][resource-322]</span>：预印本版本；作者：Chentong Chen; Mengyuan Zhong; Ye Fan; Jialong Shi; Jianyong Sun |
| <a id="paper-infeasibilityaware2026"></a>**Infeasibility-Aware CO Models**<br>Yakun Wang; Min Chen; Zeguan Wu; Junyu Liu; Sitao Zhang; Zhenwen Shao<br>[返回论文条目](#entry-infeasibilityaware2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2604.01455v1<br>数据认证与筛选定理依赖明确条件；Google Drive 提供图着色和 embedding 文件夹。<br>Author Code / Data Archive：原文关联的代码与数据归档。 |
| <a id="paper-conversation2026"></a>**Interactive Optimization Conversations**<br>Joshua Drossman; Alexandre Jacquillat; Sébastien Martin<br>[返回论文条目](#entry-conversation2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2604.02666v1<br>实现包含 decision_agent 与 evaluation 模块。 |
| <a id="paper-invbench2026"></a>**InventoryBench**<br>Jackie Baek; Yaopeng Fu; Will Ma; Tianyi Peng<br>[返回论文条目](#entry-invbench2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2602.12631v2 |
| <a id="paper-invevolve2026"></a>**InvEvolve**<br>Chenyu Huang; Jianghao Lin; Zhengyang Tang; Bo Jiang; Ruoqing Jiang; Benyou Wang; Lai Wei<br>[返回论文条目](#entry-invevolve2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2605.00369v4 |
| <a id="paper-jorbench2026"></a>**JOR-Bench**<br>Yuu Jinnai<br>[返回论文条目](#entry-jorbench2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2607.16777v1<br>日文版本是派生资源，不声称首次提出五个源基准。HF 显示的 2,638 行包含日英两种语言，不把它们当作 2,638 道不同源问题；求解答案匹配也不等同全面语义验证。 |
| <a id="paper-hsplo2026"></a>**LaGO**<br>Mingxin Yu; Ruixiao Yang; Chuchu Fan<br>[返回论文条目](#entry-hsplo2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2602.16038v1<br>forward / backward / update 描述评价、反馈和程序改写，不自动表示 LLM 反向传播或参数训练。未将引用的 ReEvo 仓库当作本方法代码。 |
| <a id="paper-latentheuristic2026"></a>**Latent Heuristic Search**<br>Cheikh Ahmed; Mahdi Mostajabdaveh; Zirui Zhou<br>[返回论文条目](#entry-latentheuristic2026) | 发表信息：2026 · LION 20 / 2026（已接收）<br>论文版本：2605.17137v1<br>训练辅助编码 / 代理 / 映射模块，生成 LLM 保持冻结。 |
| <a id="paper-liang2026leanllmopt"></a>**LEAN-LLM-OPT**<br>Kuo Liang; Yuhang Lu; Jianming Mao; Shuyi Sun; Chunwei Yang; Congcong Zeng; Xiao Jin; Hanzhang Qin; Ruihao Zhu; Chung-Piaw Teo<br>[返回论文条目](#entry-liang2026leanllmopt) | 发表信息：2026 · arXiv preprint<br>论文版本：2601.09635v3 |
| <a id="paper-ma2024llamoco"></a>**LLaMoCo**<br>Zeyuan Ma; Yue-Jiao Gong; Hongshu Guo; Jiacheng Chen; Yining Ma; Zhiguang Cao; Jun Zhang<br>[返回论文条目](#entry-ma2024llamoco) | 发表信息：2026 · IEEE TEVC 30（2026）<br>论文版本：2403.01131v2<br>LLaMoCo: Instruction Tuning of Large Language Models for Optimization Code Generation <span title="arXiv">[![arXiv][badge-002]][resource-330]</span>：预印本版本；作者：Zeyuan Ma; Hongshu Guo; Jiacheng Chen; Guojun Peng; Zhiguang Cao; Yining Ma; Yue-Jiao Gong<br>TEVC 2026 正式版与 2024 预印本的作者分别列示。提供 LLaMoCo-S 示例和 CodeGen 权重。 |
| <a id="paper-efficientfrontier2026"></a>**LLM Agents for Efficient Frontiers**<br>Simon Paquette-Greenbaum; Jiangbo Yu<br>[返回论文条目](#entry-efficientfrontier2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2601.00770v1 |
| <a id="paper-zhang2026autoconfig"></a>**LLM MIP Configuration**<br>Michael Zhang; Justin Okamoto; Antonia Chmiela; Oleksandr Radomskyi; Christian Schulz; Jeremy L Wyatt<br>[返回论文条目](#entry-zhang2026autoconfig) | 发表信息：2026 · NeurIPS 2026 MLxOR Workshop（已接收，待召开） |
| <a id="paper-behaviorrep2025"></a>**LLM Representations for Algorithm Selection**<br>Francesca Da Ros; Luca Di Gaspero; Kevin Roitero<br>[返回论文条目](#entry-behaviorrep2025) | 发表信息：2026 · Computers & Operations Research 196（2026-12 编期）<br>论文版本：2512.13374v2<br>Behavior and Representation in Open-Weight Large Language Models for Combinatorial Optimization: From Feature Extraction to Algorithm Selection <span title="arXiv">[![arXiv][badge-002]][resource-519]</span>：预印本版本；作者：Francesca Da Ros; Luca Di Gaspero; Kevin Roitero<br>出版社记录列为 2026 年 12 月编期；Zenodo 归档提供代码、数据、激活与探测实验材料。<br>Code & Analysis Data：约 1.32 GB，包含代码、数据、激活与探测实验材料。 |
| <a id="paper-zheng2026cutmgmt"></a>**LLM-guided Cutting-plane Management**<br>Zetao Zheng; Zhe Wang; Jie Shao<br>[返回论文条目](#entry-zheng2026cutmgmt) | 发表信息：2026 · IJCAI 2026 · AI4Tech |
| <a id="paper-wang2026llmmas"></a>**LLM-MAS for Service Operations**<br>Yanyuan Wang; Xiaowei Zhang<br>[返回论文条目](#entry-wang2026llmmas) | 发表信息：2026 · arXiv preprint<br>论文版本：2604.04383v1<br>LLM 模拟行为，外层算法更新设计参数；不能将其等同于 LLM 直接执行数值求解。 |
| <a id="paper-liu2024systematic"></a>**LLM4AD Survey**<br>Fei Liu; Yiming Yao; Ping Guo; Zhiyuan Yang; Zhe Zhao; Xi Lin; Xialiang Tong; Kun Mao; Zhichao Lu; Zhenkun Wang; Mingxuan Yuan; Qingfu Zhang<br>[返回论文条目](#entry-liu2024systematic) | 发表信息：2026 · ACM Computing Surveys 58(8), Article 218<br>2026-02-10 发表。 |
| <a id="paper-llm4branch2026"></a>**LLM4Branch**<br>Zhinan Hou; Xingchen Li; Yankai Zhang; Tianxun Li; Keyou You<br>[返回论文条目](#entry-llm4branch2026) | 发表信息：2026 · ICML 2026<br>论文版本：2605.10401v1 |
| <a id="paper-llmasopt2026"></a>**LLMs as Optimizers Survey**<br>Roko Peran; Luka Hobor; Mihael Kovac; Mario Brcic<br>[返回论文条目](#entry-llmasopt2026) | 发表信息：2026 · MIPRO 2026<br>论文版本：2606.15577v1 |
| <a id="paper-sysevo2025"></a>**LLMs for Evolutionary Optimization Survey**<br>Yisong Zhang; Ran Cheng; Guoxing Yi; Kay Chen Tan<br>[返回论文条目](#entry-sysevo2025) | 发表信息：2026 · IEEE CIM（期刊记录）<br>论文版本：2509.08269v7 |
| <a id="paper-meevo2026"></a>**MeEvo**<br>Zishang Qiu; Xinan Chen; Rong Qu; Ruibin Bai<br>[返回论文条目](#entry-meevo2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2606.14202v5 |
| <a id="paper-chen2025mela"></a>**MeLA**<br>Zishang Qiu; Xinan Chen; Long Chen; Wenjie Yi; Ruibin Bai<br>[返回论文条目](#entry-chen2025mela) | 发表信息：2026 · Expert Systems with Applications 330（2026-12 编期）<br>论文版本：2507.20541v4<br>MeLA: A Metacognitive LLM-Driven Architecture for Automatic Heuristic Design <span title="arXiv">[![arXiv][badge-002]][resource-337]</span>：预印本版本；作者：Zishang Qiu; Xinan Chen; Long Chen; Ruibin Bai<br>ESWA 为 2026 年 12 月编期；期刊版增加作者 Wenjie Yi。 |
| <a id="paper-milpevo2026"></a>**MILP-Evo**<br>Jinbiao Nie; Kewei Feng; Xiaoyuan Zhang; Shan Yin; Zizhuo Wang; Bin Dong<br>[返回论文条目](#entry-milpevo2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2607.18252v1<br>实现针对 SCIP 的割选择与分支回调。 |
| <a id="paper-mind2026"></a>**MIND**<br>Weiting Liu; Han Wu; Yufei Kuang; Xiongwei Han; Tao Zhong; Jianfeng Feng; Wenlian Lu<br>[返回论文条目](#entry-mind2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2602.11164v1 |
| <a id="paper-zhao2026miniopt"></a>**MiniOpt**<br>Ke Zhao; Zixiang Di; Hong Qian; Xiang Shu; Yaolin Wen; Qitao Shi; Bingdong Li; Xingyu Lu; Xiangfeng Wang; Jun Zhou; Ke Tang; Yang Yu<br>[返回论文条目](#entry-zhao2026miniopt) | 发表信息：2026 · arXiv preprint<br>论文版本：2606.25832v2<br>提供训练、推理代码与示例数据。 |
| <a id="paper-li2026miplibnl"></a>**MIPLIB-NL**<br>Zhong Li; Hongliang Lu; Tao Wei; Yuxuan Chen; Wenyu Liu; Yuan Lan; Fan Zhang; Zaiwen Wen<br>[返回论文条目](#entry-li2026miplibnl) | 发表信息：2026 · ICML 2026<br>GitHub dataset：`dataset/<problem>/` 包含 `instance.json`、`model.md`、`solve.py` 与数据文件。 |
| <a id="paper-mirror2026"></a>**MIRROR**<br>Yifan Shi; Jiayi Wang; Minyi Wu; Ye Fan; Jialong Shi; Jianyong Sun<br>[返回论文条目](#entry-mirror2026) | 发表信息：2026 · arXiv preprint<br>论文版本：arXiv:2602.03318v4 |
| <a id="paper-zhu2026mmoptbench"></a>**MM-OptBench**<br>Zhong Li; Qi Huang; Yuxuan Zhu; Mohammad Mohammadi Amiri; Niki van Stein; Thomas Bäck; Matthijs van Leeuwen; Zaiwen Wen; Lincen Yang<br>[返回论文条目](#entry-zhu2026mmoptbench) | 发表信息：2026 · NeurIPS 2026（已接收，待出版）<br>论文版本：2605.12154v1 |
| <a id="paper-moh2025"></a>**MoH**<br>Yiding Shi; Jianan Zhou; Wen Song; Jieyi Bi; Yaoxin Wu; Zhiguang Cao; Jie Zhang<br>[返回论文条目](#entry-moh2025) | 发表信息：2026 · ICLR 2026<br>论文版本：2505.20881<br>Generalizable Heuristic Generation Through LLMs with Meta-Optimization <span title="arXiv">[![arXiv][badge-002]][resource-416]</span>：预印本版本；作者：Yiding Shi; Jianan Zhou; Wen Song; Jieyi Bi; Yaoxin Wu; Zhiguang Cao; Jie Zhang<br>multi-task training 指元优化程序的多任务搜索与评价；Google Drive 提供任务数据归档。<br>CO Task Data：任务数据归档 data.zip。 |
| <a id="paper-ha2025paretogrid"></a>**MPaGE**<br>Ha Minh Hieu; Hung Phan; Tung Duy Doan; Tung Dao; Cong Dao Tran; Huynh Thi Thanh Binh<br>[返回论文条目](#entry-ha2025paretogrid) | 发表信息：2026 · AAAI 2026<br>论文版本：2507.20923v3<br>Pareto-Grid-Guided Large Language Models for Fast and High-Quality Heuristics Design in Multi-Objective Combinatorial Optimization <span title="arXiv">[![arXiv][badge-002]][resource-339]</span>：预印本版本；作者：Minh Hieu Ha; Hung Phan; Tung Duy Doan; Tung Dao; Dao Tran; Huynh Thi Thanh Binh |
| <a id="paper-warehouseformsel2026"></a>**Multi-Warehouse Formulation Selection**<br>Jintao Xu; Yingzheng Ma; Jiong Dong; Yongzhi Qi; Jianshen Zhang<br>[返回论文条目](#entry-warehouseformsel2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2607.25956v1<br>实验基于京东多仓库存分配实例。 |
| <a id="paper-nemo2026"></a>**NEMO**<br>Yang Song; Anoushka Vyas; Zirui Wei; Sina Khoshfetrat Pakazad; Henrik Ohlsson; Graham Neubig<br>[返回论文条目](#entry-nemo2026) | 发表信息：2026 · ICML 2026 · PMLR 306<br>论文版本：2601.21372v3<br>HF 提供七组逐题输出与轨迹、两组结果表。执行检查用于评测诊断，题意符合性需单独判断。 |
| <a id="paper-jiang2026nlco"></a>**NLCO**<br>Xia Jiang; Jing Chen; Cong Zhang; Jie Gao; Chengpeng Hu; Chenhao Zhang; Yaoxin Wu; Yingqian Zhang<br>[返回论文条目](#entry-jiang2026nlco) | 发表信息：2026 · Findings of ACL 2026<br>论文版本：2602.02188v2 |
| <a id="paper-opf2026reason"></a>**OPF Constrained Reasoning Study**<br>Fabien Bernier; Salah Ghamizi; Pantelis Dogoulis; Maxime Cordy<br>[返回论文条目](#entry-opf2026reason) | 发表信息：2026 · arXiv preprint<br>论文版本：2603.23004v1 |
| <a id="paper-li2026optbench"></a>**OPT-BENCH / OPT-Agent**<br>Xiaozhe Li; Jixuan Chen; Xinyu Fang; Shengyuan Ding; Haodong Duan; Qingwen Liu (刘晴雯); Kai Chen<br>[返回论文条目](#entry-li2026optbench) | 发表信息：2026 · Findings of ACL 2026<br>论文版本：2506.10764v1<br>OPT-BENCH: Evaluating LLM Agent on Large-Scale Search Spaces Optimization Problems <span title="arXiv">[![arXiv][badge-002]][resource-293]</span>：原预印本<br>OPT-BENCH: Evaluating the Iterative Self-Optimization of LLM Agents in Large-Scale Search Spaces <span title="Revised Preprint">[![Revised Preprint][badge-071]][resource-294]</span>：修订预印本<br>正式版与预印本的题名不同，另有 2605.08904 修订稿。 |
| <a id="paper-chen2026optengine"></a>**OPT-Engine**<br>Yitian Chen; Cheng Cheng; Yinan Sun; Zi Ling; Dongdong Ge<br>[返回论文条目](#entry-chen2026optengine) | 发表信息：2026 · ICML 2026 · PMLR 306<br>论文版本：2601.19924v2 |
| <a id="paper-optminer2026"></a>**Opt-Miner**<br>Haoyang Liu; Yuyang Cai; Jie Wang; Xiongwei Han; Minyang Hu; Shuqi Liu; Mingxuan Yuan; Jianye Hao; Feng Wu<br>[返回论文条目](#entry-optminer2026) | 发表信息：2026 · ICML 2026 · PMLR 306<br>代码、HF 结果和演示为第三方有限复现，主要评估基座 Qwen3-8B。 |
| <a id="paper-optarcus2026"></a>**OptArgus**<br>Zhong Li; Zihan Guo; Xiaohan Lu; Juntao Wang; Jie Song; Chao Shen; Jiageng Wu; Mingyang Sun<br>[返回论文条目](#entry-optarcus2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2605.11738v1<br>评测套件包含三个部分。 |
| <a id="paper-xiu2026optgraph"></a>**OptGraph**<br>Xianchao Xiu; Jianhao Li; Huangyue Chen; Wanquan Liu<br>[返回论文条目](#entry-xiu2026optgraph) | 发表信息：2026 · arXiv preprint<br>论文版本：2607.27918v1<br>公开主流程、种子知识图和更新工具。 |
| <a id="paper-optiagentbench2026"></a>**Opti-Agent-Bench**<br>Yongchang Fu; Xinjie Huang; Chengjun Dai; Chengzhe Feng; Junshao Zhang; Hong Zhu<br>[返回论文条目](#entry-optiagentbench2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2607.10768v1 |
| <a id="paper-optiagent2026"></a>**OptiAgent**<br>Adriana Laurindo Monteiro; Nayse Fagundes; Gabriel Mattos Langeloh; Gustavo de Oliveira Kanno; Priscila Louise Aguirre; Thiago Costa Rizuti da Rocha; Victor Leme Beltran<br>[返回论文条目](#entry-optiagent2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2607.05346v1<br>在四组既有基准上评测。 |
| <a id="paper-chen2025optichat"></a>**OptiChat**<br>Hao Chen; Gonzalo Esteban Constante-Flores; Krishna Sri Ipsit Mantri; Sai Madhukiran Kompalli; Akshdeep Singh Ahluwalia; Can Li<br>[返回论文条目](#entry-chen2025optichat) | 发表信息：2026 · INFORMS Journal on Data Science 5(3):199–220<br>论文版本：2501.08406v2<br>扩展了早期不可行诊断研究；期刊版发表于 2026 年。 |
| <a id="paper-dslmilp2026"></a>**OptiDSL**<br>Shaofeng Zhang; Hongyuan Su; Qingwen Peng; Zefang Zong; Shengcai Liu; Ke Tang; Yong Li<br>[返回论文条目](#entry-dslmilp2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2608.07040v1<br>同时提出方法与新基准；跨范式执行与跨求解器等价性证明分开。 |
| <a id="paper-optiloop2026"></a>**OptiLoop**<br>Yujia Xu; Zhiheng Wang; Thi Dinh<br>[返回论文条目](#entry-optiloop2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2605.27630v1<br>这是有限场景、有限轮协调的行为检查；不能将局部通过或匹配目标值写成任意协同问题的形式化保证。 |
| <a id="paper-optirepair2026"></a>**OptiRepair**<br>Ruicheng Ao; David Simchi-Levi; Xinshang Wang<br>[返回论文条目](#entry-optirepair2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2602.19439v2 |
| <a id="paper-optiverse2026"></a>**OptiVerse / DVA-Agent**<br>Xinyu Zhang; Boxuan Zhang; Yuchen Wan; Lingling Zhang; YiXing Yao; Bifan Wei; Yaqiang Wu; Jun Liu<br>[返回论文条目](#entry-optiverse2026) | 发表信息：2026 · Findings of ACL 2026<br>论文版本：2604.21510v1<br>OptiVerse: A Comprehensive Benchmark towards Optimization Problem Solving <span title="arXiv">[![arXiv][badge-002]][resource-240]</span>：预印本版本；作者：Xinyu Zhang; Boxuan Zhang; Yuchen Wan; Lingling Zhang; YiXing Yao; Bifan Wei; Yaqiang Wu; Jun Liu<br>DVA-Agent 基于抽取与交叉比对；推理、审核和评分脚本位于 evaluation/。 |
| <a id="paper-yang2026optskills"></a>**OptSkills**<br>Haochen Yang; Ke Zhao; Mengyuan Ma; Xingyu Lu; Xiangfeng Wang; Hong Qian<br>[返回论文条目](#entry-yang2026optskills) | 发表信息：2026 · Findings of EMNLP 2026<br>论文版本：arXiv:2605.29829v2<br>正式版本已收入 Findings of EMNLP 2026；方法与技能库说明依据所列预印本版本。 |
| <a id="paper-wang2026orprm"></a>**OR-PRM**<br>Yilin Wang; Heng Zhou; Dongxing Mao; Linjie Li; Jingru Tan; Haochen Han; Zhengyuan Yang; Alex Jinpeng Wang; Min Li<br>[返回论文条目](#entry-wang2026orprm) | 发表信息：2026 · ICLR 2026<br>OR-PRM 基于 Qwen2.5-7B-Coder，经 SFT 与 DPO 训练；Qwen3-8B 用于数据验证。OR-ProcessQA 为配套过程数据。 |
| <a id="paper-ding2026orr1"></a>**OR-R1**<br>Zezhen Ding; Zhen Tan; Jiheng Zhang; Tianlong Chen<br>[返回论文条目](#entry-ding2026orr1) | 发表信息：2026 · AAAI 2026<br>论文版本：2511.09092v1<br>OR-R1: Automating Modeling and Solving of Operations Research Optimization Problem via Test-Time Reinforcement Learning <span title="arXiv">[![arXiv][badge-002]][resource-041]</span>：预印本版本；作者：Zezhen Ding; Zhen Tan; Jiheng Zhang; Tianlong Chen<br>仓库提供 SFT、GRPO、LoRA 合并与评测代码。 |
| <a id="paper-zhou2026orspace"></a>**OR-Space**<br>Chenyu Zhou; Xinyun Lu; Jiangyue Zhao; Jianghao Lin; Dongdong Ge; Yinyu Ye<br>[返回论文条目](#entry-zhou2026orspace) | 发表信息：2026 · arXiv preprint<br>论文版本：2605.28158v1 |
| <a id="paper-oragentbench2026"></a>**ORAgentBench**<br>Jiajun Li; Mingshu Cai; Yixuan Li; Yu Ding; Ran Hou; Guanyu Nie; Xiongwei Han; Wanyuan Wang<br>[返回论文条目](#entry-oragentbench2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2606.19787v1 |
| <a id="paper-ao2026orloopbench"></a>**ORLoopBench**<br>Ruicheng Ao; David Simchi-Levi; Xinshang Wang<br>[返回论文条目](#entry-ao2026orloopbench) | 发表信息：2026 · ICML 2026<br>论文版本：2601.21008v3<br>ORDebug / ORBias 提供数据及校验脚本；发布 schema 与原文生成布局存在差异。 |
| <a id="paper-yang2025orthought"></a>**ORThought / LogiOR**<br>Beinuo Yang; Qishen Zhou; Junyi Li; Chenxing Su; Panagiotis Angeloudis; Simon Hu<br>[返回论文条目](#entry-yang2025orthought) | 发表信息：2026 · Artificial Intelligence for Transportation 6（2026）<br>论文版本：arXiv:2508.14410v3<br>ORThought: Benchmarking and Automating Logistics Optimization Modeling <span title="arXiv v3">[![arXiv v3][badge-125]][resource-564]</span>：2025；Preprint, v3 revised 2026-04-18；v3, 2026-04-18；更早版本题为 Automated Optimization Modeling through Expert-Guided Large Language Model Reasoning。；作者：Beinuo Yang; Qishen Zhou; Junyi Li; Chenxing Su; Panagiotis Angeloudis; Simon Hu<br>arXiv v3：arXiv v3。 |
| <a id="paper-yan2026pall"></a>**PALL**<br>An Yan; Huigen Ye; Hua Xu; Jiahao Zhang<br>[返回论文条目](#entry-yan2026pall) | 发表信息：2026 · NeurIPS 2026（已接收，待出版） |
| <a id="paper-pathwise2026"></a>**PathWise**<br>Oguzhan Gungordu; Siheng Xiong; Faramarz Fekri<br>[返回论文条目](#entry-pathwise2026) | 发表信息：2026 · ICML 2026 · PMLR 306<br>论文版本：2601.20539v3<br>PathWise: Planning through World Model for Automated Heuristic Design via Self-Evolving LLMs <span title="arXiv">[![arXiv][badge-002]][resource-342]</span>：预印本版本；作者：Oguzhan Gungordu; Siheng Xiong; Faramarz Fekri<br>self-evolving 指搜索状态、动作和程序演化；未据此推断更新 LLM 权重。 |
| <a id="paper-lu2026pearl"></a>**PEARL**<br>Hongliang Lu; Zhong Li; Yuxuan Chen; Yuan Lan; Fan Zhang; Zaiwen Wen<br>[返回论文条目](#entry-lu2026pearl) | 发表信息：2026 · NeurIPS 2026（已接收，待出版） |
| <a id="paper-jiang2026poweratlas"></a>**PowerAtlas / ECBench**<br>Kaiwen Jiang; Siya Xu; Ziyue Zhu; Kaiwen Xue; Chao Yang; Anh Tuan Luu; Haoran Luo<br>[返回论文条目](#entry-jiang2026poweratlas) | 发表信息：2026 · arXiv preprint<br>论文版本：2607.26710v2<br>PowerAtlas: Towards Electricity-Computing Co-Scheduling for Power Systems <span title="arXiv">[![arXiv][badge-002]][resource-270]</span>：早期题名<br>当前题名为 Feasibility-Aware Language Models for Electricity-Computing Co-Scheduling。论文报告仍有残留供给缺口；仓库提供生成器、样例及训练 / 评测代码。 |
| <a id="paper-shen2026proopf"></a>**ProOPF**<br>Chao Shen; Zihan Guo; Xu Wan; Zhenghao Yang; Yifan Zhang; Wenqi Huang; Jie Song; Zongyan Zhang; Mingyang Sun<br>[返回论文条目](#entry-shen2026proopf) | 发表信息：2026 · ICML 2026<br>论文版本：2602.03070v5<br>ProOPF_D 提供 few-shot 训练示例。 |
| <a id="paper-pyvrpplus2026"></a>**PyVRP+ / MEP**<br>Manuj Malik; Jianan Zhou; Shashank Reddy Chirra; Zhiguang Cao<br>[返回论文条目](#entry-pyvrpplus2026) | 发表信息：2026 · AAMAS 2026<br>论文版本：2604.07872v1<br>PyVRP$^+$: LLM-Driven Metacognitive Heuristic Evolution for Hybrid Genetic Search in Vehicle Routing Problems <span title="arXiv">[![arXiv][badge-002]][resource-400]</span>：预印本版本；作者：Manuj Malik; Jianan Zhou; Shashank Reddy Chirra; Zhiguang Cao<br>AAMAS 2026，起始页 2800。 |
| <a id="paper-roy2026rag"></a>**RAG for Optimization & CP Modeling**<br>Prateek Roy; Akash Singirikonda<br>[返回论文条目](#entry-roy2026rag) | 发表信息：2026 · arXiv preprint<br>论文版本：2608.00015v1<br>每组评测使用 25 个留出查询与一个基座模型；报告结果适用于该实验设定。 |
| <a id="paper-lian2026reloop"></a><a id="paper-liang2026reloop"></a>**ReLoop / RetailOpt-190**<br>Junbo Jacob Lian; Yujun Sun; Huiling Chen; Chaoyu Zhang; Hanzhang Qin; Chung-Piaw Teo<br>[返回论文条目](#entry-lian2026reloop) | 发表信息：2026 · NeurIPS 2026（已接收，待出版）<br>论文版本：2602.15983v6<br>RetailOpt-190 提供 HF 与 GitHub 数据。参数扰动提供行为诊断证据。 |
| <a id="paper-zhang2026retailbench"></a>**RetailBench**<br>Linghua Zhang; Jun Wang; Jingtong Wu; Zhisong Zhang<br>[返回论文条目](#entry-zhang2026retailbench) | 发表信息：2026 · arXiv preprint<br>论文版本：2603.16453v3<br>RetailBench: Benchmarking Long Horizon Reasoning and Coherent Decision Making of LLM Agents in Realistic Retail Environments <span title="arXiv">[![arXiv][badge-002]][resource-503]</span>：早期题名<br>论文评测周期与环境最大仿真时长不同。 |
| <a id="paper-rlvrpagents2026"></a>**RLEA**<br>Yi Chen; Zikang Yu; Jiahai Wang; Jinbiao Chen; Jianpeng Zhou; Zizhen Zhang<br>[返回论文条目](#entry-rlvrpagents2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2609.00859v1<br>Zenodo 提供论文附录。 |
| <a id="paper-ma2025sacopt"></a>**SAC-Opt**<br>Yansen Zhang; Qingcan Kang; Yujie Chen; Yufei Wang; Xiongwei Han; Tao Zhong; Mingxuan Yuan; Chen Ma<br>[返回论文条目](#entry-ma2025sacopt) | 发表信息：2026 · ICML 2026 · PMLR 306<br>论文版本：2510.05115v3 |
| <a id="paper-strategyaware2026"></a>**SAGE (Strategy-Aware Modeling)**<br>Ruiqing Zhao; Fengzhi Li; Yuan Zuo; Rui Liu; Yansong Liu; Yunfei Ma; Fanyu Meng; Junlan Feng<br>[返回论文条目](#entry-strategyaware2026) | 发表信息：2026 · ICML 2026 · PMLR 306<br>论文版本：2605.02545v1<br>Strategy-Aware Optimization Modeling with Reasoning LLMs <span title="arXiv">[![arXiv][badge-002]][resource-048]</span>：预印本版本；作者：Ruiqing Zhao; Fengzhi Li; Yuan Zuo; Rui Liu; Yansong Liu; Yunfei Ma; Fanyu Meng; Junlan Feng<br>与割不等式生成的 SAGE / 原 EvoCut 为不同论文，作者与资源分别列示。 |
| <a id="paper-sdrl2026"></a>**SDRL**<br>Shihao Zhang; Weiting Liu; Siyu Shao; Yitian Chen; Jianfeng Feng; Dongdong Ge; Yinyu Ye<br>[返回论文条目](#entry-sdrl2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2609.34427v1<br>GitHub 提供基准推理代码；HF 提供 SDRL-Qwen3-4B 的 safetensors 权重。 |
| <a id="paper-lange2026shinka"></a>**ShinkaEvolve**<br>Robert Lange; Yuki Imajuku; Edoardo Cetin<br>[返回论文条目](#entry-lange2026shinka) | 发表信息：2026 · ICLR 2026<br>论文版本：2509.19349v1<br>ShinkaEvolve: Towards Open-Ended And Sample-Efficient Program Evolution <span title="arXiv">[![arXiv][badge-002]][resource-345]</span>：预印本版本；作者：Robert Tjarko Lange; Yuki Imajuku; Edoardo Cetin<br>bandit 选择调用哪个 LLM，不等于训练了其权重；当前仓库功能包含论文后的扩展，不混用各版本实验描述。 |
| <a id="paper-smartgrid2026"></a>**Smart Grids Agentic AI Tutorial**<br>Daniela Rojas; Abdulwahab Albassam; Aidan G. Leung; Jett Ngo; Ryan Luo; Peter R. Quawas; Junpyung Kim; Kangkai Liang; Mansi Nanavati; Jonathan Mai; Meng-Chi Tsai; Yun-Tong Tsai; Yize Chen; Yuanyuan Shi<br>[返回论文条目](#entry-smartgrid2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2607.18147v1 |
| <a id="paper-li2025smilo"></a>**SMILO**<br>Qingyang Li; Lele Zhang; Vicky Mak-Hau<br>[返回论文条目](#entry-li2025smilo) | 发表信息：2026 · International Journal of Production Research（2026 在线）<br>论文版本：2511.02364v1<br>2026-05-03 在线发表。 |
| <a id="paper-solid2026"></a>**SOLID**<br>Rui Zhu; Minglong Cao; Chenyu Zhou; Jianghao Lin; Dongdong Ge<br>[返回论文条目](#entry-solid2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2609.09957v1<br>训练采用目标聚类形成的伪参考；Qwen3 与 StepORLM checkpoint 对应不同实验结果。 |
| <a id="paper-bhattacharyya2026sover"></a>**SOVER / NLEquiv-150**<br>Swapnil Bhattacharyya; Mayank Baranwal<br>[返回论文条目](#entry-bhattacharyya2026sover) | 发表信息：2026 · Findings of EMNLP 2026<br>论文版本：2609.00728v1<br>保证依赖解析、候选映射及编码假设；Z3 的线性／混整数核验与 dReal 的容差相关非线性核验分开。仓库的数值诊断模式不是 SMT 证明；不将公式间核验写成自然语言题意的完备正确性证明。<br>EquivaFormulation（使用）：论文使用的外部评测数据，不是 SOVER 的新发布。<br>NLP4LP（使用）：论文使用的外部评测数据，不是 SOVER 的新发布。 |
| <a id="paper-lai2026specahd"></a>**SpecAHD**<br>Kezhao Lai; Yutao Lai; Hai-Lin Liu<br>[返回论文条目](#entry-lai2026specahd) | 发表信息：2026 · arXiv preprint<br>论文版本：2607.23676v1<br>贪心近似保证适用于固定上层程序、修复任务与候选池下的库选择，而非整体路由解的全局近似比。 |
| <a id="paper-spo2026"></a>**SPO**<br>Xinyi Ke; Kai Li; Junliang Xing; Yifan Zhang; Jian Cheng<br>[返回论文条目](#entry-spo2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2609.31179v1<br>方法包含 LLM 参数更新。 |
| <a id="paper-zhou2026steporlm"></a>**StepORLM**<br>Chenyu Zhou; Tianyi Xu; Jianghao Lin; Dongdong Ge<br>[返回论文条目](#entry-zhou2026steporlm) | 发表信息：2026 · ICLR 2026 |
| <a id="paper-text2model2026"></a>**Text2Model**<br>Serdar Kadioglu; Karthik Uppuluri; Akash Singirikonda<br>[返回论文条目](#entry-text2model2026) | 发表信息：2026 · arXiv preprint<br>论文版本：2604.12955v3<br>复用 Text2Zinc 数据，提供建模 Copilot、编辑器与排行榜。 |
| <a id="paper-chen2026tide"></a>**TIDE**<br>Chentong Chen; Mengyuan Zhong; Ye Fan; Jialong Shi; Jianyong Sun<br>[返回论文条目](#entry-chen2026tide) | 发表信息：2026 · arXiv preprint<br>论文版本：2601.21239v2<br>tuning 指启发式数值参数优化。 |
| <a id="paper-verisimpl2026"></a>**VeriSimpl**<br>Sumaya Abdul Rahman; Seckhen Ariel Andrade Cuellar; Ghani Raissov; Mohammad Raza<br>[返回论文条目](#entry-verisimpl2026) | 发表信息：2026 · ICML 2026 · PMLR 306<br>论文版本：2607.20474v2<br>简化诊断用于模型自检。 |
| <a id="paper-vrpagent2025"></a>**VRPAgent**<br>André Hottung; Federico Berto; Chuanbo Hua; Nayeli Gast Zepeda; Daniel Wetzel; Michael Römer; Haoran Ye; Davide Zago; Michael Poli; Stefano Massaroli; Jinkyoo Park; Kevin Tierney<br>[返回论文条目](#entry-vrpagent2025) | 发表信息：2026 · Transactions on Machine Learning Research（2026）<br>论文版本：2510.07073v2<br>发表于 TMLR 2026 年 10 月；作者仓库提供生成的启发式与样例种群。<br>Generated Operators：生成的启发式与样例种群。 |

</details>

<details>
<summary>2025 · 作者与版本</summary>

| 论文与作者 | 版本与资源说明 |
|---|---|
| <a id="paper-zhao2025aimbench"></a>**AIM-Bench**<br>Xuhua Zhao; Yuxuan Xie; Caihua Chen; Yuxiang Sun<br>[返回论文条目](#entry-zhao2025aimbench) | 发表信息：2025 · arXiv preprint<br>论文版本：2508.11416v1 |
| <a id="paper-alas2025"></a>**ALAS**<br>Edward Y. Chang; Longling Geng<br>[返回论文条目](#entry-alas2025) | 发表信息：2025 · arXiv preprint<br>论文版本：2505.12501v1<br>ACID-like 是框架设计目标；其保证依赖具体框架设定。 |
| <a id="paper-novikov2025alphaevolve"></a>**AlphaEvolve**<br>Alexander Novikov; Ngân Vũ; Marvin Eisenberger; Emilien Dupont; Po-Sen Huang; Adam Zsolt Wagner; Sergey Shirobokov; Borislav Kozlovskii; Francisco J. R. Ruiz; Abbas Mehrabian; M. Pawan Kumar; Abigail See; Swarat Chaudhuri; George Holland; Alex Davies; Sebastian Nowozin; Pushmeet Kohli; Matej Balog<br>[返回论文条目](#entry-novikov2025alphaevolve) | 发表信息：2025 · Technical report<br>DeepMind 提供研究结果与问题集合。 |
| <a id="paper-kong2025alphaopt"></a>**AlphaOPT**<br>Minwei Kong; Ao Qu; Xiaotong Guo; Wenbin Ouyang; Chonghe Jiang; Han Zheng; Yining Ma; Dingyi Zhuang; Yuhan Tang; Junyi Li; Shenhao Wang; Haris Koutsopoulos; Hai Wang; Cathy Wu; Jinhua Zhao<br>[返回论文条目](#entry-kong2025alphaopt) | 发表信息：2025 · NeurIPS 2025 ScaleOpt Workshop / arXiv<br>论文版本：2510.18428v4 |
| <a id="paper-li2025ars"></a>**ARS / RoutBench**<br>Kai Li; Fei Liu; Zhenkun Wang; Xialiang Tong; Xiongwei Han; Mingxuan Yuan; Qingfu Zhang<br>[返回论文条目](#entry-li2025ars) | 发表信息：2025 · arXiv preprint |
| <a id="paper-askclarify2026"></a>**Ask, Clarify, Optimize**<br>Yaqi Duan; Yichun Hu; Jiashuo Jiang<br>[返回论文条目](#entry-askclarify2026) | 发表信息：2025 · arXiv preprint<br>论文版本：2601.00121v1 |
| <a id="paper-astorga2025autoformulation"></a>**Autoformulation**<br>Nicolás Astorga; Tennison Liu; Yuanzhang Xiao; Mihaela Van Der Schaar<br>[返回论文条目](#entry-astorga2025autoformulation) | 发表信息：2025 · ICML 2025 |
| <a id="paper-sim2025beyondhype"></a>**Beyond the Hype: Bin Packing**<br>Kevin Sim; Quentin Renau; Emma Hart<br>[返回论文条目](#entry-sim2025beyondhype) | 发表信息：2025 · EvoApplications 2025 · LNCS<br>论文版本：2501.11411v1 |
| <a id="paper-vanstein2025blade"></a>**BLADE**<br>Niki van Stein; Anna V. Kononova; Haoran Yin; Thomas Bäck<br>[返回论文条目](#entry-vanstein2025blade) | 发表信息：2025 · GECCO 2025 Workshop / Companion<br>论文版本：2504.20183v1<br>正式发表于 GECCO 2025 Workshop / Companion。 |
| <a id="paper-wang2025bppsearch"></a>**BPP-Search / StructuredOR**<br>Teng Wang; Wing Yin Yu; Zhenqi He; Zehua Liu; Hailei Gong; Han Wu; Xiongwei Han; Wei Shi; Ruifeng She; Fangzhou Zhu; Tao Zhong<br>[返回论文条目](#entry-wang2025bppsearch) | 发表信息：2025 · ACL 2025, Volume 1: Long Papers, pp. 821–838 |
| <a id="paper-kaleta2025cdss"></a>**C-DSS**<br>Mariusz Kaleta<br>[返回论文条目](#entry-kaleta2025cdss) | 发表信息：2025 · FedCSIS 2025 · ACSIS 43<br>实证范围集中于建模与编码。 |
| <a id="paper-calm2025storm"></a>**CALM / STORM**<br>Zhengyang Tang; Zihan Ye; Chenyu Huang; Xuhan Huang; Chengpeng Li; Sihang Li; Guanhua Chen; Ming Yan; Zizhuo Wang; Hongyuan Zha; Dayiheng Liu; Benyou Wang<br>[返回论文条目](#entry-calm2025storm) | 发表信息：2025 · arXiv preprint<br>论文版本：2510.04204v1<br>与算法共同演化的 CALM 为两项独立工作。 |
| <a id="paper-bomer2025emerging"></a>**CEoH**<br>Thomas Bömer; Nico Koltermann; Max Disselnmeyer; Laura Dörr; Anne Meyer<br>[返回论文条目](#entry-bomer2025emerging) | 发表信息：2025 · arXiv preprint<br>论文版本：2503.03350v1<br>预印本注记为 LION19 在审。 |
| <a id="paper-lawless2024cuts"></a>**Cold-Start Separator Configuration**<br>Connor Lawless; Yingxi Li; Anders Wikum; Madeleine Udell; Ellen Vitercik<br>[返回论文条目](#entry-lawless2024cuts) | 发表信息：2025 · CPAIOR 2025<br>论文版本：2412.12038v2<br>CPAIOR 2025，pp. 51–69。 |
| <a id="paper-peering2025"></a>**Component-Level Evaluation**<br>Dania Refai; Moataz Ahmed<br>[返回论文条目](#entry-peering2025) | 发表信息：2025 · arXiv preprint<br>论文版本：2510.16943v1 |
| <a id="paper-michailidis2025cpbench"></a>**CP-Bench / DCP-Bench-Open**<br>Kostis Michailidis; Dimos Tsouros; Tias Guns<br>[返回论文条目](#entry-michailidis2025cpbench) | 发表信息：2025 · ECAI 2025<br>论文版本：2506.06052v2<br>CP-Bench: Evaluating Large Language Models for Constraint Modelling <span title="arXiv">[![arXiv][badge-002]][resource-472]</span>：ECAI 2025<br>DCP-Bench-Open: Evaluating LLMs for Constraint Modelling of Discrete Combinatorial Problems <span title="Related version">[![Related version][badge-095]][resource-473]</span>：under review<br>CP-Bench 为 ECAI 2025 原版，DCP-Bench-Open 为扩展版；原版数据已归档。 |
| <a id="paper-daopt2025"></a>**DAOpt / OptU**<br>WenZhuo Zhu; Zheng Cui; Wenhan Lu; Sheng Liu; Yue Zhao<br>[返回论文条目](#entry-daopt2025) | 发表信息：2025 · arXiv preprint<br>论文版本：2511.11576v1 |
| <a id="paper-dheevo2025"></a>**DHEvo**<br>Zhihao Zhang; Siyuan Li; Chenxi Li; Feifan Liu; Mengjing Chen; Kai Li; Tao Zhong; Bo An; Peng Liu<br>[返回论文条目](#entry-dheevo2025) | 发表信息：2025 · arXiv preprint<br>论文版本：2507.15615v1<br>数据—算法共同演化用于启发式发现，不据此推断进行了 LLM 权重训练或发布了新基准。 |
| <a id="paper-dinn2025"></a>**DINN**<br>Yoontae Hwang; Yaxuan Kong; Stefan Zohren; Yongjae Lee<br>[返回论文条目](#entry-dinn2025) | 发表信息：2025 · arXiv preprint / submitted paper<br>论文版本：2502.00828v1<br>作者仓库提供 PyTorch 实现；实验数据通过 WRDS 账号取得。<br>资源：PyTorch 实现。 |
| <a id="paper-wasserkrug2024manifesto"></a><a id="paper-wasserkrug2025aaai"></a>**DOCP Research Manifesto**<br>Segev Wasserkrug; Leonard Boussioux; Dick Den Hertog; Farzaneh Mirzazadeh; Ş. İlker Birbil; Jannis Kurtz; Donato Maragno<br>[返回论文条目](#entry-wasserkrug2024manifesto) | 发表信息：2025 · AAAI 2025<br>论文版本：2402.16269v1<br>From Large Language Models and Optimization to Decision Optimization CoPilot: A Research Manifesto <span title="arXiv">[![arXiv][badge-002]][resource-014]</span>：2024 年早期版本<br>Enhancing Decision Making Through the Integration of Large Language Models and Operations Research Optimization <span title="Proceedings">[![Proceedings][badge-005]][resource-013]</span>：AAAI 2025 正式版<br>2024 Manifesto 为 AAAI 2025 论文的早期版本。 |
| <a id="paper-dpdlm2025"></a>**DPLM / DP-Bench**<br>Chenyu Zhou; Jingyuan Yang; Linwei Xin; Yitian Chen; Ziyan He; Dongdong Ge<br>[返回论文条目](#entry-dpdlm2025) | 发表信息：2025 · arXiv preprint<br>论文版本：2507.11737v2 |
| <a id="paper-jiang2025droc"></a>**DRoC**<br>Xia Jiang; Yaoxin Wu; Chenhao Zhang; Yingqian Zhang<br>[返回论文条目](#entry-jiang2025droc) | 发表信息：2025 · ICLR 2025 |
| <a id="paper-viktorin2025ease"></a>**EASE**<br>Adam Viktorin; Tomas Kadavy; Jozef Kovac; Michal Pluhacek; Roman Senkerik<br>[返回论文条目](#entry-viktorin2025ease) | 发表信息：2025 · arXiv preprint<br>论文版本：2509.18108v1<br>框架支持算法以外的生成任务，按邻近平台展示；未将其误标新 OR 基准或训练模型。 |
| <a id="paper-luo2025efs"></a>**EFS**<br>Jiandong Chen; Haochen Luo; Yuan Zhang; Chen Liu; Qingfu Zhang<br>[返回论文条目](#entry-luo2025efs) | 发表信息：2025 · arXiv preprint<br>论文版本：2507.17211v2 |
| <a id="paper-zhou2024elecbench"></a>**ElecBench**<br>Xiyuan Zhou; Huan Zhao; Yuheng Cheng; Gaoqi Liang; Guolong Liu; Wenxuan Liu; Yan Xu; Junhua Zhao<br>[返回论文条目](#entry-zhou2024elecbench) | 发表信息：2025 · IEEE PESGM 2025<br>论文版本：2407.05365v2<br>ElecBench: a Power Dispatch Evaluation Benchmark for Large Language Models <span title="arXiv">[![arXiv][badge-002]][resource-549]</span>：预印本版本；作者：Xiyuan Zhou; Huan Zhao; Yuheng Cheng; Yuji Cao; Gaoqi Liang; Guolong Liu; Wenxuan Liu; Yan Xu; Junhua Zhao<br>仓库提供测试子集；PESGM 2025 与预印本的题名和作者不同。 |
| <a id="paper-zhang2025decisioninfo"></a>**EOR / Decision Information**<br>Yansen Zhang; Qingcan Kang; Wing Yin Yu; Hailei Gong; Xiaojin Fu; Xiongwei Han; Tao Zhong; Chen Ma<br>[返回论文条目](#entry-zhang2025decisioninfo) | 发表信息：2025 · ICLR 2025<br>论文版本：2502.09994v1 |
| <a id="paper-zhai2025equivamap"></a>**EquivaMap**<br>Haotian Zhai; Connor Lawless; Ellen Vitercik; Liu Leqi<br>[返回论文条目](#entry-zhai2025equivamap) | 发表信息：2025 · ICML 2025 |
| <a id="paper-ucfunsearch2025"></a>**FunSearch for Unit Commitment**<br>Junjin Lv; Chenggang Cui; Shaodi Zhang; Hui Chen; Chunyang Gong; Jiaming Liu<br>[返回论文条目](#entry-ucfunsearch2025) | 发表信息：2025 · arXiv preprint<br>论文版本：2506.12495v1 |
| <a id="paper-globalconstraint2025"></a>**Gala**<br>Junyang Cai; Serdar Kadioglu; Bistra Dilkina<br>[返回论文条目](#entry-globalconstraint2025) | 发表信息：2025 · arXiv preprint<br>论文版本：2509.08970v2<br>实现位于 Text2Model 的 gala 策略。 |
| <a id="paper-yang2025heuragenix"></a>**HeurAgenix**<br>Xianliang Yang; Ling Zhang; Haolong Qian; Lei Song; Jiang Bian<br>[返回论文条目](#entry-yang2025heuragenix) | 发表信息：2025 · arXiv preprint<br>论文版本：2506.15196v2<br>实例集汇集了既有 CO 数据。 |
| <a id="paper-dat2024hsevo"></a>**HSEvo**<br>Pham Vu Tuan Dat; Long Doan; Huynh Thi Thanh Binh<br>[返回论文条目](#entry-dat2024hsevo) | 发表信息：2025 · AAAI 2025<br>论文版本：2412.14995v1<br>HSEvo: Elevating Automatic Heuristic Design with Diversity-Driven Harmony Search and Genetic Algorithm Using LLMs <span title="arXiv">[![arXiv][badge-002]][resource-361]</span>：预印本版本；作者：Pham Vu Tuan Dat; Long Doan; Huynh Thi Thanh Binh |
| <a id="paper-zhang2025instspechh"></a>**InstSpecHH**<br>Shaofeng Zhang; Shengcai Liu; Ning Lu; Jiahao Wu; Ji Liu; Yew-Soon Ong; Ke Tang<br>[返回论文条目](#entry-zhang2025instspechh) | 发表信息：2025 · arXiv preprint<br>论文版本：2506.00490v3<br>可选神经分类器用于算法选择，其训练与 LLM SFT 分开。 |
| <a id="paper-xie2025llmns"></a>**LHNS**<br>Zhuoliang Xie; Fei Liu; Zhenkun Wang; Qingfu Zhang<br>[返回论文条目](#entry-xie2025llmns) | 发表信息：2025 · IEEE CEC 2025<br>搜索对象是启发式程序。 |
| <a id="paper-vanstein2024llamea"></a>**LLaMEA**<br>Niki van Stein; Thomas Bäck<br>[返回论文条目](#entry-vanstein2024llamea) | 发表信息：2025 · IEEE TEVC 29(2):331–345<br>2024 年在线发表，卷期版为 2025 年。 |
| <a id="paper-liu2025fitness"></a>**LLM Algorithm-search Fitness Landscapes**<br>Fei Liu; Qingfu Zhang; Jialong Shi; Xialiang Tong; Kun Mao; Mingxuan Yuan<br>[返回论文条目](#entry-liu2025fitness) | 发表信息：2025 · arXiv preprint<br>论文版本：2504.19636v3 |
| <a id="paper-vanstein2025behaviour"></a>**LLM Heuristic Behaviour-space Analysis**<br>Niki van Stein; Haoran Yin; Anna V. Kononova; Thomas Bäck; Gabriela Ochoa<br>[返回论文条目](#entry-vanstein2025behaviour) | 发表信息：2025 · arXiv preprint<br>论文版本：2507.03605v1<br>Zenodo 提供 behaviour_metrics.py 行为指标代码。 |
| <a id="paper-cetinkaya2025mipsmtt"></a>**LLM-discovered EDDC / MDDC**<br>İbrahim Oğuz Çetinkaya; İ. Esra Büyüktahtakın; Parshin Shojaee; Chandan K. Reddy<br>[返回论文条目](#entry-cetinkaya2025mipsmtt) | 发表信息：2025 · arXiv preprint<br>论文版本：2510.24013v1 |
| <a id="paper-ye2025llmlns"></a>**LLM-LNS**<br>Huigen Ye; Hua Xu; An Yan; Yaoyang Cheng<br>[返回论文条目](#entry-ye2025llmlns) | 发表信息：2025 · ICML 2025 |
| <a id="paper-llmsuc2025"></a>**LLM-SUC**<br>Xinxing Ren; Chun Sing Lai; Gareth Taylor; Zekun Guo<br>[返回论文条目](#entry-llmsuc2025) | 发表信息：2025 · arXiv preprint<br>论文版本：2502.10557v2<br>不同版本的成本与削负荷统计存在差异。 |
| <a id="paper-xiao2025survey"></a>**LLM4OR Survey**<br>Ziyang Xiao; Jingrong Xie; Lilin Xu; Shisi Guan; Jingyan Zhu; Xiongwei Han; Xiaojin Fu; WingYin Yu; Han Wu; Wei Shi; Qingcan Kang; Jiahui Duan; Tao Zhong; Mingxuan Yuan; Jia Zeng; Yuan Wang; Gang Chen; Dongxiang Zhang<br>[返回论文条目](#entry-xiao2025survey) | 发表信息：2025 · IJCAI 2025 Survey Track<br>配套目录提供 ComplexOR、IndustryOR、Mamo、NL4LP、NL4Opt、ReSocratic 的清洗或错误标注材料。属于既有基准的修订评测资源，不作为这些基准的首次提出。<br>Cleaned Benchmarks：既有基准的错误标注 / 清洗材料，含 ComplexOR、IndustryOR、Mamo、NL4LP、NL4Opt、ReSocratic；不是这些原始基准的首次发布。 |
| <a id="paper-jiang2025e2eco"></a>**LLMCoSolver / E2E CO Solver**<br>Xia Jiang; Yaoxin Wu; Minshuo Li; Zhiguang Cao; Yingqian Zhang<br>[返回论文条目](#entry-jiang2025e2eco) | 发表信息：2025 · NeurIPS 2025<br>论文版本：2509.16865v1<br>Large Language Models as End-to-end Combinatorial Optimization Solvers <span title="arXiv">[![arXiv][badge-002]][resource-273]</span>：预印本版本；作者：Xia Jiang; Yaoxin Wu; Minshuo Li; Zhiguang Cao; Yingqian Zhang<br>提供代码和 Google Drive 上的 SFT / RL 数据。 |
| <a id="paper-jiang2025llmopt"></a>**LLMOPT**<br>caigao jiang; Xiang Shu; Hong Qian; Xingyu Lu; JUN ZHOU; Aimin Zhou; Yang Yu<br>[返回论文条目](#entry-jiang2025llmopt) | 发表信息：2025 · ICLR 2025<br>公开模型采用 Qwen2.5-14B；原论文的训练基座包含 Qwen1.5。 |
| <a id="paper-dsmco2024"></a>**LLMs for DSM Sequencing**<br>Shuo Jiang; Min Xie; Jianxi Luo<br>[返回论文条目](#entry-dsmco2024) | 发表信息：2025 · Proceedings of the Design Society 5 · ICED25（2025）<br>论文版本：2411.12571v1<br>Large Language Models for Combinatorial Optimization of Design Structure Matrix <span title="arXiv">[![arXiv][badge-002]][resource-278]</span>：预印本版本；作者：Shuo Jiang; Min Xie; Jianxi Luo |
| <a id="paper-talebi2025stochastic"></a>**LLMs for Stochastic Modeling**<br>Amirreza Talebi<br>[返回论文条目](#entry-talebi2025stochastic) | 发表信息：2025 · arXiv preprint<br>论文版本：2508.17200v3<br>评测案例包含文献改编。 |
| <a id="paper-wang2025lor"></a>**LLMs in OR: Methods & Challenges**<br>Yang Wang; Kai Li<br>[返回论文条目](#entry-wang2025lor) | 发表信息：2025 · arXiv preprint<br>论文版本：2509.18180v3 |
| <a id="paper-llmbl2025"></a>**LLM–Black-Litterman**<br>Youngbin Lee; Yejin Kim; Juhyeong Kim; Suin Kim; Yongjae Lee<br>[返回论文条目](#entry-llmbl2025) | 发表信息：2025 · CIKM 2025 Financial AI Workshop<br>论文版本：2504.14345v2 |
| <a id="paper-yuan2025magts"></a>**MA-GTS / G-REAL**<br>Zike Yuan; Ming Liu; Hui Wang; Bing Qin<br>[返回论文条目](#entry-yuan2025magts) | 发表信息：2025 · EMNLP 2025 Main, pp. 19286–19304<br>arXiv v2 与会议摘要的 G-REAL 数字不同，不混用性能数字。 |
| <a id="paper-huang2024mamo"></a>**Mamo**<br>Xuhan Huang; Qingning Shen; Yan Hu; Anningzhe Gao; Benyou Wang<br>[返回论文条目](#entry-huang2024mamo) | 发表信息：2025 · Findings NAACL 2025<br>Dataset（第三方镜像）：Mamo EasyLP / ComplexLP 的第三方镜像，调整了字段名。 |
| <a id="paper-zheng2025mctsahd"></a>**MCTS-AHD**<br>Zhi Zheng; Zhuoliang Xie; Zhenkun Wang; Bryan Hooi<br>[返回论文条目](#entry-zheng2025mctsahd) | 发表信息：2025 · ICML 2025 |
| <a id="paper-yao2025meoh"></a>**MEoH**<br>Shunyu Yao; Fei Liu; Xi Lin; Zhichao Lu; Zhenkun Wang; Qingfu Zhang<br>[返回论文条目](#entry-yao2025meoh) | 发表信息：2025 · AAAI 2025<br>论文版本：2409.16867v2<br>Multi-objective Evolution of Heuristic Using Large Language Model <span title="arXiv">[![arXiv][badge-002]][resource-375]</span>：预印本版本；作者：Shunyu Yao; Fei Liu; Xi Lin; Zhichao Lu; Zhenkun Wang; Qingfu Zhang<br>LLM4AD 的 meoh 模块明确引用本论文；它是共享平台内的具体实现，不是本论文新建的独立平台。 |
| <a id="paper-li2025milpevolve"></a>**MILP-Evolve**<br>Sirui Li; Janardhan Kulkarni; Ishai Menache; Cathy Wu; Beibin Li<br>[返回论文条目](#entry-li2025milpevolve) | 发表信息：2025 · ICLR 2025<br>代码在 microsoft/OptiGuide 的 milp-evolve 子目录；microsoft/MILP-Evolve 是独立数据卡仓库，未将其当作完整算法实现。 |
| <a id="paper-liu2025mmagent"></a>**MM-Agent / MM-Bench（数学建模）**<br>Fan LIU; Zherui Yang; Cancheng Liu; Tianrui Song; Xiaofeng Gao; Hao Liu<br>[返回论文条目](#entry-liu2025mmagent) | 发表信息：2025 · NeurIPS 2025<br>论文版本：2505.14148v1<br>MM-Agent: LLM as Agents for Real-world Mathematical Modeling Problem <span title="arXiv">[![arXiv][badge-002]][resource-539]</span>：预印本版本；作者：Fan Liu; Zherui Yang; Cancheng Liu; Tianrui Song; Xiaofeng Gao; Hao Liu<br>属于广义数学建模，与多模态同名 MM-Bench 区分。比赛奖项对应辅助学生团队；Expert Skills 为 2026 年版本，论文实验采用 2025 年版本。 |
| <a id="paper-qian2025modelingagent"></a>**ModelingAgent / ModelingBench**<br>Cheng Qian; Hongyi Du; Hongru Wang; Xiusi Chen; Yuji Zhang; Avirup Sil; ChengXiang Zhai; Kathleen McKeown; Heng Ji<br>[返回论文条目](#entry-qian2025modelingagent) | 发表信息：2025 · Findings of EMNLP 2025<br>论文版本：2505.15068v1<br>ModelingAgent: Bridging LLMs and Mathematical Modeling for Real-World Challenges <span title="arXiv">[![arXiv][badge-002]][resource-545]</span>：预印本版本；作者：Cheng Qian; Hongyi Du; Hongru Wang; Xiusi Chen; Yuji Zhang; Avirup Sil; Chengxiang Zhai; Kathleen McKeown; Heng Ji<br>范围含数据分析、预测、跨学科建模及报告，不等同纯运筹优化基准。评分包含 LLM 评审，与求解器目标值／可行性检测口径不同。 |
| <a id="paper-moid2025"></a>**MOID**<br>Kai Li; Ruihao Zheng; Xinye Hao; Zhenkun Wang<br>[返回论文条目](#entry-moid2025) | 发表信息：2025 · arXiv preprint<br>论文版本：2508.03406v1<br>正文给出的仓库当前仅含 50 VRP&100 solution.json 与极简 README，按诊断数据展示，不标完整求解与诊断实现。 |
| <a id="paper-xie2025murka"></a>**MURKA**<br>Wantong Xie; Yi-Xiang Hu; Jieyang Xu; Feng Wu; Xiangyang Li<br>[返回论文条目](#entry-xie2025murka) | 发表信息：2025 · NeurIPS 2025 Main Conference Track, volume 38 |
| <a id="paper-tran2025llmneural"></a>**NCO-LLM for VRP**<br>Cong Dao Tran; Quan Nguyen-Tri; Huynh Thi Thanh Binh; Hoang Thanh-Tung<br>[返回论文条目](#entry-tran2025llmneural) | 发表信息：2025 · ICLR 2025 Agentic AI Workshop<br>发表于 ICLR 2025 Towards Agentic AI for Science Workshop；仓库提供代码，微调对象为 NCO 路由策略。 |
| <a id="paper-thind2025optimai"></a>**OptimAI**<br>Raghav Thind; Youran Sun; Ling Liang; Haizhao Yang<br>[返回论文条目](#entry-thind2025optimai) | 发表信息：2025 · arXiv preprint<br>论文版本：2504.16918v3 |
| <a id="paper-zhang2025optimind"></a><a id="paper-chen2025optimind"></a>**OptiMind**<br>Xinzhi Zhang; Zeyi Chen; Humishka Zope; Hugo Barbalho; Konstantina Mellou; Marco Molinaro; Janardhan Kulkarni; Ishai Menache; Sirui Li<br>[返回论文条目](#entry-zhang2025optimind) | 发表信息：2025 · arXiv preprint |
| <a id="paper-liu2025optitree"></a>**OptiTree**<br>Haoyang Liu; Jie Wang; Yuyang Cai; Xiongwei Han; Yufei Kuang; Jianye Hao<br>[返回论文条目](#entry-liu2025optitree) | 发表信息：2025 · NeurIPS 2025 |
| <a id="paper-lima2025optitrust"></a>**OptiTrust**<br>Vinicius Lima; Dzung T. Phan; Jayant Kalagnanam; Dhaval Patel; Nianjun Zhou<br>[返回论文条目](#entry-lima2025optitrust) | 发表信息：2025 · arXiv preprint<br>论文版本：2508.03117v1 |
| <a id="paper-lu2025optmath"></a>**OptMATH**<br>Hongliang Lu; Zhonglin Xie; Yaoyu Wu; Can Ren; Yuxuan Chen; Zaiwen Wen<br>[返回论文条目](#entry-lu2025optmath) | 发表信息：2025 · ICML 2025; PMLR 267:40769–40802 |
| <a id="paper-zhang2025bwor"></a>**OR-LLM-Agent / BWOR**<br>Bowen Zhang; Pengcheng Luo; Genke Yang; Boon-Hee Soong; Chau Yuen<br>[返回论文条目](#entry-zhang2025bwor) | 发表信息：2025 · arXiv preprint<br>论文版本：2503.10009v3 |
| <a id="paper-ding2026orgeval"></a>**ORGEval / Bench4Opt**<br>Zhuohan Wang; Ziwei Zhu; Ziniu Li; Congliang Chen; Yizhou Han; Yufeng Lin; Zhihang Lin; Angyang Gu; Xinglin Hu; Ruoyu Sun; Tian Ding<br>[返回论文条目](#entry-ding2026orgeval) | 发表信息：2025 · arXiv；相关 ICML 2026 Workshop 版本<br>ORGEval: Graph-Theoretic Evaluation of LLMs in Optimization Modeling <span title="arXiv">[![arXiv][badge-002]][resource-257]</span>：2025<br>Certified Evaluation for LLMs in Optimization Modeling: From Graph Isomorphism to Formulation Isomorphism <span title="ICML workshop poster（相关）">[![ICML workshop poster（相关）][badge-065]][resource-258]</span>：2026；Poster in Workshop: Combining Theory and Benchmarks；题名和作者不同，均包含 ORGEval 与 Bench4Opt。<br>arXiv 首发于 2025 年，会议版本为 ICML 2026 Workshop Poster。 |
| <a id="paper-huang2025orlm"></a>**ORLM**<br>Chenyu Huang; Zhengyang Tang; Shixi Hu; Ruoqing Jiang; Xin Zheng; Dongdong Ge; Benyou Wang; Zizhuo Wang<br>[返回论文条目](#entry-huang2025orlm) | 发表信息：2025 · Operations Research 73(6):2986–3009 |
| <a id="paper-ormind2025"></a>**ORMind**<br>Zhiyuan Wang; Bokui Chen; Yinya Huang; Qingxing Cao; Ming He; Jianping Fan; Xiaodan Liang<br>[返回论文条目](#entry-ormind2025) | 发表信息：2025 · ACL 2025 Industry Track<br>论文版本：2506.01326v2 |
| <a id="paper-mostajabdaveh2025orqa"></a>**ORQA**<br>Mahdi Mostajabdaveh; Timothy T. Yu; Samarendra Chandan Bindu Dash; Rindranirina Ramamonjison; Jabo Serge Byusa; Giuseppe Carenini; Zirui Zhou; Yong Zhang<br>[返回论文条目](#entry-mostajabdaveh2025orqa) | 发表信息：2025 · AAAI 2025 |
| <a id="paper-ali2025pair"></a>**PAIR**<br>Shady Ali; Mahmoud Ashraf; Seif Hegazy; Fatty Salem; Hoda Mokhtar; Mohamed Medhat Gaber; Mohamed Taher Alrefaie<br>[返回论文条目](#entry-ali2025pair) | 发表信息：2025 · arXiv preprint |
| <a id="paper-quan2025reeval3d"></a>**Re-evaluating Heuristic Search: 3D Packing**<br>Guorui Quan; Mingfei Sun; Manuel López-Ibáñez<br>[返回论文条目](#entry-quan2025reeval3d) | 发表信息：2025 · arXiv preprint<br>论文版本：2509.02297v1 |
| <a id="paper-thach2025redahd"></a>**RedAHD**<br>Nguyen Thach; Aida Riahifar; Nathan Huynh; Hau Chan<br>[返回论文条目](#entry-thach2025redahd) | 发表信息：2025 · arXiv preprint<br>论文版本：2505.20242v1<br>归约的经验检验不等于所有生成变换均有正确性证明；正文引用的 ReEvo / MCTS-AHD 不作为本工作实现。 |
| <a id="paper-cao2025reflecsched"></a>**ReflecSched**<br>Shijie Cao; Yuan Yuan<br>[返回论文条目](#entry-cao2025reflecsched) | 发表信息：2025 · arXiv（2026 修订）<br>论文版本：2508.01724v3 |
| <a id="paper-yang2025resocratic"></a>**ReSocratic / OptiBench**<br>Zhicheng Yang; Yiwei Wang; Yinya Huang; Zhijiang Guo; Wei Shi; Xiongwei Han; Liang Feng; Linqi Song; Xiaodan Liang; Jing Tang<br>[返回论文条目](#entry-yang2025resocratic) | 发表信息：2025 · ICLR 2025<br>arXiv 作者姓名为 Wei Shi，会议页面的姓名拼写为 Shi Shi。 |
| <a id="paper-xu2025roco"></a>**RoCo**<br>Jiawei Xu; Feng-Feng Wei; Wei-Neng Chen<br>[返回论文条目](#entry-xu2025roco) | 发表信息：2025 · arXiv preprint<br>论文版本：2512.03762v2<br>协作与种群演化用于程序发现。 |
| <a id="paper-yazdani2025evocut"></a>**SAGE / 原 EvoCut**<br>Milad Yazdani; Mahdi Mostajabdaveh; Samin Aref; Zirui Zhou<br>[返回论文条目](#entry-yazdani2025evocut) | 发表信息：2025 · arXiv（SAGE 修订版 2026）<br>论文版本：2508.11850v3<br>LLM-Guided Evolution of Symbolic Acceleration Inequality Families for MILP <span title="arXiv">[![arXiv][badge-002]][resource-425]</span>：2026-10-19 修订，框架名 SAGE<br>EvoCut: Strengthening Integer Programs via Evolution-Guided Language Models <span title="Code（EvoCut 旧版）">[![Code（EvoCut 旧版）][badge-088]][resource-426]</span>：早期题名为 EvoCut。<br>v3 以经验可接受性与性能筛选候选不等式，未给出数学有效性证明。 |
| <a id="paper-chen2025sirl"></a>**SIRL**<br>Yitian Chen; Jingfan Xia; Siyu Shao; DongDong Ge; Yinyu Ye<br>[返回论文条目](#entry-chen2025sirl) | 发表信息：2025 · NeurIPS 2025<br>ORLMBenchmark 是作者修订的已有基准集合；它不是所有原始数据集的首次发布，不与 ORLM 的 IndustryOR 原版混计。 |
| <a id="paper-solverllm2025"></a>**SolverLLM**<br>Dong Li; Xujiang Zhao; Linlin Yu; Yanchi Liu; Wei Cheng; Zhengzhang Chen; Zhong Chen; Feng Chen; Chen Zhao; Haifeng Chen<br>[返回论文条目](#entry-solverllm2025) | 发表信息：2025 · NeurIPS 2025<br>论文版本：2510.16916v2 |
| <a id="paper-abgaryan2025starjob"></a>**Starjob**<br>Henrik Abgaryan; Tristan Cazenave; Ararat Harutyunyan<br>[返回论文条目](#entry-abgaryan2025starjob) | 发表信息：2025 · arXiv preprint<br>论文版本：2503.01877v2<br>Starjob 训练数据位于 mideavalwisard/Starjob；作者仓库提供训练脚本。arXiv 含 substantial text overlap 管理员注记。 |
| <a id="paper-wu2025stepopt"></a>**Step-Opt**<br>Yang Wu; Yifan Zhang; Yurong Wu; Yuran Wang; Junkai Zhang; Jian Cheng<br>[返回论文条目](#entry-wu2025stepopt) | 发表信息：2025 · Findings of EMNLP 2025<br>论文版本：2506.17637v1<br>Step-Opt: Boosting Optimization Modeling in LLMs through Iterative Data Synthesis and Structured Validation <span title="arXiv">[![arXiv][badge-002]][resource-085]</span>：预印本题名<br>数据与实现位于 Step/ 子目录。 |
| <a id="paper-li2025strcmp"></a>**STRCMP**<br>Xijun Li; Jiexiang Yang; Jinghao Wang; Bo Peng; Jianguo Yao; Haibing Guan<br>[返回论文条目](#entry-li2025strcmp) | 发表信息：2025 · NeurIPS 2025<br>论文版本：2506.11057v1<br>STRCMP: Integrating Graph Structural Priors with Language Models for Combinatorial Optimization <span title="arXiv">[![arXiv][badge-002]][resource-382]</span>：预印本版本；作者：Xijun Li; Jiexiang Yang; Jinghao Wang; Bo Peng; Jianguo Yao; Haibing Guan |
| <a id="paper-abedi2025thinkmath"></a>**Teaching LLMs to Think Mathematically**<br>Mohammad J. Abdel-Rahman; Yasmeen Alslman; Dania Refai; Amro Saleh; Malik A. Abu Loha; Mohammad Yahya Hamed<br>[返回论文条目](#entry-abedi2025thinkmath) | 发表信息：2025 · arXiv preprint<br>论文版本：2508.18091v1 |
| <a id="paper-singirikonda2025text2zinc"></a>**Text2Zinc**<br>Akash Singirikonda; Serdar Kadioglu; Karthik Uppuluri<br>[返回论文条目](#entry-singirikonda2025text2zinc) | 发表信息：2025 · arXiv preprint<br>论文版本：2503.10642v1<br>Text2Zinc @ AAAI 2025 为 Invited Talk。 |
| <a id="paper-nl2ps2025"></a>**Validation-in-the-Loop Power Modeling**<br>Yunkai Hu; Tianqiao Zhao; Meng Yue<br>[返回论文条目](#entry-nl2ps2025) | 发表信息：2025 · arXiv preprint<br>论文版本：2508.08147v1 |
| <a id="paper-bridgingviz2025"></a>**Visual Graph Optimization with MLLMs**<br>Jie Zhao; Kang Hao Cheong; Witold Pedrycz<br>[返回论文条目](#entry-bridgingviz2025) | 发表信息：2025 · arXiv preprint<br>论文版本：2501.11968 |
| <a id="paper-parashar2025wiqor"></a>**WIQOR**<br>Aditya Parashar; Ari Kobren; Natalia Kosilova<br>[返回论文条目](#entry-parashar2025wiqor) | 发表信息：2025 · Preprint<br>机构托管的稿件为匿名预印本。 |

</details>

<details>
<summary>2024 · 作者与版本</summary>

| 论文与作者 | 版本与资源说明 |
|---|---|
| <a id="paper-deng2024cafa"></a>**CAFA**<br>Haoxuan Deng; Bohao Zheng; Yirui Jiang; Trung Hieu Tran<br>[返回论文条目](#entry-deng2024cafa) | 发表信息：2024 · NeurIPS 2024 MATH-AI Workshop |
| <a id="paper-xiao2024coe"></a>**Chain-of-Experts**<br>Ziyang Xiao; Dongxiang Zhang; Yangjun Wu; Lilin Xu; Yuan Wang; Xiongwei Han; Xiaojin Fu; Tao Zhong; Jia Zeng; Mingli Song; Gang Chen<br>[返回论文条目](#entry-xiao2024coe) | 发表信息：2024 · ICLR 2024<br>仓库提供 ComplexOR 原始版本。 |
| <a id="paper-jiao2024cityleo"></a>**City-LEO**<br>Zihao Jiao; Mengyi Sha; Haoyu Zhang; Xinyu Jiang; Wei Qi<br>[返回论文条目](#entry-jiao2024cityleo) | 发表信息：2024 · arXiv preprint<br>论文版本：2406.10958v2<br>City-LEO 代码和数据位于 HF 的 BTBUzhy/JOC，包含数据与 Python 文件。 |
| <a id="paper-liu2024eoh"></a>**EoH**<br>Fei Liu; Tong Xialiang; Mingxuan Yuan; Xi Lin; Fu Luo; Zhenkun Wang; Zhichao Lu; Qingfu Zhang<br>[返回论文条目](#entry-liu2024eoh) | 发表信息：2024 · ICML 2024 |
| <a id="paper-xing2024lpwp"></a>**Human-aligned LPWP Evaluation**<br>Linzi Xing; Xinglu Wang; Yuxi Feng; Zhenan Fan; Jing Xiong; Zhijiang Guo; Xiaojin Fu; Rindra Ramamonjison; Mahdi Mostajabdaveh; Xiongwei Han; Zirui Zhou; Yong Zhang<br>[返回论文条目](#entry-xing2024lpwp) | 发表信息：2024 · LREC-COLING 2024<br>在既有 NL4Opt 上研究指标与人工评价；结构得分、表示层面等价与数学等价证明分别说明。 |
| <a id="paper-quan2024invagent"></a>**InvAgent**<br>Yinzhu Quan; Zefang Liu<br>[返回论文条目](#entry-quan2024invagent) | 发表信息：2024 · arXiv preprint<br>论文版本：2407.11384v2 |
| <a id="paper-tang2024itinerary"></a>**ITINERA**<br>Yihong Tang; Zhaokai Wang; Ao Qu; Yihao Yan; Zhaofeng Wu; Dingyi Zhuang; Jushi Kai; Kebing Hou; Xiaotong Guo; Jinhua Zhao; Zhan Zhao; Wei Ma<br>[返回论文条目](#entry-tang2024itinerary) | 发表信息：2024 · EMNLP 2024 Industry Track<br>论文版本：2402.07204v5<br>ITINERA: Integrating Spatial Optimization with Large Language Models for Open-domain Urban Itinerary Planning <span title="arXiv">[![arXiv][badge-002]][resource-290]</span>：预印本版本；作者：Yihong Tang; Zhaokai Wang; Ao Qu; Yihao Yan; Zhaofeng Wu; Dingyi Zhuang; Jushi Kai; Kebing Hou; Xiaotong Guo; Han Zheng; Tiange Luo; Jinhua Zhao; Zhan Zhao; Wei Ma<br>EMNLP 2024 Industry Track 与预印本的作者列表不同。 |
| <a id="paper-liu2024llm4ad"></a>**LLM4AD**<br>Fei Liu; Rui Zhang; Zhuoliang Xie; Rui Sun; Kai Li; Qinglong Hu; Ping Guo; Xi Lin; Xialiang Tong; Mingxuan Yuan; Zhenkun Wang; Zhichao Lu; Qingfu Zhang<br>[返回论文条目](#entry-liu2024llm4ad) | 发表信息：2024 · arXiv preprint |
| <a id="paper-yu2024deep"></a>**LLM–EA Automated Optimization Insights**<br>He Yu; Jing Liu<br>[返回论文条目](#entry-yu2024deep) | 发表信息：2024 · arXiv preprint<br>论文版本：2410.20848v1 |
| <a id="paper-ahmed2024lm4opt"></a>**LM4OPT**<br>Tasnim Ahmed; Salimur Choudhury<br>[返回论文条目](#entry-ahmed2024lm4opt) | 发表信息：2024 · INFOR 62（2024）<br>论文版本：2403.01342v1<br>LM4OPT: Unveiling the Potential of Large Language Models in Formulating Mathematical Optimization Problems <span title="arXiv">[![arXiv][badge-002]][resource-090]</span>：预印本版本；作者：Tasnim Ahmed; Salimur Choudhury<br>INFOR 正式版扩展了小模型比较。 |
| <a id="paper-mostajabdaveh2024multiagent"></a>**Multi-Stage Modeling & Verification**<br>Mahdi Mostajabdaveh; Timothy T. Yu; Rindranirina Ramamonjison; Giuseppe Carenini; Zirui Zhou; Yong Zhang<br>[返回论文条目](#entry-mostajabdaveh2024multiagent) | 发表信息：2024 · INFOR 62(4):599–617 |
| <a id="paper-dakle2023ner4opt"></a>**Ner4Opt**<br>Serdar Kadıoğlu; Parag Pravin Dakle; Karthik Uppuluri; Regina Politi; Preethi Raghavan; SaiKrishna Rallabandi; Ravisutha Srinivasamurthy<br>[返回论文条目](#entry-dakle2023ner4opt) | 发表信息：2024 · Constraints 29（2024）<br>Constraints 2024 与 CPAIOR 2023 为不同版本。 |
| <a id="paper-yang2024opro"></a><a id="paper-yang2025opro"></a>**OPRO**<br>Chengrun Yang; Xuezhi Wang; Yifeng Lu; Hanxiao Liu; Quoc V. Le; Denny Zhou; Xinyun Chen<br>[返回论文条目](#entry-yang2024opro) | 发表信息：2024 · ICLR 2024 |
| <a id="paper-chen2023diagnosing"></a>**OptiChat / Infeasibility Diagnosis**<br>Hao Chen; Gonzalo E. Constante-Flores; Can Li<br>[返回论文条目](#entry-chen2023diagnosing) | 发表信息：2024 · INFOR 2024<br>论文版本：2308.12923v1<br>预印本首发于 2023 年，期刊版发表于 2024 年。 |
| <a id="paper-teshnizi2024optimus"></a>**OptiMUS**<br>Ali Ahmaditeshnizi; Wenzhi Gao; Madeleine Udell<br>[返回论文条目](#entry-teshnizi2024optimus) | 发表信息：2024 · ICML 2024<br>论文版本：ICML 2024 / OptiMUS v0.2<br>OptiMUS: Optimization Modeling Using MIP Solvers and large language models <span title="OptiMUS v0.1">[![OptiMUS v0.1][badge-126]][resource-565]</span>：2023；v0.1，2023 预印本（arXiv v2）。；作者：Ali AhmadiTeshnizi; Wenzhi Gao; Madeleine Udell<br>OptiMUS: Scalable Optimization Modeling with (MI)LP Solvers and Large Language Models <span title="arXiv">[![arXiv][badge-002]][resource-183]</span>：2024；v0.2，ICML 2024 版本。；作者：Ali AhmadiTeshnizi; Wenzhi Gao; Madeleine Udell<br>OptiMUS-0.3: Using Large Language Models to Model and Solve Optimization Problems at Scale <span title="OptiMUS v0.3">[![OptiMUS v0.3][badge-127]][resource-566]</span>：2024；v0.3 扩展版（arXiv v4，2026-06-26）。；作者：Ali AhmadiTeshnizi; Wenzhi Gao; Herman Brunborg; Shayan Talaei; Connor Lawless; Madeleine Udell<br>ICML 2024 对应 v0.2；v0.3 为扩展版本，作者列表与实验范围不同。<br>OptiMUS v0.1：OptiMUS 相关版本，实验范围各有不同。<br>OptiMUS v0.3：OptiMUS 相关版本，实验范围各有不同。 |
| <a id="paper-zhang2024optllm"></a>**OptLLM**<br>Jihai Zhang; Wei Wang; Siyan Guo; Li Wang; Fangquan Lin; Cheng Yang; Wotao Yin<br>[返回论文条目](#entry-zhang2024optllm) | 发表信息：2024 · NAACL 2024 Industry Track<br>论文版本：2407.07924v1<br>Solving General Natural-Language-Description Optimization Problems with Large Language Models <span title="arXiv">[![arXiv][badge-002]][resource-198]</span>：预印本版本；作者：Jihai Zhang; Wei Wang; Siyan Guo; Li Wang; Fangquan Lin; Cheng Yang; Wotao Yin<br>发表于 NAACL 2024 Industry Track，提供云端试用页面。<br>MindOpt Trial (International)：云端试用。<br>MindOpt Trial (CN)：云端试用。 |
| <a id="paper-tang2024ragdys"></a>**RAGDyS**<br>Paul Mingzheng Tang; Kenji Kah Hoe Leong; Nowshad Shaik; Hoong Chuin Lau<br>[返回论文条目](#entry-tang2024ragdys) | 发表信息：2024 · arXiv preprint<br>论文版本：2405.06697v1 |
| <a id="paper-wang2024raremip"></a>**Rare MIP Challenges**<br>Teng Wang; Wing-Yin Yu; Ruifeng She; Wenhan Yang; Taijie Chen; Jianping Zhang<br>[返回论文条目](#entry-wang2024raremip) | 发表信息：2024 · arXiv preprint<br>论文版本：2409.04464v2 |
| <a id="paper-ye2024reevo"></a>**ReEvo**<br>Haoran Ye; Jiarui Wang; Zhiguang Cao; Federico Berto; Chuanbo Hua; Haeyeon Kim; Jinkyoo Park; Guojie Song<br>[返回论文条目](#entry-ye2024reevo) | 发表信息：2024 · NeurIPS 2024 |
| <a id="paper-ju2024ttg"></a>**To the Globe / TTG**<br>Da JU; Song Jiang; Andrew Cohen; Aaron Foss; Sasha Mitts; Arman Zharmagambetov; Brandon Amos; Xian Li; Justine T Kao; Maryam Fazel-Zarandi; Yuandong Tian<br>[返回论文条目](#entry-ju2024ttg) | 发表信息：2024 · EMNLP 2024 System Demonstrations<br>论文版本：2410.16456v1 |

</details>

<details>
<summary>2023 · 作者与版本</summary>

| 论文与作者 | 版本与资源说明 |
|---|---|
| <a id="paper-liu2023ael"></a>**AEL**<br>Fei Liu; Xialiang Tong; Mingxuan Yuan; Qingfu Zhang<br>[返回论文条目](#entry-liu2023ael) | 发表信息：2023 · arXiv preprint<br>论文版本：2311.15249v1<br>为 EoH 的前作。 |
| <a id="paper-alahakoon2023copilot"></a>**AI-Copilot for Business Optimisation**<br>Pivithuru Thejan Amarasinghe; Su Nguyen; Yuan Sun; Damminda Alahakoon<br>[返回论文条目](#entry-alahakoon2023copilot) | 发表信息：2023 · arXiv preprint<br>论文版本：2309.13218v5<br>AI-Copilot for Business Optimisation: A Framework and a Case Study in Production Scheduling <span title="arXiv">[![arXiv][badge-002]][resource-098]</span>：早期题名<br>arXiv v5 更新了题名；Artifacts 仓库提供生成的优化公式。 |
| <a id="paper-synth2023"></a>**CodeT5 Mathematical Program Synthesis**<br>Ganesh Prasath; Shirish Karande<br>[返回论文条目](#entry-synth2023) | 发表信息：2023 · ICLR 2023 DL4C Workshop / arXiv<br>论文版本：2304.03287v1<br>CodeT5 为早期小型编码模型。 |
| <a id="paper-romera2023funsearch"></a>**FunSearch**<br>Bernardino Romera-Paredes; Mohammadamin Barekatain; Alexander Novikov; Matej Balog; M. Pawan Kumar; Emilien Dupont; Francisco J. R. Ruiz; Jordan S. Ellenberg; Pengming Wang; Omar Fawzi; Pushmeet Kohli; Alhussein Fawzi<br>[返回论文条目](#entry-romera2023funsearch) | 发表信息：2023 · Nature（2023 在线发表）<br>Nature 在线发表于 2023 年，卷期年份为 2024 年。 |
| <a id="paper-kadioglu2023holygrail"></a>**Holy Grail 2.0**<br>Dimos Tsouros; Hélène Verhaeghe; Serdar Kadıoğlu; Tias Guns<br>[返回论文条目](#entry-kadioglu2023holygrail) | 发表信息：2023 · arXiv preprint<br>论文版本：2308.01589v1<br>原文为 position paper。 |
| <a id="paper-li2023power"></a>**LLMs for Power Engineering**<br>Ran Li; Chuanqing Pu; Junyi Tao; Canbing Li; Feilong Fan; Yue Xiang; Sijie Chen<br>[返回论文条目](#entry-li2023power) | 发表信息：2023 · arXiv preprint |
| <a id="paper-li2023synthesizing"></a>**Multi-stage MILP Synthesis**<br>Qingyang Li; Lele Zhang; Vicky Mak-Hau<br>[返回论文条目](#entry-li2023synthesizing) | 发表信息：2023 · arXiv preprint<br>论文版本：2311.15271v1<br>为 SMILO 引用的独立前作；仓库提供数据。 |
| <a id="paper-ramamonjison2023nl4opt"></a>**NL4Opt**<br>Rindranirina Ramamonjison; Timothy Yu; Raymond Li; Haley Li; Giuseppe Carenini; Bissan Ghaddar; Shiqi He; Mahdi Mostajabdaveh; Amin Banitalebi-Dehkordi; Zirui Zhou; Yong Zhang<br>[返回论文条目](#entry-ramamonjison2023nl4opt) | 发表信息：2023 · NeurIPS 2022 Competition Track / PMLR 220 |
| <a id="paper-iflytek2023autoformulation"></a>**NL4Opt: Auto-Formulation Approach**<br>Yuting Ning; Jiayu Liu; Longhu Qin; Tong Xiao; Shangzi Xue; Zhenya Huang; Qi Liu; Enhong Chen; Jinze Wu<br>[返回论文条目](#entry-iflytek2023autoformulation) | 发表信息：2023 · arXiv preprint<br>论文版本：2302.04643v1 |
| <a id="paper-wang2023opdnl4opt"></a>**OPD@NL4Opt**<br>Kangxu Wang; Ze Chen; Jiewen Zheng<br>[返回论文条目](#entry-wang2023opdnl4opt) | 发表信息：2023 · arXiv preprint; NL4Opt competition system |
| <a id="paper-li2023optiguide"></a>**OptiGuide**<br>Beibin Li; Konstantina Mellou; Bo Zhang; Jeevan Pathuri; Ishai Menache<br>[返回论文条目](#entry-li2023optiguide) | 发表信息：2023 · arXiv preprint<br>共享仓库包含多项优化研究工作。 |

</details>

<details>
<summary>2022 · 作者与版本</summary>

| 论文与作者 | 版本与资源说明 |
|---|---|
| <a id="paper-ramamonjison2022augmenting"></a>**Auto-formulation (2022)**<br>Rindra Ramamonjison; Haley Li; Timothy Yu; Shiqi He; Vishnu Rengan; Amin Banitalebi-Dehkordi; Zirui Zhou; Yong Zhang<br>[返回论文条目](#entry-ramamonjison2022augmenting) | 发表信息：2022 · EMNLP 2022 Industry<br>与 NL4Opt 竞赛报告共享数据；1,101 项按训练 / 开发 / 测试划分为 713 / 99 / 289。<br>Code & Data（NL4Opt）：NL4Opt 数据与评测脚本，包含 generation_data 和 ner_data。 |

</details>

[返回目录](#contents)

<a id="classification"></a>

## 分类与阅读说明

按核心研究任务分类，并提供技术、资源和应用场景索引。

- **交叉贡献：** 同时提出方法与新基准的论文进入对应方法和评测模块；仅使用既有基准验证方法的工作保留在方法模块。
- **资源类型：** 训练数据、评测数据、领域模型、技能与工具分别列示，获取索引只展示已有入口。
- **训练对象：** LLM 参数更新、辅助网络训练、神经路由策略训练与算法程序演化分别标记。
- **验证证据：** 区分执行成功、可行性、目标值匹配、结构一致、公式关系与题意符合性；核验结论依赖具体假设。
- **应用索引：** 按核心研究场景提供跳转，单个示例任务不自动构成应用归属。

| 工作 | 研究主线 | 技术标签 | 配套资源或评测 |
|---|---|---|---|
| ORLM | 优化建模与代码生成 | Data synthesis · SFT / distillation | IndustryOR、训练数据与领域模型 |
| OptiMUS | 优化建模与代码生成 | Agent · Multi-agent · Execution / solver feedback | NLP4LP |
| ReEvo | 启发式与算法自动设计 | Program evolution · Reflection | 官方代码 |
| Starjob | 直接解生成与优化决策 | SFT / distillation | 调度训练数据与模型 |
| SOVER | 模型验证、诊断与修复 | Formal verification | 核验评测 |

[返回目录](#contents)

<a id="contributing"></a>

## 收录与贡献

欢迎通过 Issue 或 Pull Request 补充论文、资源或分类建议。请提供题名、作者、年份、发表信息、论文链接及简要贡献说明。

相关合集：[LLM4OR][resource-016] · [awesome-fm4co][resource-567] · [LLM4AlgorithmDesign][resource-005]。

[返回目录](#contents)

[badge-001]: https://img.shields.io/static/v1?label=&message=DOI&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-002]: https://img.shields.io/static/v1?label=&message=arXiv&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[badge-003]: https://img.shields.io/static/v1?label=&message=Collection&color=181717&style=flat&logo=github&logoColor=white
[badge-004]: https://img.shields.io/static/v1?label=&message=Case-study+Code&color=181717&style=flat&logo=github&logoColor=white
[badge-005]: https://img.shields.io/static/v1?label=&message=Proceedings&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-006]: https://img.shields.io/static/v1?label=&message=Cleaned+data&color=181717&style=flat&logo=github&logoColor=white
[badge-007]: https://img.shields.io/static/v1?label=&message=Paper&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-008]: https://img.shields.io/static/v1?label=&message=Code&color=181717&style=flat&logo=github&logoColor=white
[badge-009]: https://img.shields.io/static/v1?label=&message=Sample+data&color=181717&style=flat&logo=github&logoColor=white
[badge-010]: https://img.shields.io/static/v1?label=&message=Results&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-011]: https://img.shields.io/static/v1?label=&message=Demo&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-012]: https://img.shields.io/static/v1?label=&message=Dataset&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-013]: https://img.shields.io/static/v1?label=&message=SAGE+SFT+100K&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-014]: https://img.shields.io/static/v1?label=&message=Model&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-015]: https://img.shields.io/static/v1?label=&message=Model+7B&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-016]: https://img.shields.io/static/v1?label=&message=Model+32B&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-017]: https://img.shields.io/static/v1?label=&message=Journal&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-018]: https://img.shields.io/static/v1?label=&message=IndustryOR&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-019]: https://img.shields.io/static/v1?label=&message=OR-Instruct-3K&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-020]: https://img.shields.io/static/v1?label=&message=RoBERTa+v1&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-021]: https://img.shields.io/static/v1?label=&message=RoBERTa+v2&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-022]: https://img.shields.io/static/v1?label=&message=Training+Data&color=181717&style=flat&logo=github&logoColor=white
[badge-023]: https://img.shields.io/static/v1?label=&message=Formulations&color=181717&style=flat&logo=github&logoColor=white
[badge-024]: https://img.shields.io/static/v1?label=&message=Case+data&color=181717&style=flat&logo=github&logoColor=white
[badge-025]: https://img.shields.io/static/v1?label=&message=Outputs&color=181717&style=flat&logo=github&logoColor=white
[badge-026]: https://img.shields.io/static/v1?label=&message=LPWP+data&color=181717&style=flat&logo=github&logoColor=white
[badge-027]: https://img.shields.io/static/v1?label=&message=Modeling+Data&color=181717&style=flat&logo=github&logoColor=white
[badge-028]: https://img.shields.io/static/v1?label=&message=Results&color=009BD5&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0ibm9uZSIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyLjUiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgZD0ibTEwIDE0IDQtNG0tNiAxLTIgMmE0IDQgMCAwIDAgNiA2bDItMm0tNC0xMCAyLTJhNCA0IDAgMCAxIDYgNmwtMiAyIi8%2BPC9zdmc%2B&logoColor=white
[badge-029]: https://img.shields.io/static/v1?label=&message=Code+%26+data&color=181717&style=flat&logo=github&logoColor=white
[badge-030]: https://img.shields.io/static/v1?label=&message=Eval+artifacts&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-031]: https://img.shields.io/static/v1?label=&message=Code+1&color=181717&style=flat&logo=github&logoColor=white
[badge-032]: https://img.shields.io/static/v1?label=&message=Code+2&color=181717&style=flat&logo=github&logoColor=white
[badge-033]: https://img.shields.io/static/v1?label=&message=Skills&color=181717&style=flat&logo=github&logoColor=white
[badge-034]: https://img.shields.io/static/v1?label=&message=Appendix&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-035]: https://img.shields.io/static/v1?label=&message=Inference&color=181717&style=flat&logo=github&logoColor=white
[badge-036]: https://img.shields.io/static/v1?label=&message=SDRL+Qwen3+4B&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-037]: https://img.shields.io/static/v1?label=&message=SOLID-Qwen3&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-038]: https://img.shields.io/static/v1?label=&message=SOLID-StepORLM&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-039]: https://img.shields.io/static/v1?label=&message=Policy+8B&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-040]: https://img.shields.io/static/v1?label=&message=GenPRM+8B&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-041]: https://img.shields.io/static/v1?label=&message=Gurobi+7B&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-042]: https://img.shields.io/static/v1?label=&message=COPT+7B&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-043]: https://img.shields.io/static/v1?label=&message=Gurobi+32B&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-044]: https://img.shields.io/static/v1?label=&message=COPT+32B&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-045]: https://img.shields.io/static/v1?label=&message=Revised+data&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-046]: https://img.shields.io/static/v1?label=&message=Data+%26+code&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-047]: https://img.shields.io/static/v1?label=&message=Trial+%28Intl%29&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-048]: https://img.shields.io/static/v1?label=&message=Trial+%28CN%29&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-049]: https://img.shields.io/static/v1?label=&message=Agent&color=181717&style=flat&logo=github&logoColor=white
[badge-050]: https://img.shields.io/static/v1?label=&message=Archive+v2&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-051]: https://img.shields.io/static/v1?label=&message=Benchmark&color=181717&style=flat&logo=github&logoColor=white
[badge-052]: https://img.shields.io/static/v1?label=&message=Text2Zinc&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-053]: https://img.shields.io/static/v1?label=&message=Editor&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-054]: https://img.shields.io/static/v1?label=&message=Leaderboard&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-055]: https://img.shields.io/static/v1?label=&message=Package&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-056]: https://img.shields.io/static/v1?label=&message=Gala+in+Text2Model&color=181717&style=flat&logo=github&logoColor=white
[badge-057]: https://img.shields.io/static/v1?label=&message=Project&color=009BD5&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0ibm9uZSIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyLjUiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgZD0ibTEwIDE0IDQtNG0tNiAxLTIgMmE0IDQgMCAwIDAgNiA2bDItMm0tNC0xMCAyLTJhNCA0IDAgMCAxIDYgNmwtMiAyIi8%2BPC9zdmc%2B&logoColor=white
[badge-058]: https://img.shields.io/static/v1?label=&message=Data+%26+checks&color=181717&style=flat&logo=github&logoColor=white
[badge-059]: https://img.shields.io/static/v1?label=&message=Diagnosis+Data&color=181717&style=flat&logo=github&logoColor=white
[badge-060]: https://img.shields.io/static/v1?label=&message=Code+%26+eval&color=181717&style=flat&logo=github&logoColor=white
[badge-061]: https://img.shields.io/static/v1?label=&message=OptiVerse+1K&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-062]: https://img.shields.io/static/v1?label=&message=EquivaFormulation&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-063]: https://img.shields.io/static/v1?label=&message=NLP4LP&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-064]: https://img.shields.io/static/v1?label=&message=Project&color=181717&style=flat&logo=github&logoColor=white
[badge-065]: https://img.shields.io/static/v1?label=&message=Poster&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-066]: https://img.shields.io/static/v1?label=&message=Benchmark+Data&color=181717&style=flat&logo=github&logoColor=white
[badge-067]: https://img.shields.io/static/v1?label=&message=Archive&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-068]: https://img.shields.io/static/v1?label=&message=Code+%26+samples&color=181717&style=flat&logo=github&logoColor=white
[badge-069]: https://img.shields.io/static/v1?label=&message=SFT+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-070]: https://img.shields.io/static/v1?label=&message=RL+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-071]: https://img.shields.io/static/v1?label=&message=Revised+arXiv&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[badge-072]: https://img.shields.io/static/v1?label=&message=Prompts+%26+code&color=181717&style=flat&logo=github&logoColor=white
[badge-073]: https://img.shields.io/static/v1?label=&message=PDF&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-074]: https://img.shields.io/static/v1?label=&message=LLaMoCo-S+Example&color=181717&style=flat&logo=github&logoColor=white
[badge-075]: https://img.shields.io/static/v1?label=&message=LLaMoCo-S&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-076]: https://img.shields.io/static/v1?label=&message=Framework&color=181717&style=flat&logo=github&logoColor=white
[badge-077]: https://img.shields.io/static/v1?label=&message=Frontend&color=181717&style=flat&logo=github&logoColor=white
[badge-078]: https://img.shields.io/static/v1?label=&message=CO+Instances&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-079]: https://img.shields.io/static/v1?label=&message=LLM4AD%3A+LHNS&color=181717&style=flat&logo=github&logoColor=white
[badge-080]: https://img.shields.io/static/v1?label=&message=LLM4AD%3A+MEoH&color=181717&style=flat&logo=github&logoColor=white
[badge-081]: https://img.shields.io/static/v1?label=&message=Evolved+ALNS&color=181717&style=flat&logo=github&logoColor=white
[badge-082]: https://img.shields.io/static/v1?label=&message=OpenReview&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-083]: https://img.shields.io/static/v1?label=&message=Operators&color=181717&style=flat&logo=github&logoColor=white
[badge-084]: https://img.shields.io/static/v1?label=&message=Lean+Proofs&color=181717&style=flat&logo=github&logoColor=white
[badge-085]: https://img.shields.io/static/v1?label=&message=CO+Task+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-086]: https://img.shields.io/static/v1?label=&message=Results&color=181717&style=flat&logo=github&logoColor=white
[badge-087]: https://img.shields.io/static/v1?label=&message=Problems&color=181717&style=flat&logo=github&logoColor=white
[badge-088]: https://img.shields.io/static/v1?label=&message=EvoCut+code&color=181717&style=flat&logo=github&logoColor=white
[badge-089]: https://img.shields.io/static/v1?label=&message=SAGE+v3&color=181717&style=flat&logo=github&logoColor=white
[badge-090]: https://img.shields.io/static/v1?label=&message=Code+Archive&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-091]: https://img.shields.io/static/v1?label=&message=Eval+data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-092]: https://img.shields.io/static/v1?label=&message=Workshop&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-093]: https://img.shields.io/static/v1?label=&message=JA%2FEN+data&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-094]: https://img.shields.io/static/v1?label=&message=Data&color=181717&style=flat&logo=github&logoColor=white
[badge-095]: https://img.shields.io/static/v1?label=&message=Version&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[badge-096]: https://img.shields.io/static/v1?label=&message=SAGE+code&color=181717&style=flat&logo=github&logoColor=white
[badge-097]: https://img.shields.io/static/v1?label=&message=Original+data&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-098]: https://img.shields.io/static/v1?label=&message=Original+data&color=181717&style=flat&logo=github&logoColor=white
[badge-099]: https://img.shields.io/static/v1?label=&message=Record&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-100]: https://img.shields.io/static/v1?label=&message=InventoryBench&color=181717&style=flat&logo=github&logoColor=white
[badge-101]: https://img.shields.io/static/v1?label=&message=Experiment&color=181717&style=flat&logo=github&logoColor=white
[badge-102]: https://img.shields.io/static/v1?label=&message=Leaderboard&color=009BD5&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0ibm9uZSIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyLjUiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgZD0ibTEwIDE0IDQtNG0tNiAxLTIgMmE0IDQgMCAwIDAgNiA2bDItMm0tNC0xMCAyLTJhNCA0IDAgMCAxIDYgNmwtMiAyIi8%2BPC9zdmc%2B&logoColor=white
[badge-103]: https://img.shields.io/static/v1?label=&message=Code+%26+data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-104]: https://img.shields.io/static/v1?label=&message=Metrics+code&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-105]: https://img.shields.io/static/v1?label=&message=Study+Code&color=181717&style=flat&logo=github&logoColor=white
[badge-106]: https://img.shields.io/static/v1?label=&message=Skills+2026&color=181717&style=flat&logo=github&logoColor=white
[badge-107]: https://img.shields.io/static/v1?label=&message=Test+subset&color=181717&style=flat&logo=github&logoColor=white
[badge-108]: https://img.shields.io/static/v1?label=&message=Weights&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-109]: https://img.shields.io/static/v1?label=&message=Repo&color=181717&style=flat&logo=github&logoColor=white
[badge-110]: https://img.shields.io/static/v1?label=&message=Suite&color=181717&style=flat&logo=github&logoColor=white
[badge-111]: https://img.shields.io/static/v1?label=&message=Data&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-112]: https://img.shields.io/static/v1?label=&message=Data+%26+eval&color=181717&style=flat&logo=github&logoColor=white
[badge-113]: https://img.shields.io/static/v1?label=&message=Data+subset&color=181717&style=flat&logo=github&logoColor=white
[badge-114]: https://img.shields.io/static/v1?label=&message=Eval+code&color=181717&style=flat&logo=github&logoColor=white
[badge-115]: https://img.shields.io/static/v1?label=&message=Test+data&color=181717&style=flat&logo=github&logoColor=white
[badge-116]: https://img.shields.io/static/v1?label=&message=Data+mirror&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-117]: https://img.shields.io/static/v1?label=&message=Environment&color=181717&style=flat&logo=github&logoColor=white
[badge-118]: https://img.shields.io/static/v1?label=&message=Train+data&color=181717&style=flat&logo=github&logoColor=white
[badge-119]: https://img.shields.io/static/v1?label=&message=Zenodo+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-120]: https://img.shields.io/static/v1?label=&message=Zenodo+v2&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-121]: https://img.shields.io/static/v1?label=&message=Instances&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-122]: https://img.shields.io/static/v1?label=&message=Google+Drive+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-123]: https://img.shields.io/static/v1?label=&message=Artifacts&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-124]: https://img.shields.io/static/v1?label=&message=Paper&color=FFD21E&style=flat&logo=huggingface&logoColor=1F2937
[badge-125]: https://img.shields.io/static/v1?label=&message=arXiv+v3&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[badge-126]: https://img.shields.io/static/v1?label=&message=OptiMUS+v0.1&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[badge-127]: https://img.shields.io/static/v1?label=&message=OptiMUS+v0.3&color=B31B1B&style=flat&logo=arxiv&logoColor=white

[resource-001]: https://doi.org/10.1145/3801961
[resource-002]: https://arxiv.org/abs/2507.03637
[resource-003]: https://arxiv.org/abs/2410.14716
[resource-004]: https://doi.org/10.1145/3787585
[resource-005]: https://github.com/FeiLiu36/LLM4AlgorithmDesign
[resource-006]: https://doi.org/10.1109/MIPRO70003.2026.11591581
[resource-007]: https://arxiv.org/abs/2606.15577
[resource-008]: https://doi.org/10.1109/MCI.2026.3727078
[resource-009]: https://arxiv.org/abs/2509.08269
[resource-010]: https://github.com/ishmael233/LLM4OPT
[resource-011]: https://arxiv.org/abs/2607.18147
[resource-012]: https://github.com/d2rojas/LLMs-Agents-For-SmartGrids-Code
[resource-013]: https://ojs.aaai.org/index.php/AAAI/article/view/35090
[resource-014]: https://arxiv.org/abs/2402.16269
[resource-015]: https://arxiv.org/abs/2508.10047
[resource-016]: https://github.com/LLM4OR/LLM4OR
[resource-017]: https://github.com/LLM4OR/LLM4OR/tree/master/static/clean_benchmarks
[resource-018]: https://arxiv.org/abs/2509.18180
[resource-019]: https://arxiv.org/abs/2508.18091
[resource-020]: https://arxiv.org/abs/2410.20848
[resource-021]: https://icml.cc/virtual/2026/78174
[resource-022]: https://arxiv.org/abs/2604.16804
[resource-023]: https://arxiv.org/abs/2606.27611
[resource-024]: https://github.com/xxxxxa-hub/COOPA
[resource-025]: https://ojs.aaai.org/index.php/AAAI/article/view/40699
[resource-026]: https://github.com/xzymustbexzy/DeepOR
[resource-027]: https://github.com/xzymustbexzy/DeepOR/tree/main/data
[resource-028]: https://arxiv.org/abs/2601.09100
[resource-029]: https://arxiv.org/abs/2602.01082
[resource-030]: https://github.com/WillowHe/EvoOpt_oppangu_optimization_model
[resource-031]: https://neurips.cc/virtual/2026/poster/155640
[resource-032]: https://arxiv.org/abs/2606.26578
[resource-033]: https://arxiv.org/abs/2602.11164
[resource-034]: https://proceedings.mlr.press/v306/liu26d.html
[resource-035]: https://github.com/ernikhildhaka-arch/OptMiner-Reproduction
[resource-036]: https://huggingface.co/datasets/ernikhil411/OptMiner-Reproduction
[resource-037]: https://huggingface.co/spaces/ernikhil411/repro-opt-miner
[resource-038]: https://arxiv.org/abs/2607.05346
[resource-039]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/4624803ce92f6c44d8cabe085d8d9d96-Abstract-Conference.html
[resource-040]: https://doi.org/10.1609/aaai.v40i1.36983
[resource-041]: https://arxiv.org/abs/2511.09092
[resource-042]: https://github.com/SCUTE-ZZ/OR-R1
[resource-043]: https://doi.org/10.1016/j.ait.2026.100059
[resource-044]: https://arxiv.org/abs/2508.14410
[resource-045]: https://github.com/ZJU-TSELab/ORThought
[resource-046]: https://huggingface.co/datasets/LabMem012/LogiOR
[resource-047]: https://proceedings.mlr.press/v306/zhao26z.html
[resource-048]: https://arxiv.org/abs/2605.02545
[resource-049]: https://github.com/rachhhhing/SAGE
[resource-050]: https://huggingface.co/datasets/Rachhhhing/SAGE-SFT-100K
[resource-051]: https://doi.org/10.1080/00207543.2026.2663386
[resource-052]: https://arxiv.org/abs/2511.02364
[resource-053]: https://neurips.cc/virtual/2025/133378
[resource-054]: https://arxiv.org/abs/2510.18428
[resource-055]: https://github.com/Minw913/AlphaOPT
[resource-056]: https://proceedings.mlr.press/v267/astorga25a.html
[resource-057]: https://arxiv.org/abs/2411.01679
[resource-058]: https://github.com/jumpynitro/AutoFormulator
[resource-059]: https://aclanthology.org/2025.acl-long.40/
[resource-060]: https://github.com/LLM4OR/StructuredOR
[resource-061]: https://huggingface.co/datasets/LLM4OR/StructuredOR
[resource-062]: https://arxiv.org/abs/2510.04204
[resource-063]: https://arxiv.org/abs/2509.22979
[resource-064]: https://github.com/microsoft/OptiGuide
[resource-065]: https://huggingface.co/microsoft/OptiMind-SFT
[resource-066]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/aeaf9b454f4670d5bf2f02b4b6e5bffd-Abstract-Conference.html
[resource-067]: https://arxiv.org/abs/2510.22192
[resource-068]: https://github.com/MIRALab-USTC/OptiTree
[resource-069]: https://arxiv.org/abs/2508.03117
[resource-070]: https://proceedings.mlr.press/v267/lu25o.html
[resource-071]: https://github.com/optsuite/OptMATH
[resource-072]: https://huggingface.co/Aurora-Gem/OptMATH-Qwen2.5-7B
[resource-073]: https://huggingface.co/Aurora-Gem/OptMATH-Qwen2.5-32B-Instruct
[resource-074]: https://huggingface.co/datasets/Aurora-Gem/OptMATH-Train
[resource-075]: https://arxiv.org/abs/2405.17743
[resource-076]: https://pubsonline.informs.org/doi/10.1287/opre.2024.1233
[resource-077]: https://github.com/Cardinal-Operations/ORLM
[resource-078]: https://huggingface.co/CardinalOperations/ORLM-LLaMA-3-8B
[resource-079]: https://huggingface.co/datasets/CardinalOperations/IndustryOR
[resource-080]: https://huggingface.co/datasets/CardinalOperations/OR-Instruct-Data-3K
[resource-081]: https://proceedings.iclr.cc/paper_files/paper/2025/hash/3deb687c44d3687ace0729e5db3b4efd-Abstract-Conference.html
[resource-082]: https://arxiv.org/abs/2407.09887
[resource-083]: https://github.com/yangzhch6/PRIVATE-RS
[resource-084]: https://aclanthology.org/2025.findings-emnlp.691/
[resource-085]: https://arxiv.org/abs/2506.17637
[resource-086]: https://github.com/samwu-learn/Step
[resource-087]: https://proceedings.iclr.cc/paper_files/paper/2024/hash/d45ee77826332c100a1e15f7765b99ff-Abstract-Conference.html
[resource-088]: https://github.com/xzymustbexzy/Chain-of-Experts
[resource-089]: https://doi.org/10.1080/03155986.2024.2388452
[resource-090]: https://arxiv.org/abs/2403.01342
[resource-091]: https://doi.org/10.1007/s10601-024-09376-5
[resource-092]: https://github.com/skadio/ner4opt
[resource-093]: https://huggingface.co/skadio/ner4opt-roberta-v1
[resource-094]: https://huggingface.co/skadio/ner4opt-roberta-v2
[resource-095]: https://huggingface.co/spaces/skadio/Ner4Opt
[resource-096]: https://aclanthology.org/2024.emnlp-demo.25/
[resource-097]: https://arxiv.org/abs/2410.16456
[resource-098]: https://arxiv.org/abs/2309.13218
[resource-099]: https://github.com/pivithuruthejanamarasinghe/AI-Copilot-Data
[resource-100]: https://github.com/pivithuruthejanamarasinghe/AI-Copilot-Artifacts
[resource-101]: https://github.com/pivithuruthejanamarasinghe/AI-Copilot-Data-Real-World-Scenario
[resource-102]: https://github.com/pivithuruthejanamarasinghe/AI-Copilot-Artifacts-Real-World-Scenario
[resource-103]: https://github.com/pivithuruthejanamarasinghe/LPWP
[resource-104]: https://arxiv.org/abs/2304.03287
[resource-105]: https://arxiv.org/abs/2311.15271
[resource-106]: https://github.com/yangyangyang777/Datasets-for-automatic-modeling.git
[resource-107]: https://arxiv.org/abs/2302.04643
[resource-108]: https://github.com/bigdata-ustc/nl4opt
[resource-109]: https://arxiv.org/abs/2301.02459
[resource-110]: https://nl4opt.github.io/results/
[resource-111]: https://aclanthology.org/2022.emnlp-industry.4/
[resource-112]: https://github.com/nl4opt/nl4opt-competition
[resource-113]: https://arxiv.org/abs/2604.25847
[resource-114]: https://github.com/CHIANGEL/Agora-Opt
[resource-115]: https://link.springer.com/chapter/10.1007/978-3-032-09192-5_5
[resource-116]: https://arxiv.org/abs/2505.01485
[resource-117]: https://arxiv.org/abs/2602.02029
[resource-118]: https://arxiv.org/abs/2604.00442
[resource-119]: https://arxiv.org/abs/2604.17708
[resource-120]: https://arxiv.org/abs/2601.09635
[resource-121]: https://github.com/CoraLiang01/lean-llm-opt
[resource-122]: https://arxiv.org/abs/2606.25832
[resource-123]: https://github.com/Hsiang-1/MiniOpt
[resource-124]: https://proceedings.mlr.press/v306/song26z.html
[resource-125]: https://arxiv.org/abs/2601.21372
[resource-126]: https://huggingface.co/datasets/c3aiia3c/nemo-icml2026
[resource-127]: https://arxiv.org/abs/2607.27918
[resource-128]: https://github.com/xianchaoxiu/OptGraph
[resource-129]: https://arxiv.org/abs/2608.07040
[resource-130]: https://aclanthology.org/2026.findings-emnlp.394/
[resource-131]: https://arxiv.org/abs/2605.29829
[resource-132]: https://github.com/fujiwaranoM0kou/OptSkills
[resource-133]: https://github.com/HQian-AI/OptSkills
[resource-134]: https://github.com/HQian-AI/OptSkills/tree/main/skill_library
[resource-135]: https://arxiv.org/abs/2607.18256
[resource-136]: https://neurips.cc/virtual/2026/poster/152032
[resource-137]: https://github.com/AuroraLHL/PEARL
[resource-138]: https://huggingface.co/Aurora-Gem/PEARL-Qwen3-4B-Instruct-2507
[resource-139]: https://arxiv.org/abs/2609.00859
[resource-140]: https://doi.org/10.5281/zenodo.19134435
[resource-141]: https://arxiv.org/abs/2609.34427
[resource-142]: https://github.com/tokentideAI/LLMMetaSolver
[resource-143]: https://huggingface.co/tokentideAI/SDRL-Qwen3-4B
[resource-144]: https://arxiv.org/abs/2609.09957
[resource-145]: https://github.com/AIOR-Research/SOLID
[resource-146]: https://huggingface.co/AIOR-Research/SOLID-Qwen3
[resource-147]: https://huggingface.co/AIOR-Research/SOLID-StepORLM
[resource-148]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/0bcfb525c8f8f07ae10a93d0b2a40e00-Abstract-Conference.html
[resource-149]: https://arxiv.org/abs/2509.22558
[resource-150]: https://github.com/0xzhouchenyu/StepORLM
[resource-151]: https://huggingface.co/Chenyu-Zhou/StepORLM-Qwen3-8B
[resource-152]: https://huggingface.co/Chenyu-Zhou/StepORLM-GenPRM-Qwen3-8B
[resource-153]: https://proceedings.iclr.cc/paper_files/paper/2025/hash/73d6c3e4b214deebbbf8256e26d2cf45-Abstract-Conference.html
[resource-154]: https://iclr.cc/virtual/2025/poster/28142
[resource-155]: https://github.com/Summer142857/DRoC
[resource-156]: https://proceedings.iclr.cc/paper_files/paper/2025/hash/fbe6dd68b0cf2b1d43b458d2b8ca31b0-Abstract-Conference.html
[resource-157]: https://arxiv.org/abs/2410.13213
[resource-158]: https://github.com/antgroup/LLMOPT
[resource-159]: https://huggingface.co/ant-opt/LLMOPT-Qwen2.5-14B
[resource-160]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/31e89283741f8f70ad2290b5c197ae18-Abstract-Conference.html
[resource-161]: https://arxiv.org/abs/2504.16918
[resource-162]: https://arxiv.org/abs/2503.10009
[resource-163]: https://github.com/bwz96sco/or_llm_agent
[resource-164]: https://huggingface.co/datasets/SJTU/BWOR
[resource-165]: https://aclanthology.org/2025.acl-industry.10/
[resource-166]: https://arxiv.org/abs/2506.01326
[resource-167]: https://github.com/XiaoAI1989/ORMind
[resource-168]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/98555b92e5dedbdad5921049281995bc-Abstract-Conference.html
[resource-169]: https://arxiv.org/abs/2505.11792
[resource-170]: https://github.com/Cardinal-Operations/SIRL
[resource-171]: https://huggingface.co/chenyitian-shanshu/SIRL-Gurobi
[resource-172]: https://huggingface.co/chenyitian-shanshu/SIRL-COPT
[resource-173]: https://huggingface.co/chenyitian-shanshu/SIRL-Gurobi32B
[resource-174]: https://huggingface.co/chenyitian-shanshu/SIRL-COPT32B
[resource-175]: https://huggingface.co/datasets/chenyitian-shanshu/ORLMBenchmark
[resource-176]: https://proceedings.nips.cc/paper_files/paper/2025/hash/903475a4d33d21bfd75d4fa0d124abfe-Abstract-Conference.html
[resource-177]: https://arxiv.org/abs/2510.16916
[resource-178]: https://arxiv.org/abs/2508.08147
[resource-179]: https://neurips.cc/virtual/2024/98475
[resource-180]: https://github.com/BlueAsuka/CAFA
[resource-181]: https://doi.org/10.1080/03155986.2024.2381306
[resource-182]: https://proceedings.mlr.press/v235/ahmaditeshnizi24a.html
[resource-183]: https://arxiv.org/abs/2402.10172
[resource-184]: https://github.com/teshnizi/OptiMUS
[resource-185]: https://huggingface.co/datasets/udell-lab/NLP4LP
[resource-186]: https://arxiv.org/abs/2305.11202
[resource-187]: https://arxiv.org/abs/2604.02666
[resource-188]: https://github.com/joshddrossman/LLMforIO
[resource-189]: https://doi.org/10.1287/ijds.2025.0074
[resource-190]: https://arxiv.org/abs/2501.08406
[resource-191]: https://github.com/li-group/OptiChat
[resource-192]: https://arxiv.org/abs/2601.00121
[resource-193]: https://doi.org/10.15439/2025F5420
[resource-194]: https://annals-csis.org/Volume_43/drp/5420.html
[resource-195]: https://arxiv.org/abs/2406.10958
[resource-196]: https://huggingface.co/datasets/BTBUzhy/JOC
[resource-197]: https://aclanthology.org/2024.naacl-industry.42/
[resource-198]: https://arxiv.org/abs/2407.07924
[resource-199]: https://opt.alibabacloud.com/chat
[resource-200]: https://opt.aliyun.com/chat
[resource-201]: https://arxiv.org/abs/2405.06697
[resource-202]: https://arxiv.org/abs/2307.03875
[resource-203]: https://arxiv.org/abs/2605.11813
[resource-204]: https://arxiv.org/abs/2511.11576
[resource-205]: https://arxiv.org/abs/2502.10557
[resource-206]: https://github.com/drzekunguo/LLM_Agent_Power_System_Balance
[resource-207]: https://arxiv.org/abs/2508.17200
[resource-208]: https://github.com/Amirreza-96/LLM-SO-manuscript
[resource-209]: https://doi.org/10.1145/3786181.3788711
[resource-210]: https://arxiv.org/abs/2508.07468
[resource-211]: https://github.com/szeider/agentic-python-coder
[resource-212]: https://doi.org/10.5281/zenodo.21361220
[resource-213]: https://arxiv.org/abs/2605.01675
[resource-214]: https://github.com/Yuliang795/LLMs-CP-CPSynC
[resource-215]: https://arxiv.org/abs/2608.00015
[resource-216]: https://arxiv.org/abs/2604.12955
[resource-217]: https://github.com/skadio/text2model
[resource-218]: https://huggingface.co/datasets/skadio/text2zinc
[resource-219]: https://huggingface.co/spaces/skadio/text2zinc-editor
[resource-220]: https://huggingface.co/spaces/skadio/text2model-leaderboard
[resource-221]: https://pypi.org/project/text2model/
[resource-222]: https://arxiv.org/abs/2509.08970
[resource-223]: https://skadio.github.io/text2model/
[resource-224]: https://arxiv.org/abs/2308.01589
[resource-225]: https://arxiv.org/abs/2507.11737
[resource-226]: https://arxiv.org/abs/2602.03318
[resource-227]: https://arxiv.org/abs/2602.19439
[resource-228]: https://proceedings.mlr.press/v306/ao26a.html
[resource-229]: https://arxiv.org/abs/2601.21008
[resource-230]: https://github.com/Archer222arc/ORLoopBench
[resource-231]: https://proceedings.iclr.cc/paper_files/paper/2025/hash/a48e5877c7bf86a513950ab23b360498-Abstract-Conference.html
[resource-232]: https://arxiv.org/abs/2502.09994
[resource-233]: https://github.com/Forrest-Stone/EOR
[resource-234]: https://arxiv.org/abs/2508.03406
[resource-235]: https://github.com/Ahalikai/MOID-Diagnosis
[resource-236]: https://arxiv.org/abs/2308.12923
[resource-237]: https://doi.org/10.1080/03155986.2024.2385189
[resource-238]: https://arxiv.org/abs/2605.11738
[resource-239]: https://aclanthology.org/2026.findings-acl.150/
[resource-240]: https://arxiv.org/abs/2604.21510
[resource-241]: https://github.com/Waichenbxx/OptiVerse
[resource-242]: https://huggingface.co/datasets/Waicheng/OptiVerse
[resource-243]: https://proceedings.mlr.press/v306/zhang26cb.html
[resource-244]: https://arxiv.org/abs/2510.05115
[resource-245]: https://github.com/Forrest-Stone/SAC-Opt
[resource-246]: https://aclanthology.org/2026.findings-emnlp.1886/
[resource-247]: https://arxiv.org/abs/2609.00728
[resource-248]: https://github.com/baranwa2/SOVER
[resource-249]: https://huggingface.co/datasets/humainlab/EquivaFormulation
[resource-250]: https://proceedings.mlr.press/v306/rahman26a.html
[resource-251]: https://arxiv.org/abs/2607.20474
[resource-252]: https://icml.cc/virtual/2026/poster/65537
[resource-253]: https://github.com/suabar/VeriSimple
[resource-254]: https://proceedings.mlr.press/v267/zhai25a.html
[resource-255]: https://arxiv.org/abs/2502.14760
[resource-256]: https://github.com/HumainLab/EquivaMap
[resource-257]: https://arxiv.org/abs/2510.27610
[resource-258]: https://icml.cc/virtual/2026/68291
[resource-259]: https://aclanthology.org/2026.findings-emnlp.1787/
[resource-260]: https://arxiv.org/abs/2606.04816
[resource-261]: https://github.com/ccccziiii/VRPBench
[resource-262]: https://arxiv.org/abs/2607.16646
[resource-263]: https://arxiv.org/abs/2605.27630
[resource-264]: https://arxiv.org/abs/2602.15983
[resource-265]: https://neurips.cc/virtual/2026/poster/153462
[resource-266]: https://github.com/junbolian/ReLoop
[resource-267]: https://huggingface.co/datasets/Jacoblian/RetailOpt-190
[resource-268]: https://arxiv.org/abs/2604.01455
[resource-269]: https://drive.google.com/drive/folders/1P7ixNFALdlZHyGm3vc8eGNRy8681W2jY?usp=drive_link
[resource-270]: https://arxiv.org/abs/2607.26710
[resource-271]: https://github.com/JAVA-Jiang/PowerAtlas
[resource-272]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/f0c6c93e1dbff84daf6082fef7e1a094-Abstract-Conference.html
[resource-273]: https://arxiv.org/abs/2509.16865
[resource-274]: https://github.com/Summer142857/LLMCoSolver
[resource-275]: https://drive.google.com/drive/folders/1bE1coGUa00gfuMkPXnfvldi1-WHGNnEb?usp=sharing
[resource-276]: https://drive.google.com/drive/folders/1VN9crftdW7DTsMQupbc06u6PzRT-Bwnx?usp=sharing
[resource-277]: https://doi.org/10.1017/pds.2025.10234
[resource-278]: https://arxiv.org/abs/2411.12571
[resource-279]: https://arxiv.org/abs/2503.01877
[resource-280]: https://github.com/starjob42/Starjob
[resource-281]: https://huggingface.co/datasets/mideavalwisard/Starjob
[resource-282]: https://arxiv.org/abs/2501.11968
[resource-283]: https://arxiv.org/abs/2409.04464
[resource-284]: https://arxiv.org/abs/2605.17036
[resource-285]: https://arxiv.org/abs/2505.12501
[resource-286]: https://arxiv.org/abs/2508.01724
[resource-287]: https://arxiv.org/abs/2407.11384
[resource-288]: https://github.com/zefang-liu/InvAgent
[resource-289]: https://aclanthology.org/2024.emnlp-industry.104/
[resource-290]: https://arxiv.org/abs/2402.07204
[resource-291]: https://github.com/YihongT/ITINERA
[resource-292]: https://aclanthology.org/2026.findings-acl.1417/
[resource-293]: https://arxiv.org/abs/2506.10764
[resource-294]: https://arxiv.org/abs/2605.08904
[resource-295]: https://github.com/OliverLeeXZ/OPT-BENCH
[resource-296]: https://huggingface.co/datasets/OPT-Bench/OPT-Bench
[resource-297]: https://proceedings.iclr.cc/paper_files/paper/2024/hash/3339f19c5fcee3ad74502947a32be9e6-Abstract-Conference.html
[resource-298]: https://arxiv.org/abs/2309.03409
[resource-299]: https://github.com/google-deepmind/opro
[resource-300]: https://proceedings.mlr.press/v306/chen26hb.html
[resource-301]: https://icml.cc/virtual/2026/poster/64869
[resource-302]: https://arxiv.org/abs/2604.24043
[resource-303]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/b9c91701ff28d480f186e4643e71ad11-Abstract-Conference.html
[resource-304]: https://iclr.cc/virtual/2026/poster/10010957
[resource-305]: https://arxiv.org/abs/2510.16701
[resource-306]: https://github.com/ZHANG-NI/AFL.git
[resource-307]: https://arxiv.org/abs/2609.08071
[resource-308]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/75ed738c083f8941cfc990245e4f6265-Abstract-Conference.html
[resource-309]: https://arxiv.org/abs/2505.12285
[resource-310]: https://github.com/whxru/CALM
[resource-311]: https://journal.iberamia.org/index.php/intartif/article/view/2584
[resource-312]: https://doi.org/10.4114/intartif.vol29iss77pp108-132
[resource-313]: https://arxiv.org/abs/2503.10968
[resource-314]: https://github.com/camilochs/comb-opt-for-all
[resource-315]: https://camilochs.github.io/comb-opt-for-all/
[resource-316]: https://arxiv.org/abs/2603.27628
[resource-317]: https://arxiv.org/abs/2610.17379
[resource-318]: https://arxiv.org/abs/2609.00023
[resource-319]: https://conference.cs.cityu.edu.hk/icist/program/ICIST%202026%20Program%20v3.pdf
[resource-320]: https://github.com/Mriya0306/ES-AHD
[resource-321]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/be36e50757bf9cd280aa74f89a7d1c23-Abstract-Conference.html
[resource-322]: https://arxiv.org/abs/2508.13333
[resource-323]: https://github.com/Challenger-XJTU/HiFo-Prompt
[resource-324]: https://arxiv.org/abs/2605.00369
[resource-325]: https://arxiv.org/abs/2602.16038
[resource-326]: https://arxiv.org/abs/2605.17137
[resource-327]: https://www.lion20.org/papers/
[resource-328]: https://github.com/cheikh025/LHS
[resource-329]: https://doi.org/10.1109/tevc.2026.3656374
[resource-330]: https://arxiv.org/abs/2403.01131
[resource-331]: https://github.com/MetaEvo/LLaMoCo
[resource-332]: https://huggingface.co/steven-0419/LLaMoCo
[resource-333]: https://arxiv.org/abs/2601.00770
[resource-334]: https://arxiv.org/abs/2606.14202
[resource-335]: https://github.com/Qzs1335/MeEvo
[resource-336]: https://doi.org/10.1016/j.eswa.2026.133022
[resource-337]: https://arxiv.org/abs/2507.20541
[resource-338]: https://doi.org/10.1609/aaai.v40i43.41024
[resource-339]: https://arxiv.org/abs/2507.20923
[resource-340]: https://github.com/langkhachhoha/MPaGE
[resource-341]: https://proceedings.mlr.press/v306/gungordu26a.html
[resource-342]: https://arxiv.org/abs/2601.20539
[resource-343]: https://github.com/oguzhangungordu/PathWise
[resource-344]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/7886b9bafe76c52fd568db10ff9772df-Abstract-Conference.html
[resource-345]: https://arxiv.org/abs/2509.19349
[resource-346]: https://github.com/SakanaAI/ShinkaEvolve
[resource-347]: https://arxiv.org/abs/2601.21239
[resource-348]: https://arxiv.org/abs/2502.15359
[resource-349]: https://github.com/Ahalikai/ARS-Routbench
[resource-350]: https://arxiv.org/abs/2503.03350
[resource-351]: https://github.com/nico-koltermann/contextual-evolution-of-heuristics
[resource-352]: https://arxiv.org/abs/2509.18108
[resource-353]: https://github.com/TBU-AILab/EASE
[resource-354]: https://github.com/TBU-AILab/frontEASE
[resource-355]: https://arxiv.org/abs/2507.17211
[resource-356]: https://arxiv.org/abs/2506.12495
[resource-357]: https://arxiv.org/abs/2506.15196
[resource-358]: https://github.com/microsoft/HeurAgenix
[resource-359]: https://huggingface.co/datasets/VictorYXL/HeurAgenixDataset
[resource-360]: https://doi.org/10.1609/aaai.v39i25.34898
[resource-361]: https://arxiv.org/abs/2412.14995
[resource-362]: https://github.com/datphamvn/HSEvo
[resource-363]: https://arxiv.org/abs/2506.00490
[resource-364]: https://doi.org/10.1109/CEC65147.2025.11043025
[resource-365]: https://scholars.cityu.edu.hk/en/publications/llm-driven-neighborhood-search-for-efficient-heuristic-design/
[resource-366]: https://github.com/Optima-CityU/LLM4AD/tree/main/llm4ad/method/lhns
[resource-367]: https://arxiv.org/abs/2405.20132
[resource-368]: https://github.com/XAI-liacs/LLaMEA
[resource-369]: https://arxiv.org/abs/2510.24013
[resource-370]: https://github.com/ibrahimoguzc/DiscoverHeuristics
[resource-371]: https://proceedings.mlr.press/v267/zheng25o.html
[resource-372]: https://arxiv.org/abs/2501.08603
[resource-373]: https://github.com/zz1358m/MCTS-AHD-master
[resource-374]: https://doi.org/10.1609/aaai.v39i25.34922
[resource-375]: https://arxiv.org/abs/2409.16867
[resource-376]: https://github.com/Optima-CityU/LLM4AD
[resource-377]: https://iclr.cc/virtual/2025/33144
[resource-378]: https://github.com/Fsoft-AIC/NCO-LLM
[resource-379]: https://arxiv.org/abs/2505.20242
[resource-380]: https://arxiv.org/abs/2512.03762
[resource-381]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/57f2d605790f01cc2d89699b0bf3b33e-Abstract-Conference.html
[resource-382]: https://arxiv.org/abs/2506.11057
[resource-383]: https://github.com/Y-Palver/L2O-STRCMP
[resource-384]: https://proceedings.mlr.press/v235/liu24bs.html
[resource-385]: https://arxiv.org/abs/2401.02051
[resource-386]: https://github.com/FeiLiu36/EoH
[resource-387]: https://proceedings.neurips.cc/paper_files/paper/2024/hash/4ced59d480e07d290b6f29fc8798f195-Abstract-Conference.html
[resource-388]: https://arxiv.org/abs/2402.01145
[resource-389]: https://github.com/ai4co/reevo
[resource-390]: https://arxiv.org/abs/2311.15249
[resource-391]: https://doi.org/10.1038/s41586-023-06924-6
[resource-392]: https://github.com/google-deepmind/funsearch
[resource-393]: https://arxiv.org/abs/2602.23092
[resource-394]: https://arxiv.org/abs/2603.06996
[resource-395]: https://github.com/Shaohua-Yu/LLM-ALNS
[resource-396]: https://arxiv.org/abs/2602.08253
[resource-397]: https://github.com/zboyn/G-LNS
[resource-398]: https://neurips.cc/virtual/2026/poster/150513
[resource-399]: https://doi.org/10.65109/ISFV2587
[resource-400]: https://arxiv.org/abs/2604.07872
[resource-401]: https://ifaamas.org/Proceedings/aamas2026/forms/contents.htm
[resource-402]: https://arxiv.org/abs/2607.23676
[resource-403]: https://arxiv.org/abs/2609.31179
[resource-404]: https://openreview.net/forum?id=2cYbzycSbz
[resource-405]: https://arxiv.org/abs/2510.07073
[resource-406]: https://github.com/ai4co/vrpagent
[resource-407]: https://proceedings.mlr.press/v267/ye25j.html
[resource-408]: https://github.com/thuiar/LLM-LNS
[resource-409]: https://arxiv.org/abs/2503.03239
[resource-410]: https://github.com/SHIXOOM/PAIR
[resource-411]: https://arxiv.org/abs/2608.07407
[resource-412]: https://github.com/Shuvomoy/AutoOPT
[resource-413]: https://github.com/Shuvomoy/AutoOPT/tree/main/Skills
[resource-414]: https://github.com/Shuvomoy/AutoOPT/tree/main/Lean-Related
[resource-415]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/c1e67cde895c3c91edb43569ad0df260-Abstract-Conference.html
[resource-416]: https://arxiv.org/abs/2505.20881
[resource-417]: https://github.com/yiding-s/MoH
[resource-418]: https://drive.google.com/file/d/1e4T8Yiz-qvHcChys2Tk841pbXumGVYu2/view?usp=sharing
[resource-419]: https://arxiv.org/abs/2506.13131
[resource-420]: https://github.com/google-deepmind/alphaevolve_results
[resource-421]: https://github.com/google-deepmind/alphaevolve_repository_of_problems
[resource-422]: https://doi.org/10.24963/ijcai.2026/736
[resource-423]: https://github.com/BeeeeenWANG/LLM-guided-cutting-plane-management
[resource-424]: https://arxiv.org/abs/2607.18252
[resource-425]: https://arxiv.org/abs/2508.11850
[resource-426]: https://github.com/milad1378yz/EvoCut
[resource-427]: https://github.com/milad1378yz/sage
[resource-428]: https://arxiv.org/abs/2609.36735
[resource-429]: https://arxiv.org/abs/2610.22861
[resource-430]: https://proceedings.mlr.press/v306/hou26d.html
[resource-431]: https://arxiv.org/abs/2605.10401
[resource-432]: https://github.com/hzn18/LLM4Branch
[resource-433]: https://arxiv.org/abs/2606.23299
[resource-434]: https://neurips.cc/virtual/2026/171741
[resource-435]: https://arxiv.org/abs/2607.25956
[resource-436]: https://arxiv.org/abs/2412.12038
[resource-437]: https://doi.org/10.1007/978-3-031-95976-9_4
[resource-438]: https://github.com/OptiMUS-optimization-modeling/LLM-Solver-Configuration
[resource-439]: https://arxiv.org/abs/2502.18540
[resource-440]: https://aclanthology.org/2025.emnlp-main.973/
[resource-441]: https://github.com/ZIKEYUAN/MA-GTS
[resource-442]: https://aclanthology.org/2026.emnlp-main.221/
[resource-443]: https://arxiv.org/abs/2608.23353
[resource-444]: https://github.com/Xyz-yuanhf/formuevo
[resource-445]: https://arxiv.org/abs/2605.09186
[resource-446]: https://www.nature.com/articles/s41467-026-74949-2
[resource-447]: https://arxiv.org/abs/2507.22876
[resource-448]: https://doi.org/10.5281/zenodo.17856395
[resource-449]: https://doi.org/10.5281/zenodo.17856423
[resource-450]: https://doi.org/10.1613/jair.1.20499
[resource-451]: https://arxiv.org/abs/2402.10705
[resource-452]: https://github.com/YiwenAI/AutoSAT
[resource-453]: https://arxiv.org/abs/2507.15615
[resource-454]: https://arxiv.org/abs/2605.12421
[resource-455]: https://neurips.cc/virtual/2026/173061
[resource-456]: https://arxiv.org/abs/2607.16777
[resource-457]: https://huggingface.co/datasets/cyberagent/JOR-Bench
[resource-458]: https://proceedings.mlr.press/v306/li26dz.html
[resource-459]: https://arxiv.org/abs/2602.10450
[resource-460]: https://github.com/optsuite/MIPLIB-NL
[resource-461]: https://github.com/optsuite/MIPLIB-NL/tree/main/dataset
[resource-462]: https://neurips.cc/virtual/2026/poster/139697
[resource-463]: https://arxiv.org/abs/2605.12154
[resource-464]: https://proceedings.mlr.press/v306/chen26o.html
[resource-465]: https://arxiv.org/abs/2601.19924
[resource-466]: https://github.com/Cardinal-Operations/OPTEngine
[resource-467]: https://huggingface.co/datasets/chenyitian-shanshu/OPTEngine
[resource-468]: https://proceedings.mlr.press/v306/shen26h.html
[resource-469]: https://icml.cc/virtual/2026/poster/63658
[resource-470]: https://arxiv.org/abs/2602.03070
[resource-471]: https://github.com/shenchao188/ProOPF-Benchamrk-Dataset
[resource-472]: https://arxiv.org/abs/2506.06052v2
[resource-473]: https://arxiv.org/abs/2506.06052
[resource-474]: https://doi.org/10.3233/faia250890
[resource-475]: https://github.com/DCP-Bench/DCP-Bench-Open
[resource-476]: https://huggingface.co/datasets/kostis-init/CP-Bench
[resource-477]: https://github.com/kostis-init/CP-Bench
[resource-478]: https://arxiv.org/abs/2405.13144
[resource-479]: https://aclanthology.org/2025.findings-naacl.146/
[resource-480]: https://github.com/FreedomIntelligence/Mamo
[resource-481]: https://huggingface.co/datasets/CardinalOperations/MAMO
[resource-482]: https://ojs.aaai.org/index.php/AAAI/article/view/34673
[resource-483]: https://arxiv.org/abs/2412.17874
[resource-484]: https://github.com/nl4opt/ORQA
[resource-485]: https://arxiv.org/abs/2503.10642
[resource-486]: https://apexapps.oracle.com/pls/apex/f?p=LABS%3A0%3A108770064556151%3AAPPLICATION_PROCESS%3DGETDOC_INLINE%3A%3A%3ADOC_ID%3A4780
[resource-487]: https://labs.oracle.com/pls/apex/f?p=94065%3A10%3A18082377147334%3A11529
[resource-488]: https://proceedings.mlr.press/v220/ramamonjison23a.html
[resource-489]: https://arxiv.org/abs/2303.08233
[resource-490]: https://arxiv.org/abs/2602.22465
[resource-491]: https://proceedings.mlr.press/v306/cao26z.html
[resource-492]: https://arxiv.org/abs/2605.27566
[resource-493]: https://github.com/dsbx7/DynaSchedBench
[resource-494]: https://dsbx7.github.io/
[resource-495]: https://arxiv.org/abs/2602.12631
[resource-496]: https://github.com/TianyiPeng/InventoryBench
[resource-497]: https://github.com/TianyiPeng/AI-human-inventory-game
[resource-498]: https://aclanthology.org/2026.findings-acl.1529/
[resource-499]: https://arxiv.org/abs/2602.02188
[resource-500]: https://github.com/jing12e/nlco
[resource-501]: https://huggingface.co/datasets/summer142857jiang/NLCO
[resource-502]: https://arxiv.org/abs/2603.23004
[resource-503]: https://arxiv.org/abs/2603.16453
[resource-504]: https://github.com/linghuazhang01/RetailBench
[resource-505]: https://arxiv.org/abs/2508.11416
[resource-506]: https://ojs.aaai.org/index.php/AAAI/article/view/40596
[resource-507]: https://arxiv.org/abs/2504.04310
[resource-508]: https://github.com/sunnweiwei/CO-Bench
[resource-509]: https://huggingface.co/datasets/CO-Bench/CO-Bench
[resource-510]: https://neurips.cc/virtual/2026/poster/139096
[resource-511]: https://arxiv.org/abs/2605.25246
[resource-512]: https://github.com/Minw913/FrontierOR
[resource-513]: https://huggingface.co/datasets/frontieror/FrontierOR
[resource-514]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/2e49934cac6cb8604b0c67cfa0828718-Abstract-Conference.html
[resource-515]: https://arxiv.org/abs/2506.07972
[resource-516]: https://github.com/cornell-zhang/heurigym
[resource-517]: https://cornell-zhang.github.io/heurigym/
[resource-518]: https://doi.org/10.1016/j.cor.2026.107603
[resource-519]: https://arxiv.org/abs/2512.13374
[resource-520]: https://doi.org/10.5281/zenodo.21891840
[resource-521]: https://doi.org/10.1007/978-3-031-90065-5_24
[resource-522]: https://arxiv.org/abs/2501.11411
[resource-523]: https://zenodo.org/records/14162744
[resource-524]: https://doi.org/10.1145/3712255.3734347
[resource-525]: https://arxiv.org/abs/2504.20183
[resource-526]: https://github.com/XAI-liacs/BLADE
[resource-527]: https://arxiv.org/abs/2504.19636
[resource-528]: https://arxiv.org/abs/2507.03605
[resource-529]: https://doi.org/10.5281/zenodo.15675581
[resource-530]: https://arxiv.org/abs/2509.02297
[resource-531]: https://github.com/quangr/EoH
[resource-532]: https://arxiv.org/abs/2607.10768
[resource-533]: https://arxiv.org/abs/2605.28158
[resource-534]: https://github.com/0xzhouchenyu/OR-Space
[resource-535]: https://huggingface.co/datasets/Chenyu-Zhou/OR-Space
[resource-536]: https://arxiv.org/abs/2606.19787
[resource-537]: https://github.com/ORAgentBench/ORAgentBench
[resource-538]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/1ddd6c6909c2a7acf877ce0f84abf6eb-Abstract-Conference.html
[resource-539]: https://arxiv.org/abs/2505.14148
[resource-540]: https://doi.org/10.52202/085713-0704
[resource-541]: https://github.com/usail-hkust/LLM-MM-Agent
[resource-542]: https://github.com/luckyfan-cs/mm-agent-expert
[resource-543]: https://huggingface.co/spaces/MathematicalModelingAgent/MathematicalModelingAgent
[resource-544]: https://aclanthology.org/2025.findings-emnlp.85/
[resource-545]: https://arxiv.org/abs/2505.15068
[resource-546]: https://github.com/qiancheng0/ModelingAgent
[resource-547]: https://arxiv.org/abs/2510.16943
[resource-548]: https://doi.org/10.1109/PESGM52009.2025.11225826
[resource-549]: https://arxiv.org/abs/2407.05365
[resource-550]: https://github.com/xiyuan-zhou/ElecBench-a-Power-Dispatch-Evaluation-Benchmark-for-Large-Language-Models
[resource-551]: https://aclanthology.org/2024.lrec-main.1438/
[resource-552]: https://proceedings.iclr.cc/paper_files/paper/2025/hash/dc594b8712f5d3ea1904092d74739d25-Abstract-Conference.html
[resource-553]: https://arxiv.org/abs/2410.08288
[resource-554]: https://github.com/microsoft/OptiGuide/tree/main/milp-evolve
[resource-555]: https://huggingface.co/datasets/microsoft/MILP-Evolve
[resource-556]: https://github.com/microsoft/MILP-Evolve
[resource-557]: https://arxiv.org/abs/2412.17287
[resource-558]: https://arxiv.org/abs/2604.04383
[resource-559]: https://arxiv.org/abs/2502.00828
[resource-560]: https://github.com/Yoontae6719/Decision-informed-Neural-Networks-with-Large-Language-Model-Integration-for-Portfolio-Optimization
[resource-561]: https://arxiv.org/abs/2504.14345
[resource-562]: https://advancesinfinancialai.com/#accepted-paper
[resource-563]: https://github.com/youngandbin/LLM-BLM
[resource-564]: https://arxiv.org/abs/2508.14410v3
[resource-565]: https://arxiv.org/abs/2310.06116
[resource-566]: https://arxiv.org/abs/2407.19633
[resource-567]: https://github.com/ai4co/awesome-fm4co
