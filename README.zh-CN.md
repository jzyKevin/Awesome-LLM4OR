# Awesome LLM4OR

[English](README.md) | **简体中文**

A curated collection of papers, benchmarks, datasets, models, and tools for **Large Language Models for Operations Research**.

系统整理 LLM 在运筹优化中的研究：从自然语言建模与求解器代码，到算法设计、Agent、模型训练和评测验证。论文、代码、模型与数据入口直接列在本页；“详情”跳转到本页的作者、版本与资源说明。

**更新：2026-10-25 · 收录 235 篇论文。** 同一篇论文可跨多个模块展示，论文总数按唯一 ID 去重。

**如何阅读：** “方法 · 基准 · 数据 · 模型”等表示论文实际提出的贡献，可同时出现；贡献类型不代表对应资源一定已公开。例如 ORLM 同时提供训练方法、IndustryOR 基准、数据与领域模型；它会出现在建模、训练和基准等相关模块。仅展示已确认关联的资源；第三方镜像与相关资源另有文字标记。未找到或未确认的资源省略，独立资源栏以 `-` 表示。

**阅读层级：** “核心”标记代表性方法、基础工作或重要评测资源；“探索性”标记开放式数学建模等邻近研究；其余为补充工作。层级用于阅读筛选，不是论文质量排名，参见[分类与阅读说明](#classification)。

[作者与版本](#paper-info) · [分类与阅读说明](#classification)

<a id="contents"></a>

## 目录

- [入门阅读路线](#start-here)
- [模型、数据与基准入口](#resources)
- [问题理解与数学建模](#modeling)（115 篇）
- [优化代码生成、执行与修复](#code)（88 篇）
- [求解器增强与算法设计](#algorithms)（94 篇）
- [OR Agents 与端到端系统](#agents)（91 篇）
- [数据合成与模型训练](#training)（62 篇）
- [推理、搜索与验证](#verification)（48 篇）
- [Benchmarks、数据集与评测](#benchmarks)（109 篇）
- [运筹优化应用](#applications)（59 篇）
- [综述与基础资源](#surveys)（15 篇）
- [邻近方向与算法发现](#adjacent)（50 篇）
- [作者、版本与资源说明](#paper-info)
- [分类与阅读说明](#classification)
- [收录与贡献](#contributing)

<a id="start-here"></a>

## 入门阅读路线

| 阅读目的 | 代表工作 |
|---|---|
| 了解领域全貌 | [LLM4OR Survey](#paper-xiao2025survey) → [LLM4AD Survey](#paper-liu2024systematic) |
| 理解任务与评测 | [NL4Opt](#paper-ramamonjison2023nl4opt) → [Mamo](#paper-huang2024mamo) → [EquivaMap](#paper-zhai2025equivamap) |
| 从描述到模型与求解器 | [Chain-of-Experts](#paper-xiao2024coe) → [OptiMUS](#paper-teshnizi2024optimus) → [OptiGuide](#paper-li2023optiguide) |
| 数据合成与领域训练 | [ORLM](#paper-huang2025orlm) → [OptMATH](#paper-lu2025optmath) → [SIRL](#paper-chen2025sirl) |
| 算法与启发式自动设计 | [FunSearch](#paper-romera2023funsearch) → [EoH](#paper-liu2024eoh) → [ReEvo](#paper-ye2024reevo) |

<a id="resources"></a>

## 模型、数据与基准入口

同一论文的训练数据、评测基准和模型分别列出；数据在 GitHub 发布时同样提供入口。模型表包含论文训练的模型，未公开或未确认下载入口时为 `-`；基座模型不作为论文权重入口。未公开下载入口的基准保留名称，不据此推断数据已发布。

[模型与权重](#model-weights) · [评测基准](#evaluation-benchmarks) · [训练数据](#training-data) · [修订评测数据](#evaluation-data) · [技能库](#skills)

<a id="model-weights"></a>

### 模型与权重

| 资源名称 | 关联论文 | 获取入口 |
|---|---|---|
| AI-Copilot 微调模型（未核到权重入口） | [AI-Copilot for Business Optimisation](#paper-alahakoon2023copilot) | - |
| Human Imitator | [Ask, Clarify, Optimize](#paper-askclarify2026) | - |
| AutoOR 8B | [AutoOR](#paper-autoor2026) | - |
| CALM 共同演化模型 | [CALM (Algorithm–LM Co-evolution)](#paper-huang2025calm) | - |
| STORM 4B | [CALM / STORM](#paper-calm2025storm) | - |
| 经领域微调的 CodeT5 | [CodeT5 Mathematical Program Synthesis](#paper-synth2023) | - |
| VRPCoder（权重入口未找到） | [Constraint Injection / VRPCoder](#paper-constraintinjection2026) | - |
| DPLM 7B | [DPLM / DP-Bench](#paper-dpdlm2025) | - |
| DScheLLM 微调模型（未核到权重入口） | [DScheLLM](#paper-zhang2026dschellm) | - |
| EPOCH 经过偏好优化的生成器 | [EPOCH](#paper-epoch2026) | - |
| EVOM 建模模型（权重入口未找到） | [EVOM](#paper-guan2026evom) | - |
| EvoOpt-LLM LoRA 模型 | [EvoOpt-LLM](#paper-he2026evoopt) | - |
| EvoOptiGraph 建模模型 | [EvoOptiGraph](#paper-evooptigraph2026) | - |
| HeurAgenix 微调选择器 | [HeurAgenix](#paper-yang2025heuragenix) | - |
| 不可行性感知 8B 模型 | [Infeasibility-Aware CO Models](#paper-infeasibilityaware2026) | - |
| LLaMoCo-S（CodeGen 350M） | [LLaMoCo](#paper-ma2024llamoco) | [![HF Weights][badge-001]][resource-001] |
| LLMCoSolver 微调模型 | [LLMCoSolver / E2E CO Solver](#paper-jiang2025e2eco) | - |
| LLMOPT-Qwen2.5-14B（后续发布） | [LLMOPT](#paper-jiang2025llmopt) | [![HF Model][badge-002]][resource-002] |
| LM4OPT 微调小模型 | [LM4OPT](#paper-ahmed2024lm4opt) | - |
| MIND 建模模型（未核到权重入口） | [MIND](#paper-mind2026) | - |
| MiniOpt 领域模型 | [MiniOpt](#paper-zhao2026miniopt) | - |
| 多仓公式选择 LLM（未核到权重入口） | [Multi-Warehouse Formulation Selection](#paper-warehouseformsel2026) | - |
| LEHD-LLM / POMO-LLM（神经路由策略） | [NCO-LLM for VRP](#paper-tran2025llmneural) | - |
| ner4opt-roberta-v1 | [Ner4Opt](#paper-dakle2023ner4opt) | [![HF Model][badge-002]][resource-003] |
| ner4opt-roberta-v2 | [Ner4Opt](#paper-dakle2023ner4opt) | [![HF Model][badge-002]][resource-004] |
| Opt-Miner-Qwen3-8B | [Opt-Miner](#paper-optminer2026) | - |
| OptiMind-SFT | [OptiMind](#paper-zhang2025optimind) | [![HF Model][badge-002]][resource-005] |
| OptiRepair P1 8B（可行性修复） | [OptiRepair](#paper-optirepair2026) | - |
| OptiRepair P2 8B（运营合理性修复） | [OptiRepair](#paper-optirepair2026) | - |
| OptiTrust 建模模型（未核到权重入口） | [OptiTrust](#paper-lima2025optitrust) | - |
| OptLLM Qwen-SFT | [OptLLM](#paper-zhang2024optllm) | - |
| OptMATH Qwen2.5 7B / 32B | [OptMATH](#paper-lu2025optmath) | [![Model 7B][badge-003]][resource-006] · [![Model 32B][badge-004]][resource-007] |
| OR-PRM（Qwen2.5-7B-Coder，SFT + DPO） | [OR-PRM](#paper-wang2026orprm) | - |
| OR-R1 微调模型 | [OR-R1](#paper-ding2026orr1) | - |
| ORLM-LLaMA-3-8B | [ORLM](#paper-huang2025orlm) | [![HF Model][badge-002]][resource-008] |
| Qwen3-8B-OM（SFT / GRPO / Curriculum） | [ORLoopBench](#paper-ao2026orloopbench) | - |
| OR-Debug PRM（Qwen3-8B LoRA） | [ORLoopBench](#paper-ao2026orloopbench) | - |
| PALL 8B LNS 选择器 | [PALL](#paper-yan2026pall) | - |
| PEARL-Qwen3-4B-Instruct-2507 | [PEARL](#paper-lu2026pearl) | [![HF Model][badge-002]][resource-009] |
| PowerAtlas 微调模型 | [PowerAtlas / ECBench](#paper-jiang2026poweratlas) | - |
| SAGE 学生模型 | [SAGE (Strategy-Aware Modeling)](#paper-strategyaware2026) | - |
| SDRL-Qwen3-4B | [SDRL](#paper-sdrl2026) | [![HF Weights][badge-001]][resource-010] |
| SDRL-Qwen3-32B（仅核到模型卡，无可见权重） | [SDRL](#paper-sdrl2026) | - |
| SIRL Gurobi / COPT 7B / 32B | [SIRL](#paper-chen2025sirl) | [![Model Gurobi-7B][badge-005]][resource-011] · [![Model COPT-7B][badge-006]][resource-012] · [![Model Gurobi-32B][badge-007]][resource-013] · [![Model COPT-32B][badge-008]][resource-014] |
| SOLID-Qwen3 | [SOLID](#paper-solid2026) | [![HF Model][badge-002]][resource-015] |
| SOLID-StepORLM | [SOLID](#paper-solid2026) | [![HF Model][badge-002]][resource-016] |
| SPO 角色化算子生成模型 | [SPO](#paper-spo2026) | - |
| Starjob LLaMA 8B（4-bit，LoRA） | [Starjob](#paper-abgaryan2025starjob) | - |
| Step-Opt（权重入口未找到） | [Step-Opt](#paper-wu2025stepopt) | - |
| StepORLM policy / GenPRM 8B | [StepORLM](#paper-zhou2026steporlm) | [![Policy 8B][badge-009]][resource-017] · [![GenPRM 8B][badge-010]][resource-018] |
| STRCMP 结构增强模型 | [STRCMP](#paper-li2025strcmp) | - |
| TTG 自然语言→符号翻译模型 | [To the Globe / TTG](#paper-ju2024ttg) | - |

<a id="evaluation-benchmarks"></a>

### 评测基准

| 资源名称 | 关联论文 | 获取入口 |
|---|---|---|
| AIM-Bench 库存实验 | [AIM-Bench](#paper-zhao2025aimbench) | - |
| RoutBench | [ARS / RoutBench](#paper-li2025ars) | [![GitHub][badge-011]][resource-019] |
| LPWP / NL4Opt 早期数据（1101 项） | [Auto-formulation (2022)](#paper-ramamonjison2022augmenting) | [![GitHub Data][badge-012]][resource-020] |
| AutoRO-Bench | [AutoREM / AutoRO-Bench](#paper-robustreform2026) | - |
| BLADE | [BLADE](#paper-vanstein2025blade) | [![GitHub Suite][badge-013]][resource-021] |
| StructuredOR | [BPP-Search / StructuredOR](#paper-wang2025bppsearch) | [![HF Data][badge-014]][resource-022] |
| ComplexOR（仓库原始版） | [Chain-of-Experts](#paper-xiao2024coe) | [![GitHub][badge-011]][resource-023] |
| NL4Opt-Code（Gurobi 标注扩展） | [CHORUS](#paper-lporch2025) | - |
| R2C 规则建模评测集（描述性名称） | [CIR / R2C](#paper-canonicalir2026) | - |
| CO-Bench | [CO-Bench](#paper-sun2026cobench) | [![HF Data][badge-014]][resource-024] |
| VRPBench | [Constraint Injection / VRPCoder](#paper-constraintinjection2026) | [![GitHub Data][badge-012]][resource-025] |
| ConstraintBench | [ConstraintBench](#paper-constraintbench2026) | - |
| CP-Bench（原版归档） | [CP-Bench / DCP-Bench-Open](#paper-michailidis2025cpbench) | [![HF Dataset][badge-015]][resource-026] |
| DCP-Bench-Open（扩展版） | [CP-Bench / DCP-Bench-Open](#paper-michailidis2025cpbench) | [![GitHub][badge-011]][resource-027] |
| CP-SynC Benchmark | [CP-SynC](#paper-cpsync2026) | [![GitHub Data & Evaluation][badge-016]][resource-028] |
| OptU | [DAOpt / OptU](#paper-daopt2025) | - |
| DP-Bench | [DPLM / DP-Bench](#paper-dpdlm2025) | - |
| DynaSchedBench | [DynaSchedBench](#paper-dynaschedbench2026) | [![GitHub Benchmark][badge-017]][resource-029] |
| ElecBench（公开测试子集） | [ElecBench](#paper-zhou2024elecbench) | [![GitHub Subset][badge-018]][resource-030] |
| EOR 工业解释评测集 | [EOR / Decision Information](#paper-zhang2025decisioninfo) | [![GitHub][badge-011]][resource-031] |
| EquivaFormulation | [EquivaMap](#paper-zhai2025equivamap) | [![HF Data][badge-014]][resource-032] |
| CP-SynC-XL | [Formalize, Don't Optimize](#paper-wang2026formalize) | - |
| FrontierOR-v1（2026-09-27 发布） | [FrontierOR](#paper-kong2026frontieror) | [![HF Dataset][badge-015]][resource-033] · [![Evaluation code][badge-019]][resource-034] |
| HeuriGym | [HeuriGym](#paper-chen2025heurigym) | [![GitHub Benchmark][badge-017]][resource-035] |
| InventoryBench | [InventoryBench](#paper-invbench2026) | [![GitHub][badge-011]][resource-036] |
| JOR-Bench（五组日译与英文对照） | [JOR-Bench](#paper-jorbench2026) | [![HF Dataset][badge-015]][resource-037] |
| Large-Scale-OR | [LEAN-LLM-OPT](#paper-liang2026leanllmopt) | [![GitHub：Test_Dataset][badge-020]][resource-038] |
| Air-NRM | [LEAN-LLM-OPT](#paper-liang2026leanllmopt) | [![GitHub：Test_Dataset][badge-020]][resource-038] |
| G-REAL | [MA-GTS / G-REAL](#paper-yuan2025magts) | [![GitHub][badge-011]][resource-039] |
| Mamo | [Mamo](#paper-huang2024mamo) | [![GitHub][badge-011]][resource-040] · [![HF 镜像（第三方字段适配）][badge-021]][resource-041] |
| MIPLIB-NL | [MIPLIB-NL](#paper-li2026miplibnl) | [![GitHub][badge-011]][resource-042] |
| MM-Bench（数学建模竞赛） | [MM-Agent / MM-Bench（数学建模）](#paper-liu2025mmagent) | [![GitHub Data][badge-012]][resource-043] |
| MM-OptBench | [MM-OptBench](#paper-zhu2026mmoptbench) | - |
| ModelingBench | [ModelingAgent / ModelingBench](#paper-qian2025modelingagent) | [![GitHub Data][badge-012]][resource-044] |
| 专家规格—Zimpl 优化建模评测集（描述性名称） | [Multi-Stage Modeling & Verification](#paper-mostajabdaveh2024multiagent) | - |
| NL4Opt | [NL4Opt](#paper-ramamonjison2023nl4opt) | [![GitHub][badge-011]][resource-020] |
| NLCO | [NLCO](#paper-jiang2026nlco) | [![HF Dataset][badge-015]][resource-045] · [![Code][badge-022]][resource-046] |
| OPT-BENCH | [OPT-BENCH / OPT-Agent](#paper-li2026optbench) | [![HF Dataset][badge-015]][resource-047] · [![Code][badge-022]][resource-048] |
| OPT-Engine / C³-Bench | [OPT-Engine](#paper-chen2026optengine) | [![HF Dataset][badge-015]][resource-049] · [![Evaluation code][badge-019]][resource-050] |
| OptArgus 幻觉检测评测套件 | [OptArgus](#paper-optarcus2026) | - |
| Opti-Agent-Bench | [Opti-Agent-Bench](#paper-optiagentbench2026) | - |
| OptiDSL 44 类 COP 评测集 | [OptiDSL](#paper-dslmilp2026) | - |
| NLP4LP | [OptiMUS](#paper-teshnizi2024optimus) | [![HF Data][badge-014]][resource-051] |
| OptiRepair-SC（976 项，含独立训练 / 测试划分） | [OptiRepair](#paper-optirepair2026) | - |
| OptiVerse | [OptiVerse / DVA-Agent](#paper-optiverse2026) | [![HF Dataset][badge-015]][resource-052] · [![Evaluation Code][badge-023]][resource-053] |
| OptMATH-Bench | [OptMATH](#paper-lu2025optmath) | [![GitHub][badge-011]][resource-054] |
| BWOR | [OR-LLM-Agent / BWOR](#paper-zhang2025bwor) | [![HF Dataset][badge-015]][resource-055] |
| OR-Space | [OR-Space](#paper-zhou2026orspace) | [![HF Dataset][badge-015]][resource-056] · [![Evaluation Code][badge-023]][resource-057] |
| ORAgentBench | [ORAgentBench](#paper-oragentbench2026) | [![GitHub Benchmark][badge-017]][resource-058] |
| Bench4Opt | [ORGEval / Bench4Opt](#paper-ding2026orgeval) | - |
| IndustryOR | [ORLM](#paper-huang2025orlm) | [![IndustryOR][badge-024]][resource-059] |
| ORDebug / OR-Debug-Bench | [ORLoopBench](#paper-ao2026orloopbench) | [![GitHub][badge-011]][resource-060] |
| ORBias / OR-Bias-Bench | [ORLoopBench](#paper-ao2026orloopbench) | [![GitHub][badge-011]][resource-060] |
| ORQA | [ORQA](#paper-mostajabdaveh2025orqa) | [![GitHub][badge-011]][resource-061] |
| LogiOR | [ORThought / LogiOR](#paper-yang2025orthought) | [![HF Data][badge-014]][resource-062] |
| ECBench（生成器与公开样例） | [PowerAtlas / ECBench](#paper-jiang2026poweratlas) | [![GitHub][badge-011]][resource-063] |
| ProOPF-B | [ProOPF](#paper-shen2026proopf) | [![GitHub：ProOPF_B][badge-025]][resource-064] |
| RetailOpt-190 | [ReLoop / RetailOpt-190](#paper-lian2026reloop) | [![HF Dataset][badge-015]][resource-065] |
| OptiBench | [ReSocratic / OptiBench](#paper-yang2025resocratic) | [![GitHub][badge-011]][resource-066] |
| RetailBench | [RetailBench](#paper-zhang2026retailbench) | [![GitHub Environment][badge-026]][resource-067] |
| NLEquiv-150 | [SOVER / NLEquiv-150](#paper-bhattacharyya2026sover) | [![GitHub Benchmark][badge-017]][resource-068] |
| Text2Zinc（复用既有基准） | [Text2Model](#paper-text2model2026) | [![HF Dataset][badge-015]][resource-069] |
| Text2Zinc | [Text2Zinc](#paper-singirikonda2025text2zinc) | [![HF Dataset][badge-015]][resource-069] |
| WIQOR（下载入口未核到） | [WIQOR](#paper-parashar2025wiqor) | - |

<a id="training-data"></a>

### 训练数据

| 资源名称 | 关联论文 | 获取入口 |
|---|---|---|
| AI-Copilot 排程训练样本 | [AI-Copilot for Business Optimisation](#paper-alahakoon2023copilot) | [![GitHub Data][badge-012]][resource-070] |
| AI-Copilot 工业案例训练样本 | [AI-Copilot for Business Optimisation](#paper-alahakoon2023copilot) | [![GitHub Case Data][badge-027]][resource-071] |
| AutoOR 合成训练数据 | [AutoOR](#paper-autoor2026) | - |
| CALM 纠正轨迹训练数据 | [CALM / STORM](#paper-calm2025storm) | - |
| DeepOR 种子与 SFT/RL 样例（非完整训练集） | [DeepOR](#paper-xiao2026deepor) | [![官方种子与样例数据][badge-028]][resource-072] |
| DualReflect 合成训练数据 | [DPLM / DP-Bench](#paper-dpdlm2025) | - |
| DScheLLM 快／慢思考训练数据（未核到下载入口） | [DScheLLM](#paper-zhang2026dschellm) | - |
| EvoOptiGraph 结构化合成训练实例 | [EvoOptiGraph](#paper-evooptigraph2026) | - |
| 不可行性感知图优化训练数据 | [Infeasibility-Aware CO Models](#paper-infeasibilityaware2026) | [![Author Archive（相关）][badge-029]][resource-073] |
| LLaMoCo 问题—优化代码指令集 | [LLaMoCo](#paper-ma2024llamoco) | - |
| LLMCoSolver SFT Data | [LLMCoSolver / E2E CO Solver](#paper-jiang2025e2eco) | [![SFT Data][badge-030]][resource-074] |
| LLMCoSolver RL Data | [LLMCoSolver / E2E CO Solver](#paper-jiang2025e2eco) | [![RL Data][badge-031]][resource-075] |
| MILP-Evolve | [MILP-Evolve](#paper-li2025milpevolve) | [![HF Data][badge-014]][resource-076] |
| MIND 局部错误训练语料 | [MIND](#paper-mind2026) | - |
| 扩展 NL4Opt 的 MILP 训练／测试材料 | [Multi-stage MILP Synthesis](#paper-li2023synthesizing) | [![GitHub Data][badge-012]][resource-077] |
| Opt-Miner 合成训练数据 | [Opt-Miner](#paper-optminer2026) | - |
| OptiTrust 合成训练示范 | [OptiTrust](#paper-lima2025optitrust) | - |
| OptLLM 中英建模训练语料 | [OptLLM](#paper-zhang2024optllm) | - |
| OptMATH-Train | [OptMATH](#paper-lu2025optmath) | [![HF Data][badge-014]][resource-078] |
| OR-ProcessQA | [OR-PRM](#paper-wang2026orprm) | - |
| OR-Instruct-Data-3K（公开子集） | [ORLM](#paper-huang2025orlm) | [![OR-Instruct-3K][badge-032]][resource-079] |
| ProOPF-D（公开 few-shot 示例） | [ProOPF](#paper-shen2026proopf) | [![GitHub：ProOPF_D，非全量][badge-033]][resource-064] |
| RAG 建模的 500 条合成检索示例 | [RAG for Optimization & CP Modeling](#paper-roy2026rag) | - |
| ReSocratic-29k | [ReSocratic / OptiBench](#paper-yang2025resocratic) | [![GitHub][badge-011]][resource-066] |
| SAGE 多策略 SFT 数据 | [SAGE (Strategy-Aware Modeling)](#paper-strategyaware2026) | [![HF Dataset][badge-015]][resource-080] |
| SDRL 文本／文件混合训练语料 | [SDRL](#paper-sdrl2026) | - |
| Starjob 训练集 | [Starjob](#paper-abgaryan2025starjob) | [![HF Dataset][badge-015]][resource-081] |
| Step-Opt-Instruct 训练数据 | [Step-Opt](#paper-wu2025stepopt) | [![GitHub：Step/Dataset][badge-034]][resource-082] |

<a id="evaluation-data"></a>

### 修订评测数据

| 资源名称 | 关联论文 | 获取入口 |
|---|---|---|
| Agora-Opt 修订并统一格式的既有 OR 评测数据 | [Agora-Opt](#paper-soliloquy2026) | [![GitHub Data][badge-012]][resource-083] |
| AutoModSAT 评测数据（含生成与工业 EDA 实例） | [AutoModSAT](#paper-sun2025satheur) | [![Zenodo Data][badge-035]][resource-084] |
| 装箱系统评测数据与演化实例 | [Beyond the Hype: Bin Packing](#paper-sim2025beyondhype) | [![Zenodo Data][badge-035]][resource-085] |
| City-LEO 共享电动自行车数据与代码 | [City-LEO](#paper-jiao2024cityleo) | [![HF：Data & Code][badge-036]][resource-086] |
| CP-Bench 修订评测材料（CP-Agent，Zenodo v2） | [CP-Agent](#paper-cpagent2025) | [![Zenodo v2][badge-037]][resource-087] |
| DRoC VRP 评测实例 | [DRoC](#paper-jiang2025droc) | [![GitHub: problems][badge-038]][resource-088] |
| HeurAgenix 使用的 CO 实例汇集 | [HeurAgenix](#paper-yang2025heuragenix) | [![HF Instances][badge-039]][resource-089] |
| 学校排课交互评测与对话材料 | [Interactive Optimization Conversations](#paper-conversation2026) | [![GitHub][badge-011]][resource-090] |
| Representation / Probing 实验材料 | [LLM Representations for Algorithm Selection](#paper-behaviorrep2025) | [![Zenodo Archive][badge-040]][resource-091] |
| LLM4OR 既有建模基准的清洗 / 错误标注合集 | [LLM4OR Survey](#paper-xiao2025survey) | [![GitHub Data][badge-012]][resource-092] |
| 随机优化评测案例（含文献改编） | [LLMs for Stochastic Modeling](#paper-talebi2025stochastic) | [![GitHub：dataset.zip][badge-041]][resource-093] |
| MoH 使用的 CO 任务数据包 | [MoH](#paper-moh2025) | [![Google Drive Data][badge-042]][resource-094] |
| MOID 路由不可行诊断案例与解 | [MOID](#paper-moid2025) | [![GitHub Data][badge-012]][resource-095] |
| NEMO 逐题输出与轨迹（既有基准） | [NEMO](#paper-nemo2026) | [![HF Artifacts][badge-043]][resource-096] |
| Opt-Miner 第三方基座复现实验输出 | [Opt-Miner](#paper-optminer2026) | [![HF：第三方结果][badge-044]][resource-097] |
| OptiChat 模型解释问答评测 | [OptiChat](#paper-chen2025optichat) | [![GitHub][badge-011]][resource-098] |
| ORLMBenchmark（既有基准修订版） | [SIRL](#paper-chen2025sirl) | [![修订评测集][badge-045]][resource-099] |
| 修订 NL4Opt / MAMO / IndustryOR 评测数据 | [Step-Opt](#paper-wu2025stepopt) | [![GitHub：Step/test][badge-046]][resource-082] |
| 计算机网络优化建模实验语料 | [Teaching LLMs to Think Mathematically](#paper-abedi2025thinkmath) | - |

<a id="skills"></a>

### 技能库

| 资源名称 | 关联论文 | 获取入口 |
|---|---|---|
| AutoOPT 领域研究技能 | [AutoOPT](#paper-autoopt2026) | [![GitHub Skills][badge-047]][resource-100] |
| MM-Agent Expert Skills（2026 后续发布） | [MM-Agent / MM-Bench（数学建模）](#paper-liu2025mmagent) | [![GitHub Skills][badge-047]][resource-101] |
| OptSkills 工作流技能库 | [OptSkills](#paper-yang2026optskills) | [![官方技能库（相关）][badge-048]][resource-102] |

[返回目录](#contents)

<a id="modeling"></a>

## 问题理解与数学建模

从问题描述抽取变量、目标与约束，形成 LP、MILP、CP 等数学模型。

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · arXiv preprint | **Agora-Opt**<br>From Soliloquy to Agora: Memory-Enhanced LLM Agents with Decentralized Debate for Optimization Modeling | 由多个 Agent 团队独立建模并开展结果驱动辩论，以读写记忆复用求解经验和分歧修订。 | 方法 · 数据 | [![Paper][badge-049]][resource-103] · [![Code & Cleaned Data][badge-050]][resource-083] · [详情](#paper-soliloquy2026) |
| 2026 · ICML 2026 RLxF Workshop / arXiv | **AutoOR**<br>AutoOR: Scalably Post-training LLMs to Autoformulate Operations Research Problems | 从标准优化形式合成训练样本，并以执行反馈和课程式 RL 训练自然语言到模型的能力。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-104] · [![Paper 2][badge-052]][resource-105] · [详情](#paper-autoor2026) |
| 2026 · arXiv preprint | **AutoREM / AutoRO-Bench**<br>Automated Reformulation of Robust Optimization via Memory-Augmented Large Language Models | 以失败经验记忆辅助鲁棒优化的确定性重构，并提出 AutoRO-Bench。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-106] · [详情](#paper-robustreform2026) |
| 2026 · LION 19 / LNCS 15745（2026 出版） | **CHORUS**<br>CHORUS: Zero-shot Hierarchical Retrieval and Orchestration for Generating Linear Programming Code | 用分层文档切分、元数据检索和重排，为 LLM 生成 Gurobi LP 代码提供相关知识。 | 方法 · 基准 · 数据 | [![Publication][badge-053]][resource-107] · [![Paper 2][badge-052]][resource-108] · [详情](#paper-lporch2025) |
| 2026 · arXiv preprint | **CIR / R2C**<br>Canonical Intermediate Representation for LLM-based optimization problem formulation and code generation | 以规范中间表示编码复杂规则，再检索知识并生成约束实现。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-109] · [详情](#paper-canonicalir2026) |
| 2026 · ACM Computing Surveys 58（2026） | **Combinatorial Optimization Systematic Review**<br>Large Language Models for Combinatorial Optimization: A Systematic Review | 按 PRISMA 流程筛选 LLM 组合优化研究，归纳任务、模型架构、评测数据与应用领域。 | 综述 | [![Paper 1][badge-051]][resource-110] · [![Paper 2][badge-052]][resource-111] · [详情](#paper-lco2026review) |
| 2026 · arXiv preprint | **COOPA**<br>COOPA: A Modular LLM Agent Architecture for Operations Research Problems | 迭代比较候选公式的置信度，追踪建模元素的来源，再路由至适用求解器 Agent。 | 方法 | [![Paper][badge-049]][resource-112] · [![Code][badge-022]][resource-113] · [详情](#paper-coopa2026) |
| 2026 · LLM4Code 2026 Workshop @ ICSE | **CP-Agent**<br>CP-Agent: Agentic Constraint Programming | 通过持久 IPython 内核和简短领域提示，执行并迭代修正约束模型。 | 方法 · 数据 | [![Paper 1][badge-051]][resource-114] · [![Paper 2][badge-052]][resource-115] · [![Author Coding Agent（相关）][badge-054]][resource-116] · [![Evaluation Archive v2][badge-055]][resource-087] · [详情](#paper-cpagent2025) |
| 2026 · arXiv preprint | **CP-SynC**<br>CP-SynC: Multi-Agent Zero-Shot Constraint Modeling in MiniZinc with Synthesized Checkers | 由建模、检查与选择 Agent 并行探索 MiniZinc 模型，并合成语义检查器聚合证据。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-117] · [![Benchmark & Evaluation][badge-056]][resource-028] · [详情](#paper-cpsync2026) |
| 2026 · AAAI 2026 | **DeepOR**<br>DeepOR: A Deep Reasoning Foundation Model for Optimization Modeling | 以流程图引导长思维链合成和监督微调，再用求解器反馈构造奖励进行强化学习。 | 方法 · 数据 | [![Paper][badge-057]][resource-118] · [![Code][badge-022]][resource-119] · [![官方种子与样例数据][badge-028]][resource-072] · [详情](#paper-xiao2026deepor) |
| 2026 · arXiv preprint | **EVOM**<br>Execution-Verified Reinforcement Learning for Optimization Modeling | 以求解器执行结果训练建模 LLM，并研究 Gurobi、OR-Tools 与 COPT 间的迁移。 | 方法 · 模型 | [![Paper][badge-049]][resource-120] · [详情](#paper-guan2026evom) |
| 2026 · arXiv preprint | **EvoOpt-LLM**<br>EvoOpt-LLM: Evolving industrial optimization models with large language models | 以 7B 模型和 LoRA 支持工业 MILP 的模型构建、新业务约束注入与变量剪枝。 | 方法 · 模型 | [![Paper][badge-049]][resource-121] · [![Code][badge-022]][resource-122] · [详情](#paper-he2026evoopt) |
| 2026 · NeurIPS 2026（已接收，待出版） | **EvoOptiGraph**<br>EvoOptiGraph: Weakness-Driven Coevolution via Graph-Based Structural Generation for Optimization Modeling | 以属性二部图演化结构多样的 MILP，结合编译、回译、SFT 与 RLVR 针对模型弱点更新训练分布。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-123] · [![Paper 2][badge-052]][resource-124] · [详情](#paper-evooptigraph2026) |
| 2026 · arXiv preprint | **EvoOR-Agent**<br>Co-evolving Agent Architectures and Interpretable Reasoning for Automated Optimization | 以 AOE 图表示建模—求解工作流，共同演化 Agent 架构与可解释推理路径。 | 方法 | [![Paper][badge-049]][resource-125] · [详情](#paper-coevolve2026) |
| 2026 · arXiv；NeurIPS 2026 Workshop 版本 | **Formalize, Don't Optimize**<br>Formalize, Don't Optimize: The Heuristic Trap in LLM-Generated Combinatorial Solvers | 用 CP-SynC-XL 比较原生搜索、Python 求解器 API 与 MiniZinc，并审计搜索优化带来的错误。 | 基准 · 数据 | [![Paper 1][badge-058]][resource-126] · [![Workshop][badge-059]][resource-127] · [详情](#paper-wang2026formalize) |
| 2026 · EMNLP 2026 | **FormuEvo**<br>FormuEvo: LLM-Guided Evolution for Discovering Solver-Efficient Mixed-Integer Programming Formulations | 在建模程序空间演化更强的 MIP 表达，以求解器统计诊断和结构化记忆指导改写。 | 方法 | [![Publication][badge-053]][resource-128] · [![Paper 2][badge-052]][resource-129] · [![Code][badge-022]][resource-130] · [详情](#paper-yuan2026formuevo) |
| 2026 · NeurIPS 2026（已接收，待出版） | **FrontierOR**<br>FrontierOR: Benchmarking LLMs' Capacity for Efficient Algorithm Design in Large-Scale Optimization | 评测 LLM 在文献驱动的大规模 OR 任务中生成高效且可行算法的能力。 | 基准 · 数据 | [![Paper 1][badge-051]][resource-131] · [![Paper 2][badge-052]][resource-132] · [![Code][badge-022]][resource-034] · [![Dataset][badge-060]][resource-033] · [详情](#paper-kong2026frontieror) |
| 2026 · arXiv preprint | **Interactive Optimization Conversations**<br>Let's Have a Conversation: Designing and Evaluating LLM Agents for Interactive Optimization | 用带内部效用函数的决策 Agent 扮演利益相关者，评测多轮交互优化而非只看单次答案。 | 方法 · 数据 · 应用 | [![Paper][badge-049]][resource-133] · [![Code][badge-022]][resource-090] · [详情](#paper-conversation2026) |
| 2026 · arXiv preprint | **LEAN-LLM-OPT**<br>Large-Scale Optimization Model Auto-Formulation: Harnessing LLM Flexibility via Structured Workflow | 动态构建建模工作流并将数据处理交给工具，面向大规模优化和航空收入管理。 | 方法 · 基准 · 数据 · 应用 | [![Paper][badge-049]][resource-134] · [![Code][badge-022]][resource-038] · [详情](#paper-liang2026leanllmopt) |
| 2026 · IEEE CIM（期刊记录；出版日期未确认） | **LLMs for Evolutionary Optimization Survey**<br>A Systematic Survey on Large Language Models for Evolutionary Optimization: From Modeling to Solving | 从建模到求解梳理 LLM 与进化优化，区分直接优化、算法内部辅助与高层算法设计。 | 综述 | [![Journal record][badge-061]][resource-135] · [![Paper 2][badge-052]][resource-136] · [![Literature Collection（相关）][badge-062]][resource-137] · [详情](#paper-sysevo2025) |
| 2026 · arXiv preprint | **MIND**<br>Automated Optimization Modeling via a Localizable Error-Driven Perspective | 依据建模错误的局部性合成针对性训练问题，并用 DFPO 对困难样本做局部修订。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-138] · [详情](#paper-mind2026) |
| 2026 · arXiv preprint | **MiniOpt**<br>MiniOpt: Reasoning to Model and Solve General Optimization Problems with Limited Resources | 以结构化推理连接建模和代码生成，用分层 OptReward 同时反馈公式与解的质量。 | 方法 · 模型 | [![Paper][badge-049]][resource-139] · [![Code][badge-022]][resource-140] · [详情](#paper-zhao2026miniopt) |
| 2026 · ICML 2026 | **MIPLIB-NL**（核心）<br>Constructing Industrial-Scale Optimization Modeling Benchmark | 从 MIPLIB 2017 真实 MILP 逆向恢复可复用结构，分离问题与数据，构建自然语言建模基准。 | 基准 · 数据 | [![Publication][badge-053]][resource-141] · [![Paper 2][badge-052]][resource-142] · [![Code][badge-022]][resource-042] · [![GitHub dataset][badge-063]][resource-143] · [详情](#paper-li2026miplibnl) |
| 2026 · arXiv preprint | **MIRROR**<br>MIRROR: A Multi-Agent Framework with Iterative Adaptive Revision and Hierarchical Retrieval for Optimization Modeling in Operations Research | 通过执行驱动的迭代修订与分层检索，获取建模和代码示例来修复优化模型。 | 方法 | [![Paper][badge-049]][resource-144] · [详情](#paper-mirror2026) |
| 2026 · NeurIPS 2026（已接收，待出版） | **MM-OptBench**<br>MM-OptBench: A Solver-Grounded Benchmark for Multimodal Optimization Modeling | 以文本和表格、图、地图等视觉输入评测优化公式与求解器代码生成。 | 基准 · 数据 | [![Paper 1][badge-051]][resource-145] · [![Paper 2][badge-052]][resource-146] · [详情](#paper-zhu2026mmoptbench) |
| 2026 · arXiv preprint | **Multi-Warehouse Formulation Selection**<br>Large Language Model for Operations Research Formulation Selection in Multi-Warehouse Inventory Allocation | 在多仓库存分配中选择适合实例的 MIP 公式专家，并用求解质量反馈训练选择器。 | 方法 · 模型 · 应用 | [![Paper][badge-049]][resource-147] · [详情](#paper-warehouseformsel2026) |
| 2026 · ICML 2026 · PMLR 306 | **NEMO**<br>NEMO: Execution-Aware Optimization Modeling via Autonomous Coding Agents | 用自主编码 Agent 生成优化器与模拟器，再以交叉执行、经验复用和候选一致性改进建模。 | 方法 | [![Paper 1][badge-051]][resource-148] · [![Paper 2][badge-052]][resource-149] · [![Evaluation Artifacts][badge-064]][resource-096] · [详情](#paper-nemo2026) |
| 2026 · ICML 2026 · PMLR 306 | **OPT-Engine**<br>OPT-Engine: Benchmarking the Limits of LLMs in Optimization Modeling via Complexity Scaling | 可控地扩展 OR 问题复杂度，比较文本推理、工具调用与求解器集成。 | 基准 · 数据 | [![Paper 1][badge-051]][resource-150] · [![Paper 2][badge-052]][resource-151] · [![Code][badge-022]][resource-050] · [![Dataset][badge-060]][resource-049] · [详情](#paper-chen2026optengine) |
| 2026 · ICML 2026 · PMLR 306 | **Opt-Miner**<br>Opt-Miner: Empowering Information-Seeking Agent with Tree-Guided Data Synthesis for Optimization Modeling | 用树结构合成带知识缺口的优化任务，并以 R-GRPO 训练主动检索知识的建模 Agent。 | 方法 · 数据 · 模型 | [![Paper][badge-057]][resource-152] · [![Reproduction Code（第三方）][badge-065]][resource-153] · [![Reproduction Results（第三方）][badge-066]][resource-097] · [![Demo（第三方）][badge-067]][resource-154] · [详情](#paper-optminer2026) |
| 2026 · arXiv preprint | **OptGraph**<br>OptGraph: Large Language Models Enhanced Evolutionary Optimization Via Graph Retrieval-Augmented Generation | 将建模模式、公式、实现和错误修订组织成类型图，以邻域检索和运行轨迹更新支持优化建模。 | 方法 | [![Paper][badge-049]][resource-155] · [![Code][badge-022]][resource-156] · [详情](#paper-xiu2026optgraph) |
| 2026 · arXiv preprint | **Opti-Agent-Bench**<br>Opti-Agent-Bench: Benchmarking End-to-End Optimization R&D Agents on Real-World Business Problems | 评测业务理解、形式化、实现与报告，并检查跨模块一致性和任务评分有效性。 | 基准 · 数据 | [![Paper][badge-049]][resource-157] · [详情](#paper-optiagentbench2026) |
| 2026 · arXiv preprint | **OptiAgent**<br>OptiAgent: End-to-End Optimization Modeling via Multi-Agent Iterative Refinement | 通过专门建模 Agent 与多层反馈循环，提取变量和约束并修正公式及可执行代码。 | 方法 | [![Paper][badge-049]][resource-158] · [详情](#paper-optiagent2026) |
| 2026 · INFORMS Journal on Data Science 5(3):199–220 | **OptiChat**<br>OptiChat: Bridging Optimization Models and Practitioners with Large Language Models | 用自然语言查询已有优化模型，支持不可行诊断、敏感性、what-if 和反事实解释。 | 方法 · 数据 | [![Paper 1][badge-051]][resource-159] · [![Paper 2][badge-052]][resource-160] · [![Code][badge-022]][resource-098] · [详情](#paper-chen2025optichat) |
| 2026 · arXiv preprint | **OptiDSL**<br>Not All Problems Are Best Modeled as MILP: A DSL-Centric Framework for Flexible and Accurate Optimization Modeling | 将自然语言映射为领域 DSL，再接入专用求解器，避免所有问题强制采用 MILP。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-161] · [详情](#paper-dslmilp2026) |
| 2026 · Findings of ACL 2026 | **OptiVerse / DVA-Agent**<br>OptiVerse: A Comprehensive Benchmark towards Optimization Problem Solving | 以 1,000 道多范式优化题评测建模与求解，并用双视角审核 Agent 对照需求与代码语义。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-162] · [![Paper 2][badge-052]][resource-163] · [![Inference, Auditor & Evaluation][badge-068]][resource-053] · [![OptiVerse 1K][badge-069]][resource-052] · [详情](#paper-optiverse2026) |
| 2026 · Findings of EMNLP 2026 | **OptSkills**<br>OptSkills: Learning Generalizable Optimization Skills from Problem Archetypes via Cluster-Based Distillation | 按问题原型聚类，从成功建模轨迹提炼、检索并更新可复用的工作流技能。 | 方法 | [![Publication][badge-053]][resource-164] · [![Paper 2][badge-052]][resource-165] · [![Code 1][badge-070]][resource-166] · [![Code 2][badge-071]][resource-167] · [![官方技能库（相关）][badge-048]][resource-102] · [详情](#paper-yang2026optskills) |
| 2026 · ICLR 2026 | **OR-PRM**<br>OR-PRM: A Process Reward Model for Algorithmic Problem in Operations Research | 先清洗已有合成数据，基于 MCTS 和逐步检查构建 OR-ProcessQA，再训练用于建模推理的过程奖励模型。 | 方法 · 数据 · 模型 | [![Paper][badge-057]][resource-168] · [详情](#paper-wang2026orprm) |
| 2026 · AAAI 2026 | **OR-R1**<br>OR-R1: Automating Modeling and Solving of Operations Research Optimization Problem via Test-Time Reinforcement Learning | 先用少量有标签数据 SFT，再以测试时 TGRPO 从未标注问题和求解一致性中学习。 | 方法 · 模型 | [![Paper 1][badge-051]][resource-169] · [![Paper 2][badge-052]][resource-170] · [![Code][badge-022]][resource-171] · [详情](#paper-ding2026orr1) |
| 2026 · arXiv preprint | **OR-Space**<br>OR-Space: A Full-Lifecycle Workspace Benchmark for Industrial Optimization Agents | 用持久多文件工作区评测模型构建、需求变更和基于证据的解释三类生命周期任务。 | 基准 · 数据 | [![Paper][badge-049]][resource-172] · [![Code][badge-022]][resource-057] · [![Dataset][badge-060]][resource-056] · [详情](#paper-zhou2026orspace) |
| 2026 · arXiv preprint | **ORAgentBench**<br>ORAgentBench: Can LLM Agents Solve Challenging Operations Research Tasks End to End? | 在隔离工作环境中评测从业务说明、多文件材料到可验证决策的完整 OR 任务。 | 基准 · 数据 | [![Paper][badge-049]][resource-173] · [![Code][badge-022]][resource-058] · [详情](#paper-oragentbench2026) |
| 2026 · Artificial Intelligence for Transportation 6（2026） | **ORThought / LogiOR**<br>ORThought: Benchmarking and automating logistics optimization modeling via structured LLM reasoning | 以专家建模原则指导结构化双 Agent 推理，并发布物流建模基准 LogiOR。 | 方法 · 基准 · 数据 | [![Publication][badge-053]][resource-174] · [![Paper 2][badge-052]][resource-175] · [![Code][badge-022]][resource-176] · [![Dataset][badge-060]][resource-062] · [详情](#paper-yang2025orthought) |
| 2026 · NeurIPS 2026（已接收，待出版） | **PEARL**（核心）<br>PEARL: Solver-in-the-Loop Interactive Optimization Modeling from Natural Language | 在多轮工具调用中执行、调试和修订优化模型，用求解器反馈训练交互建模策略。 | 方法 · 模型 | [![Paper 1][badge-058]][resource-177] · [![Conference][badge-072]][resource-178] · [![Code][badge-022]][resource-179] · [![Model][badge-073]][resource-009] · [详情](#paper-lu2026pearl) |
| 2026 · ICML 2026 | **ProOPF**<br>ProOPF: Benchmarking and Improving LLMs for Professional-Grade Power Systems Optimization Modeling | 构建专业最优潮流建模数据和基准，区分参数调整与结构扩展难度。 | 基准 · 数据 · 应用 | [![Publication][badge-053]][resource-180] · [![Paper 2][badge-074]][resource-181] · [![Paper 3][badge-075]][resource-182] · [![Evaluation Code & Data][badge-076]][resource-064] · [详情](#paper-shen2026proopf) |
| 2026 · arXiv preprint | **RAG for Optimization & CP Modeling**<br>Optimization and Constraint Modeling using LLMs with a Retrieval Augmented Generation Process | 从 Text2Zinc 种子和角色描述合成 500 个问题，以检索示例辅助 LLM 生成优化与约束模型代码。 | 方法 · 数据 | [![Paper][badge-049]][resource-183] · [详情](#paper-roy2026rag) |
| 2026 · ICML 2026 · PMLR 306 | **SAC-Opt**<br>SAC-Opt: Semantic Anchors for Iterative Correction in Optimization Modeling | 把生成代码回译为语义锚点，与原始需求对齐后定点修正约束和目标。 | 方法 | [![Paper 1][badge-051]][resource-184] · [![Paper 2][badge-052]][resource-185] · [![Code][badge-022]][resource-186] · [详情](#paper-ma2025sacopt) |
| 2026 · ICML 2026 · PMLR 306 | **SAGE (Strategy-Aware Modeling)**<br>Strategy-Aware Optimization Modeling with Reasoning LLMs | 生成并筛选多策略建模示范，经 SFT 与 Segment-Weighted GRPO 兼顾公式正确性和求解效率。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-187] · [![Paper 2][badge-052]][resource-188] · [![Code][badge-022]][resource-189] · [![SAGE SFT 100K][badge-077]][resource-080] · [详情](#paper-strategyaware2026) |
| 2026 · arXiv preprint | **SDRL**<br>LLMs as Adaptive Meta-Solvers: Strategy-Diverse RL for Industrial-Scale Optimization | 用正确性门控的层次多样性奖励，训练模型在求解器、精确组合算法和启发式之间适配策略。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-190] · [![Benchmark Inference][badge-078]][resource-191] · [![SDRL Qwen3 4B][badge-079]][resource-010] · [详情](#paper-sdrl2026) |
| 2026 · International Journal of Production Research（2026 在线） | **SMILO**<br>An LLM-powered MILP modelling engine for workforce scheduling guided by expert knowledge | 结合专家建模图、LLM 信息抽取与模板生成劳动力排班 MILP。 | 方法 · 应用 | [![Paper 1][badge-051]][resource-192] · [![Paper 2][badge-052]][resource-193] · [详情](#paper-li2025smilo) |
| 2026 · arXiv preprint | **SOLID**<br>Beyond Verified Answers: Solver-Informed Self-Distillation for Bootstrapping Operations Research Language Models | 从多次求解 rollout 的目标聚类构建伪参考，以求解器产物做无真值的自蒸馏后训练。 | 方法 · 模型 | [![Paper][badge-049]][resource-194] · [![Code][badge-022]][resource-195] · [![SOLID-Qwen3][badge-080]][resource-015] · [![SOLID-StepORLM][badge-081]][resource-016] · [详情](#paper-solid2026) |
| 2026 · arXiv preprint | **Text2Model**<br>Text2Model: Modeling Copilots for Text-to-Model Translation | 提供面向 MiniZinc 的多种建模 Copilot、交互编辑器与在线排行榜。 | 方法 · 平台 | [![Paper][badge-049]][resource-196] · [![Code][badge-022]][resource-197] · [![Text2Zinc（复用）][badge-082]][resource-069] · [![Editor（相关）][badge-083]][resource-198] · [![Leaderboard（相关）][badge-084]][resource-199] · [![Python Package（相关）][badge-085]][resource-200] · [详情](#paper-text2model2026) |
| 2026 · ICML 2026 · PMLR 306 | **VeriSimpl**<br>VeriSimpl: Robust Optimization Modeling from Natural Language using Simplification-based Verification | 用求解器构造简化诊断问题，帮助 LLM 检查模型是否符合自然语言题意。 | 方法 | [![Publication][badge-053]][resource-201] · [![Paper 2][badge-052]][resource-202] · [![Conference][badge-072]][resource-203] · [![官方项目（仅 README）（相关）][badge-086]][resource-204] · [详情](#paper-verisimpl2026) |
| 2025 · NeurIPS 2025 ScaleOpt Workshop / arXiv | **AlphaOPT**<br>AlphaOPT: Formulating Optimization Programs with Self-Improving LLM Experience Library | 通过求解器反馈提炼并演化可检索的建模经验库，无需更新 LLM 参数。 | 方法 | [![Paper 1][badge-051]][resource-205] · [![Paper 2][badge-052]][resource-206] · [![Code][badge-022]][resource-207] · [详情](#paper-kong2025alphaopt) |
| 2025 · arXiv preprint | **Ask, Clarify, Optimize**<br>Ask, Clarify, Optimize: Human-LLM Agent Collaboration for Smarter Inventory Control | 由 LLM 澄清库存需求并解释结果，把随机优化计算交给算法，以模拟经理测试交互。 | 方法 · 模型 · 应用 | [![Paper][badge-049]][resource-208] · [详情](#paper-askclarify2026) |
| 2025 · ICML 2025 | **Autoformulation**（核心）<br>Autoformulation of Mathematical Optimization Models Using LLMs | 使用 MCTS 搜索候选优化模型，通过符号剪枝与 LLM 部分模型估值引导探索。 | 方法 | [![Paper 1][badge-051]][resource-209] · [![arXiv][badge-087]][resource-210] · [![Code][badge-022]][resource-211] · [详情](#paper-astorga2025autoformulation) |
| 2025 · ACL 2025, Volume 1: Long Papers, pp. 821–838 | **BPP-Search / StructuredOR**<br>BPP-Search: Enhancing Tree of Thought Reasoning for Mathematical Modeling Problem Solving | 提出 BPP-Search，将束搜索、过程奖励模型和成对偏好机制结合到思维树推理中。 | 方法 · 基准 · 数据 | [![Paper][badge-057]][resource-212] · [![Code][badge-022]][resource-213] · [![Dataset][badge-060]][resource-022] · [详情](#paper-wang2025bppsearch) |
| 2025 · FedCSIS 2025 · ACSIS 43 | **C-DSS**<br>Toward Conversational Decision Support Systems: Integrating LLMs in the Operations Research Methodology | 提出对话式决策支持架构，比较建模、AMPL 编码、RAG 和验证角色的不同组合。 | 方法 | [![Paper 1][badge-051]][resource-214] · [![Paper 2][badge-074]][resource-215] · [详情](#paper-kaleta2025cdss) |
| 2025 · arXiv preprint | **CALM / STORM**<br>CALM Before the STORM: Unlocking Native Reasoning for Optimization Modeling | 用少量纠正提示修订推理轨迹，再经 SFT 与强化学习训练优化建模模型 STORM。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-216] · [详情](#paper-calm2025storm) |
| 2025 · arXiv preprint | **Component-Level Evaluation**<br>Peering Inside the Black Box: Uncovering LLM Errors in Optimization Modelling through Component-Level Evaluation | 按变量、约束、目标的覆盖和数值误差评价模型，补充最优值与运行时间指标。 | 方法 | [![Paper][badge-049]][resource-217] · [详情](#paper-peering2025) |
| 2025 · ECAI 2025 | **CP-Bench / DCP-Bench-Open**<br>CP-Bench: Evaluating Large Language Models for Constraint Modelling | 以多领域离散组合问题评测 LLM 约束建模，并在 DCP-Bench-Open 中持续扩展。 | 基准 · 数据 | [![Paper 1][badge-058]][resource-218] · [![Related version][badge-088]][resource-219] · [![Publication][badge-053]][resource-220] · [![Code（当前扩展版）][badge-089]][resource-027] · [![Dataset（原版归档）][badge-090]][resource-026] · [![CP-Bench 原版归档][badge-091]][resource-221] · [详情](#paper-michailidis2025cpbench) |
| 2025 · arXiv preprint | **DAOpt / OptU**<br>DAOpt: Modeling and Evaluation of Data-Driven Optimization under Uncertainty with LLMs | 结合不确定性建模、多 Agent 与仿真环境，评估样本外可行性和稳健性。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-222] · [详情](#paper-daopt2025) |
| 2025 · AAAI 2025 | **DOCP Research Manifesto**（核心）<br>Enhancing Decision Making Through the Integration of Large Language Models and Operations Research Optimization | 提出面向业务用户的优化 Copilot 愿景，梳理需求澄清、模型核验和求解效率等研究要求。 | 综述 · 基础 | [![Paper 1][badge-051]][resource-223] · [![Paper 2][badge-052]][resource-224] · [详情](#paper-wasserkrug2024manifesto) |
| 2025 · arXiv preprint | **DPLM / DP-Bench**<br>Auto-Formulating Dynamic Programming Problems with Large Language Models | 提出 DP-Bench，并用双向反思合成训练数据，训练从自然语言构造动态规划模型的 DPLM。 | 方法 · 基准 · 数据 · 模型 | [![Paper][badge-049]][resource-225] · [详情](#paper-dpdlm2025) |
| 2025 · ICLR 2025 | **DRoC**<br>DRoC: Elevating Large Language Models for Complex Vehicle Routing via Decomposed Retrieval of Constraints | 分解复杂 VRP 的约束并分别检索文档，动态选择 RAG 或自调试生成求解器程序。 | 方法 · 数据 · 应用 | [![Publication][badge-053]][resource-226] · [![Paper 2][badge-074]][resource-227] · [![Code][badge-022]][resource-088] · [详情](#paper-jiang2025droc) |
| 2025 · ICLR 2025 | **EOR / Decision Information**<br>Decision Information Meets Large Language Models: The Future of Explainable Operations Research | 用 what-if 决策信息与二部图比较模型变化，生成可操作的优化解释。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-228] · [![Paper 2][badge-052]][resource-229] · [![Code][badge-022]][resource-031] · [详情](#paper-zhang2025decisioninfo) |
| 2025 · ICML 2025 | **EquivaMap**（核心）<br>EquivaMap: Leveraging LLMs for Automatic Equivalence Checking of Optimization Formulations | 用 LLM 寻找决策变量映射来检查 Quasi-Karp 等价，并构建 EquivaFormulation。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-230] · [![arXiv][badge-087]][resource-231] · [![Code][badge-022]][resource-232] · [![Dataset][badge-060]][resource-032] · [详情](#paper-zhai2025equivamap) |
| 2025 · arXiv preprint | **Gala**<br>Gala: Global LLM Agents for Text-to-Model Translation | 按全局约束类型分工 Agent，再由组装 Agent 合成完整 MiniZinc 模型。 | 方法 | [![Paper][badge-049]][resource-233] · [![Gala in Text2Model][badge-092]][resource-197] · [![Author Project（相关）][badge-093]][resource-234] · [详情](#paper-globalconstraint2025) |
| 2025 · arXiv preprint | **LLM-SUC**（探索性）<br>Can Large Language Model Agents Balance Energy Systems? | 将 LLM Agent 与多场景随机机组组合结合，辅助高风电不确定性下的运行决策。 | 方法 · 应用 | [![Paper][badge-049]][resource-235] · [![Code][badge-022]][resource-236] · [详情](#paper-llmsuc2025) |
| 2025 · IJCAI 2025 Survey Track | **LLM4OR Survey**（核心）<br>A Survey of Optimization Modeling Meets LLMs: Progress and Future Directions | 综述优化建模全流程，分析并标记基准错误，提供清洗数据与评测门户。 | 综述 · 数据 | [![Paper][badge-049]][resource-237] · [![官方资源库（相关）][badge-094]][resource-238] · [![Cleaned Benchmarks][badge-095]][resource-092] · [详情](#paper-xiao2025survey) |
| 2025 · ICLR 2025 | **LLMOPT**（核心）<br>LLMOPT: Learning to Define and Solve General Optimization Problems from Scratch | 通过五要素形式化、多指令微调与自纠错，提高多类优化问题的建模与代码生成泛化。 | 方法 · 模型 | [![Paper 1][badge-051]][resource-239] · [![arXiv][badge-087]][resource-240] · [![Code][badge-022]][resource-241] · [![Model][badge-073]][resource-002] · [详情](#paper-jiang2025llmopt) |
| 2025 · arXiv preprint | **LLMs for Stochastic Modeling**<br>Large Language Model-Based Automatic Formulation for Stochastic Optimization Models | 以结构化提示生成机会约束与两阶段随机规划，并用软评分检查模型结构。 | 方法 | [![Paper][badge-049]][resource-242] · [![Code][badge-022]][resource-093] · [详情](#paper-talebi2025stochastic) |
| 2025 · arXiv preprint | **LLMs in OR: Methods & Challenges**<br>Large Language Models in Operations Research: Methods, Applications, and Challenges | 按自动建模、辅助优化和直接求解梳理 LLM 在运筹学中的方法与应用。 | 综述 | [![Paper][badge-049]][resource-243] · [详情](#paper-wang2025lor) |
| 2025 · Findings NAACL 2025 | **Mamo**（核心）<br>LLMs for Mathematical Modeling: Towards Bridging the Gap between Natural and Mathematical Languages | 提出 Mamo，以求解器辅助的过程评估研究语言到数学建模，涵盖 LP、MILP 与 ODE。 | 基准 · 数据 | [![Paper 1][badge-058]][resource-244] · [![Paper 2][badge-074]][resource-245] · [![Code][badge-022]][resource-040] · [![Dataset（第三方镜像）][badge-096]][resource-041] · [详情](#paper-huang2024mamo) |
| 2025 · NeurIPS 2025 | **MM-Agent / MM-Bench（数学建模）**（探索性）<br>MM-Agent: LLM as Agents for Real-world Mathematical Modeling Problem | 将数学建模拆为问题分析、模型构造、计算求解和报告生成，并提供 MCM/ICM 来源的 MM-Bench。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-246] · [![Paper 2][badge-052]][resource-247] · [![Paper 3][badge-097]][resource-248] · [![Code & MM-Bench][badge-098]][resource-043] · [![Expert Skills (2026 add-on)][badge-099]][resource-101] · [![HF Demo（相关）][badge-100]][resource-249] · [详情](#paper-liu2025mmagent) |
| 2025 · Findings of EMNLP 2025 | **ModelingAgent / ModelingBench**（探索性）<br>ModelingAgent: Bridging LLMs and Mathematical Modeling for Real-World Challenges | 用多 Agent 协调工具和迭代修订处理开放式建模，并以 ModelingBench 与 ModelingJudge 评估报告。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-250] · [![Paper 2][badge-052]][resource-251] · [![Code & ModelingBench][badge-101]][resource-044] · [详情](#paper-qian2025modelingagent) |
| 2025 · arXiv preprint | **MOID**<br>Multi-Objective Infeasibility Diagnosis for Routing Problems Using Large Language Models | 联合路径成本与约束违反量做多目标优化，再由 LLM 分析一组可恢复可行性的调整建议。 | 方法 · 数据 · 应用 | [![Paper][badge-049]][resource-252] · [![Diagnosis Data][badge-102]][resource-095] · [详情](#paper-moid2025) |
| 2025 · NeurIPS 2025 Main Conference Track, volume 38 | **MURKA**<br>MURKA: Multi-Reward Reinforcement Learning with Knowledge Alignment for Optimization Tasks | 用多奖励强化学习与知识蒸馏对齐 Extractor、Solver、Checker 三类 Agent，支持从文本到可执行优化程序。 | 方法 | [![Paper][badge-057]][resource-253] · [详情](#paper-xie2025murka) |
| 2025 · arXiv preprint | **OptimAI**<br>OptimAI: Optimization from Natural Language Using LLM-Powered AI Agents | 以建模、规划、编码和代码批评角色协作求解，并用 UCB 调度调试与备选计划。 | 方法 | [![Paper][badge-049]][resource-254] · [详情](#paper-thind2025optimai) |
| 2025 · arXiv preprint | **OptiMind**（核心）<br>OptiMind: Teaching LLMs to Think Like Optimization Experts | 用按优化问题类别组织的专家错误分析指导训练与推理，减少 MILP 形式化常见错误。 | 方法 · 模型 | [![Paper][badge-049]][resource-255] · [![Code][badge-022]][resource-256] · [![Model][badge-073]][resource-005] · [详情](#paper-zhang2025optimind) |
| 2025 · NeurIPS 2025 | **OptiTree**（核心）<br>OptiTree: Hierarchical Thoughts Generation with Tree Search for LLM Optimization Modeling | 利用层级建模树搜索，将复杂优化问题自适应分解为可复用的简单建模思路。 | 方法 | [![Publication][badge-053]][resource-257] · [![Paper 2][badge-052]][resource-258] · [![Code][badge-022]][resource-259] · [详情](#paper-liu2025optitree) |
| 2025 · arXiv preprint | **OptiTrust**<br>Toward a Trustworthy Optimization Modeling Agent via Verifiable Synthetic Data Generation | 从带已知最优解的符号问题合成示范，用跨建模语言投票和分步推理训练建模 Agent。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-260] · [详情](#paper-lima2025optitrust) |
| 2025 · ICML 2025; PMLR 267:40769–40802 | **OptMATH**（核心）<br>OptMATH: A Scalable Bidirectional Data Synthesis Framework for Optimization Modeling | 通过数学模型到问题数据再到自然语言的双向合成流程生成优化建模数据，并用正向建模和拒绝采样筛选。 | 方法 · 基准 · 数据 · 模型 | [![Paper][badge-057]][resource-261] · [![Code][badge-022]][resource-054] · [![Model 7B][badge-003]][resource-006] · [![Model 32B][badge-004]][resource-007] · [![Dataset][badge-060]][resource-078] · [详情](#paper-lu2025optmath) |
| 2025 · arXiv preprint | **OR-LLM-Agent / BWOR**<br>OR-LLM-Agent: Automating Modeling and Solving of Operations Research Optimization Problems with Reasoning LLM | 将建模、代码生成与调试分配给推理 Agent，并提出 BWOR 评测集。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-262] · [![Code][badge-022]][resource-263] · [![Dataset][badge-060]][resource-055] · [详情](#paper-zhang2025bwor) |
| 2025 · arXiv；相关 ICML 2026 Workshop 版本 | **ORGEval / Bench4Opt**（核心）<br>ORGEval: Graph-Theoretic Evaluation of LLMs in Optimization Modeling | 将优化形式化表示为图，通过图同构及对称可分解条件下的 WL 测试评价结构等价性。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-264] · [![ICML workshop poster（相关）][badge-103]][resource-265] · [详情](#paper-ding2026orgeval) |
| 2025 · Operations Research 73(6):2986–3009 | **ORLM**（核心）<br>ORLM: A Customizable Framework in Training Large Models for Automated Optimization Modeling | 通过 OR-Instruct 合成数据训练优化领域模型，并提出工业基准 IndustryOR。 | 方法 · 基准 · 数据 · 模型 | [![Paper 1][badge-058]][resource-266] · [![Journal][badge-104]][resource-267] · [![Code][badge-022]][resource-268] · [![Model][badge-073]][resource-008] · [![IndustryOR][badge-024]][resource-059] · [![OR-Instruct-3K][badge-032]][resource-079] · [详情](#paper-huang2025orlm) |
| 2025 · ACL 2025 Industry Track | **ORMind**<br>ORMind: A Cognitive-Inspired End-to-End Reasoning Framework for Operations Research | 以认知启发的角色协作、执行修复和反事实检查完成优化建模。 | 方法 | [![Paper 1][badge-051]][resource-269] · [![Paper 2][badge-052]][resource-270] · [![Code][badge-022]][resource-271] · [详情](#paper-ormind2025) |
| 2025 · AAAI 2025 | **ORQA**<br>Evaluating LLM Reasoning in the Operations Research Domain with ORQA | 以 OR 专家设计的问题检验模型对建模知识和多步推理的掌握。 | 基准 · 数据 | [![Proceedings][badge-105]][resource-272] · [![Paper 2][badge-052]][resource-273] · [![Code][badge-022]][resource-061] · [详情](#paper-mostajabdaveh2025orqa) |
| 2025 · ICLR 2025 | **ReSocratic / OptiBench**（核心）<br>OptiBench Meets ReSocratic: Measure and Improve LLMs for Optimization Modeling | 先合成数学形式与求解示范再逆向生成问题，配套 OptiBench 与 ReSocratic-29k。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-274] · [![arXiv][badge-087]][resource-275] · [![Code][badge-022]][resource-066] · [详情](#paper-yang2025resocratic) |
| 2025 · NeurIPS 2025 | **SIRL**（核心）<br>Solver-Informed RL: Grounding Large Language Models for Authentic Optimization Modeling | 用求解器检查代码及 LP 实例，构造 RL 可验证奖励，并发布模型与修订评测数据。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-276] · [![arXiv][badge-087]][resource-277] · [![Code][badge-022]][resource-278] · [![Model Gurobi-7B][badge-005]][resource-011] · [![Model COPT-7B][badge-006]][resource-012] · [![Model Gurobi-32B][badge-007]][resource-013] · [![Model COPT-32B][badge-008]][resource-014] · [![修订评测集][badge-045]][resource-099] · [详情](#paper-chen2025sirl) |
| 2025 · NeurIPS 2025 | **SolverLLM**<br>SolverLLM: Leveraging Test-Time Scaling for Optimization Problem via LLM-Guided Search | 用动态扩展的 MCTS 搜索公式和求解器代码，以提示和不确定性回传指导测试时探索。 | 方法 | [![Paper 1][badge-051]][resource-279] · [![Paper 2][badge-052]][resource-280] · [详情](#paper-solverllm2025) |
| 2025 · Findings of EMNLP 2025 | **Step-Opt**<br>Training LLMs for Optimization Modeling via Iterative Data Synthesis and Structured Validation | 逐步提高合成问题复杂度并结构化校验训练数据，再微调优化建模模型。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-281] · [![Paper 2][badge-052]][resource-282] · [![Code][badge-022]][resource-082] · [详情](#paper-wu2025stepopt) |
| 2025 · arXiv preprint | **Teaching LLMs to Think Mathematically**<br>Teaching LLMs to Think Mathematically: A Critical Study of Decision-Making via Optimization | 结合系统综述与元分析，在新构造的计算机网络优化题中比较三种提示策略。 | 综述 · 评测分析 · 数据 | [![Paper][badge-049]][resource-283] · [详情](#paper-abedi2025thinkmath) |
| 2025 · arXiv preprint | **Text2Zinc**<br>Text2Zinc: A Cross-Domain Dataset for Modeling Optimization and Satisfaction Problems in MiniZinc | 用 MiniZinc 统一表示自然语言描述的约束满足与优化问题。 | 基准 · 数据 | [![Paper][badge-049]][resource-284] · [![Dataset][badge-060]][resource-069] · [![作者项目门户（相关）][badge-106]][resource-234] · [详情](#paper-singirikonda2025text2zinc) |
| 2025 · arXiv preprint | **Validation-in-the-Loop Power Modeling**（探索性）<br>From Natural Language to Solver-Ready Power System Optimization: An LLM-Assisted, Validation-in-the-Loop Framework | 通过领域提示、结构化 schema、可行性校验与迭代修复生成电力优化模型。 | 方法 · 应用 | [![Paper][badge-049]][resource-285] · [详情](#paper-nl2ps2025) |
| 2025 · Preprint · ICLR 2025 关联未确认 | **WIQOR**<br>WIQOR: A dataset for what-if analysis of Operations Research problems | 评测根据自然语言 what-if 请求修改既有数学规划模型的能力。 | 基准 · 数据 | [![Paper PDF][badge-107]][resource-286] · [![Institution record][badge-108]][resource-287] · [详情](#paper-parashar2025wiqor) |
| 2024 · NeurIPS 2024 MATH-AI Workshop | **CAFA**<br>CAFA: Coding as Auto-Formulation Can Boost Large Language Models in Solving Linear Programming Problem | 用紧凑提示直接生成调用优化求解器的 Python 程序，执行求解线性规划问题。 | 方法 | [![Paper][badge-057]][resource-288] · [![Code][badge-022]][resource-289] · [详情](#paper-deng2024cafa) |
| 2024 · ICLR 2024 | **Chain-of-Experts**（核心）<br>Chain-of-Experts: When LLMs Meet Complex Operations Research Problems | 为不同 Agent 配置 OR 专长，由 conductor 组织前向思维构造与反向反思，完成复杂建模和编程。 | 方法 · 基准 · 数据 | [![Paper][badge-057]][resource-290] · [![Code][badge-022]][resource-023] · [详情](#paper-xiao2024coe) |
| 2024 · arXiv preprint | **City-LEO**<br>City-LEO: Toward Transparent City Management Using LLM with End-to-End Optimization | 通过对话限定优化范围，并结合预测与优化管理共享电动自行车运营。 | 方法 · 应用 | [![Paper][badge-049]][resource-291] · [![Data & Code][badge-109]][resource-086] · [详情](#paper-jiao2024cityleo) |
| 2024 · LREC-COLING 2024 | **Human-aligned LPWP Evaluation**<br>Towards Human-aligned Evaluation for Linear Programming Word Problems | 以图编辑距离比较线性规划模型，并以人工评分研究评价指标与人类判断的一致性。 | 方法 · 评测分析 | [![Paper][badge-057]][resource-292] · [详情](#paper-xing2024lpwp) |
| 2024 · EMNLP 2024 Industry Track | **ITINERA**<br>ItiNera: Integrating Spatial Optimization with Large Language Models for Open-domain Urban Itinerary Planning | 分解城市漫步需求、选择兴趣点，并用聚类感知的空间优化排序与生成个性化行程。 | 方法 · 应用 | [![Paper 1][badge-051]][resource-293] · [![Paper 2][badge-052]][resource-294] · [![Code][badge-022]][resource-295] · [详情](#paper-tang2024itinerary) |
| 2024 · INFOR 62（2024） | **LM4OPT**<br>LM4OPT: Unveiling the potential of Large Language Models in formulating mathematical optimization problems | 先适配数学语料再微调 LP 建模任务，以带噪嵌入训练小模型，并比较零样本与单样本提示。 | 方法 · 模型 · 评测分析 | [![Paper 1][badge-051]][resource-296] · [![Paper 2][badge-052]][resource-297] · [详情](#paper-ahmed2024lm4opt) |
| 2024 · INFOR 62(4):599–617 | **Multi-Stage Modeling & Verification**<br>Optimization modeling and verification from problem specifications using a multi-agent multi-stage LLM framework | 分阶段从问题规格生成数学模型与 Zimpl 代码，并由多个 LLM Agent 交叉检查。 | 方法 · 基准 · 数据 | [![Paper][badge-057]][resource-298] · [详情](#paper-mostajabdaveh2024multiagent) |
| 2024 · Constraints 29（2024） | **Ner4Opt**<br>Ner4Opt: named entity recognition for optimization modelling from natural language | 从优化问题文本识别变量、参数、目标和约束等实体，比较词法、语义、微调及语言模型方案。 | 方法 · 模型 · 基础 | [![Paper][badge-057]][resource-299] · [![Code][badge-022]][resource-300] · [![ner4opt-roberta-v1][badge-110]][resource-003] · [![ner4opt-roberta-v2][badge-111]][resource-004] · [![HF Demo（相关）][badge-100]][resource-301] · [详情](#paper-dakle2023ner4opt) |
| 2024 · ICML 2024 | **OptiMUS**（核心）<br>OptiMUS: Scalable Optimization Modeling with (MI)LP Solvers and Large Language Models | 用模块化 Agent 完成 MILP 建模、代码生成、调试与评估，同时发布 NLP4LP。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-302] · [![arXiv][badge-087]][resource-303] · [![Code][badge-022]][resource-304] · [![Dataset][badge-060]][resource-051] · [详情](#paper-teshnizi2024optimus) |
| 2024 · NAACL 2024 Industry Track | **OptLLM**<br>Solving General Natural-Language-Description Optimization Problems with Large Language Models | 通过多轮澄清、公式与代码转换、外部求解器和结果解释支持自然语言优化，并微调 Qwen。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-305] · [![Paper 2][badge-052]][resource-306] · [![MindOpt Trial (International)（相关）][badge-112]][resource-307] · [![MindOpt Trial (CN)（相关）][badge-113]][resource-308] · [详情](#paper-zhang2024optllm) |
| 2024 · arXiv preprint | **RAGDyS**<br>Automated Conversion of Static to Dynamic Scheduler via Natural Language | 从既有静态排程模型出发，用检索增强生成按自然语言约束实施动态排程修改。 | 方法 · 应用 | [![Paper][badge-049]][resource-309] · [详情](#paper-tang2024ragdys) |
| 2024 · EMNLP 2024 System Demonstrations | **To the Globe / TTG**<br>To the Globe (TTG): Towards Language-Driven Guaranteed Travel Planning | 将旅行需求译为符号表示，再由 MILP 求解器生成满足已编码约束的行程。 | 方法 · 应用 · 模型 | [![Paper 1][badge-051]][resource-310] · [![Paper 2][badge-052]][resource-311] · [详情](#paper-ju2024ttg) |
| 2023 · arXiv preprint | **AI-Copilot for Business Optimisation**<br>Language Models for Business Optimisation with a Real World Case Study in Production Scheduling | 微调成本较低的 LLM 生成优化公式，并在真实生产排程案例中评估。 | 方法 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-312] · [![Training Data][badge-114]][resource-070] · [![Generated Formulations（相关）][badge-115]][resource-313] · [![Industrial Case Data][badge-116]][resource-071] · [![Industrial Outputs（相关）][badge-117]][resource-314] · [![LPWP Evaluation Data（相关）][badge-118]][resource-315] · [详情](#paper-alahakoon2023copilot) |
| 2023 · ICLR 2023 DL4C Workshop / arXiv | **CodeT5 Mathematical Program Synthesis**<br>Synthesis of Mathematical programs from Natural Language Specifications | 用 GPT-3 反向翻译扩充训练样本，微调 CodeT5，并依据 LP 规则重评和修正候选输出。 | 方法 · 模型 · 基础 | [![Paper][badge-049]][resource-316] · [详情](#paper-synth2023) |
| 2023 · arXiv preprint | **Holy Grail 2.0**<br>Holy Grail 2.0: From Natural Language to Constraint Models | 讨论把自然语言转为约束模型的分解式提示流程，并报告 GPT 模型的早期结果。 | 方法 · 基础 | [![Paper][badge-049]][resource-317] · [详情](#paper-kadioglu2023holygrail) |
| 2023 · arXiv preprint | **Multi-stage MILP Synthesis**<br>Synthesizing mixed-integer linear programming models from natural language descriptions | 以变量识别、约束／目标分类和模板构建合成 MILP，并扩展 NL4Opt 的逻辑约束与二元变量问题。 | 方法 · 数据 | [![Paper][badge-049]][resource-318] · [![Modeling Data][badge-119]][resource-077] · [详情](#paper-li2023synthesizing) |
| 2023 · NeurIPS 2022 Competition Track / PMLR 220 | **NL4Opt**（核心）<br>NL4Opt Competition: Formulating Optimization Problems Based on Their Natural Language Descriptions | 将自然语言优化任务分为实体识别与中间形式生成，提供 LP 文字题与竞赛评测。 | 基准 · 数据 · 基础 | [![Paper 1][badge-051]][resource-319] · [![arXiv][badge-087]][resource-320] · [![Code][badge-022]][resource-020] · [详情](#paper-ramamonjison2023nl4opt) |
| 2023 · arXiv preprint | **NL4Opt: Auto-Formulation Approach**<br>A Novel Approach for Auto-Formulation of Optimization Problems | 在 NL4Opt 竞赛的实体识别和公式生成两任务中，结合预训练、对抗训练、提示和模型集成。 | 方法 · 基础 | [![Paper][badge-049]][resource-321] · [![Code][badge-022]][resource-322] · [详情](#paper-iflytek2023autoformulation) |
| 2023 · arXiv preprint; NL4Opt competition system | **OPD@NL4Opt**<br>OPD@NL4Opt: An ensemble approach for the NER task of the optimization problem | 对预训练语言模型使用差分学习率、对抗训练与集成，完成优化问题描述中的命名实体识别。 | 方法 · 基础 | [![Paper][badge-049]][resource-323] · [![竞赛结果（相关）][badge-120]][resource-324] · [详情](#paper-wang2023opdnl4opt) |
| 2023 · arXiv preprint | **OptiGuide**（核心）<br>Large Language Models for Supply Chain Optimization | OptiGuide 将自然语言 what-if 查询转成对现有优化程序的分析，解释供应链决策结果。 | 方法 · 应用 | [![Paper][badge-049]][resource-325] · [![Code][badge-022]][resource-256] · [详情](#paper-li2023optiguide) |
| 2022 · EMNLP 2022 Industry | **Auto-formulation (2022)**（核心）<br>Augmenting Operations Research with Auto-Formulation of Optimization Models From Problem Descriptions | 以受控生成从问题描述建议优化模型，并通过交互界面供用户校验与修改。 | 方法 · 基准 · 数据 · 基础 | [![Paper][badge-057]][resource-326] · [![Code & Data（NL4Opt）][badge-121]][resource-020] · [详情](#paper-ramamonjison2022augmenting) |

[返回目录](#contents)

<a id="code"></a>

## 优化代码生成、执行与修复

生成求解器代码，利用执行反馈调试，检查可行性与建模错误。

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · ICML 2026 | **A2DEPT**<br>A2DEPT: Large Language Model-Driven Automated Algorithm Design via Evolutionary Program Trees | 以树结构演化、混合选择和分层操作搜索完整算法，并通过执行反馈修复程序。 | 方法 | [![Publication][badge-053]][resource-327] · [![Paper 2][badge-074]][resource-328] · [![Paper 3][badge-075]][resource-329] · [详情](#paper-chen2026a2dept) |
| 2026 · ICLR 2026 | **AFL**<br>An Agentic Framework with LLMs for Solving Complex Vehicle Routing Problems | 由四个专门 Agent 从原始 VRP 输入自主生成并协调修正求解程序。 | 方法 · 应用 | [![Publication][badge-053]][resource-330] · [![Paper 2][badge-074]][resource-331] · [![Paper 3][badge-075]][resource-332] · [![Code][badge-022]][resource-333] · [详情](#paper-zhang2026afl) |
| 2026 · arXiv preprint | **Agentic MIP Research**<br>Agentic MIP Research: Accelerated Constraint Handler Generation | 用求解器感知的 Agent 工作环境恢复全局约束结构，并生成 SCIP 传播型约束处理器。 | 方法 | [![Paper][badge-049]][resource-334] · [详情](#paper-xu2026agenticmip) |
| 2026 · arXiv preprint | **Agora-Opt**<br>From Soliloquy to Agora: Memory-Enhanced LLM Agents with Decentralized Debate for Optimization Modeling | 由多个 Agent 团队独立建模并开展结果驱动辩论，以读写记忆复用求解经验和分歧修订。 | 方法 · 数据 | [![Paper][badge-049]][resource-103] · [![Code & Cleaned Data][badge-050]][resource-083] · [详情](#paper-soliloquy2026) |
| 2026 · LION 19 / LNCS 15745（2026 出版） | **CHORUS**<br>CHORUS: Zero-shot Hierarchical Retrieval and Orchestration for Generating Linear Programming Code | 用分层文档切分、元数据检索和重排，为 LLM 生成 Gurobi LP 代码提供相关知识。 | 方法 · 基准 · 数据 | [![Publication][badge-053]][resource-107] · [![Paper 2][badge-052]][resource-108] · [详情](#paper-lporch2025) |
| 2026 · arXiv preprint | **CIR / R2C**<br>Canonical Intermediate Representation for LLM-based optimization problem formulation and code generation | 以规范中间表示编码复杂规则，再检索知识并生成约束实现。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-109] · [详情](#paper-canonicalir2026) |
| 2026 · Findings of EMNLP 2026 | **Constraint Injection / VRPCoder**<br>Beyond Objective Equivalence: Constraint Injection for LLM-Based Optimization Modeling on Vehicle Routing Problems | 用可行解和单约束违反解测试 VRP 代码，补充最优值相同仍可能漏约束的检查。 | 方法 · 基准 · 数据 · 模型 · 应用 | [![Publication][badge-053]][resource-335] · [![Paper 2][badge-052]][resource-336] · [![Benchmark Data][badge-122]][resource-025] · [详情](#paper-constraintinjection2026) |
| 2026 · arXiv preprint | **COOPA**<br>COOPA: A Modular LLM Agent Architecture for Operations Research Problems | 迭代比较候选公式的置信度，追踪建模元素的来源，再路由至适用求解器 Agent。 | 方法 | [![Paper][badge-049]][resource-112] · [![Code][badge-022]][resource-113] · [详情](#paper-coopa2026) |
| 2026 · LLM4Code 2026 Workshop @ ICSE | **CP-Agent**<br>CP-Agent: Agentic Constraint Programming | 通过持久 IPython 内核和简短领域提示，执行并迭代修正约束模型。 | 方法 · 数据 | [![Paper 1][badge-051]][resource-114] · [![Paper 2][badge-052]][resource-115] · [![Author Coding Agent（相关）][badge-054]][resource-116] · [![Evaluation Archive v2][badge-055]][resource-087] · [详情](#paper-cpagent2025) |
| 2026 · arXiv preprint | **CP-SynC**<br>CP-SynC: Multi-Agent Zero-Shot Constraint Modeling in MiniZinc with Synthesized Checkers | 由建模、检查与选择 Agent 并行探索 MiniZinc 模型，并合成语义检查器聚合证据。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-117] · [![Benchmark & Evaluation][badge-056]][resource-028] · [详情](#paper-cpsync2026) |
| 2026 · arXiv preprint | **DScheLLM**<br>DScheLLM: Enabling Dynamic Scheduling through a Fine-Tuned Dual-System Large language Model | 用求解器排程合成快／慢思考示范，LoRA 微调双系统 LLM 应对动态扰动。 | 方法 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-337] · [详情](#paper-zhang2026dschellm) |
| 2026 · arXiv preprint | **EVOM**<br>Execution-Verified Reinforcement Learning for Optimization Modeling | 以求解器执行结果训练建模 LLM，并研究 Gurobi、OR-Tools 与 COPT 间的迁移。 | 方法 · 模型 | [![Paper][badge-049]][resource-120] · [详情](#paper-guan2026evom) |
| 2026 · arXiv preprint | **EvoOpt-LLM**<br>EvoOpt-LLM: Evolving industrial optimization models with large language models | 以 7B 模型和 LoRA 支持工业 MILP 的模型构建、新业务约束注入与变量剪枝。 | 方法 · 模型 | [![Paper][badge-049]][resource-121] · [![Code][badge-022]][resource-122] · [详情](#paper-he2026evoopt) |
| 2026 · arXiv preprint | **EvoOR-Agent**<br>Co-evolving Agent Architectures and Interpretable Reasoning for Automated Optimization | 以 AOE 图表示建模—求解工作流，共同演化 Agent 架构与可解释推理路径。 | 方法 | [![Paper][badge-049]][resource-125] · [详情](#paper-coevolve2026) |
| 2026 · arXiv preprint | **Falsification-Based Verification**<br>Falsification-Based Verification of LLM-Generated Optimization Models: Sound Test Batteries and Their Detection Limits | 通过数值角色扰动、对偶与敏感性关系测试生成模型，并刻画可检测错误与盲区。 | 方法 | [![Paper][badge-049]][resource-338] · [详情](#paper-li2026falsification) |
| 2026 · arXiv；NeurIPS 2026 Workshop 版本 | **Formalize, Don't Optimize**<br>Formalize, Don't Optimize: The Heuristic Trap in LLM-Generated Combinatorial Solvers | 用 CP-SynC-XL 比较原生搜索、Python 求解器 API 与 MiniZinc，并审计搜索优化带来的错误。 | 基准 · 数据 | [![Paper 1][badge-058]][resource-126] · [![Workshop][badge-059]][resource-127] · [详情](#paper-wang2026formalize) |
| 2026 · EMNLP 2026 | **FormuEvo**<br>FormuEvo: LLM-Guided Evolution for Discovering Solver-Efficient Mixed-Integer Programming Formulations | 在建模程序空间演化更强的 MIP 表达，以求解器统计诊断和结构化记忆指导改写。 | 方法 | [![Publication][badge-053]][resource-128] · [![Paper 2][badge-052]][resource-129] · [![Code][badge-022]][resource-130] · [详情](#paper-yuan2026formuevo) |
| 2026 · arXiv preprint | **LEAN-LLM-OPT**<br>Large-Scale Optimization Model Auto-Formulation: Harnessing LLM Flexibility via Structured Workflow | 动态构建建模工作流并将数据处理交给工具，面向大规模优化和航空收入管理。 | 方法 · 基准 · 数据 · 应用 | [![Paper][badge-049]][resource-134] · [![Code][badge-022]][resource-038] · [详情](#paper-liang2026leanllmopt) |
| 2026 · IEEE TEVC 30（2026） | **LLaMoCo**<br>LLaMoCo: Instruction Tuning of Large Language Models for Optimization Code Generation | 构造问题—优化代码指令集，以对比学习预热和指令微调训练从问题代码生成优化程序的模型。 | 方法 · 模型 · 数据 | [![Paper 1][badge-051]][resource-339] · [![Paper 2][badge-052]][resource-340] · [![LLaMoCo-S Example][badge-123]][resource-341] · [![LLaMoCo-S][badge-124]][resource-001] · [详情](#paper-ma2024llamoco) |
| 2026 · Expert Systems with Applications 330（2026-12 编期） | **MeLA**<br>MeLA: A metacognitive LLM-driven architecture for automatic heuristic design | 通过问题分析、错误诊断和元认知搜索演化生成启发式的提示，而非仅对代码做变异。 | 方法 | [![Paper 1][badge-051]][resource-342] · [![Paper 2][badge-052]][resource-343] · [详情](#paper-chen2025mela) |
| 2026 · arXiv preprint | **MILP-Evo**<br>MILP-Evo: Closed-Loop Fully Automatic Design of MILP Solvers | 在 PySCIPOpt 中联合演化割选择与分支回调，结合执行修复、诊断反思和多样性维护。 | 方法 | [![Paper][badge-049]][resource-344] · [详情](#paper-milpevo2026) |
| 2026 · arXiv preprint | **MIND**<br>Automated Optimization Modeling via a Localizable Error-Driven Perspective | 依据建模错误的局部性合成针对性训练问题，并用 DFPO 对困难样本做局部修订。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-138] · [详情](#paper-mind2026) |
| 2026 · arXiv preprint | **MiniOpt**<br>MiniOpt: Reasoning to Model and Solve General Optimization Problems with Limited Resources | 以结构化推理连接建模和代码生成，用分层 OptReward 同时反馈公式与解的质量。 | 方法 · 模型 | [![Paper][badge-049]][resource-139] · [![Code][badge-022]][resource-140] · [详情](#paper-zhao2026miniopt) |
| 2026 · arXiv preprint | **MIRROR**<br>MIRROR: A Multi-Agent Framework with Iterative Adaptive Revision and Hierarchical Retrieval for Optimization Modeling in Operations Research | 通过执行驱动的迭代修订与分层检索，获取建模和代码示例来修复优化模型。 | 方法 | [![Paper][badge-049]][resource-144] · [详情](#paper-mirror2026) |
| 2026 · NeurIPS 2026（已接收，待出版） | **MM-OptBench**<br>MM-OptBench: A Solver-Grounded Benchmark for Multimodal Optimization Modeling | 以文本和表格、图、地图等视觉输入评测优化公式与求解器代码生成。 | 基准 · 数据 | [![Paper 1][badge-051]][resource-145] · [![Paper 2][badge-052]][resource-146] · [详情](#paper-zhu2026mmoptbench) |
| 2026 · ICML 2026 · PMLR 306 | **NEMO**<br>NEMO: Execution-Aware Optimization Modeling via Autonomous Coding Agents | 用自主编码 Agent 生成优化器与模拟器，再以交叉执行、经验复用和候选一致性改进建模。 | 方法 | [![Paper 1][badge-051]][resource-148] · [![Paper 2][badge-052]][resource-149] · [![Evaluation Artifacts][badge-064]][resource-096] · [详情](#paper-nemo2026) |
| 2026 · ICML 2026 · PMLR 306 | **OPT-Engine**<br>OPT-Engine: Benchmarking the Limits of LLMs in Optimization Modeling via Complexity Scaling | 可控地扩展 OR 问题复杂度，比较文本推理、工具调用与求解器集成。 | 基准 · 数据 | [![Paper 1][badge-051]][resource-150] · [![Paper 2][badge-052]][resource-151] · [![Code][badge-022]][resource-050] · [![Dataset][badge-060]][resource-049] · [详情](#paper-chen2026optengine) |
| 2026 · arXiv preprint | **OptArgus**（探索性）<br>OptArgus: A Multi-Agent System to Detect Hallucinations in LLM-based Optimization Modeling | 用幻觉分类法和专家 Agent 审计问题描述、数学模型与求解器实现的一致性。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-345] · [详情](#paper-optarcus2026) |
| 2026 · arXiv preprint | **OptGraph**<br>OptGraph: Large Language Models Enhanced Evolutionary Optimization Via Graph Retrieval-Augmented Generation | 将建模模式、公式、实现和错误修订组织成类型图，以邻域检索和运行轨迹更新支持优化建模。 | 方法 | [![Paper][badge-049]][resource-155] · [![Code][badge-022]][resource-156] · [详情](#paper-xiu2026optgraph) |
| 2026 · arXiv preprint | **OptiAgent**<br>OptiAgent: End-to-End Optimization Modeling via Multi-Agent Iterative Refinement | 通过专门建模 Agent 与多层反馈循环，提取变量和约束并修正公式及可执行代码。 | 方法 | [![Paper][badge-049]][resource-158] · [详情](#paper-optiagent2026) |
| 2026 · INFORMS Journal on Data Science 5(3):199–220 | **OptiChat**<br>OptiChat: Bridging Optimization Models and Practitioners with Large Language Models | 用自然语言查询已有优化模型，支持不可行诊断、敏感性、what-if 和反事实解释。 | 方法 · 数据 | [![Paper 1][badge-051]][resource-159] · [![Paper 2][badge-052]][resource-160] · [![Code][badge-022]][resource-098] · [详情](#paper-chen2025optichat) |
| 2026 · arXiv preprint | **OptiDSL**<br>Not All Problems Are Best Modeled as MILP: A DSL-Centric Framework for Flexible and Accurate Optimization Modeling | 将自然语言映射为领域 DSL，再接入专用求解器，避免所有问题强制采用 MILP。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-161] · [详情](#paper-dslmilp2026) |
| 2026 · arXiv preprint | **OptiLoop**<br>OptiLoop: Coordination-in-the-Loop Verification and Repair for LLM-Generated Optimization Agents | 在有限轮 ADMM 式协同中测试本地优化 Agent，利用行为与静态证据修复实现或公式。 | 方法 | [![Paper][badge-049]][resource-346] · [详情](#paper-optiloop2026) |
| 2026 · arXiv preprint | **OptiRepair**（探索性）<br>OptiRepair: Closed-Loop Diagnosis and Repair of Supply Chain Optimization Models with LLM Agents | 以 IIS 与运营合理性检查构建两阶段供应链修复闭环，提出 OptiRepair-SC 并训练 P1 / P2 模型。 | 方法 · 基准 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-347] · [详情](#paper-optirepair2026) |
| 2026 · Findings of EMNLP 2026 | **OptSkills**<br>OptSkills: Learning Generalizable Optimization Skills from Problem Archetypes via Cluster-Based Distillation | 按问题原型聚类，从成功建模轨迹提炼、检索并更新可复用的工作流技能。 | 方法 | [![Publication][badge-053]][resource-164] · [![Paper 2][badge-052]][resource-165] · [![Code 1][badge-070]][resource-166] · [![Code 2][badge-071]][resource-167] · [![官方技能库（相关）][badge-048]][resource-102] · [详情](#paper-yang2026optskills) |
| 2026 · AAAI 2026 | **OR-R1**<br>OR-R1: Automating Modeling and Solving of Operations Research Optimization Problem via Test-Time Reinforcement Learning | 先用少量有标签数据 SFT，再以测试时 TGRPO 从未标注问题和求解一致性中学习。 | 方法 · 模型 | [![Paper 1][badge-051]][resource-169] · [![Paper 2][badge-052]][resource-170] · [![Code][badge-022]][resource-171] · [详情](#paper-ding2026orr1) |
| 2026 · arXiv preprint | **OR-Space**<br>OR-Space: A Full-Lifecycle Workspace Benchmark for Industrial Optimization Agents | 用持久多文件工作区评测模型构建、需求变更和基于证据的解释三类生命周期任务。 | 基准 · 数据 | [![Paper][badge-049]][resource-172] · [![Code][badge-022]][resource-057] · [![Dataset][badge-060]][resource-056] · [详情](#paper-zhou2026orspace) |
| 2026 · arXiv preprint | **ORAgentBench**<br>ORAgentBench: Can LLM Agents Solve Challenging Operations Research Tasks End to End? | 在隔离工作环境中评测从业务说明、多文件材料到可验证决策的完整 OR 任务。 | 基准 · 数据 | [![Paper][badge-049]][resource-173] · [![Code][badge-022]][resource-058] · [详情](#paper-oragentbench2026) |
| 2026 · ICML 2026 | **ORLoopBench**<br>ORLoopBench: Solver-in-the-Loop Benchmarks for Self-Correction and Behavioral Rationality in Operations Research | 以 IIS 和求解器重执行定义不可行模型修复闭环，配套 ORDebug 与 ORBias 评测。 | 方法 · 基准 · 数据 · 模型 | [![Publication][badge-053]][resource-348] · [![Paper 2][badge-052]][resource-349] · [![数据与校验代码][badge-125]][resource-060] · [详情](#paper-ao2026orloopbench) |
| 2026 · NeurIPS 2026（已接收，待出版） | **PEARL**（核心）<br>PEARL: Solver-in-the-Loop Interactive Optimization Modeling from Natural Language | 在多轮工具调用中执行、调试和修订优化模型，用求解器反馈训练交互建模策略。 | 方法 · 模型 | [![Paper 1][badge-058]][resource-177] · [![Conference][badge-072]][resource-178] · [![Code][badge-022]][resource-179] · [![Model][badge-073]][resource-009] · [详情](#paper-lu2026pearl) |
| 2026 · ICML 2026 | **ProOPF**<br>ProOPF: Benchmarking and Improving LLMs for Professional-Grade Power Systems Optimization Modeling | 构建专业最优潮流建模数据和基准，区分参数调整与结构扩展难度。 | 基准 · 数据 · 应用 | [![Publication][badge-053]][resource-180] · [![Paper 2][badge-074]][resource-181] · [![Paper 3][badge-075]][resource-182] · [![Evaluation Code & Data][badge-076]][resource-064] · [详情](#paper-shen2026proopf) |
| 2026 · arXiv preprint | **RAG for Optimization & CP Modeling**<br>Optimization and Constraint Modeling using LLMs with a Retrieval Augmented Generation Process | 从 Text2Zinc 种子和角色描述合成 500 个问题，以检索示例辅助 LLM 生成优化与约束模型代码。 | 方法 · 数据 | [![Paper][badge-049]][resource-183] · [详情](#paper-roy2026rag) |
| 2026 · NeurIPS 2026（已接收，待出版） | **ReLoop / RetailOpt-190**（探索性）<br>ReLoop: Structured Modeling and Behavioral Verification for Reliable LLM-Based Optimization | 结合结构化建模链与求解器参数扰动检查，定位静默错误并实施诊断引导修复。 | 方法 · 基准 · 数据 | [![Paper 1][badge-058]][resource-350] · [![Conference][badge-072]][resource-351] · [![Code][badge-022]][resource-352] · [![Dataset][badge-060]][resource-065] · [详情](#paper-lian2026reloop) |
| 2026 · arXiv preprint | **RLEA**<br>Reinforcement Learning Enhanced LLM Agents for Complex Vehicle Routing Problems | 以 Soft Q-learning 训练轻量 Planner 调度 LLM Agent，结合记忆与检索完成复杂 VRP 建模。 | 方法 · 应用 | [![Paper][badge-049]][resource-353] · [![Appendix（相关）][badge-126]][resource-354] · [详情](#paper-rlvrpagents2026) |
| 2026 · ICML 2026 · PMLR 306 | **SAC-Opt**<br>SAC-Opt: Semantic Anchors for Iterative Correction in Optimization Modeling | 把生成代码回译为语义锚点，与原始需求对齐后定点修正约束和目标。 | 方法 | [![Paper 1][badge-051]][resource-184] · [![Paper 2][badge-052]][resource-185] · [![Code][badge-022]][resource-186] · [详情](#paper-ma2025sacopt) |
| 2026 · ICML 2026 · PMLR 306 | **SAGE (Strategy-Aware Modeling)**<br>Strategy-Aware Optimization Modeling with Reasoning LLMs | 生成并筛选多策略建模示范，经 SFT 与 Segment-Weighted GRPO 兼顾公式正确性和求解效率。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-187] · [![Paper 2][badge-052]][resource-188] · [![Code][badge-022]][resource-189] · [![SAGE SFT 100K][badge-077]][resource-080] · [详情](#paper-strategyaware2026) |
| 2026 · arXiv preprint | **SDRL**<br>LLMs as Adaptive Meta-Solvers: Strategy-Diverse RL for Industrial-Scale Optimization | 用正确性门控的层次多样性奖励，训练模型在求解器、精确组合算法和启发式之间适配策略。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-190] · [![Benchmark Inference][badge-078]][resource-191] · [![SDRL Qwen3 4B][badge-079]][resource-010] · [详情](#paper-sdrl2026) |
| 2026 · International Journal of Production Research（2026 在线） | **SMILO**<br>An LLM-powered MILP modelling engine for workforce scheduling guided by expert knowledge | 结合专家建模图、LLM 信息抽取与模板生成劳动力排班 MILP。 | 方法 · 应用 | [![Paper 1][badge-051]][resource-192] · [![Paper 2][badge-052]][resource-193] · [详情](#paper-li2025smilo) |
| 2026 · arXiv preprint | **SOLID**<br>Beyond Verified Answers: Solver-Informed Self-Distillation for Bootstrapping Operations Research Language Models | 从多次求解 rollout 的目标聚类构建伪参考，以求解器产物做无真值的自蒸馏后训练。 | 方法 · 模型 | [![Paper][badge-049]][resource-194] · [![Code][badge-022]][resource-195] · [![SOLID-Qwen3][badge-080]][resource-015] · [![SOLID-StepORLM][badge-081]][resource-016] · [详情](#paper-solid2026) |
| 2026 · Findings of EMNLP 2026 | **SOVER / NLEquiv-150**<br>SOVER: Formal Certification of Optimization Reformulations via LLM-Assisted SMT Verification | 由 LLM 提取重构映射，再用 Z3 或 dReal 核验公式之间的可行性及目标关系。 | 方法 · 基准 · 数据 | [![Publication][badge-053]][resource-355] · [![Paper 2][badge-052]][resource-356] · [![Code][badge-022]][resource-068] · [![EquivaFormulation（使用）（相关）][badge-127]][resource-032] · [![NLP4LP（使用）（相关）][badge-128]][resource-051] · [详情](#paper-bhattacharyya2026sover) |
| 2026 · ICLR 2026 | **StepORLM**（核心）<br>StepORLM: A Self-Evolving Framework With Generative Process Supervision For Operations Research Language Models | 让策略模型与生成式过程奖励模型共同演化，融合求解器结果反馈和全程评价。 | 方法 · 模型 | [![Paper 1][badge-051]][resource-357] · [![arXiv][badge-087]][resource-358] · [![Code][badge-022]][resource-359] · [![Policy 8B][badge-009]][resource-017] · [![GenPRM 8B][badge-010]][resource-018] · [详情](#paper-zhou2026steporlm) |
| 2026 · arXiv preprint | **Text2Model**<br>Text2Model: Modeling Copilots for Text-to-Model Translation | 提供面向 MiniZinc 的多种建模 Copilot、交互编辑器与在线排行榜。 | 方法 · 平台 | [![Paper][badge-049]][resource-196] · [![Code][badge-022]][resource-197] · [![Text2Zinc（复用）][badge-082]][resource-069] · [![Editor（相关）][badge-083]][resource-198] · [![Leaderboard（相关）][badge-084]][resource-199] · [![Python Package（相关）][badge-085]][resource-200] · [详情](#paper-text2model2026) |
| 2026 · ICML 2026 · PMLR 306 | **VeriSimpl**<br>VeriSimpl: Robust Optimization Modeling from Natural Language using Simplification-based Verification | 用求解器构造简化诊断问题，帮助 LLM 检查模型是否符合自然语言题意。 | 方法 | [![Publication][badge-053]][resource-201] · [![Paper 2][badge-052]][resource-202] · [![Conference][badge-072]][resource-203] · [![官方项目（仅 README）（相关）][badge-086]][resource-204] · [详情](#paper-verisimpl2026) |
| 2025 · NeurIPS 2025 ScaleOpt Workshop / arXiv | **AlphaOPT**<br>AlphaOPT: Formulating Optimization Programs with Self-Improving LLM Experience Library | 通过求解器反馈提炼并演化可检索的建模经验库，无需更新 LLM 参数。 | 方法 | [![Paper 1][badge-051]][resource-205] · [![Paper 2][badge-052]][resource-206] · [![Code][badge-022]][resource-207] · [详情](#paper-kong2025alphaopt) |
| 2025 · FedCSIS 2025 · ACSIS 43 | **C-DSS**<br>Toward Conversational Decision Support Systems: Integrating LLMs in the Operations Research Methodology | 提出对话式决策支持架构，比较建模、AMPL 编码、RAG 和验证角色的不同组合。 | 方法 | [![Paper 1][badge-051]][resource-214] · [![Paper 2][badge-074]][resource-215] · [详情](#paper-kaleta2025cdss) |
| 2025 · arXiv preprint | **DPLM / DP-Bench**<br>Auto-Formulating Dynamic Programming Problems with Large Language Models | 提出 DP-Bench，并用双向反思合成训练数据，训练从自然语言构造动态规划模型的 DPLM。 | 方法 · 基准 · 数据 · 模型 | [![Paper][badge-049]][resource-225] · [详情](#paper-dpdlm2025) |
| 2025 · ICLR 2025 | **DRoC**<br>DRoC: Elevating Large Language Models for Complex Vehicle Routing via Decomposed Retrieval of Constraints | 分解复杂 VRP 的约束并分别检索文档，动态选择 RAG 或自调试生成求解器程序。 | 方法 · 数据 · 应用 | [![Publication][badge-053]][resource-226] · [![Paper 2][badge-074]][resource-227] · [![Code][badge-022]][resource-088] · [详情](#paper-jiang2025droc) |
| 2025 · arXiv preprint | **EASE**<br>Solve it with EASE | 以模块化生成、测试、分析和评价循环支持算法方案演化，允许多个 LLM 承担互补角色。 | 方法 · 平台 | [![Paper][badge-049]][resource-360] · [![Framework][badge-129]][resource-361] · [![Frontend][badge-130]][resource-362] · [详情](#paper-viktorin2025ease) |
| 2025 · arXiv preprint | **Gala**<br>Gala: Global LLM Agents for Text-to-Model Translation | 按全局约束类型分工 Agent，再由组装 Agent 合成完整 MiniZinc 模型。 | 方法 | [![Paper][badge-049]][resource-233] · [![Gala in Text2Model][badge-092]][resource-197] · [![Author Project（相关）][badge-093]][resource-234] · [详情](#paper-globalconstraint2025) |
| 2025 · ICLR 2025 | **LLMOPT**（核心）<br>LLMOPT: Learning to Define and Solve General Optimization Problems from Scratch | 通过五要素形式化、多指令微调与自纠错，提高多类优化问题的建模与代码生成泛化。 | 方法 · 模型 | [![Paper 1][badge-051]][resource-239] · [![arXiv][badge-087]][resource-240] · [![Code][badge-022]][resource-241] · [![Model][badge-073]][resource-002] · [详情](#paper-jiang2025llmopt) |
| 2025 · Findings NAACL 2025 | **Mamo**（核心）<br>LLMs for Mathematical Modeling: Towards Bridging the Gap between Natural and Mathematical Languages | 提出 Mamo，以求解器辅助的过程评估研究语言到数学建模，涵盖 LP、MILP 与 ODE。 | 基准 · 数据 | [![Paper 1][badge-058]][resource-244] · [![Paper 2][badge-074]][resource-245] · [![Code][badge-022]][resource-040] · [![Dataset（第三方镜像）][badge-096]][resource-041] · [详情](#paper-huang2024mamo) |
| 2025 · NeurIPS 2025 | **MM-Agent / MM-Bench（数学建模）**（探索性）<br>MM-Agent: LLM as Agents for Real-world Mathematical Modeling Problem | 将数学建模拆为问题分析、模型构造、计算求解和报告生成，并提供 MCM/ICM 来源的 MM-Bench。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-246] · [![Paper 2][badge-052]][resource-247] · [![Paper 3][badge-097]][resource-248] · [![Code & MM-Bench][badge-098]][resource-043] · [![Expert Skills (2026 add-on)][badge-099]][resource-101] · [![HF Demo（相关）][badge-100]][resource-249] · [详情](#paper-liu2025mmagent) |
| 2025 · Findings of EMNLP 2025 | **ModelingAgent / ModelingBench**（探索性）<br>ModelingAgent: Bridging LLMs and Mathematical Modeling for Real-World Challenges | 用多 Agent 协调工具和迭代修订处理开放式建模，并以 ModelingBench 与 ModelingJudge 评估报告。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-250] · [![Paper 2][badge-052]][resource-251] · [![Code & ModelingBench][badge-101]][resource-044] · [详情](#paper-qian2025modelingagent) |
| 2025 · arXiv preprint | **MOID**<br>Multi-Objective Infeasibility Diagnosis for Routing Problems Using Large Language Models | 联合路径成本与约束违反量做多目标优化，再由 LLM 分析一组可恢复可行性的调整建议。 | 方法 · 数据 · 应用 | [![Paper][badge-049]][resource-252] · [![Diagnosis Data][badge-102]][resource-095] · [详情](#paper-moid2025) |
| 2025 · NeurIPS 2025 Main Conference Track, volume 38 | **MURKA**<br>MURKA: Multi-Reward Reinforcement Learning with Knowledge Alignment for Optimization Tasks | 用多奖励强化学习与知识蒸馏对齐 Extractor、Solver、Checker 三类 Agent，支持从文本到可执行优化程序。 | 方法 | [![Paper][badge-057]][resource-253] · [详情](#paper-xie2025murka) |
| 2025 · arXiv preprint | **OptimAI**<br>OptimAI: Optimization from Natural Language Using LLM-Powered AI Agents | 以建模、规划、编码和代码批评角色协作求解，并用 UCB 调度调试与备选计划。 | 方法 | [![Paper][badge-049]][resource-254] · [详情](#paper-thind2025optimai) |
| 2025 · arXiv preprint | **OptiMind**（核心）<br>OptiMind: Teaching LLMs to Think Like Optimization Experts | 用按优化问题类别组织的专家错误分析指导训练与推理，减少 MILP 形式化常见错误。 | 方法 · 模型 | [![Paper][badge-049]][resource-255] · [![Code][badge-022]][resource-256] · [![Model][badge-073]][resource-005] · [详情](#paper-zhang2025optimind) |
| 2025 · arXiv preprint | **OptiTrust**<br>Toward a Trustworthy Optimization Modeling Agent via Verifiable Synthetic Data Generation | 从带已知最优解的符号问题合成示范，用跨建模语言投票和分步推理训练建模 Agent。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-260] · [详情](#paper-lima2025optitrust) |
| 2025 · arXiv preprint | **OR-LLM-Agent / BWOR**<br>OR-LLM-Agent: Automating Modeling and Solving of Operations Research Optimization Problems with Reasoning LLM | 将建模、代码生成与调试分配给推理 Agent，并提出 BWOR 评测集。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-262] · [![Code][badge-022]][resource-263] · [![Dataset][badge-060]][resource-055] · [详情](#paper-zhang2025bwor) |
| 2025 · Operations Research 73(6):2986–3009 | **ORLM**（核心）<br>ORLM: A Customizable Framework in Training Large Models for Automated Optimization Modeling | 通过 OR-Instruct 合成数据训练优化领域模型，并提出工业基准 IndustryOR。 | 方法 · 基准 · 数据 · 模型 | [![Paper 1][badge-058]][resource-266] · [![Journal][badge-104]][resource-267] · [![Code][badge-022]][resource-268] · [![Model][badge-073]][resource-008] · [![IndustryOR][badge-024]][resource-059] · [![OR-Instruct-3K][badge-032]][resource-079] · [详情](#paper-huang2025orlm) |
| 2025 · ACL 2025 Industry Track | **ORMind**<br>ORMind: A Cognitive-Inspired End-to-End Reasoning Framework for Operations Research | 以认知启发的角色协作、执行修复和反事实检查完成优化建模。 | 方法 | [![Paper 1][badge-051]][resource-269] · [![Paper 2][badge-052]][resource-270] · [![Code][badge-022]][resource-271] · [详情](#paper-ormind2025) |
| 2025 · arXiv preprint | **Re-evaluating Heuristic Search: 3D Packing**<br>Re-evaluating LLM-based Heuristic Search: A Case Study on the 3D Packing Problem | 以约束脚手架和自修复支持 3D 装箱程序生成，分析搜索偏向评分函数及紧约束下的局限。 | 评测分析 | [![Paper][badge-049]][resource-363] · [![Study Code][badge-131]][resource-364] · [详情](#paper-quan2025reeval3d) |
| 2025 · arXiv preprint | **RedAHD**<br>RedAHD: Reduction-Based End-to-End Automatic Heuristic Design with Large Language Models | 让 LLM 设计问题与解的归约，将原组合问题变为更熟悉的问题，再演化求解启发式。 | 方法 | [![Paper][badge-049]][resource-365] · [详情](#paper-thach2025redahd) |
| 2025 · ICLR 2025 | **ReSocratic / OptiBench**（核心）<br>OptiBench Meets ReSocratic: Measure and Improve LLMs for Optimization Modeling | 先合成数学形式与求解示范再逆向生成问题，配套 OptiBench 与 ReSocratic-29k。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-274] · [![arXiv][badge-087]][resource-275] · [![Code][badge-022]][resource-066] · [详情](#paper-yang2025resocratic) |
| 2025 · NeurIPS 2025 | **SIRL**（核心）<br>Solver-Informed RL: Grounding Large Language Models for Authentic Optimization Modeling | 用求解器检查代码及 LP 实例，构造 RL 可验证奖励，并发布模型与修订评测数据。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-276] · [![arXiv][badge-087]][resource-277] · [![Code][badge-022]][resource-278] · [![Model Gurobi-7B][badge-005]][resource-011] · [![Model COPT-7B][badge-006]][resource-012] · [![Model Gurobi-32B][badge-007]][resource-013] · [![Model COPT-32B][badge-008]][resource-014] · [![修订评测集][badge-045]][resource-099] · [详情](#paper-chen2025sirl) |
| 2025 · NeurIPS 2025 | **SolverLLM**<br>SolverLLM: Leveraging Test-Time Scaling for Optimization Problem via LLM-Guided Search | 用动态扩展的 MCTS 搜索公式和求解器代码，以提示和不确定性回传指导测试时探索。 | 方法 | [![Paper 1][badge-051]][resource-279] · [![Paper 2][badge-052]][resource-280] · [详情](#paper-solverllm2025) |
| 2025 · NeurIPS 2025 | **STRCMP**<br>STRCMP: Integrating Graph Structural Priors with Language Models for Combinatorial Optimization | 将图神经网络的结构先验接入语言模型，通过训练和演化生成求解器专用算法代码。 | 方法 · 模型 | [![Paper 1][badge-051]][resource-366] · [![Paper 2][badge-052]][resource-367] · [![Code][badge-022]][resource-368] · [详情](#paper-li2025strcmp) |
| 2025 · arXiv preprint | **Validation-in-the-Loop Power Modeling**（探索性）<br>From Natural Language to Solver-Ready Power System Optimization: An LLM-Assisted, Validation-in-the-Loop Framework | 通过领域提示、结构化 schema、可行性校验与迭代修复生成电力优化模型。 | 方法 · 应用 | [![Paper][badge-049]][resource-285] · [详情](#paper-nl2ps2025) |
| 2024 · NeurIPS 2024 MATH-AI Workshop | **CAFA**<br>CAFA: Coding as Auto-Formulation Can Boost Large Language Models in Solving Linear Programming Problem | 用紧凑提示直接生成调用优化求解器的 Python 程序，执行求解线性规划问题。 | 方法 | [![Paper][badge-057]][resource-288] · [![Code][badge-022]][resource-289] · [详情](#paper-deng2024cafa) |
| 2024 · INFOR 62(4):599–617 | **Multi-Stage Modeling & Verification**<br>Optimization modeling and verification from problem specifications using a multi-agent multi-stage LLM framework | 分阶段从问题规格生成数学模型与 Zimpl 代码，并由多个 LLM Agent 交叉检查。 | 方法 · 基准 · 数据 | [![Paper][badge-057]][resource-298] · [详情](#paper-mostajabdaveh2024multiagent) |
| 2024 · INFOR 2024 | **OptiChat / Infeasibility Diagnosis**<br>Diagnosing Infeasible Optimization Problems Using Large Language Models | 通过 GPT-4、求解器 IIS 与对话界面解释不可行原因，并建议模型修复。 | 方法 | [![Paper 1][badge-058]][resource-369] · [![Publication][badge-053]][resource-370] · [![Code][badge-022]][resource-098] · [详情](#paper-chen2023diagnosing) |
| 2024 · ICML 2024 | **OptiMUS**（核心）<br>OptiMUS: Scalable Optimization Modeling with (MI)LP Solvers and Large Language Models | 用模块化 Agent 完成 MILP 建模、代码生成、调试与评估，同时发布 NLP4LP。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-302] · [![arXiv][badge-087]][resource-303] · [![Code][badge-022]][resource-304] · [![Dataset][badge-060]][resource-051] · [详情](#paper-teshnizi2024optimus) |
| 2024 · NAACL 2024 Industry Track | **OptLLM**<br>Solving General Natural-Language-Description Optimization Problems with Large Language Models | 通过多轮澄清、公式与代码转换、外部求解器和结果解释支持自然语言优化，并微调 Qwen。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-305] · [![Paper 2][badge-052]][resource-306] · [![MindOpt Trial (International)（相关）][badge-112]][resource-307] · [![MindOpt Trial (CN)（相关）][badge-113]][resource-308] · [详情](#paper-zhang2024optllm) |
| 2024 · arXiv preprint | **RAGDyS**<br>Automated Conversion of Static to Dynamic Scheduler via Natural Language | 从既有静态排程模型出发，用检索增强生成按自然语言约束实施动态排程修改。 | 方法 · 应用 | [![Paper][badge-049]][resource-309] · [详情](#paper-tang2024ragdys) |
| 2024 · EMNLP 2024 System Demonstrations | **To the Globe / TTG**<br>To the Globe (TTG): Towards Language-Driven Guaranteed Travel Planning | 将旅行需求译为符号表示，再由 MILP 求解器生成满足已编码约束的行程。 | 方法 · 应用 · 模型 | [![Paper 1][badge-051]][resource-310] · [![Paper 2][badge-052]][resource-311] · [详情](#paper-ju2024ttg) |
| 2023 · arXiv preprint | **AI-Copilot for Business Optimisation**<br>Language Models for Business Optimisation with a Real World Case Study in Production Scheduling | 微调成本较低的 LLM 生成优化公式，并在真实生产排程案例中评估。 | 方法 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-312] · [![Training Data][badge-114]][resource-070] · [![Generated Formulations（相关）][badge-115]][resource-313] · [![Industrial Case Data][badge-116]][resource-071] · [![Industrial Outputs（相关）][badge-117]][resource-314] · [![LPWP Evaluation Data（相关）][badge-118]][resource-315] · [详情](#paper-alahakoon2023copilot) |
| 2023 · arXiv preprint | **LLMs for Power Engineering**（探索性）<br>LLM-based Frameworks for Power Engineering from Routine to Novel Tasks | 对常规电力优化编程采用端到端流程，对新任务采用工程师参与的分解与代码合成。 | 方法 · 应用 | [![Paper][badge-049]][resource-371] · [详情](#paper-li2023power) |
| 2023 · arXiv preprint | **OptiGuide**（核心）<br>Large Language Models for Supply Chain Optimization | OptiGuide 将自然语言 what-if 查询转成对现有优化程序的分析，解释供应链决策结果。 | 方法 · 应用 | [![Paper][badge-049]][resource-325] · [![Code][badge-022]][resource-256] · [详情](#paper-li2023optiguide) |

[返回目录](#contents)

<a id="algorithms"></a>

## 求解器增强与算法设计

改进求解器组件、邻域、启发式、元启发式与算法配置。

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · ICML 2026 | **A2DEPT**<br>A2DEPT: Large Language Model-Driven Automated Algorithm Design via Evolutionary Program Trees | 以树结构演化、混合选择和分层操作搜索完整算法，并通过执行反馈修复程序。 | 方法 | [![Publication][badge-053]][resource-327] · [![Paper 2][badge-074]][resource-328] · [![Paper 3][badge-075]][resource-329] · [详情](#paper-chen2026a2dept) |
| 2026 · ICLR 2026 | **AFL**<br>An Agentic Framework with LLMs for Solving Complex Vehicle Routing Problems | 由四个专门 Agent 从原始 VRP 输入自主生成并协调修正求解程序。 | 方法 · 应用 | [![Publication][badge-053]][resource-330] · [![Paper 2][badge-074]][resource-331] · [![Paper 3][badge-075]][resource-332] · [![Code][badge-022]][resource-333] · [详情](#paper-zhang2026afl) |
| 2026 · arXiv preprint | **Agentic MIP Research**<br>Agentic MIP Research: Accelerated Constraint Handler Generation | 用求解器感知的 Agent 工作环境恢复全局约束结构，并生成 SCIP 传播型约束处理器。 | 方法 | [![Paper][badge-049]][resource-334] · [详情](#paper-xu2026agenticmip) |
| 2026 · arXiv preprint | **AILS-AHD**<br>Enhancing CVRP Solver through LLM-driven Automatic Heuristic Design | 在自适应迭代局部搜索中演化 ruin 启发式，并结合 LLM 辅助加速改善 CVRP 求解。 | 方法 · 应用 | [![Paper][badge-049]][resource-372] · [详情](#paper-xie2026ailsahd) |
| 2026 · arXiv preprint | **Automated Inventory Policy Design**<br>Automated Design of Inventory Policy with Large Language Models: An Exploratory Study | 让 LLM 迭代生成库存策略函数类，再由外部优化器在类内调参并反馈成本。 | 方法 · 应用 | [![Paper][badge-049]][resource-373] · [详情](#paper-invpolicy2026) |
| 2026 · Nature Communications（2026） | **AutoModSAT**<br>Discovering heuristics in a complex SAT solver with large language models | 结合模块化 SAT 求解器、提示优化和进化搜索，发现复杂求解器中的有效启发式。 | 方法 · 数据 | [![Paper 1][badge-051]][resource-374] · [![Paper 2][badge-052]][resource-375] · [![Code Archive][badge-132]][resource-376] · [![Evaluation Data][badge-133]][resource-084] · [详情](#paper-sun2025satheur) |
| 2026 · JAIR 86（2026） | **AutoSAT**<br>AutoSAT: Automatically Optimize SAT Solvers via Large Language Models | 在模块化 CDCL 求解器中搜索并替换启发式，以 LLM 生成代码并迭代评估。 | 方法 | [![Paper 1][badge-051]][resource-377] · [![Paper 2][badge-052]][resource-378] · [![Code][badge-022]][resource-379] · [详情](#paper-sun2024autosat) |
| 2026 · arXiv preprint | **BiFE**<br>BiFE: Search-Efficient Discovery of CPU-Only Branching Policies via LLM-based Bi-Fidelity Evolution | 用低保真模仿评分预筛分支规则，再对精英候选运行高保真 B&B 评估。 | 方法 | [![Paper][badge-049]][resource-380] · [详情](#paper-bife2026) |
| 2026 · ICLR 2026 | **CALM (Algorithm–LM Co-evolution)**<br>CALM: Co-evolution of Algorithms and Language Model for Automatic Heuristic Design | 用生成启发式的质量作 RL 信号，共同演化候选算法与底层语言模型。 | 方法 · 模型 | [![Paper 1][badge-051]][resource-381] · [![Paper 2][badge-052]][resource-382] · [![Code][badge-022]][resource-383] · [详情](#paper-huang2025calm) |
| 2026 · AAAI 2026 | **CO-Bench**（核心）<br>CO-Bench: Benchmarking Language Model Agents in Algorithm Search for Combinatorial Optimization | 提供组合优化算法搜索基准，比较 LLM Agent 与人工设计算法。 | 基准 · 数据 | [![Proceedings][badge-105]][resource-384] · [![Paper 2][badge-052]][resource-385] · [![Code][badge-022]][resource-386] · [![Dataset][badge-060]][resource-024] · [详情](#paper-sun2026cobench) |
| 2026 · Inteligencia Artificial 29（2026） | **Combinatorial Optimization for All**<br>Combinatorial Optimization for All: Using LLMs to Aid Non-Experts in Improving Optimization Algorithms | 以较少专业知识的提示改进十种已有 TSP 算法，比较解质量、运行时间和代码复杂度。 | 方法 · 评测分析 | [![Paper 1][badge-051]][resource-387] · [![Paper 2][badge-074]][resource-388] · [![Paper 3][badge-075]][resource-389] · [![Prompts & Algorithms][badge-134]][resource-390] · [![Project（相关）][badge-135]][resource-391] · [详情](#paper-co4all2025) |
| 2026 · ACM Computing Surveys 58（2026） | **Combinatorial Optimization Systematic Review**<br>Large Language Models for Combinatorial Optimization: A Systematic Review | 按 PRISMA 流程筛选 LLM 组合优化研究，归纳任务、模型架构、评测数据与应用领域。 | 综述 | [![Paper 1][badge-051]][resource-110] · [![Paper 2][badge-052]][resource-111] · [详情](#paper-lco2026review) |
| 2026 · arXiv preprint | **DSevolve**<br>DSevolve: Enabling Real-Time Adaptive Scheduling on Dynamic Flexible Job Shop with LLM-Evolved Heuristic Portfolios | 离线演化互补排程规则库，再用状态条件神经选择器在线响应柔性车间扰动。 | 方法 · 应用 | [![Paper][badge-049]][resource-392] · [详情](#paper-dsevolve2026) |
| 2026 · arXiv preprint | **EPOCH**<br>EPOCH: Coverage-Aware Evolution with Experiential Preference Optimization for LLM-based Automated Heuristic Design | 以实例覆盖选择互补启发式，并用教师反思形成偏好对，通过 DPO 与反思自蒸馏更新生成器。 | 方法 · 模型 | [![Paper][badge-049]][resource-393] · [详情](#paper-epoch2026) |
| 2026 · ICIST 2026（已接收；论文集待确认） | **ES-AHD**<br>ES-AHD: An Evolution Strategy Framework for Automatic Heuristic Design | 让 LLM 从精英程序提取语义中心，并通过带动量的温度采样调节搜索范围。 | 方法 | [![Paper 1][badge-058]][resource-394] · [![Conference][badge-072]][resource-395] · [![Code][badge-022]][resource-396] · [详情](#paper-es2026ahd) |
| 2026 · arXiv preprint | **Evo-B&B**<br>Evo-B&B: Behavior-Aware LLM-Guided Joint Evolution of Branching and Node Selection Policies for MILP | 用 SCIP 端到端反馈联合演化分支与节点选择策略，并按行为相似性维护多样性。 | 方法 | [![Paper][badge-049]][resource-397] · [详情](#paper-chen2026evobb) |
| 2026 · arXiv preprint | **EvoOpt-LLM**<br>EvoOpt-LLM: Evolving industrial optimization models with large language models | 以 7B 模型和 LoRA 支持工业 MILP 的模型构建、新业务约束注入与变量剪枝。 | 方法 · 模型 | [![Paper][badge-049]][resource-121] · [![Code][badge-022]][resource-122] · [详情](#paper-he2026evoopt) |
| 2026 · EMNLP 2026 | **FormuEvo**<br>FormuEvo: LLM-Guided Evolution for Discovering Solver-Efficient Mixed-Integer Programming Formulations | 在建模程序空间演化更强的 MIP 表达，以求解器统计诊断和结构化记忆指导改写。 | 方法 | [![Publication][badge-053]][resource-128] · [![Paper 2][badge-052]][resource-129] · [![Code][badge-022]][resource-130] · [详情](#paper-yuan2026formuevo) |
| 2026 · NeurIPS 2026（已接收，待出版） | **FrontierOR**<br>FrontierOR: Benchmarking LLMs' Capacity for Efficient Algorithm Design in Large-Scale Optimization | 评测 LLM 在文献驱动的大规模 OR 任务中生成高效且可行算法的能力。 | 基准 · 数据 | [![Paper 1][badge-051]][resource-131] · [![Paper 2][badge-052]][resource-132] · [![Code][badge-022]][resource-034] · [![Dataset][badge-060]][resource-033] · [详情](#paper-kong2026frontieror) |
| 2026 · arXiv preprint | **Full-Component ALNS Evolution**<br>Large Language Model-Driven Full-Component Evolution of Adaptive Large Neighborhood Search | 拆分并演化 ALNS 的七类组件，以多维精英档案兼顾解质量和策略多样性。 | 方法 | [![Paper][badge-049]][resource-398] · [![Evolved ALNS（相关）][badge-136]][resource-399] · [详情](#paper-yu2026alns) |
| 2026 · arXiv preprint | **G-LNS**<br>G-LNS: Generative Large Neighborhood Search for LLM-Based Automatic Heuristic Design | 共同演化 LNS 的 destroy／repair 算子对，以协作评估捕捉破坏与修复的互补关系。 | 方法 | [![Paper][badge-049]][resource-400] · [![Code][badge-022]][resource-401] · [详情](#paper-zhao2026glns) |
| 2026 · arXiv preprint | **GRIMIP**<br>GRIMIP: A General Framework for Instance-Specific Configuration of MIP Solvers Using LLMs | 将 LLM 作为贝叶斯优化中的概率代理，为具体 MIP 实例搜索求解器配置。 | 方法 | [![Paper][badge-049]][resource-402] · [详情](#paper-luo2026grimip) |
| 2026 · ICLR 2026 | **HeuriGym**<br>HeuriGym: An Agentic Benchmark for LLM-Crafted Heuristics in Combinatorial Optimization | 让 LLM 通过代码运行反馈迭代生成组合优化启发式，并联合衡量质量与有效产出。 | 基准 · 平台 | [![Publication][badge-053]][resource-403] · [![Paper 2][badge-052]][resource-404] · [![Code][badge-022]][resource-035] · [![Leaderboard（相关）][badge-137]][resource-405] · [详情](#paper-chen2025heurigym) |
| 2026 · ICLR 2026 | **HiFo-Prompt**<br>HiFo-Prompt: Prompting with Hindsight and Foresight for LLM-based Automatic Heuristic Design | 用事后知识池积累启发式设计原则，并依群体动态选择面向未来的搜索提示。 | 方法 | [![Paper 1][badge-051]][resource-406] · [![Paper 2][badge-052]][resource-407] · [![Code][badge-022]][resource-408] · [详情](#paper-chen2025hifoprompt) |
| 2026 · arXiv preprint | **Infeasibility-Aware CO Models**<br>Infeasibility Aware Large Language Models for Combinatorial Optimization | 用精确优化与可认证筛选构建可行／不可行训练样本，微调模型输出解或不可行判断，再辅助局部搜索。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-409] · [![Author Code / Data Archive（相关）][badge-138]][resource-073] · [详情](#paper-infeasibilityaware2026) |
| 2026 · arXiv preprint | **InvEvolve**（探索性）<br>InvEvolve: Evolving White-Box Inventory Policies via Large Language Models with Performance Guarantees | 用 LLM 演化白盒库存策略，并以置信区间认证框架研究部署安全与性能改进。 | 方法 · 应用 | [![Paper][badge-049]][resource-410] · [详情](#paper-invevolve2026) |
| 2026 · arXiv preprint | **LaGO**<br>Heuristic Search as Language-Guided Program Optimization | 将启发式发现拆为执行评价、语言分析反馈和程序更新三个模块，支持独立改进组件。 | 方法 | [![Paper][badge-049]][resource-411] · [详情](#paper-hsplo2026) |
| 2026 · LION 20 / 2026（已接收；论文集待确认） | **Latent Heuristic Search**<br>Latent Heuristic Search: Continuous Optimization for Automated Algorithm Design | 学习程序编码、性能代理、可逆流和软提示映射，在连续潜空间中优化并解码为启发式。 | 方法 | [![Paper 1][badge-058]][resource-412] · [![Conference][badge-072]][resource-413] · [![Code][badge-022]][resource-414] · [详情](#paper-latentheuristic2026) |
| 2026 · IEEE TEVC 30（2026） | **LLaMoCo**<br>LLaMoCo: Instruction Tuning of Large Language Models for Optimization Code Generation | 构造问题—优化代码指令集，以对比学习预热和指令微调训练从问题代码生成优化程序的模型。 | 方法 · 模型 · 数据 | [![Paper 1][badge-051]][resource-339] · [![Paper 2][badge-052]][resource-340] · [![LLaMoCo-S Example][badge-123]][resource-341] · [![LLaMoCo-S][badge-124]][resource-001] · [详情](#paper-ma2024llamoco) |
| 2026 · arXiv preprint | **LLM Agents for Efficient Frontiers**<br>LLM Agents for Combinatorial Efficient Frontiers: Investment Portfolio Optimization | 用 Agent 自动化基数约束均值—方差投资组合的启发式开发及有效前沿构建。 | 方法 · 应用 | [![Paper][badge-049]][resource-415] · [详情](#paper-efficientfrontier2026) |
| 2026 · NeurIPS 2026 MLxOR Workshop（已接收，待召开） | **LLM MIP Configuration**<br>Automating MIP Solver Configuration with Large Language Models | 根据求解器反馈迭代提出 MIP 参数设置，并聚合为问题类级别配置。 | 方法 | [![Paper][badge-057]][resource-416] · [详情](#paper-zhang2026autoconfig) |
| 2026 · Computers & Operations Research 196（2026-12 编期） | **LLM Representations for Algorithm Selection**<br>Behavior and representation in open-weight Large Language Models for combinatorial optimization: From feature extraction to algorithm selection | 在冻结的开源 LLM 上比较显式特征提取、隐藏层探测和逐实例算法选择的可用信息。 | 评测分析 | [![Paper 1][badge-051]][resource-417] · [![Paper 2][badge-052]][resource-418] · [![Code & Analysis Data][badge-139]][resource-091] · [详情](#paper-behaviorrep2025) |
| 2026 · IJCAI 2026 · AI4Tech | **LLM-guided Cutting-plane Management**<br>LLM-guided Cutting-plane Management for Mixed-integer Linear Programming | 结合实例级分离器配置与求解阶段感知的割选择，减少 MILP 求解中的人工调参。 | 方法 | [![Paper][badge-057]][resource-419] · [![Code][badge-022]][resource-420] · [详情](#paper-zheng2026cutmgmt) |
| 2026 · ACM Computing Surveys 58(8), Article 218 | **LLM4AD Survey**（核心）<br>A Systematic Survey on Large Language Models for Algorithm Design | 从优化器、预测器、抽取器和设计器四种角色综述 LLM 算法设计。 | 综述 | [![Paper 1][badge-058]][resource-421] · [![Journal][badge-104]][resource-422] · [![官方资源库（相关）][badge-094]][resource-423] · [详情](#paper-liu2024systematic) |
| 2026 · ICML 2026 | **LLM4Branch**（探索性）<br>LLM4Branch: Large Language Model for Discovering Efficient Branching Policies of Integer Programs | 让 LLM 生成分支策略程序骨架，再用端到端求解反馈优化参数。 | 方法 | [![Publication][badge-053]][resource-424] · [![Paper 2][badge-052]][resource-425] · [![Code][badge-022]][resource-426] · [详情](#paper-llm4branch2026) |
| 2026 · MIPRO 2026 | **LLMs as Optimizers Survey**<br>Large Language Models as Optimizers: A Survey of Direct vs. Tool-Augmented Approaches and Their Performance Frontiers | 区分直接优化、调用工具优化和创造可复用工具三种范式，比较文献中的性能边界。 | 综述 | [![Publication][badge-053]][resource-427] · [![Paper 2][badge-052]][resource-428] · [详情](#paper-llmasopt2026) |
| 2026 · IEEE CIM（期刊记录；出版日期未确认） | **LLMs for Evolutionary Optimization Survey**<br>A Systematic Survey on Large Language Models for Evolutionary Optimization: From Modeling to Solving | 从建模到求解梳理 LLM 与进化优化，区分直接优化、算法内部辅助与高层算法设计。 | 综述 | [![Journal record][badge-061]][resource-135] · [![Paper 2][badge-052]][resource-136] · [![Literature Collection（相关）][badge-062]][resource-137] · [详情](#paper-sysevo2025) |
| 2026 · arXiv preprint | **MeEvo**<br>MeEvo: Metacognitive Evolution Combined with Natural Evolution for Automatic Heuristic Design | 交替执行代码重组／变异和基于推理历史的元认知反思，把两阶段结果反馈到下一轮。 | 方法 | [![Paper][badge-049]][resource-429] · [![Code][badge-022]][resource-430] · [详情](#paper-meevo2026) |
| 2026 · Expert Systems with Applications 330（2026-12 编期） | **MeLA**<br>MeLA: A metacognitive LLM-driven architecture for automatic heuristic design | 通过问题分析、错误诊断和元认知搜索演化生成启发式的提示，而非仅对代码做变异。 | 方法 | [![Paper 1][badge-051]][resource-342] · [![Paper 2][badge-052]][resource-343] · [详情](#paper-chen2025mela) |
| 2026 · arXiv preprint | **MILP-Evo**<br>MILP-Evo: Closed-Loop Fully Automatic Design of MILP Solvers | 在 PySCIPOpt 中联合演化割选择与分支回调，结合执行修复、诊断反思和多样性维护。 | 方法 | [![Paper][badge-049]][resource-344] · [详情](#paper-milpevo2026) |
| 2026 · ICLR 2026 | **MoH**<br>Generalizable Heuristic Generation Through LLMs with Meta-Optimization | 演化可自调用的元优化程序，让其构造启发式优化器，再为多个下游问题演化启发式。 | 方法 | [![Paper 1][badge-051]][resource-431] · [![Paper 2][badge-052]][resource-432] · [![Code][badge-022]][resource-433] · [![CO Task Data][badge-140]][resource-094] · [详情](#paper-moh2025) |
| 2026 · AAAI 2026 | **MPaGE**<br>Pareto-Grid-Guided Large Language Models for Fast and High-Quality Heuristics Design in Multi-Objective Combinatorial Optimization | 用 Pareto 前沿网格和语义聚类指导 LLM 启发式演化，兼顾多目标质量、速度与多样性。 | 方法 | [![Paper 1][badge-051]][resource-434] · [![Paper 2][badge-052]][resource-435] · [![Code][badge-022]][resource-436] · [详情](#paper-ha2025paretogrid) |
| 2026 · arXiv preprint | **Multi-Warehouse Formulation Selection**<br>Large Language Model for Operations Research Formulation Selection in Multi-Warehouse Inventory Allocation | 在多仓库存分配中选择适合实例的 MIP 公式专家，并用求解质量反馈训练选择器。 | 方法 · 模型 · 应用 | [![Paper][badge-049]][resource-147] · [详情](#paper-warehouseformsel2026) |
| 2026 · arXiv preprint | **OptiDSL**<br>Not All Problems Are Best Modeled as MILP: A DSL-Centric Framework for Flexible and Accurate Optimization Modeling | 将自然语言映射为领域 DSL，再接入专用求解器，避免所有问题强制采用 MILP。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-161] · [详情](#paper-dslmilp2026) |
| 2026 · NeurIPS 2026（已接收，待出版） | **PALL**<br>Process-Aware LNS for Large-Scale MILP via Context-Enhanced Fine-Tuned LLM-driven Selector | 离线演化 LNS 算子组合，以 hindsight oracle 轨迹微调 8B LLM 在线选择器。 | 方法 · 模型 | [![Paper][badge-057]][resource-437] · [详情](#paper-yan2026pall) |
| 2026 · ICML 2026 · PMLR 306 | **PathWise**<br>PathWise: Planning through World Model for Automated Heuristic Design via Self-Evolving LLMs | 在保存搜索历史的蕴含图上规划演化动作，由策略、世界模型和评论 Agent 协作生成启发式。 | 方法 | [![Paper 1][badge-051]][resource-438] · [![Paper 2][badge-052]][resource-439] · [![Code][badge-022]][resource-440] · [详情](#paper-pathwise2026) |
| 2026 · AAMAS 2026 | **PyVRP+ / MEP**<br>PyVRP+: LLM-Driven Metacognitive Heuristic Evolution for Hybrid Genetic Search in Vehicle Routing Problems | 通过 Reason–Act–Reflect 诊断和设计假设，演化 HGS 中的路由启发式组件。 | 方法 · 应用 | [![Paper 1][badge-051]][resource-441] · [![Paper 2][badge-052]][resource-442] · [![Proceedings][badge-105]][resource-443] · [详情](#paper-pyvrpplus2026) |
| 2026 · arXiv preprint | **SDRL**<br>LLMs as Adaptive Meta-Solvers: Strategy-Diverse RL for Industrial-Scale Optimization | 用正确性门控的层次多样性奖励，训练模型在求解器、精确组合算法和启发式之间适配策略。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-190] · [![Benchmark Inference][badge-078]][resource-191] · [![SDRL Qwen3 4B][badge-079]][resource-010] · [详情](#paper-sdrl2026) |
| 2026 · ICLR 2026 | **ShinkaEvolve**<br>ShinkaEvolve: Towards Open-Ended and Sample-Efficient Program Evolution | 结合父代采样、代码新颖性拒绝采样和 bandit 模型选择，提高程序演化的样本效率。 | 方法 · 平台 | [![Paper 1][badge-051]][resource-444] · [![Paper 2][badge-052]][resource-445] · [![Code][badge-022]][resource-446] · [详情](#paper-lange2026shinka) |
| 2026 · arXiv preprint | **SpecAHD**<br>SpecAHD: Localize to Specialize for Automated Heuristic Design in Large-Scale Routing Problems | 以双层搜索共同选择局部修复区域，并演化适配区域差异的互补启发式库。 | 方法 · 应用 | [![Paper][badge-049]][resource-447] · [详情](#paper-lai2026specahd) |
| 2026 · arXiv preprint | **SPO**<br>SPO: Discovering Adaptive Large Neighborhood Search Operators via Stackelberg Program Optimization | 按 Stackelberg 主从关系发现状态依赖的 destroy / repair 程序，并共同更新程序种群与生成器。 | 方法 · 模型 · 应用 | [![Paper][badge-049]][resource-448] · [详情](#paper-spo2026) |
| 2026 · arXiv preprint | **TIDE**<br>TIDE: Tuning-Integrated Dynamic Evolution for LLM-Based Automated Heuristic Design | 用外层岛模型搜索程序结构，内层差分变异调整数值参数，再由 UCB 调度提示策略。 | 方法 | [![Paper][badge-049]][resource-449] · [详情](#paper-chen2026tide) |
| 2026 · Transactions on Machine Learning Research（2026） | **VRPAgent**<br>VRPAgent: LLM-Driven Discovery of Heuristic Operators for Vehicle Routing Problems | 将 LLM 生成的路由算子嵌入共享 LNS 框架，以带代码长度惩罚的遗传搜索改进候选。 | 方法 · 应用 | [![Paper 1][badge-051]][resource-450] · [![Paper 2][badge-052]][resource-451] · [![Generated Operators（相关）][badge-141]][resource-452] · [详情](#paper-vrpagent2025) |
| 2025 · Technical report | **AlphaEvolve**（核心）<br>AlphaEvolve: A coding agent for scientific and algorithmic discovery | 用 LLM 与进化式代码修改闭环改进算法，覆盖科学问题及计算基础设施优化。 | 方法 | [![Paper][badge-049]][resource-453] · [![官方结果（相关）][badge-142]][resource-454] · [![官方问题集（相关）][badge-143]][resource-455] · [详情](#paper-novikov2025alphaevolve) |
| 2025 · arXiv preprint | **ARS / RoutBench**（核心）<br>ARS: Automatic Routing Solver with Large Language Models | 根据问题描述生成约束感知的路由启发式，配套多变体 VRP 基准 RoutBench。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-456] · [![Code][badge-022]][resource-019] · [详情](#paper-li2025ars) |
| 2025 · EvoApplications 2025 · LNCS | **Beyond the Hype: Bin Packing**<br>Beyond the Hype: Benchmarking LLM-Evolved Heuristics for Bin Packing | 跨广泛装箱实例与多种指标复评 LLM 演化启发式，并分析各算法优势所在的实例区域。 | 评测分析 · 数据 | [![Paper 1][badge-051]][resource-457] · [![Paper 2][badge-052]][resource-458] · [![Evaluation Data][badge-133]][resource-085] · [详情](#paper-sim2025beyondhype) |
| 2025 · GECCO 2025 Workshop / Companion | **BLADE**<br>BLADE: Benchmark suite for LLM-driven Automated Design and Evolution of iterative optimisation heuristics | 为 LLM 自动算法发现提供连续黑箱优化问题、实例生成、标准日志及行为分析工具。 | 基准 · 平台 | [![Paper 1][badge-051]][resource-459] · [![Paper 2][badge-052]][resource-460] · [![Code][badge-022]][resource-021] · [详情](#paper-vanstein2025blade) |
| 2025 · arXiv preprint | **CEoH**<br>Leveraging Large Language Models to Develop Heuristics for Emerging Optimization Problems | 在 EoH 提示中加入问题上下文，为仓储单元载荷预翻垛等较少研究的任务发现启发式。 | 方法 · 应用 | [![Paper][badge-049]][resource-461] · [![Code][badge-022]][resource-462] · [详情](#paper-bomer2025emerging) |
| 2025 · CPAIOR 2025 | **Cold-Start Separator Configuration**<br>LLMs for Cold-Start Cutting Plane Separator Configuration | 根据问题描述及分离器文档生成配置，再聚类集成为小规模配置组合。 | 方法 | [![Paper 1][badge-058]][resource-463] · [![Publication][badge-053]][resource-464] · [![Code][badge-022]][resource-465] · [详情](#paper-lawless2024cuts) |
| 2025 · arXiv preprint | **DHEvo**<br>DHEvo: Data-Algorithm Based Heuristic Evolution for Generalizable MILP Solving | 共同演化代表性实例与 diving 启发式，提高同类 MILP 实例内的泛化能力。 | 方法 | [![Paper][badge-049]][resource-466] · [详情](#paper-dheevo2025) |
| 2025 · arXiv preprint | **EASE**<br>Solve it with EASE | 以模块化生成、测试、分析和评价循环支持算法方案演化，允许多个 LLM 承担互补角色。 | 方法 · 平台 | [![Paper][badge-049]][resource-360] · [![Framework][badge-129]][resource-361] · [![Frontend][badge-130]][resource-362] · [详情](#paper-viktorin2025ease) |
| 2025 · arXiv preprint | **EFS**<br>Evolutionary Factor Searching for Sparse Portfolio Optimization Using Large Language Models | 用 LLM 与进化搜索产生排序因子，并结合去冗余权重分配构建稀疏投资组合。 | 方法 · 应用 | [![Paper][badge-049]][resource-467] · [详情](#paper-luo2025efs) |
| 2025 · arXiv preprint | **FunSearch for Unit Commitment**（探索性）<br>Automated Heuristic Design for Unit Commitment Using Large Language Models | 将 LLM 程序搜索与评估器用于机组组合启发式自动设计。 | 方法 · 应用 | [![Paper][badge-049]][resource-468] · [详情](#paper-ucfunsearch2025) |
| 2025 · arXiv preprint | **HeurAgenix**<br>HeurAgenix: Leveraging LLMs for Solving Complex Combinatorial Optimization Challenges | 先生成与演化启发式库，再按问题状态选择算子；选择器可采用通用 LLM 或领域微调模型。 | 方法 · 模型 | [![Paper][badge-049]][resource-469] · [![Code][badge-022]][resource-470] · [![CO Instances][badge-144]][resource-089] · [详情](#paper-yang2025heuragenix) |
| 2025 · AAAI 2025 | **HSEvo**<br>HSEvo: Elevating Automatic Heuristic Design with Diversity-Driven Harmony Search and Genetic Algorithm Using LLMs | 以多样性指标分析启发式演化，并将和声搜索与遗传搜索结合改善探索。 | 方法 · 评测分析 | [![Paper 1][badge-051]][resource-471] · [![Paper 2][badge-052]][resource-472] · [![Code][badge-022]][resource-473] · [详情](#paper-dat2024hsevo) |
| 2025 · arXiv preprint | **InstSpecHH**<br>LLM-Driven Instance-Specific Heuristic Generation and Selection | 按实例特征划分子类，离线演化专门启发式，并通过 LLM 或轻量分类器选择适用算法。 | 方法 | [![Paper][badge-049]][resource-474] · [详情](#paper-zhang2025instspechh) |
| 2025 · IEEE CEC 2025 | **LHNS**<br>LLM-Driven Neighborhood Search for Efficient Heuristic Design | 以启发式程序的邻域搜索组织 LLM 改写，设计三种搜索方式以降低发现成本。 | 方法 | [![Paper 1][badge-051]][resource-475] · [![Paper 2][badge-074]][resource-476] · [![LLM4AD: LHNS][badge-145]][resource-477] · [详情](#paper-xie2025llmns) |
| 2025 · IEEE TEVC 29(2):331–345 | **LLaMEA**（核心）<br>LLaMEA: A Large Language Model Evolutionary Algorithm for Automatically Generating Metaheuristics | 通过 LLM 自动生成、变异及选择元启发式，用运行评价反馈持续改进算法。 | 方法 | [![Paper][badge-049]][resource-478] · [![Code][badge-022]][resource-479] · [详情](#paper-vanstein2024llamea) |
| 2025 · arXiv preprint | **LLM Algorithm-search Fitness Landscapes**<br>Fitness Landscape of Large Language Model-Assisted Automated Algorithm Search | 以算法为节点、LLM 转换为边构造图景，跨任务和模型研究搜索崎岖性及相似性。 | 评测分析 | [![Paper][badge-049]][resource-480] · [详情](#paper-liu2025fitness) |
| 2025 · arXiv preprint | **LLM Heuristic Behaviour-space Analysis**<br>Behaviour Space Analysis of LLM-driven Meta-heuristic Discovery | 比较 LLaMEA 的提示变体，在 BBOB 上记录探索、利用、收敛和停滞等行为指标。 | 评测分析 | [![Paper][badge-049]][resource-481] · [![Behaviour Metrics Code][badge-146]][resource-482] · [详情](#paper-vanstein2025behaviour) |
| 2025 · arXiv preprint | **LLM-discovered EDDC / MDDC**<br>Discovering Heuristics with Large Language Models (LLMs) for Mixed-Integer Programs: Single-Machine Scheduling | 用 LLM 与进化流程发现单机总拖期启发式 EDDC 和 MDDC，按解质量与时间比较经典规则。 | 方法 · 应用 | [![Paper][badge-049]][resource-483] · [![Code][badge-022]][resource-484] · [详情](#paper-cetinkaya2025mipsmtt) |
| 2025 · ICML 2025 | **LLM-LNS**（核心）<br>Large Language Model-driven Large Neighborhood Search for Large-Scale MILP Problems | 通过双层自演化 LLM Agent 设计 LNS 邻域策略，研究向大规模 MILP 的迁移。 | 方法 | [![Paper][badge-057]][resource-485] · [![Code][badge-022]][resource-486] · [详情](#paper-ye2025llmlns) |
| 2025 · arXiv preprint | **LLMs in OR: Methods & Challenges**<br>Large Language Models in Operations Research: Methods, Applications, and Challenges | 按自动建模、辅助优化和直接求解梳理 LLM 在运筹学中的方法与应用。 | 综述 | [![Paper][badge-049]][resource-243] · [详情](#paper-wang2025lor) |
| 2025 · EMNLP 2025 Main, pp. 19286–19304 | **MA-GTS / G-REAL**<br>MA-GTS: A Multi-Agent Framework for Solving Complex Graph Problems in Real-World Applications | 从隐式文本图信息恢复结构化图，并用多 Agent 根据问题约束及规模选择算法。 | 方法 · 基准 · 数据 | [![Paper 1][badge-058]][resource-487] · [![Paper 2][badge-074]][resource-488] · [![Code][badge-022]][resource-039] · [详情](#paper-yuan2025magts) |
| 2025 · ICML 2025 | **MCTS-AHD**（核心）<br>Monte Carlo Tree Search for Comprehensive Exploration in LLM-Based Automatic Heuristic Design | 将生成的启发式组织为 MCTS 搜索树，继续探索暂时低分候选的潜力。 | 方法 | [![Paper 1][badge-051]][resource-489] · [![arXiv][badge-087]][resource-490] · [![Code][badge-022]][resource-491] · [详情](#paper-zheng2025mctsahd) |
| 2025 · AAAI 2025 | **MEoH**<br>Multi-Objective Evolution of Heuristic Using Large Language Model | 在解质量、计算效率和可扩展性之间搜索 Pareto 启发式，并以支配关系和差异性选择候选。 | 方法 | [![Paper 1][badge-051]][resource-492] · [![Paper 2][badge-052]][resource-493] · [![LLM4AD: MEoH][badge-147]][resource-494] · [详情](#paper-yao2025meoh) |
| 2025 · ICLR 2025 | **MILP-Evolve**（核心）<br>Towards Foundation Models for Mixed Integer Linear Programming | 用 LLM 演化生成多样 MILP 类与实例，支持间隙预测、学习分支和语言对齐。 | 方法 · 数据 | [![Paper 1][badge-051]][resource-495] · [![arXiv][badge-087]][resource-496] · [![Code][badge-022]][resource-497] · [![Dataset][badge-060]][resource-076] · [![GitHub Data][badge-012]][resource-498] · [详情](#paper-li2025milpevolve) |
| 2025 · ICLR 2025 Agentic AI Workshop | **NCO-LLM for VRP**<br>Large Language Models powered Neural Solvers for Generalized Vehicle Routing Problems | 演化 LLM 生成的结构偏置并注入注意力分数，再微调 LEHD / POMO 神经路由策略。 | 方法 · 模型 · 应用 | [![Paper][badge-057]][resource-499] · [![Code][badge-022]][resource-500] · [详情](#paper-tran2025llmneural) |
| 2025 · arXiv preprint | **PAIR**<br>PAIR: A Novel Large Language Model-Guided Selection Strategy for Evolutionary Algorithms | 通过适应度、多样性与交叉兼容性提示 LLM 选择进化算法中的配对个体，并在 TSP 上评测。 | 方法 | [![Paper][badge-049]][resource-501] · [![Code][badge-022]][resource-502] · [详情](#paper-ali2025pair) |
| 2025 · arXiv preprint | **Re-evaluating Heuristic Search: 3D Packing**<br>Re-evaluating LLM-based Heuristic Search: A Case Study on the 3D Packing Problem | 以约束脚手架和自修复支持 3D 装箱程序生成，分析搜索偏向评分函数及紧约束下的局限。 | 评测分析 | [![Paper][badge-049]][resource-363] · [![Study Code][badge-131]][resource-364] · [详情](#paper-quan2025reeval3d) |
| 2025 · arXiv preprint | **RedAHD**<br>RedAHD: Reduction-Based End-to-End Automatic Heuristic Design with Large Language Models | 让 LLM 设计问题与解的归约，将原组合问题变为更熟悉的问题，再演化求解启发式。 | 方法 | [![Paper][badge-049]][resource-365] · [详情](#paper-thach2025redahd) |
| 2025 · arXiv preprint | **RoCo**<br>RoCo: Role-Based LLMs Collaboration for Automatic Heuristic Design | 用探索者、开发者、批评者和整合者四个角色协作生成、审查和修订启发式。 | 方法 | [![Paper][badge-049]][resource-503] · [详情](#paper-xu2025roco) |
| 2025 · arXiv（SAGE 修订版 2026） | **SAGE / 原 EvoCut**<br>LLM-Guided Evolution of Symbolic Acceleration Inequality Families for MILP | 用 LLM 与演化搜索发现可复用的 MILP 加速不等式，并按经验可接受性及性能筛选。 | 方法 | [![Paper][badge-049]][resource-504] · [![Code（EvoCut 旧版）][badge-148]][resource-505] · [![Code（SAGE v3）][badge-149]][resource-506] · [详情](#paper-yazdani2025evocut) |
| 2025 · NeurIPS 2025 | **STRCMP**<br>STRCMP: Integrating Graph Structural Priors with Language Models for Combinatorial Optimization | 将图神经网络的结构先验接入语言模型，通过训练和演化生成求解器专用算法代码。 | 方法 · 模型 | [![Paper 1][badge-051]][resource-366] · [![Paper 2][badge-052]][resource-367] · [![Code][badge-022]][resource-368] · [详情](#paper-li2025strcmp) |
| 2024 · arXiv preprint | **City-LEO**<br>City-LEO: Toward Transparent City Management Using LLM with End-to-End Optimization | 通过对话限定优化范围，并结合预测与优化管理共享电动自行车运营。 | 方法 · 应用 | [![Paper][badge-049]][resource-291] · [![Data & Code][badge-109]][resource-086] · [详情](#paper-jiao2024cityleo) |
| 2024 · ICML 2024 | **EoH**（核心）<br>Evolution of Heuristics: Towards Efficient Automatic Algorithm Design Using Large Language Model | 同步演化自然语言启发式思路和可执行代码，以性能反馈驱动自动算法设计。 | 方法 · 基础 | [![Paper 1][badge-051]][resource-507] · [![arXiv][badge-087]][resource-508] · [![Code][badge-022]][resource-509] · [详情](#paper-liu2024eoh) |
| 2024 · EMNLP 2024 Industry Track | **ITINERA**<br>ItiNera: Integrating Spatial Optimization with Large Language Models for Open-domain Urban Itinerary Planning | 分解城市漫步需求、选择兴趣点，并用聚类感知的空间优化排序与生成个性化行程。 | 方法 · 应用 | [![Paper 1][badge-051]][resource-293] · [![Paper 2][badge-052]][resource-294] · [![Code][badge-022]][resource-295] · [详情](#paper-tang2024itinerary) |
| 2024 · arXiv preprint | **LLM4AD**（核心）<br>LLM4AD: A Platform for Algorithm Design with Large Language Model | 提供模块化算法设计平台，统一搜索方法、任务、LLM 接口与评估沙箱。 | 平台 | [![Paper][badge-049]][resource-510] · [![Code][badge-022]][resource-494] · [详情](#paper-liu2024llm4ad) |
| 2024 · arXiv preprint | **LLM–EA Automated Optimization Insights**<br>Deep Insights into Automated Optimization with Large Language Models and Evolutionary Algorithms | 梳理 LLM 与进化算法的自动优化框架，分析表示、变异、适应度和提示设计。 | 综述 | [![Paper][badge-049]][resource-511] · [详情](#paper-yu2024deep) |
| 2024 · ICLR 2024 | **OPRO**（探索性）<br>Large Language Models as Optimizers | 根据历史候选及其数值评价提示 LLM 生成新解，研究直接优化与提示优化。 | 方法 · 基础 | [![Publication][badge-053]][resource-512] · [![Paper 2][badge-052]][resource-513] · [![Code][badge-022]][resource-514] · [详情](#paper-yang2024opro) |
| 2024 · arXiv preprint | **Rare MIP Challenges**<br>Leveraging Large Language Models for Solving Rare MIP Challenges | 结合微调、思维链与递归动态温度生成罕见 MIP 场景的可行解。 | 方法 | [![Paper][badge-049]][resource-515] · [详情](#paper-wang2024raremip) |
| 2024 · NeurIPS 2024 | **ReEvo**（核心）<br>ReEvo: Large Language Models as Hyper-Heuristics with Reflective Evolution | 结合进化搜索与 LLM 反思，用语言反馈指导超启发式程序改进。 | 方法 | [![Paper 1][badge-051]][resource-516] · [![arXiv][badge-087]][resource-517] · [![Code][badge-022]][resource-518] · [详情](#paper-ye2024reevo) |
| 2023 · arXiv preprint | **AEL**（核心）<br>Algorithm Evolution Using Large Language Model | 让 LLM 生成算法并在进化循环中选择改写，以 TSP 构造启发式展示算法级演化。 | 方法 · 基础 | [![Paper][badge-049]][resource-519] · [详情](#paper-liu2023ael) |
| 2023 · Nature（2023 在线发表） | **FunSearch**（核心）<br>Mathematical discoveries from program search with large language models | 结合 LLM 程序生成、进化搜索和自动评估，发现数学构造与装箱启发式。 | 方法 · 基础 | [![Paper][badge-057]][resource-520] · [![Code][badge-022]][resource-521] · [详情](#paper-romera2023funsearch) |

[返回目录](#contents)

<a id="agents"></a>

## OR Agents 与端到端系统

通过角色协作、工具调用、记忆与反馈闭环完成优化任务。

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · ICLR 2026 | **AFL**<br>An Agentic Framework with LLMs for Solving Complex Vehicle Routing Problems | 由四个专门 Agent 从原始 VRP 输入自主生成并协调修正求解程序。 | 方法 · 应用 | [![Publication][badge-053]][resource-330] · [![Paper 2][badge-074]][resource-331] · [![Paper 3][badge-075]][resource-332] · [![Code][badge-022]][resource-333] · [详情](#paper-zhang2026afl) |
| 2026 · arXiv preprint | **Agentic MIP Research**<br>Agentic MIP Research: Accelerated Constraint Handler Generation | 用求解器感知的 Agent 工作环境恢复全局约束结构，并生成 SCIP 传播型约束处理器。 | 方法 | [![Paper][badge-049]][resource-334] · [详情](#paper-xu2026agenticmip) |
| 2026 · arXiv preprint | **Agora-Opt**<br>From Soliloquy to Agora: Memory-Enhanced LLM Agents with Decentralized Debate for Optimization Modeling | 由多个 Agent 团队独立建模并开展结果驱动辩论，以读写记忆复用求解经验和分歧修订。 | 方法 · 数据 | [![Paper][badge-049]][resource-103] · [![Code & Cleaned Data][badge-050]][resource-083] · [详情](#paper-soliloquy2026) |
| 2026 · arXiv preprint | **AutoOPT**（探索性）<br>A Domain-Specific Harness for End-to-End Automation of Optimization Research | 连接数值方法设计、LLM 符号推导、Lean 4 验证和人工解释，研究最优一阶优化算法。 | 方法 · 平台 | [![Paper][badge-049]][resource-522] · [![Code][badge-022]][resource-523] · [![Skills][badge-150]][resource-100] · [![Lean Proofs][badge-151]][resource-524] · [详情](#paper-autoopt2026) |
| 2026 · arXiv preprint | **AutoREM / AutoRO-Bench**<br>Automated Reformulation of Robust Optimization via Memory-Augmented Large Language Models | 以失败经验记忆辅助鲁棒优化的确定性重构，并提出 AutoRO-Bench。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-106] · [详情](#paper-robustreform2026) |
| 2026 · arXiv preprint | **CIR / R2C**<br>Canonical Intermediate Representation for LLM-based optimization problem formulation and code generation | 以规范中间表示编码复杂规则，再检索知识并生成约束实现。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-109] · [详情](#paper-canonicalir2026) |
| 2026 · AAAI 2026 | **CO-Bench**（核心）<br>CO-Bench: Benchmarking Language Model Agents in Algorithm Search for Combinatorial Optimization | 提供组合优化算法搜索基准，比较 LLM Agent 与人工设计算法。 | 基准 · 数据 | [![Proceedings][badge-105]][resource-384] · [![Paper 2][badge-052]][resource-385] · [![Code][badge-022]][resource-386] · [![Dataset][badge-060]][resource-024] · [详情](#paper-sun2026cobench) |
| 2026 · arXiv preprint | **COOPA**<br>COOPA: A Modular LLM Agent Architecture for Operations Research Problems | 迭代比较候选公式的置信度，追踪建模元素的来源，再路由至适用求解器 Agent。 | 方法 | [![Paper][badge-049]][resource-112] · [![Code][badge-022]][resource-113] · [详情](#paper-coopa2026) |
| 2026 · LLM4Code 2026 Workshop @ ICSE | **CP-Agent**<br>CP-Agent: Agentic Constraint Programming | 通过持久 IPython 内核和简短领域提示，执行并迭代修正约束模型。 | 方法 · 数据 | [![Paper 1][badge-051]][resource-114] · [![Paper 2][badge-052]][resource-115] · [![Author Coding Agent（相关）][badge-054]][resource-116] · [![Evaluation Archive v2][badge-055]][resource-087] · [详情](#paper-cpagent2025) |
| 2026 · arXiv preprint | **CP-SynC**<br>CP-SynC: Multi-Agent Zero-Shot Constraint Modeling in MiniZinc with Synthesized Checkers | 由建模、检查与选择 Agent 并行探索 MiniZinc 模型，并合成语义检查器聚合证据。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-117] · [![Benchmark & Evaluation][badge-056]][resource-028] · [详情](#paper-cpsync2026) |
| 2026 · arXiv preprint | **EPOCH**<br>EPOCH: Coverage-Aware Evolution with Experiential Preference Optimization for LLM-based Automated Heuristic Design | 以实例覆盖选择互补启发式，并用教师反思形成偏好对，通过 DPO 与反思自蒸馏更新生成器。 | 方法 · 模型 | [![Paper][badge-049]][resource-393] · [详情](#paper-epoch2026) |
| 2026 · arXiv preprint | **EvoOR-Agent**<br>Co-evolving Agent Architectures and Interpretable Reasoning for Automated Optimization | 以 AOE 图表示建模—求解工作流，共同演化 Agent 架构与可解释推理路径。 | 方法 | [![Paper][badge-049]][resource-125] · [详情](#paper-coevolve2026) |
| 2026 · EMNLP 2026 | **FormuEvo**<br>FormuEvo: LLM-Guided Evolution for Discovering Solver-Efficient Mixed-Integer Programming Formulations | 在建模程序空间演化更强的 MIP 表达，以求解器统计诊断和结构化记忆指导改写。 | 方法 | [![Publication][badge-053]][resource-128] · [![Paper 2][badge-052]][resource-129] · [![Code][badge-022]][resource-130] · [详情](#paper-yuan2026formuevo) |
| 2026 · arXiv preprint | **GenAI Beer Game Reliability**<br>Reliability and Effectiveness of Autonomous AI Agents in Supply Chain Management | 在多级 Beer Game 中研究 Agent 决策波动，并比较强化学习后训练与运营护栏的可靠性。 | 方法 · 评测分析 · 应用 | [![Paper][badge-049]][resource-525] · [详情](#paper-beergame2026) |
| 2026 · ICLR 2026 | **HeuriGym**<br>HeuriGym: An Agentic Benchmark for LLM-Crafted Heuristics in Combinatorial Optimization | 让 LLM 通过代码运行反馈迭代生成组合优化启发式，并联合衡量质量与有效产出。 | 基准 · 平台 | [![Publication][badge-053]][resource-403] · [![Paper 2][badge-052]][resource-404] · [![Code][badge-022]][resource-035] · [![Leaderboard（相关）][badge-137]][resource-405] · [详情](#paper-chen2025heurigym) |
| 2026 · ICLR 2026 | **HiFo-Prompt**<br>HiFo-Prompt: Prompting with Hindsight and Foresight for LLM-based Automatic Heuristic Design | 用事后知识池积累启发式设计原则，并依群体动态选择面向未来的搜索提示。 | 方法 | [![Paper 1][badge-051]][resource-406] · [![Paper 2][badge-052]][resource-407] · [![Code][badge-022]][resource-408] · [详情](#paper-chen2025hifoprompt) |
| 2026 · arXiv preprint | **Interactive Optimization Conversations**<br>Let's Have a Conversation: Designing and Evaluating LLM Agents for Interactive Optimization | 用带内部效用函数的决策 Agent 扮演利益相关者，评测多轮交互优化而非只看单次答案。 | 方法 · 数据 · 应用 | [![Paper][badge-049]][resource-133] · [![Code][badge-022]][resource-090] · [详情](#paper-conversation2026) |
| 2026 · arXiv preprint | **InventoryBench**<br>AI Agents for Inventory Control: Human-LLM-OR Complementarity | 构建库存决策基准，并结合人类实验研究 OR、LLM 和人工决策的互补性。 | 方法 · 基准 · 数据 · 应用 | [![Paper][badge-049]][resource-526] · [![InventoryBench][badge-152]][resource-036] · [![人机实验平台][badge-153]][resource-527] · [详情](#paper-invbench2026) |
| 2026 · arXiv preprint | **LaGO**<br>Heuristic Search as Language-Guided Program Optimization | 将启发式发现拆为执行评价、语言分析反馈和程序更新三个模块，支持独立改进组件。 | 方法 | [![Paper][badge-049]][resource-411] · [详情](#paper-hsplo2026) |
| 2026 · arXiv preprint | **LEAN-LLM-OPT**<br>Large-Scale Optimization Model Auto-Formulation: Harnessing LLM Flexibility via Structured Workflow | 动态构建建模工作流并将数据处理交给工具，面向大规模优化和航空收入管理。 | 方法 · 基准 · 数据 · 应用 | [![Paper][badge-049]][resource-134] · [![Code][badge-022]][resource-038] · [详情](#paper-liang2026leanllmopt) |
| 2026 · arXiv preprint | **LLM Agents for Efficient Frontiers**<br>LLM Agents for Combinatorial Efficient Frontiers: Investment Portfolio Optimization | 用 Agent 自动化基数约束均值—方差投资组合的启发式开发及有效前沿构建。 | 方法 · 应用 | [![Paper][badge-049]][resource-415] · [详情](#paper-efficientfrontier2026) |
| 2026 · arXiv preprint | **LLM-MAS for Service Operations**<br>Optimizing Service Operations via LLM-Powered Multi-Agent Simulation | 用交互 LLM 模拟参与者响应，并以轨迹上的梯度估计和方差缩减优化服务设计。 | 方法 · 应用 | [![Paper][badge-049]][resource-528] · [详情](#paper-wang2026llmmas) |
| 2026 · MIPRO 2026 | **LLMs as Optimizers Survey**<br>Large Language Models as Optimizers: A Survey of Direct vs. Tool-Augmented Approaches and Their Performance Frontiers | 区分直接优化、调用工具优化和创造可复用工具三种范式，比较文献中的性能边界。 | 综述 | [![Publication][badge-053]][resource-427] · [![Paper 2][badge-052]][resource-428] · [详情](#paper-llmasopt2026) |
| 2026 · arXiv preprint | **MeEvo**<br>MeEvo: Metacognitive Evolution Combined with Natural Evolution for Automatic Heuristic Design | 交替执行代码重组／变异和基于推理历史的元认知反思，把两阶段结果反馈到下一轮。 | 方法 | [![Paper][badge-049]][resource-429] · [![Code][badge-022]][resource-430] · [详情](#paper-meevo2026) |
| 2026 · Expert Systems with Applications 330（2026-12 编期） | **MeLA**<br>MeLA: A metacognitive LLM-driven architecture for automatic heuristic design | 通过问题分析、错误诊断和元认知搜索演化生成启发式的提示，而非仅对代码做变异。 | 方法 | [![Paper 1][badge-051]][resource-342] · [![Paper 2][badge-052]][resource-343] · [详情](#paper-chen2025mela) |
| 2026 · arXiv preprint | **MIRROR**<br>MIRROR: A Multi-Agent Framework with Iterative Adaptive Revision and Hierarchical Retrieval for Optimization Modeling in Operations Research | 通过执行驱动的迭代修订与分层检索，获取建模和代码示例来修复优化模型。 | 方法 | [![Paper][badge-049]][resource-144] · [详情](#paper-mirror2026) |
| 2026 · ICML 2026 · PMLR 306 | **NEMO**<br>NEMO: Execution-Aware Optimization Modeling via Autonomous Coding Agents | 用自主编码 Agent 生成优化器与模拟器，再以交叉执行、经验复用和候选一致性改进建模。 | 方法 | [![Paper 1][badge-051]][resource-148] · [![Paper 2][badge-052]][resource-149] · [![Evaluation Artifacts][badge-064]][resource-096] · [详情](#paper-nemo2026) |
| 2026 · Findings of ACL 2026 | **OPT-BENCH / OPT-Agent**<br>OPT-BENCH: Evaluating the Iterative Self-Optimization of LLM Agents in Large-Scale Search Spaces | 在机器学习调优与 NP 问题中评测迭代自优化，并用 OPT-Agent 复用历史反馈修订方案。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-529] · [![Paper 2][badge-052]][resource-530] · [![Revised Preprint][badge-154]][resource-531] · [![Code][badge-022]][resource-048] · [![Dataset][badge-060]][resource-047] · [详情](#paper-li2026optbench) |
| 2026 · ICML 2026 · PMLR 306 | **Opt-Miner**<br>Opt-Miner: Empowering Information-Seeking Agent with Tree-Guided Data Synthesis for Optimization Modeling | 用树结构合成带知识缺口的优化任务，并以 R-GRPO 训练主动检索知识的建模 Agent。 | 方法 · 数据 · 模型 | [![Paper][badge-057]][resource-152] · [![Reproduction Code（第三方）][badge-065]][resource-153] · [![Reproduction Results（第三方）][badge-066]][resource-097] · [![Demo（第三方）][badge-067]][resource-154] · [详情](#paper-optminer2026) |
| 2026 · arXiv preprint | **OptArgus**（探索性）<br>OptArgus: A Multi-Agent System to Detect Hallucinations in LLM-based Optimization Modeling | 用幻觉分类法和专家 Agent 审计问题描述、数学模型与求解器实现的一致性。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-345] · [详情](#paper-optarcus2026) |
| 2026 · arXiv preprint | **OptGraph**<br>OptGraph: Large Language Models Enhanced Evolutionary Optimization Via Graph Retrieval-Augmented Generation | 将建模模式、公式、实现和错误修订组织成类型图，以邻域检索和运行轨迹更新支持优化建模。 | 方法 | [![Paper][badge-049]][resource-155] · [![Code][badge-022]][resource-156] · [详情](#paper-xiu2026optgraph) |
| 2026 · arXiv preprint | **Opti-Agent-Bench**<br>Opti-Agent-Bench: Benchmarking End-to-End Optimization R&D Agents on Real-World Business Problems | 评测业务理解、形式化、实现与报告，并检查跨模块一致性和任务评分有效性。 | 基准 · 数据 | [![Paper][badge-049]][resource-157] · [详情](#paper-optiagentbench2026) |
| 2026 · arXiv preprint | **OptiAgent**<br>OptiAgent: End-to-End Optimization Modeling via Multi-Agent Iterative Refinement | 通过专门建模 Agent 与多层反馈循环，提取变量和约束并修正公式及可执行代码。 | 方法 | [![Paper][badge-049]][resource-158] · [详情](#paper-optiagent2026) |
| 2026 · INFORMS Journal on Data Science 5(3):199–220 | **OptiChat**<br>OptiChat: Bridging Optimization Models and Practitioners with Large Language Models | 用自然语言查询已有优化模型，支持不可行诊断、敏感性、what-if 和反事实解释。 | 方法 · 数据 | [![Paper 1][badge-051]][resource-159] · [![Paper 2][badge-052]][resource-160] · [![Code][badge-022]][resource-098] · [详情](#paper-chen2025optichat) |
| 2026 · arXiv preprint | **OptiLoop**<br>OptiLoop: Coordination-in-the-Loop Verification and Repair for LLM-Generated Optimization Agents | 在有限轮 ADMM 式协同中测试本地优化 Agent，利用行为与静态证据修复实现或公式。 | 方法 | [![Paper][badge-049]][resource-346] · [详情](#paper-optiloop2026) |
| 2026 · arXiv preprint | **OptiRepair**（探索性）<br>OptiRepair: Closed-Loop Diagnosis and Repair of Supply Chain Optimization Models with LLM Agents | 以 IIS 与运营合理性检查构建两阶段供应链修复闭环，提出 OptiRepair-SC 并训练 P1 / P2 模型。 | 方法 · 基准 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-347] · [详情](#paper-optirepair2026) |
| 2026 · Findings of ACL 2026 | **OptiVerse / DVA-Agent**<br>OptiVerse: A Comprehensive Benchmark towards Optimization Problem Solving | 以 1,000 道多范式优化题评测建模与求解，并用双视角审核 Agent 对照需求与代码语义。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-162] · [![Paper 2][badge-052]][resource-163] · [![Inference, Auditor & Evaluation][badge-068]][resource-053] · [![OptiVerse 1K][badge-069]][resource-052] · [详情](#paper-optiverse2026) |
| 2026 · Findings of EMNLP 2026 | **OptSkills**<br>OptSkills: Learning Generalizable Optimization Skills from Problem Archetypes via Cluster-Based Distillation | 按问题原型聚类，从成功建模轨迹提炼、检索并更新可复用的工作流技能。 | 方法 | [![Publication][badge-053]][resource-164] · [![Paper 2][badge-052]][resource-165] · [![Code 1][badge-070]][resource-166] · [![Code 2][badge-071]][resource-167] · [![官方技能库（相关）][badge-048]][resource-102] · [详情](#paper-yang2026optskills) |
| 2026 · arXiv preprint | **OR-Space**<br>OR-Space: A Full-Lifecycle Workspace Benchmark for Industrial Optimization Agents | 用持久多文件工作区评测模型构建、需求变更和基于证据的解释三类生命周期任务。 | 基准 · 数据 | [![Paper][badge-049]][resource-172] · [![Code][badge-022]][resource-057] · [![Dataset][badge-060]][resource-056] · [详情](#paper-zhou2026orspace) |
| 2026 · arXiv preprint | **ORAgentBench**<br>ORAgentBench: Can LLM Agents Solve Challenging Operations Research Tasks End to End? | 在隔离工作环境中评测从业务说明、多文件材料到可验证决策的完整 OR 任务。 | 基准 · 数据 | [![Paper][badge-049]][resource-173] · [![Code][badge-022]][resource-058] · [详情](#paper-oragentbench2026) |
| 2026 · Artificial Intelligence for Transportation 6（2026） | **ORThought / LogiOR**<br>ORThought: Benchmarking and automating logistics optimization modeling via structured LLM reasoning | 以专家建模原则指导结构化双 Agent 推理，并发布物流建模基准 LogiOR。 | 方法 · 基准 · 数据 | [![Publication][badge-053]][resource-174] · [![Paper 2][badge-052]][resource-175] · [![Code][badge-022]][resource-176] · [![Dataset][badge-060]][resource-062] · [详情](#paper-yang2025orthought) |
| 2026 · ICML 2026 · PMLR 306 | **PathWise**<br>PathWise: Planning through World Model for Automated Heuristic Design via Self-Evolving LLMs | 在保存搜索历史的蕴含图上规划演化动作，由策略、世界模型和评论 Agent 协作生成启发式。 | 方法 | [![Paper 1][badge-051]][resource-438] · [![Paper 2][badge-052]][resource-439] · [![Code][badge-022]][resource-440] · [详情](#paper-pathwise2026) |
| 2026 · NeurIPS 2026（已接收，待出版） | **PEARL**（核心）<br>PEARL: Solver-in-the-Loop Interactive Optimization Modeling from Natural Language | 在多轮工具调用中执行、调试和修订优化模型，用求解器反馈训练交互建模策略。 | 方法 · 模型 | [![Paper 1][badge-058]][resource-177] · [![Conference][badge-072]][resource-178] · [![Code][badge-022]][resource-179] · [![Model][badge-073]][resource-009] · [详情](#paper-lu2026pearl) |
| 2026 · AAMAS 2026 | **PyVRP+ / MEP**<br>PyVRP+: LLM-Driven Metacognitive Heuristic Evolution for Hybrid Genetic Search in Vehicle Routing Problems | 通过 Reason–Act–Reflect 诊断和设计假设，演化 HGS 中的路由启发式组件。 | 方法 · 应用 | [![Paper 1][badge-051]][resource-441] · [![Paper 2][badge-052]][resource-442] · [![Proceedings][badge-105]][resource-443] · [详情](#paper-pyvrpplus2026) |
| 2026 · arXiv preprint | **RLEA**<br>Reinforcement Learning Enhanced LLM Agents for Complex Vehicle Routing Problems | 以 Soft Q-learning 训练轻量 Planner 调度 LLM Agent，结合记忆与检索完成复杂 VRP 建模。 | 方法 · 应用 | [![Paper][badge-049]][resource-353] · [![Appendix（相关）][badge-126]][resource-354] · [详情](#paper-rlvrpagents2026) |
| 2026 · ICML 2026 · PMLR 306 | **SAC-Opt**<br>SAC-Opt: Semantic Anchors for Iterative Correction in Optimization Modeling | 把生成代码回译为语义锚点，与原始需求对齐后定点修正约束和目标。 | 方法 | [![Paper 1][badge-051]][resource-184] · [![Paper 2][badge-052]][resource-185] · [![Code][badge-022]][resource-186] · [详情](#paper-ma2025sacopt) |
| 2026 · ICLR 2026 | **ShinkaEvolve**<br>ShinkaEvolve: Towards Open-Ended and Sample-Efficient Program Evolution | 结合父代采样、代码新颖性拒绝采样和 bandit 模型选择，提高程序演化的样本效率。 | 方法 · 平台 | [![Paper 1][badge-051]][resource-444] · [![Paper 2][badge-052]][resource-445] · [![Code][badge-022]][resource-446] · [详情](#paper-lange2026shinka) |
| 2026 · arXiv preprint | **Smart Grids Agentic AI Tutorial**<br>LLMs and Agentic AI Systems for Smart Grids: A Tutorial on Architectures and Applications | 综述智能电网 Agent 架构，并以充电、潮流和故障诊断等案例演示可信工具与显式检查。 | 综述 · 应用 | [![Paper][badge-049]][resource-532] · [![Case-study Code][badge-155]][resource-533] · [详情](#paper-smartgrid2026) |
| 2026 · arXiv preprint | **Text2Model**<br>Text2Model: Modeling Copilots for Text-to-Model Translation | 提供面向 MiniZinc 的多种建模 Copilot、交互编辑器与在线排行榜。 | 方法 · 平台 | [![Paper][badge-049]][resource-196] · [![Code][badge-022]][resource-197] · [![Text2Zinc（复用）][badge-082]][resource-069] · [![Editor（相关）][badge-083]][resource-198] · [![Leaderboard（相关）][badge-084]][resource-199] · [![Python Package（相关）][badge-085]][resource-200] · [详情](#paper-text2model2026) |
| 2025 · arXiv preprint | **ALAS**<br>ALAS: A Stateful Multi-LLM Agent Framework for Disruption-Aware Planning | 用角色化 Agent、持久状态与历史感知的局部补偿，处理调度计划中的运行扰动。 | 方法 · 应用 | [![Paper][badge-049]][resource-534] · [详情](#paper-alas2025) |
| 2025 · Technical report | **AlphaEvolve**（核心）<br>AlphaEvolve: A coding agent for scientific and algorithmic discovery | 用 LLM 与进化式代码修改闭环改进算法，覆盖科学问题及计算基础设施优化。 | 方法 | [![Paper][badge-049]][resource-453] · [![官方结果（相关）][badge-142]][resource-454] · [![官方问题集（相关）][badge-143]][resource-455] · [详情](#paper-novikov2025alphaevolve) |
| 2025 · NeurIPS 2025 ScaleOpt Workshop / arXiv | **AlphaOPT**<br>AlphaOPT: Formulating Optimization Programs with Self-Improving LLM Experience Library | 通过求解器反馈提炼并演化可检索的建模经验库，无需更新 LLM 参数。 | 方法 | [![Paper 1][badge-051]][resource-205] · [![Paper 2][badge-052]][resource-206] · [![Code][badge-022]][resource-207] · [详情](#paper-kong2025alphaopt) |
| 2025 · arXiv preprint | **ARS / RoutBench**（核心）<br>ARS: Automatic Routing Solver with Large Language Models | 根据问题描述生成约束感知的路由启发式，配套多变体 VRP 基准 RoutBench。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-456] · [![Code][badge-022]][resource-019] · [详情](#paper-li2025ars) |
| 2025 · arXiv preprint | **Ask, Clarify, Optimize**<br>Ask, Clarify, Optimize: Human-LLM Agent Collaboration for Smarter Inventory Control | 由 LLM 澄清库存需求并解释结果，把随机优化计算交给算法，以模拟经理测试交互。 | 方法 · 模型 · 应用 | [![Paper][badge-049]][resource-208] · [详情](#paper-askclarify2026) |
| 2025 · FedCSIS 2025 · ACSIS 43 | **C-DSS**<br>Toward Conversational Decision Support Systems: Integrating LLMs in the Operations Research Methodology | 提出对话式决策支持架构，比较建模、AMPL 编码、RAG 和验证角色的不同组合。 | 方法 | [![Paper 1][badge-051]][resource-214] · [![Paper 2][badge-074]][resource-215] · [详情](#paper-kaleta2025cdss) |
| 2025 · arXiv preprint | **DAOpt / OptU**<br>DAOpt: Modeling and Evaluation of Data-Driven Optimization under Uncertainty with LLMs | 结合不确定性建模、多 Agent 与仿真环境，评估样本外可行性和稳健性。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-222] · [详情](#paper-daopt2025) |
| 2025 · arXiv preprint | **DHEvo**<br>DHEvo: Data-Algorithm Based Heuristic Evolution for Generalizable MILP Solving | 共同演化代表性实例与 diving 启发式，提高同类 MILP 实例内的泛化能力。 | 方法 | [![Paper][badge-049]][resource-466] · [详情](#paper-dheevo2025) |
| 2025 · AAAI 2025 | **DOCP Research Manifesto**（核心）<br>Enhancing Decision Making Through the Integration of Large Language Models and Operations Research Optimization | 提出面向业务用户的优化 Copilot 愿景，梳理需求澄清、模型核验和求解效率等研究要求。 | 综述 · 基础 | [![Paper 1][badge-051]][resource-223] · [![Paper 2][badge-052]][resource-224] · [详情](#paper-wasserkrug2024manifesto) |
| 2025 · ICLR 2025 | **DRoC**<br>DRoC: Elevating Large Language Models for Complex Vehicle Routing via Decomposed Retrieval of Constraints | 分解复杂 VRP 的约束并分别检索文档，动态选择 RAG 或自调试生成求解器程序。 | 方法 · 数据 · 应用 | [![Publication][badge-053]][resource-226] · [![Paper 2][badge-074]][resource-227] · [![Code][badge-022]][resource-088] · [详情](#paper-jiang2025droc) |
| 2025 · arXiv preprint | **EASE**<br>Solve it with EASE | 以模块化生成、测试、分析和评价循环支持算法方案演化，允许多个 LLM 承担互补角色。 | 方法 · 平台 | [![Paper][badge-049]][resource-360] · [![Framework][badge-129]][resource-361] · [![Frontend][badge-130]][resource-362] · [详情](#paper-viktorin2025ease) |
| 2025 · ICLR 2025 | **EOR / Decision Information**<br>Decision Information Meets Large Language Models: The Future of Explainable Operations Research | 用 what-if 决策信息与二部图比较模型变化，生成可操作的优化解释。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-228] · [![Paper 2][badge-052]][resource-229] · [![Code][badge-022]][resource-031] · [详情](#paper-zhang2025decisioninfo) |
| 2025 · arXiv preprint | **Gala**<br>Gala: Global LLM Agents for Text-to-Model Translation | 按全局约束类型分工 Agent，再由组装 Agent 合成完整 MiniZinc 模型。 | 方法 | [![Paper][badge-049]][resource-233] · [![Gala in Text2Model][badge-092]][resource-197] · [![Author Project（相关）][badge-093]][resource-234] · [详情](#paper-globalconstraint2025) |
| 2025 · arXiv preprint | **HeurAgenix**<br>HeurAgenix: Leveraging LLMs for Solving Complex Combinatorial Optimization Challenges | 先生成与演化启发式库，再按问题状态选择算子；选择器可采用通用 LLM 或领域微调模型。 | 方法 · 模型 | [![Paper][badge-049]][resource-469] · [![Code][badge-022]][resource-470] · [![CO Instances][badge-144]][resource-089] · [详情](#paper-yang2025heuragenix) |
| 2025 · ICML 2025 | **LLM-LNS**（核心）<br>Large Language Model-driven Large Neighborhood Search for Large-Scale MILP Problems | 通过双层自演化 LLM Agent 设计 LNS 邻域策略，研究向大规模 MILP 的迁移。 | 方法 | [![Paper][badge-057]][resource-485] · [![Code][badge-022]][resource-486] · [详情](#paper-ye2025llmlns) |
| 2025 · arXiv preprint | **LLM-SUC**（探索性）<br>Can Large Language Model Agents Balance Energy Systems? | 将 LLM Agent 与多场景随机机组组合结合，辅助高风电不确定性下的运行决策。 | 方法 · 应用 | [![Paper][badge-049]][resource-235] · [![Code][badge-022]][resource-236] · [详情](#paper-llmsuc2025) |
| 2025 · arXiv preprint | **LLMs for Stochastic Modeling**<br>Large Language Model-Based Automatic Formulation for Stochastic Optimization Models | 以结构化提示生成机会约束与两阶段随机规划，并用软评分检查模型结构。 | 方法 | [![Paper][badge-049]][resource-242] · [![Code][badge-022]][resource-093] · [详情](#paper-talebi2025stochastic) |
| 2025 · EMNLP 2025 Main, pp. 19286–19304 | **MA-GTS / G-REAL**<br>MA-GTS: A Multi-Agent Framework for Solving Complex Graph Problems in Real-World Applications | 从隐式文本图信息恢复结构化图，并用多 Agent 根据问题约束及规模选择算法。 | 方法 · 基准 · 数据 | [![Paper 1][badge-058]][resource-487] · [![Paper 2][badge-074]][resource-488] · [![Code][badge-022]][resource-039] · [详情](#paper-yuan2025magts) |
| 2025 · NeurIPS 2025 | **MM-Agent / MM-Bench（数学建模）**（探索性）<br>MM-Agent: LLM as Agents for Real-world Mathematical Modeling Problem | 将数学建模拆为问题分析、模型构造、计算求解和报告生成，并提供 MCM/ICM 来源的 MM-Bench。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-246] · [![Paper 2][badge-052]][resource-247] · [![Paper 3][badge-097]][resource-248] · [![Code & MM-Bench][badge-098]][resource-043] · [![Expert Skills (2026 add-on)][badge-099]][resource-101] · [![HF Demo（相关）][badge-100]][resource-249] · [详情](#paper-liu2025mmagent) |
| 2025 · Findings of EMNLP 2025 | **ModelingAgent / ModelingBench**（探索性）<br>ModelingAgent: Bridging LLMs and Mathematical Modeling for Real-World Challenges | 用多 Agent 协调工具和迭代修订处理开放式建模，并以 ModelingBench 与 ModelingJudge 评估报告。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-250] · [![Paper 2][badge-052]][resource-251] · [![Code & ModelingBench][badge-101]][resource-044] · [详情](#paper-qian2025modelingagent) |
| 2025 · arXiv preprint | **MOID**<br>Multi-Objective Infeasibility Diagnosis for Routing Problems Using Large Language Models | 联合路径成本与约束违反量做多目标优化，再由 LLM 分析一组可恢复可行性的调整建议。 | 方法 · 数据 · 应用 | [![Paper][badge-049]][resource-252] · [![Diagnosis Data][badge-102]][resource-095] · [详情](#paper-moid2025) |
| 2025 · NeurIPS 2025 Main Conference Track, volume 38 | **MURKA**<br>MURKA: Multi-Reward Reinforcement Learning with Knowledge Alignment for Optimization Tasks | 用多奖励强化学习与知识蒸馏对齐 Extractor、Solver、Checker 三类 Agent，支持从文本到可执行优化程序。 | 方法 | [![Paper][badge-057]][resource-253] · [详情](#paper-xie2025murka) |
| 2025 · arXiv preprint | **OptimAI**<br>OptimAI: Optimization from Natural Language Using LLM-Powered AI Agents | 以建模、规划、编码和代码批评角色协作求解，并用 UCB 调度调试与备选计划。 | 方法 | [![Paper][badge-049]][resource-254] · [详情](#paper-thind2025optimai) |
| 2025 · arXiv preprint | **OptiTrust**<br>Toward a Trustworthy Optimization Modeling Agent via Verifiable Synthetic Data Generation | 从带已知最优解的符号问题合成示范，用跨建模语言投票和分步推理训练建模 Agent。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-260] · [详情](#paper-lima2025optitrust) |
| 2025 · arXiv preprint | **OR-LLM-Agent / BWOR**<br>OR-LLM-Agent: Automating Modeling and Solving of Operations Research Optimization Problems with Reasoning LLM | 将建模、代码生成与调试分配给推理 Agent，并提出 BWOR 评测集。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-262] · [![Code][badge-022]][resource-263] · [![Dataset][badge-060]][resource-055] · [详情](#paper-zhang2025bwor) |
| 2025 · ACL 2025 Industry Track | **ORMind**<br>ORMind: A Cognitive-Inspired End-to-End Reasoning Framework for Operations Research | 以认知启发的角色协作、执行修复和反事实检查完成优化建模。 | 方法 | [![Paper 1][badge-051]][resource-269] · [![Paper 2][badge-052]][resource-270] · [![Code][badge-022]][resource-271] · [详情](#paper-ormind2025) |
| 2025 · arXiv（2026 修订） | **ReflecSched**（探索性）<br>ReflecSched: Solving Dynamic Flexible Job-Shop Scheduling via LLM-Powered Hierarchical Reflection | 从多规划时域的启发式仿真中提炼战略经验，指导动态柔性作业车间调度决策。 | 方法 · 应用 | [![Paper][badge-049]][resource-535] · [详情](#paper-cao2025reflecsched) |
| 2025 · arXiv preprint | **RoCo**<br>RoCo: Role-Based LLMs Collaboration for Automatic Heuristic Design | 用探索者、开发者、批评者和整合者四个角色协作生成、审查和修订启发式。 | 方法 | [![Paper][badge-049]][resource-503] · [详情](#paper-xu2025roco) |
| 2025 · arXiv preprint | **Validation-in-the-Loop Power Modeling**（探索性）<br>From Natural Language to Solver-Ready Power System Optimization: An LLM-Assisted, Validation-in-the-Loop Framework | 通过领域提示、结构化 schema、可行性校验与迭代修复生成电力优化模型。 | 方法 · 应用 | [![Paper][badge-049]][resource-285] · [详情](#paper-nl2ps2025) |
| 2024 · ICLR 2024 | **Chain-of-Experts**（核心）<br>Chain-of-Experts: When LLMs Meet Complex Operations Research Problems | 为不同 Agent 配置 OR 专长，由 conductor 组织前向思维构造与反向反思，完成复杂建模和编程。 | 方法 · 基准 · 数据 | [![Paper][badge-057]][resource-290] · [![Code][badge-022]][resource-023] · [详情](#paper-xiao2024coe) |
| 2024 · arXiv preprint | **City-LEO**<br>City-LEO: Toward Transparent City Management Using LLM with End-to-End Optimization | 通过对话限定优化范围，并结合预测与优化管理共享电动自行车运营。 | 方法 · 应用 | [![Paper][badge-049]][resource-291] · [![Data & Code][badge-109]][resource-086] · [详情](#paper-jiao2024cityleo) |
| 2024 · arXiv preprint | **InvAgent**（探索性）<br>InvAgent: A Large Language Model based Multi-Agent System for Inventory Management in Supply Chains | 让多个 LLM Agent 通过零样本推理管理供应链库存并适应需求变化。 | 方法 · 应用 | [![Paper][badge-049]][resource-536] · [![Code][badge-022]][resource-537] · [详情](#paper-quan2024invagent) |
| 2024 · EMNLP 2024 Industry Track | **ITINERA**<br>ItiNera: Integrating Spatial Optimization with Large Language Models for Open-domain Urban Itinerary Planning | 分解城市漫步需求、选择兴趣点，并用聚类感知的空间优化排序与生成个性化行程。 | 方法 · 应用 | [![Paper 1][badge-051]][resource-293] · [![Paper 2][badge-052]][resource-294] · [![Code][badge-022]][resource-295] · [详情](#paper-tang2024itinerary) |
| 2024 · INFOR 62(4):599–617 | **Multi-Stage Modeling & Verification**<br>Optimization modeling and verification from problem specifications using a multi-agent multi-stage LLM framework | 分阶段从问题规格生成数学模型与 Zimpl 代码，并由多个 LLM Agent 交叉检查。 | 方法 · 基准 · 数据 | [![Paper][badge-057]][resource-298] · [详情](#paper-mostajabdaveh2024multiagent) |
| 2024 · INFOR 2024 | **OptiChat / Infeasibility Diagnosis**<br>Diagnosing Infeasible Optimization Problems Using Large Language Models | 通过 GPT-4、求解器 IIS 与对话界面解释不可行原因，并建议模型修复。 | 方法 | [![Paper 1][badge-058]][resource-369] · [![Publication][badge-053]][resource-370] · [![Code][badge-022]][resource-098] · [详情](#paper-chen2023diagnosing) |
| 2024 · ICML 2024 | **OptiMUS**（核心）<br>OptiMUS: Scalable Optimization Modeling with (MI)LP Solvers and Large Language Models | 用模块化 Agent 完成 MILP 建模、代码生成、调试与评估，同时发布 NLP4LP。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-302] · [![arXiv][badge-087]][resource-303] · [![Code][badge-022]][resource-304] · [![Dataset][badge-060]][resource-051] · [详情](#paper-teshnizi2024optimus) |
| 2024 · NAACL 2024 Industry Track | **OptLLM**<br>Solving General Natural-Language-Description Optimization Problems with Large Language Models | 通过多轮澄清、公式与代码转换、外部求解器和结果解释支持自然语言优化，并微调 Qwen。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-305] · [![Paper 2][badge-052]][resource-306] · [![MindOpt Trial (International)（相关）][badge-112]][resource-307] · [![MindOpt Trial (CN)（相关）][badge-113]][resource-308] · [详情](#paper-zhang2024optllm) |
| 2024 · arXiv preprint | **RAGDyS**<br>Automated Conversion of Static to Dynamic Scheduler via Natural Language | 从既有静态排程模型出发，用检索增强生成按自然语言约束实施动态排程修改。 | 方法 · 应用 | [![Paper][badge-049]][resource-309] · [详情](#paper-tang2024ragdys) |
| 2024 · EMNLP 2024 System Demonstrations | **To the Globe / TTG**<br>To the Globe (TTG): Towards Language-Driven Guaranteed Travel Planning | 将旅行需求译为符号表示，再由 MILP 求解器生成满足已编码约束的行程。 | 方法 · 应用 · 模型 | [![Paper 1][badge-051]][resource-310] · [![Paper 2][badge-052]][resource-311] · [详情](#paper-ju2024ttg) |
| 2023 · arXiv preprint | **Holy Grail 2.0**<br>Holy Grail 2.0: From Natural Language to Constraint Models | 讨论把自然语言转为约束模型的分解式提示流程，并报告 GPT 模型的早期结果。 | 方法 · 基础 | [![Paper][badge-049]][resource-317] · [详情](#paper-kadioglu2023holygrail) |
| 2023 · arXiv preprint | **LLMs for Power Engineering**（探索性）<br>LLM-based Frameworks for Power Engineering from Routine to Novel Tasks | 对常规电力优化编程采用端到端流程，对新任务采用工程师参与的分解与代码合成。 | 方法 · 应用 | [![Paper][badge-049]][resource-371] · [详情](#paper-li2023power) |
| 2023 · arXiv preprint | **OptiGuide**（核心）<br>Large Language Models for Supply Chain Optimization | OptiGuide 将自然语言 what-if 查询转成对现有优化程序的分析，解释供应链决策结果。 | 方法 · 应用 | [![Paper][badge-049]][resource-325] · [![Code][badge-022]][resource-256] · [详情](#paper-li2023optiguide) |

[返回目录](#contents)

<a id="training"></a>

## 数据合成与模型训练

合成训练数据、微调领域模型，开展强化学习与自进化。

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · ICML 2026 RLxF Workshop / arXiv | **AutoOR**<br>AutoOR: Scalably Post-training LLMs to Autoformulate Operations Research Problems | 从标准优化形式合成训练样本，并以执行反馈和课程式 RL 训练自然语言到模型的能力。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-104] · [![Paper 2][badge-052]][resource-105] · [详情](#paper-autoor2026) |
| 2026 · ICLR 2026 | **CALM (Algorithm–LM Co-evolution)**<br>CALM: Co-evolution of Algorithms and Language Model for Automatic Heuristic Design | 用生成启发式的质量作 RL 信号，共同演化候选算法与底层语言模型。 | 方法 · 模型 | [![Paper 1][badge-051]][resource-381] · [![Paper 2][badge-052]][resource-382] · [![Code][badge-022]][resource-383] · [详情](#paper-huang2025calm) |
| 2026 · Findings of EMNLP 2026 | **Constraint Injection / VRPCoder**<br>Beyond Objective Equivalence: Constraint Injection for LLM-Based Optimization Modeling on Vehicle Routing Problems | 用可行解和单约束违反解测试 VRP 代码，补充最优值相同仍可能漏约束的检查。 | 方法 · 基准 · 数据 · 模型 · 应用 | [![Publication][badge-053]][resource-335] · [![Paper 2][badge-052]][resource-336] · [![Benchmark Data][badge-122]][resource-025] · [详情](#paper-constraintinjection2026) |
| 2026 · AAAI 2026 | **DeepOR**<br>DeepOR: A Deep Reasoning Foundation Model for Optimization Modeling | 以流程图引导长思维链合成和监督微调，再用求解器反馈构造奖励进行强化学习。 | 方法 · 数据 | [![Paper][badge-057]][resource-118] · [![Code][badge-022]][resource-119] · [![官方种子与样例数据][badge-028]][resource-072] · [详情](#paper-xiao2026deepor) |
| 2026 · arXiv preprint | **DScheLLM**<br>DScheLLM: Enabling Dynamic Scheduling through a Fine-Tuned Dual-System Large language Model | 用求解器排程合成快／慢思考示范，LoRA 微调双系统 LLM 应对动态扰动。 | 方法 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-337] · [详情](#paper-zhang2026dschellm) |
| 2026 · arXiv preprint | **EPOCH**<br>EPOCH: Coverage-Aware Evolution with Experiential Preference Optimization for LLM-based Automated Heuristic Design | 以实例覆盖选择互补启发式，并用教师反思形成偏好对，通过 DPO 与反思自蒸馏更新生成器。 | 方法 · 模型 | [![Paper][badge-049]][resource-393] · [详情](#paper-epoch2026) |
| 2026 · arXiv preprint | **EVOM**<br>Execution-Verified Reinforcement Learning for Optimization Modeling | 以求解器执行结果训练建模 LLM，并研究 Gurobi、OR-Tools 与 COPT 间的迁移。 | 方法 · 模型 | [![Paper][badge-049]][resource-120] · [详情](#paper-guan2026evom) |
| 2026 · arXiv preprint | **EvoOpt-LLM**<br>EvoOpt-LLM: Evolving industrial optimization models with large language models | 以 7B 模型和 LoRA 支持工业 MILP 的模型构建、新业务约束注入与变量剪枝。 | 方法 · 模型 | [![Paper][badge-049]][resource-121] · [![Code][badge-022]][resource-122] · [详情](#paper-he2026evoopt) |
| 2026 · NeurIPS 2026（已接收，待出版） | **EvoOptiGraph**<br>EvoOptiGraph: Weakness-Driven Coevolution via Graph-Based Structural Generation for Optimization Modeling | 以属性二部图演化结构多样的 MILP，结合编译、回译、SFT 与 RLVR 针对模型弱点更新训练分布。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-123] · [![Paper 2][badge-052]][resource-124] · [详情](#paper-evooptigraph2026) |
| 2026 · arXiv preprint | **GenAI Beer Game Reliability**<br>Reliability and Effectiveness of Autonomous AI Agents in Supply Chain Management | 在多级 Beer Game 中研究 Agent 决策波动，并比较强化学习后训练与运营护栏的可靠性。 | 方法 · 评测分析 · 应用 | [![Paper][badge-049]][resource-525] · [详情](#paper-beergame2026) |
| 2026 · arXiv preprint | **Infeasibility-Aware CO Models**<br>Infeasibility Aware Large Language Models for Combinatorial Optimization | 用精确优化与可认证筛选构建可行／不可行训练样本，微调模型输出解或不可行判断，再辅助局部搜索。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-409] · [![Author Code / Data Archive（相关）][badge-138]][resource-073] · [详情](#paper-infeasibilityaware2026) |
| 2026 · arXiv preprint | **InvEvolve**（探索性）<br>InvEvolve: Evolving White-Box Inventory Policies via Large Language Models with Performance Guarantees | 用 LLM 演化白盒库存策略，并以置信区间认证框架研究部署安全与性能改进。 | 方法 · 应用 | [![Paper][badge-049]][resource-410] · [详情](#paper-invevolve2026) |
| 2026 · IEEE TEVC 30（2026） | **LLaMoCo**<br>LLaMoCo: Instruction Tuning of Large Language Models for Optimization Code Generation | 构造问题—优化代码指令集，以对比学习预热和指令微调训练从问题代码生成优化程序的模型。 | 方法 · 模型 · 数据 | [![Paper 1][badge-051]][resource-339] · [![Paper 2][badge-052]][resource-340] · [![LLaMoCo-S Example][badge-123]][resource-341] · [![LLaMoCo-S][badge-124]][resource-001] · [详情](#paper-ma2024llamoco) |
| 2026 · arXiv preprint | **MIND**<br>Automated Optimization Modeling via a Localizable Error-Driven Perspective | 依据建模错误的局部性合成针对性训练问题，并用 DFPO 对困难样本做局部修订。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-138] · [详情](#paper-mind2026) |
| 2026 · arXiv preprint | **MiniOpt**<br>MiniOpt: Reasoning to Model and Solve General Optimization Problems with Limited Resources | 以结构化推理连接建模和代码生成，用分层 OptReward 同时反馈公式与解的质量。 | 方法 · 模型 | [![Paper][badge-049]][resource-139] · [![Code][badge-022]][resource-140] · [详情](#paper-zhao2026miniopt) |
| 2026 · ICML 2026 | **MIPLIB-NL**（核心）<br>Constructing Industrial-Scale Optimization Modeling Benchmark | 从 MIPLIB 2017 真实 MILP 逆向恢复可复用结构，分离问题与数据，构建自然语言建模基准。 | 基准 · 数据 | [![Publication][badge-053]][resource-141] · [![Paper 2][badge-052]][resource-142] · [![Code][badge-022]][resource-042] · [![GitHub dataset][badge-063]][resource-143] · [详情](#paper-li2026miplibnl) |
| 2026 · arXiv preprint | **Multi-Warehouse Formulation Selection**<br>Large Language Model for Operations Research Formulation Selection in Multi-Warehouse Inventory Allocation | 在多仓库存分配中选择适合实例的 MIP 公式专家，并用求解质量反馈训练选择器。 | 方法 · 模型 · 应用 | [![Paper][badge-049]][resource-147] · [详情](#paper-warehouseformsel2026) |
| 2026 · ICML 2026 · PMLR 306 | **Opt-Miner**<br>Opt-Miner: Empowering Information-Seeking Agent with Tree-Guided Data Synthesis for Optimization Modeling | 用树结构合成带知识缺口的优化任务，并以 R-GRPO 训练主动检索知识的建模 Agent。 | 方法 · 数据 · 模型 | [![Paper][badge-057]][resource-152] · [![Reproduction Code（第三方）][badge-065]][resource-153] · [![Reproduction Results（第三方）][badge-066]][resource-097] · [![Demo（第三方）][badge-067]][resource-154] · [详情](#paper-optminer2026) |
| 2026 · arXiv preprint | **OptiRepair**（探索性）<br>OptiRepair: Closed-Loop Diagnosis and Repair of Supply Chain Optimization Models with LLM Agents | 以 IIS 与运营合理性检查构建两阶段供应链修复闭环，提出 OptiRepair-SC 并训练 P1 / P2 模型。 | 方法 · 基准 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-347] · [详情](#paper-optirepair2026) |
| 2026 · ICLR 2026 | **OR-PRM**<br>OR-PRM: A Process Reward Model for Algorithmic Problem in Operations Research | 先清洗已有合成数据，基于 MCTS 和逐步检查构建 OR-ProcessQA，再训练用于建模推理的过程奖励模型。 | 方法 · 数据 · 模型 | [![Paper][badge-057]][resource-168] · [详情](#paper-wang2026orprm) |
| 2026 · AAAI 2026 | **OR-R1**<br>OR-R1: Automating Modeling and Solving of Operations Research Optimization Problem via Test-Time Reinforcement Learning | 先用少量有标签数据 SFT，再以测试时 TGRPO 从未标注问题和求解一致性中学习。 | 方法 · 模型 | [![Paper 1][badge-051]][resource-169] · [![Paper 2][badge-052]][resource-170] · [![Code][badge-022]][resource-171] · [详情](#paper-ding2026orr1) |
| 2026 · ICML 2026 | **ORLoopBench**<br>ORLoopBench: Solver-in-the-Loop Benchmarks for Self-Correction and Behavioral Rationality in Operations Research | 以 IIS 和求解器重执行定义不可行模型修复闭环，配套 ORDebug 与 ORBias 评测。 | 方法 · 基准 · 数据 · 模型 | [![Publication][badge-053]][resource-348] · [![Paper 2][badge-052]][resource-349] · [![数据与校验代码][badge-125]][resource-060] · [详情](#paper-ao2026orloopbench) |
| 2026 · NeurIPS 2026（已接收，待出版） | **PALL**<br>Process-Aware LNS for Large-Scale MILP via Context-Enhanced Fine-Tuned LLM-driven Selector | 离线演化 LNS 算子组合，以 hindsight oracle 轨迹微调 8B LLM 在线选择器。 | 方法 · 模型 | [![Paper][badge-057]][resource-437] · [详情](#paper-yan2026pall) |
| 2026 · NeurIPS 2026（已接收，待出版） | **PEARL**（核心）<br>PEARL: Solver-in-the-Loop Interactive Optimization Modeling from Natural Language | 在多轮工具调用中执行、调试和修订优化模型，用求解器反馈训练交互建模策略。 | 方法 · 模型 | [![Paper 1][badge-058]][resource-177] · [![Conference][badge-072]][resource-178] · [![Code][badge-022]][resource-179] · [![Model][badge-073]][resource-009] · [详情](#paper-lu2026pearl) |
| 2026 · arXiv preprint | **PowerAtlas / ECBench**<br>PowerAtlas: Feasibility-Aware Language Models for Electricity-Computing Co-Scheduling | 以可行性反馈训练 LLM 直接生成电力—计算联合排程，并提出 ECBench 与确定性评分。 | 方法 · 基准 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-538] · [![Code & Sample Data][badge-156]][resource-063] · [详情](#paper-jiang2026poweratlas) |
| 2026 · ICML 2026 | **ProOPF**<br>ProOPF: Benchmarking and Improving LLMs for Professional-Grade Power Systems Optimization Modeling | 构建专业最优潮流建模数据和基准，区分参数调整与结构扩展难度。 | 基准 · 数据 · 应用 | [![Publication][badge-053]][resource-180] · [![Paper 2][badge-074]][resource-181] · [![Paper 3][badge-075]][resource-182] · [![Evaluation Code & Data][badge-076]][resource-064] · [详情](#paper-shen2026proopf) |
| 2026 · arXiv preprint | **RAG for Optimization & CP Modeling**<br>Optimization and Constraint Modeling using LLMs with a Retrieval Augmented Generation Process | 从 Text2Zinc 种子和角色描述合成 500 个问题，以检索示例辅助 LLM 生成优化与约束模型代码。 | 方法 · 数据 | [![Paper][badge-049]][resource-183] · [详情](#paper-roy2026rag) |
| 2026 · arXiv preprint | **RLEA**<br>Reinforcement Learning Enhanced LLM Agents for Complex Vehicle Routing Problems | 以 Soft Q-learning 训练轻量 Planner 调度 LLM Agent，结合记忆与检索完成复杂 VRP 建模。 | 方法 · 应用 | [![Paper][badge-049]][resource-353] · [![Appendix（相关）][badge-126]][resource-354] · [详情](#paper-rlvrpagents2026) |
| 2026 · ICML 2026 · PMLR 306 | **SAGE (Strategy-Aware Modeling)**<br>Strategy-Aware Optimization Modeling with Reasoning LLMs | 生成并筛选多策略建模示范，经 SFT 与 Segment-Weighted GRPO 兼顾公式正确性和求解效率。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-187] · [![Paper 2][badge-052]][resource-188] · [![Code][badge-022]][resource-189] · [![SAGE SFT 100K][badge-077]][resource-080] · [详情](#paper-strategyaware2026) |
| 2026 · arXiv preprint | **SDRL**<br>LLMs as Adaptive Meta-Solvers: Strategy-Diverse RL for Industrial-Scale Optimization | 用正确性门控的层次多样性奖励，训练模型在求解器、精确组合算法和启发式之间适配策略。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-190] · [![Benchmark Inference][badge-078]][resource-191] · [![SDRL Qwen3 4B][badge-079]][resource-010] · [详情](#paper-sdrl2026) |
| 2026 · arXiv preprint | **SOLID**<br>Beyond Verified Answers: Solver-Informed Self-Distillation for Bootstrapping Operations Research Language Models | 从多次求解 rollout 的目标聚类构建伪参考，以求解器产物做无真值的自蒸馏后训练。 | 方法 · 模型 | [![Paper][badge-049]][resource-194] · [![Code][badge-022]][resource-195] · [![SOLID-Qwen3][badge-080]][resource-015] · [![SOLID-StepORLM][badge-081]][resource-016] · [详情](#paper-solid2026) |
| 2026 · arXiv preprint | **SPO**<br>SPO: Discovering Adaptive Large Neighborhood Search Operators via Stackelberg Program Optimization | 按 Stackelberg 主从关系发现状态依赖的 destroy / repair 程序，并共同更新程序种群与生成器。 | 方法 · 模型 · 应用 | [![Paper][badge-049]][resource-448] · [详情](#paper-spo2026) |
| 2026 · ICLR 2026 | **StepORLM**（核心）<br>StepORLM: A Self-Evolving Framework With Generative Process Supervision For Operations Research Language Models | 让策略模型与生成式过程奖励模型共同演化，融合求解器结果反馈和全程评价。 | 方法 · 模型 | [![Paper 1][badge-051]][resource-357] · [![arXiv][badge-087]][resource-358] · [![Code][badge-022]][resource-359] · [![Policy 8B][badge-009]][resource-017] · [![GenPRM 8B][badge-010]][resource-018] · [详情](#paper-zhou2026steporlm) |
| 2025 · arXiv preprint | **Ask, Clarify, Optimize**<br>Ask, Clarify, Optimize: Human-LLM Agent Collaboration for Smarter Inventory Control | 由 LLM 澄清库存需求并解释结果，把随机优化计算交给算法，以模拟经理测试交互。 | 方法 · 模型 · 应用 | [![Paper][badge-049]][resource-208] · [详情](#paper-askclarify2026) |
| 2025 · ACL 2025, Volume 1: Long Papers, pp. 821–838 | **BPP-Search / StructuredOR**<br>BPP-Search: Enhancing Tree of Thought Reasoning for Mathematical Modeling Problem Solving | 提出 BPP-Search，将束搜索、过程奖励模型和成对偏好机制结合到思维树推理中。 | 方法 · 基准 · 数据 | [![Paper][badge-057]][resource-212] · [![Code][badge-022]][resource-213] · [![Dataset][badge-060]][resource-022] · [详情](#paper-wang2025bppsearch) |
| 2025 · arXiv preprint | **CALM / STORM**<br>CALM Before the STORM: Unlocking Native Reasoning for Optimization Modeling | 用少量纠正提示修订推理轨迹，再经 SFT 与强化学习训练优化建模模型 STORM。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-216] · [详情](#paper-calm2025storm) |
| 2025 · arXiv preprint | **DPLM / DP-Bench**<br>Auto-Formulating Dynamic Programming Problems with Large Language Models | 提出 DP-Bench，并用双向反思合成训练数据，训练从自然语言构造动态规划模型的 DPLM。 | 方法 · 基准 · 数据 · 模型 | [![Paper][badge-049]][resource-225] · [详情](#paper-dpdlm2025) |
| 2025 · arXiv preprint | **HeurAgenix**<br>HeurAgenix: Leveraging LLMs for Solving Complex Combinatorial Optimization Challenges | 先生成与演化启发式库，再按问题状态选择算子；选择器可采用通用 LLM 或领域微调模型。 | 方法 · 模型 | [![Paper][badge-049]][resource-469] · [![Code][badge-022]][resource-470] · [![CO Instances][badge-144]][resource-089] · [详情](#paper-yang2025heuragenix) |
| 2025 · IJCAI 2025 Survey Track | **LLM4OR Survey**（核心）<br>A Survey of Optimization Modeling Meets LLMs: Progress and Future Directions | 综述优化建模全流程，分析并标记基准错误，提供清洗数据与评测门户。 | 综述 · 数据 | [![Paper][badge-049]][resource-237] · [![官方资源库（相关）][badge-094]][resource-238] · [![Cleaned Benchmarks][badge-095]][resource-092] · [详情](#paper-xiao2025survey) |
| 2025 · NeurIPS 2025 | **LLMCoSolver / E2E CO Solver**<br>Large Language Models as End-to-end Combinatorial Optimization Solvers | 经 SFT 与可行性／最优性感知的 FOARL，训练 LLM 从问题描述直接输出组合优化解。 | 方法 · 模型 · 数据 | [![Paper 1][badge-051]][resource-539] · [![Paper 2][badge-052]][resource-540] · [![Code][badge-022]][resource-541] · [![SFT Data][badge-030]][resource-074] · [![RL Data][badge-031]][resource-075] · [详情](#paper-jiang2025e2eco) |
| 2025 · ICLR 2025 | **LLMOPT**（核心）<br>LLMOPT: Learning to Define and Solve General Optimization Problems from Scratch | 通过五要素形式化、多指令微调与自纠错，提高多类优化问题的建模与代码生成泛化。 | 方法 · 模型 | [![Paper 1][badge-051]][resource-239] · [![arXiv][badge-087]][resource-240] · [![Code][badge-022]][resource-241] · [![Model][badge-073]][resource-002] · [详情](#paper-jiang2025llmopt) |
| 2025 · ICLR 2025 | **MILP-Evolve**（核心）<br>Towards Foundation Models for Mixed Integer Linear Programming | 用 LLM 演化生成多样 MILP 类与实例，支持间隙预测、学习分支和语言对齐。 | 方法 · 数据 | [![Paper 1][badge-051]][resource-495] · [![arXiv][badge-087]][resource-496] · [![Code][badge-022]][resource-497] · [![Dataset][badge-060]][resource-076] · [![GitHub Data][badge-012]][resource-498] · [详情](#paper-li2025milpevolve) |
| 2025 · NeurIPS 2025 Main Conference Track, volume 38 | **MURKA**<br>MURKA: Multi-Reward Reinforcement Learning with Knowledge Alignment for Optimization Tasks | 用多奖励强化学习与知识蒸馏对齐 Extractor、Solver、Checker 三类 Agent，支持从文本到可执行优化程序。 | 方法 | [![Paper][badge-057]][resource-253] · [详情](#paper-xie2025murka) |
| 2025 · arXiv preprint | **OptiMind**（核心）<br>OptiMind: Teaching LLMs to Think Like Optimization Experts | 用按优化问题类别组织的专家错误分析指导训练与推理，减少 MILP 形式化常见错误。 | 方法 · 模型 | [![Paper][badge-049]][resource-255] · [![Code][badge-022]][resource-256] · [![Model][badge-073]][resource-005] · [详情](#paper-zhang2025optimind) |
| 2025 · arXiv preprint | **OptiTrust**<br>Toward a Trustworthy Optimization Modeling Agent via Verifiable Synthetic Data Generation | 从带已知最优解的符号问题合成示范，用跨建模语言投票和分步推理训练建模 Agent。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-260] · [详情](#paper-lima2025optitrust) |
| 2025 · ICML 2025; PMLR 267:40769–40802 | **OptMATH**（核心）<br>OptMATH: A Scalable Bidirectional Data Synthesis Framework for Optimization Modeling | 通过数学模型到问题数据再到自然语言的双向合成流程生成优化建模数据，并用正向建模和拒绝采样筛选。 | 方法 · 基准 · 数据 · 模型 | [![Paper][badge-057]][resource-261] · [![Code][badge-022]][resource-054] · [![Model 7B][badge-003]][resource-006] · [![Model 32B][badge-004]][resource-007] · [![Dataset][badge-060]][resource-078] · [详情](#paper-lu2025optmath) |
| 2025 · Operations Research 73(6):2986–3009 | **ORLM**（核心）<br>ORLM: A Customizable Framework in Training Large Models for Automated Optimization Modeling | 通过 OR-Instruct 合成数据训练优化领域模型，并提出工业基准 IndustryOR。 | 方法 · 基准 · 数据 · 模型 | [![Paper 1][badge-058]][resource-266] · [![Journal][badge-104]][resource-267] · [![Code][badge-022]][resource-268] · [![Model][badge-073]][resource-008] · [![IndustryOR][badge-024]][resource-059] · [![OR-Instruct-3K][badge-032]][resource-079] · [详情](#paper-huang2025orlm) |
| 2025 · ICLR 2025 | **ReSocratic / OptiBench**（核心）<br>OptiBench Meets ReSocratic: Measure and Improve LLMs for Optimization Modeling | 先合成数学形式与求解示范再逆向生成问题，配套 OptiBench 与 ReSocratic-29k。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-274] · [![arXiv][badge-087]][resource-275] · [![Code][badge-022]][resource-066] · [详情](#paper-yang2025resocratic) |
| 2025 · NeurIPS 2025 | **SIRL**（核心）<br>Solver-Informed RL: Grounding Large Language Models for Authentic Optimization Modeling | 用求解器检查代码及 LP 实例，构造 RL 可验证奖励，并发布模型与修订评测数据。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-276] · [![arXiv][badge-087]][resource-277] · [![Code][badge-022]][resource-278] · [![Model Gurobi-7B][badge-005]][resource-011] · [![Model COPT-7B][badge-006]][resource-012] · [![Model Gurobi-32B][badge-007]][resource-013] · [![Model COPT-32B][badge-008]][resource-014] · [![修订评测集][badge-045]][resource-099] · [详情](#paper-chen2025sirl) |
| 2025 · arXiv preprint | **Starjob**<br>Starjob: Dataset for LLM-Driven Job Shop Scheduling | 发布作业车间调度训练数据，用 LoRA 微调 LLM 直接输出调度解。 | 方法 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-542] · [![Code][badge-022]][resource-543] · [![Dataset][badge-060]][resource-081] · [详情](#paper-abgaryan2025starjob) |
| 2025 · Findings of EMNLP 2025 | **Step-Opt**<br>Training LLMs for Optimization Modeling via Iterative Data Synthesis and Structured Validation | 逐步提高合成问题复杂度并结构化校验训练数据，再微调优化建模模型。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-281] · [![Paper 2][badge-052]][resource-282] · [![Code][badge-022]][resource-082] · [详情](#paper-wu2025stepopt) |
| 2025 · NeurIPS 2025 | **STRCMP**<br>STRCMP: Integrating Graph Structural Priors with Language Models for Combinatorial Optimization | 将图神经网络的结构先验接入语言模型，通过训练和演化生成求解器专用算法代码。 | 方法 · 模型 | [![Paper 1][badge-051]][resource-366] · [![Paper 2][badge-052]][resource-367] · [![Code][badge-022]][resource-368] · [详情](#paper-li2025strcmp) |
| 2024 · INFOR 62（2024） | **LM4OPT**<br>LM4OPT: Unveiling the potential of Large Language Models in formulating mathematical optimization problems | 先适配数学语料再微调 LP 建模任务，以带噪嵌入训练小模型，并比较零样本与单样本提示。 | 方法 · 模型 · 评测分析 | [![Paper 1][badge-051]][resource-296] · [![Paper 2][badge-052]][resource-297] · [详情](#paper-ahmed2024lm4opt) |
| 2024 · Constraints 29（2024） | **Ner4Opt**<br>Ner4Opt: named entity recognition for optimization modelling from natural language | 从优化问题文本识别变量、参数、目标和约束等实体，比较词法、语义、微调及语言模型方案。 | 方法 · 模型 · 基础 | [![Paper][badge-057]][resource-299] · [![Code][badge-022]][resource-300] · [![ner4opt-roberta-v1][badge-110]][resource-003] · [![ner4opt-roberta-v2][badge-111]][resource-004] · [![HF Demo（相关）][badge-100]][resource-301] · [详情](#paper-dakle2023ner4opt) |
| 2024 · NAACL 2024 Industry Track | **OptLLM**<br>Solving General Natural-Language-Description Optimization Problems with Large Language Models | 通过多轮澄清、公式与代码转换、外部求解器和结果解释支持自然语言优化，并微调 Qwen。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-305] · [![Paper 2][badge-052]][resource-306] · [![MindOpt Trial (International)（相关）][badge-112]][resource-307] · [![MindOpt Trial (CN)（相关）][badge-113]][resource-308] · [详情](#paper-zhang2024optllm) |
| 2024 · arXiv preprint | **Rare MIP Challenges**<br>Leveraging Large Language Models for Solving Rare MIP Challenges | 结合微调、思维链与递归动态温度生成罕见 MIP 场景的可行解。 | 方法 | [![Paper][badge-049]][resource-515] · [详情](#paper-wang2024raremip) |
| 2024 · EMNLP 2024 System Demonstrations | **To the Globe / TTG**<br>To the Globe (TTG): Towards Language-Driven Guaranteed Travel Planning | 将旅行需求译为符号表示，再由 MILP 求解器生成满足已编码约束的行程。 | 方法 · 应用 · 模型 | [![Paper 1][badge-051]][resource-310] · [![Paper 2][badge-052]][resource-311] · [详情](#paper-ju2024ttg) |
| 2023 · arXiv preprint | **AI-Copilot for Business Optimisation**<br>Language Models for Business Optimisation with a Real World Case Study in Production Scheduling | 微调成本较低的 LLM 生成优化公式，并在真实生产排程案例中评估。 | 方法 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-312] · [![Training Data][badge-114]][resource-070] · [![Generated Formulations（相关）][badge-115]][resource-313] · [![Industrial Case Data][badge-116]][resource-071] · [![Industrial Outputs（相关）][badge-117]][resource-314] · [![LPWP Evaluation Data（相关）][badge-118]][resource-315] · [详情](#paper-alahakoon2023copilot) |
| 2023 · ICLR 2023 DL4C Workshop / arXiv | **CodeT5 Mathematical Program Synthesis**<br>Synthesis of Mathematical programs from Natural Language Specifications | 用 GPT-3 反向翻译扩充训练样本，微调 CodeT5，并依据 LP 规则重评和修正候选输出。 | 方法 · 模型 · 基础 | [![Paper][badge-049]][resource-316] · [详情](#paper-synth2023) |
| 2023 · arXiv preprint | **Multi-stage MILP Synthesis**<br>Synthesizing mixed-integer linear programming models from natural language descriptions | 以变量识别、约束／目标分类和模板构建合成 MILP，并扩展 NL4Opt 的逻辑约束与二元变量问题。 | 方法 · 数据 | [![Paper][badge-049]][resource-318] · [![Modeling Data][badge-119]][resource-077] · [详情](#paper-li2023synthesizing) |
| 2023 · arXiv preprint | **NL4Opt: Auto-Formulation Approach**<br>A Novel Approach for Auto-Formulation of Optimization Problems | 在 NL4Opt 竞赛的实体识别和公式生成两任务中，结合预训练、对抗训练、提示和模型集成。 | 方法 · 基础 | [![Paper][badge-049]][resource-321] · [![Code][badge-022]][resource-322] · [详情](#paper-iflytek2023autoformulation) |
| 2023 · arXiv preprint; NL4Opt competition system | **OPD@NL4Opt**<br>OPD@NL4Opt: An ensemble approach for the NER task of the optimization problem | 对预训练语言模型使用差分学习率、对抗训练与集成，完成优化问题描述中的命名实体识别。 | 方法 · 基础 | [![Paper][badge-049]][resource-323] · [![竞赛结果（相关）][badge-120]][resource-324] · [详情](#paper-wang2023opdnl4opt) |

[返回目录](#contents)

<a id="verification"></a>

## 推理、搜索与验证

推理时搜索、过程监督、模型等价性检查与行为验证。

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · ICML 2026 | **A2DEPT**<br>A2DEPT: Large Language Model-Driven Automated Algorithm Design via Evolutionary Program Trees | 以树结构演化、混合选择和分层操作搜索完整算法，并通过执行反馈修复程序。 | 方法 | [![Publication][badge-053]][resource-327] · [![Paper 2][badge-074]][resource-328] · [![Paper 3][badge-075]][resource-329] · [详情](#paper-chen2026a2dept) |
| 2026 · arXiv preprint | **AutoOPT**（探索性）<br>A Domain-Specific Harness for End-to-End Automation of Optimization Research | 连接数值方法设计、LLM 符号推导、Lean 4 验证和人工解释，研究最优一阶优化算法。 | 方法 · 平台 | [![Paper][badge-049]][resource-522] · [![Code][badge-022]][resource-523] · [![Skills][badge-150]][resource-100] · [![Lean Proofs][badge-151]][resource-524] · [详情](#paper-autoopt2026) |
| 2026 · Findings of EMNLP 2026 | **Constraint Injection / VRPCoder**<br>Beyond Objective Equivalence: Constraint Injection for LLM-Based Optimization Modeling on Vehicle Routing Problems | 用可行解和单约束违反解测试 VRP 代码，补充最优值相同仍可能漏约束的检查。 | 方法 · 基准 · 数据 · 模型 · 应用 | [![Publication][badge-053]][resource-335] · [![Paper 2][badge-052]][resource-336] · [![Benchmark Data][badge-122]][resource-025] · [详情](#paper-constraintinjection2026) |
| 2026 · arXiv preprint | **COOPA**<br>COOPA: A Modular LLM Agent Architecture for Operations Research Problems | 迭代比较候选公式的置信度，追踪建模元素的来源，再路由至适用求解器 Agent。 | 方法 | [![Paper][badge-049]][resource-112] · [![Code][badge-022]][resource-113] · [详情](#paper-coopa2026) |
| 2026 · arXiv preprint | **CP-SynC**<br>CP-SynC: Multi-Agent Zero-Shot Constraint Modeling in MiniZinc with Synthesized Checkers | 由建模、检查与选择 Agent 并行探索 MiniZinc 模型，并合成语义检查器聚合证据。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-117] · [![Benchmark & Evaluation][badge-056]][resource-028] · [详情](#paper-cpsync2026) |
| 2026 · AAAI 2026 | **DeepOR**<br>DeepOR: A Deep Reasoning Foundation Model for Optimization Modeling | 以流程图引导长思维链合成和监督微调，再用求解器反馈构造奖励进行强化学习。 | 方法 · 数据 | [![Paper][badge-057]][resource-118] · [![Code][badge-022]][resource-119] · [![官方种子与样例数据][badge-028]][resource-072] · [详情](#paper-xiao2026deepor) |
| 2026 · arXiv preprint | **EvoOR-Agent**<br>Co-evolving Agent Architectures and Interpretable Reasoning for Automated Optimization | 以 AOE 图表示建模—求解工作流，共同演化 Agent 架构与可解释推理路径。 | 方法 | [![Paper][badge-049]][resource-125] · [详情](#paper-coevolve2026) |
| 2026 · arXiv preprint | **Falsification-Based Verification**<br>Falsification-Based Verification of LLM-Generated Optimization Models: Sound Test Batteries and Their Detection Limits | 通过数值角色扰动、对偶与敏感性关系测试生成模型，并刻画可检测错误与盲区。 | 方法 | [![Paper][badge-049]][resource-338] · [详情](#paper-li2026falsification) |
| 2026 · arXiv；NeurIPS 2026 Workshop 版本 | **Formalize, Don't Optimize**<br>Formalize, Don't Optimize: The Heuristic Trap in LLM-Generated Combinatorial Solvers | 用 CP-SynC-XL 比较原生搜索、Python 求解器 API 与 MiniZinc，并审计搜索优化带来的错误。 | 基准 · 数据 | [![Paper 1][badge-058]][resource-126] · [![Workshop][badge-059]][resource-127] · [详情](#paper-wang2026formalize) |
| 2026 · arXiv preprint | **InvEvolve**（探索性）<br>InvEvolve: Evolving White-Box Inventory Policies via Large Language Models with Performance Guarantees | 用 LLM 演化白盒库存策略，并以置信区间认证框架研究部署安全与性能改进。 | 方法 · 应用 | [![Paper][badge-049]][resource-410] · [详情](#paper-invevolve2026) |
| 2026 · LION 20 / 2026（已接收；论文集待确认） | **Latent Heuristic Search**<br>Latent Heuristic Search: Continuous Optimization for Automated Algorithm Design | 学习程序编码、性能代理、可逆流和软提示映射，在连续潜空间中优化并解码为启发式。 | 方法 | [![Paper 1][badge-058]][resource-412] · [![Conference][badge-072]][resource-413] · [![Code][badge-022]][resource-414] · [详情](#paper-latentheuristic2026) |
| 2026 · arXiv preprint | **MiniOpt**<br>MiniOpt: Reasoning to Model and Solve General Optimization Problems with Limited Resources | 以结构化推理连接建模和代码生成，用分层 OptReward 同时反馈公式与解的质量。 | 方法 · 模型 | [![Paper][badge-049]][resource-139] · [![Code][badge-022]][resource-140] · [详情](#paper-zhao2026miniopt) |
| 2026 · arXiv preprint | **MIRROR**<br>MIRROR: A Multi-Agent Framework with Iterative Adaptive Revision and Hierarchical Retrieval for Optimization Modeling in Operations Research | 通过执行驱动的迭代修订与分层检索，获取建模和代码示例来修复优化模型。 | 方法 | [![Paper][badge-049]][resource-144] · [详情](#paper-mirror2026) |
| 2026 · ICML 2026 · PMLR 306 | **NEMO**<br>NEMO: Execution-Aware Optimization Modeling via Autonomous Coding Agents | 用自主编码 Agent 生成优化器与模拟器，再以交叉执行、经验复用和候选一致性改进建模。 | 方法 | [![Paper 1][badge-051]][resource-148] · [![Paper 2][badge-052]][resource-149] · [![Evaluation Artifacts][badge-064]][resource-096] · [详情](#paper-nemo2026) |
| 2026 · arXiv preprint | **OptArgus**（探索性）<br>OptArgus: A Multi-Agent System to Detect Hallucinations in LLM-based Optimization Modeling | 用幻觉分类法和专家 Agent 审计问题描述、数学模型与求解器实现的一致性。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-345] · [详情](#paper-optarcus2026) |
| 2026 · arXiv preprint | **OptiAgent**<br>OptiAgent: End-to-End Optimization Modeling via Multi-Agent Iterative Refinement | 通过专门建模 Agent 与多层反馈循环，提取变量和约束并修正公式及可执行代码。 | 方法 | [![Paper][badge-049]][resource-158] · [详情](#paper-optiagent2026) |
| 2026 · arXiv preprint | **OptiLoop**<br>OptiLoop: Coordination-in-the-Loop Verification and Repair for LLM-Generated Optimization Agents | 在有限轮 ADMM 式协同中测试本地优化 Agent，利用行为与静态证据修复实现或公式。 | 方法 | [![Paper][badge-049]][resource-346] · [详情](#paper-optiloop2026) |
| 2026 · arXiv preprint | **OptiRepair**（探索性）<br>OptiRepair: Closed-Loop Diagnosis and Repair of Supply Chain Optimization Models with LLM Agents | 以 IIS 与运营合理性检查构建两阶段供应链修复闭环，提出 OptiRepair-SC 并训练 P1 / P2 模型。 | 方法 · 基准 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-347] · [详情](#paper-optirepair2026) |
| 2026 · Findings of ACL 2026 | **OptiVerse / DVA-Agent**<br>OptiVerse: A Comprehensive Benchmark towards Optimization Problem Solving | 以 1,000 道多范式优化题评测建模与求解，并用双视角审核 Agent 对照需求与代码语义。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-162] · [![Paper 2][badge-052]][resource-163] · [![Inference, Auditor & Evaluation][badge-068]][resource-053] · [![OptiVerse 1K][badge-069]][resource-052] · [详情](#paper-optiverse2026) |
| 2026 · Findings of EMNLP 2026 | **OptSkills**<br>OptSkills: Learning Generalizable Optimization Skills from Problem Archetypes via Cluster-Based Distillation | 按问题原型聚类，从成功建模轨迹提炼、检索并更新可复用的工作流技能。 | 方法 | [![Publication][badge-053]][resource-164] · [![Paper 2][badge-052]][resource-165] · [![Code 1][badge-070]][resource-166] · [![Code 2][badge-071]][resource-167] · [![官方技能库（相关）][badge-048]][resource-102] · [详情](#paper-yang2026optskills) |
| 2026 · ICLR 2026 | **OR-PRM**<br>OR-PRM: A Process Reward Model for Algorithmic Problem in Operations Research | 先清洗已有合成数据，基于 MCTS 和逐步检查构建 OR-ProcessQA，再训练用于建模推理的过程奖励模型。 | 方法 · 数据 · 模型 | [![Paper][badge-057]][resource-168] · [详情](#paper-wang2026orprm) |
| 2026 · ICML 2026 | **ORLoopBench**<br>ORLoopBench: Solver-in-the-Loop Benchmarks for Self-Correction and Behavioral Rationality in Operations Research | 以 IIS 和求解器重执行定义不可行模型修复闭环，配套 ORDebug 与 ORBias 评测。 | 方法 · 基准 · 数据 · 模型 | [![Publication][badge-053]][resource-348] · [![Paper 2][badge-052]][resource-349] · [![数据与校验代码][badge-125]][resource-060] · [详情](#paper-ao2026orloopbench) |
| 2026 · Artificial Intelligence for Transportation 6（2026） | **ORThought / LogiOR**<br>ORThought: Benchmarking and automating logistics optimization modeling via structured LLM reasoning | 以专家建模原则指导结构化双 Agent 推理，并发布物流建模基准 LogiOR。 | 方法 · 基准 · 数据 | [![Publication][badge-053]][resource-174] · [![Paper 2][badge-052]][resource-175] · [![Code][badge-022]][resource-176] · [![Dataset][badge-060]][resource-062] · [详情](#paper-yang2025orthought) |
| 2026 · ICML 2026 · PMLR 306 | **PathWise**<br>PathWise: Planning through World Model for Automated Heuristic Design via Self-Evolving LLMs | 在保存搜索历史的蕴含图上规划演化动作，由策略、世界模型和评论 Agent 协作生成启发式。 | 方法 | [![Paper 1][badge-051]][resource-438] · [![Paper 2][badge-052]][resource-439] · [![Code][badge-022]][resource-440] · [详情](#paper-pathwise2026) |
| 2026 · NeurIPS 2026（已接收，待出版） | **ReLoop / RetailOpt-190**（探索性）<br>ReLoop: Structured Modeling and Behavioral Verification for Reliable LLM-Based Optimization | 结合结构化建模链与求解器参数扰动检查，定位静默错误并实施诊断引导修复。 | 方法 · 基准 · 数据 | [![Paper 1][badge-058]][resource-350] · [![Conference][badge-072]][resource-351] · [![Code][badge-022]][resource-352] · [![Dataset][badge-060]][resource-065] · [详情](#paper-lian2026reloop) |
| 2026 · ICML 2026 · PMLR 306 | **SAC-Opt**<br>SAC-Opt: Semantic Anchors for Iterative Correction in Optimization Modeling | 把生成代码回译为语义锚点，与原始需求对齐后定点修正约束和目标。 | 方法 | [![Paper 1][badge-051]][resource-184] · [![Paper 2][badge-052]][resource-185] · [![Code][badge-022]][resource-186] · [详情](#paper-ma2025sacopt) |
| 2026 · Findings of EMNLP 2026 | **SOVER / NLEquiv-150**<br>SOVER: Formal Certification of Optimization Reformulations via LLM-Assisted SMT Verification | 由 LLM 提取重构映射，再用 Z3 或 dReal 核验公式之间的可行性及目标关系。 | 方法 · 基准 · 数据 | [![Publication][badge-053]][resource-355] · [![Paper 2][badge-052]][resource-356] · [![Code][badge-022]][resource-068] · [![EquivaFormulation（使用）（相关）][badge-127]][resource-032] · [![NLP4LP（使用）（相关）][badge-128]][resource-051] · [详情](#paper-bhattacharyya2026sover) |
| 2026 · ICLR 2026 | **StepORLM**（核心）<br>StepORLM: A Self-Evolving Framework With Generative Process Supervision For Operations Research Language Models | 让策略模型与生成式过程奖励模型共同演化，融合求解器结果反馈和全程评价。 | 方法 · 模型 | [![Paper 1][badge-051]][resource-357] · [![arXiv][badge-087]][resource-358] · [![Code][badge-022]][resource-359] · [![Policy 8B][badge-009]][resource-017] · [![GenPRM 8B][badge-010]][resource-018] · [详情](#paper-zhou2026steporlm) |
| 2026 · ICML 2026 · PMLR 306 | **VeriSimpl**<br>VeriSimpl: Robust Optimization Modeling from Natural Language using Simplification-based Verification | 用求解器构造简化诊断问题，帮助 LLM 检查模型是否符合自然语言题意。 | 方法 | [![Publication][badge-053]][resource-201] · [![Paper 2][badge-052]][resource-202] · [![Conference][badge-072]][resource-203] · [![官方项目（仅 README）（相关）][badge-086]][resource-204] · [详情](#paper-verisimpl2026) |
| 2025 · arXiv preprint | **AIM-Bench**<br>AIM-Bench: Evaluating Decision-making Biases of Agentic LLM as Inventory Manager | 在不确定库存补货实验中检查 LLM Agent 的决策偏差与信息共享效果。 | 基准 · 数据 · 评测分析 | [![Paper][badge-049]][resource-544] · [详情](#paper-zhao2025aimbench) |
| 2025 · ICML 2025 | **Autoformulation**（核心）<br>Autoformulation of Mathematical Optimization Models Using LLMs | 使用 MCTS 搜索候选优化模型，通过符号剪枝与 LLM 部分模型估值引导探索。 | 方法 | [![Paper 1][badge-051]][resource-209] · [![arXiv][badge-087]][resource-210] · [![Code][badge-022]][resource-211] · [详情](#paper-astorga2025autoformulation) |
| 2025 · ACL 2025, Volume 1: Long Papers, pp. 821–838 | **BPP-Search / StructuredOR**<br>BPP-Search: Enhancing Tree of Thought Reasoning for Mathematical Modeling Problem Solving | 提出 BPP-Search，将束搜索、过程奖励模型和成对偏好机制结合到思维树推理中。 | 方法 · 基准 · 数据 | [![Paper][badge-057]][resource-212] · [![Code][badge-022]][resource-213] · [![Dataset][badge-060]][resource-022] · [详情](#paper-wang2025bppsearch) |
| 2025 · arXiv preprint | **Component-Level Evaluation**<br>Peering Inside the Black Box: Uncovering LLM Errors in Optimization Modelling through Component-Level Evaluation | 按变量、约束、目标的覆盖和数值误差评价模型，补充最优值与运行时间指标。 | 方法 | [![Paper][badge-049]][resource-217] · [详情](#paper-peering2025) |
| 2025 · ICML 2025 | **EquivaMap**（核心）<br>EquivaMap: Leveraging LLMs for Automatic Equivalence Checking of Optimization Formulations | 用 LLM 寻找决策变量映射来检查 Quasi-Karp 等价，并构建 EquivaFormulation。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-230] · [![arXiv][badge-087]][resource-231] · [![Code][badge-022]][resource-232] · [![Dataset][badge-060]][resource-032] · [详情](#paper-zhai2025equivamap) |
| 2025 · ICML 2025 | **MCTS-AHD**（核心）<br>Monte Carlo Tree Search for Comprehensive Exploration in LLM-Based Automatic Heuristic Design | 将生成的启发式组织为 MCTS 搜索树，继续探索暂时低分候选的潜力。 | 方法 | [![Paper 1][badge-051]][resource-489] · [![arXiv][badge-087]][resource-490] · [![Code][badge-022]][resource-491] · [详情](#paper-zheng2025mctsahd) |
| 2025 · arXiv preprint | **OptiMind**（核心）<br>OptiMind: Teaching LLMs to Think Like Optimization Experts | 用按优化问题类别组织的专家错误分析指导训练与推理，减少 MILP 形式化常见错误。 | 方法 · 模型 | [![Paper][badge-049]][resource-255] · [![Code][badge-022]][resource-256] · [![Model][badge-073]][resource-005] · [详情](#paper-zhang2025optimind) |
| 2025 · NeurIPS 2025 | **OptiTree**（核心）<br>OptiTree: Hierarchical Thoughts Generation with Tree Search for LLM Optimization Modeling | 利用层级建模树搜索，将复杂优化问题自适应分解为可复用的简单建模思路。 | 方法 | [![Publication][badge-053]][resource-257] · [![Paper 2][badge-052]][resource-258] · [![Code][badge-022]][resource-259] · [详情](#paper-liu2025optitree) |
| 2025 · arXiv preprint | **OptiTrust**<br>Toward a Trustworthy Optimization Modeling Agent via Verifiable Synthetic Data Generation | 从带已知最优解的符号问题合成示范，用跨建模语言投票和分步推理训练建模 Agent。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-260] · [详情](#paper-lima2025optitrust) |
| 2025 · arXiv；相关 ICML 2026 Workshop 版本 | **ORGEval / Bench4Opt**（核心）<br>ORGEval: Graph-Theoretic Evaluation of LLMs in Optimization Modeling | 将优化形式化表示为图，通过图同构及对称可分解条件下的 WL 测试评价结构等价性。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-264] · [![ICML workshop poster（相关）][badge-103]][resource-265] · [详情](#paper-ding2026orgeval) |
| 2025 · ACL 2025 Industry Track | **ORMind**<br>ORMind: A Cognitive-Inspired End-to-End Reasoning Framework for Operations Research | 以认知启发的角色协作、执行修复和反事实检查完成优化建模。 | 方法 | [![Paper 1][badge-051]][resource-269] · [![Paper 2][badge-052]][resource-270] · [![Code][badge-022]][resource-271] · [详情](#paper-ormind2025) |
| 2025 · arXiv（2026 修订） | **ReflecSched**（探索性）<br>ReflecSched: Solving Dynamic Flexible Job-Shop Scheduling via LLM-Powered Hierarchical Reflection | 从多规划时域的启发式仿真中提炼战略经验，指导动态柔性作业车间调度决策。 | 方法 · 应用 | [![Paper][badge-049]][resource-535] · [详情](#paper-cao2025reflecsched) |
| 2025 · NeurIPS 2025 | **SIRL**（核心）<br>Solver-Informed RL: Grounding Large Language Models for Authentic Optimization Modeling | 用求解器检查代码及 LP 实例，构造 RL 可验证奖励，并发布模型与修订评测数据。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-276] · [![arXiv][badge-087]][resource-277] · [![Code][badge-022]][resource-278] · [![Model Gurobi-7B][badge-005]][resource-011] · [![Model COPT-7B][badge-006]][resource-012] · [![Model Gurobi-32B][badge-007]][resource-013] · [![Model COPT-32B][badge-008]][resource-014] · [![修订评测集][badge-045]][resource-099] · [详情](#paper-chen2025sirl) |
| 2025 · NeurIPS 2025 | **SolverLLM**<br>SolverLLM: Leveraging Test-Time Scaling for Optimization Problem via LLM-Guided Search | 用动态扩展的 MCTS 搜索公式和求解器代码，以提示和不确定性回传指导测试时探索。 | 方法 | [![Paper 1][badge-051]][resource-279] · [![Paper 2][badge-052]][resource-280] · [详情](#paper-solverllm2025) |
| 2024 · LREC-COLING 2024 | **Human-aligned LPWP Evaluation**<br>Towards Human-aligned Evaluation for Linear Programming Word Problems | 以图编辑距离比较线性规划模型，并以人工评分研究评价指标与人类判断的一致性。 | 方法 · 评测分析 | [![Paper][badge-057]][resource-292] · [详情](#paper-xing2024lpwp) |
| 2024 · INFOR 62(4):599–617 | **Multi-Stage Modeling & Verification**<br>Optimization modeling and verification from problem specifications using a multi-agent multi-stage LLM framework | 分阶段从问题规格生成数学模型与 Zimpl 代码，并由多个 LLM Agent 交叉检查。 | 方法 · 基准 · 数据 | [![Paper][badge-057]][resource-298] · [详情](#paper-mostajabdaveh2024multiagent) |
| 2024 · INFOR 2024 | **OptiChat / Infeasibility Diagnosis**<br>Diagnosing Infeasible Optimization Problems Using Large Language Models | 通过 GPT-4、求解器 IIS 与对话界面解释不可行原因，并建议模型修复。 | 方法 | [![Paper 1][badge-058]][resource-369] · [![Publication][badge-053]][resource-370] · [![Code][badge-022]][resource-098] · [详情](#paper-chen2023diagnosing) |
| 2024 · arXiv preprint | **Rare MIP Challenges**<br>Leveraging Large Language Models for Solving Rare MIP Challenges | 结合微调、思维链与递归动态温度生成罕见 MIP 场景的可行解。 | 方法 | [![Paper][badge-049]][resource-515] · [详情](#paper-wang2024raremip) |
| 2024 · NeurIPS 2024 | **ReEvo**（核心）<br>ReEvo: Large Language Models as Hyper-Heuristics with Reflective Evolution | 结合进化搜索与 LLM 反思，用语言反馈指导超启发式程序改进。 | 方法 | [![Paper 1][badge-051]][resource-516] · [![arXiv][badge-087]][resource-517] · [![Code][badge-022]][resource-518] · [详情](#paper-ye2024reevo) |

[返回目录](#contents)

<a id="benchmarks"></a>

## Benchmarks、数据集与评测

提出基准、数据集、评测方法或系统性评测分析；仅用已有基准验证新方法不归入本模块。

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · arXiv preprint | **Agora-Opt**<br>From Soliloquy to Agora: Memory-Enhanced LLM Agents with Decentralized Debate for Optimization Modeling | 由多个 Agent 团队独立建模并开展结果驱动辩论，以读写记忆复用求解经验和分歧修订。 | 方法 · 数据 | [![Paper][badge-049]][resource-103] · [![Code & Cleaned Data][badge-050]][resource-083] · [详情](#paper-soliloquy2026) |
| 2026 · Nature Communications（2026） | **AutoModSAT**<br>Discovering heuristics in a complex SAT solver with large language models | 结合模块化 SAT 求解器、提示优化和进化搜索，发现复杂求解器中的有效启发式。 | 方法 · 数据 | [![Paper 1][badge-051]][resource-374] · [![Paper 2][badge-052]][resource-375] · [![Code Archive][badge-132]][resource-376] · [![Evaluation Data][badge-133]][resource-084] · [详情](#paper-sun2025satheur) |
| 2026 · ICML 2026 RLxF Workshop / arXiv | **AutoOR**<br>AutoOR: Scalably Post-training LLMs to Autoformulate Operations Research Problems | 从标准优化形式合成训练样本，并以执行反馈和课程式 RL 训练自然语言到模型的能力。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-104] · [![Paper 2][badge-052]][resource-105] · [详情](#paper-autoor2026) |
| 2026 · arXiv preprint | **AutoREM / AutoRO-Bench**<br>Automated Reformulation of Robust Optimization via Memory-Augmented Large Language Models | 以失败经验记忆辅助鲁棒优化的确定性重构，并提出 AutoRO-Bench。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-106] · [详情](#paper-robustreform2026) |
| 2026 · LION 19 / LNCS 15745（2026 出版） | **CHORUS**<br>CHORUS: Zero-shot Hierarchical Retrieval and Orchestration for Generating Linear Programming Code | 用分层文档切分、元数据检索和重排，为 LLM 生成 Gurobi LP 代码提供相关知识。 | 方法 · 基准 · 数据 | [![Publication][badge-053]][resource-107] · [![Paper 2][badge-052]][resource-108] · [详情](#paper-lporch2025) |
| 2026 · arXiv preprint | **CIR / R2C**<br>Canonical Intermediate Representation for LLM-based optimization problem formulation and code generation | 以规范中间表示编码复杂规则，再检索知识并生成约束实现。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-109] · [详情](#paper-canonicalir2026) |
| 2026 · AAAI 2026 | **CO-Bench**（核心）<br>CO-Bench: Benchmarking Language Model Agents in Algorithm Search for Combinatorial Optimization | 提供组合优化算法搜索基准，比较 LLM Agent 与人工设计算法。 | 基准 · 数据 | [![Proceedings][badge-105]][resource-384] · [![Paper 2][badge-052]][resource-385] · [![Code][badge-022]][resource-386] · [![Dataset][badge-060]][resource-024] · [详情](#paper-sun2026cobench) |
| 2026 · Inteligencia Artificial 29（2026） | **Combinatorial Optimization for All**<br>Combinatorial Optimization for All: Using LLMs to Aid Non-Experts in Improving Optimization Algorithms | 以较少专业知识的提示改进十种已有 TSP 算法，比较解质量、运行时间和代码复杂度。 | 方法 · 评测分析 | [![Paper 1][badge-051]][resource-387] · [![Paper 2][badge-074]][resource-388] · [![Paper 3][badge-075]][resource-389] · [![Prompts & Algorithms][badge-134]][resource-390] · [![Project（相关）][badge-135]][resource-391] · [详情](#paper-co4all2025) |
| 2026 · Findings of EMNLP 2026 | **Constraint Injection / VRPCoder**<br>Beyond Objective Equivalence: Constraint Injection for LLM-Based Optimization Modeling on Vehicle Routing Problems | 用可行解和单约束违反解测试 VRP 代码，补充最优值相同仍可能漏约束的检查。 | 方法 · 基准 · 数据 · 模型 · 应用 | [![Publication][badge-053]][resource-335] · [![Paper 2][badge-052]][resource-336] · [![Benchmark Data][badge-122]][resource-025] · [详情](#paper-constraintinjection2026) |
| 2026 · arXiv preprint | **ConstraintBench**<br>ConstraintBench: Benchmarking LLM Constraint Reasoning on Direct Optimization | 要求 LLM 直接输出结构化解，使用确定性校验器逐约束检查并与 Gurobi 最优解比较。 | 基准 · 数据 | [![Paper][badge-049]][resource-545] · [详情](#paper-constraintbench2026) |
| 2026 · LLM4Code 2026 Workshop @ ICSE | **CP-Agent**<br>CP-Agent: Agentic Constraint Programming | 通过持久 IPython 内核和简短领域提示，执行并迭代修正约束模型。 | 方法 · 数据 | [![Paper 1][badge-051]][resource-114] · [![Paper 2][badge-052]][resource-115] · [![Author Coding Agent（相关）][badge-054]][resource-116] · [![Evaluation Archive v2][badge-055]][resource-087] · [详情](#paper-cpagent2025) |
| 2026 · arXiv preprint | **CP-SynC**<br>CP-SynC: Multi-Agent Zero-Shot Constraint Modeling in MiniZinc with Synthesized Checkers | 由建模、检查与选择 Agent 并行探索 MiniZinc 模型，并合成语义检查器聚合证据。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-117] · [![Benchmark & Evaluation][badge-056]][resource-028] · [详情](#paper-cpsync2026) |
| 2026 · AAAI 2026 | **DeepOR**<br>DeepOR: A Deep Reasoning Foundation Model for Optimization Modeling | 以流程图引导长思维链合成和监督微调，再用求解器反馈构造奖励进行强化学习。 | 方法 · 数据 | [![Paper][badge-057]][resource-118] · [![Code][badge-022]][resource-119] · [![官方种子与样例数据][badge-028]][resource-072] · [详情](#paper-xiao2026deepor) |
| 2026 · arXiv preprint | **DScheLLM**<br>DScheLLM: Enabling Dynamic Scheduling through a Fine-Tuned Dual-System Large language Model | 用求解器排程合成快／慢思考示范，LoRA 微调双系统 LLM 应对动态扰动。 | 方法 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-337] · [详情](#paper-zhang2026dschellm) |
| 2026 · ICML 2026 · PMLR 306 | **DynaSchedBench**<br>DynaSchedBench: Calibrated Dynamic Scheduling Benchmarks and Observability Paradox in LLM-based Scheduling Agents | 校准动态柔性车间实例难度，统一仿真、轨迹评测和不同观测条件下的 Agent 比较。 | 方法 · 基准 · 数据 · 应用 | [![Paper 1][badge-051]][resource-546] · [![Paper 2][badge-052]][resource-547] · [![Code][badge-022]][resource-029] · [![Project（相关）][badge-135]][resource-548] · [详情](#paper-dynaschedbench2026) |
| 2026 · NeurIPS 2026（已接收，待出版） | **EvoOptiGraph**<br>EvoOptiGraph: Weakness-Driven Coevolution via Graph-Based Structural Generation for Optimization Modeling | 以属性二部图演化结构多样的 MILP，结合编译、回译、SFT 与 RLVR 针对模型弱点更新训练分布。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-123] · [![Paper 2][badge-052]][resource-124] · [详情](#paper-evooptigraph2026) |
| 2026 · arXiv preprint | **Falsification-Based Verification**<br>Falsification-Based Verification of LLM-Generated Optimization Models: Sound Test Batteries and Their Detection Limits | 通过数值角色扰动、对偶与敏感性关系测试生成模型，并刻画可检测错误与盲区。 | 方法 | [![Paper][badge-049]][resource-338] · [详情](#paper-li2026falsification) |
| 2026 · arXiv；NeurIPS 2026 Workshop 版本 | **Formalize, Don't Optimize**<br>Formalize, Don't Optimize: The Heuristic Trap in LLM-Generated Combinatorial Solvers | 用 CP-SynC-XL 比较原生搜索、Python 求解器 API 与 MiniZinc，并审计搜索优化带来的错误。 | 基准 · 数据 | [![Paper 1][badge-058]][resource-126] · [![Workshop][badge-059]][resource-127] · [详情](#paper-wang2026formalize) |
| 2026 · NeurIPS 2026（已接收，待出版） | **FrontierOR**<br>FrontierOR: Benchmarking LLMs' Capacity for Efficient Algorithm Design in Large-Scale Optimization | 评测 LLM 在文献驱动的大规模 OR 任务中生成高效且可行算法的能力。 | 基准 · 数据 | [![Paper 1][badge-051]][resource-131] · [![Paper 2][badge-052]][resource-132] · [![Code][badge-022]][resource-034] · [![Dataset][badge-060]][resource-033] · [详情](#paper-kong2026frontieror) |
| 2026 · arXiv preprint | **GenAI Beer Game Reliability**<br>Reliability and Effectiveness of Autonomous AI Agents in Supply Chain Management | 在多级 Beer Game 中研究 Agent 决策波动，并比较强化学习后训练与运营护栏的可靠性。 | 方法 · 评测分析 · 应用 | [![Paper][badge-049]][resource-525] · [详情](#paper-beergame2026) |
| 2026 · ICLR 2026 | **HeuriGym**<br>HeuriGym: An Agentic Benchmark for LLM-Crafted Heuristics in Combinatorial Optimization | 让 LLM 通过代码运行反馈迭代生成组合优化启发式，并联合衡量质量与有效产出。 | 基准 · 平台 | [![Publication][badge-053]][resource-403] · [![Paper 2][badge-052]][resource-404] · [![Code][badge-022]][resource-035] · [![Leaderboard（相关）][badge-137]][resource-405] · [详情](#paper-chen2025heurigym) |
| 2026 · arXiv preprint | **Infeasibility-Aware CO Models**<br>Infeasibility Aware Large Language Models for Combinatorial Optimization | 用精确优化与可认证筛选构建可行／不可行训练样本，微调模型输出解或不可行判断，再辅助局部搜索。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-409] · [![Author Code / Data Archive（相关）][badge-138]][resource-073] · [详情](#paper-infeasibilityaware2026) |
| 2026 · arXiv preprint | **Interactive Optimization Conversations**<br>Let's Have a Conversation: Designing and Evaluating LLM Agents for Interactive Optimization | 用带内部效用函数的决策 Agent 扮演利益相关者，评测多轮交互优化而非只看单次答案。 | 方法 · 数据 · 应用 | [![Paper][badge-049]][resource-133] · [![Code][badge-022]][resource-090] · [详情](#paper-conversation2026) |
| 2026 · arXiv preprint | **InventoryBench**<br>AI Agents for Inventory Control: Human-LLM-OR Complementarity | 构建库存决策基准，并结合人类实验研究 OR、LLM 和人工决策的互补性。 | 方法 · 基准 · 数据 · 应用 | [![Paper][badge-049]][resource-526] · [![InventoryBench][badge-152]][resource-036] · [![人机实验平台][badge-153]][resource-527] · [详情](#paper-invbench2026) |
| 2026 · arXiv preprint | **JOR-Bench**<br>JOR-Bench: Japanese Operations Research Benchmarks for Large Language Models | 将五组既有英文 OR 评测译为日文，比较跨语言建模与求解表现。 | 基准 · 数据 | [![Paper][badge-049]][resource-549] · [![Japanese / English OR Data][badge-157]][resource-037] · [详情](#paper-jorbench2026) |
| 2026 · arXiv preprint | **LEAN-LLM-OPT**<br>Large-Scale Optimization Model Auto-Formulation: Harnessing LLM Flexibility via Structured Workflow | 动态构建建模工作流并将数据处理交给工具，面向大规模优化和航空收入管理。 | 方法 · 基准 · 数据 · 应用 | [![Paper][badge-049]][resource-134] · [![Code][badge-022]][resource-038] · [详情](#paper-liang2026leanllmopt) |
| 2026 · IEEE TEVC 30（2026） | **LLaMoCo**<br>LLaMoCo: Instruction Tuning of Large Language Models for Optimization Code Generation | 构造问题—优化代码指令集，以对比学习预热和指令微调训练从问题代码生成优化程序的模型。 | 方法 · 模型 · 数据 | [![Paper 1][badge-051]][resource-339] · [![Paper 2][badge-052]][resource-340] · [![LLaMoCo-S Example][badge-123]][resource-341] · [![LLaMoCo-S][badge-124]][resource-001] · [详情](#paper-ma2024llamoco) |
| 2026 · Computers & Operations Research 196（2026-12 编期） | **LLM Representations for Algorithm Selection**<br>Behavior and representation in open-weight Large Language Models for combinatorial optimization: From feature extraction to algorithm selection | 在冻结的开源 LLM 上比较显式特征提取、隐藏层探测和逐实例算法选择的可用信息。 | 评测分析 | [![Paper 1][badge-051]][resource-417] · [![Paper 2][badge-052]][resource-418] · [![Code & Analysis Data][badge-139]][resource-091] · [详情](#paper-behaviorrep2025) |
| 2026 · arXiv preprint | **MIND**<br>Automated Optimization Modeling via a Localizable Error-Driven Perspective | 依据建模错误的局部性合成针对性训练问题，并用 DFPO 对困难样本做局部修订。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-138] · [详情](#paper-mind2026) |
| 2026 · ICML 2026 | **MIPLIB-NL**（核心）<br>Constructing Industrial-Scale Optimization Modeling Benchmark | 从 MIPLIB 2017 真实 MILP 逆向恢复可复用结构，分离问题与数据，构建自然语言建模基准。 | 基准 · 数据 | [![Publication][badge-053]][resource-141] · [![Paper 2][badge-052]][resource-142] · [![Code][badge-022]][resource-042] · [![GitHub dataset][badge-063]][resource-143] · [详情](#paper-li2026miplibnl) |
| 2026 · NeurIPS 2026（已接收，待出版） | **MM-OptBench**<br>MM-OptBench: A Solver-Grounded Benchmark for Multimodal Optimization Modeling | 以文本和表格、图、地图等视觉输入评测优化公式与求解器代码生成。 | 基准 · 数据 | [![Paper 1][badge-051]][resource-145] · [![Paper 2][badge-052]][resource-146] · [详情](#paper-zhu2026mmoptbench) |
| 2026 · Findings of ACL 2026 | **NLCO**<br>Reasoning in a Combinatorial and Constrained World: Benchmarking LLMs on Natural-Language Combinatorial Optimization | 评测直接从自然语言情景输出离散解的能力，按变量、约束、全局结构与目标分层分析。 | 基准 · 数据 | [![Paper 1][badge-051]][resource-550] · [![Paper 2][badge-052]][resource-551] · [![Code][badge-022]][resource-046] · [![Dataset][badge-060]][resource-045] · [详情](#paper-jiang2026nlco) |
| 2026 · arXiv preprint | **OPF Constrained Reasoning Study**<br>Can Large Language Models Reason and Optimize Under Constraints? | 在最优潮流场景中测试结构化输入、算术及物理约束下的直接推理和优化能力。 | 评测分析 | [![Paper][badge-049]][resource-552] · [详情](#paper-opf2026reason) |
| 2026 · Findings of ACL 2026 | **OPT-BENCH / OPT-Agent**<br>OPT-BENCH: Evaluating the Iterative Self-Optimization of LLM Agents in Large-Scale Search Spaces | 在机器学习调优与 NP 问题中评测迭代自优化，并用 OPT-Agent 复用历史反馈修订方案。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-529] · [![Paper 2][badge-052]][resource-530] · [![Revised Preprint][badge-154]][resource-531] · [![Code][badge-022]][resource-048] · [![Dataset][badge-060]][resource-047] · [详情](#paper-li2026optbench) |
| 2026 · ICML 2026 · PMLR 306 | **OPT-Engine**<br>OPT-Engine: Benchmarking the Limits of LLMs in Optimization Modeling via Complexity Scaling | 可控地扩展 OR 问题复杂度，比较文本推理、工具调用与求解器集成。 | 基准 · 数据 | [![Paper 1][badge-051]][resource-150] · [![Paper 2][badge-052]][resource-151] · [![Code][badge-022]][resource-050] · [![Dataset][badge-060]][resource-049] · [详情](#paper-chen2026optengine) |
| 2026 · ICML 2026 · PMLR 306 | **Opt-Miner**<br>Opt-Miner: Empowering Information-Seeking Agent with Tree-Guided Data Synthesis for Optimization Modeling | 用树结构合成带知识缺口的优化任务，并以 R-GRPO 训练主动检索知识的建模 Agent。 | 方法 · 数据 · 模型 | [![Paper][badge-057]][resource-152] · [![Reproduction Code（第三方）][badge-065]][resource-153] · [![Reproduction Results（第三方）][badge-066]][resource-097] · [![Demo（第三方）][badge-067]][resource-154] · [详情](#paper-optminer2026) |
| 2026 · arXiv preprint | **OptArgus**（探索性）<br>OptArgus: A Multi-Agent System to Detect Hallucinations in LLM-based Optimization Modeling | 用幻觉分类法和专家 Agent 审计问题描述、数学模型与求解器实现的一致性。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-345] · [详情](#paper-optarcus2026) |
| 2026 · arXiv preprint | **Opti-Agent-Bench**<br>Opti-Agent-Bench: Benchmarking End-to-End Optimization R&D Agents on Real-World Business Problems | 评测业务理解、形式化、实现与报告，并检查跨模块一致性和任务评分有效性。 | 基准 · 数据 | [![Paper][badge-049]][resource-157] · [详情](#paper-optiagentbench2026) |
| 2026 · INFORMS Journal on Data Science 5(3):199–220 | **OptiChat**<br>OptiChat: Bridging Optimization Models and Practitioners with Large Language Models | 用自然语言查询已有优化模型，支持不可行诊断、敏感性、what-if 和反事实解释。 | 方法 · 数据 | [![Paper 1][badge-051]][resource-159] · [![Paper 2][badge-052]][resource-160] · [![Code][badge-022]][resource-098] · [详情](#paper-chen2025optichat) |
| 2026 · arXiv preprint | **OptiDSL**<br>Not All Problems Are Best Modeled as MILP: A DSL-Centric Framework for Flexible and Accurate Optimization Modeling | 将自然语言映射为领域 DSL，再接入专用求解器，避免所有问题强制采用 MILP。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-161] · [详情](#paper-dslmilp2026) |
| 2026 · arXiv preprint | **OptiRepair**（探索性）<br>OptiRepair: Closed-Loop Diagnosis and Repair of Supply Chain Optimization Models with LLM Agents | 以 IIS 与运营合理性检查构建两阶段供应链修复闭环，提出 OptiRepair-SC 并训练 P1 / P2 模型。 | 方法 · 基准 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-347] · [详情](#paper-optirepair2026) |
| 2026 · Findings of ACL 2026 | **OptiVerse / DVA-Agent**<br>OptiVerse: A Comprehensive Benchmark towards Optimization Problem Solving | 以 1,000 道多范式优化题评测建模与求解，并用双视角审核 Agent 对照需求与代码语义。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-162] · [![Paper 2][badge-052]][resource-163] · [![Inference, Auditor & Evaluation][badge-068]][resource-053] · [![OptiVerse 1K][badge-069]][resource-052] · [详情](#paper-optiverse2026) |
| 2026 · ICLR 2026 | **OR-PRM**<br>OR-PRM: A Process Reward Model for Algorithmic Problem in Operations Research | 先清洗已有合成数据，基于 MCTS 和逐步检查构建 OR-ProcessQA，再训练用于建模推理的过程奖励模型。 | 方法 · 数据 · 模型 | [![Paper][badge-057]][resource-168] · [详情](#paper-wang2026orprm) |
| 2026 · arXiv preprint | **OR-Space**<br>OR-Space: A Full-Lifecycle Workspace Benchmark for Industrial Optimization Agents | 用持久多文件工作区评测模型构建、需求变更和基于证据的解释三类生命周期任务。 | 基准 · 数据 | [![Paper][badge-049]][resource-172] · [![Code][badge-022]][resource-057] · [![Dataset][badge-060]][resource-056] · [详情](#paper-zhou2026orspace) |
| 2026 · arXiv preprint | **ORAgentBench**<br>ORAgentBench: Can LLM Agents Solve Challenging Operations Research Tasks End to End? | 在隔离工作环境中评测从业务说明、多文件材料到可验证决策的完整 OR 任务。 | 基准 · 数据 | [![Paper][badge-049]][resource-173] · [![Code][badge-022]][resource-058] · [详情](#paper-oragentbench2026) |
| 2026 · ICML 2026 | **ORLoopBench**<br>ORLoopBench: Solver-in-the-Loop Benchmarks for Self-Correction and Behavioral Rationality in Operations Research | 以 IIS 和求解器重执行定义不可行模型修复闭环，配套 ORDebug 与 ORBias 评测。 | 方法 · 基准 · 数据 · 模型 | [![Publication][badge-053]][resource-348] · [![Paper 2][badge-052]][resource-349] · [![数据与校验代码][badge-125]][resource-060] · [详情](#paper-ao2026orloopbench) |
| 2026 · Artificial Intelligence for Transportation 6（2026） | **ORThought / LogiOR**<br>ORThought: Benchmarking and automating logistics optimization modeling via structured LLM reasoning | 以专家建模原则指导结构化双 Agent 推理，并发布物流建模基准 LogiOR。 | 方法 · 基准 · 数据 | [![Publication][badge-053]][resource-174] · [![Paper 2][badge-052]][resource-175] · [![Code][badge-022]][resource-176] · [![Dataset][badge-060]][resource-062] · [详情](#paper-yang2025orthought) |
| 2026 · arXiv preprint | **PowerAtlas / ECBench**<br>PowerAtlas: Feasibility-Aware Language Models for Electricity-Computing Co-Scheduling | 以可行性反馈训练 LLM 直接生成电力—计算联合排程，并提出 ECBench 与确定性评分。 | 方法 · 基准 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-538] · [![Code & Sample Data][badge-156]][resource-063] · [详情](#paper-jiang2026poweratlas) |
| 2026 · ICML 2026 | **ProOPF**<br>ProOPF: Benchmarking and Improving LLMs for Professional-Grade Power Systems Optimization Modeling | 构建专业最优潮流建模数据和基准，区分参数调整与结构扩展难度。 | 基准 · 数据 · 应用 | [![Publication][badge-053]][resource-180] · [![Paper 2][badge-074]][resource-181] · [![Paper 3][badge-075]][resource-182] · [![Evaluation Code & Data][badge-076]][resource-064] · [详情](#paper-shen2026proopf) |
| 2026 · arXiv preprint | **RAG for Optimization & CP Modeling**<br>Optimization and Constraint Modeling using LLMs with a Retrieval Augmented Generation Process | 从 Text2Zinc 种子和角色描述合成 500 个问题，以检索示例辅助 LLM 生成优化与约束模型代码。 | 方法 · 数据 | [![Paper][badge-049]][resource-183] · [详情](#paper-roy2026rag) |
| 2026 · NeurIPS 2026（已接收，待出版） | **ReLoop / RetailOpt-190**（探索性）<br>ReLoop: Structured Modeling and Behavioral Verification for Reliable LLM-Based Optimization | 结合结构化建模链与求解器参数扰动检查，定位静默错误并实施诊断引导修复。 | 方法 · 基准 · 数据 | [![Paper 1][badge-058]][resource-350] · [![Conference][badge-072]][resource-351] · [![Code][badge-022]][resource-352] · [![Dataset][badge-060]][resource-065] · [详情](#paper-lian2026reloop) |
| 2026 · arXiv preprint | **RetailBench**<br>RetailBench: Evaluating Long-Horizon Autonomous Decision-Making and Strategy Stability of LLM Agents in Realistic Retail Environments | 在单店超市仿真中评测定价、补货、供应商和现金流等长期连贯决策。 | 基准 · 数据 · 平台 | [![Paper][badge-049]][resource-553] · [![Code][badge-022]][resource-067] · [详情](#paper-zhang2026retailbench) |
| 2026 · ICML 2026 · PMLR 306 | **SAGE (Strategy-Aware Modeling)**<br>Strategy-Aware Optimization Modeling with Reasoning LLMs | 生成并筛选多策略建模示范，经 SFT 与 Segment-Weighted GRPO 兼顾公式正确性和求解效率。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-187] · [![Paper 2][badge-052]][resource-188] · [![Code][badge-022]][resource-189] · [![SAGE SFT 100K][badge-077]][resource-080] · [详情](#paper-strategyaware2026) |
| 2026 · arXiv preprint | **SDRL**<br>LLMs as Adaptive Meta-Solvers: Strategy-Diverse RL for Industrial-Scale Optimization | 用正确性门控的层次多样性奖励，训练模型在求解器、精确组合算法和启发式之间适配策略。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-190] · [![Benchmark Inference][badge-078]][resource-191] · [![SDRL Qwen3 4B][badge-079]][resource-010] · [详情](#paper-sdrl2026) |
| 2026 · arXiv preprint | **Smart Grids Agentic AI Tutorial**<br>LLMs and Agentic AI Systems for Smart Grids: A Tutorial on Architectures and Applications | 综述智能电网 Agent 架构，并以充电、潮流和故障诊断等案例演示可信工具与显式检查。 | 综述 · 应用 | [![Paper][badge-049]][resource-532] · [![Case-study Code][badge-155]][resource-533] · [详情](#paper-smartgrid2026) |
| 2026 · Findings of EMNLP 2026 | **SOVER / NLEquiv-150**<br>SOVER: Formal Certification of Optimization Reformulations via LLM-Assisted SMT Verification | 由 LLM 提取重构映射，再用 Z3 或 dReal 核验公式之间的可行性及目标关系。 | 方法 · 基准 · 数据 | [![Publication][badge-053]][resource-355] · [![Paper 2][badge-052]][resource-356] · [![Code][badge-022]][resource-068] · [![EquivaFormulation（使用）（相关）][badge-127]][resource-032] · [![NLP4LP（使用）（相关）][badge-128]][resource-051] · [详情](#paper-bhattacharyya2026sover) |
| 2026 · arXiv preprint | **Text2Model**<br>Text2Model: Modeling Copilots for Text-to-Model Translation | 提供面向 MiniZinc 的多种建模 Copilot、交互编辑器与在线排行榜。 | 方法 · 平台 | [![Paper][badge-049]][resource-196] · [![Code][badge-022]][resource-197] · [![Text2Zinc（复用）][badge-082]][resource-069] · [![Editor（相关）][badge-083]][resource-198] · [![Leaderboard（相关）][badge-084]][resource-199] · [![Python Package（相关）][badge-085]][resource-200] · [详情](#paper-text2model2026) |
| 2025 · arXiv preprint | **AIM-Bench**<br>AIM-Bench: Evaluating Decision-making Biases of Agentic LLM as Inventory Manager | 在不确定库存补货实验中检查 LLM Agent 的决策偏差与信息共享效果。 | 基准 · 数据 · 评测分析 | [![Paper][badge-049]][resource-544] · [详情](#paper-zhao2025aimbench) |
| 2025 · arXiv preprint | **ARS / RoutBench**（核心）<br>ARS: Automatic Routing Solver with Large Language Models | 根据问题描述生成约束感知的路由启发式，配套多变体 VRP 基准 RoutBench。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-456] · [![Code][badge-022]][resource-019] · [详情](#paper-li2025ars) |
| 2025 · arXiv preprint | **Ask, Clarify, Optimize**<br>Ask, Clarify, Optimize: Human-LLM Agent Collaboration for Smarter Inventory Control | 由 LLM 澄清库存需求并解释结果，把随机优化计算交给算法，以模拟经理测试交互。 | 方法 · 模型 · 应用 | [![Paper][badge-049]][resource-208] · [详情](#paper-askclarify2026) |
| 2025 · EvoApplications 2025 · LNCS | **Beyond the Hype: Bin Packing**<br>Beyond the Hype: Benchmarking LLM-Evolved Heuristics for Bin Packing | 跨广泛装箱实例与多种指标复评 LLM 演化启发式，并分析各算法优势所在的实例区域。 | 评测分析 · 数据 | [![Paper 1][badge-051]][resource-457] · [![Paper 2][badge-052]][resource-458] · [![Evaluation Data][badge-133]][resource-085] · [详情](#paper-sim2025beyondhype) |
| 2025 · GECCO 2025 Workshop / Companion | **BLADE**<br>BLADE: Benchmark suite for LLM-driven Automated Design and Evolution of iterative optimisation heuristics | 为 LLM 自动算法发现提供连续黑箱优化问题、实例生成、标准日志及行为分析工具。 | 基准 · 平台 | [![Paper 1][badge-051]][resource-459] · [![Paper 2][badge-052]][resource-460] · [![Code][badge-022]][resource-021] · [详情](#paper-vanstein2025blade) |
| 2025 · ACL 2025, Volume 1: Long Papers, pp. 821–838 | **BPP-Search / StructuredOR**<br>BPP-Search: Enhancing Tree of Thought Reasoning for Mathematical Modeling Problem Solving | 提出 BPP-Search，将束搜索、过程奖励模型和成对偏好机制结合到思维树推理中。 | 方法 · 基准 · 数据 | [![Paper][badge-057]][resource-212] · [![Code][badge-022]][resource-213] · [![Dataset][badge-060]][resource-022] · [详情](#paper-wang2025bppsearch) |
| 2025 · arXiv preprint | **CALM / STORM**<br>CALM Before the STORM: Unlocking Native Reasoning for Optimization Modeling | 用少量纠正提示修订推理轨迹，再经 SFT 与强化学习训练优化建模模型 STORM。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-216] · [详情](#paper-calm2025storm) |
| 2025 · arXiv preprint | **Component-Level Evaluation**<br>Peering Inside the Black Box: Uncovering LLM Errors in Optimization Modelling through Component-Level Evaluation | 按变量、约束、目标的覆盖和数值误差评价模型，补充最优值与运行时间指标。 | 方法 | [![Paper][badge-049]][resource-217] · [详情](#paper-peering2025) |
| 2025 · ECAI 2025 | **CP-Bench / DCP-Bench-Open**<br>CP-Bench: Evaluating Large Language Models for Constraint Modelling | 以多领域离散组合问题评测 LLM 约束建模，并在 DCP-Bench-Open 中持续扩展。 | 基准 · 数据 | [![Paper 1][badge-058]][resource-218] · [![Related version][badge-088]][resource-219] · [![Publication][badge-053]][resource-220] · [![Code（当前扩展版）][badge-089]][resource-027] · [![Dataset（原版归档）][badge-090]][resource-026] · [![CP-Bench 原版归档][badge-091]][resource-221] · [详情](#paper-michailidis2025cpbench) |
| 2025 · arXiv preprint | **DAOpt / OptU**<br>DAOpt: Modeling and Evaluation of Data-Driven Optimization under Uncertainty with LLMs | 结合不确定性建模、多 Agent 与仿真环境，评估样本外可行性和稳健性。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-222] · [详情](#paper-daopt2025) |
| 2025 · arXiv preprint | **DPLM / DP-Bench**<br>Auto-Formulating Dynamic Programming Problems with Large Language Models | 提出 DP-Bench，并用双向反思合成训练数据，训练从自然语言构造动态规划模型的 DPLM。 | 方法 · 基准 · 数据 · 模型 | [![Paper][badge-049]][resource-225] · [详情](#paper-dpdlm2025) |
| 2025 · ICLR 2025 | **DRoC**<br>DRoC: Elevating Large Language Models for Complex Vehicle Routing via Decomposed Retrieval of Constraints | 分解复杂 VRP 的约束并分别检索文档，动态选择 RAG 或自调试生成求解器程序。 | 方法 · 数据 · 应用 | [![Publication][badge-053]][resource-226] · [![Paper 2][badge-074]][resource-227] · [![Code][badge-022]][resource-088] · [详情](#paper-jiang2025droc) |
| 2025 · IEEE PESGM 2025 | **ElecBench**（探索性）<br>ElecBench: a Power Grid Dispatch Evaluation Benchmark for Large Language Models | 以电力知识、监控、调度和黑启动文本任务评价事实性、逻辑性及稳定性等维度。 | 基准 · 数据 | [![Paper 1][badge-051]][resource-554] · [![Paper 2][badge-052]][resource-555] · [![Public Test Subset][badge-158]][resource-030] · [详情](#paper-zhou2024elecbench) |
| 2025 · ICLR 2025 | **EOR / Decision Information**<br>Decision Information Meets Large Language Models: The Future of Explainable Operations Research | 用 what-if 决策信息与二部图比较模型变化，生成可操作的优化解释。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-228] · [![Paper 2][badge-052]][resource-229] · [![Code][badge-022]][resource-031] · [详情](#paper-zhang2025decisioninfo) |
| 2025 · ICML 2025 | **EquivaMap**（核心）<br>EquivaMap: Leveraging LLMs for Automatic Equivalence Checking of Optimization Formulations | 用 LLM 寻找决策变量映射来检查 Quasi-Karp 等价，并构建 EquivaFormulation。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-230] · [![arXiv][badge-087]][resource-231] · [![Code][badge-022]][resource-232] · [![Dataset][badge-060]][resource-032] · [详情](#paper-zhai2025equivamap) |
| 2025 · AAAI 2025 | **HSEvo**<br>HSEvo: Elevating Automatic Heuristic Design with Diversity-Driven Harmony Search and Genetic Algorithm Using LLMs | 以多样性指标分析启发式演化，并将和声搜索与遗传搜索结合改善探索。 | 方法 · 评测分析 | [![Paper 1][badge-051]][resource-471] · [![Paper 2][badge-052]][resource-472] · [![Code][badge-022]][resource-473] · [详情](#paper-dat2024hsevo) |
| 2025 · arXiv preprint | **LLM Algorithm-search Fitness Landscapes**<br>Fitness Landscape of Large Language Model-Assisted Automated Algorithm Search | 以算法为节点、LLM 转换为边构造图景，跨任务和模型研究搜索崎岖性及相似性。 | 评测分析 | [![Paper][badge-049]][resource-480] · [详情](#paper-liu2025fitness) |
| 2025 · arXiv preprint | **LLM Heuristic Behaviour-space Analysis**<br>Behaviour Space Analysis of LLM-driven Meta-heuristic Discovery | 比较 LLaMEA 的提示变体，在 BBOB 上记录探索、利用、收敛和停滞等行为指标。 | 评测分析 | [![Paper][badge-049]][resource-481] · [![Behaviour Metrics Code][badge-146]][resource-482] · [详情](#paper-vanstein2025behaviour) |
| 2025 · IJCAI 2025 Survey Track | **LLM4OR Survey**（核心）<br>A Survey of Optimization Modeling Meets LLMs: Progress and Future Directions | 综述优化建模全流程，分析并标记基准错误，提供清洗数据与评测门户。 | 综述 · 数据 | [![Paper][badge-049]][resource-237] · [![官方资源库（相关）][badge-094]][resource-238] · [![Cleaned Benchmarks][badge-095]][resource-092] · [详情](#paper-xiao2025survey) |
| 2025 · NeurIPS 2025 | **LLMCoSolver / E2E CO Solver**<br>Large Language Models as End-to-end Combinatorial Optimization Solvers | 经 SFT 与可行性／最优性感知的 FOARL，训练 LLM 从问题描述直接输出组合优化解。 | 方法 · 模型 · 数据 | [![Paper 1][badge-051]][resource-539] · [![Paper 2][badge-052]][resource-540] · [![Code][badge-022]][resource-541] · [![SFT Data][badge-030]][resource-074] · [![RL Data][badge-031]][resource-075] · [详情](#paper-jiang2025e2eco) |
| 2025 · arXiv preprint | **LLMs for Stochastic Modeling**<br>Large Language Model-Based Automatic Formulation for Stochastic Optimization Models | 以结构化提示生成机会约束与两阶段随机规划，并用软评分检查模型结构。 | 方法 | [![Paper][badge-049]][resource-242] · [![Code][badge-022]][resource-093] · [详情](#paper-talebi2025stochastic) |
| 2025 · EMNLP 2025 Main, pp. 19286–19304 | **MA-GTS / G-REAL**<br>MA-GTS: A Multi-Agent Framework for Solving Complex Graph Problems in Real-World Applications | 从隐式文本图信息恢复结构化图，并用多 Agent 根据问题约束及规模选择算法。 | 方法 · 基准 · 数据 | [![Paper 1][badge-058]][resource-487] · [![Paper 2][badge-074]][resource-488] · [![Code][badge-022]][resource-039] · [详情](#paper-yuan2025magts) |
| 2025 · Findings NAACL 2025 | **Mamo**（核心）<br>LLMs for Mathematical Modeling: Towards Bridging the Gap between Natural and Mathematical Languages | 提出 Mamo，以求解器辅助的过程评估研究语言到数学建模，涵盖 LP、MILP 与 ODE。 | 基准 · 数据 | [![Paper 1][badge-058]][resource-244] · [![Paper 2][badge-074]][resource-245] · [![Code][badge-022]][resource-040] · [![Dataset（第三方镜像）][badge-096]][resource-041] · [详情](#paper-huang2024mamo) |
| 2025 · ICLR 2025 | **MILP-Evolve**（核心）<br>Towards Foundation Models for Mixed Integer Linear Programming | 用 LLM 演化生成多样 MILP 类与实例，支持间隙预测、学习分支和语言对齐。 | 方法 · 数据 | [![Paper 1][badge-051]][resource-495] · [![arXiv][badge-087]][resource-496] · [![Code][badge-022]][resource-497] · [![Dataset][badge-060]][resource-076] · [![GitHub Data][badge-012]][resource-498] · [详情](#paper-li2025milpevolve) |
| 2025 · NeurIPS 2025 | **MM-Agent / MM-Bench（数学建模）**（探索性）<br>MM-Agent: LLM as Agents for Real-world Mathematical Modeling Problem | 将数学建模拆为问题分析、模型构造、计算求解和报告生成，并提供 MCM/ICM 来源的 MM-Bench。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-246] · [![Paper 2][badge-052]][resource-247] · [![Paper 3][badge-097]][resource-248] · [![Code & MM-Bench][badge-098]][resource-043] · [![Expert Skills (2026 add-on)][badge-099]][resource-101] · [![HF Demo（相关）][badge-100]][resource-249] · [详情](#paper-liu2025mmagent) |
| 2025 · Findings of EMNLP 2025 | **ModelingAgent / ModelingBench**（探索性）<br>ModelingAgent: Bridging LLMs and Mathematical Modeling for Real-World Challenges | 用多 Agent 协调工具和迭代修订处理开放式建模，并以 ModelingBench 与 ModelingJudge 评估报告。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-250] · [![Paper 2][badge-052]][resource-251] · [![Code & ModelingBench][badge-101]][resource-044] · [详情](#paper-qian2025modelingagent) |
| 2025 · arXiv preprint | **MOID**<br>Multi-Objective Infeasibility Diagnosis for Routing Problems Using Large Language Models | 联合路径成本与约束违反量做多目标优化，再由 LLM 分析一组可恢复可行性的调整建议。 | 方法 · 数据 · 应用 | [![Paper][badge-049]][resource-252] · [![Diagnosis Data][badge-102]][resource-095] · [详情](#paper-moid2025) |
| 2025 · arXiv preprint | **OptiTrust**<br>Toward a Trustworthy Optimization Modeling Agent via Verifiable Synthetic Data Generation | 从带已知最优解的符号问题合成示范，用跨建模语言投票和分步推理训练建模 Agent。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-260] · [详情](#paper-lima2025optitrust) |
| 2025 · ICML 2025; PMLR 267:40769–40802 | **OptMATH**（核心）<br>OptMATH: A Scalable Bidirectional Data Synthesis Framework for Optimization Modeling | 通过数学模型到问题数据再到自然语言的双向合成流程生成优化建模数据，并用正向建模和拒绝采样筛选。 | 方法 · 基准 · 数据 · 模型 | [![Paper][badge-057]][resource-261] · [![Code][badge-022]][resource-054] · [![Model 7B][badge-003]][resource-006] · [![Model 32B][badge-004]][resource-007] · [![Dataset][badge-060]][resource-078] · [详情](#paper-lu2025optmath) |
| 2025 · arXiv preprint | **OR-LLM-Agent / BWOR**<br>OR-LLM-Agent: Automating Modeling and Solving of Operations Research Optimization Problems with Reasoning LLM | 将建模、代码生成与调试分配给推理 Agent，并提出 BWOR 评测集。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-262] · [![Code][badge-022]][resource-263] · [![Dataset][badge-060]][resource-055] · [详情](#paper-zhang2025bwor) |
| 2025 · arXiv；相关 ICML 2026 Workshop 版本 | **ORGEval / Bench4Opt**（核心）<br>ORGEval: Graph-Theoretic Evaluation of LLMs in Optimization Modeling | 将优化形式化表示为图，通过图同构及对称可分解条件下的 WL 测试评价结构等价性。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-264] · [![ICML workshop poster（相关）][badge-103]][resource-265] · [详情](#paper-ding2026orgeval) |
| 2025 · Operations Research 73(6):2986–3009 | **ORLM**（核心）<br>ORLM: A Customizable Framework in Training Large Models for Automated Optimization Modeling | 通过 OR-Instruct 合成数据训练优化领域模型，并提出工业基准 IndustryOR。 | 方法 · 基准 · 数据 · 模型 | [![Paper 1][badge-058]][resource-266] · [![Journal][badge-104]][resource-267] · [![Code][badge-022]][resource-268] · [![Model][badge-073]][resource-008] · [![IndustryOR][badge-024]][resource-059] · [![OR-Instruct-3K][badge-032]][resource-079] · [详情](#paper-huang2025orlm) |
| 2025 · AAAI 2025 | **ORQA**<br>Evaluating LLM Reasoning in the Operations Research Domain with ORQA | 以 OR 专家设计的问题检验模型对建模知识和多步推理的掌握。 | 基准 · 数据 | [![Proceedings][badge-105]][resource-272] · [![Paper 2][badge-052]][resource-273] · [![Code][badge-022]][resource-061] · [详情](#paper-mostajabdaveh2025orqa) |
| 2025 · arXiv preprint | **Re-evaluating Heuristic Search: 3D Packing**<br>Re-evaluating LLM-based Heuristic Search: A Case Study on the 3D Packing Problem | 以约束脚手架和自修复支持 3D 装箱程序生成，分析搜索偏向评分函数及紧约束下的局限。 | 评测分析 | [![Paper][badge-049]][resource-363] · [![Study Code][badge-131]][resource-364] · [详情](#paper-quan2025reeval3d) |
| 2025 · ICLR 2025 | **ReSocratic / OptiBench**（核心）<br>OptiBench Meets ReSocratic: Measure and Improve LLMs for Optimization Modeling | 先合成数学形式与求解示范再逆向生成问题，配套 OptiBench 与 ReSocratic-29k。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-274] · [![arXiv][badge-087]][resource-275] · [![Code][badge-022]][resource-066] · [详情](#paper-yang2025resocratic) |
| 2025 · NeurIPS 2025 | **SIRL**（核心）<br>Solver-Informed RL: Grounding Large Language Models for Authentic Optimization Modeling | 用求解器检查代码及 LP 实例，构造 RL 可验证奖励，并发布模型与修订评测数据。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-276] · [![arXiv][badge-087]][resource-277] · [![Code][badge-022]][resource-278] · [![Model Gurobi-7B][badge-005]][resource-011] · [![Model COPT-7B][badge-006]][resource-012] · [![Model Gurobi-32B][badge-007]][resource-013] · [![Model COPT-32B][badge-008]][resource-014] · [![修订评测集][badge-045]][resource-099] · [详情](#paper-chen2025sirl) |
| 2025 · arXiv preprint | **Starjob**<br>Starjob: Dataset for LLM-Driven Job Shop Scheduling | 发布作业车间调度训练数据，用 LoRA 微调 LLM 直接输出调度解。 | 方法 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-542] · [![Code][badge-022]][resource-543] · [![Dataset][badge-060]][resource-081] · [详情](#paper-abgaryan2025starjob) |
| 2025 · Findings of EMNLP 2025 | **Step-Opt**<br>Training LLMs for Optimization Modeling via Iterative Data Synthesis and Structured Validation | 逐步提高合成问题复杂度并结构化校验训练数据，再微调优化建模模型。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-281] · [![Paper 2][badge-052]][resource-282] · [![Code][badge-022]][resource-082] · [详情](#paper-wu2025stepopt) |
| 2025 · arXiv preprint | **Teaching LLMs to Think Mathematically**<br>Teaching LLMs to Think Mathematically: A Critical Study of Decision-Making via Optimization | 结合系统综述与元分析，在新构造的计算机网络优化题中比较三种提示策略。 | 综述 · 评测分析 · 数据 | [![Paper][badge-049]][resource-283] · [详情](#paper-abedi2025thinkmath) |
| 2025 · arXiv preprint | **Text2Zinc**<br>Text2Zinc: A Cross-Domain Dataset for Modeling Optimization and Satisfaction Problems in MiniZinc | 用 MiniZinc 统一表示自然语言描述的约束满足与优化问题。 | 基准 · 数据 | [![Paper][badge-049]][resource-284] · [![Dataset][badge-060]][resource-069] · [![作者项目门户（相关）][badge-106]][resource-234] · [详情](#paper-singirikonda2025text2zinc) |
| 2025 · arXiv preprint | **Visual Graph Optimization with MLLMs**（探索性）<br>Bridging Visualization and Optimization: Multimodal Large Language Models on Graph-Structured Combinatorial Optimization | 把图结构呈现为图像，结合多模态 LLM 与简单搜索处理影响最大化、网络拆解和图任务。 | 方法 · 评测分析 | [![Paper][badge-049]][resource-556] · [详情](#paper-bridgingviz2025) |
| 2025 · Preprint · ICLR 2025 关联未确认 | **WIQOR**<br>WIQOR: A dataset for what-if analysis of Operations Research problems | 评测根据自然语言 what-if 请求修改既有数学规划模型的能力。 | 基准 · 数据 | [![Paper PDF][badge-107]][resource-286] · [![Institution record][badge-108]][resource-287] · [详情](#paper-parashar2025wiqor) |
| 2024 · ICLR 2024 | **Chain-of-Experts**（核心）<br>Chain-of-Experts: When LLMs Meet Complex Operations Research Problems | 为不同 Agent 配置 OR 专长，由 conductor 组织前向思维构造与反向反思，完成复杂建模和编程。 | 方法 · 基准 · 数据 | [![Paper][badge-057]][resource-290] · [![Code][badge-022]][resource-023] · [详情](#paper-xiao2024coe) |
| 2024 · LREC-COLING 2024 | **Human-aligned LPWP Evaluation**<br>Towards Human-aligned Evaluation for Linear Programming Word Problems | 以图编辑距离比较线性规划模型，并以人工评分研究评价指标与人类判断的一致性。 | 方法 · 评测分析 | [![Paper][badge-057]][resource-292] · [详情](#paper-xing2024lpwp) |
| 2024 · INFOR 62（2024） | **LM4OPT**<br>LM4OPT: Unveiling the potential of Large Language Models in formulating mathematical optimization problems | 先适配数学语料再微调 LP 建模任务，以带噪嵌入训练小模型，并比较零样本与单样本提示。 | 方法 · 模型 · 评测分析 | [![Paper 1][badge-051]][resource-296] · [![Paper 2][badge-052]][resource-297] · [详情](#paper-ahmed2024lm4opt) |
| 2024 · INFOR 62(4):599–617 | **Multi-Stage Modeling & Verification**<br>Optimization modeling and verification from problem specifications using a multi-agent multi-stage LLM framework | 分阶段从问题规格生成数学模型与 Zimpl 代码，并由多个 LLM Agent 交叉检查。 | 方法 · 基准 · 数据 | [![Paper][badge-057]][resource-298] · [详情](#paper-mostajabdaveh2024multiagent) |
| 2024 · ICML 2024 | **OptiMUS**（核心）<br>OptiMUS: Scalable Optimization Modeling with (MI)LP Solvers and Large Language Models | 用模块化 Agent 完成 MILP 建模、代码生成、调试与评估，同时发布 NLP4LP。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-302] · [![arXiv][badge-087]][resource-303] · [![Code][badge-022]][resource-304] · [![Dataset][badge-060]][resource-051] · [详情](#paper-teshnizi2024optimus) |
| 2024 · NAACL 2024 Industry Track | **OptLLM**<br>Solving General Natural-Language-Description Optimization Problems with Large Language Models | 通过多轮澄清、公式与代码转换、外部求解器和结果解释支持自然语言优化，并微调 Qwen。 | 方法 · 数据 · 模型 | [![Paper 1][badge-051]][resource-305] · [![Paper 2][badge-052]][resource-306] · [![MindOpt Trial (International)（相关）][badge-112]][resource-307] · [![MindOpt Trial (CN)（相关）][badge-113]][resource-308] · [详情](#paper-zhang2024optllm) |
| 2023 · arXiv preprint | **AI-Copilot for Business Optimisation**<br>Language Models for Business Optimisation with a Real World Case Study in Production Scheduling | 微调成本较低的 LLM 生成优化公式，并在真实生产排程案例中评估。 | 方法 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-312] · [![Training Data][badge-114]][resource-070] · [![Generated Formulations（相关）][badge-115]][resource-313] · [![Industrial Case Data][badge-116]][resource-071] · [![Industrial Outputs（相关）][badge-117]][resource-314] · [![LPWP Evaluation Data（相关）][badge-118]][resource-315] · [详情](#paper-alahakoon2023copilot) |
| 2023 · arXiv preprint | **Multi-stage MILP Synthesis**<br>Synthesizing mixed-integer linear programming models from natural language descriptions | 以变量识别、约束／目标分类和模板构建合成 MILP，并扩展 NL4Opt 的逻辑约束与二元变量问题。 | 方法 · 数据 | [![Paper][badge-049]][resource-318] · [![Modeling Data][badge-119]][resource-077] · [详情](#paper-li2023synthesizing) |
| 2023 · NeurIPS 2022 Competition Track / PMLR 220 | **NL4Opt**（核心）<br>NL4Opt Competition: Formulating Optimization Problems Based on Their Natural Language Descriptions | 将自然语言优化任务分为实体识别与中间形式生成，提供 LP 文字题与竞赛评测。 | 基准 · 数据 · 基础 | [![Paper 1][badge-051]][resource-319] · [![arXiv][badge-087]][resource-320] · [![Code][badge-022]][resource-020] · [详情](#paper-ramamonjison2023nl4opt) |
| 2022 · EMNLP 2022 Industry | **Auto-formulation (2022)**（核心）<br>Augmenting Operations Research with Auto-Formulation of Optimization Models From Problem Descriptions | 以受控生成从问题描述建议优化模型，并通过交互界面供用户校验与修改。 | 方法 · 基准 · 数据 · 基础 | [![Paper][badge-057]][resource-326] · [![Code & Data（NL4Opt）][badge-121]][resource-020] · [详情](#paper-ramamonjison2022augmenting) |

[返回目录](#contents)

<a id="applications"></a>

## 运筹优化应用

供应链、库存、路径规划、调度、生产与其他优化场景。

### 调度与生产

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · arXiv preprint | **DScheLLM**<br>DScheLLM: Enabling Dynamic Scheduling through a Fine-Tuned Dual-System Large language Model | 用求解器排程合成快／慢思考示范，LoRA 微调双系统 LLM 应对动态扰动。 | 方法 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-337] · [详情](#paper-zhang2026dschellm) |
| 2026 · arXiv preprint | **DSevolve**<br>DSevolve: Enabling Real-Time Adaptive Scheduling on Dynamic Flexible Job Shop with LLM-Evolved Heuristic Portfolios | 离线演化互补排程规则库，再用状态条件神经选择器在线响应柔性车间扰动。 | 方法 · 应用 | [![Paper][badge-049]][resource-392] · [详情](#paper-dsevolve2026) |
| 2026 · ICML 2026 · PMLR 306 | **DynaSchedBench**<br>DynaSchedBench: Calibrated Dynamic Scheduling Benchmarks and Observability Paradox in LLM-based Scheduling Agents | 校准动态柔性车间实例难度，统一仿真、轨迹评测和不同观测条件下的 Agent 比较。 | 方法 · 基准 · 数据 · 应用 | [![Paper 1][badge-051]][resource-546] · [![Paper 2][badge-052]][resource-547] · [![Code][badge-022]][resource-029] · [![Project（相关）][badge-135]][resource-548] · [详情](#paper-dynaschedbench2026) |
| 2026 · arXiv preprint | **Interactive Optimization Conversations**<br>Let's Have a Conversation: Designing and Evaluating LLM Agents for Interactive Optimization | 用带内部效用函数的决策 Agent 扮演利益相关者，评测多轮交互优化而非只看单次答案。 | 方法 · 数据 · 应用 | [![Paper][badge-049]][resource-133] · [![Code][badge-022]][resource-090] · [详情](#paper-conversation2026) |
| 2026 · arXiv preprint | **PowerAtlas / ECBench**<br>PowerAtlas: Feasibility-Aware Language Models for Electricity-Computing Co-Scheduling | 以可行性反馈训练 LLM 直接生成电力—计算联合排程，并提出 ECBench 与确定性评分。 | 方法 · 基准 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-538] · [![Code & Sample Data][badge-156]][resource-063] · [详情](#paper-jiang2026poweratlas) |
| 2026 · International Journal of Production Research（2026 在线） | **SMILO**<br>An LLM-powered MILP modelling engine for workforce scheduling guided by expert knowledge | 结合专家建模图、LLM 信息抽取与模板生成劳动力排班 MILP。 | 方法 · 应用 | [![Paper 1][badge-051]][resource-192] · [![Paper 2][badge-052]][resource-193] · [详情](#paper-li2025smilo) |
| 2025 · arXiv preprint | **ALAS**<br>ALAS: A Stateful Multi-LLM Agent Framework for Disruption-Aware Planning | 用角色化 Agent、持久状态与历史感知的局部补偿，处理调度计划中的运行扰动。 | 方法 · 应用 | [![Paper][badge-049]][resource-534] · [详情](#paper-alas2025) |
| 2025 · arXiv preprint | **LLM-discovered EDDC / MDDC**<br>Discovering Heuristics with Large Language Models (LLMs) for Mixed-Integer Programs: Single-Machine Scheduling | 用 LLM 与进化流程发现单机总拖期启发式 EDDC 和 MDDC，按解质量与时间比较经典规则。 | 方法 · 应用 | [![Paper][badge-049]][resource-483] · [![Code][badge-022]][resource-484] · [详情](#paper-cetinkaya2025mipsmtt) |
| 2025 · Proceedings of the Design Society 5 · ICED25（2025） | **LLMs for DSM Sequencing**<br>Large language models for combinatorial optimization of design structure matrix | 把网络拓扑和领域知识共同提供给 LLM，迭代搜索设计结构矩阵的排序方案。 | 方法 · 应用 | [![Paper 1][badge-051]][resource-557] · [![Paper 2][badge-052]][resource-558] · [详情](#paper-dsmco2024) |
| 2025 · arXiv（2026 修订） | **ReflecSched**（探索性）<br>ReflecSched: Solving Dynamic Flexible Job-Shop Scheduling via LLM-Powered Hierarchical Reflection | 从多规划时域的启发式仿真中提炼战略经验，指导动态柔性作业车间调度决策。 | 方法 · 应用 | [![Paper][badge-049]][resource-535] · [详情](#paper-cao2025reflecsched) |
| 2025 · arXiv preprint | **Starjob**<br>Starjob: Dataset for LLM-Driven Job Shop Scheduling | 发布作业车间调度训练数据，用 LoRA 微调 LLM 直接输出调度解。 | 方法 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-542] · [![Code][badge-022]][resource-543] · [![Dataset][badge-060]][resource-081] · [详情](#paper-abgaryan2025starjob) |
| 2024 · arXiv preprint | **RAGDyS**<br>Automated Conversion of Static to Dynamic Scheduler via Natural Language | 从既有静态排程模型出发，用检索增强生成按自然语言约束实施动态排程修改。 | 方法 · 应用 | [![Paper][badge-049]][resource-309] · [详情](#paper-tang2024ragdys) |
| 2023 · arXiv preprint | **AI-Copilot for Business Optimisation**<br>Language Models for Business Optimisation with a Real World Case Study in Production Scheduling | 微调成本较低的 LLM 生成优化公式，并在真实生产排程案例中评估。 | 方法 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-312] · [![Training Data][badge-114]][resource-070] · [![Generated Formulations（相关）][badge-115]][resource-313] · [![Industrial Case Data][badge-116]][resource-071] · [![Industrial Outputs（相关）][badge-117]][resource-314] · [![LPWP Evaluation Data（相关）][badge-118]][resource-315] · [详情](#paper-alahakoon2023copilot) |

### 路由与物流

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · ICLR 2026 | **AFL**<br>An Agentic Framework with LLMs for Solving Complex Vehicle Routing Problems | 由四个专门 Agent 从原始 VRP 输入自主生成并协调修正求解程序。 | 方法 · 应用 | [![Publication][badge-053]][resource-330] · [![Paper 2][badge-074]][resource-331] · [![Paper 3][badge-075]][resource-332] · [![Code][badge-022]][resource-333] · [详情](#paper-zhang2026afl) |
| 2026 · arXiv preprint | **AILS-AHD**<br>Enhancing CVRP Solver through LLM-driven Automatic Heuristic Design | 在自适应迭代局部搜索中演化 ruin 启发式，并结合 LLM 辅助加速改善 CVRP 求解。 | 方法 · 应用 | [![Paper][badge-049]][resource-372] · [详情](#paper-xie2026ailsahd) |
| 2026 · Findings of EMNLP 2026 | **Constraint Injection / VRPCoder**<br>Beyond Objective Equivalence: Constraint Injection for LLM-Based Optimization Modeling on Vehicle Routing Problems | 用可行解和单约束违反解测试 VRP 代码，补充最优值相同仍可能漏约束的检查。 | 方法 · 基准 · 数据 · 模型 · 应用 | [![Publication][badge-053]][resource-335] · [![Paper 2][badge-052]][resource-336] · [![Benchmark Data][badge-122]][resource-025] · [详情](#paper-constraintinjection2026) |
| 2026 · Artificial Intelligence for Transportation 6（2026） | **ORThought / LogiOR**<br>ORThought: Benchmarking and automating logistics optimization modeling via structured LLM reasoning | 以专家建模原则指导结构化双 Agent 推理，并发布物流建模基准 LogiOR。 | 方法 · 基准 · 数据 | [![Publication][badge-053]][resource-174] · [![Paper 2][badge-052]][resource-175] · [![Code][badge-022]][resource-176] · [![Dataset][badge-060]][resource-062] · [详情](#paper-yang2025orthought) |
| 2026 · AAMAS 2026 | **PyVRP+ / MEP**<br>PyVRP+: LLM-Driven Metacognitive Heuristic Evolution for Hybrid Genetic Search in Vehicle Routing Problems | 通过 Reason–Act–Reflect 诊断和设计假设，演化 HGS 中的路由启发式组件。 | 方法 · 应用 | [![Paper 1][badge-051]][resource-441] · [![Paper 2][badge-052]][resource-442] · [![Proceedings][badge-105]][resource-443] · [详情](#paper-pyvrpplus2026) |
| 2026 · arXiv preprint | **RLEA**<br>Reinforcement Learning Enhanced LLM Agents for Complex Vehicle Routing Problems | 以 Soft Q-learning 训练轻量 Planner 调度 LLM Agent，结合记忆与检索完成复杂 VRP 建模。 | 方法 · 应用 | [![Paper][badge-049]][resource-353] · [![Appendix（相关）][badge-126]][resource-354] · [详情](#paper-rlvrpagents2026) |
| 2026 · arXiv preprint | **SpecAHD**<br>SpecAHD: Localize to Specialize for Automated Heuristic Design in Large-Scale Routing Problems | 以双层搜索共同选择局部修复区域，并演化适配区域差异的互补启发式库。 | 方法 · 应用 | [![Paper][badge-049]][resource-447] · [详情](#paper-lai2026specahd) |
| 2026 · arXiv preprint | **SPO**<br>SPO: Discovering Adaptive Large Neighborhood Search Operators via Stackelberg Program Optimization | 按 Stackelberg 主从关系发现状态依赖的 destroy / repair 程序，并共同更新程序种群与生成器。 | 方法 · 模型 · 应用 | [![Paper][badge-049]][resource-448] · [详情](#paper-spo2026) |
| 2026 · Transactions on Machine Learning Research（2026） | **VRPAgent**<br>VRPAgent: LLM-Driven Discovery of Heuristic Operators for Vehicle Routing Problems | 将 LLM 生成的路由算子嵌入共享 LNS 框架，以带代码长度惩罚的遗传搜索改进候选。 | 方法 · 应用 | [![Paper 1][badge-051]][resource-450] · [![Paper 2][badge-052]][resource-451] · [![Generated Operators（相关）][badge-141]][resource-452] · [详情](#paper-vrpagent2025) |
| 2025 · arXiv preprint | **ARS / RoutBench**（核心）<br>ARS: Automatic Routing Solver with Large Language Models | 根据问题描述生成约束感知的路由启发式，配套多变体 VRP 基准 RoutBench。 | 方法 · 基准 · 数据 | [![Paper][badge-049]][resource-456] · [![Code][badge-022]][resource-019] · [详情](#paper-li2025ars) |
| 2025 · ICLR 2025 | **DRoC**<br>DRoC: Elevating Large Language Models for Complex Vehicle Routing via Decomposed Retrieval of Constraints | 分解复杂 VRP 的约束并分别检索文档，动态选择 RAG 或自调试生成求解器程序。 | 方法 · 数据 · 应用 | [![Publication][badge-053]][resource-226] · [![Paper 2][badge-074]][resource-227] · [![Code][badge-022]][resource-088] · [详情](#paper-jiang2025droc) |
| 2025 · arXiv preprint | **InstSpecHH**<br>LLM-Driven Instance-Specific Heuristic Generation and Selection | 按实例特征划分子类，离线演化专门启发式，并通过 LLM 或轻量分类器选择适用算法。 | 方法 | [![Paper][badge-049]][resource-474] · [详情](#paper-zhang2025instspechh) |
| 2025 · EMNLP 2025 Main, pp. 19286–19304 | **MA-GTS / G-REAL**<br>MA-GTS: A Multi-Agent Framework for Solving Complex Graph Problems in Real-World Applications | 从隐式文本图信息恢复结构化图，并用多 Agent 根据问题约束及规模选择算法。 | 方法 · 基准 · 数据 | [![Paper 1][badge-058]][resource-487] · [![Paper 2][badge-074]][resource-488] · [![Code][badge-022]][resource-039] · [详情](#paper-yuan2025magts) |
| 2025 · arXiv preprint | **MOID**<br>Multi-Objective Infeasibility Diagnosis for Routing Problems Using Large Language Models | 联合路径成本与约束违反量做多目标优化，再由 LLM 分析一组可恢复可行性的调整建议。 | 方法 · 数据 · 应用 | [![Paper][badge-049]][resource-252] · [![Diagnosis Data][badge-102]][resource-095] · [详情](#paper-moid2025) |
| 2025 · ICLR 2025 Agentic AI Workshop | **NCO-LLM for VRP**<br>Large Language Models powered Neural Solvers for Generalized Vehicle Routing Problems | 演化 LLM 生成的结构偏置并注入注意力分数，再微调 LEHD / POMO 神经路由策略。 | 方法 · 模型 · 应用 | [![Paper][badge-057]][resource-499] · [![Code][badge-022]][resource-500] · [详情](#paper-tran2025llmneural) |
| 2025 · arXiv preprint | **PAIR**<br>PAIR: A Novel Large Language Model-Guided Selection Strategy for Evolutionary Algorithms | 通过适应度、多样性与交叉兼容性提示 LLM 选择进化算法中的配对个体，并在 TSP 上评测。 | 方法 | [![Paper][badge-049]][resource-501] · [![Code][badge-022]][resource-502] · [详情](#paper-ali2025pair) |
| 2024 · arXiv preprint | **City-LEO**<br>City-LEO: Toward Transparent City Management Using LLM with End-to-End Optimization | 通过对话限定优化范围，并结合预测与优化管理共享电动自行车运营。 | 方法 · 应用 | [![Paper][badge-049]][resource-291] · [![Data & Code][badge-109]][resource-086] · [详情](#paper-jiao2024cityleo) |
| 2024 · EMNLP 2024 Industry Track | **ITINERA**<br>ItiNera: Integrating Spatial Optimization with Large Language Models for Open-domain Urban Itinerary Planning | 分解城市漫步需求、选择兴趣点，并用聚类感知的空间优化排序与生成个性化行程。 | 方法 · 应用 | [![Paper 1][badge-051]][resource-293] · [![Paper 2][badge-052]][resource-294] · [![Code][badge-022]][resource-295] · [详情](#paper-tang2024itinerary) |
| 2024 · EMNLP 2024 System Demonstrations | **To the Globe / TTG**<br>To the Globe (TTG): Towards Language-Driven Guaranteed Travel Planning | 将旅行需求译为符号表示，再由 MILP 求解器生成满足已编码约束的行程。 | 方法 · 应用 · 模型 | [![Paper 1][badge-051]][resource-310] · [![Paper 2][badge-052]][resource-311] · [详情](#paper-ju2024ttg) |

### 库存、零售与供应链

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · arXiv preprint | **Automated Inventory Policy Design**<br>Automated Design of Inventory Policy with Large Language Models: An Exploratory Study | 让 LLM 迭代生成库存策略函数类，再由外部优化器在类内调参并反馈成本。 | 方法 · 应用 | [![Paper][badge-049]][resource-373] · [详情](#paper-invpolicy2026) |
| 2026 · arXiv preprint | **GenAI Beer Game Reliability**<br>Reliability and Effectiveness of Autonomous AI Agents in Supply Chain Management | 在多级 Beer Game 中研究 Agent 决策波动，并比较强化学习后训练与运营护栏的可靠性。 | 方法 · 评测分析 · 应用 | [![Paper][badge-049]][resource-525] · [详情](#paper-beergame2026) |
| 2026 · arXiv preprint | **InventoryBench**<br>AI Agents for Inventory Control: Human-LLM-OR Complementarity | 构建库存决策基准，并结合人类实验研究 OR、LLM 和人工决策的互补性。 | 方法 · 基准 · 数据 · 应用 | [![Paper][badge-049]][resource-526] · [![InventoryBench][badge-152]][resource-036] · [![人机实验平台][badge-153]][resource-527] · [详情](#paper-invbench2026) |
| 2026 · arXiv preprint | **InvEvolve**（探索性）<br>InvEvolve: Evolving White-Box Inventory Policies via Large Language Models with Performance Guarantees | 用 LLM 演化白盒库存策略，并以置信区间认证框架研究部署安全与性能改进。 | 方法 · 应用 | [![Paper][badge-049]][resource-410] · [详情](#paper-invevolve2026) |
| 2026 · arXiv preprint | **LLM-MAS for Service Operations**<br>Optimizing Service Operations via LLM-Powered Multi-Agent Simulation | 用交互 LLM 模拟参与者响应，并以轨迹上的梯度估计和方差缩减优化服务设计。 | 方法 · 应用 | [![Paper][badge-049]][resource-528] · [详情](#paper-wang2026llmmas) |
| 2026 · arXiv preprint | **Multi-Warehouse Formulation Selection**<br>Large Language Model for Operations Research Formulation Selection in Multi-Warehouse Inventory Allocation | 在多仓库存分配中选择适合实例的 MIP 公式专家，并用求解质量反馈训练选择器。 | 方法 · 模型 · 应用 | [![Paper][badge-049]][resource-147] · [详情](#paper-warehouseformsel2026) |
| 2026 · arXiv preprint | **OptiRepair**（探索性）<br>OptiRepair: Closed-Loop Diagnosis and Repair of Supply Chain Optimization Models with LLM Agents | 以 IIS 与运营合理性检查构建两阶段供应链修复闭环，提出 OptiRepair-SC 并训练 P1 / P2 模型。 | 方法 · 基准 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-347] · [详情](#paper-optirepair2026) |
| 2026 · ICML 2026 | **ORLoopBench**<br>ORLoopBench: Solver-in-the-Loop Benchmarks for Self-Correction and Behavioral Rationality in Operations Research | 以 IIS 和求解器重执行定义不可行模型修复闭环，配套 ORDebug 与 ORBias 评测。 | 方法 · 基准 · 数据 · 模型 | [![Publication][badge-053]][resource-348] · [![Paper 2][badge-052]][resource-349] · [![数据与校验代码][badge-125]][resource-060] · [详情](#paper-ao2026orloopbench) |
| 2026 · NeurIPS 2026（已接收，待出版） | **ReLoop / RetailOpt-190**（探索性）<br>ReLoop: Structured Modeling and Behavioral Verification for Reliable LLM-Based Optimization | 结合结构化建模链与求解器参数扰动检查，定位静默错误并实施诊断引导修复。 | 方法 · 基准 · 数据 | [![Paper 1][badge-058]][resource-350] · [![Conference][badge-072]][resource-351] · [![Code][badge-022]][resource-352] · [![Dataset][badge-060]][resource-065] · [详情](#paper-lian2026reloop) |
| 2026 · arXiv preprint | **RetailBench**<br>RetailBench: Evaluating Long-Horizon Autonomous Decision-Making and Strategy Stability of LLM Agents in Realistic Retail Environments | 在单店超市仿真中评测定价、补货、供应商和现金流等长期连贯决策。 | 基准 · 数据 · 平台 | [![Paper][badge-049]][resource-553] · [![Code][badge-022]][resource-067] · [详情](#paper-zhang2026retailbench) |
| 2025 · arXiv preprint | **AIM-Bench**<br>AIM-Bench: Evaluating Decision-making Biases of Agentic LLM as Inventory Manager | 在不确定库存补货实验中检查 LLM Agent 的决策偏差与信息共享效果。 | 基准 · 数据 · 评测分析 | [![Paper][badge-049]][resource-544] · [详情](#paper-zhao2025aimbench) |
| 2025 · arXiv preprint | **Ask, Clarify, Optimize**<br>Ask, Clarify, Optimize: Human-LLM Agent Collaboration for Smarter Inventory Control | 由 LLM 澄清库存需求并解释结果，把随机优化计算交给算法，以模拟经理测试交互。 | 方法 · 模型 · 应用 | [![Paper][badge-049]][resource-208] · [详情](#paper-askclarify2026) |
| 2025 · arXiv preprint | **CEoH**<br>Leveraging Large Language Models to Develop Heuristics for Emerging Optimization Problems | 在 EoH 提示中加入问题上下文，为仓储单元载荷预翻垛等较少研究的任务发现启发式。 | 方法 · 应用 | [![Paper][badge-049]][resource-461] · [![Code][badge-022]][resource-462] · [详情](#paper-bomer2025emerging) |
| 2024 · arXiv preprint | **InvAgent**（探索性）<br>InvAgent: A Large Language Model based Multi-Agent System for Inventory Management in Supply Chains | 让多个 LLM Agent 通过零样本推理管理供应链库存并适应需求变化。 | 方法 · 应用 | [![Paper][badge-049]][resource-536] · [![Code][badge-022]][resource-537] · [详情](#paper-quan2024invagent) |
| 2023 · arXiv preprint | **OptiGuide**（核心）<br>Large Language Models for Supply Chain Optimization | OptiGuide 将自然语言 what-if 查询转成对现有优化程序的分析，解释供应链决策结果。 | 方法 · 应用 | [![Paper][badge-049]][resource-325] · [![Code][badge-022]][resource-256] · [详情](#paper-li2023optiguide) |

### 能源与电力

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · arXiv preprint | **OPF Constrained Reasoning Study**<br>Can Large Language Models Reason and Optimize Under Constraints? | 在最优潮流场景中测试结构化输入、算术及物理约束下的直接推理和优化能力。 | 评测分析 | [![Paper][badge-049]][resource-552] · [详情](#paper-opf2026reason) |
| 2026 · ICML 2026 | **ProOPF**<br>ProOPF: Benchmarking and Improving LLMs for Professional-Grade Power Systems Optimization Modeling | 构建专业最优潮流建模数据和基准，区分参数调整与结构扩展难度。 | 基准 · 数据 · 应用 | [![Publication][badge-053]][resource-180] · [![Paper 2][badge-074]][resource-181] · [![Paper 3][badge-075]][resource-182] · [![Evaluation Code & Data][badge-076]][resource-064] · [详情](#paper-shen2026proopf) |
| 2026 · arXiv preprint | **Smart Grids Agentic AI Tutorial**<br>LLMs and Agentic AI Systems for Smart Grids: A Tutorial on Architectures and Applications | 综述智能电网 Agent 架构，并以充电、潮流和故障诊断等案例演示可信工具与显式检查。 | 综述 · 应用 | [![Paper][badge-049]][resource-532] · [![Case-study Code][badge-155]][resource-533] · [详情](#paper-smartgrid2026) |
| 2025 · arXiv preprint | **FunSearch for Unit Commitment**（探索性）<br>Automated Heuristic Design for Unit Commitment Using Large Language Models | 将 LLM 程序搜索与评估器用于机组组合启发式自动设计。 | 方法 · 应用 | [![Paper][badge-049]][resource-468] · [详情](#paper-ucfunsearch2025) |
| 2025 · arXiv preprint | **LLM-SUC**（探索性）<br>Can Large Language Model Agents Balance Energy Systems? | 将 LLM Agent 与多场景随机机组组合结合，辅助高风电不确定性下的运行决策。 | 方法 · 应用 | [![Paper][badge-049]][resource-235] · [![Code][badge-022]][resource-236] · [详情](#paper-llmsuc2025) |
| 2025 · arXiv preprint | **Validation-in-the-Loop Power Modeling**（探索性）<br>From Natural Language to Solver-Ready Power System Optimization: An LLM-Assisted, Validation-in-the-Loop Framework | 通过领域提示、结构化 schema、可行性校验与迭代修复生成电力优化模型。 | 方法 · 应用 | [![Paper][badge-049]][resource-285] · [详情](#paper-nl2ps2025) |
| 2023 · arXiv preprint | **LLMs for Power Engineering**（探索性）<br>LLM-based Frameworks for Power Engineering from Routine to Novel Tasks | 对常规电力优化编程采用端到端流程，对新任务采用工程师参与的分解与代码合成。 | 方法 · 应用 | [![Paper][badge-049]][resource-371] · [详情](#paper-li2023power) |

### 金融与资源配置

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · arXiv preprint | **LEAN-LLM-OPT**<br>Large-Scale Optimization Model Auto-Formulation: Harnessing LLM Flexibility via Structured Workflow | 动态构建建模工作流并将数据处理交给工具，面向大规模优化和航空收入管理。 | 方法 · 基准 · 数据 · 应用 | [![Paper][badge-049]][resource-134] · [![Code][badge-022]][resource-038] · [详情](#paper-liang2026leanllmopt) |
| 2026 · arXiv preprint | **LLM Agents for Efficient Frontiers**<br>LLM Agents for Combinatorial Efficient Frontiers: Investment Portfolio Optimization | 用 Agent 自动化基数约束均值—方差投资组合的启发式开发及有效前沿构建。 | 方法 · 应用 | [![Paper][badge-049]][resource-415] · [详情](#paper-efficientfrontier2026) |
| 2025 · arXiv preprint / submitted paper | **DINN**（探索性）<br>Decision-informed Neural Networks with Large Language Model Integration for Portfolio Optimization | 将 LLM 表征与决策导向训练结合，通过可微凸优化层直接对齐组合投资目标。 | 方法 · 应用 | [![Paper][badge-049]][resource-559] · [![Code][badge-022]][resource-560] · [详情](#paper-dinn2025) |
| 2025 · arXiv preprint | **EFS**<br>Evolutionary Factor Searching for Sparse Portfolio Optimization Using Large Language Models | 用 LLM 与进化搜索产生排序因子，并结合去冗余权重分配构建稀疏投资组合。 | 方法 · 应用 | [![Paper][badge-049]][resource-467] · [详情](#paper-luo2025efs) |
| 2025 · CIKM 2025 Financial AI Workshop | **LLM–Black-Litterman**（探索性）<br>LLM-Enhanced Black-Litterman Portfolio Optimization | 将 LLM 收益预测和不确定性转换为 Black–Litterman 投资观点及置信度。 | 方法 · 应用 | [![Paper 1][badge-058]][resource-561] · [![Workshop][badge-059]][resource-562] · [![Code][badge-022]][resource-563] · [详情](#paper-llmbl2025) |


[返回目录](#contents)

<a id="surveys"></a>

## 综述与基础资源

领域综述、分类框架和资源门户。

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · ACM Computing Surveys 58（2026） | **Combinatorial Optimization Systematic Review**<br>Large Language Models for Combinatorial Optimization: A Systematic Review | 按 PRISMA 流程筛选 LLM 组合优化研究，归纳任务、模型架构、评测数据与应用领域。 | 综述 | [![Paper 1][badge-051]][resource-110] · [![Paper 2][badge-052]][resource-111] · [详情](#paper-lco2026review) |
| 2026 · ACM Computing Surveys 58(8), Article 218 | **LLM4AD Survey**（核心）<br>A Systematic Survey on Large Language Models for Algorithm Design | 从优化器、预测器、抽取器和设计器四种角色综述 LLM 算法设计。 | 综述 | [![Paper 1][badge-058]][resource-421] · [![Journal][badge-104]][resource-422] · [![官方资源库（相关）][badge-094]][resource-423] · [详情](#paper-liu2024systematic) |
| 2026 · MIPRO 2026 | **LLMs as Optimizers Survey**<br>Large Language Models as Optimizers: A Survey of Direct vs. Tool-Augmented Approaches and Their Performance Frontiers | 区分直接优化、调用工具优化和创造可复用工具三种范式，比较文献中的性能边界。 | 综述 | [![Publication][badge-053]][resource-427] · [![Paper 2][badge-052]][resource-428] · [详情](#paper-llmasopt2026) |
| 2026 · IEEE CIM（期刊记录；出版日期未确认） | **LLMs for Evolutionary Optimization Survey**<br>A Systematic Survey on Large Language Models for Evolutionary Optimization: From Modeling to Solving | 从建模到求解梳理 LLM 与进化优化，区分直接优化、算法内部辅助与高层算法设计。 | 综述 | [![Journal record][badge-061]][resource-135] · [![Paper 2][badge-052]][resource-136] · [![Literature Collection（相关）][badge-062]][resource-137] · [详情](#paper-sysevo2025) |
| 2026 · arXiv preprint | **Smart Grids Agentic AI Tutorial**<br>LLMs and Agentic AI Systems for Smart Grids: A Tutorial on Architectures and Applications | 综述智能电网 Agent 架构，并以充电、潮流和故障诊断等案例演示可信工具与显式检查。 | 综述 · 应用 | [![Paper][badge-049]][resource-532] · [![Case-study Code][badge-155]][resource-533] · [详情](#paper-smartgrid2026) |
| 2025 · AAAI 2025 | **DOCP Research Manifesto**（核心）<br>Enhancing Decision Making Through the Integration of Large Language Models and Operations Research Optimization | 提出面向业务用户的优化 Copilot 愿景，梳理需求澄清、模型核验和求解效率等研究要求。 | 综述 · 基础 | [![Paper 1][badge-051]][resource-223] · [![Paper 2][badge-052]][resource-224] · [详情](#paper-wasserkrug2024manifesto) |
| 2025 · IJCAI 2025 Survey Track | **LLM4OR Survey**（核心）<br>A Survey of Optimization Modeling Meets LLMs: Progress and Future Directions | 综述优化建模全流程，分析并标记基准错误，提供清洗数据与评测门户。 | 综述 · 数据 | [![Paper][badge-049]][resource-237] · [![官方资源库（相关）][badge-094]][resource-238] · [![Cleaned Benchmarks][badge-095]][resource-092] · [详情](#paper-xiao2025survey) |
| 2025 · arXiv preprint | **LLMs in OR: Methods & Challenges**<br>Large Language Models in Operations Research: Methods, Applications, and Challenges | 按自动建模、辅助优化和直接求解梳理 LLM 在运筹学中的方法与应用。 | 综述 | [![Paper][badge-049]][resource-243] · [详情](#paper-wang2025lor) |
| 2025 · arXiv preprint | **Teaching LLMs to Think Mathematically**<br>Teaching LLMs to Think Mathematically: A Critical Study of Decision-Making via Optimization | 结合系统综述与元分析，在新构造的计算机网络优化题中比较三种提示策略。 | 综述 · 评测分析 · 数据 | [![Paper][badge-049]][resource-283] · [详情](#paper-abedi2025thinkmath) |
| 2024 · arXiv preprint | **LLM4AD**（核心）<br>LLM4AD: A Platform for Algorithm Design with Large Language Model | 提供模块化算法设计平台，统一搜索方法、任务、LLM 接口与评估沙箱。 | 平台 | [![Paper][badge-049]][resource-510] · [![Code][badge-022]][resource-494] · [详情](#paper-liu2024llm4ad) |
| 2024 · arXiv preprint | **LLM–EA Automated Optimization Insights**<br>Deep Insights into Automated Optimization with Large Language Models and Evolutionary Algorithms | 梳理 LLM 与进化算法的自动优化框架，分析表示、变异、适应度和提示设计。 | 综述 | [![Paper][badge-049]][resource-511] · [详情](#paper-yu2024deep) |
| 2024 · Constraints 29（2024） | **Ner4Opt**<br>Ner4Opt: named entity recognition for optimization modelling from natural language | 从优化问题文本识别变量、参数、目标和约束等实体，比较词法、语义、微调及语言模型方案。 | 方法 · 模型 · 基础 | [![Paper][badge-057]][resource-299] · [![Code][badge-022]][resource-300] · [![ner4opt-roberta-v1][badge-110]][resource-003] · [![ner4opt-roberta-v2][badge-111]][resource-004] · [![HF Demo（相关）][badge-100]][resource-301] · [详情](#paper-dakle2023ner4opt) |
| 2023 · ICLR 2023 DL4C Workshop / arXiv | **CodeT5 Mathematical Program Synthesis**<br>Synthesis of Mathematical programs from Natural Language Specifications | 用 GPT-3 反向翻译扩充训练样本，微调 CodeT5，并依据 LP 规则重评和修正候选输出。 | 方法 · 模型 · 基础 | [![Paper][badge-049]][resource-316] · [详情](#paper-synth2023) |
| 2023 · arXiv preprint | **Holy Grail 2.0**<br>Holy Grail 2.0: From Natural Language to Constraint Models | 讨论把自然语言转为约束模型的分解式提示流程，并报告 GPT 模型的早期结果。 | 方法 · 基础 | [![Paper][badge-049]][resource-317] · [详情](#paper-kadioglu2023holygrail) |
| 2023 · arXiv preprint | **NL4Opt: Auto-Formulation Approach**<br>A Novel Approach for Auto-Formulation of Optimization Problems | 在 NL4Opt 竞赛的实体识别和公式生成两任务中，结合预训练、对抗训练、提示和模型集成。 | 方法 · 基础 | [![Paper][badge-049]][resource-321] · [![Code][badge-022]][resource-322] · [详情](#paper-iflytek2023autoformulation) |

[返回目录](#contents)

<a id="adjacent"></a>

## 邻近方向与算法发现

通用程序演化、科学发现与 LLM 直接求解等相关研究。

| 年份 / Venue | 论文 | 一句话贡献 | 贡献类型 | 资源 |
|---|---|---|---|---|
| 2026 · Nature Communications（2026） | **AutoModSAT**<br>Discovering heuristics in a complex SAT solver with large language models | 结合模块化 SAT 求解器、提示优化和进化搜索，发现复杂求解器中的有效启发式。 | 方法 · 数据 | [![Paper 1][badge-051]][resource-374] · [![Paper 2][badge-052]][resource-375] · [![Code Archive][badge-132]][resource-376] · [![Evaluation Data][badge-133]][resource-084] · [详情](#paper-sun2025satheur) |
| 2026 · arXiv preprint | **AutoOPT**（探索性）<br>A Domain-Specific Harness for End-to-End Automation of Optimization Research | 连接数值方法设计、LLM 符号推导、Lean 4 验证和人工解释，研究最优一阶优化算法。 | 方法 · 平台 | [![Paper][badge-049]][resource-522] · [![Code][badge-022]][resource-523] · [![Skills][badge-150]][resource-100] · [![Lean Proofs][badge-151]][resource-524] · [详情](#paper-autoopt2026) |
| 2026 · JAIR 86（2026） | **AutoSAT**<br>AutoSAT: Automatically Optimize SAT Solvers via Large Language Models | 在模块化 CDCL 求解器中搜索并替换启发式，以 LLM 生成代码并迭代评估。 | 方法 | [![Paper 1][badge-051]][resource-377] · [![Paper 2][badge-052]][resource-378] · [![Code][badge-022]][resource-379] · [详情](#paper-sun2024autosat) |
| 2026 · AAAI 2026 | **CO-Bench**（核心）<br>CO-Bench: Benchmarking Language Model Agents in Algorithm Search for Combinatorial Optimization | 提供组合优化算法搜索基准，比较 LLM Agent 与人工设计算法。 | 基准 · 数据 | [![Proceedings][badge-105]][resource-384] · [![Paper 2][badge-052]][resource-385] · [![Code][badge-022]][resource-386] · [![Dataset][badge-060]][resource-024] · [详情](#paper-sun2026cobench) |
| 2026 · ACM Computing Surveys 58（2026） | **Combinatorial Optimization Systematic Review**<br>Large Language Models for Combinatorial Optimization: A Systematic Review | 按 PRISMA 流程筛选 LLM 组合优化研究，归纳任务、模型架构、评测数据与应用领域。 | 综述 | [![Paper 1][badge-051]][resource-110] · [![Paper 2][badge-052]][resource-111] · [详情](#paper-lco2026review) |
| 2026 · arXiv preprint | **ConstraintBench**<br>ConstraintBench: Benchmarking LLM Constraint Reasoning on Direct Optimization | 要求 LLM 直接输出结构化解，使用确定性校验器逐约束检查并与 Gurobi 最优解比较。 | 基准 · 数据 | [![Paper][badge-049]][resource-545] · [详情](#paper-constraintbench2026) |
| 2026 · arXiv preprint | **Infeasibility-Aware CO Models**<br>Infeasibility Aware Large Language Models for Combinatorial Optimization | 用精确优化与可认证筛选构建可行／不可行训练样本，微调模型输出解或不可行判断，再辅助局部搜索。 | 方法 · 数据 · 模型 | [![Paper][badge-049]][resource-409] · [![Author Code / Data Archive（相关）][badge-138]][resource-073] · [详情](#paper-infeasibilityaware2026) |
| 2026 · IEEE TEVC 30（2026） | **LLaMoCo**<br>LLaMoCo: Instruction Tuning of Large Language Models for Optimization Code Generation | 构造问题—优化代码指令集，以对比学习预热和指令微调训练从问题代码生成优化程序的模型。 | 方法 · 模型 · 数据 | [![Paper 1][badge-051]][resource-339] · [![Paper 2][badge-052]][resource-340] · [![LLaMoCo-S Example][badge-123]][resource-341] · [![LLaMoCo-S][badge-124]][resource-001] · [详情](#paper-ma2024llamoco) |
| 2026 · arXiv preprint | **LLM-MAS for Service Operations**<br>Optimizing Service Operations via LLM-Powered Multi-Agent Simulation | 用交互 LLM 模拟参与者响应，并以轨迹上的梯度估计和方差缩减优化服务设计。 | 方法 · 应用 | [![Paper][badge-049]][resource-528] · [详情](#paper-wang2026llmmas) |
| 2026 · ACM Computing Surveys 58(8), Article 218 | **LLM4AD Survey**（核心）<br>A Systematic Survey on Large Language Models for Algorithm Design | 从优化器、预测器、抽取器和设计器四种角色综述 LLM 算法设计。 | 综述 | [![Paper 1][badge-058]][resource-421] · [![Journal][badge-104]][resource-422] · [![官方资源库（相关）][badge-094]][resource-423] · [详情](#paper-liu2024systematic) |
| 2026 · MIPRO 2026 | **LLMs as Optimizers Survey**<br>Large Language Models as Optimizers: A Survey of Direct vs. Tool-Augmented Approaches and Their Performance Frontiers | 区分直接优化、调用工具优化和创造可复用工具三种范式，比较文献中的性能边界。 | 综述 | [![Publication][badge-053]][resource-427] · [![Paper 2][badge-052]][resource-428] · [详情](#paper-llmasopt2026) |
| 2026 · IEEE CIM（期刊记录；出版日期未确认） | **LLMs for Evolutionary Optimization Survey**<br>A Systematic Survey on Large Language Models for Evolutionary Optimization: From Modeling to Solving | 从建模到求解梳理 LLM 与进化优化，区分直接优化、算法内部辅助与高层算法设计。 | 综述 | [![Journal record][badge-061]][resource-135] · [![Paper 2][badge-052]][resource-136] · [![Literature Collection（相关）][badge-062]][resource-137] · [详情](#paper-sysevo2025) |
| 2026 · ICLR 2026 | **MoH**<br>Generalizable Heuristic Generation Through LLMs with Meta-Optimization | 演化可自调用的元优化程序，让其构造启发式优化器，再为多个下游问题演化启发式。 | 方法 | [![Paper 1][badge-051]][resource-431] · [![Paper 2][badge-052]][resource-432] · [![Code][badge-022]][resource-433] · [![CO Task Data][badge-140]][resource-094] · [详情](#paper-moh2025) |
| 2026 · Findings of ACL 2026 | **NLCO**<br>Reasoning in a Combinatorial and Constrained World: Benchmarking LLMs on Natural-Language Combinatorial Optimization | 评测直接从自然语言情景输出离散解的能力，按变量、约束、全局结构与目标分层分析。 | 基准 · 数据 | [![Paper 1][badge-051]][resource-550] · [![Paper 2][badge-052]][resource-551] · [![Code][badge-022]][resource-046] · [![Dataset][badge-060]][resource-045] · [详情](#paper-jiang2026nlco) |
| 2026 · arXiv preprint | **OPF Constrained Reasoning Study**<br>Can Large Language Models Reason and Optimize Under Constraints? | 在最优潮流场景中测试结构化输入、算术及物理约束下的直接推理和优化能力。 | 评测分析 | [![Paper][badge-049]][resource-552] · [详情](#paper-opf2026reason) |
| 2026 · Findings of ACL 2026 | **OPT-BENCH / OPT-Agent**<br>OPT-BENCH: Evaluating the Iterative Self-Optimization of LLM Agents in Large-Scale Search Spaces | 在机器学习调优与 NP 问题中评测迭代自优化，并用 OPT-Agent 复用历史反馈修订方案。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-529] · [![Paper 2][badge-052]][resource-530] · [![Revised Preprint][badge-154]][resource-531] · [![Code][badge-022]][resource-048] · [![Dataset][badge-060]][resource-047] · [详情](#paper-li2026optbench) |
| 2026 · arXiv preprint | **PowerAtlas / ECBench**<br>PowerAtlas: Feasibility-Aware Language Models for Electricity-Computing Co-Scheduling | 以可行性反馈训练 LLM 直接生成电力—计算联合排程，并提出 ECBench 与确定性评分。 | 方法 · 基准 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-538] · [![Code & Sample Data][badge-156]][resource-063] · [详情](#paper-jiang2026poweratlas) |
| 2026 · arXiv preprint | **RetailBench**<br>RetailBench: Evaluating Long-Horizon Autonomous Decision-Making and Strategy Stability of LLM Agents in Realistic Retail Environments | 在单店超市仿真中评测定价、补货、供应商和现金流等长期连贯决策。 | 基准 · 数据 · 平台 | [![Paper][badge-049]][resource-553] · [![Code][badge-022]][resource-067] · [详情](#paper-zhang2026retailbench) |
| 2026 · ICLR 2026 | **ShinkaEvolve**<br>ShinkaEvolve: Towards Open-Ended and Sample-Efficient Program Evolution | 结合父代采样、代码新颖性拒绝采样和 bandit 模型选择，提高程序演化的样本效率。 | 方法 · 平台 | [![Paper 1][badge-051]][resource-444] · [![Paper 2][badge-052]][resource-445] · [![Code][badge-022]][resource-446] · [详情](#paper-lange2026shinka) |
| 2025 · Technical report | **AlphaEvolve**（核心）<br>AlphaEvolve: A coding agent for scientific and algorithmic discovery | 用 LLM 与进化式代码修改闭环改进算法，覆盖科学问题及计算基础设施优化。 | 方法 | [![Paper][badge-049]][resource-453] · [![官方结果（相关）][badge-142]][resource-454] · [![官方问题集（相关）][badge-143]][resource-455] · [详情](#paper-novikov2025alphaevolve) |
| 2025 · GECCO 2025 Workshop / Companion | **BLADE**<br>BLADE: Benchmark suite for LLM-driven Automated Design and Evolution of iterative optimisation heuristics | 为 LLM 自动算法发现提供连续黑箱优化问题、实例生成、标准日志及行为分析工具。 | 基准 · 平台 | [![Paper 1][badge-051]][resource-459] · [![Paper 2][badge-052]][resource-460] · [![Code][badge-022]][resource-021] · [详情](#paper-vanstein2025blade) |
| 2025 · arXiv preprint / submitted paper | **DINN**（探索性）<br>Decision-informed Neural Networks with Large Language Model Integration for Portfolio Optimization | 将 LLM 表征与决策导向训练结合，通过可微凸优化层直接对齐组合投资目标。 | 方法 · 应用 | [![Paper][badge-049]][resource-559] · [![Code][badge-022]][resource-560] · [详情](#paper-dinn2025) |
| 2025 · arXiv preprint | **EASE**<br>Solve it with EASE | 以模块化生成、测试、分析和评价循环支持算法方案演化，允许多个 LLM 承担互补角色。 | 方法 · 平台 | [![Paper][badge-049]][resource-360] · [![Framework][badge-129]][resource-361] · [![Frontend][badge-130]][resource-362] · [详情](#paper-viktorin2025ease) |
| 2025 · arXiv preprint | **EFS**<br>Evolutionary Factor Searching for Sparse Portfolio Optimization Using Large Language Models | 用 LLM 与进化搜索产生排序因子，并结合去冗余权重分配构建稀疏投资组合。 | 方法 · 应用 | [![Paper][badge-049]][resource-467] · [详情](#paper-luo2025efs) |
| 2025 · IEEE PESGM 2025 | **ElecBench**（探索性）<br>ElecBench: a Power Grid Dispatch Evaluation Benchmark for Large Language Models | 以电力知识、监控、调度和黑启动文本任务评价事实性、逻辑性及稳定性等维度。 | 基准 · 数据 | [![Paper 1][badge-051]][resource-554] · [![Paper 2][badge-052]][resource-555] · [![Public Test Subset][badge-158]][resource-030] · [详情](#paper-zhou2024elecbench) |
| 2025 · arXiv preprint | **FunSearch for Unit Commitment**（探索性）<br>Automated Heuristic Design for Unit Commitment Using Large Language Models | 将 LLM 程序搜索与评估器用于机组组合启发式自动设计。 | 方法 · 应用 | [![Paper][badge-049]][resource-468] · [详情](#paper-ucfunsearch2025) |
| 2025 · IEEE TEVC 29(2):331–345 | **LLaMEA**（核心）<br>LLaMEA: A Large Language Model Evolutionary Algorithm for Automatically Generating Metaheuristics | 通过 LLM 自动生成、变异及选择元启发式，用运行评价反馈持续改进算法。 | 方法 | [![Paper][badge-049]][resource-478] · [![Code][badge-022]][resource-479] · [详情](#paper-vanstein2024llamea) |
| 2025 · arXiv preprint | **LLM Algorithm-search Fitness Landscapes**<br>Fitness Landscape of Large Language Model-Assisted Automated Algorithm Search | 以算法为节点、LLM 转换为边构造图景，跨任务和模型研究搜索崎岖性及相似性。 | 评测分析 | [![Paper][badge-049]][resource-480] · [详情](#paper-liu2025fitness) |
| 2025 · arXiv preprint | **LLM Heuristic Behaviour-space Analysis**<br>Behaviour Space Analysis of LLM-driven Meta-heuristic Discovery | 比较 LLaMEA 的提示变体，在 BBOB 上记录探索、利用、收敛和停滞等行为指标。 | 评测分析 | [![Paper][badge-049]][resource-481] · [![Behaviour Metrics Code][badge-146]][resource-482] · [详情](#paper-vanstein2025behaviour) |
| 2025 · NeurIPS 2025 | **LLMCoSolver / E2E CO Solver**<br>Large Language Models as End-to-end Combinatorial Optimization Solvers | 经 SFT 与可行性／最优性感知的 FOARL，训练 LLM 从问题描述直接输出组合优化解。 | 方法 · 模型 · 数据 | [![Paper 1][badge-051]][resource-539] · [![Paper 2][badge-052]][resource-540] · [![Code][badge-022]][resource-541] · [![SFT Data][badge-030]][resource-074] · [![RL Data][badge-031]][resource-075] · [详情](#paper-jiang2025e2eco) |
| 2025 · Proceedings of the Design Society 5 · ICED25（2025） | **LLMs for DSM Sequencing**<br>Large language models for combinatorial optimization of design structure matrix | 把网络拓扑和领域知识共同提供给 LLM，迭代搜索设计结构矩阵的排序方案。 | 方法 · 应用 | [![Paper 1][badge-051]][resource-557] · [![Paper 2][badge-052]][resource-558] · [详情](#paper-dsmco2024) |
| 2025 · arXiv preprint | **LLMs in OR: Methods & Challenges**<br>Large Language Models in Operations Research: Methods, Applications, and Challenges | 按自动建模、辅助优化和直接求解梳理 LLM 在运筹学中的方法与应用。 | 综述 | [![Paper][badge-049]][resource-243] · [详情](#paper-wang2025lor) |
| 2025 · CIKM 2025 Financial AI Workshop | **LLM–Black-Litterman**（探索性）<br>LLM-Enhanced Black-Litterman Portfolio Optimization | 将 LLM 收益预测和不确定性转换为 Black–Litterman 投资观点及置信度。 | 方法 · 应用 | [![Paper 1][badge-058]][resource-561] · [![Workshop][badge-059]][resource-562] · [![Code][badge-022]][resource-563] · [详情](#paper-llmbl2025) |
| 2025 · ICML 2025 | **MCTS-AHD**（核心）<br>Monte Carlo Tree Search for Comprehensive Exploration in LLM-Based Automatic Heuristic Design | 将生成的启发式组织为 MCTS 搜索树，继续探索暂时低分候选的潜力。 | 方法 | [![Paper 1][badge-051]][resource-489] · [![arXiv][badge-087]][resource-490] · [![Code][badge-022]][resource-491] · [详情](#paper-zheng2025mctsahd) |
| 2025 · AAAI 2025 | **MEoH**<br>Multi-Objective Evolution of Heuristic Using Large Language Model | 在解质量、计算效率和可扩展性之间搜索 Pareto 启发式，并以支配关系和差异性选择候选。 | 方法 | [![Paper 1][badge-051]][resource-492] · [![Paper 2][badge-052]][resource-493] · [![LLM4AD: MEoH][badge-147]][resource-494] · [详情](#paper-yao2025meoh) |
| 2025 · ICLR 2025 | **MILP-Evolve**（核心）<br>Towards Foundation Models for Mixed Integer Linear Programming | 用 LLM 演化生成多样 MILP 类与实例，支持间隙预测、学习分支和语言对齐。 | 方法 · 数据 | [![Paper 1][badge-051]][resource-495] · [![arXiv][badge-087]][resource-496] · [![Code][badge-022]][resource-497] · [![Dataset][badge-060]][resource-076] · [![GitHub Data][badge-012]][resource-498] · [详情](#paper-li2025milpevolve) |
| 2025 · NeurIPS 2025 | **MM-Agent / MM-Bench（数学建模）**（探索性）<br>MM-Agent: LLM as Agents for Real-world Mathematical Modeling Problem | 将数学建模拆为问题分析、模型构造、计算求解和报告生成，并提供 MCM/ICM 来源的 MM-Bench。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-246] · [![Paper 2][badge-052]][resource-247] · [![Paper 3][badge-097]][resource-248] · [![Code & MM-Bench][badge-098]][resource-043] · [![Expert Skills (2026 add-on)][badge-099]][resource-101] · [![HF Demo（相关）][badge-100]][resource-249] · [详情](#paper-liu2025mmagent) |
| 2025 · Findings of EMNLP 2025 | **ModelingAgent / ModelingBench**（探索性）<br>ModelingAgent: Bridging LLMs and Mathematical Modeling for Real-World Challenges | 用多 Agent 协调工具和迭代修订处理开放式建模，并以 ModelingBench 与 ModelingJudge 评估报告。 | 方法 · 基准 · 数据 | [![Paper 1][badge-051]][resource-250] · [![Paper 2][badge-052]][resource-251] · [![Code & ModelingBench][badge-101]][resource-044] · [详情](#paper-qian2025modelingagent) |
| 2025 · arXiv preprint | **PAIR**<br>PAIR: A Novel Large Language Model-Guided Selection Strategy for Evolutionary Algorithms | 通过适应度、多样性与交叉兼容性提示 LLM 选择进化算法中的配对个体，并在 TSP 上评测。 | 方法 | [![Paper][badge-049]][resource-501] · [![Code][badge-022]][resource-502] · [详情](#paper-ali2025pair) |
| 2025 · arXiv preprint | **Starjob**<br>Starjob: Dataset for LLM-Driven Job Shop Scheduling | 发布作业车间调度训练数据，用 LoRA 微调 LLM 直接输出调度解。 | 方法 · 数据 · 模型 · 应用 | [![Paper][badge-049]][resource-542] · [![Code][badge-022]][resource-543] · [![Dataset][badge-060]][resource-081] · [详情](#paper-abgaryan2025starjob) |
| 2025 · arXiv preprint | **Visual Graph Optimization with MLLMs**（探索性）<br>Bridging Visualization and Optimization: Multimodal Large Language Models on Graph-Structured Combinatorial Optimization | 把图结构呈现为图像，结合多模态 LLM 与简单搜索处理影响最大化、网络拆解和图任务。 | 方法 · 评测分析 | [![Paper][badge-049]][resource-556] · [详情](#paper-bridgingviz2025) |
| 2024 · ICML 2024 | **EoH**（核心）<br>Evolution of Heuristics: Towards Efficient Automatic Algorithm Design Using Large Language Model | 同步演化自然语言启发式思路和可执行代码，以性能反馈驱动自动算法设计。 | 方法 · 基础 | [![Paper 1][badge-051]][resource-507] · [![arXiv][badge-087]][resource-508] · [![Code][badge-022]][resource-509] · [详情](#paper-liu2024eoh) |
| 2024 · arXiv preprint | **InvAgent**（探索性）<br>InvAgent: A Large Language Model based Multi-Agent System for Inventory Management in Supply Chains | 让多个 LLM Agent 通过零样本推理管理供应链库存并适应需求变化。 | 方法 · 应用 | [![Paper][badge-049]][resource-536] · [![Code][badge-022]][resource-537] · [详情](#paper-quan2024invagent) |
| 2024 · arXiv preprint | **LLM4AD**（核心）<br>LLM4AD: A Platform for Algorithm Design with Large Language Model | 提供模块化算法设计平台，统一搜索方法、任务、LLM 接口与评估沙箱。 | 平台 | [![Paper][badge-049]][resource-510] · [![Code][badge-022]][resource-494] · [详情](#paper-liu2024llm4ad) |
| 2024 · arXiv preprint | **LLM–EA Automated Optimization Insights**<br>Deep Insights into Automated Optimization with Large Language Models and Evolutionary Algorithms | 梳理 LLM 与进化算法的自动优化框架，分析表示、变异、适应度和提示设计。 | 综述 | [![Paper][badge-049]][resource-511] · [详情](#paper-yu2024deep) |
| 2024 · ICLR 2024 | **OPRO**（探索性）<br>Large Language Models as Optimizers | 根据历史候选及其数值评价提示 LLM 生成新解，研究直接优化与提示优化。 | 方法 · 基础 | [![Publication][badge-053]][resource-512] · [![Paper 2][badge-052]][resource-513] · [![Code][badge-022]][resource-514] · [详情](#paper-yang2024opro) |
| 2024 · arXiv preprint | **Rare MIP Challenges**<br>Leveraging Large Language Models for Solving Rare MIP Challenges | 结合微调、思维链与递归动态温度生成罕见 MIP 场景的可行解。 | 方法 | [![Paper][badge-049]][resource-515] · [详情](#paper-wang2024raremip) |
| 2024 · NeurIPS 2024 | **ReEvo**（核心）<br>ReEvo: Large Language Models as Hyper-Heuristics with Reflective Evolution | 结合进化搜索与 LLM 反思，用语言反馈指导超启发式程序改进。 | 方法 | [![Paper 1][badge-051]][resource-516] · [![arXiv][badge-087]][resource-517] · [![Code][badge-022]][resource-518] · [详情](#paper-ye2024reevo) |
| 2023 · arXiv preprint | **AEL**（核心）<br>Algorithm Evolution Using Large Language Model | 让 LLM 生成算法并在进化循环中选择改写，以 TSP 构造启发式展示算法级演化。 | 方法 · 基础 | [![Paper][badge-049]][resource-519] · [详情](#paper-liu2023ael) |
| 2023 · Nature（2023 在线发表） | **FunSearch**（核心）<br>Mathematical discoveries from program search with large language models | 结合 LLM 程序生成、进化搜索和自动评估，发现数学构造与装箱启发式。 | 方法 · 基础 | [![Paper][badge-057]][resource-520] · [![Code][badge-022]][resource-521] · [详情](#paper-romera2023funsearch) |

[返回目录](#contents)

<a id="contributing"></a>

## 收录与贡献

欢迎通过 Issue 或 Pull Request 补充论文、修正分类或提供遗漏资源。请提供题名、作者、年份、发表状态、原文链接、一句话贡献及可确认关联的资源。一篇工作使用一个稳定 ID，相关版本在同一记录下说明；论文可同时属于多个模块，见[分类与阅读说明](#classification)。

- **范围：** 优先收录涉及优化模型、求解器、OR 算法或相关评测的工作；邻近方向明确标注。
- **准确性：** 区分正式发表、作者声明接收、预印本与 Workshop；资源存在不自动等于官方发布。“复核”覆盖元数据、摘要方法与逐链接证据，不表示已重现实验。
- **引文与版本：** 作者、相关版本及资源范围见本页[文献信息](#paper-info)；引用时采用论文正式页面或注明版本的原始引文。

相关资源列表：[LLM4OR][resource-238] · [awesome-fm4co][resource-564] · [LLM4AlgorithmDesign][resource-423]。本库逐条核验并采用自己的多标签分类，不将外部列表的记录直接视为已确认信息。

<a id="paper-info"></a>

## 作者、版本与资源说明

论文以正式发表记录或注明的预印本为依据；同一工作保持一个 ID，相关版本的作者、题名与实验范围可不同。

| 论文与作者 | 版本与资源说明 |
|---|---|
| <a id="paper-chen2026a2dept"></a>**A2DEPT**<br>Bin Chen; Shouliang Zhu; Beidan Liu; Yong Zhao; Tianle Pu; Huichun Li; Zhengqiu Zhu | 摘要依据：2604.24043v1<br>论文提供 arXiv 与 ICML 2026 会议入口。程序树演化不自动等同 LLM 参数训练；未确认公开实现或权重。 |
| <a id="paper-zhang2026afl"></a>**AFL**<br>Zhang, Ni; Cao, Zhiguang; Zhou, Jianan; Zhang, Cong; Ong, Yew-Soon | 摘要依据：2510.16701v2<br>与 DRoC 的外部求解器／文档检索路线分开；实验可行性高不等于任意新约束均有正确性保证。 |
| <a id="paper-xu2026agenticmip"></a>**Agentic MIP Research**<br>Xu, Liding; Zhou, Yugeng; Pokutta, Sebastian | 摘要依据：2605.09186v1<br>作者主页列为 submitted。插件通过框架测试和求解评估，不据此声称每条生成传播规则均有数学有效性证明；作者其他 SCIP 仓库没有明确关联本论文，未混入。 |
| <a id="paper-soliloquy2026"></a>**Agora-Opt**<br>Jianghao Lin; Zi Ling; Chenyu Zhou; Tianyi Xu; Ruoqing Jiang; Zizhuo Wang; Dongdong Ge | 摘要依据：2604.25847v1<br>HF 同名仓库主要是脚本文件，未核实作者归属，不能作为模型权重。修订数据不标为首次提出七个新基准，求解一致性也不自动证明完整题意符合性。 |
| <a id="paper-xie2026ailsahd"></a>**AILS-AHD**<br>Zhuoliang Xie; Fei Liu; Zhenkun Wang; Qingfu Zhang | 摘要依据：2602.23092v2<br>原文中的 AILS-CVRP 与 PyHygese 为基线或底层工具，不当作 AILS-AHD 官方实现。未核到本方法代码入口。 |
| <a id="paper-invpolicy2026"></a>**Automated Inventory Policy Design**<br>Yang, Fenghua; Baxi, Preet; Zhang, Yi; Jasin, Stefanus; Lei, Yanzhe; Liu, Mo; Pakiman, Parshan | 摘要依据：2609.08071v1 |
| <a id="paper-sun2025satheur"></a>**AutoModSAT**<br>Sun, Yiwen; Ye, Furong; Chen, Zhihan; Wei, Ke; Cai, Shaowei | 摘要依据：2507.22876v2<br>Automatically Discovering Heuristics in a Complex SAT Solver with Large Language Models [![版本][badge-159]][resource-375]：预印本题名含 Automatically，当前正式版题名不含该词<br>正式版题名已由 Automatically discovering 改为 Discovering，按 Nature Communications 页面记录；与 AutoSAT 为相关的独立论文，分别保留。 |
| <a id="paper-autoopt2026"></a>**AutoOPT**<br>Heechang Kim; Ernest K. Ryu; Shuvomoy Das Gupta | 摘要依据：2608.07407v1<br>属于连续优化算法研究的邻近方向。两个案例的形式化结论依赖具体假设，流程仍包含人工审查。 |
| <a id="paper-autoor2026"></a>**AutoOR**<br>Motwani, Sumeet Ramesh; Du, Chuan; Petrov, Aleksander; Davis, Christopher; Torr, Philip; Papania-Davis, Antonio; Yan, Weishi | 摘要依据：2604.16804v4<br>ICML 2026 页面明确为 RLxF: RL from World Feedback Workshop，不标主会。当前 arXiv 标题为 Autoformulate，会议页面为 Autoformalize；标准 verifiers / TRL 库不当作本方法实现。 |
| <a id="paper-robustreform2026"></a>**AutoREM / AutoRO-Bench**<br>Chen, Jinbiao; Jin, Shuang; Zhang, Guoyun; Zhang, Junyu; Wang, Guanyi; Qin, Hanzhang | 摘要依据：2605.11813v1<br>记忆离线适配不等同权重训练；未核到公开实现或数据下载入口。 |
| <a id="paper-sun2024autosat"></a>**AutoSAT**<br>Sun, Yiwen; Ye, Furong; Zhang, Xianyin; Huang, Shiyu; Zhang, Bingzhen; Wei, Ke; Cai, Shaowei | 摘要依据：2402.10705v3<br>JAIR 正式出版年份由 DOI 注册记录核实为 2026，保留历史 2024 ID。SAT 求解器增强与 MILP 传播组件分开标记。 |
| <a id="paper-bife2026"></a>**BiFE**<br>Zhang, Ce; Zhang, Bin; Xu, Zhiwei; Chen, Hao; Lu, Xinyue; Fan, Shanwei; Teng, Yingxuan; Fan, Guoliang | 摘要依据：2609.36735v1 |
| <a id="paper-huang2025calm"></a>**CALM (Algorithm–LM Co-evolution)**<br>Ziyao Huang; Weiwei Wu; Kui Wu; Wei-Bin Lee; Jianping Wang | 摘要依据：2505.12285v1<br>CALM: Co-evolution of Algorithms and Language Model for Automatic Heuristic Design [![版本][badge-159]][resource-382]：预印本版本；正式引文按 proceedings 元数据；作者：Ziyao Huang; Weiwei Wu; Kui Wu; Jianping Wang; Wei-Bin Lee<br>与 CALM Before the STORM 是不同工作。正式引文采用 ICLR proceedings 元数据；仓库提供 GRPO 代码，所用 Qwen 基座不当作已发布的 CALM 微调权重。 |
| <a id="paper-lporch2025"></a>**CHORUS**<br>Tasnim Ahmed; Salimur Choudhury | 摘要依据：2505.01485v1<br>LION 19 为 2025 年会议，正式章节于 2026-01-02 出版，引文年份采用 2026；历史 ID 保留。目标值匹配是该评测的操作性判据，不证明任意模型完全符合题意。未把后续 CHORUS++ 自动归为本工作实现。 |
| <a id="paper-canonicalir2026"></a>**CIR / R2C**<br>Lyu, Zhongyuan; Hu, Shuoyu; Liu, Lujie; Yang, Hongxia; LI, Ming | 摘要依据：2602.02029v1<br>原文中间表示用于约束语义与建模范式选择，不自动提供跨求解器正确性保证。 |
| <a id="paper-sun2026cobench"></a>**CO-Bench**<br>Sun, Weiwei; Feng, Shengyu; Li, Shanda; Yang, Yiming | AAAI 正式论文页确认 2026 年发表、作者与 DOI；仓库仍引用 2025 arXiv 版。HF 另有 FrontierCO 后续资源，本条仅将 CO-Bench/CO-Bench 视为本论文数据。 |
| <a id="paper-co4all2025"></a>**Combinatorial Optimization for All**<br>Camilo Chacón Sartori; Christian Blum | 摘要依据：2503.10968v1<br>Combinatorial Optimization for All: Using LLMs to Aid Non-Experts in Improving Optimization Algorithms [![版本][badge-159]][resource-389]：预印本版本；正式引文按 DOI 注册信息；作者：Camilo Chacón Sartori; Christian Blum<br>作者资源包括提示、生成算法、实例和结果；未将其标为新的通用组合优化基准。 |
| <a id="paper-lco2026review"></a>**Combinatorial Optimization Systematic Review**<br>Francesca Da Ros; Michael Soprano; Luca Di Gaspero; Kevin Roitero | 摘要依据：2507.03637v1<br>Large Language Models for Combinatorial Optimization: A Systematic Review [![版本][badge-159]][resource-111]：预印本版本；正式引文按 DOI 注册信息；作者：Francesca Da Ros; Michael Soprano; Luca Di Gaspero; Kevin Roitero |
| <a id="paper-constraintinjection2026"></a>**Constraint Injection / VRPCoder**<br>Luo, Xizi; He, Changhong; Geng, Dongdong; Shi, Chenggong; Mei, Yu | 摘要依据：2606.04816v2<br>当前 VRPBench 仓库发布问题与参考最优值，不能据此宣称验证器、训练流程或 VRPCoder 权重已公开。 |
| <a id="paper-constraintbench2026"></a>**ConstraintBench**<br>Tso, Joseph; Schmittou, Preston; Huynh, Quan; Hutchins, Jibran | 摘要依据：2602.22465v2<br>原文声明代码将公开；未确认实际发布入口，未将未来发布声明视为已有资源。 |
| <a id="paper-coopa2026"></a>**COOPA**<br>Chuanhao Li; Xiaoan Xu; Dirk Bergemann; Ethan X. Fang; Yehua Wei; Zhuoran Yang | 摘要依据：2606.27611v1<br>置信度来自模型自评，来源可追溯不等于模型已获形式化正确性或概率校准保证。 |
| <a id="paper-cpagent2025"></a>**CP-Agent**<br>Szeider, Stefan | 摘要依据：2508.07468v3<br>正式版发表于 ICSE 2026 的 LLM4Code Workshop，保留历史 2025 ID。Zenodo 概念 DOI 指向当前 v2（2026-07-14），说明修正了变异审计发现的验证问题；原版与修订版实验不可混用。<br>Author Coding Agent：作者的通用编码 Agent 与 CPMpy 模板；实验与修订评测材料由 Zenodo 单独发布。 |
| <a id="paper-cpsync2026"></a>**CP-SynC**<br>Song, Yuliang; Cohen, Eldan | 摘要依据：2605.01675v1<br>官方仓库当前已含 benchmark 与 eval.py；README 将 Modeling Workflow Code 和 Solution Format Checker 标为 Coming soon，未标完整方法实现已公开。与后续 CP-SynC-XL 的研究分别说明，不混用资源版本。<br>Benchmark & Evaluation：当前公开内容以数据与评测为主，完整建模工作流尚未开放。 |
| <a id="paper-xiao2026deepor"></a>**DeepOR**<br>Ziyang Xiao; Yuan Jessica Wang; Xiongwei Han; Shisi Guan; Jingyan Zhu; Jingrong Xie; Lilin Xu; Han Wu; Wing Yin Yu; Zehua Liu; Xiaojin Fu; Gang Chen; Dongxiang Zhang | 正式论文页确认 AAAI 2026；官方仓库首页的 AAAI 2025 与其自身 BibTeX 冲突，以正式论文页为准。未检索到可确认的作者发布权重。<br>官方种子与样例数据：README 声明提供种子和 SFT/RL 样例；不能视为完整训练数据发布。 |
| <a id="paper-zhang2026dschellm"></a>**DScheLLM**<br>Zhang, Lixiang; Zhao, Chenggong; Gao, Qing; Zhao, Xiaoke; Bai, Gengyi; Lv, Jinhu | 摘要依据：2601.09100<br>正文数据声明称研究数据包含在文章中；未核到独立数据或权重下载，不把基础 OpenPangu 权重当成本论文模型发布。 |
| <a id="paper-dsevolve2026"></a>**DSevolve**<br>Zhou, XinLei; Huang, Jin; Yang, Jie; Li, Xinyu; Gao, Liang | 摘要依据：2603.27628v2<br>题名和方法采用 arXiv v2；神经选择器训练不自动等同 LLM 参数微调，不混用其他版本数字。 |
| <a id="paper-dynaschedbench2026"></a>**DynaSchedBench**<br>Cao, Shijie; Yuan, Yuan; Liu, Jing | 摘要依据：2605.27566v1<br>仓库发布实例生成器、数据、仿真和评测代码；ICML 2026 proceedings 已确认。 |
| <a id="paper-epoch2026"></a>**EPOCH**<br>Oguzhan Gungordu; Ayse Tursucular; Siheng Xiong; Faramarz Fekri | 摘要依据：2610.17379v1<br>作者主页列为预印本；未核到官方代码、训练语料或 checkpoint 下载。HF 搜索中的同名 epoch / heuristic 模型不自动关联。 |
| <a id="paper-es2026ahd"></a>**ES-AHD**<br>Yutao Lai; Kezhao Lai; Hai-Lin Liu; Yuping Wang; Ping Guo | 摘要依据：2609.00023v1<br>ICIST 2026 官方最终议程列出同题报告及 Hai-Lin Liu，确认会议接收；议程不代替正式论文集记录。完整作者名单依据预印本，不以报告人替换作者。仓库可见 run_es_ahd.py 和 llm4ad 实现目录。 |
| <a id="paper-chen2026evobb"></a>**Evo-B&B**<br>Chen, Jiayu; Chen, Chentong; Liu, Yuhan; Fan, Ye; Sun, Jianyong; Shi, Jialong | 摘要依据：2610.22861v1 |
| <a id="paper-guan2026evom"></a>**EVOM**<br>Guan, Runda; Shen, Xiangqing; Zhang, Jiajun; Zhang, Yifan; Cheng, Jian; Xia, Rui | 摘要依据：2604.00442v1<br>执行成功或最优值匹配不构成题意完全正确的数学证明。未确认公开的官方代码与模型入口。 |
| <a id="paper-he2026evoopt"></a>**EvoOpt-LLM**<br>Yiliu He; Tianle Li; Binghao Ji; Zhiyuan Liu; Di Huang | 摘要依据：2602.01082<br>代码使用 Openpangu-7B 基座，未将基座下载当作 EvoOpt 微调权重。原文剪枝的经验分类指标不提供一般最优性保留保证。 |
| <a id="paper-evooptigraph2026"></a>**EvoOptiGraph**<br>Qingcan Kang; Mingyang Liu; Xiaojin Fu; Shixiong Kai; Tao Zhong; Mingxuan Yuan | 摘要依据：2606.26578v1<br>图操作、编译和回译检查的有效性依赖原文设定，不表示任意自然语言模型均获语义保证。NeurIPS 2026 官方海报日程确认接收，待正式出版；未确认官方代码或权重入口。 |
| <a id="paper-coevolve2026"></a>**EvoOR-Agent**<br>Jiahao Huang; Peilan Xu; Xiaoya Nan; Wenjian Luo | 摘要依据：2604.17708v2<br>演化对象是架构和推理程序，不是 LLM 权重。原文匿名代码入口受限；另找到研究实现仓库，但未核实作者归属，未作为官方代码展示。 |
| <a id="paper-li2026falsification"></a>**Falsification-Based Verification**<br>Li, Haifeng; Hai, Mo | 摘要依据：2607.16646v2<br>这是有条件的可证伪审计，不是对任意自然语言需求或所有模型错误的完备正确性证明。采用 arXiv v2；未找到可核实的代码、数据与权重入口。 |
| <a id="paper-wang2026formalize"></a>**Formalize, Don't Optimize**<br>Wang, Haoyu; Song, Yuliang; Li, Tao; Deng, Zhiwei; Wang, Yaqing; Ramachandran, Deepak; Cohen, Eldan; Roth, Dan | 摘要依据：2605.12421v1<br>对应 NeurIPS 页面明确为 Who Verifies the Agents? Workshop，不是主会。CP-SynC-XL 已在论文中提出，但未确认下载入口。 |
| <a id="paper-yuan2026formuevo"></a>**FormuEvo**<br>Yuan, Haofeng; Peng, Jianing; Bi, Jieyi; Zhang, Ni; Song, Shiji; Cao, Zhiguang | 摘要依据：2608.23353v2<br>未将经验记忆迁移写成已发布的蒸馏权重，也未把运行反馈写成全部重构已获形式化等价证明。 |
| <a id="paper-kong2026frontieror"></a>**FrontierOR**<br>Kong, Minwei; Jiang, Chonghe; Qu, Ao; Ouyang, Wenbin; Zeng, Zhaoming; Guo, Xiaotong; Li, Zhekai; Li, Junyi; Fan, Yi; Zheng, Xinshou; Jing, Xi; Zhang, Yikai; Liang, Zhiwei; Kim, Seonghoo; Yang, Runqing; Zhou, Zijian; Li, Sirui; Zheng, Han; Ying, Wangyang; Zheng, Ou; Wang, Chonghuan; Zhao, Jinglong; Qin, Hanzhang; Wu, Cathy; Liang, Paul Pu; Zhao, Jinhua; Wang, Hai | 摘要依据：2605.25246v3<br>相关版本 [![版本][badge-160]][resource-033]：FrontierOR-v1，180 项；发布日期 2026-09-27<br>相关版本 [![版本][badge-161]][resource-131]：会议页面摘要为 110 项，保持版本区分<br>当前 arXiv / 官方发布为 180 项任务，NeurIPS 会议页面描述 110 项；不混用版本数字。官方海报日程确认接收，待正式出版；不据全站导航推断本篇 Track。 |
| <a id="paper-yu2026alns"></a>**Full-Component ALNS Evolution**<br>Yu, Shaohua; Chen, Tianyu; Liu, Linyan; Puchinger, Jakob | 摘要依据：2603.06996v2<br>官方仓库主要发布各演化模式得到的 ALNS 程序及汇总，不据此确认完整 LLM 演化工作流已开放。<br>Evolved ALNS：原文数据声明与目录树确认演化结果；不是完整框架实现的发布声明。 |
| <a id="paper-zhao2026glns"></a>**G-LNS**<br>Zhao, Baoyun; Wang, He; Zeng, Liang | 摘要依据：2602.08253v1 |
| <a id="paper-beergame2026"></a>**GenAI Beer Game Reliability**<br>Long, Carol Xuan; Simchi-Levi, David; Zhu, Feng; Su, Huangyuan; Calmon, Andre P.; Calmon, Flavio P. | 摘要依据：2605.17036v4<br>使用既有 Beer Game 研究可靠性，不把它自动标为首次提出新的库存基准；原文结果依赖具体配置与需求路径。 |
| <a id="paper-luo2026grimip"></a>**GRIMIP**<br>Luo, Yidong; Chen, Xuemin; Wang, Chenguang; Zhu, Fangzhou; Zhong, Tao; Yu, Tianshu | 摘要依据：2606.23299v2 |
| <a id="paper-chen2025heurigym"></a>**HeuriGym**<br>Chen, Hongzheng; Wang, Yingheng; Cai, Yaohui; Hu, Hins; Li, Jiajie; Huang, Shirley; Deng, Chenhui; Liang, Rongjian; Kong, Shufeng; Ren, Haoxing; Samaranayake, Samitha; Gomes, Carla P.; Zhang, Zhiru | 摘要依据：2506.07972v2<br>ICLR 2026 正式论文集已收录。官方主页同时宣传后续 HeuriGen 数据，未将后续工作的训练数据误归本论文。 |
| <a id="paper-chen2025hifoprompt"></a>**HiFo-Prompt**<br>Chentong Chen; Mengyuan Zhong; Jialong Shi; Jianyong Sun; Ye Fan | 摘要依据：2508.13333v2<br>HiFo-Prompt: Prompting with Hindsight and Foresight for LLM-based Automatic Heuristic Design [![版本][badge-159]][resource-407]：预印本版本；正式引文按 proceedings 元数据；作者：Chentong Chen; Mengyuan Zhong; Ye Fan; Jialong Shi; Jianyong Sun |
| <a id="paper-infeasibilityaware2026"></a>**Infeasibility-Aware CO Models**<br>Yakun Wang; Min Chen; Zeguan Wu; Junyu Liu; Sitao Zhang; Zhenwen Shao | 摘要依据：2604.01455v1<br>数据标签的认证和筛选定理具有明确适用条件，不表示 LLM 每次不可行判断都带有效证书。作者 Google Drive 归档可见图着色和 embedding 文件夹；未核到独立权重下载。HF 同名 LLMOptimizer 资源与本文未建立关联。<br>Author Code / Data Archive：原文提供的代码与数据目录；checkpoint 发布范围未确认。 |
| <a id="paper-conversation2026"></a>**Interactive Optimization Conversations**<br>Drossman, Joshua; Jacquillat, Alexandre; Martin, Sébastien | 摘要依据：2604.02666v1<br>原文仓库的 README 为空，但目录树包含 decision_agent、evaluation 等代码；空 README 不代表空实现。 |
| <a id="paper-invbench2026"></a>**InventoryBench**<br>Baek, Jackie; Fu, Yaopeng; Ma, Will; Peng, Tianyi | 摘要依据：2602.12631v2 |
| <a id="paper-invevolve2026"></a>**InvEvolve**<br>Huang, Chenyu; Lin, Jianghao; Tang, Zhengyang; Jiang, Bo; Jiang, Ruoqing; Wang, Benyou; Wei, Lai | 摘要依据：2605.00369v4 |
| <a id="paper-jorbench2026"></a>**JOR-Bench**<br>Yuu Jinnai | 摘要依据：2607.16777v1<br>日文版本是派生资源，不声称首次提出五个源基准。HF 显示的 2,638 行包含日英两种语言，不把它们当作 2,638 道不同源问题；求解答案匹配也不等同全面语义验证。 |
| <a id="paper-hsplo2026"></a>**LaGO**<br>Mingxin Yu; Ruixiao Yang; Chuchu Fan | 摘要依据：2602.16038v1<br>forward / backward / update 描述评价、反馈和程序改写，不自动表示 LLM 反向传播或参数训练。未将引用的 ReEvo 仓库当作本方法代码。 |
| <a id="paper-latentheuristic2026"></a>**Latent Heuristic Search**<br>Cheikh Ahmed; Mahdi Mostajabdaveh; Zirui Zhou | 摘要依据：2605.17137v1<br>LION 20 官方接收名单及议程可核；名单页明确不构成正式出版，未核到本篇正式论文集记录。训练的是辅助编码／代理／映射模块，生成 LLM 保持冻结，不能写成领域 LLM SFT。代码已核，未确认预训练辅助权重下载。 |
| <a id="paper-liang2026leanllmopt"></a>**LEAN-LLM-OPT**<br>Liang, Kuo; Lu, Yuhang; Mao, Jianming; Sun, Shuyi; Yang, Chunwei; Zeng, Congcong; Jin, Xiao; Qin, Hanzhang; Zhu, Ruihao; Teo, Chung-Piaw | 摘要依据：2601.09635v3 |
| <a id="paper-ma2024llamoco"></a>**LLaMoCo**<br>Zeyuan Ma; Yue-Jiao Gong; Hongshu Guo; Jiacheng Chen; Yining Ma; Zhiguang Cao; Jun Zhang | 摘要依据：2403.01131v2<br>LLaMoCo: Instruction Tuning of Large Language Models for Optimization Code Generation [![版本][badge-159]][resource-340]：预印本版本；正式引文按 DOI 注册信息；作者：Zeyuan Ma; Hongshu Guo; Jiacheng Chen; Guojun Peng; Zhiguang Cao; Yining Ma; Yue-Jiao Gong<br>正式 TEVC 2026 作者列表与 2024 预印本不同，分别保留。已确认 LLaMoCo-S 示例和 CodeGen 权重，不将承诺后续公开的 M/L 模型或其他同名 HF checkpoint 当作已发布。匿名旧入口受限，使用已核作者仓库。 |
| <a id="paper-efficientfrontier2026"></a>**LLM Agents for Efficient Frontiers**<br>Paquette-Greenbaum, Simon; Yu, Jiangbo | 摘要依据：2601.00770v1 |
| <a id="paper-zhang2026autoconfig"></a>**LLM MIP Configuration**<br>Michael Zhang; Justin Okamoto; Antonia Chmiela; Oleksandr Radomskyi; Christian Schulz; Jeremy L Wyatt | NeurIPS 页面明确写 Poster in Workshop: Second Workshop on MLxOR，非主会录用证明。作者直接按该官方页面记录。 |
| <a id="paper-behaviorrep2025"></a>**LLM Representations for Algorithm Selection**<br>Francesca Da Ros; Luca Di Gaspero; Kevin Roitero | 摘要依据：2512.13374v2<br>Behavior and Representation in Open-Weight Large Language Models for Combinatorial Optimization: From Feature Extraction to Algorithm Selection [![版本][badge-159]][resource-418]：预印本版本；正式引文按 DOI 注册信息；作者：Francesca Da Ros; Luca Di Gaspero; Kevin Roitero<br>出版社记录已匹配题名及作者，仅给出 2026 年 12 月编期，无可核的 online 日期；不将未来编期记为已出版。Zenodo 是代码、数据、激活与探测产物归档，不当作新领域 LLM 权重。<br>Code & Analysis Data：约1.32 GB的物化归档，文件清单和 README 描述包含代码、数据、激活与探测实验材料；不包含新的领域模型权重声明。 |
| <a id="paper-zheng2026cutmgmt"></a>**LLM-guided Cutting-plane Management**<br>Zheng, Zetao; Wang, Zhe; Shao, Jie | - |
| <a id="paper-wang2026llmmas"></a>**LLM-MAS for Service Operations**<br>Wang, Yanyuan; Zhang, Xiaowei | 摘要依据：2604.04383v1<br>LLM 模拟行为，外层算法更新设计参数；不能将其等同于 LLM 直接执行数值求解。 |
| <a id="paper-liu2024systematic"></a>**LLM4AD Survey**<br>Liu, Fei; Yao, Yiming; Guo, Ping; Yang, Zhiyuan; Zhao, Zhe; Lin, Xi; Tong, Xialiang; Mao, Kun; Lu, Zhichao; Wang, Zhenkun; Yuan, Mingxuan; Zhang, Qingfu | ACM 记录为2026-02-10正式发表；历史 ID 保留2024，主记录采用发表年份2026，作者采用 arXiv 版本。 |
| <a id="paper-llm4branch2026"></a>**LLM4Branch**<br>Hou, Zhinan; Li, Xingchen; Zhang, Yankai; Li, Tianxun; You, Keyou | 摘要依据：2605.10401v1 |
| <a id="paper-llmasopt2026"></a>**LLMs as Optimizers Survey**<br>Roko Peran; Luka Hobor; Mihael Kovac; Mario Brcic | 摘要依据：2606.15577v1 |
| <a id="paper-sysevo2025"></a>**LLMs for Evolutionary Optimization Survey**<br>Yisong Zhang; Ran Cheng; Guoxing Yi; Kay Chen Tan | 摘要依据：2509.08269v7<br>出版社 DOI 注册记录已匹配题名和四位作者，登记年份为 2026、页码 1–21；未给出卷期及可核的 online 日期，不据此标已正式出版。方法范围依据所列 arXiv 版本。 |
| <a id="paper-meevo2026"></a>**MeEvo**<br>Zishang Qiu; Xinan Chen; Rong Qu; Ruibin Bai | 摘要依据：2606.14202v5 |
| <a id="paper-chen2025mela"></a>**MeLA**<br>Zishang Qiu; Xinan Chen; Long Chen; Wenjie Yi; Ruibin Bai | 摘要依据：2507.20541v4<br>MeLA: A Metacognitive LLM-Driven Architecture for Automatic Heuristic Design [![版本][badge-159]][resource-343]：预印本版本；正式引文按 DOI 注册信息；作者：Zishang Qiu; Xinan Chen; Long Chen; Ruibin Bai<br>ESWA 正式记录增加 Wenjie Yi，预印本作者另列。Crossref 仅给出2026年12月编期，未给出可核 online 日期，采用未来编期状态；方法说明依据预印本。 |
| <a id="paper-milpevo2026"></a>**MILP-Evo**<br>Nie, Jinbiao; Feng, Kewei; Zhang, Xiaoyuan; Yin, Shan; Wang, Zizhuo; Dong, Bin | 摘要依据：2607.18252v1<br>具体实例化为 SCIP 的割选择和分支规则；标题中的 solver auto-design 不表示重新实现整个 MILP 求解器。与 microsoft/MILP-Evolve 的实例生成工作不同，不关联其 HF 数据。 |
| <a id="paper-mind2026"></a>**MIND**<br>Liu, Weiting; Wu, Han; Kuang, Yufei; Han, Xiongwei; Zhong, Tao; Feng, Jianfeng; Lu, Wenlian | 摘要依据：2602.11164v1<br>同作者其他基准不自动归属本工作；未发现可确认的 MIND 官方发布入口。 |
| <a id="paper-zhao2026miniopt"></a>**MiniOpt**<br>Ke Zhao; Zixiang Di; Hong Qian; Xiang Shu; Yaolin Wen; Qitao Shi; Bingdong Li; Xingyu Lu; Xiangfeng Wang; Jun Zhou; Ke Tang; Yang Yu | 摘要依据：2606.25832v2<br>公开训练／推理代码与示例数据，未确认完整训练数据或最终权重下载入口。 |
| <a id="paper-li2026miplibnl"></a>**MIPLIB-NL**<br>Li, Zhong; Lu, Hongliang; Wei, Tao; Chen, Yuxuan; Liu, Wenyu; Lan, Yuan; Zhang, Fan; Wen, Zaiwen | GitHub dataset：官方 README 描述 dataset/<problem>/ 下的 instance.json、model.md、solve.py 与数据文件。 |
| <a id="paper-mirror2026"></a>**MIRROR**<br>Shi, Yifan; Wang, Jiayi; Wu, Minyi; Fan, Ye; Shi, Jialong; Sun, Jianyong | 摘要依据：arXiv:2602.03318v4<br>按 2026-08-24 的 arXiv v4 作者列表记录；旧搜索索引作者顺序和人数不同。 |
| <a id="paper-zhu2026mmoptbench"></a>**MM-OptBench**<br>Li, Zhong; Huang, Qi; Zhu, Yuxuan; Amiri, Mohammad Mohammadi; van Stein, Niki; Bäck, Thomas; van Leeuwen, Matthijs; Wen, Zaiwen; Yang, Lincen | 摘要依据：2605.12154v1<br>NeurIPS 2026 官方海报日程确认接收，待正式出版。未核到公开代码、数据或模型入口，不因摘要称 benchmark 而推断已开放下载。 |
| <a id="paper-moh2025"></a>**MoH**<br>Yiding Shi; Jianan Zhou; Wen Song; Jieyi Bi; Yaoxin Wu; Zhiguang Cao; Jie Zhang | 摘要依据：2505.20881<br>Generalizable Heuristic Generation Through LLMs with Meta-Optimization [![版本][badge-159]][resource-432]：预印本版本；正式引文按 proceedings 元数据；作者：Yiding Shi; Jianan Zhou; Wen Song; Jieyi Bi; Yaoxin Wu; Zhiguang Cao; Jie Zhang<br>本文 multi-task training 是元优化程序的多任务搜索与评价，未发现 LLM 权重训练步骤。Google Drive 是作者提供的任务数据压缩包入口，不当新命名基准。<br>CO Task Data：作者提供的数据归档 data.zip；未将归档视为完整训练框架。 |
| <a id="paper-ha2025paretogrid"></a>**MPaGE**<br>Ha Minh Hieu; Hung Phan; Tung Duy Doan; Tung Dao; Cong Dao Tran; Huynh Thi Thanh Binh | 摘要依据：2507.20923v3<br>Pareto-Grid-Guided Large Language Models for Fast and High-Quality Heuristics Design in Multi-Objective Combinatorial Optimization [![版本][badge-159]][resource-435]：预印本版本；正式引文按 DOI 注册信息；作者：Minh Hieu Ha; Hung Phan; Tung Duy Doan; Tung Dao; Dao Tran; Huynh Thi Thanh Binh |
| <a id="paper-warehouseformsel2026"></a>**Multi-Warehouse Formulation Selection**<br>Xu, Jintao; Ma, Yingzheng; Dong, Jiong; Qi, Yongzhi; Zhang, Jianshen | 摘要依据：2607.25956v1<br>使用京东实例进行实验不代表原始业务数据已公开；未核到官方代码、数据或权重入口。 |
| <a id="paper-nemo2026"></a>**NEMO**<br>Yang Song; Anoushka Vyas; Zirui Wei; Sina Khoshfetrat Pakazad; Henrik Ohlsson; Graham Neubig | 摘要依据：2601.21372v3<br>HF 仓库发布七组逐题产物与两组结果表，属于评测输出与轨迹，不是新建九个基准，也不等同完整 NEMO 编排源码。执行通过不保证题意完全正确。 |
| <a id="paper-jiang2026nlco"></a>**NLCO**<br>Xia Jiang; Jing Chen; Cong Zhang; Jie Gao; Chengpeng Hu; Chenhao Zhang; Yaoxin Wu; Yingqian Zhang | 摘要依据：2602.02188v2<br>已替换失效 ACL preview 地址为正式 Findings 页面；Ministral 等测试模型不是本论文的新权重。 |
| <a id="paper-opf2026reason"></a>**OPF Constrained Reasoning Study**<br>Bernier, Fabien; Ghamizi, Salah; Dogoulis, Pantelis; Cordy, Maxime | 摘要依据：2603.23004v1 |
| <a id="paper-li2026optbench"></a>**OPT-BENCH / OPT-Agent**<br>Xiaozhe Li; Jixuan Chen; Xinyu Fang; Shengyuan Ding; Haodong Duan; Qingwen Liu (刘晴雯); Kai Chen | 摘要依据：2506.10764v1<br>OPT-BENCH: Evaluating LLM Agent on Large-Scale Search Spaces Optimization Problems [![版本][badge-159]][resource-530]：原预印本<br>OPT-BENCH: Evaluating the Iterative Self-Optimization of LLM Agents in Large-Scale Search Spaces [![版本][badge-159]][resource-531]：官方仓库关联的修订预印本<br>正式版题名已更改；仓库明确将 2025 原预印本与 2605.08904 修订预印本关联为同一 OPT-BENCH，不新增 ID。 |
| <a id="paper-chen2026optengine"></a>**OPT-Engine**<br>Chen, Yitian; Cheng, Cheng; Sun, Yinan; Ling, Zi; Ge, Dongdong | 摘要依据：2601.19924v2<br>HF 官方卡及仓库均关联 chenyitian-shanshu/OPTEngine；同名 chengcheng2k4/OPT-Engine 缺少资源关联证据，未展示。仓库列出的 SIRL checkpoint 属其他训练工作，不归成本论文的新模型。 |
| <a id="paper-optminer2026"></a>**Opt-Miner**<br>Haoyang Liu; Yuyang Cai; Jie Wang; Xiongwei Han; Minyang Hu; Shuqi Liu; Mingxuan Yuan; Jianye Hao; Feng Wu | 代码、HF 结果和演示均为第三方有限复现，主要评估基座 Qwen3-8B，未覆盖作者完整 R-GRPO 训练；未确认作者权重下载入口。 |
| <a id="paper-optarcus2026"></a>**OptArgus**<br>Li, Zhong; Guo, Zihan; Lu, Xiaohan; Wang, Juntao; Song, Jie; Shen, Chao; Wu, Jiageng; Sun, Mingyang | 摘要依据：2605.11738v1<br>题名采用 OptArgus，稳定 ID 为 optarcus2026。原文提出三部分评测套件，未确认代码或数据下载入口。 |
| <a id="paper-xiu2026optgraph"></a>**OptGraph**<br>Xianchao Xiu; Jianhao Li; Huangyue Chen; Wanquan Liu | 摘要依据：2607.27918v1<br>不因题名含 evolutionary optimization 就仅归入启发式设计。公开主流程、种子知识图与更新工具，仓库明确不含原始日志和非主实验脚本。 |
| <a id="paper-optiagentbench2026"></a>**Opti-Agent-Bench**<br>Fu, Yongchang; Huang, Xinjie; Dai, Chengjun; Feng, Chengzhe; Zhang, Junshao; Zhu, Hong | 摘要依据：2607.10768v1<br>微软 RD-Agent 是基线或相关系统，不能作为本基准官方实现；未确认公开基准数据或评测代码。 |
| <a id="paper-optiagent2026"></a>**OptiAgent**<br>Monteiro, Adriana Laurindo; Fagundes, Nayse; Langeloh, Gabriel Mattos; Kanno, Gustavo de Oliveira; Aguirre, Priscila Louise; da Rocha, Thiago Costa Rizuti; Beltran, Victor Leme | 摘要依据：2607.05346v1<br>仅使用已有四组基准；正文提到的 ORThought 和 LLMOPT 属其他工作，不作为本论文发布的代码或权重。 |
| <a id="paper-chen2025optichat"></a>**OptiChat**<br>Chen, Hao; Constante-Flores, Gonzalo Esteban; Mantri, Krishna Sri Ipsit; Kompalli, Sai Madhukiran; Ahluwalia, Akshdeep Singh; Li, Can | 摘要依据：2501.08406v2<br>这是早期不可行诊断工作的扩展论文，分别有独立题名和 arXiv ID，不合并成同一篇。Crossref 确认期刊版为 2026 年；保留历史 2025 ID。 |
| <a id="paper-dslmilp2026"></a>**OptiDSL**<br>Zhang, Shaofeng; Su, Hongyuan; Peng, Qingwen; Zong, Zefang; Liu, Shengcai; Tang, Ke; Li, Yong | 摘要依据：2608.07040v1<br>正文明确提出新基准，故同时归入方法与评测。原文匿名实现地址返回 403，当前内容无法确认，代码和数据入口留空；跨范式执行不等于已证明跨求解器等价。 |
| <a id="paper-optiloop2026"></a>**OptiLoop**<br>Xu, Yujia; Wang, Zhiheng; Dinh, Thi | 摘要依据：2605.27630v1<br>这是有限场景、有限轮协调的行为检查；不能将局部通过或匹配目标值写成任意协同问题的形式化保证。 |
| <a id="paper-optirepair2026"></a>**OptiRepair**<br>Ao, Ruicheng; Simchi-Levi, David; Wang, Xinshang | 摘要依据：2602.19439v2<br>OptiRepair-SC 与 P1/P2 模型分别登记；ORLoopBench 将本工作作为相关的供应链专用前作引用，分别保留论文 ID。未确认可对应的权重或数据下载入口。 |
| <a id="paper-optiverse2026"></a>**OptiVerse / DVA-Agent**<br>Xinyu Zhang; Boxuan Zhang; Yuchen Wan; Lingling Zhang; YiXing Yao; Bifan Wei; Yaqiang Wu; Jun Liu | 摘要依据：2604.21510v1<br>OptiVerse: A Comprehensive Benchmark towards Optimization Problem Solving [![版本][badge-159]][resource-163]：预印本版本；正式引文采用 proceedings 元数据；作者：Xinyu Zhang; Boxuan Zhang; Yuchen Wan; Lingling Zhang; YiXing Yao; Bifan Wei; Yaqiang Wu; Jun Liu<br>DVA-Agent 依赖抽取和交叉比对，不能当作任意模型的形式化正确性证明。仓库实际执行文件位于 evaluation/，已核推理、审核和评分脚本。 |
| <a id="paper-yang2026optskills"></a>**OptSkills**<br>Yang, Haochen; Zhao, Ke; Ma, Mengyuan; Lu, Xingyu; Wang, Xiangfeng; Qian, Hong | 摘要依据：arXiv:2605.29829v2<br>正式版本已收入 Findings of EMNLP 2026；方法与技能库说明依据所列预印本版本。<br>资源：作者团队仓库，README 含同名论文与作者；关联到 fujiwaranoM0kou 作者账号。 |
| <a id="paper-wang2026orprm"></a>**OR-PRM**<br>Wang, Yilin; Zhou, Heng; Mao, Dongxing; Li, Linjie; Tan, Jingru; Han, Haochen; Yang, Zhengyuan; Wang, Alex Jinpeng; Li, Min | OR-PRM 以 Qwen2.5-7B-Coder 为基座，经 SFT 与 DPO 训练；Qwen3-8B 是数据验证器。模型与数据贡献分别指 OR-PRM 和 OR-ProcessQA，未确认公开下载入口。 |
| <a id="paper-ding2026orr1"></a>**OR-R1**<br>Zezhen Ding; Zhen Tan; Jiheng Zhang; Tianlong Chen | 摘要依据：2511.09092v1<br>OR-R1: Automating Modeling and Solving of Operations Research Optimization Problem via Test-Time Reinforcement Learning [![版本][badge-159]][resource-170]：预印本版本；正式引文按 DOI 注册信息；作者：Zezhen Ding; Zhen Tan; Jiheng Zhang; Tianlong Chen<br>AAAI 正式 DOI、卷期与页码由注册记录核实。仓库无 README 但可见 SFT、GRPO、LoRA 合并及评测代码，不据 README 缺失判定未发布。 |
| <a id="paper-zhou2026orspace"></a>**OR-Space**<br>Zhou, Chenyu; Lu, Xinyun; Zhao, Jiangyue; Lin, Jianghao; Ge, Dongdong; Ye, Yinyu | 摘要依据：2605.28158v1 |
| <a id="paper-oragentbench2026"></a>**ORAgentBench**<br>Li, Jiajun; Cai, Mingshu; Li, Yixuan; Ding, Yu; Hou, Ran; Nie, Guanyu; Han, Xiongwei; Wang, Wanyuan | 摘要依据：2606.19787v1 |
| <a id="paper-ao2026orloopbench"></a>**ORLoopBench**<br>Ao, Ruicheng; Simchi-Levi, David; Wang, Xinshang | 摘要依据：2601.21008v3<br>公开仓库提供 ORDebug/ORBias 数据及校验脚本，发布 schema 与原文生成布局存在差异。策略模型和 PRM 分别登记，未确认论文权重下载入口。 |
| <a id="paper-yang2025orthought"></a>**ORThought / LogiOR**<br>Beinuo Yang; Qishen Zhou; Junyi Li; Chenxing Su; Panagiotis Angeloudis; Simon Hu | 摘要依据：arXiv:2508.14410v3<br>ORThought: Benchmarking and Automating Logistics Optimization Modeling [![版本][badge-159]][resource-565]：2025；Preprint, v3 revised 2026-04-18；v3, 2026-04-18；更早版本题为 Automated Optimization Modeling through Expert-Guided Large Language Model Reasoning。；作者：Beinuo Yang; Qishen Zhou; Junyi Li; Chenxing Su; Panagiotis Angeloudis; Simon Hu<br>期刊正式题名、六位作者、2026年、卷6及文章号100059由 DOI 注册元数据核实，官方仓库直接引用同一出版页面。保留历史 ID yang2025orthought；2025 是预印本首发年份。方法摘要按 arXiv v3，未混入其他版本性能数字。注册记录未给出可核的具体日月，不填猜测日期。出版社正文访问受限，未声称重新阅读全文。<br>arXiv v3：对应摘要方法的固定版本；主记录题名、作者和年份采用期刊正式元数据。 |
| <a id="paper-yan2026pall"></a>**PALL**<br>An Yan; Huigen Ye; Hua Xu; Jiahao Zhang | NeurIPS 2026 官方海报日程确认接收，待正式出版。未确认代码或权重入口。 |
| <a id="paper-pathwise2026"></a>**PathWise**<br>Oguzhan Gungordu; Siheng Xiong; Faramarz Fekri | 摘要依据：2601.20539v3<br>PathWise: Planning through World Model for Automated Heuristic Design via Self-Evolving LLMs [![版本][badge-159]][resource-439]：预印本版本；正式引文按 proceedings 元数据；作者：Oguzhan Gungordu; Siheng Xiong; Faramarz Fekri<br>self-evolving 指搜索状态、动作和程序演化；未据此推断更新 LLM 权重。 |
| <a id="paper-lu2026pearl"></a>**PEARL**<br>Lu, Hongliang; Li, Zhong; Chen, Yuxuan; Lan, Yuan; Zhang, Fan; Wen, Zaiwen | NeurIPS 2026 官方海报日程已确认接收；会议安排在 2026 年 12 月，暂不记为正式出版。 |
| <a id="paper-jiang2026poweratlas"></a>**PowerAtlas / ECBench**<br>Jiang, Kaiwen; Xu, Siya; Zhu, Ziyue; Xue, Kaiwen; Yang, Chao; Luu, Anh Tuan; Luo, Haoran | 摘要依据：2607.26710v2<br>PowerAtlas: Towards Electricity-Computing Co-Scheduling for Power Systems [![版本][badge-159]][resource-538]：历史题名；当前采用原文新题名<br>当前 arXiv 标题已更新为 Feasibility-Aware Language Models for Electricity-Computing Co-Scheduling。原文报告仍有残留供给缺口，不能将 feasibility-aware 写成保证可行。仓库有生成器、样例和训练／评测代码，未确认完整打包的 2,000 实例或权重下载。 |
| <a id="paper-shen2026proopf"></a>**ProOPF**<br>Shen, Chao; Guo, Zihan; Wan, Xu; Yang, Zhenghao; Zhang, Yifan; Huang, Wenqi; Song, Jie; Zhang, Zongyan; Sun, Mingyang | 摘要依据：2602.03070v5<br>官方仓库的 ProOPF_D 目录标为 few-shot example data，仅将其列为公开训练示例，不宣称完整 12K 数据已公开。作者名 Wenqi Huang 采用 ICML 页面，arXiv citation 元数据拼写为 Wengi。 |
| <a id="paper-pyvrpplus2026"></a>**PyVRP+ / MEP**<br>Manuj Malik; Jianan Zhou; Shashank Reddy Chirra; Zhiguang Cao | 摘要依据：2604.07872v1<br>PyVRP$^+$: LLM-Driven Metacognitive Heuristic Evolution for Hybrid Genetic Search in Vehicle Routing Problems [![版本][badge-159]][resource-442]：预印本版本；作者：Manuj Malik; Jianan Zhou; Shashank Reddy Chirra; Zhiguang Cao<br>AAMAS 2026 官方论文集目录列出同题论文、四位作者及起始页 2800。原文代码地址当前只有 README.md，未标实现已开放。PyVRP 基础求解器不是本论文新发布的代码。 |
| <a id="paper-roy2026rag"></a>**RAG for Optimization & CP Modeling**<br>Prateek Roy; Akash Singirikonda | 摘要依据：2608.00015v1<br>每组评测仅使用 25 个留出查询、一个基座模型；不将报告的提升外推为完整公开基准结果。LangChain 是依赖，不当作本方法实现；未核到官方代码或语料下载。 |
| <a id="paper-lian2026reloop"></a><a id="paper-liang2026reloop"></a>**ReLoop / RetailOpt-190**<br>Lian, Junbo Jacob; Sun, Yujun; Chen, Huiling; Zhang, Chaoyu; Qin, Hanzhang; Teo, Chung-Piaw | 摘要依据：2602.15983v6<br>按 arXiv v6（2026-10-12）记录。NeurIPS 官方日程列出六位作者及 2026-12-08 海报，确认接收，待正式出版；RetailOpt-190 的 HF 与 GitHub 入口已确认。行为扰动测试提供诊断证据，不等同完整语义正确性证明。 |
| <a id="paper-zhang2026retailbench"></a>**RetailBench**<br>Zhang, Linghua; Wang, Jun; Wu, Jingtong; Zhang, Zhisong | 摘要依据：2603.16453v3<br>RetailBench: Benchmarking Long Horizon Reasoning and Coherent Decision Making of LLM Agents in Realistic Retail Environments [![版本][badge-159]][resource-553]：历史题名；当前采用原文新题名<br>当前标题与历史记录不同；环境支持长周期仿真，但论文报告的评测周期与环境最大能力不能混用。未将同名 HF 数据自动当作官方发布。 |
| <a id="paper-rlvrpagents2026"></a>**RLEA**<br>Chen, Yi; Yu, Zikang; Wang, Jiahai; Chen, Jinbiao; Zhou, Jianpeng; Zhang, Zizhen | 摘要依据：2609.00859v1<br>原文 Zenodo 地址当前文件为 Appendix_RELA.pdf，按附录展示，不当作训练代码、数据或权重。 最新 Zenodo 20484739 也仅列两份附录 PDF。 |
| <a id="paper-ma2025sacopt"></a>**SAC-Opt**<br>Zhang, Yansen; Kang, Qingcan; Chen, Yujie; Wang, Yufei; Han, Xiongwei; Zhong, Tao; Yuan, Mingxuan; Ma, Chen | 摘要依据：2510.05115v3<br>该方法的语义锚点检查与 SOVER 的 SMT 编码保证不同；ICML 2026 正式 proceedings 已确认。 |
| <a id="paper-strategyaware2026"></a>**SAGE (Strategy-Aware Modeling)**<br>Ruiqing Zhao; Fengzhi Li; Yuan Zuo; Rui Liu; Yansong Liu; Yunfei Ma; Fanyu Meng; Junlan Feng | 摘要依据：2605.02545v1<br>Strategy-Aware Optimization Modeling with Reasoning LLMs [![版本][badge-159]][resource-188]：预印本版本；正式引文按 proceedings 元数据；作者：Ruiqing Zhao; Fengzhi Li; Yuan Zuo; Rui Liu; Yansong Liu; Yunfei Ma; Fanyu Meng; Junlan Feng<br>与割不等式生成的 SAGE / 原 EvoCut 为不同论文，简称、作者与仓库分别展示。未核到对应学生模型权重入口。 |
| <a id="paper-sdrl2026"></a>**SDRL**<br>Shihao Zhang; Weiting Liu; Siyu Shao; Yitian Chen; Jianfeng Feng; Dongdong Ge; Yinyu Ye | 摘要依据：2609.34427v1<br>GitHub 当前发布基准推理代码；4B HF 有可见 safetensors，32B 页面目前只有模型卡，不能称权重已开放。同作者 GACC-Bench 不自动归属此论文。 |
| <a id="paper-lange2026shinka"></a>**ShinkaEvolve**<br>Robert Lange; Yuki Imajuku; Edoardo Cetin | 摘要依据：2509.19349v1<br>ShinkaEvolve: Towards Open-Ended And Sample-Efficient Program Evolution [![版本][badge-159]][resource-445]：预印本版本；正式引文按 proceedings 元数据；作者：Robert Tjarko Lange; Yuki Imajuku; Edoardo Cetin<br>bandit 选择调用哪个 LLM，不等于训练了其权重；当前仓库功能包含论文后的扩展，不混用各版本实验描述。 |
| <a id="paper-smartgrid2026"></a>**Smart Grids Agentic AI Tutorial**<br>Rojas, Daniela; Albassam, Abdulwahab; Leung, Aidan G.; Ngo, Jett; Luo, Ryan; Quawas, Peter R.; Kim, Junpyung; Liang, Kangkai; Nanavati, Mansi; Mai, Jonathan; Tsai, Meng-Chi; Tsai, Yun-Tong; Chen, Yize; Shi, Yuanyuan | 摘要依据：2607.18147v1 |
| <a id="paper-li2025smilo"></a>**SMILO**<br>Li, Qingyang; Zhang, Lele; Mak-Hau, Vicky | 摘要依据：2511.02364v1<br>Crossref 确认期刊版于 2026-05-03 在线发表，沿用历史 2025 ID。原文匿名代码链接返回 403，无法确认内容，资源留空。 |
| <a id="paper-solid2026"></a>**SOLID**<br>Zhu, Rui; Cao, Minglong; Zhou, Chenyu; Lin, Jianghao; Ge, Dongdong | 摘要依据：2609.09957v1<br>多数目标簇是伪参考，不等同已认证正确答案。官方代码与模型由作者主页建立关联；Qwen3 与 StepORLM checkpoint 分开，不混合两者的指标。JamesX421 和第三方量化未因同名自动标为作者发布。 |
| <a id="paper-bhattacharyya2026sover"></a>**SOVER / NLEquiv-150**<br>Bhattacharyya, Swapnil; Baranwal, Mayank | 摘要依据：2609.00728v1<br>保证依赖解析、候选映射及编码假设；Z3 的线性／混整数核验与 dReal 的容差相关非线性核验分开。仓库的数值诊断模式不是 SMT 证明；不将公式间核验写成自然语言题意的完备正确性证明。<br>EquivaFormulation（使用）：论文使用的外部评测数据，不是 SOVER 的新发布。<br>NLP4LP（使用）：论文使用的外部评测数据，不是 SOVER 的新发布。 |
| <a id="paper-lai2026specahd"></a>**SpecAHD**<br>Kezhao Lai; Yutao Lai; Hai-Lin Liu | 摘要依据：2607.23676v1<br>贪心近似保证只针对固定上层程序、修复任务和候选池下的库选择，不是整体路由解的全局近似比。未核到官方代码或模型入口。 |
| <a id="paper-spo2026"></a>**SPO**<br>Xinyi Ke; Kai Li; Junliang Xing; Yifan Zhang; Jian Cheng | 摘要依据：2609.31179v1<br>正文明确包含 LLM 参数更新；不是仅用进化算法修改程序。未核到官方训练代码或微调权重入口。 |
| <a id="paper-zhou2026steporlm"></a>**StepORLM**<br>Zhou, Chenyu; Xu, Tianyi; Lin, Jianghao; Ge, Dongdong | - |
| <a id="paper-text2model2026"></a>**Text2Model**<br>Kadioglu, Serdar; Uppuluri, Karthik; Singirikonda, Akash | 摘要依据：2604.12955v3<br>arXiv 注记列 AAAI 2025 Bridge Program 与 CPAIOR 2026 Master Class，仅表明相关活动，不能据此标为 Workshop 论文或主会接收。作者门户将 Text2Zinc 原论文与 Text2Model 分列；复用既有数据，不另计新基准。Learn2Zinc 模型属于后续独立工作，未归入本论文权重资源。 |
| <a id="paper-chen2026tide"></a>**TIDE**<br>Chentong Chen; Mengyuan Zhong; Ye Fan; Jialong Shi; Jianyong Sun | 摘要依据：2601.21239v2<br>这里的 tuning 是启发式数值参数优化，不是对 LLM 权重微调；未核到官方代码或模型入口。 |
| <a id="paper-verisimpl2026"></a>**VeriSimpl**<br>Rahman, Sumaya Abdul; Cuellar, Seckhen Ariel Andrade; Raissov, Ghani; Raza, Mohammad | 摘要依据：2607.20474v2<br>正式引文为 PMLR 306:103091–103123。PMLR Software 指向 suabar/VeriSimple，当前仅有 README，未作为已发布实现。方法摘要按 arXiv v2；简化诊断和高精度自验证信号不等同形式化正确性证明。<br>官方项目（仅 README）：页面目前仅有项目声明，没有实现文件；不能计为代码已发布。 |
| <a id="paper-vrpagent2025"></a>**VRPAgent**<br>André Hottung; Federico Berto; Chuanbo Hua; Nayeli Gast Zepeda; Daniel Wetzel; Michael Römer; Haoran Ye; Davide Zago; Michael Poli; Stefano Massaroli; Jinkyoo Park; Kevin Tierney | 摘要依据：2510.07073v2<br>TMLR 2026 年 10 月正式清单及 BibTeX 已确认。作者仓库当前是 generated heuristics / sample populations 的早期发布，按演化结果展示，不标完整 Agent 搜索框架已开放。框架约束与一般代码的形式化证明分开。<br>Generated Operators：官方早期发布：生成的启发式与样例种群；未包含完整发现流程。 |
| <a id="paper-zhao2025aimbench"></a>**AIM-Bench**<br>Zhao, Xuhua; Xie, Yuxuan; Chen, Caihua; Sun, Yuxiang | 摘要依据：2508.11416v1 |
| <a id="paper-alas2025"></a>**ALAS**<br>Edward Y. Chang; Longling Geng | 摘要依据：2505.12501v1<br>ACID-like 是框架设计目标，不据此声称一般 LLM 规划具备数据库事务保证。未将后续 ALAS / SagaLLM 的不同稿件或同作者代码自动归为本版本实现。 |
| <a id="paper-novikov2025alphaevolve"></a>**AlphaEvolve**<br>Novikov, Alexander; Vũ, Ngân; Eisenberger, Marvin; Dupont, Emilien; Huang, Po-Sen; Wagner, Adam Zsolt; Shirobokov, Sergey; Kozlovskii, Borislav; Ruiz, Francisco J. R.; Mehrabian, Abbas; Kumar, M. Pawan; See, Abigail; Chaudhuri, Swarat; Holland, George; Davies, Alex; Nowozin, Sebastian; Kohli, Pushmeet; Balog, Matej | 未找到本论文完整系统的官方开源实现；DeepMind 提供的结果与问题集合是相关资源。 |
| <a id="paper-kong2025alphaopt"></a>**AlphaOPT**<br>Kong, Minwei; Qu, Ao; Guo, Xiaotong; Ouyang, Wenbin; Jiang, Chonghe; Zheng, Han; Ma, Yining; Zhuang, Dingyi; Tang, Yuhan; Li, Junyi; Wang, Shenhao; Koutsopoulos, Haris; Wang, Hai; Wu, Cathy; Zhao, Jinhua | 摘要依据：2510.18428v4<br>NeurIPS 2025 页面明确为 ScaleOpt Workshop；当前 arXiv 为后续修订，作者列表与 Workshop 页面可能不同，采用当前 arXiv 元数据。 |
| <a id="paper-li2025ars"></a>**ARS / RoutBench**<br>Li, Kai; Liu, Fei; Wang, Zhenkun; Tong, Xialiang; Han, Xiongwei; Yuan, Mingxuan; Zhang, Qingfu | arXiv comments 提到作者讨论，当前按已打开的作者列表记录；GitHub 数据版本与正文版本需分别固定。 |
| <a id="paper-askclarify2026"></a>**Ask, Clarify, Optimize**<br>Duan, Yaqi; Hu, Yichun; Jiang, Jiashuo | 摘要依据：2601.00121v1<br>正文称发布合并后的 Human Imitator checkpoint，但有限检索未定位到可核实下载地址；不猜测模型 ID。 |
| <a id="paper-astorga2025autoformulation"></a>**Autoformulation**<br>Nicolás Astorga; Tennison Liu; Yuanzhang Xiao; Mihaela Van Der Schaar | - |
| <a id="paper-sim2025beyondhype"></a>**Beyond the Hype: Bin Packing**<br>Sim, Kevin; Renau, Quentin; Hart, Emma | 摘要依据：2501.11411v1 |
| <a id="paper-vanstein2025blade"></a>**BLADE**<br>van Stein, Niki; Kononova, Anna V.; Yin, Haoran; Bäck, Thomas | 摘要依据：2504.20183v1<br>GECCO 2025 Workshop / Companion 正式发表，不写成 GECCO 主会论文。当前仓库 IOH-BLADE 包含后续扩展，不混用不同版本功能与实验数字。 |
| <a id="paper-wang2025bppsearch"></a>**BPP-Search / StructuredOR**<br>Teng Wang; Wing Yin Yu; Zhenqi He; Zehua Liu; Hailei Gong; Han Wu; Xiongwei Han; Wei Shi; Ruifeng She; Fangzhou Zhu; Tao Zhong | ACL 摘要直接给出官方 GitHub/HF；HF 页面存在，但数据预览报告 FeaturesError，未验证数据加载和代码运行。 |
| <a id="paper-kaleta2025cdss"></a>**C-DSS**<br>Mariusz Kaleta | 实证范围集中于建模与编码；更广的可视化、解释和编排生态属于架构愿景，不当作已经完整部署的系统或通用基准。未核到官方实现。 |
| <a id="paper-calm2025storm"></a>**CALM / STORM**<br>Tang, Zhengyang; Ye, Zihan; Huang, Chenyu; Huang, Xuhan; Li, Chengpeng; Li, Sihang; Chen, Guanhua; Yan, Ming; Wang, Zizhuo; Zha, Hongyuan; Liu, Dayiheng; Wang, Benyou | 摘要依据：2510.04204v1<br>与算法共同演化的 CALM 是不同论文。原文注记为 work in progress；未从同名 STORM 模型中推断官方发布。 |
| <a id="paper-bomer2025emerging"></a>**CEoH**<br>Thomas Bömer; Nico Koltermann; Max Disselnmeyer; Laura Dörr; Anne Meyer | 摘要依据：2503.03350v1<br>预印本注记为 LION19 在审，尚未确认正式出版记录，未据此标记接收或发表。 |
| <a id="paper-lawless2024cuts"></a>**Cold-Start Separator Configuration**<br>Lawless, Connor; Li, Yingxi; Wikum, Anders; Udell, Madeleine; Vitercik, Ellen | 摘要依据：2412.12038v2<br>正式版本为 CPAIOR 2025, pp. 51–69；ID 保留预印本年份2024。代码入口由原文提供。 |
| <a id="paper-peering2025"></a>**Component-Level Evaluation**<br>Refai, Dania; Ahmed, Moataz | 摘要依据：2510.16943v1 |
| <a id="paper-michailidis2025cpbench"></a>**CP-Bench / DCP-Bench-Open**<br>Michailidis, Kostis; Tsouros, Dimos; Guns, Tias | 摘要依据：2506.06052v2（原版元数据）；扩展版单独关联<br>CP-Bench: Evaluating Large Language Models for Constraint Modelling [![版本][badge-159]][resource-218]：ECAI 2025，DOI 已核<br>DCP-Bench-Open: Evaluating LLMs for Constraint Modelling of Discrete Combinatorial Problems [![版本][badge-159]][resource-219]：under review（原文 comments）<br>原 CP-Bench 已归档，HF 卡指向 DCP-Bench-Open。旧 LLM-CP-Modeling 地址返回 404，改用原版 CP-Bench 与当前扩展仓库；两个版本不混用性能数字。 正式发表状态对应 CP-Bench 原版；DCP-Bench-Open v3 的在投说明仅属于扩展版本。 |
| <a id="paper-daopt2025"></a>**DAOpt / OptU**<br>Zhu, WenZhuo; Cui, Zheng; Lu, Wenhan; Liu, Sheng; Zhao, Yue | 摘要依据：2511.11576v1<br>原文声明匿名代码入口，但无法确认当前发布内容，资源留空；未将预印本记为 NeurIPS 主会发表。 |
| <a id="paper-dheevo2025"></a>**DHEvo**<br>Zhang, Zhihao; Li, Siyuan; Li, Chenxi; Liu, Feifan; Chen, Mengjing; Li, Kai; Zhong, Tao; An, Bo; Liu, Peng | 摘要依据：2507.15615v1<br>数据—算法共同演化用于启发式发现，不据此推断进行了 LLM 权重训练或发布了新基准。 |
| <a id="paper-dinn2025"></a>**DINN**<br>Hwang, Yoontae; Kong, Yaxuan; Zohren, Stefan; Lee, Yongjae | 摘要依据：2502.00828v1<br>正文旧匿名代码页直接请求为 403；作者仓库公开实现可访问。数据需通过 WRDS 账号取得，未把下载脚本当作公开数据集或公开模型权重。<br>资源：作者名 Yoontae Hwang 对应的仓库，README 声明原始 PyTorch 实现并引用同名论文。 |
| <a id="paper-wasserkrug2024manifesto"></a><a id="paper-wasserkrug2025aaai"></a>**DOCP Research Manifesto**<br>Segev Wasserkrug; Leonard Boussioux; Dick Den Hertog; Farzaneh Mirzazadeh; Ş. İlker Birbil; Jannis Kurtz; Donato Maragno | 摘要依据：2402.16269v1<br>From Large Language Models and Optimization to Decision Optimization CoPilot: A Research Manifesto [![版本][badge-159]][resource-224]：2024 早期详细版本；正式版脚注 1 确认关系<br>Enhancing Decision Making Through the Integration of Large Language Models and Operations Research Optimization [![版本][badge-161]][resource-223]：AAAI 2025 正式版<br>AAAI 正式版第 2 页脚注 1 明确称 2024 Manifesto 是本文的较早版本；合并为一个 ID，保留题名、版本与原记录。 |
| <a id="paper-dpdlm2025"></a>**DPLM / DP-Bench**<br>Zhou, Chenyu; Yang, Jingyuan; Xin, Linwei; Chen, Yitian; He, Ziyan; Ge, Dongdong | 摘要依据：2507.11737v2<br>正文、作者主页与有限检索未定位到可核实的代码、DP-Bench 下载或 DPLM 权重；HF 同名蛋白质模型不关联本论文。 |
| <a id="paper-jiang2025droc"></a>**DRoC**<br>Xia Jiang; Yaoxin Wu; Chenhao Zhang; Yingqian Zhang | - |
| <a id="paper-viktorin2025ease"></a>**EASE**<br>Adam Viktorin; Tomas Kadavy; Jozef Kovac; Michal Pluhacek; Roman Senkerik | 摘要依据：2509.18108v1<br>框架支持算法以外的生成任务，按邻近平台展示；未将其误标新 OR 基准或训练模型。 |
| <a id="paper-luo2025efs"></a>**EFS**<br>Chen, Jiandong; Luo, Haochen; Zhang, Yuan; Liu, Chen; Zhang, Qingfu | 摘要依据：2507.17211v2<br>题名和方法采用当前修订版；原文引用的 ReEvo 是相关方法，不能作为 EFS 官方实现。未确认 EFS 代码或数据入口。 |
| <a id="paper-zhou2024elecbench"></a>**ElecBench**<br>Xiyuan Zhou; Huan Zhao; Yuheng Cheng; Gaoqi Liang; Guolong Liu; Wenxuan Liu; Yan Xu; Junhua Zhao | 摘要依据：2407.05365v2<br>ElecBench: a Power Dispatch Evaluation Benchmark for Large Language Models [![版本][badge-159]][resource-555]：预印本版本；作者：Zhou, Xiyuan; Zhao, Huan; Cheng, Yuheng; Cao, Yuji; Liang, Gaoqi; Liu, Guolong; Liu, Wenxuan; Xu, Yan; Zhao, Junhua<br>官方仓库明确为部分开源，仅展示公开测试子集。正式 PESGM 2025 元数据与预印本的题名、作者列表有差异，分别保留；未把另一个同名期刊 DOI 自动当作扩展版。 |
| <a id="paper-zhang2025decisioninfo"></a>**EOR / Decision Information**<br>Zhang, Yansen; Kang, Qingcan; Yu, Wing Yin; Gong, Hailei; Fu, Xiaojin; Han, Xiongwei; Zhong, Tao; Ma, Chen | 摘要依据：2502.09994v1 |
| <a id="paper-zhai2025equivamap"></a>**EquivaMap**<br>Haotian Zhai; Connor Lawless; Ellen Vitercik; Liu Leqi | - |
| <a id="paper-ucfunsearch2025"></a>**FunSearch for Unit Commitment**<br>Lv, Junjin; Cui, Chenggang; Zhang, Shaodi; Chen, Hui; Gong, Chunyang; Liu, Jiaming | 摘要依据：2506.12495v1 |
| <a id="paper-globalconstraint2025"></a>**Gala**<br>Cai, Junyang; Kadioglu, Serdar; Dilkina, Bistra | 摘要依据：2509.08970v2<br>Text2Model 官方仓库明确将 gala 策略关联本论文；该仓库是共享平台实现，不将 Learn2Zinc 模型或 Text2Zinc 原始数据计成本论文的新发布。 |
| <a id="paper-yang2025heuragenix"></a>**HeurAgenix**<br>Xianliang Yang; Ling Zhang; Haolong Qian; Lei Song; Jiang Bian | 摘要依据：2506.15196v2<br>官方下载脚本确认 HF 实例集的归属，包含既有 CO 数据；不称其为首次提出的新基准，未核到微调选择器权重。 |
| <a id="paper-dat2024hsevo"></a>**HSEvo**<br>Pham Vu Tuan Dat; Long Doan; Huynh Thi Thanh Binh | 摘要依据：2412.14995v1<br>HSEvo: Elevating Automatic Heuristic Design with Diversity-Driven Harmony Search and Genetic Algorithm Using LLMs [![版本][badge-159]][resource-472]：预印本版本；正式引文按 DOI 注册信息；作者：Pham Vu Tuan Dat; Long Doan; Huynh Thi Thanh Binh |
| <a id="paper-zhang2025instspechh"></a>**InstSpecHH**<br>Shaofeng Zhang; Shengcai Liu; Ning Lu; Jiahao Wu; Ji Liu; Yew-Soon Ong; Ke Tang | 摘要依据：2506.00490v3<br>正文的可选神经分类器训练不是 LLM SFT。原文仍称 code and data will be made publicly available；有限检索未确认实际发布入口，不把未来声明当作已有下载。 |
| <a id="paper-xie2025llmns"></a>**LHNS**<br>Zhuoliang Xie; Fei Liu; Zhenkun Wang; Qingfu Zhang | 搜索对象是启发式程序，不自动归为对 VRP 解进行 destroy–repair 的 LNS。元数据和方法摘要由 IEEE、作者机构页面与 LLM4AD 模块交叉核对；未取得 IEEE PDF 正文。 |
| <a id="paper-vanstein2024llamea"></a>**LLaMEA**<br>van Stein, Niki; Bäck, Thomas | IEEE TEVC 在线发表为 2024，卷期版为 2025；本条按卷期 2025。作者文档给出完整引文。 |
| <a id="paper-liu2025fitness"></a>**LLM Algorithm-search Fitness Landscapes**<br>Fei Liu; Qingfu Zhang; Jialong Shi; Xialiang Tong; Kun Mao; Mingxuan Yuan | 摘要依据：2504.19636v3 |
| <a id="paper-vanstein2025behaviour"></a>**LLM Heuristic Behaviour-space Analysis**<br>Niki van Stein; Haoran Yin; Anna V. Kononova; Thomas Bäck; Gabriela Ochoa | 摘要依据：2507.03605v1<br>Zenodo 发布一个 behaviour_metrics.py 文件，按行为指标代码展示，不标完整实验数据或新基准下载。 |
| <a id="paper-cetinkaya2025mipsmtt"></a>**LLM-discovered EDDC / MDDC**<br>İbrahim Oğuz Çetinkaya; İ. Esra Büyüktahtakın; Parshin Shojaee; Chandan K. Reddy | 摘要依据：2510.24013v1 |
| <a id="paper-ye2025llmlns"></a>**LLM-LNS**<br>Huigen Ye; Hua Xu; An Yan; Yaoyang Cheng | - |
| <a id="paper-llmsuc2025"></a>**LLM-SUC**<br>Ren, Xinxing; Lai, Chun Sing; Taylor, Gareth; Guo, Zekun | 摘要依据：2502.10557v2<br>方法说明采用 arXiv v2；不同版本的成本与削负荷统计不同，不混用性能数字。 |
| <a id="paper-xiao2025survey"></a>**LLM4OR Survey**<br>Xiao, Ziyang; Xie, Jingrong; Xu, Lilin; Guan, Shisi; Zhu, Jingyan; Han, Xiongwei; Fu, Xiaojin; Yu, WingYin; Wu, Han; Shi, Wei; Kang, Qingcan; Duan, Jiahui; Zhong, Tao; Yuan, Mingxuan; Zeng, Jia; Wang, Yuan; Chen, Gang; Zhang, Dongxiang | 配套目录提供 ComplexOR、IndustryOR、Mamo、NL4LP、NL4Opt、ReSocratic 的清洗或错误标注材料。属于既有基准的修订评测资源，不作为这些基准的首次提出。<br>Cleaned Benchmarks：既有基准的错误标注 / 清洗材料，含 ComplexOR、IndustryOR、Mamo、NL4LP、NL4Opt、ReSocratic；不是这些原始基准的首次发布。 |
| <a id="paper-jiang2025e2eco"></a>**LLMCoSolver / E2E CO Solver**<br>Xia Jiang; Yaoxin Wu; Minshuo Li; Zhiguang Cao; Yingqian Zhang | 摘要依据：2509.16865v1<br>Large Language Models as End-to-end Combinatorial Optimization Solvers [![版本][badge-159]][resource-540]：预印本版本；正式引文按 proceedings 元数据；作者：Xia Jiang; Yaoxin Wu; Minshuo Li; Zhiguang Cao; Yingqian Zhang<br>代码和 Google Drive 的 SFT / RL 数据已核；未找到可确认的 HF 权重入口，不附基础 Qwen 权重冒充本工作模型。 |
| <a id="paper-jiang2025llmopt"></a>**LLMOPT**<br>jiang, caigao; Shu, Xiang; Qian, Hong; Lu, Xingyu; ZHOU, JUN; Zhou, Aimin; Yu, Yang | 原 caigaojiang 仓库已重定向至 antgroup/LLMOPT；当前公开 HF 模型为 Qwen2.5-14B 版本，原论文训练基座包含 Qwen1.5，不能视为完全相同的实验 checkpoint。 |
| <a id="paper-dsmco2024"></a>**LLMs for DSM Sequencing**<br>Shuo Jiang; Min Xie; Jianxi Luo | 摘要依据：2411.12571v1<br>Large Language Models for Combinatorial Optimization of Design Structure Matrix [![版本][badge-159]][resource-558]：预印本版本；正式引文按 DOI 注册信息；作者：Shuo Jiang; Min Xie; Jianxi Luo<br>主记录采用 ICED25 正式版本。后续同题变体缺少明确版本关联声明，未混用；未确认公开代码或数据入口。 |
| <a id="paper-talebi2025stochastic"></a>**LLMs for Stochastic Modeling**<br>Talebi, Amirreza | 摘要依据：2508.17200v3<br>公开评测案例含文献改编，不将其误写成新命名基准。仓库 README 主要引用已有 Chain-of-Experts，关联依据采用本论文的数据与代码声明。 |
| <a id="paper-wang2025lor"></a>**LLMs in OR: Methods & Challenges**<br>Yang Wang; Kai Li | 摘要依据：2509.18180v3 |
| <a id="paper-llmbl2025"></a>**LLM–Black-Litterman**<br>Lee, Youngbin; Kim, Yejin; Kim, Juhyeong; Kim, Suin; Lee, Yongjae | 摘要依据：2504.14345v2<br>主办方 accepted-paper 名单列有同题论文及五位作者，确认为 Financial AI Workshop 展示，不标为 CIKM 主会或正式主会论文集。代码和数据为原文明确链接的仓库。 |
| <a id="paper-yuan2025magts"></a>**MA-GTS / G-REAL**<br>Yuan, Zike; Liu, Ming; Wang, Hui; Qin, Bing | arXiv v2 与会议摘要的 G-REAL 数字不同，不混用性能数字。 |
| <a id="paper-huang2024mamo"></a>**Mamo**<br>Huang, Xuhan; Shen, Qingning; Hu, Yan; Gao, Anningzhe; Wang, Benyou | ID 保留历史年份 2024 以维持引用稳定，year 使用正式发表年份 2025。<br>Dataset（第三方镜像）：数据卡明确声明直接复制 Mamo 的 EasyLP / ComplexLP，并调整字段名；属于第三方适配镜像，不是原作者发布。 |
| <a id="paper-zheng2025mctsahd"></a>**MCTS-AHD**<br>Zhi Zheng; Zhuoliang Xie; Zhenkun Wang; Bryan Hooi | - |
| <a id="paper-yao2025meoh"></a>**MEoH**<br>Shunyu Yao; Fei Liu; Xi Lin; Zhichao Lu; Zhenkun Wang; Qingfu Zhang | 摘要依据：2409.16867v2<br>Multi-objective Evolution of Heuristic Using Large Language Model [![版本][badge-159]][resource-493]：预印本版本；正式引文按 DOI 注册信息；作者：Shunyu Yao; Fei Liu; Xi Lin; Zhichao Lu; Zhenkun Wang; Qingfu Zhang<br>LLM4AD 的 meoh 模块明确引用本论文；它是共享平台内的具体实现，不是本论文新建的独立平台。 |
| <a id="paper-li2025milpevolve"></a>**MILP-Evolve**<br>Li, Sirui; Kulkarni, Janardhan; Menache, Ishai; Wu, Cathy; Li, Beibin | 代码在 microsoft/OptiGuide 的 milp-evolve 子目录；microsoft/MILP-Evolve 是独立数据卡仓库，未将其当作完整算法实现。 |
| <a id="paper-liu2025mmagent"></a>**MM-Agent / MM-Bench（数学建模）**<br>Fan LIU; Zherui Yang; Cancheng Liu; Tianrui Song; Xiaofeng Gao; Hao Liu | 摘要依据：2505.14148v1<br>MM-Agent: LLM as Agents for Real-world Mathematical Modeling Problem [![版本][badge-159]][resource-247]：预印本版本；正式引文采用 proceedings 元数据；作者：Fan Liu; Zherui Yang; Cancheng Liu; Tianrui Song; Xiaofeng Gao; Hao Liu<br>这是广义数学建模资源，与多模态同名 MM-Bench 区分。比赛奖项对应辅助学生团队，不能写成自主 Agent 获奖。2026 Expert Skills 和升级 Demo 是后续发布，不混入 2025 论文实验。<br>HF Demo：在线演示入口，服务状态不等同功能或实验结果验证。 |
| <a id="paper-qian2025modelingagent"></a>**ModelingAgent / ModelingBench**<br>Cheng Qian; Hongyi Du; Hongru Wang; Xiusi Chen; Yuji Zhang; Avirup Sil; ChengXiang Zhai; Kathleen McKeown; Heng Ji | 摘要依据：2505.15068v1<br>ModelingAgent: Bridging LLMs and Mathematical Modeling for Real-World Challenges [![版本][badge-159]][resource-251]：预印本版本；正式引文采用 proceedings 元数据；作者：Cheng Qian; Hongyi Du; Hongru Wang; Xiusi Chen; Yuji Zhang; Avirup Sil; Chengxiang Zhai; Kathleen McKeown; Heng Ji<br>范围含数据分析、预测、跨学科建模及报告，不等同纯运筹优化基准。评分包含 LLM 评审，与求解器目标值／可行性检测口径不同。 |
| <a id="paper-moid2025"></a>**MOID**<br>Li, Kai; Zheng, Ruihao; Hao, Xinye; Wang, Zhenkun | 摘要依据：2508.03406v1<br>正文给出的仓库当前仅含 50 VRP&100 solution.json 与极简 README，按诊断数据展示，不标完整求解与诊断实现。 |
| <a id="paper-xie2025murka"></a>**MURKA**<br>Wantong Xie; Yi-Xiang Hu; Jieyang Xu; Feng Wu; Xiangyang Li | 页码来源存在冲突，暂不列页码；会议年份采用2025，网页上线日期不等同会议年份。 |
| <a id="paper-tran2025llmneural"></a>**NCO-LLM for VRP**<br>Cong Dao Tran; Quan Nguyen-Tri; Huynh Thi Thanh Binh; Hoang Thanh-Tung | 会议入口明确为 ICLR 2025 Towards Agentic AI for Science Workshop。微调对象是 NCO 策略而非 LLM，因此不标 LLM SFT；仓库提供代码，但未核到独立作者 checkpoint 下载。 |
| <a id="paper-thind2025optimai"></a>**OptimAI**<br>Thind, Raghav; Sun, Youran; Liang, Ling; Yang, Haizhao | 摘要依据：2504.16918v3 |
| <a id="paper-zhang2025optimind"></a><a id="paper-chen2025optimind"></a>**OptiMind**<br>Zhang, Xinzhi; Chen, Zeyi; Zope, Humishka; Barbalho, Hugo; Mellou, Konstantina; Molinaro, Marco; Kulkarni, Janardhan; Menache, Ishai; Li, Sirui | microsoft/OptiGuide 为包含多项工作的 monorepo；通过 Microsoft 发布的 OptiMind-SFT 模型卡关联。只列已确认的模型入口，不把其他 monorepo 数据归给本论文。 |
| <a id="paper-liu2025optitree"></a>**OptiTree**<br>Liu, Haoyang; Wang, Jie; Cai, Yuyang; Han, Xiongwei; Kuang, Yufei; Hao, Jianye | - |
| <a id="paper-lima2025optitrust"></a>**OptiTrust**<br>Lima, Vinicius; Phan, Dzung T.; Kalagnanam, Jayant; Patel, Dhaval; Zhou, Nianjun | 摘要依据：2508.03117v1<br>同名 charguer/optitrust 是另一项源码变换项目，未作为本论文代码。有限检索未找到可确认的官方权重、代码或数据下载入口。 |
| <a id="paper-lu2025optmath"></a>**OptMATH**<br>Hongliang Lu; Zhonglin Xie; Yaoyu Wu; Can Ren; Yuxuan Chen; Zaiwen Wen | 采用 PMLR 正式页面关联的 optsuite/OptMATH，以及官方 README 关联的 Aurora-Gem 模型与数据。<br>Model 7B：模型由官方 README 关联，模型卡与 HF 文件入口可访问。<br>Model 32B：模型由官方 README 关联，模型卡与 HF 文件入口可访问。 |
| <a id="paper-zhang2025bwor"></a>**OR-LLM-Agent / BWOR**<br>Zhang, Bowen; Luo, Pengcheng; Yang, Genke; Soong, Boon-Hee; Yuen, Chau | 摘要依据：2503.10009v3 |
| <a id="paper-ding2026orgeval"></a>**ORGEval / Bench4Opt**<br>Wang, Zhuohan; Zhu, Ziwei; Li, Ziniu; Chen, Congliang; Han, Yizhou; Lin, Yufeng; Lin, Zhihang; Gu, Angyang; Hu, Xinglin; Sun, Ruoyu; Ding, Tian | ORGEval: Graph-Theoretic Evaluation of LLMs in Optimization Modeling [![版本][badge-159]][resource-264]：2025<br>Certified Evaluation for LLMs in Optimization Modeling: From Graph Isomorphism to Formulation Isomorphism [![版本（相关）][badge-162]][resource-265]：2026；Poster in Workshop: Combining Theory and Benchmarks；标题与作者有变化；页面摘要同样明确使用 ORGEval 与 Bench4Opt，按相关版本关联，进一步出版关系待核。<br>纠正历史 ICML 2026 主会表述：实际页面标注 workshop poster。ID 沿用历史 2026，year 按已确认的 arXiv 首发 2025。 |
| <a id="paper-huang2025orlm"></a>**ORLM**<br>Huang, Chenyu; Tang, Zhengyang; Hu, Shixi; Jiang, Ruoqing; Zheng, Xin; Ge, Dongdong; Wang, Benyou; Wang, Zizhuo | 期刊状态及卷期采用出版社记录；作者顺序采用 arXiv 元数据，与仓库示例引文存在差异。 |
| <a id="paper-ormind2025"></a>**ORMind**<br>Wang, Zhiyuan; Chen, Bokui; Huang, Yinya; Cao, Qingxing; He, Ming; Fan, Jianping; Liang, Xiaodan | 摘要依据：2506.01326v2<br>正式发表在 ACL 2025 Industry Track；仓库区分论文实现与后续扩展，后续模式不对应论文报告数字。 |
| <a id="paper-mostajabdaveh2025orqa"></a>**ORQA**<br>Mostajabdaveh, Mahdi; Yu, Timothy T.; Dash, Samarendra Chandan Bindu; Ramamonjison, Rindranirina; Byusa, Jabo Serge; Carenini, Giuseppe; Zhou, Zirui; Zhang, Yong | 正式 AAAI 2025 页面确认发表；作者名称存在缩写差别，本条按已打开的 arXiv 引文记录，正式页列 Timothy Tin Long Yu / Rindra Ramamonjison。 |
| <a id="paper-ali2025pair"></a>**PAIR**<br>Ali, Shady; Ashraf, Mahmoud; Hegazy, Seif; Salem, Fatty; Mokhtar, Hoda; Gaber, Mohamed Medhat; Alrefaie, Mohamed Taher | 经作者公开介绍中的短链接追踪到 SHIXOOM/PAIR；仓库 README 明确说明用于本论文实验，并链接论文。 |
| <a id="paper-quan2025reeval3d"></a>**Re-evaluating Heuristic Search: 3D Packing**<br>Quan, Guorui; Sun, Mingfei; López-Ibáñez, Manuel | 摘要依据：2509.02297v1 |
| <a id="paper-thach2025redahd"></a>**RedAHD**<br>Nguyen Thach; Aida Riahifar; Nathan Huynh; Hau Chan | 摘要依据：2505.20242v1<br>归约的经验检验不等于所有生成变换均有正确性证明；正文引用的 ReEvo / MCTS-AHD 不作为本工作实现。 |
| <a id="paper-cao2025reflecsched"></a>**ReflecSched**<br>Cao, Shijie; Yuan, Yuan | 摘要依据：2508.01724v3<br>方法采用2026-01-19的 arXiv v3；原文声明的代码地址暂不可用，未列为公开资源入口。 |
| <a id="paper-yang2025resocratic"></a>**ReSocratic / OptiBench**<br>Yang, Zhicheng; Wang, Yiwei; Huang, Yinya; Guo, Zhijiang; Shi, Wei; Han, Xiongwei; Feng, Liang; Song, Linqi; Liang, Xiaodan; Tang, Jing | 旧代码入口重定向至 yangzhch6/PRIVATE-RS，实际为公开可访问仓库。ICLR 页面作者 meta 含 Shi, Shi，与 arXiv 的 Shi, Wei 不同，本条作者统一按 arXiv 记录。 |
| <a id="paper-xu2025roco"></a>**RoCo**<br>Jiawei Xu; Feng-Feng Wei; Wei-Neng Chen | 摘要依据：2512.03762v2<br>协作与种群演化属于程序发现机制，未将其标作语言模型权重训练；未确认官方代码入口。 |
| <a id="paper-yazdani2025evocut"></a>**SAGE / 原 EvoCut**<br>Yazdani, Milad; Mostajabdaveh, Mahdi; Aref, Samin; Zhou, Zirui | 摘要依据：2508.11850v3<br>LLM-Guided Evolution of Symbolic Acceleration Inequality Families for MILP [![版本][badge-159]][resource-504]：2026-10-19 修订，框架名 SAGE<br>EvoCut: Strengthening Integer Programs via Evolution-Guided Language Models [![版本][badge-163]][resource-505]：早期题名 EvoCut；旧代码仓库仍在，原版正文关系待进一步逐版本核对。<br>采用已打开的 v3 摘要与声明：候选不等式经经验可接受性筛选，并无数学有效性证明。旧 EvoCut 与新 SAGE 代码分别保留，未增加独立论文计数。 |
| <a id="paper-chen2025sirl"></a>**SIRL**<br>Chen, Yitian; Xia, Jingfan; Shao, Siyu; Ge, DongDong; Ye, Yinyu | ORLMBenchmark 是作者修订的已有基准集合；它不是所有原始数据集的首次发布，不与 ORLM 的 IndustryOR 原版混计。 |
| <a id="paper-solverllm2025"></a>**SolverLLM**<br>Li, Dong; Zhao, Xujiang; Yu, Linlin; Liu, Yanchi; Cheng, Wei; Chen, Zhengzhang; Chen, Zhong; Chen, Feng; Zhao, Chen; Chen, Haifeng | 摘要依据：2510.16916v2 |
| <a id="paper-abgaryan2025starjob"></a>**Starjob**<br>Abgaryan, Henrik; Cazenave, Tristan; Harutyunyan, Ararat | 摘要依据：2503.01877v2<br>作者仓库的数据链接由 henri24/Starjob 重定向至 mideavalwisard/Starjob。arXiv 有 substantial text overlap 管理员注记。仓库含训练脚本及数据；未确认微调权重入口。Starjob 主要是训练数据，不等同新增独立测试基准。 |
| <a id="paper-wu2025stepopt"></a>**Step-Opt**<br>Yang Wu; Yifan Zhang; Yurong Wu; Yuran Wang; Junkai Zhang; Jian Cheng | 摘要依据：2506.17637v1<br>Step-Opt: Boosting Optimization Modeling in LLMs through Iterative Data Synthesis and Structured Validation [![版本][badge-159]][resource-282]：预印本题名<br>正式版题名已更改，保留旧 arXiv 标题关联。仓库数据和实现位于 Step/ 子目录；未核到官方权重下载入口。 |
| <a id="paper-li2025strcmp"></a>**STRCMP**<br>Xijun Li; Jiexiang Yang; Jinghao Wang; Bo Peng; Jianguo Yao; Haibing Guan | 摘要依据：2506.11057v1<br>STRCMP: Integrating Graph Structural Priors with Language Models for Combinatorial Optimization [![版本][badge-159]][resource-367]：预印本版本；正式引文按 proceedings 元数据；作者：Xijun Li; Jiexiang Yang; Jinghao Wang; Bo Peng; Jianguo Yao; Haibing Guan |
| <a id="paper-abedi2025thinkmath"></a>**Teaching LLMs to Think Mathematically**<br>Mohammad J. Abdel-Rahman; Yasmeen Alslman; Dania Refai; Amro Saleh; Malik A. Abu Loha; Mohammad Yahya Hamed | 摘要依据：2508.18091v1<br>作者为 Mohammad J. Abdel-Rahman 等，历史 ID 保留。未核到该评测语料下载入口，不给数据集虚构名称或 HF 地址。 |
| <a id="paper-singirikonda2025text2zinc"></a>**Text2Zinc**<br>Singirikonda, Akash; Kadioglu, Serdar; Uppuluri, Karthik | 摘要依据：2503.10642v1<br>作者报告页明确标 Text2Zinc @ AAAI 2025 为 Invited Talk；邀请报告不作为主会或 Workshop 论文接收证据。HF 数据集由原文与作者门户关联。后续 Text2Model（text2model2026）复用本数据并扩展 Copilot / 编辑器 / 排行榜；门户内 Learn2Zinc 模型也不归入本论文权重资源。 |
| <a id="paper-nl2ps2025"></a>**Validation-in-the-Loop Power Modeling**<br>Hu, Yunkai; Zhao, Tianqiao; Yue, Meng | 摘要依据：2508.08147v1 |
| <a id="paper-bridgingviz2025"></a>**Visual Graph Optimization with MLLMs**<br>Jie Zhao; Kang Hao Cheong; Witold Pedrycz | 摘要依据：2501.11968<br>原文任务和对比结果不等于提出新统一 OR 基准；未核到作者代码、数据或微调权重入口。 |
| <a id="paper-parashar2025wiqor"></a>**WIQOR**<br>Aditya Parashar; Ari Kobren; Natalia Kosilova | 摘要依据：Oracle institution-hosted anonymous submission, DOC_ID 4780<br>机构记录列出 ICLR 2025，但未明确接收或 track；机构托管 PDF 仍为匿名投稿稿，不能据此标接收。作者采用具名机构记录；原记录可能访问受限，另提供机构 PDF。未确认公开数据或官方代码入口。<br>Paper PDF：作者机构托管的匿名投稿稿件；首页标 Under review，不能据此认定接收。<br>Institution record：具名机构记录；可能访问受限，另提供机构托管的投稿 PDF。 |
| <a id="paper-deng2024cafa"></a>**CAFA**<br>Haoxuan Deng; Bohao Zheng; Yirui Jiang; Trung Hieu Tran | 会议入口为 NeurIPS 2024 MATH-AI Workshop，不写成主会。作者按官方仓库的论文引文记录；当前代码包含后续整理，不混用其新增模型测试结果。 |
| <a id="paper-xiao2024coe"></a>**Chain-of-Experts**<br>Ziyang Xiao; Dongxiang Zhang; Yangjun Wu; Lilin Xu; Yuan Wang; Xiongwei Han; Xiaojin Fu; Tao Zhong; Jia Zeng; Mingli Song; Gang Chen | OpenReview 网页触发验证，改用 ICLR 正式 proceedings；仓库声明仅提供 ComplexOR 原始版本，完整正式版本发布情况未核。 |
| <a id="paper-jiao2024cityleo"></a>**City-LEO**<br>Jiao, Zihao; Sha, Mengyi; Zhang, Haoyu; Jiang, Xinyu; Qi, Wei | 摘要依据：2406.10958v2<br>原文明确将 City-LEO 代码和数据发布在 HF 的 BTBUzhy/JOC；API 可见数据和 Python 文件。该仓库没有标准 README.md，不能据此判定资源不存在。 |
| <a id="paper-liu2024eoh"></a>**EoH**<br>Fei Liu; Tong Xialiang; Mingxuan Yuan; Xi Lin; Fu Luo; Zhenkun Wang; Zhichao Lu; Qingfu Zhang | - |
| <a id="paper-xing2024lpwp"></a>**Human-aligned LPWP Evaluation**<br>Linzi Xing; Xinglu Wang; Yuxi Feng; Zhenan Fan; Jing Xiong; Zhijiang Guo; Xiaojin Fu; Rindra Ramamonjison; Mahdi Mostajabdaveh; Xiongwei Han; Zirui Zhou; Yong Zhang | 基于既有 NL4Opt 做指标与人工评价实验，不标首次提出新基准；结构得分与表示层面的等价识别不提升为任意 LP / NLP 模型的完整数学等价证明。未核到作者实现下载。 |
| <a id="paper-quan2024invagent"></a>**InvAgent**<br>Quan, Yinzhu; Liu, Zefang | 摘要依据：2407.11384v2 |
| <a id="paper-tang2024itinerary"></a>**ITINERA**<br>Yihong Tang; Zhaokai Wang; Ao Qu; Yihao Yan; Zhaofeng Wu; Dingyi Zhuang; Jushi Kai; Kebing Hou; Xiaotong Guo; Jinhua Zhao; Zhan Zhao; Wei Ma | 摘要依据：2402.07204v5<br>ITINERA: Integrating Spatial Optimization with Large Language Models for Open-domain Urban Itinerary Planning [![版本][badge-159]][resource-294]：预印本版本；作者：Tang, Yihong; Wang, Zhaokai; Qu, Ao; Yan, Yihao; Wu, Zhaofeng; Zhuang, Dingyi; Kai, Jushi; Hou, Kebing; Guo, Xiaotong; Zheng, Han; Luo, Tiange; Zhao, Jinhua; Zhao, Zhan; Ma, Wei<br>正式发表在 EMNLP 2024 Industry Track，KDD UrbComp 的 Workshop 展示不写成 KDD 主会。正式作者列表按 ACL 记录，较预印本不同。 |
| <a id="paper-liu2024llm4ad"></a>**LLM4AD**<br>Liu, Fei; Zhang, Rui; Xie, Zhuoliang; Sun, Rui; Li, Kai; Hu, Qinglong; Guo, Ping; Lin, Xi; Tong, Xialiang; Yuan, Mingxuan; Wang, Zhenkun; Lu, Zhichao; Zhang, Qingfu | - |
| <a id="paper-yu2024deep"></a>**LLM–EA Automated Optimization Insights**<br>He Yu; Jing Liu | 摘要依据：2410.20848v1 |
| <a id="paper-ahmed2024lm4opt"></a>**LM4OPT**<br>Tasnim Ahmed; Salimur Choudhury | 摘要依据：2403.01342v1<br>LM4OPT: Unveiling the Potential of Large Language Models in Formulating Mathematical Optimization Problems [![版本][badge-159]][resource-297]：预印本版本；正式引文按 DOI 注册信息；作者：Tasnim Ahmed; Salimur Choudhury<br>正式 INFOR 版本扩展了小模型比较；未核到官方微调权重。 |
| <a id="paper-mostajabdaveh2024multiagent"></a>**Multi-Stage Modeling & Verification**<br>Mahdi Mostajabdaveh; Timothy T. Yu; Rindranirina Ramamonjison; Giuseppe Carenini; Zirui Zhou; Yong Zhang | 出版社一手原文检索与作者页面确认方法，Crossref 确认出版元数据。NL4Opt 公告提及本论文，但竞赛与 ORQA 资源不自动视为本框架或新评测集的下载入口。 |
| <a id="paper-dakle2023ner4opt"></a>**Ner4Opt**<br>Serdar Kadıoğlu; Parag Pravin Dakle; Karthik Uppuluri; Regina Politi; Preethi Raghavan; SaiKrishna Rallabandi; Ravisutha Srinivasamurthy | Constraints 2024 正式版的第一作者为 Serdar Kadıoğlu，保留历史 dakle2023ner4opt ID；作者仓库另列 CPAIOR 2023 早期版。 |
| <a id="paper-yang2024opro"></a><a id="paper-yang2025opro"></a>**OPRO**<br>Yang, Chengrun; Wang, Xuezhi; Lu, Yifeng; Liu, Hanxiao; Le, Quoc V.; Zhou, Denny; Chen, Xinyun | - |
| <a id="paper-chen2023diagnosing"></a>**OptiChat / Infeasibility Diagnosis**<br>Chen, Hao; Constante-Flores, Gonzalo E.; Li, Can | 摘要依据：2308.12923v1<br>原始预印本为 2023，期刊 DOI 的注册元数据确认 2024 发表；ID 保持稳定。仓库还包含后续 OptiChat 工作，不能混用版本与评测。 |
| <a id="paper-teshnizi2024optimus"></a>**OptiMUS**<br>Ali Ahmaditeshnizi; Wenzhi Gao; Madeleine Udell | 摘要依据：ICML 2024 / OptiMUS v0.2<br>OptiMUS: Optimization Modeling Using MIP Solvers and large language models [![版本][badge-159]][resource-566]：2023；v0.1；2023 预印本，核对至 arXiv v2。；作者：AhmadiTeshnizi, Ali; Gao, Wenzhi; Udell, Madeleine<br>OptiMUS: Scalable Optimization Modeling with (MI)LP Solvers and Large Language Models [![版本][badge-159]][resource-303]：2024；v0.2；本条 ICML 2024 主体，保持主记录作者与引文。；作者：AhmadiTeshnizi, Ali; Gao, Wenzhi; Udell, Madeleine<br>OptiMUS-0.3: Using Large Language Models to Model and Solve Optimization Problems at Scale [![版本][badge-159]][resource-567]：2024；v0.3 相关扩展；作者列表按 arXiv v4（2026-06-26）为六位，包含 Connor Lawless。仓库示例 BibTeX 仍列五位，不据此覆盖当前原文作者；基准与性能不与 ICML 2024 版混用。；作者：AhmadiTeshnizi, Ali; Gao, Wenzhi; Brunborg, Herman; Talaei, Shayan; Lawless, Connor; Udell, Madeleine<br>作者仓库与 arXiv 注记明确关联 v0.1、v0.2、v0.3。主记录采用 ICML 2024 v0.2，v0.3 的六位作者列于相关版本表。NLP4LP 当前下载内容可能含后续扩展，复现实验需固定论文、代码和数据版本。<br>OptiMUS v0.1：作者仓库与原文明确关联的版本；不替代主条目的 ICML 2024 引文和实验范围。<br>OptiMUS v0.3：作者仓库与原文明确关联的版本；不替代主条目的 ICML 2024 引文和实验范围。 |
| <a id="paper-zhang2024optllm"></a>**OptLLM**<br>Jihai Zhang; Wei Wang; Siyan Guo; Li Wang; Fangquan Lin; Cheng Yang; Wotao Yin | 摘要依据：2407.07924v1<br>Solving General Natural-Language-Description Optimization Problems with Large Language Models [![版本][badge-159]][resource-306]：预印本版本；正式引文采用 proceedings 元数据；作者：Jihai Zhang; Wei Wang; Siyan Guo; Li Wang; Fangquan Lin; Cheng Yang; Wotao Yin<br>正式发表于 NAACL 2024 Industry Track。原文试用入口当前可访问，但未测试交互功能；商业试用不等于源码或权重开放。HF 同名 optLLM-small 为另一个 Flan-T5 抽取模型，未关联本论文。<br>MindOpt Trial (International)：作者原文给出的云端试用入口；仅检查页面，未登录或提交任务。<br>MindOpt Trial (CN)：作者原文给出的云端试用入口；仅检查页面，未登录或提交任务。 |
| <a id="paper-tang2024ragdys"></a>**RAGDyS**<br>Tang, Paul Mingzheng; Leong, Kenji Kah Hoe; Shaik, Nowshad; Lau, Hoong Chuin | 摘要依据：2405.06697v1 |
| <a id="paper-wang2024raremip"></a>**Rare MIP Challenges**<br>Wang, Teng; Yu, Wing-Yin; She, Ruifeng; Yang, Wenhan; Chen, Taijie; Zhang, Jianping | 摘要依据：2409.04464v2 |
| <a id="paper-ye2024reevo"></a>**ReEvo**<br>Ye, Haoran; Wang, Jiarui; Cao, Zhiguang; Berto, Federico; Hua, Chuanbo; Kim, Haeyeon; Park, Jinkyoo; Song, Guojie | - |
| <a id="paper-ju2024ttg"></a>**To the Globe / TTG**<br>JU, Da; Jiang, Song; Cohen, Andrew; Foss, Aaron; Mitts, Sasha; Zharmagambetov, Arman; Amos, Brandon; Li, Xian; Kao, Justine T; Fazel-Zarandi, Maryam; Tian, Yuandong | 摘要依据：2410.16456v1<br>未核到官方代码、数据或权重下载；BotUI、Llama 等基础依赖不作为本论文资源。 |
| <a id="paper-liu2023ael"></a>**AEL**<br>Fei Liu; Xialiang Tong; Mingxuan Yuan; Qingfu Zhang | 摘要依据：2311.15249v1<br>与后续 EoH 为相关前作关系；未取得同一论文版本声明，不合并 ID 或自动挂接 EoH 实现。 |
| <a id="paper-alahakoon2023copilot"></a>**AI-Copilot for Business Optimisation**<br>Amarasinghe, Pivithuru Thejan; Nguyen, Su; Sun, Yuan; Alahakoon, Damminda | 摘要依据：2309.13218v5<br>AI-Copilot for Business Optimisation: A Framework and a Case Study in Production Scheduling [![版本][badge-159]][resource-312]：历史题名；当前采用 arXiv v5 题名<br>当前 arXiv v5 已改题名并更新至 2025；沿用初次预印本年份与稳定 ID，旧题名留在版本信息。Artifacts 仓库发布生成公式，不等同训练实现或模型权重。 |
| <a id="paper-synth2023"></a>**CodeT5 Mathematical Program Synthesis**<br>Ganesh Prasath; Shirish Karande | 摘要依据：2304.03287v1<br>CodeT5 为早期小型编码模型。DL4C 官网历史 PDF 的网页缓存可核到同题论文及作者邮箱，仅记为 Workshop 版本，不作为 ICLR 主会接收证明。原 PDF 已失效，仅保留 arXiv 入口。未核到作者权重或代码入口。 |
| <a id="paper-romera2023funsearch"></a>**FunSearch**<br>Romera-Paredes, Bernardino; Barekatain, Mohammadamin; Novikov, Alexander; Balog, Matej; Kumar, M. Pawan; Dupont, Emilien; Ruiz, Francisco J. R.; Ellenberg, Jordan S.; Wang, Pengming; Fawzi, Omar; Kohli, Pushmeet; Fawzi, Alhussein | 按 2023 在线发表年份，后续 Nature 卷期为 2024。官方代码不含 LLM、执行沙箱或完整分布式系统。 |
| <a id="paper-kadioglu2023holygrail"></a>**Holy Grail 2.0**<br>Dimos Tsouros; Hélène Verhaeghe; Serdar Kadıoğlu; Tias Guns | 摘要依据：2308.01589v1<br>原文明确是 position paper；计划中的评测、组件和后续系统不能写成已完成的通用实现，也不附同作者后续项目的模型。 |
| <a id="paper-li2023power"></a>**LLMs for Power Engineering**<br>Li, Ran; Pu, Chuanqing; Tao, Junyi; Li, Canbing; Fan, Feilong; Xiang, Yue; Chen, Sijie | - |
| <a id="paper-li2023synthesizing"></a>**Multi-stage MILP Synthesis**<br>Qingyang Li; Lele Zhang; Vicky Mak-Hau | 摘要依据：2311.15271v1<br>SMILO 正文将本工作作为独立前作引用，未取得同一论文扩展版的明确声明，不仅因作者相同而合并。仓库以数据为主，不标完整实现。 |
| <a id="paper-ramamonjison2023nl4opt"></a>**NL4Opt**<br>Rindranirina Ramamonjison; Timothy Yu; Raymond Li; Haley Li; Giuseppe Carenini; Bissan Ghaddar; Shiqi He; Mahdi Mostajabdaveh; Amin Banitalebi-Dehkordi; Zirui Zhou; Yong Zhang | - |
| <a id="paper-iflytek2023autoformulation"></a>**NL4Opt: Auto-Formulation Approach**<br>Yuting Ning; Jiayu Liu; Longhu Qin; Tong Xiao; Shangzi Xue; Zhenya Huang; Qi Liu; Enhong Chen; Jinze Wu | 摘要依据：2302.04643v1 |
| <a id="paper-wang2023opdnl4opt"></a>**OPD@NL4Opt**<br>Wang, Kangxu; Chen, Ze; Zheng, Jiewen | - |
| <a id="paper-li2023optiguide"></a>**OptiGuide**<br>Li, Beibin; Mellou, Konstantina; Zhang, Bo; Pathuri, Jeevan; Menache, Ishai | 资源为包含多项工作的官方 monorepo；不能把其中后来发布的 OptiMind 权重归为本论文模型。 |
| <a id="paper-ramamonjison2022augmenting"></a>**Auto-formulation (2022)**<br>Rindra Ramamonjison; Haley Li; Timothy Yu; Shiqi He; Vishnu Rengan; Amin Banitalebi-Dehkordi; Zirui Zhou; Yong Zhang | 原始 PDF 首页直接关联 NL4Opt 竞赛代码与数据。数据共1101项，训练 / 开发 / 测试为713 / 99 / 289。与后来 NL4Opt 竞赛报告共享数据谱系，分别保留论文 ID，不视作两个独立数据集。<br>Code & Data（NL4Opt）：论文首页明确给出共享竞赛代码与数据仓库；当前有 generation_data、ner_data 与评测脚本，不据此宣称包含完整交互 UI。 |

[返回目录](#contents)

<a id="classification"></a>

## 分类与阅读说明

每篇论文指定一个主要类别，并按实际贡献标记所有相关模块；跨模块出现不增加论文数量。

- **核心 / 补充 / 探索性：** 核心工作代表主要研究路线、基础方法或重要评测资源；补充工作覆盖具体方法与场景；探索性工作说明与 OR 的相关性。层级用于阅读筛选，不是质量排名。
- **方法与基准：** 同时提出方法和新基准的论文标记两类贡献；仅使用既有基准测试的方法不计为新基准。
- **数据与模型：** 训练数据、评测基准、修订评测数据和模型分别列出。提出模型不表示权重已公开，复用数据不表示首次提出该数据集。
- **训练与程序演化：** 更新 LLM 权重与生成、选择或进化算法程序分开分类；辅助网络或 NCO 策略训练不自动等同 LLM 微调。
- **验证：** 可执行、求解可行、目标值一致、图同构、数学等价和题意符合性分别说明；行为扰动诊断不等同完整正确性证明。
- **资源：** 第三方复现与相关资源单独标记；没有确认入口的资源省略或显示 `-`，不以基础依赖代替论文发布资源。

[返回目录](#contents)

[badge-001]: https://img.shields.io/static/v1?label=HF&message=HF+Weights&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-002]: https://img.shields.io/static/v1?label=HF&message=HF+Model&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-003]: https://img.shields.io/static/v1?label=HF&message=Model+7B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-004]: https://img.shields.io/static/v1?label=HF&message=Model+32B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-005]: https://img.shields.io/static/v1?label=HF&message=Model+Gurobi-7B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-006]: https://img.shields.io/static/v1?label=HF&message=Model+COPT-7B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-007]: https://img.shields.io/static/v1?label=HF&message=Model+Gurobi-32B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-008]: https://img.shields.io/static/v1?label=HF&message=Model+COPT-32B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-009]: https://img.shields.io/static/v1?label=HF&message=Policy+8B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-010]: https://img.shields.io/static/v1?label=HF&message=GenPRM+8B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-011]: https://img.shields.io/static/v1?label=&message=GitHub&color=181717&style=flat&logo=github&logoColor=white
[badge-012]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+Data&color=181717&style=flat&logo=github&logoColor=white
[badge-013]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+Suite&color=181717&style=flat&logo=github&logoColor=white
[badge-014]: https://img.shields.io/static/v1?label=HF&message=HF+Data&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-015]: https://img.shields.io/static/v1?label=HF&message=HF+Dataset&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-016]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+Data+%26+Evaluation&color=181717&style=flat&logo=github&logoColor=white
[badge-017]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+Benchmark&color=181717&style=flat&logo=github&logoColor=white
[badge-018]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+Subset&color=181717&style=flat&logo=github&logoColor=white
[badge-019]: https://img.shields.io/static/v1?label=GitHub&message=Evaluation+code&color=181717&style=flat&logo=github&logoColor=white
[badge-020]: https://img.shields.io/static/v1?label=GitHub&message=GitHub%EF%BC%9ATest_Dataset&color=181717&style=flat&logo=github&logoColor=white
[badge-021]: https://img.shields.io/static/v1?label=HF&message=HF+%E9%95%9C%E5%83%8F%EF%BC%88%E7%AC%AC%E4%B8%89%E6%96%B9%E5%AD%97%E6%AE%B5%E9%80%82%E9%85%8D%EF%BC%89&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-022]: https://img.shields.io/static/v1?label=GitHub&message=Code&color=181717&style=flat&logo=github&logoColor=white
[badge-023]: https://img.shields.io/static/v1?label=GitHub&message=Evaluation+Code&color=181717&style=flat&logo=github&logoColor=white
[badge-024]: https://img.shields.io/static/v1?label=HF&message=IndustryOR&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-025]: https://img.shields.io/static/v1?label=GitHub&message=GitHub%EF%BC%9AProOPF_B&color=181717&style=flat&logo=github&logoColor=white
[badge-026]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+Environment&color=181717&style=flat&logo=github&logoColor=white
[badge-027]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+Case+Data&color=181717&style=flat&logo=github&logoColor=white
[badge-028]: https://img.shields.io/static/v1?label=GitHub&message=%E5%AE%98%E6%96%B9%E7%A7%8D%E5%AD%90%E4%B8%8E%E6%A0%B7%E4%BE%8B%E6%95%B0%E6%8D%AE&color=181717&style=flat&logo=github&logoColor=white
[badge-029]: https://img.shields.io/static/v1?label=&message=Author+Archive%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-030]: https://img.shields.io/static/v1?label=&message=SFT+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-031]: https://img.shields.io/static/v1?label=&message=RL+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-032]: https://img.shields.io/static/v1?label=HF&message=OR-Instruct-3K&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-033]: https://img.shields.io/static/v1?label=GitHub&message=GitHub%EF%BC%9AProOPF_D%EF%BC%8C%E9%9D%9E%E5%85%A8%E9%87%8F&color=181717&style=flat&logo=github&logoColor=white
[badge-034]: https://img.shields.io/static/v1?label=GitHub&message=GitHub%EF%BC%9AStep%2FDataset&color=181717&style=flat&logo=github&logoColor=white
[badge-035]: https://img.shields.io/static/v1?label=&message=Zenodo+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-036]: https://img.shields.io/static/v1?label=HF&message=HF%EF%BC%9AData+%26+Code&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-037]: https://img.shields.io/static/v1?label=&message=Zenodo+v2&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-038]: https://img.shields.io/static/v1?label=GitHub&message=GitHub%3A+problems&color=181717&style=flat&logo=github&logoColor=white
[badge-039]: https://img.shields.io/static/v1?label=HF&message=HF+Instances&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-040]: https://img.shields.io/static/v1?label=&message=Zenodo+Archive&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-041]: https://img.shields.io/static/v1?label=GitHub&message=GitHub%EF%BC%9Adataset.zip&color=181717&style=flat&logo=github&logoColor=white
[badge-042]: https://img.shields.io/static/v1?label=&message=Google+Drive+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-043]: https://img.shields.io/static/v1?label=HF&message=HF+Artifacts&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-044]: https://img.shields.io/static/v1?label=HF&message=HF%EF%BC%9A%E7%AC%AC%E4%B8%89%E6%96%B9%E7%BB%93%E6%9E%9C&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-045]: https://img.shields.io/static/v1?label=HF&message=%E4%BF%AE%E8%AE%A2%E8%AF%84%E6%B5%8B%E9%9B%86&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-046]: https://img.shields.io/static/v1?label=GitHub&message=GitHub%EF%BC%9AStep%2Ftest&color=181717&style=flat&logo=github&logoColor=white
[badge-047]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+Skills&color=181717&style=flat&logo=github&logoColor=white
[badge-048]: https://img.shields.io/static/v1?label=GitHub&message=%E5%AE%98%E6%96%B9%E6%8A%80%E8%83%BD%E5%BA%93%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-049]: https://img.shields.io/static/v1?label=arXiv&message=Paper&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[badge-050]: https://img.shields.io/static/v1?label=GitHub&message=Code+%26+Cleaned+Data&color=181717&style=flat&logo=github&logoColor=white
[badge-051]: https://img.shields.io/static/v1?label=&message=Paper+1&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-052]: https://img.shields.io/static/v1?label=arXiv&message=Paper+2&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[badge-053]: https://img.shields.io/static/v1?label=&message=Publication&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-054]: https://img.shields.io/static/v1?label=GitHub&message=Author+Coding+Agent%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-055]: https://img.shields.io/static/v1?label=&message=Evaluation+Archive+v2&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-056]: https://img.shields.io/static/v1?label=GitHub&message=Benchmark+%26+Evaluation&color=181717&style=flat&logo=github&logoColor=white
[badge-057]: https://img.shields.io/static/v1?label=&message=Paper&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-058]: https://img.shields.io/static/v1?label=arXiv&message=Paper+1&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[badge-059]: https://img.shields.io/static/v1?label=&message=Workshop&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-060]: https://img.shields.io/static/v1?label=HF&message=Dataset&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-061]: https://img.shields.io/static/v1?label=&message=Journal+record&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-062]: https://img.shields.io/static/v1?label=GitHub&message=Literature+Collection%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-063]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+dataset&color=181717&style=flat&logo=github&logoColor=white
[badge-064]: https://img.shields.io/static/v1?label=HF&message=Evaluation+Artifacts&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-065]: https://img.shields.io/static/v1?label=GitHub&message=Reproduction+Code%EF%BC%88%E7%AC%AC%E4%B8%89%E6%96%B9%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-066]: https://img.shields.io/static/v1?label=HF&message=Reproduction+Results%EF%BC%88%E7%AC%AC%E4%B8%89%E6%96%B9%EF%BC%89&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-067]: https://img.shields.io/static/v1?label=HF&message=Demo%EF%BC%88%E7%AC%AC%E4%B8%89%E6%96%B9%EF%BC%89&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-068]: https://img.shields.io/static/v1?label=GitHub&message=Inference%2C+Auditor+%26+Evaluation&color=181717&style=flat&logo=github&logoColor=white
[badge-069]: https://img.shields.io/static/v1?label=HF&message=OptiVerse+1K&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-070]: https://img.shields.io/static/v1?label=GitHub&message=Code+1&color=181717&style=flat&logo=github&logoColor=white
[badge-071]: https://img.shields.io/static/v1?label=GitHub&message=Code+2&color=181717&style=flat&logo=github&logoColor=white
[badge-072]: https://img.shields.io/static/v1?label=&message=Conference&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-073]: https://img.shields.io/static/v1?label=HF&message=Model&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-074]: https://img.shields.io/static/v1?label=&message=Paper+2&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-075]: https://img.shields.io/static/v1?label=arXiv&message=Paper+3&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[badge-076]: https://img.shields.io/static/v1?label=GitHub&message=Evaluation+Code+%26+Data&color=181717&style=flat&logo=github&logoColor=white
[badge-077]: https://img.shields.io/static/v1?label=HF&message=SAGE+SFT+100K&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-078]: https://img.shields.io/static/v1?label=GitHub&message=Benchmark+Inference&color=181717&style=flat&logo=github&logoColor=white
[badge-079]: https://img.shields.io/static/v1?label=HF&message=SDRL+Qwen3+4B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-080]: https://img.shields.io/static/v1?label=HF&message=SOLID-Qwen3&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-081]: https://img.shields.io/static/v1?label=HF&message=SOLID-StepORLM&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-082]: https://img.shields.io/static/v1?label=HF&message=Text2Zinc%EF%BC%88%E5%A4%8D%E7%94%A8%EF%BC%89&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-083]: https://img.shields.io/static/v1?label=HF&message=Editor%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-084]: https://img.shields.io/static/v1?label=HF&message=Leaderboard%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-085]: https://img.shields.io/static/v1?label=&message=Python+Package%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-086]: https://img.shields.io/static/v1?label=GitHub&message=%E5%AE%98%E6%96%B9%E9%A1%B9%E7%9B%AE%EF%BC%88%E4%BB%85+README%EF%BC%89%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-087]: https://img.shields.io/static/v1?label=&message=arXiv&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[badge-088]: https://img.shields.io/static/v1?label=arXiv&message=Related+version&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[badge-089]: https://img.shields.io/static/v1?label=GitHub&message=Code%EF%BC%88%E5%BD%93%E5%89%8D%E6%89%A9%E5%B1%95%E7%89%88%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-090]: https://img.shields.io/static/v1?label=HF&message=Dataset%EF%BC%88%E5%8E%9F%E7%89%88%E5%BD%92%E6%A1%A3%EF%BC%89&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-091]: https://img.shields.io/static/v1?label=GitHub&message=CP-Bench+%E5%8E%9F%E7%89%88%E5%BD%92%E6%A1%A3&color=181717&style=flat&logo=github&logoColor=white
[badge-092]: https://img.shields.io/static/v1?label=GitHub&message=Gala+in+Text2Model&color=181717&style=flat&logo=github&logoColor=white
[badge-093]: https://img.shields.io/static/v1?label=&message=Author+Project%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=009BD5&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0ibm9uZSIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyLjUiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgZD0ibTEwIDE0IDQtNG0tNiAxLTIgMmE0IDQgMCAwIDAgNiA2bDItMm0tNC0xMCAyLTJhNCA0IDAgMCAxIDYgNmwtMiAyIi8%2BPC9zdmc%2B&logoColor=white
[badge-094]: https://img.shields.io/static/v1?label=GitHub&message=%E5%AE%98%E6%96%B9%E8%B5%84%E6%BA%90%E5%BA%93%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-095]: https://img.shields.io/static/v1?label=GitHub&message=Cleaned+Benchmarks&color=181717&style=flat&logo=github&logoColor=white
[badge-096]: https://img.shields.io/static/v1?label=HF&message=Dataset%EF%BC%88%E7%AC%AC%E4%B8%89%E6%96%B9%E9%95%9C%E5%83%8F%EF%BC%89&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-097]: https://img.shields.io/static/v1?label=&message=Paper+3&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-098]: https://img.shields.io/static/v1?label=GitHub&message=Code+%26+MM-Bench&color=181717&style=flat&logo=github&logoColor=white
[badge-099]: https://img.shields.io/static/v1?label=GitHub&message=Expert+Skills+%282026+add-on%29&color=181717&style=flat&logo=github&logoColor=white
[badge-100]: https://img.shields.io/static/v1?label=HF&message=HF+Demo%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-101]: https://img.shields.io/static/v1?label=GitHub&message=Code+%26+ModelingBench&color=181717&style=flat&logo=github&logoColor=white
[badge-102]: https://img.shields.io/static/v1?label=GitHub&message=Diagnosis+Data&color=181717&style=flat&logo=github&logoColor=white
[badge-103]: https://img.shields.io/static/v1?label=&message=ICML+workshop+poster%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-104]: https://img.shields.io/static/v1?label=&message=Journal&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-105]: https://img.shields.io/static/v1?label=&message=Proceedings&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-106]: https://img.shields.io/static/v1?label=&message=%E4%BD%9C%E8%80%85%E9%A1%B9%E7%9B%AE%E9%97%A8%E6%88%B7%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=009BD5&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0ibm9uZSIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyLjUiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgZD0ibTEwIDE0IDQtNG0tNiAxLTIgMmE0IDQgMCAwIDAgNiA2bDItMm0tNC0xMCAyLTJhNCA0IDAgMCAxIDYgNmwtMiAyIi8%2BPC9zdmc%2B&logoColor=white
[badge-107]: https://img.shields.io/static/v1?label=&message=Paper+PDF&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-108]: https://img.shields.io/static/v1?label=&message=Institution+record&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-109]: https://img.shields.io/static/v1?label=HF&message=Data+%26+Code&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-110]: https://img.shields.io/static/v1?label=HF&message=ner4opt-roberta-v1&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-111]: https://img.shields.io/static/v1?label=HF&message=ner4opt-roberta-v2&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-112]: https://img.shields.io/static/v1?label=&message=MindOpt+Trial+%28International%29%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-113]: https://img.shields.io/static/v1?label=&message=MindOpt+Trial+%28CN%29%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-114]: https://img.shields.io/static/v1?label=GitHub&message=Training+Data&color=181717&style=flat&logo=github&logoColor=white
[badge-115]: https://img.shields.io/static/v1?label=GitHub&message=Generated+Formulations%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-116]: https://img.shields.io/static/v1?label=GitHub&message=Industrial+Case+Data&color=181717&style=flat&logo=github&logoColor=white
[badge-117]: https://img.shields.io/static/v1?label=GitHub&message=Industrial+Outputs%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-118]: https://img.shields.io/static/v1?label=GitHub&message=LPWP+Evaluation+Data%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-119]: https://img.shields.io/static/v1?label=GitHub&message=Modeling+Data&color=181717&style=flat&logo=github&logoColor=white
[badge-120]: https://img.shields.io/static/v1?label=&message=%E7%AB%9E%E8%B5%9B%E7%BB%93%E6%9E%9C%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=009BD5&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0ibm9uZSIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyLjUiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgZD0ibTEwIDE0IDQtNG0tNiAxLTIgMmE0IDQgMCAwIDAgNiA2bDItMm0tNC0xMCAyLTJhNCA0IDAgMCAxIDYgNmwtMiAyIi8%2BPC9zdmc%2B&logoColor=white
[badge-121]: https://img.shields.io/static/v1?label=GitHub&message=Code+%26+Data%EF%BC%88NL4Opt%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-122]: https://img.shields.io/static/v1?label=GitHub&message=Benchmark+Data&color=181717&style=flat&logo=github&logoColor=white
[badge-123]: https://img.shields.io/static/v1?label=GitHub&message=LLaMoCo-S+Example&color=181717&style=flat&logo=github&logoColor=white
[badge-124]: https://img.shields.io/static/v1?label=HF&message=LLaMoCo-S&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-125]: https://img.shields.io/static/v1?label=GitHub&message=%E6%95%B0%E6%8D%AE%E4%B8%8E%E6%A0%A1%E9%AA%8C%E4%BB%A3%E7%A0%81&color=181717&style=flat&logo=github&logoColor=white
[badge-126]: https://img.shields.io/static/v1?label=&message=Appendix%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-127]: https://img.shields.io/static/v1?label=HF&message=EquivaFormulation%EF%BC%88%E4%BD%BF%E7%94%A8%EF%BC%89%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-128]: https://img.shields.io/static/v1?label=HF&message=NLP4LP%EF%BC%88%E4%BD%BF%E7%94%A8%EF%BC%89%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-129]: https://img.shields.io/static/v1?label=GitHub&message=Framework&color=181717&style=flat&logo=github&logoColor=white
[badge-130]: https://img.shields.io/static/v1?label=GitHub&message=Frontend&color=181717&style=flat&logo=github&logoColor=white
[badge-131]: https://img.shields.io/static/v1?label=GitHub&message=Study+Code&color=181717&style=flat&logo=github&logoColor=white
[badge-132]: https://img.shields.io/static/v1?label=&message=Code+Archive&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-133]: https://img.shields.io/static/v1?label=&message=Evaluation+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-134]: https://img.shields.io/static/v1?label=GitHub&message=Prompts+%26+Algorithms&color=181717&style=flat&logo=github&logoColor=white
[badge-135]: https://img.shields.io/static/v1?label=&message=Project%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=009BD5&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0ibm9uZSIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyLjUiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgZD0ibTEwIDE0IDQtNG0tNiAxLTIgMmE0IDQgMCAwIDAgNiA2bDItMm0tNC0xMCAyLTJhNCA0IDAgMCAxIDYgNmwtMiAyIi8%2BPC9zdmc%2B&logoColor=white
[badge-136]: https://img.shields.io/static/v1?label=GitHub&message=Evolved+ALNS%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-137]: https://img.shields.io/static/v1?label=&message=Leaderboard%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=009BD5&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0ibm9uZSIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyLjUiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgZD0ibTEwIDE0IDQtNG0tNiAxLTIgMmE0IDQgMCAwIDAgNiA2bDItMm0tNC0xMCAyLTJhNCA0IDAgMCAxIDYgNmwtMiAyIi8%2BPC9zdmc%2B&logoColor=white
[badge-138]: https://img.shields.io/static/v1?label=&message=Author+Code+%2F+Data+Archive%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-139]: https://img.shields.io/static/v1?label=&message=Code+%26+Analysis+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-140]: https://img.shields.io/static/v1?label=&message=CO+Task+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-141]: https://img.shields.io/static/v1?label=GitHub&message=Generated+Operators%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-142]: https://img.shields.io/static/v1?label=GitHub&message=%E5%AE%98%E6%96%B9%E7%BB%93%E6%9E%9C%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-143]: https://img.shields.io/static/v1?label=GitHub&message=%E5%AE%98%E6%96%B9%E9%97%AE%E9%A2%98%E9%9B%86%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-144]: https://img.shields.io/static/v1?label=HF&message=CO+Instances&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-145]: https://img.shields.io/static/v1?label=GitHub&message=LLM4AD%3A+LHNS&color=181717&style=flat&logo=github&logoColor=white
[badge-146]: https://img.shields.io/static/v1?label=&message=Behaviour+Metrics+Code&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-147]: https://img.shields.io/static/v1?label=GitHub&message=LLM4AD%3A+MEoH&color=181717&style=flat&logo=github&logoColor=white
[badge-148]: https://img.shields.io/static/v1?label=GitHub&message=Code%EF%BC%88EvoCut+%E6%97%A7%E7%89%88%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-149]: https://img.shields.io/static/v1?label=GitHub&message=Code%EF%BC%88SAGE+v3%EF%BC%89&color=181717&style=flat&logo=github&logoColor=white
[badge-150]: https://img.shields.io/static/v1?label=GitHub&message=Skills&color=181717&style=flat&logo=github&logoColor=white
[badge-151]: https://img.shields.io/static/v1?label=GitHub&message=Lean+Proofs&color=181717&style=flat&logo=github&logoColor=white
[badge-152]: https://img.shields.io/static/v1?label=GitHub&message=InventoryBench&color=181717&style=flat&logo=github&logoColor=white
[badge-153]: https://img.shields.io/static/v1?label=GitHub&message=%E4%BA%BA%E6%9C%BA%E5%AE%9E%E9%AA%8C%E5%B9%B3%E5%8F%B0&color=181717&style=flat&logo=github&logoColor=white
[badge-154]: https://img.shields.io/static/v1?label=arXiv&message=Revised+Preprint&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[badge-155]: https://img.shields.io/static/v1?label=GitHub&message=Case-study+Code&color=181717&style=flat&logo=github&logoColor=white
[badge-156]: https://img.shields.io/static/v1?label=GitHub&message=Code+%26+Sample+Data&color=181717&style=flat&logo=github&logoColor=white
[badge-157]: https://img.shields.io/static/v1?label=HF&message=Japanese+%2F+English+OR+Data&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-158]: https://img.shields.io/static/v1?label=GitHub&message=Public+Test+Subset&color=181717&style=flat&logo=github&logoColor=white
[badge-159]: https://img.shields.io/static/v1?label=arXiv&message=%E7%89%88%E6%9C%AC&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[badge-160]: https://img.shields.io/static/v1?label=HF&message=%E7%89%88%E6%9C%AC&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[badge-161]: https://img.shields.io/static/v1?label=&message=%E7%89%88%E6%9C%AC&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-162]: https://img.shields.io/static/v1?label=&message=%E7%89%88%E6%9C%AC%EF%BC%88%E7%9B%B8%E5%85%B3%EF%BC%89&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[badge-163]: https://img.shields.io/static/v1?label=GitHub&message=%E7%89%88%E6%9C%AC&color=181717&style=flat&logo=github&logoColor=white

[resource-001]: https://huggingface.co/steven-0419/LLaMoCo
[resource-002]: https://huggingface.co/ant-opt/LLMOPT-Qwen2.5-14B
[resource-003]: https://huggingface.co/skadio/ner4opt-roberta-v1
[resource-004]: https://huggingface.co/skadio/ner4opt-roberta-v2
[resource-005]: https://huggingface.co/microsoft/OptiMind-SFT
[resource-006]: https://huggingface.co/Aurora-Gem/OptMATH-Qwen2.5-7B
[resource-007]: https://huggingface.co/Aurora-Gem/OptMATH-Qwen2.5-32B-Instruct
[resource-008]: https://huggingface.co/CardinalOperations/ORLM-LLaMA-3-8B
[resource-009]: https://huggingface.co/Aurora-Gem/PEARL-Qwen3-4B-Instruct-2507
[resource-010]: https://huggingface.co/tokentideAI/SDRL-Qwen3-4B
[resource-011]: https://huggingface.co/chenyitian-shanshu/SIRL-Gurobi
[resource-012]: https://huggingface.co/chenyitian-shanshu/SIRL-COPT
[resource-013]: https://huggingface.co/chenyitian-shanshu/SIRL-Gurobi32B
[resource-014]: https://huggingface.co/chenyitian-shanshu/SIRL-COPT32B
[resource-015]: https://huggingface.co/AIOR-Research/SOLID-Qwen3
[resource-016]: https://huggingface.co/AIOR-Research/SOLID-StepORLM
[resource-017]: https://huggingface.co/Chenyu-Zhou/StepORLM-Qwen3-8B
[resource-018]: https://huggingface.co/Chenyu-Zhou/StepORLM-GenPRM-Qwen3-8B
[resource-019]: https://github.com/Ahalikai/ARS-Routbench
[resource-020]: https://github.com/nl4opt/nl4opt-competition
[resource-021]: https://github.com/XAI-liacs/BLADE
[resource-022]: https://huggingface.co/datasets/LLM4OR/StructuredOR
[resource-023]: https://github.com/xzymustbexzy/Chain-of-Experts
[resource-024]: https://huggingface.co/datasets/CO-Bench/CO-Bench
[resource-025]: https://github.com/ccccziiii/VRPBench
[resource-026]: https://huggingface.co/datasets/kostis-init/CP-Bench
[resource-027]: https://github.com/DCP-Bench/DCP-Bench-Open
[resource-028]: https://github.com/Yuliang795/LLMs-CP-CPSynC
[resource-029]: https://github.com/dsbx7/DynaSchedBench
[resource-030]: https://github.com/xiyuan-zhou/ElecBench-a-Power-Dispatch-Evaluation-Benchmark-for-Large-Language-Models
[resource-031]: https://github.com/Forrest-Stone/EOR
[resource-032]: https://huggingface.co/datasets/humainlab/EquivaFormulation
[resource-033]: https://huggingface.co/datasets/frontieror/FrontierOR
[resource-034]: https://github.com/Minw913/FrontierOR
[resource-035]: https://github.com/cornell-zhang/heurigym
[resource-036]: https://github.com/TianyiPeng/InventoryBench
[resource-037]: https://huggingface.co/datasets/cyberagent/JOR-Bench
[resource-038]: https://github.com/CoraLiang01/lean-llm-opt
[resource-039]: https://github.com/ZIKEYUAN/MA-GTS
[resource-040]: https://github.com/FreedomIntelligence/Mamo
[resource-041]: https://huggingface.co/datasets/CardinalOperations/MAMO
[resource-042]: https://github.com/optsuite/MIPLIB-NL
[resource-043]: https://github.com/usail-hkust/LLM-MM-Agent
[resource-044]: https://github.com/qiancheng0/ModelingAgent
[resource-045]: https://huggingface.co/datasets/summer142857jiang/NLCO
[resource-046]: https://github.com/jing12e/nlco
[resource-047]: https://huggingface.co/datasets/OPT-Bench/OPT-Bench
[resource-048]: https://github.com/OliverLeeXZ/OPT-BENCH
[resource-049]: https://huggingface.co/datasets/chenyitian-shanshu/OPTEngine
[resource-050]: https://github.com/Cardinal-Operations/OPTEngine
[resource-051]: https://huggingface.co/datasets/udell-lab/NLP4LP
[resource-052]: https://huggingface.co/datasets/Waicheng/OptiVerse
[resource-053]: https://github.com/Waichenbxx/OptiVerse
[resource-054]: https://github.com/optsuite/OptMATH
[resource-055]: https://huggingface.co/datasets/SJTU/BWOR
[resource-056]: https://huggingface.co/datasets/Chenyu-Zhou/OR-Space
[resource-057]: https://github.com/0xzhouchenyu/OR-Space
[resource-058]: https://github.com/ORAgentBench/ORAgentBench
[resource-059]: https://huggingface.co/datasets/CardinalOperations/IndustryOR
[resource-060]: https://github.com/Archer222arc/ORLoopBench
[resource-061]: https://github.com/nl4opt/ORQA
[resource-062]: https://huggingface.co/datasets/LabMem012/LogiOR
[resource-063]: https://github.com/JAVA-Jiang/PowerAtlas
[resource-064]: https://github.com/shenchao188/ProOPF-Benchamrk-Dataset
[resource-065]: https://huggingface.co/datasets/Jacoblian/RetailOpt-190
[resource-066]: https://github.com/yangzhch6/PRIVATE-RS
[resource-067]: https://github.com/linghuazhang01/RetailBench
[resource-068]: https://github.com/baranwa2/SOVER
[resource-069]: https://huggingface.co/datasets/skadio/text2zinc
[resource-070]: https://github.com/pivithuruthejanamarasinghe/AI-Copilot-Data
[resource-071]: https://github.com/pivithuruthejanamarasinghe/AI-Copilot-Data-Real-World-Scenario
[resource-072]: https://github.com/xzymustbexzy/DeepOR/tree/main/data
[resource-073]: https://drive.google.com/drive/folders/1P7ixNFALdlZHyGm3vc8eGNRy8681W2jY?usp=drive_link
[resource-074]: https://drive.google.com/drive/folders/1bE1coGUa00gfuMkPXnfvldi1-WHGNnEb?usp=sharing
[resource-075]: https://drive.google.com/drive/folders/1VN9crftdW7DTsMQupbc06u6PzRT-Bwnx?usp=sharing
[resource-076]: https://huggingface.co/datasets/microsoft/MILP-Evolve
[resource-077]: https://github.com/yangyangyang777/Datasets-for-automatic-modeling.git
[resource-078]: https://huggingface.co/datasets/Aurora-Gem/OptMATH-Train
[resource-079]: https://huggingface.co/datasets/CardinalOperations/OR-Instruct-Data-3K
[resource-080]: https://huggingface.co/datasets/Rachhhhing/SAGE-SFT-100K
[resource-081]: https://huggingface.co/datasets/mideavalwisard/Starjob
[resource-082]: https://github.com/samwu-learn/Step
[resource-083]: https://github.com/CHIANGEL/Agora-Opt
[resource-084]: https://doi.org/10.5281/zenodo.17856423
[resource-085]: https://zenodo.org/records/14162744
[resource-086]: https://huggingface.co/datasets/BTBUzhy/JOC
[resource-087]: https://doi.org/10.5281/zenodo.21361220
[resource-088]: https://github.com/Summer142857/DRoC
[resource-089]: https://huggingface.co/datasets/VictorYXL/HeurAgenixDataset
[resource-090]: https://github.com/joshddrossman/LLMforIO
[resource-091]: https://doi.org/10.5281/zenodo.21891840
[resource-092]: https://github.com/LLM4OR/LLM4OR/tree/master/static/clean_benchmarks
[resource-093]: https://github.com/Amirreza-96/LLM-SO-manuscript
[resource-094]: https://drive.google.com/file/d/1e4T8Yiz-qvHcChys2Tk841pbXumGVYu2/view?usp=sharing
[resource-095]: https://github.com/Ahalikai/MOID-Diagnosis
[resource-096]: https://huggingface.co/datasets/c3aiia3c/nemo-icml2026
[resource-097]: https://huggingface.co/datasets/ernikhil411/OptMiner-Reproduction
[resource-098]: https://github.com/li-group/OptiChat
[resource-099]: https://huggingface.co/datasets/chenyitian-shanshu/ORLMBenchmark
[resource-100]: https://github.com/Shuvomoy/AutoOPT/tree/main/Skills
[resource-101]: https://github.com/luckyfan-cs/mm-agent-expert
[resource-102]: https://github.com/HQian-AI/OptSkills/tree/main/skill_library
[resource-103]: https://arxiv.org/abs/2604.25847
[resource-104]: https://icml.cc/virtual/2026/78174
[resource-105]: https://arxiv.org/abs/2604.16804
[resource-106]: https://arxiv.org/abs/2605.11813
[resource-107]: https://link.springer.com/chapter/10.1007/978-3-032-09192-5_5
[resource-108]: https://arxiv.org/abs/2505.01485
[resource-109]: https://arxiv.org/abs/2602.02029
[resource-110]: https://doi.org/10.1145/3801961
[resource-111]: https://arxiv.org/abs/2507.03637
[resource-112]: https://arxiv.org/abs/2606.27611
[resource-113]: https://github.com/xxxxxa-hub/COOPA
[resource-114]: https://doi.org/10.1145/3786181.3788711
[resource-115]: https://arxiv.org/abs/2508.07468
[resource-116]: https://github.com/szeider/agentic-python-coder
[resource-117]: https://arxiv.org/abs/2605.01675
[resource-118]: https://ojs.aaai.org/index.php/AAAI/article/view/40699
[resource-119]: https://github.com/xzymustbexzy/DeepOR
[resource-120]: https://arxiv.org/abs/2604.00442
[resource-121]: https://arxiv.org/abs/2602.01082
[resource-122]: https://github.com/WillowHe/EvoOpt_oppangu_optimization_model
[resource-123]: https://neurips.cc/virtual/2026/poster/155640
[resource-124]: https://arxiv.org/abs/2606.26578
[resource-125]: https://arxiv.org/abs/2604.17708
[resource-126]: https://arxiv.org/abs/2605.12421
[resource-127]: https://neurips.cc/virtual/2026/173061
[resource-128]: https://aclanthology.org/2026.emnlp-main.221/
[resource-129]: https://arxiv.org/abs/2608.23353
[resource-130]: https://github.com/Xyz-yuanhf/formuevo
[resource-131]: https://neurips.cc/virtual/2026/poster/139096
[resource-132]: https://arxiv.org/abs/2605.25246
[resource-133]: https://arxiv.org/abs/2604.02666
[resource-134]: https://arxiv.org/abs/2601.09635
[resource-135]: https://doi.org/10.1109/MCI.2026.3727078
[resource-136]: https://arxiv.org/abs/2509.08269
[resource-137]: https://github.com/ishmael233/LLM4OPT
[resource-138]: https://arxiv.org/abs/2602.11164
[resource-139]: https://arxiv.org/abs/2606.25832
[resource-140]: https://github.com/Hsiang-1/MiniOpt
[resource-141]: https://proceedings.mlr.press/v306/li26dz.html
[resource-142]: https://arxiv.org/abs/2602.10450
[resource-143]: https://github.com/optsuite/MIPLIB-NL/tree/main/dataset
[resource-144]: https://arxiv.org/abs/2602.03318
[resource-145]: https://neurips.cc/virtual/2026/poster/139697
[resource-146]: https://arxiv.org/abs/2605.12154
[resource-147]: https://arxiv.org/abs/2607.25956
[resource-148]: https://proceedings.mlr.press/v306/song26z.html
[resource-149]: https://arxiv.org/abs/2601.21372
[resource-150]: https://proceedings.mlr.press/v306/chen26o.html
[resource-151]: https://arxiv.org/abs/2601.19924
[resource-152]: https://proceedings.mlr.press/v306/liu26d.html
[resource-153]: https://github.com/ernikhildhaka-arch/OptMiner-Reproduction
[resource-154]: https://huggingface.co/spaces/ernikhil411/repro-opt-miner
[resource-155]: https://arxiv.org/abs/2607.27918
[resource-156]: https://github.com/xianchaoxiu/OptGraph
[resource-157]: https://arxiv.org/abs/2607.10768
[resource-158]: https://arxiv.org/abs/2607.05346
[resource-159]: https://doi.org/10.1287/ijds.2025.0074
[resource-160]: https://arxiv.org/abs/2501.08406
[resource-161]: https://arxiv.org/abs/2608.07040
[resource-162]: https://aclanthology.org/2026.findings-acl.150/
[resource-163]: https://arxiv.org/abs/2604.21510
[resource-164]: https://aclanthology.org/2026.findings-emnlp.394/
[resource-165]: https://arxiv.org/abs/2605.29829
[resource-166]: https://github.com/fujiwaranoM0kou/OptSkills
[resource-167]: https://github.com/HQian-AI/OptSkills
[resource-168]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/4624803ce92f6c44d8cabe085d8d9d96-Abstract-Conference.html
[resource-169]: https://doi.org/10.1609/aaai.v40i1.36983
[resource-170]: https://arxiv.org/abs/2511.09092
[resource-171]: https://github.com/SCUTE-ZZ/OR-R1
[resource-172]: https://arxiv.org/abs/2605.28158
[resource-173]: https://arxiv.org/abs/2606.19787
[resource-174]: https://doi.org/10.1016/j.ait.2026.100059
[resource-175]: https://arxiv.org/abs/2508.14410
[resource-176]: https://github.com/ZJU-TSELab/ORThought
[resource-177]: https://arxiv.org/abs/2607.18256
[resource-178]: https://neurips.cc/virtual/2026/poster/152032
[resource-179]: https://github.com/AuroraLHL/PEARL
[resource-180]: https://proceedings.mlr.press/v306/shen26h.html
[resource-181]: https://icml.cc/virtual/2026/poster/63658
[resource-182]: https://arxiv.org/abs/2602.03070
[resource-183]: https://arxiv.org/abs/2608.00015
[resource-184]: https://proceedings.mlr.press/v306/zhang26cb.html
[resource-185]: https://arxiv.org/abs/2510.05115
[resource-186]: https://github.com/Forrest-Stone/SAC-Opt
[resource-187]: https://proceedings.mlr.press/v306/zhao26z.html
[resource-188]: https://arxiv.org/abs/2605.02545
[resource-189]: https://github.com/rachhhhing/SAGE
[resource-190]: https://arxiv.org/abs/2609.34427
[resource-191]: https://github.com/tokentideAI/LLMMetaSolver
[resource-192]: https://doi.org/10.1080/00207543.2026.2663386
[resource-193]: https://arxiv.org/abs/2511.02364
[resource-194]: https://arxiv.org/abs/2609.09957
[resource-195]: https://github.com/AIOR-Research/SOLID
[resource-196]: https://arxiv.org/abs/2604.12955
[resource-197]: https://github.com/skadio/text2model
[resource-198]: https://huggingface.co/spaces/skadio/text2zinc-editor
[resource-199]: https://huggingface.co/spaces/skadio/text2model-leaderboard
[resource-200]: https://pypi.org/project/text2model/
[resource-201]: https://proceedings.mlr.press/v306/rahman26a.html
[resource-202]: https://arxiv.org/abs/2607.20474
[resource-203]: https://icml.cc/virtual/2026/poster/65537
[resource-204]: https://github.com/suabar/VeriSimple
[resource-205]: https://neurips.cc/virtual/2025/133378
[resource-206]: https://arxiv.org/abs/2510.18428
[resource-207]: https://github.com/Minw913/AlphaOPT
[resource-208]: https://arxiv.org/abs/2601.00121
[resource-209]: https://proceedings.mlr.press/v267/astorga25a.html
[resource-210]: https://arxiv.org/abs/2411.01679
[resource-211]: https://github.com/jumpynitro/AutoFormulator
[resource-212]: https://aclanthology.org/2025.acl-long.40/
[resource-213]: https://github.com/LLM4OR/StructuredOR
[resource-214]: https://doi.org/10.15439/2025F5420
[resource-215]: https://annals-csis.org/Volume_43/drp/5420.html
[resource-216]: https://arxiv.org/abs/2510.04204
[resource-217]: https://arxiv.org/abs/2510.16943
[resource-218]: https://arxiv.org/abs/2506.06052v2
[resource-219]: https://arxiv.org/abs/2506.06052
[resource-220]: https://doi.org/10.3233/faia250890
[resource-221]: https://github.com/kostis-init/CP-Bench
[resource-222]: https://arxiv.org/abs/2511.11576
[resource-223]: https://ojs.aaai.org/index.php/AAAI/article/view/35090
[resource-224]: https://arxiv.org/abs/2402.16269
[resource-225]: https://arxiv.org/abs/2507.11737
[resource-226]: https://proceedings.iclr.cc/paper_files/paper/2025/hash/73d6c3e4b214deebbbf8256e26d2cf45-Abstract-Conference.html
[resource-227]: https://iclr.cc/virtual/2025/poster/28142
[resource-228]: https://proceedings.iclr.cc/paper_files/paper/2025/hash/a48e5877c7bf86a513950ab23b360498-Abstract-Conference.html
[resource-229]: https://arxiv.org/abs/2502.09994
[resource-230]: https://proceedings.mlr.press/v267/zhai25a.html
[resource-231]: https://arxiv.org/abs/2502.14760
[resource-232]: https://github.com/HumainLab/EquivaMap
[resource-233]: https://arxiv.org/abs/2509.08970
[resource-234]: https://skadio.github.io/text2model/
[resource-235]: https://arxiv.org/abs/2502.10557
[resource-236]: https://github.com/drzekunguo/LLM_Agent_Power_System_Balance
[resource-237]: https://arxiv.org/abs/2508.10047
[resource-238]: https://github.com/LLM4OR/LLM4OR
[resource-239]: https://proceedings.iclr.cc/paper_files/paper/2025/hash/fbe6dd68b0cf2b1d43b458d2b8ca31b0-Abstract-Conference.html
[resource-240]: https://arxiv.org/abs/2410.13213
[resource-241]: https://github.com/antgroup/LLMOPT
[resource-242]: https://arxiv.org/abs/2508.17200
[resource-243]: https://arxiv.org/abs/2509.18180
[resource-244]: https://arxiv.org/abs/2405.13144
[resource-245]: https://aclanthology.org/2025.findings-naacl.146/
[resource-246]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/1ddd6c6909c2a7acf877ce0f84abf6eb-Abstract-Conference.html
[resource-247]: https://arxiv.org/abs/2505.14148
[resource-248]: https://doi.org/10.52202/085713-0704
[resource-249]: https://huggingface.co/spaces/MathematicalModelingAgent/MathematicalModelingAgent
[resource-250]: https://aclanthology.org/2025.findings-emnlp.85/
[resource-251]: https://arxiv.org/abs/2505.15068
[resource-252]: https://arxiv.org/abs/2508.03406
[resource-253]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/31e89283741f8f70ad2290b5c197ae18-Abstract-Conference.html
[resource-254]: https://arxiv.org/abs/2504.16918
[resource-255]: https://arxiv.org/abs/2509.22979
[resource-256]: https://github.com/microsoft/OptiGuide
[resource-257]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/aeaf9b454f4670d5bf2f02b4b6e5bffd-Abstract-Conference.html
[resource-258]: https://arxiv.org/abs/2510.22192
[resource-259]: https://github.com/MIRALab-USTC/OptiTree
[resource-260]: https://arxiv.org/abs/2508.03117
[resource-261]: https://proceedings.mlr.press/v267/lu25o.html
[resource-262]: https://arxiv.org/abs/2503.10009
[resource-263]: https://github.com/bwz96sco/or_llm_agent
[resource-264]: https://arxiv.org/abs/2510.27610
[resource-265]: https://icml.cc/virtual/2026/68291
[resource-266]: https://arxiv.org/abs/2405.17743
[resource-267]: https://pubsonline.informs.org/doi/10.1287/opre.2024.1233
[resource-268]: https://github.com/Cardinal-Operations/ORLM
[resource-269]: https://aclanthology.org/2025.acl-industry.10/
[resource-270]: https://arxiv.org/abs/2506.01326
[resource-271]: https://github.com/XiaoAI1989/ORMind
[resource-272]: https://ojs.aaai.org/index.php/AAAI/article/view/34673
[resource-273]: https://arxiv.org/abs/2412.17874
[resource-274]: https://proceedings.iclr.cc/paper_files/paper/2025/hash/3deb687c44d3687ace0729e5db3b4efd-Abstract-Conference.html
[resource-275]: https://arxiv.org/abs/2407.09887
[resource-276]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/98555b92e5dedbdad5921049281995bc-Abstract-Conference.html
[resource-277]: https://arxiv.org/abs/2505.11792
[resource-278]: https://github.com/Cardinal-Operations/SIRL
[resource-279]: https://proceedings.nips.cc/paper_files/paper/2025/hash/903475a4d33d21bfd75d4fa0d124abfe-Abstract-Conference.html
[resource-280]: https://arxiv.org/abs/2510.16916
[resource-281]: https://aclanthology.org/2025.findings-emnlp.691/
[resource-282]: https://arxiv.org/abs/2506.17637
[resource-283]: https://arxiv.org/abs/2508.18091
[resource-284]: https://arxiv.org/abs/2503.10642
[resource-285]: https://arxiv.org/abs/2508.08147
[resource-286]: https://apexapps.oracle.com/pls/apex/f?p=LABS%3A0%3A108770064556151%3AAPPLICATION_PROCESS%3DGETDOC_INLINE%3A%3A%3ADOC_ID%3A4780
[resource-287]: https://labs.oracle.com/pls/apex/f?p=94065%3A10%3A18082377147334%3A11529
[resource-288]: https://neurips.cc/virtual/2024/98475
[resource-289]: https://github.com/BlueAsuka/CAFA
[resource-290]: https://proceedings.iclr.cc/paper_files/paper/2024/hash/d45ee77826332c100a1e15f7765b99ff-Abstract-Conference.html
[resource-291]: https://arxiv.org/abs/2406.10958
[resource-292]: https://aclanthology.org/2024.lrec-main.1438/
[resource-293]: https://aclanthology.org/2024.emnlp-industry.104/
[resource-294]: https://arxiv.org/abs/2402.07204
[resource-295]: https://github.com/YihongT/ITINERA
[resource-296]: https://doi.org/10.1080/03155986.2024.2388452
[resource-297]: https://arxiv.org/abs/2403.01342
[resource-298]: https://doi.org/10.1080/03155986.2024.2381306
[resource-299]: https://doi.org/10.1007/s10601-024-09376-5
[resource-300]: https://github.com/skadio/ner4opt
[resource-301]: https://huggingface.co/spaces/skadio/Ner4Opt
[resource-302]: https://proceedings.mlr.press/v235/ahmaditeshnizi24a.html
[resource-303]: https://arxiv.org/abs/2402.10172
[resource-304]: https://github.com/teshnizi/OptiMUS
[resource-305]: https://aclanthology.org/2024.naacl-industry.42/
[resource-306]: https://arxiv.org/abs/2407.07924
[resource-307]: https://opt.alibabacloud.com/chat
[resource-308]: https://opt.aliyun.com/chat
[resource-309]: https://arxiv.org/abs/2405.06697
[resource-310]: https://aclanthology.org/2024.emnlp-demo.25/
[resource-311]: https://arxiv.org/abs/2410.16456
[resource-312]: https://arxiv.org/abs/2309.13218
[resource-313]: https://github.com/pivithuruthejanamarasinghe/AI-Copilot-Artifacts
[resource-314]: https://github.com/pivithuruthejanamarasinghe/AI-Copilot-Artifacts-Real-World-Scenario
[resource-315]: https://github.com/pivithuruthejanamarasinghe/LPWP
[resource-316]: https://arxiv.org/abs/2304.03287
[resource-317]: https://arxiv.org/abs/2308.01589
[resource-318]: https://arxiv.org/abs/2311.15271
[resource-319]: https://proceedings.mlr.press/v220/ramamonjison23a.html
[resource-320]: https://arxiv.org/abs/2303.08233
[resource-321]: https://arxiv.org/abs/2302.04643
[resource-322]: https://github.com/bigdata-ustc/nl4opt
[resource-323]: https://arxiv.org/abs/2301.02459
[resource-324]: https://nl4opt.github.io/results/
[resource-325]: https://arxiv.org/abs/2307.03875
[resource-326]: https://aclanthology.org/2022.emnlp-industry.4/
[resource-327]: https://proceedings.mlr.press/v306/chen26hb.html
[resource-328]: https://icml.cc/virtual/2026/poster/64869
[resource-329]: https://arxiv.org/abs/2604.24043
[resource-330]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/b9c91701ff28d480f186e4643e71ad11-Abstract-Conference.html
[resource-331]: https://iclr.cc/virtual/2026/poster/10010957
[resource-332]: https://arxiv.org/abs/2510.16701
[resource-333]: https://github.com/ZHANG-NI/AFL.git
[resource-334]: https://arxiv.org/abs/2605.09186
[resource-335]: https://aclanthology.org/2026.findings-emnlp.1787/
[resource-336]: https://arxiv.org/abs/2606.04816
[resource-337]: https://arxiv.org/abs/2601.09100
[resource-338]: https://arxiv.org/abs/2607.16646
[resource-339]: https://doi.org/10.1109/tevc.2026.3656374
[resource-340]: https://arxiv.org/abs/2403.01131
[resource-341]: https://github.com/MetaEvo/LLaMoCo
[resource-342]: https://doi.org/10.1016/j.eswa.2026.133022
[resource-343]: https://arxiv.org/abs/2507.20541
[resource-344]: https://arxiv.org/abs/2607.18252
[resource-345]: https://arxiv.org/abs/2605.11738
[resource-346]: https://arxiv.org/abs/2605.27630
[resource-347]: https://arxiv.org/abs/2602.19439
[resource-348]: https://proceedings.mlr.press/v306/ao26a.html
[resource-349]: https://arxiv.org/abs/2601.21008
[resource-350]: https://arxiv.org/abs/2602.15983
[resource-351]: https://neurips.cc/virtual/2026/poster/153462
[resource-352]: https://github.com/junbolian/ReLoop
[resource-353]: https://arxiv.org/abs/2609.00859
[resource-354]: https://doi.org/10.5281/zenodo.19134435
[resource-355]: https://aclanthology.org/2026.findings-emnlp.1886/
[resource-356]: https://arxiv.org/abs/2609.00728
[resource-357]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/0bcfb525c8f8f07ae10a93d0b2a40e00-Abstract-Conference.html
[resource-358]: https://arxiv.org/abs/2509.22558
[resource-359]: https://github.com/0xzhouchenyu/StepORLM
[resource-360]: https://arxiv.org/abs/2509.18108
[resource-361]: https://github.com/TBU-AILab/EASE
[resource-362]: https://github.com/TBU-AILab/frontEASE
[resource-363]: https://arxiv.org/abs/2509.02297
[resource-364]: https://github.com/quangr/EoH
[resource-365]: https://arxiv.org/abs/2505.20242
[resource-366]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/57f2d605790f01cc2d89699b0bf3b33e-Abstract-Conference.html
[resource-367]: https://arxiv.org/abs/2506.11057
[resource-368]: https://github.com/Y-Palver/L2O-STRCMP
[resource-369]: https://arxiv.org/abs/2308.12923
[resource-370]: https://doi.org/10.1080/03155986.2024.2385189
[resource-371]: https://arxiv.org/abs/2305.11202
[resource-372]: https://arxiv.org/abs/2602.23092
[resource-373]: https://arxiv.org/abs/2609.08071
[resource-374]: https://www.nature.com/articles/s41467-026-74949-2
[resource-375]: https://arxiv.org/abs/2507.22876
[resource-376]: https://doi.org/10.5281/zenodo.17856395
[resource-377]: https://doi.org/10.1613/jair.1.20499
[resource-378]: https://arxiv.org/abs/2402.10705
[resource-379]: https://github.com/YiwenAI/AutoSAT
[resource-380]: https://arxiv.org/abs/2609.36735
[resource-381]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/75ed738c083f8941cfc990245e4f6265-Abstract-Conference.html
[resource-382]: https://arxiv.org/abs/2505.12285
[resource-383]: https://github.com/whxru/CALM
[resource-384]: https://ojs.aaai.org/index.php/AAAI/article/view/40596
[resource-385]: https://arxiv.org/abs/2504.04310
[resource-386]: https://github.com/sunnweiwei/CO-Bench
[resource-387]: https://journal.iberamia.org/index.php/intartif/article/view/2584
[resource-388]: https://doi.org/10.4114/intartif.vol29iss77pp108-132
[resource-389]: https://arxiv.org/abs/2503.10968
[resource-390]: https://github.com/camilochs/comb-opt-for-all
[resource-391]: https://camilochs.github.io/comb-opt-for-all/
[resource-392]: https://arxiv.org/abs/2603.27628
[resource-393]: https://arxiv.org/abs/2610.17379
[resource-394]: https://arxiv.org/abs/2609.00023
[resource-395]: https://conference.cs.cityu.edu.hk/icist/program/ICIST%202026%20Program%20v3.pdf
[resource-396]: https://github.com/Mriya0306/ES-AHD
[resource-397]: https://arxiv.org/abs/2610.22861
[resource-398]: https://arxiv.org/abs/2603.06996
[resource-399]: https://github.com/Shaohua-Yu/LLM-ALNS
[resource-400]: https://arxiv.org/abs/2602.08253
[resource-401]: https://github.com/zboyn/G-LNS
[resource-402]: https://arxiv.org/abs/2606.23299
[resource-403]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/2e49934cac6cb8604b0c67cfa0828718-Abstract-Conference.html
[resource-404]: https://arxiv.org/abs/2506.07972
[resource-405]: https://cornell-zhang.github.io/heurigym/
[resource-406]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/be36e50757bf9cd280aa74f89a7d1c23-Abstract-Conference.html
[resource-407]: https://arxiv.org/abs/2508.13333
[resource-408]: https://github.com/Challenger-XJTU/HiFo-Prompt
[resource-409]: https://arxiv.org/abs/2604.01455
[resource-410]: https://arxiv.org/abs/2605.00369
[resource-411]: https://arxiv.org/abs/2602.16038
[resource-412]: https://arxiv.org/abs/2605.17137
[resource-413]: https://www.lion20.org/papers/
[resource-414]: https://github.com/cheikh025/LHS
[resource-415]: https://arxiv.org/abs/2601.00770
[resource-416]: https://neurips.cc/virtual/2026/171741
[resource-417]: https://doi.org/10.1016/j.cor.2026.107603
[resource-418]: https://arxiv.org/abs/2512.13374
[resource-419]: https://doi.org/10.24963/ijcai.2026/736
[resource-420]: https://github.com/BeeeeenWANG/LLM-guided-cutting-plane-management
[resource-421]: https://arxiv.org/abs/2410.14716
[resource-422]: https://doi.org/10.1145/3787585
[resource-423]: https://github.com/FeiLiu36/LLM4AlgorithmDesign
[resource-424]: https://proceedings.mlr.press/v306/hou26d.html
[resource-425]: https://arxiv.org/abs/2605.10401
[resource-426]: https://github.com/hzn18/LLM4Branch
[resource-427]: https://doi.org/10.1109/MIPRO70003.2026.11591581
[resource-428]: https://arxiv.org/abs/2606.15577
[resource-429]: https://arxiv.org/abs/2606.14202
[resource-430]: https://github.com/Qzs1335/MeEvo
[resource-431]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/c1e67cde895c3c91edb43569ad0df260-Abstract-Conference.html
[resource-432]: https://arxiv.org/abs/2505.20881
[resource-433]: https://github.com/yiding-s/MoH
[resource-434]: https://doi.org/10.1609/aaai.v40i43.41024
[resource-435]: https://arxiv.org/abs/2507.20923
[resource-436]: https://github.com/langkhachhoha/MPaGE
[resource-437]: https://neurips.cc/virtual/2026/poster/150513
[resource-438]: https://proceedings.mlr.press/v306/gungordu26a.html
[resource-439]: https://arxiv.org/abs/2601.20539
[resource-440]: https://github.com/oguzhangungordu/PathWise
[resource-441]: https://doi.org/10.65109/ISFV2587
[resource-442]: https://arxiv.org/abs/2604.07872
[resource-443]: https://ifaamas.org/Proceedings/aamas2026/forms/contents.htm
[resource-444]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/7886b9bafe76c52fd568db10ff9772df-Abstract-Conference.html
[resource-445]: https://arxiv.org/abs/2509.19349
[resource-446]: https://github.com/SakanaAI/ShinkaEvolve
[resource-447]: https://arxiv.org/abs/2607.23676
[resource-448]: https://arxiv.org/abs/2609.31179
[resource-449]: https://arxiv.org/abs/2601.21239
[resource-450]: https://openreview.net/forum?id=2cYbzycSbz
[resource-451]: https://arxiv.org/abs/2510.07073
[resource-452]: https://github.com/ai4co/vrpagent
[resource-453]: https://arxiv.org/abs/2506.13131
[resource-454]: https://github.com/google-deepmind/alphaevolve_results
[resource-455]: https://github.com/google-deepmind/alphaevolve_repository_of_problems
[resource-456]: https://arxiv.org/abs/2502.15359
[resource-457]: https://doi.org/10.1007/978-3-031-90065-5_24
[resource-458]: https://arxiv.org/abs/2501.11411
[resource-459]: https://doi.org/10.1145/3712255.3734347
[resource-460]: https://arxiv.org/abs/2504.20183
[resource-461]: https://arxiv.org/abs/2503.03350
[resource-462]: https://github.com/nico-koltermann/contextual-evolution-of-heuristics
[resource-463]: https://arxiv.org/abs/2412.12038
[resource-464]: https://doi.org/10.1007/978-3-031-95976-9_4
[resource-465]: https://github.com/OptiMUS-optimization-modeling/LLM-Solver-Configuration
[resource-466]: https://arxiv.org/abs/2507.15615
[resource-467]: https://arxiv.org/abs/2507.17211
[resource-468]: https://arxiv.org/abs/2506.12495
[resource-469]: https://arxiv.org/abs/2506.15196
[resource-470]: https://github.com/microsoft/HeurAgenix
[resource-471]: https://doi.org/10.1609/aaai.v39i25.34898
[resource-472]: https://arxiv.org/abs/2412.14995
[resource-473]: https://github.com/datphamvn/HSEvo
[resource-474]: https://arxiv.org/abs/2506.00490
[resource-475]: https://doi.org/10.1109/CEC65147.2025.11043025
[resource-476]: https://scholars.cityu.edu.hk/en/publications/llm-driven-neighborhood-search-for-efficient-heuristic-design/
[resource-477]: https://github.com/Optima-CityU/LLM4AD/tree/main/llm4ad/method/lhns
[resource-478]: https://arxiv.org/abs/2405.20132
[resource-479]: https://github.com/XAI-liacs/LLaMEA
[resource-480]: https://arxiv.org/abs/2504.19636
[resource-481]: https://arxiv.org/abs/2507.03605
[resource-482]: https://doi.org/10.5281/zenodo.15675581
[resource-483]: https://arxiv.org/abs/2510.24013
[resource-484]: https://github.com/ibrahimoguzc/DiscoverHeuristics
[resource-485]: https://proceedings.mlr.press/v267/ye25j.html
[resource-486]: https://github.com/thuiar/LLM-LNS
[resource-487]: https://arxiv.org/abs/2502.18540
[resource-488]: https://aclanthology.org/2025.emnlp-main.973/
[resource-489]: https://proceedings.mlr.press/v267/zheng25o.html
[resource-490]: https://arxiv.org/abs/2501.08603
[resource-491]: https://github.com/zz1358m/MCTS-AHD-master
[resource-492]: https://doi.org/10.1609/aaai.v39i25.34922
[resource-493]: https://arxiv.org/abs/2409.16867
[resource-494]: https://github.com/Optima-CityU/LLM4AD
[resource-495]: https://proceedings.iclr.cc/paper_files/paper/2025/hash/dc594b8712f5d3ea1904092d74739d25-Abstract-Conference.html
[resource-496]: https://arxiv.org/abs/2410.08288
[resource-497]: https://github.com/microsoft/OptiGuide/tree/main/milp-evolve
[resource-498]: https://github.com/microsoft/MILP-Evolve
[resource-499]: https://iclr.cc/virtual/2025/33144
[resource-500]: https://github.com/Fsoft-AIC/NCO-LLM
[resource-501]: https://arxiv.org/abs/2503.03239
[resource-502]: https://github.com/SHIXOOM/PAIR
[resource-503]: https://arxiv.org/abs/2512.03762
[resource-504]: https://arxiv.org/abs/2508.11850
[resource-505]: https://github.com/milad1378yz/EvoCut
[resource-506]: https://github.com/milad1378yz/sage
[resource-507]: https://proceedings.mlr.press/v235/liu24bs.html
[resource-508]: https://arxiv.org/abs/2401.02051
[resource-509]: https://github.com/FeiLiu36/EoH
[resource-510]: https://arxiv.org/abs/2412.17287
[resource-511]: https://arxiv.org/abs/2410.20848
[resource-512]: https://proceedings.iclr.cc/paper_files/paper/2024/hash/3339f19c5fcee3ad74502947a32be9e6-Abstract-Conference.html
[resource-513]: https://arxiv.org/abs/2309.03409
[resource-514]: https://github.com/google-deepmind/opro
[resource-515]: https://arxiv.org/abs/2409.04464
[resource-516]: https://proceedings.neurips.cc/paper_files/paper/2024/hash/4ced59d480e07d290b6f29fc8798f195-Abstract-Conference.html
[resource-517]: https://arxiv.org/abs/2402.01145
[resource-518]: https://github.com/ai4co/reevo
[resource-519]: https://arxiv.org/abs/2311.15249
[resource-520]: https://doi.org/10.1038/s41586-023-06924-6
[resource-521]: https://github.com/google-deepmind/funsearch
[resource-522]: https://arxiv.org/abs/2608.07407
[resource-523]: https://github.com/Shuvomoy/AutoOPT
[resource-524]: https://github.com/Shuvomoy/AutoOPT/tree/main/Lean-Related
[resource-525]: https://arxiv.org/abs/2605.17036
[resource-526]: https://arxiv.org/abs/2602.12631
[resource-527]: https://github.com/TianyiPeng/AI-human-inventory-game
[resource-528]: https://arxiv.org/abs/2604.04383
[resource-529]: https://aclanthology.org/2026.findings-acl.1417/
[resource-530]: https://arxiv.org/abs/2506.10764
[resource-531]: https://arxiv.org/abs/2605.08904
[resource-532]: https://arxiv.org/abs/2607.18147
[resource-533]: https://github.com/d2rojas/LLMs-Agents-For-SmartGrids-Code
[resource-534]: https://arxiv.org/abs/2505.12501
[resource-535]: https://arxiv.org/abs/2508.01724
[resource-536]: https://arxiv.org/abs/2407.11384
[resource-537]: https://github.com/zefang-liu/InvAgent
[resource-538]: https://arxiv.org/abs/2607.26710
[resource-539]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/f0c6c93e1dbff84daf6082fef7e1a094-Abstract-Conference.html
[resource-540]: https://arxiv.org/abs/2509.16865
[resource-541]: https://github.com/Summer142857/LLMCoSolver
[resource-542]: https://arxiv.org/abs/2503.01877
[resource-543]: https://github.com/starjob42/Starjob
[resource-544]: https://arxiv.org/abs/2508.11416
[resource-545]: https://arxiv.org/abs/2602.22465
[resource-546]: https://proceedings.mlr.press/v306/cao26z.html
[resource-547]: https://arxiv.org/abs/2605.27566
[resource-548]: https://dsbx7.github.io/
[resource-549]: https://arxiv.org/abs/2607.16777
[resource-550]: https://aclanthology.org/2026.findings-acl.1529/
[resource-551]: https://arxiv.org/abs/2602.02188
[resource-552]: https://arxiv.org/abs/2603.23004
[resource-553]: https://arxiv.org/abs/2603.16453
[resource-554]: https://doi.org/10.1109/PESGM52009.2025.11225826
[resource-555]: https://arxiv.org/abs/2407.05365
[resource-556]: https://arxiv.org/abs/2501.11968
[resource-557]: https://doi.org/10.1017/pds.2025.10234
[resource-558]: https://arxiv.org/abs/2411.12571
[resource-559]: https://arxiv.org/abs/2502.00828
[resource-560]: https://github.com/Yoontae6719/Decision-informed-Neural-Networks-with-Large-Language-Model-Integration-for-Portfolio-Optimization
[resource-561]: https://arxiv.org/abs/2504.14345
[resource-562]: https://advancesinfinancialai.com/#accepted-paper
[resource-563]: https://github.com/youngandbin/LLM-BLM
[resource-564]: https://github.com/ai4co/awesome-fm4co
[resource-565]: https://arxiv.org/abs/2508.14410v3
[resource-566]: https://arxiv.org/abs/2310.06116
[resource-567]: https://arxiv.org/abs/2407.19633
