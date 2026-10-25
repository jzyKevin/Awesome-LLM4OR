# Awesome LLM4OR

**English** | [简体中文](README.zh-CN.md)

A curated collection of papers, benchmarks, datasets, models, and tools for **Large Language Models for Operations Research**.

Research on LLMs for operations research, covering mathematical modeling, solver code, algorithm design, agents, training, and evaluation. Paper, code, model, and data links are listed on this page; Details opens the corresponding author, version, and resource notes below.

**Updated: 2026-10-25 · 235 papers.** A paper may appear in multiple modules; the total counts unique paper IDs.

**Reading the tables:** Browse methods by research task and resources by contribution type. Agent, RAG, SFT, RL, and MCTS are technique tags. Cross-module entries require independent contributions; each paper ID is counted once. Resource columns show available links.

**Reading tiers:** Core marks representative methods, foundational work, or important evaluation resources; Exploratory marks adjacent research such as open-ended mathematical modeling. Other entries are supplementary. Tiers guide reading rather than rank paper quality; see [Classification guide](#classification).

[Authors and versions](#paper-info) · [Classification guide](#classification)

<a id="contents"></a>

## Contents

- [Surveys](#surveys) (10 papers)
- [Getting started](#start-here)
- [Research methods](#research)
  - [Optimization modeling and code generation](#modeling) (83 papers)
  - [Model verification, diagnosis, and repair](#verification) (21 papers)
  - [Direct solution generation and optimization decisions](#direct-solving) (15 papers)
  - [Heuristic and algorithm discovery](#algorithms) (54 papers)
  - [Solver components and configuration](#solver-enhancement) (17 papers)
- [Benchmarks and evaluation](#benchmarks) (86 papers)
- [Models, data, and tools](#resources)
- [Techniques and topic index](#techniques)
- [Application index](#applications)
- [Related research](#adjacent) (9 papers)
- [Authors, versions, and resource notes](#paper-info)
- [Classification guide](#classification)
- [Scope and contributions](#contributing)

<a id="surveys"></a>

## Surveys

Surveys, systematic reviews, tutorials, and research frameworks.

| Year / Venue | Paper | Contribution summary | Contributions | Resources |
|---|---|---|---|---|
| 2026 · ACM Computing Surveys 58 (2026) | <a id="entry-lco2026review"></a>**Combinatorial Optimization Systematic Review**<br>Large Language Models for Combinatorial Optimization: A Systematic Review | Uses a PRISMA review process to organize LLM combinatorial optimization studies by tasks, architectures, evaluation data, and application domains. | Survey | [![Paper 1][b001]][r001] · [![Paper 2][b002]][r002] · [Details](#paper-lco2026review) |
| 2026 · ACM Computing Surveys 58(8), Article 218 | <a id="entry-liu2024systematic"></a>**LLM4AD Survey** (Core)<br>A Systematic Survey on Large Language Models for Algorithm Design | Surveys LLM algorithm design through four roles: optimizer, predictor, extractor, and designer. | Survey | [![Paper 1][b003]][r003] · [![Journal][b004]][r004] · [![Official resource repository (related)][b005]][r005] · [Details](#paper-liu2024systematic) |
| 2026 · MIPRO 2026 | <a id="entry-llmasopt2026"></a>**LLMs as Optimizers Survey**<br>Large Language Models as Optimizers: A Survey of Direct vs. Tool-Augmented Approaches and Their Performance Frontiers | Distinguishes direct optimization, tool-assisted optimization, and reusable-tool creation, comparing performance frontiers across the literature. | Survey | [![Publication][b006]][r006] · [![Paper 2][b002]][r007] · [Details](#paper-llmasopt2026) |
| 2026 · IEEE CIM (journal record) | <a id="entry-sysevo2025"></a>**LLMs for Evolutionary Optimization Survey**<br>A Systematic Survey on Large Language Models for Evolutionary Optimization: From Modeling to Solving | Surveys LLMs and evolutionary optimization from modeling to solving, distinguishing direct optimization, internal assistance, and high-level algorithm design. | Survey | [![Journal record][b007]][r008] · [![Paper 2][b002]][r009] · [![Literature Collection (related)][b008]][r010] · [Details](#paper-sysevo2025) |
| 2026 · arXiv preprint | <a id="entry-smartgrid2026"></a>**Smart Grids Agentic AI Tutorial**<br>LLMs and Agentic AI Systems for Smart Grids: A Tutorial on Architectures and Applications | Surveys smart-grid agent architectures and demonstrates trusted tools and explicit checks in charging, power-flow, and fault-diagnosis cases. | Survey · Application | [![Paper][b009]][r011] · [![Case-study Code][b010]][r012] · [Details](#paper-smartgrid2026) |
| 2025 · AAAI 2025 | <a id="entry-wasserkrug2024manifesto"></a>**DOCP Research Manifesto** (Core)<br>Enhancing Decision Making Through the Integration of Large Language Models and Operations Research Optimization | Sets out a business-user optimization-copilot vision and research needs in requirement clarification, model verification, and solving efficiency. | Survey · Foundational | [![Paper 1][b001]][r013] · [![Paper 2][b002]][r014] · [Details](#paper-wasserkrug2024manifesto) |
| 2025 · IJCAI 2025 Survey Track | <a id="entry-xiao2025survey"></a>**LLM4OR Survey** (Core)<br>A Survey of Optimization Modeling Meets LLMs: Progress and Future Directions | Surveys the optimization modeling pipeline, analyzes and annotates benchmark errors, and provides cleaned data and an evaluation portal. | Survey · Data | [![Paper][b009]][r015] · [![Official resource repository (related)][b005]][r016] · [![Cleaned Benchmarks][b011]][r017] · [Details](#paper-xiao2025survey) |
| 2025 · arXiv preprint | <a id="entry-wang2025lor"></a>**LLMs in OR: Methods & Challenges**<br>Large Language Models in Operations Research: Methods, Applications, and Challenges | Surveys LLM methods and applications in OR through automatic modeling, optimization assistance, and direct solving. | Survey | [![Paper][b009]][r018] · [Details](#paper-wang2025lor) |
| 2025 · arXiv preprint | <a id="entry-abedi2025thinkmath"></a>**Teaching LLMs to Think Mathematically**<br>Teaching LLMs to Think Mathematically: A Critical Study of Decision-Making via Optimization | Combines a systematic review and meta-analysis with comparisons of three prompting strategies on newly constructed network-optimization problems. | Survey · Evaluation analysis · Data | [![Paper][b009]][r019] · [Details](#paper-abedi2025thinkmath) |
| 2024 · arXiv preprint | <a id="entry-yu2024deep"></a>**LLM–EA Automated Optimization Insights**<br>Deep Insights into Automated Optimization with Large Language Models and Evolutionary Algorithms | Reviews automatic optimization with LLMs and evolutionary algorithms, analyzing representation, mutation, fitness, and prompt design. | Survey | [![Paper][b009]][r020] · [Details](#paper-yu2024deep) |

[Back to contents](#contents)

<a id="start-here"></a>

## Getting started

| Reading goal | Representative works |
|---|---|
| Field overview | [LLM4OR Survey](#entry-xiao2025survey) → [LLM4AD Survey](#entry-liu2024systematic) |
| Tasks and evaluation | [NL4Opt](#entry-ramamonjison2023nl4opt) → [Mamo](#entry-huang2024mamo) → [EquivaMap](#entry-zhai2025equivamap) |
| From descriptions to models and solvers | [Chain-of-Experts](#entry-xiao2024coe) → [OptiMUS](#entry-teshnizi2024optimus) → [OptiGuide](#entry-li2023optiguide) |
| Direct solution generation and optimization decisions | [LLMCoSolver / E2E CO Solver](#entry-jiang2025e2eco) → [Starjob](#entry-abgaryan2025starjob) → [OPRO](#entry-yang2024opro) |
| Automatic algorithm and heuristic design | [FunSearch](#entry-romera2023funsearch) → [EoH](#entry-liu2024eoh) → [ReEvo](#entry-ye2024reevo) |

<a id="research"></a>

## Research methods

Organized by research objective; a cross-task entry requires an independent contribution to that task.

<a id="code"></a>

<a id="modeling"></a>

### Optimization modeling and code generation

Turning requirements into mathematical models, structured representations, or solver programs, including interactive, CP, and dynamic-programming modeling.

#### Mathematical formulation and element extraction

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · ICML 2026 RLxF Workshop / arXiv | <a id="entry-autoor2026"></a>**AutoOR**<br>AutoOR: Scalably Post-training LLMs to Autoformulate Operations Research Problems | Synthesizes training examples from standard optimization forms and trains natural-language modeling through execution feedback and curriculum RL. | Method · Data · Model | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r021] · [![Paper 2][b002]][r022] · [Details](#paper-autoor2026) |
| 2026 · arXiv preprint | <a id="entry-coopa2026"></a>**COOPA**<br>COOPA: A Modular LLM Agent Architecture for Operations Research Problems | Iteratively compares formulation confidence, traces modeling-element provenance, and routes tasks to suitable solver agents. | Method | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | [![Paper][b009]][r023] · [![Code][b012]][r024] · [Details](#paper-coopa2026) |
| 2026 · AAAI 2026 | <a id="entry-xiao2026deepor"></a>**DeepOR**<br>DeepOR: A Deep Reasoning Foundation Model for Optimization Modeling | Uses flowcharts to guide long-chain-of-thought synthesis and SFT, followed by RL with solver-feedback rewards. | Method · Data | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) · [CoT / structured reasoning](#tech-cot) | [![Paper][b013]][r025] · [![Code][b012]][r026] · [![Official seeds and sample data][b014]][r027] · [Details](#paper-xiao2026deepor) |
| 2026 · arXiv preprint | <a id="entry-zhang2026dschellm"></a>**DScheLLM**<br>DScheLLM: Enabling Dynamic Scheduling through a Fine-Tuned Dual-System Large language Model | Synthesizes fast/slow-thinking demonstrations from solver schedules and LoRA-tunes a dual-system LLM for dynamic disruptions. | Method · Data · Model · Application | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) · [CoT / structured reasoning](#tech-cot) | [![Paper][b009]][r028] · [Details](#paper-zhang2026dschellm) |
| 2026 · arXiv preprint | <a id="entry-he2026evoopt"></a>**EvoOpt-LLM**<br>EvoOpt-LLM: Evolving industrial optimization models with large language models | Uses a 7B model and LoRA for industrial MILP modeling, new business-constraint injection, and variable pruning. | Method · Model | [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r029] · [![Code][b012]][r030] · [Details](#paper-he2026evoopt) |
| 2026 · NeurIPS 2026 (accepted; publication pending) | <a id="entry-evooptigraph2026"></a>**EvoOptiGraph**<br>EvoOptiGraph: Weakness-Driven Coevolution via Graph-Based Structural Generation for Optimization Modeling | Evolves structurally diverse MILPs as attributed bipartite graphs, using compilation, back-translation, SFT, and RLVR to target model weaknesses. | Method · Data · Model | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r031] · [![Paper 2][b002]][r032] · [Details](#paper-evooptigraph2026) |
| 2026 · arXiv preprint | <a id="entry-mind2026"></a>**MIND**<br>Automated Optimization Modeling via a Localizable Error-Driven Perspective | Synthesizes targeted training tasks from localized modeling errors and applies DFPO to locally revise difficult examples. | Method · Data · Model | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Preference optimization](#tech-preference) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r033] · [Details](#paper-mind2026) |
| 2026 · ICML 2026 · PMLR 306 | <a id="entry-optminer2026"></a>**Opt-Miner**<br>Opt-Miner: Empowering Information-Seeking Agent with Tree-Guided Data Synthesis for Optimization Modeling | Synthesizes optimization tasks with knowledge gaps in a tree structure and trains an actively retrieving modeling agent with R-GRPO. | Method · Data · Model | [Agent](#tech-agent) · [RAG](#tech-rag) · [Data synthesis](#tech-data-synthesis) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b013]][r034] · [![Reproduction Code (third-party)][b015]][r035] · [![Reproduction Results (third-party)][b016]][r036] · [![Demo (third-party)][b017]][r037] · [Details](#paper-optminer2026) |
| 2026 · arXiv preprint | <a id="entry-optiagent2026"></a>**OptiAgent**<br>OptiAgent: End-to-End Optimization Modeling via Multi-Agent Iterative Refinement | Uses a dedicated modeling agent and layered feedback loops to extract variables and constraints and repair formulations and executable code. | Method | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r038] · [Details](#paper-optiagent2026) |
| 2026 · ICLR 2026 | <a id="entry-wang2026orprm"></a>**OR-PRM**<br>OR-PRM: A Process Reward Model for Algorithmic Problem in Operations Research | Cleans existing synthetic data, builds OR-ProcessQA with MCTS and stepwise checks, and trains a process reward model for modeling reasoning. | Method · Data · Model | [Data synthesis](#tech-data-synthesis) · [MCTS](#tech-mcts) · [SFT / distillation](#tech-sft) · [Preference optimization](#tech-preference) · [Process rewards](#tech-prm) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b013]][r039] · [Details](#paper-wang2026orprm) |
| 2026 · AAAI 2026 | <a id="entry-ding2026orr1"></a>**OR-R1**<br>OR-R1: Automating Modeling and Solving of Operations Research Optimization Problem via Test-Time Reinforcement Learning | Applies SFT with limited labeled data, then learns from unlabeled problems and solution consistency through test-time TGRPO. | Method · Model | [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r040] · [![Paper 2][b002]][r041] · [![Code][b012]][r042] · [Details](#paper-ding2026orr1) |
| 2026 · Artificial Intelligence for Transportation 6 (2026) | <a id="entry-yang2025orthought"></a>**ORThought / LogiOR**<br>ORThought: Benchmarking and automating logistics optimization modeling via structured LLM reasoning | Guides structured two-agent reasoning with expert modeling principles and introduces the logistics modeling benchmark LogiOR. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [CoT / structured reasoning](#tech-cot) | [![Publication][b006]][r043] · [![Paper 2][b002]][r044] · [![Code][b012]][r045] · [![Dataset][b018]][r046] · [Details](#paper-yang2025orthought) |
| 2026 · ICML 2026 · PMLR 306 | <a id="entry-strategyaware2026"></a>**SAGE (Strategy-Aware Modeling)**<br>Strategy-Aware Optimization Modeling with Reasoning LLMs | Generates and filters multi-strategy modeling demonstrations, combining SFT and Segment-Weighted GRPO for correct formulations and efficient solving. | Method · Data · Model | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r047] · [![Paper 2][b002]][r048] · [![Code][b012]][r049] · [![SAGE SFT 100K][b019]][r050] · [Details](#paper-strategyaware2026) |
| 2026 · International Journal of Production Research (online 2026) | <a id="entry-li2025smilo"></a>**SMILO**<br>An LLM-powered MILP modelling engine for workforce scheduling guided by expert knowledge | Combines expert modeling graphs, LLM information extraction, and templates to generate workforce-scheduling MILPs. | Method · Application |  | [![Paper 1][b001]][r051] · [![Paper 2][b002]][r052] · [Details](#paper-li2025smilo) |
| 2025 · NeurIPS 2025 ScaleOpt Workshop / arXiv | <a id="entry-kong2025alphaopt"></a>**AlphaOPT**<br>AlphaOPT: Formulating Optimization Programs with Self-Improving LLM Experience Library | Distills solver feedback into an evolving, retrievable modeling experience library without updating LLM parameters. | Method | [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r053] · [![Paper 2][b002]][r054] · [![Code][b012]][r055] · [Details](#paper-kong2025alphaopt) |
| 2025 · ICML 2025 | <a id="entry-astorga2025autoformulation"></a>**Autoformulation** (Core)<br>Autoformulation of Mathematical Optimization Models Using LLMs | Searches candidate optimization models with MCTS, guided by symbolic pruning and LLM estimates of partial models. | Method | [MCTS](#tech-mcts) | [![Paper 1][b001]][r056] · [![arXiv][b020]][r057] · [![Code][b012]][r058] · [Details](#paper-astorga2025autoformulation) |
| 2025 · ACL 2025, Volume 1: Long Papers, pp. 821–838 | <a id="entry-wang2025bppsearch"></a>**BPP-Search / StructuredOR**<br>BPP-Search: Enhancing Tree of Thought Reasoning for Mathematical Modeling Problem Solving | Introduces BPP-Search, combining beam search, process reward models, and pairwise preferences in tree-of-thought reasoning. | Method · Benchmark · Data | [Tree / beam search](#tech-tree-search) · [Preference optimization](#tech-preference) · [Process rewards](#tech-prm) · [CoT / structured reasoning](#tech-cot) | [![Paper][b013]][r059] · [![Code][b012]][r060] · [![Dataset][b018]][r061] · [Details](#paper-wang2025bppsearch) |
| 2025 · arXiv preprint | <a id="entry-calm2025storm"></a>**CALM / STORM**<br>CALM Before the STORM: Unlocking Native Reasoning for Optimization Modeling | Revises reasoning traces with a small set of corrective prompts, then trains the STORM optimization modeling model through SFT and RL. | Method · Data · Model | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r062] · [Details](#paper-calm2025storm) |
| 2025 · arXiv preprint | <a id="entry-zhang2025optimind"></a>**OptiMind** (Core)<br>OptiMind: Teaching LLMs to Think Like Optimization Experts | Organizes expert error analyses by optimization problem class to guide training and inference and reduce common MILP formalization errors. | Method · Model | [SFT / distillation](#tech-sft) | [![Paper][b009]][r063] · [![Code][b012]][r064] · [![Model][b021]][r065] · [Details](#paper-zhang2025optimind) |
| 2025 · NeurIPS 2025 | <a id="entry-liu2025optitree"></a>**OptiTree** (Core)<br>OptiTree: Hierarchical Thoughts Generation with Tree Search for LLM Optimization Modeling | Uses hierarchical modeling tree search to decompose complex optimization tasks adaptively into reusable simpler modeling ideas. | Method | [Tree / beam search](#tech-tree-search) · [Memory](#tech-memory) | [![Publication][b006]][r066] · [![Paper 2][b002]][r067] · [![Code][b012]][r068] · [Details](#paper-liu2025optitree) |
| 2025 · arXiv preprint | <a id="entry-lima2025optitrust"></a>**OptiTrust**<br>Toward a Trustworthy Optimization Modeling Agent via Verifiable Synthetic Data Generation | Synthesizes demonstrations from symbolic problems with known optima and trains modeling agents with cross-language voting and stepwise reasoning. | Method · Data · Model | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r069] · [Details](#paper-lima2025optitrust) |
| 2025 · ICML 2025; PMLR 267:40769–40802 | <a id="entry-lu2025optmath"></a>**OptMATH** (Core)<br>OptMATH: A Scalable Bidirectional Data Synthesis Framework for Optimization Modeling | Synthesizes modeling data bidirectionally from mathematical models through problem data to natural language, filtered by forward modeling and rejection sampling. | Method · Benchmark · Data · Model | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b013]][r070] · [![Code][b012]][r071] · [![Model 7B][b022]][r072] · [![Model 32B][b023]][r073] · [![Dataset][b018]][r074] · [Details](#paper-lu2025optmath) |
| 2025 · Operations Research 73(6):2986–3009 | <a id="entry-huang2025orlm"></a>**ORLM** (Core)<br>ORLM: A Customizable Framework in Training Large Models for Automated Optimization Modeling | Trains optimization-domain models on OR-Instruct synthetic data and introduces the industrial benchmark IndustryOR. | Method · Benchmark · Data · Model | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b003]][r075] · [![Journal][b004]][r076] · [![Code][b012]][r077] · [![Model][b021]][r078] · [![IndustryOR][b024]][r079] · [![OR-Instruct-3K][b025]][r080] · [Details](#paper-huang2025orlm) |
| 2025 · ICLR 2025 | <a id="entry-yang2025resocratic"></a>**ReSocratic / OptiBench** (Core)<br>OptiBench Meets ReSocratic: Measure and Improve LLMs for Optimization Modeling | Synthesizes mathematical formulations and solution demonstrations before generating problems in reverse, alongside OptiBench and ReSocratic-29k. | Method · Benchmark · Data | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r081] · [![arXiv][b020]][r082] · [![Code][b012]][r083] · [Details](#paper-yang2025resocratic) |
| 2025 · Findings of EMNLP 2025 | <a id="entry-wu2025stepopt"></a>**Step-Opt**<br>Training LLMs for Optimization Modeling via Iterative Data Synthesis and Structured Validation | Progressively increases synthetic problem complexity, validates training data structurally, and fine-tunes optimization modeling models. | Method · Data · Model | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r084] · [![Paper 2][b002]][r085] · [![Code][b012]][r086] · [Details](#paper-wu2025stepopt) |
| 2024 · ICLR 2024 | <a id="entry-xiao2024coe"></a>**Chain-of-Experts** (Core)<br>Chain-of-Experts: When LLMs Meet Complex Operations Research Problems | Assigns OR expertise to agents coordinated by a conductor for forward reasoning and backward reflection on modeling and coding. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) · [CoT / structured reasoning](#tech-cot) | [![Paper][b013]][r087] · [![Code][b012]][r088] · [Details](#paper-xiao2024coe) |
| 2024 · INFOR 62 (2024) | <a id="entry-ahmed2024lm4opt"></a>**LM4OPT**<br>LM4OPT: Unveiling the potential of Large Language Models in formulating mathematical optimization problems | Adapts models to mathematical corpora before LP-modeling fine-tuning, using noisy embeddings for small models and comparing zero/one-shot prompts. | Method · Model · Evaluation analysis | [SFT / distillation](#tech-sft) | [![Paper 1][b001]][r089] · [![Paper 2][b002]][r090] · [Details](#paper-ahmed2024lm4opt) |
| 2024 · Constraints 29 (2024) | <a id="entry-dakle2023ner4opt"></a>**Ner4Opt**<br>Ner4Opt: named entity recognition for optimization modelling from natural language | Extracts variables, parameters, objectives, and constraints from optimization text, comparing lexical, semantic, fine-tuned, and language-model approaches. | Method · Model · Foundational | [SFT / distillation](#tech-sft) | [![Paper][b013]][r091] · [![Code][b012]][r092] · [![ner4opt-roberta-v1][b026]][r093] · [![ner4opt-roberta-v2][b027]][r094] · [![HF Demo (related)][b028]][r095] · [Details](#paper-dakle2023ner4opt) |
| 2024 · EMNLP 2024 System Demonstrations | <a id="entry-ju2024ttg"></a>**To the Globe / TTG**<br>To the Globe (TTG): Towards Language-Driven Guaranteed Travel Planning | Translates travel requirements into symbolic representations, then uses MILP to generate itineraries satisfying encoded constraints. | Method · Application · Model | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r096] · [![Paper 2][b002]][r097] · [Details](#paper-ju2024ttg) |
| 2023 · arXiv preprint | <a id="entry-alahakoon2023copilot"></a>**AI-Copilot for Business Optimisation**<br>Language Models for Business Optimisation with a Real World Case Study in Production Scheduling | Fine-tunes lower-cost LLMs to generate optimization formulations and evaluates them on a real production-scheduling case. | Method · Data · Model · Application | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r098] · [![Training Data][b029]][r099] · [![Generated Formulations (related)][b030]][r100] · [![Industrial Case Data][b031]][r101] · [![Industrial Outputs (related)][b032]][r102] · [![LPWP Evaluation Data (related)][b033]][r103] · [Details](#paper-alahakoon2023copilot) |
| 2023 · ICLR 2023 DL4C Workshop / arXiv | <a id="entry-synth2023"></a>**CodeT5 Mathematical Program Synthesis**<br>Synthesis of Mathematical programs from Natural Language Specifications | Augments training data with GPT-3 back-translation, fine-tunes CodeT5, and reranks and repairs candidates using LP rules. | Method · Model · Foundational | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r104] · [Details](#paper-synth2023) |
| 2023 · arXiv preprint | <a id="entry-li2023synthesizing"></a>**Multi-stage MILP Synthesis**<br>Synthesizing mixed-integer linear programming models from natural language descriptions | Synthesizes MILPs through variable identification, constraint/objective classification, and templates, extending NL4Opt with logical constraints and binary variables. | Method · Data | [SFT / distillation](#tech-sft) | [![Paper][b009]][r105] · [![Modeling Data][b034]][r106] · [Details](#paper-li2023synthesizing) |
| 2023 · arXiv preprint | <a id="entry-iflytek2023autoformulation"></a>**NL4Opt: Auto-Formulation Approach**<br>A Novel Approach for Auto-Formulation of Optimization Problems | Combines pretraining, adversarial training, prompting, and ensembling for NL4Opt entity recognition and formulation generation. | Method · Foundational | [SFT / distillation](#tech-sft) | [![Paper][b009]][r107] · [![Code][b012]][r108] · [Details](#paper-iflytek2023autoformulation) |
| 2023 · arXiv preprint; NL4Opt competition system | <a id="entry-wang2023opdnl4opt"></a>**OPD@NL4Opt**<br>OPD@NL4Opt: An ensemble approach for the NER task of the optimization problem | Uses differential learning rates, adversarial training, and ensembles of pretrained language models for optimization-description named entity recognition. | Method · Foundational | [SFT / distillation](#tech-sft) | [![Paper][b009]][r109] · [![Competition results (related)][b035]][r110] · [Details](#paper-wang2023opdnl4opt) |
| 2022 · EMNLP 2022 Industry | <a id="entry-ramamonjison2022augmenting"></a>**Auto-formulation (2022)** (Core)<br>Augmenting Operations Research with Auto-Formulation of Optimization Models From Problem Descriptions | Uses controlled generation to suggest optimization models from problem descriptions, with an interface for user validation and revision. | Method · Benchmark · Data · Foundational |  | [![Paper][b013]][r111] · [![Code & Data (NL4Opt)][b036]][r112] · [Details](#paper-ramamonjison2022augmenting) |

#### Solver code and domain languages

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-soliloquy2026"></a>**Agora-Opt**<br>From Soliloquy to Agora: Memory-Enhanced LLM Agents with Decentralized Debate for Optimization Modeling | Uses independent modeling teams and outcome-driven debate, with read/write memory to reuse solving experience and revisions arising from disagreements. | Method · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r113] · [![Code & Cleaned Data][b037]][r114] · [Details](#paper-soliloquy2026) |
| 2026 · LION 19 / LNCS 15745 (published 2026) | <a id="entry-lporch2025"></a>**CHORUS**<br>CHORUS: Zero-shot Hierarchical Retrieval and Orchestration for Generating Linear Programming Code | Supplies knowledge for Gurobi LP code generation through hierarchical document chunking, metadata retrieval, and reranking. | Method · Benchmark · Data | [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | [![Publication][b006]][r115] · [![Paper 2][b002]][r116] · [Details](#paper-lporch2025) |
| 2026 · arXiv preprint | <a id="entry-canonicalir2026"></a>**CIR / R2C**<br>Canonical Intermediate Representation for LLM-based optimization problem formulation and code generation | Encodes complex rules in a canonical intermediate representation before retrieving knowledge and generating constraint implementations. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r117] · [Details](#paper-canonicalir2026) |
| 2026 · arXiv preprint | <a id="entry-guan2026evom"></a>**EVOM**<br>Execution-Verified Reinforcement Learning for Optimization Modeling | Trains modeling LLMs with solver execution outcomes and studies transfer across Gurobi, OR-Tools, and COPT. | Method · Model | [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r118] · [Details](#paper-guan2026evom) |
| 2026 · arXiv preprint | <a id="entry-coevolve2026"></a>**EvoOR-Agent**<br>Co-evolving Agent Architectures and Interpretable Reasoning for Automated Optimization | Represents modeling–solving workflows as AOE graphs and co-evolves agent architectures with interpretable reasoning paths. | Method | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r119] · [Details](#paper-coevolve2026) |
| 2026 · arXiv preprint | <a id="entry-liang2026leanllmopt"></a>**LEAN-LLM-OPT**<br>Large-Scale Optimization Model Auto-Formulation: Harnessing LLM Flexibility via Structured Workflow | Builds modeling workflows dynamically and delegates data processing to tools for large-scale optimization and airline revenue management. | Method · Benchmark · Data · Application | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r120] · [![Code][b012]][r121] · [Details](#paper-liang2026leanllmopt) |
| 2026 · arXiv preprint | <a id="entry-zhao2026miniopt"></a>**MiniOpt**<br>MiniOpt: Reasoning to Model and Solve General Optimization Problems with Limited Resources | Connects modeling and code generation through structured reasoning, using hierarchical OptReward feedback on formulations and solutions. | Method · Model | [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) · [CoT / structured reasoning](#tech-cot) | [![Paper][b009]][r122] · [![Code][b012]][r123] · [Details](#paper-zhao2026miniopt) |
| 2026 · ICML 2026 · PMLR 306 | <a id="entry-nemo2026"></a>**NEMO**<br>NEMO: Execution-Aware Optimization Modeling via Autonomous Coding Agents | Uses autonomous coding agents to generate optimizers and simulators, refining models through cross-execution, experience reuse, and candidate consistency. | Method | [Agent](#tech-agent) · [Memory](#tech-memory) · [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r124] · [![Paper 2][b002]][r125] · [![Evaluation Artifacts][b038]][r126] · [Details](#paper-nemo2026) |
| 2026 · arXiv preprint | <a id="entry-xiu2026optgraph"></a>**OptGraph**<br>OptGraph: Large Language Models Enhanced Evolutionary Optimization Via Graph Retrieval-Augmented Generation | Organizes modeling patterns, formulations, implementations, and repairs in a typed graph, using neighborhood retrieval and execution-trace updates for modeling. | Method | [Agent](#tech-agent) · [Memory](#tech-memory) · [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r127] · [![Code][b012]][r128] · [Details](#paper-xiu2026optgraph) |
| 2026 · arXiv preprint | <a id="entry-dslmilp2026"></a>**OptiDSL**<br>Not All Problems Are Best Modeled as MILP: A DSL-Centric Framework for Flexible and Accurate Optimization Modeling | Maps natural language to domain DSLs and specialized solvers rather than forcing every problem into MILP. | Method · Benchmark · Data | [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r129] · [Details](#paper-dslmilp2026) |
| 2026 · Findings of EMNLP 2026 | <a id="entry-yang2026optskills"></a>**OptSkills**<br>OptSkills: Learning Generalizable Optimization Skills from Problem Archetypes via Cluster-Based Distillation | Clusters problem archetypes and distills, retrieves, and updates reusable workflow skills from successful modeling trajectories. | Method | [Agent](#tech-agent) · [Memory](#tech-memory) · [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | [![Publication][b006]][r130] · [![Paper 2][b002]][r131] · [![Code 1][b039]][r132] · [![Code 2][b040]][r133] · [![Official skill library (related)][b041]][r134] · [Details](#paper-yang2026optskills) |
| 2026 · NeurIPS 2026 (accepted; publication pending) | <a id="entry-lu2026pearl"></a>**PEARL** (Core)<br>PEARL: Solver-in-the-Loop Interactive Optimization Modeling from Natural Language | Executes, debugs, and revises optimization models through multi-turn tool use, training interactive modeling policies with solver feedback. | Method · Model | [Agent](#tech-agent) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b003]][r135] · [![Conference][b042]][r136] · [![Code][b012]][r137] · [![Model][b021]][r138] · [Details](#paper-lu2026pearl) |
| 2026 · arXiv preprint | <a id="entry-rlvrpagents2026"></a>**RLEA**<br>Reinforcement Learning Enhanced LLM Agents for Complex Vehicle Routing Problems | Trains a lightweight planner with Soft Q-learning to coordinate LLM agents, memory, and retrieval for complex VRP modeling. | Method · Application | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Memory](#tech-memory) · [RAG](#tech-rag) · [Auxiliary / NCO learning](#tech-auxiliary-learning) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r139] · [![Appendix (related)][b043]][r140] · [Details](#paper-rlvrpagents2026) |
| 2026 · arXiv preprint | <a id="entry-sdrl2026"></a>**SDRL**<br>LLMs as Adaptive Meta-Solvers: Strategy-Diverse RL for Industrial-Scale Optimization | Uses correctness-gated hierarchical diversity rewards to train adaptive choices among solvers, exact combinatorial algorithms, and heuristics. | Method · Data · Model | [Data synthesis](#tech-data-synthesis) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r141] · [![Benchmark Inference][b044]][r142] · [![SDRL Qwen3 4B][b045]][r143] · [Details](#paper-sdrl2026) |
| 2026 · arXiv preprint | <a id="entry-solid2026"></a>**SOLID**<br>Beyond Verified Answers: Solver-Informed Self-Distillation for Bootstrapping Operations Research Language Models | Clusters objectives from repeated solver rollouts into pseudo-references for ground-truth-free, solver-based self-distillation. | Method · Model | [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r144] · [![Code][b012]][r145] · [![SOLID-Qwen3][b046]][r146] · [![SOLID-StepORLM][b047]][r147] · [Details](#paper-solid2026) |
| 2026 · ICLR 2026 | <a id="entry-zhou2026steporlm"></a>**StepORLM** (Core)<br>StepORLM: A Self-Evolving Framework With Generative Process Supervision For Operations Research Language Models | Co-evolves a policy model and a generative process reward model using solver outcomes and full-trajectory assessment. | Method · Model | [LLM RL](#tech-llm-rl) · [Process rewards](#tech-prm) · [Execution / solver feedback](#tech-solver-feedback) · [CoT / structured reasoning](#tech-cot) | [![Paper 1][b001]][r148] · [![arXiv][b020]][r149] · [![Code][b012]][r150] · [![Policy 8B][b048]][r151] · [![GenPRM 8B][b049]][r152] · [Details](#paper-zhou2026steporlm) |
| 2025 · ICLR 2025 | <a id="entry-jiang2025droc"></a>**DRoC**<br>DRoC: Elevating Large Language Models for Complex Vehicle Routing via Decomposed Retrieval of Constraints | Decomposes complex VRP constraints, retrieves documents separately, and dynamically chooses RAG or self-debugging to generate solver programs. | Method · Data · Application | [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | [![Publication][b006]][r153] · [![Paper 2][b050]][r154] · [![Code][b012]][r155] · [Details](#paper-jiang2025droc) |
| 2025 · ICLR 2025 | <a id="entry-jiang2025llmopt"></a>**LLMOPT** (Core)<br>LLMOPT: Learning to Define and Solve General Optimization Problems from Scratch | Combines five-component formalization, multi-instruction tuning, and self-correction to generalize modeling and code generation across optimization tasks. | Method · Model | [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r156] · [![arXiv][b020]][r157] · [![Code][b012]][r158] · [![Model][b021]][r159] · [Details](#paper-jiang2025llmopt) |
| 2025 · NeurIPS 2025 Main Conference Track, volume 38 | <a id="entry-xie2025murka"></a>**MURKA**<br>MURKA: Multi-Reward Reinforcement Learning with Knowledge Alignment for Optimization Tasks | Aligns Extractor, Solver, and Checker agents through multi-reward RL and knowledge distillation for text-to-executable optimization programs. | Method | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b013]][r160] · [Details](#paper-xie2025murka) |
| 2025 · arXiv preprint | <a id="entry-thind2025optimai"></a>**OptimAI**<br>OptimAI: Optimization from Natural Language Using LLM-Powered AI Agents | Coordinates modeling, planning, coding, and code-critique roles, using UCB to schedule debugging and alternative plans. | Method | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r161] · [Details](#paper-thind2025optimai) |
| 2025 · arXiv preprint | <a id="entry-zhang2025bwor"></a>**OR-LLM-Agent / BWOR**<br>OR-LLM-Agent: Automating Modeling and Solving of Operations Research Optimization Problems with Reasoning LLM | Assigns modeling, code generation, and debugging to reasoning agents and introduces the BWOR evaluation set. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r162] · [![Code][b012]][r163] · [![Dataset][b018]][r164] · [Details](#paper-zhang2025bwor) |
| 2025 · ACL 2025 Industry Track | <a id="entry-ormind2025"></a>**ORMind**<br>ORMind: A Cognitive-Inspired End-to-End Reasoning Framework for Operations Research | Uses cognitively inspired role collaboration, execution-based repair, and counterfactual checks for optimization modeling. | Method | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r165] · [![Paper 2][b002]][r166] · [![Code][b012]][r167] · [Details](#paper-ormind2025) |
| 2025 · NeurIPS 2025 | <a id="entry-chen2025sirl"></a>**SIRL** (Core)<br>Solver-Informed RL: Grounding Large Language Models for Authentic Optimization Modeling | Checks code and LP instances with a solver to construct verifiable RL rewards, releasing models and revised evaluation data. | Method · Data · Model | [Data synthesis](#tech-data-synthesis) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r168] · [![arXiv][b020]][r169] · [![Code][b012]][r170] · [![Model Gurobi-7B][b051]][r171] · [![Model COPT-7B][b052]][r172] · [![Model Gurobi-32B][b053]][r173] · [![Model COPT-32B][b054]][r174] · [![Revised evaluation set][b055]][r175] · [Details](#paper-chen2025sirl) |
| 2025 · NeurIPS 2025 | <a id="entry-solverllm2025"></a>**SolverLLM**<br>SolverLLM: Leveraging Test-Time Scaling for Optimization Problem via LLM-Guided Search | Uses dynamically expanding MCTS to search formulations and solver code, guiding test-time exploration with prompts and uncertainty backpropagation. | Method | [MCTS](#tech-mcts) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r176] · [![Paper 2][b002]][r177] · [Details](#paper-solverllm2025) |
| 2025 · arXiv preprint | <a id="entry-nl2ps2025"></a>**Validation-in-the-Loop Power Modeling** (Exploratory)<br>From Natural Language to Solver-Ready Power System Optimization: An LLM-Assisted, Validation-in-the-Loop Framework | Generates power-system optimization models through domain prompts, structured schemas, feasibility checks, and iterative repair. | Method · Application | [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r178] · [Details](#paper-nl2ps2025) |
| 2024 · NeurIPS 2024 MATH-AI Workshop | <a id="entry-deng2024cafa"></a>**CAFA**<br>CAFA: Coding as Auto-Formulation Can Boost Large Language Models in Solving Linear Programming Problem | Uses compact prompts to generate Python programs that call optimization solvers for linear programming. | Method | [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b013]][r179] · [![Code][b012]][r180] · [Details](#paper-deng2024cafa) |
| 2024 · INFOR 62(4):599–617 | <a id="entry-mostajabdaveh2024multiagent"></a>**Multi-Stage Modeling & Verification**<br>Optimization modeling and verification from problem specifications using a multi-agent multi-stage LLM framework | Generates mathematical models and Zimpl code from specifications in stages, with cross-checks by multiple LLM agents. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b013]][r181] · [Details](#paper-mostajabdaveh2024multiagent) |
| 2024 · ICML 2024 | <a id="entry-teshnizi2024optimus"></a>**OptiMUS** (Core)<br>OptiMUS: Scalable Optimization Modeling with (MI)LP Solvers and Large Language Models | Uses modular agents for MILP modeling, code generation, debugging, and evaluation, and introduces NLP4LP. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r182] · [![arXiv][b020]][r183] · [![Code][b012]][r184] · [![Dataset][b018]][r185] · [Details](#paper-teshnizi2024optimus) |
| 2023 · arXiv preprint | <a id="entry-li2023power"></a>**LLMs for Power Engineering** (Exploratory)<br>LLM-based Frameworks for Power Engineering from Routine to Novel Tasks | Uses an end-to-end workflow for routine power-optimization coding and engineer-guided decomposition and code synthesis for novel tasks. | Method · Application | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r186] · [Details](#paper-li2023power) |

#### Interactive modeling and requirement changes

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-conversation2026"></a>**Interactive Optimization Conversations**<br>Let's Have a Conversation: Designing and Evaluating LLM Agents for Interactive Optimization | Uses decision agents with internal utility functions as stakeholders to evaluate multi-turn interactive optimization beyond single-answer quality. | Method · Data · Application | [Agent](#tech-agent) | [![Paper][b009]][r187] · [![Code][b012]][r188] · [Details](#paper-conversation2026) |
| 2026 · INFORMS Journal on Data Science 5(3):199–220 | <a id="entry-chen2025optichat"></a>**OptiChat**<br>OptiChat: Bridging Optimization Models and Practitioners with Large Language Models | Supports natural-language queries over existing optimization models for infeasibility diagnosis, sensitivity, what-if analysis, and counterfactual explanations. | Method · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r189] · [![Paper 2][b002]][r190] · [![Code][b012]][r191] · [Details](#paper-chen2025optichat) |
| 2025 · arXiv preprint | <a id="entry-askclarify2026"></a>**Ask, Clarify, Optimize**<br>Ask, Clarify, Optimize: Human-LLM Agent Collaboration for Smarter Inventory Control | Uses LLMs to clarify inventory needs and explain results, delegating stochastic optimization to algorithms and testing interaction with simulated managers. | Method · Model · Application | [Agent](#tech-agent) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r192] · [Details](#paper-askclarify2026) |
| 2025 · FedCSIS 2025 · ACSIS 43 | <a id="entry-kaleta2025cdss"></a>**C-DSS**<br>Toward Conversational Decision Support Systems: Integrating LLMs in the Operations Research Methodology | Proposes a conversational decision-support architecture comparing combinations of modeling, AMPL coding, RAG, and validation roles. | Method | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r193] · [![Paper 2][b050]][r194] · [Details](#paper-kaleta2025cdss) |
| 2024 · arXiv preprint | <a id="entry-jiao2024cityleo"></a>**City-LEO**<br>City-LEO: Toward Transparent City Management Using LLM with End-to-End Optimization | Narrows optimization scope through dialogue and combines prediction with optimization to manage shared e-bike operations. | Method · Application | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r195] · [![Data & Code][b056]][r196] · [Details](#paper-jiao2024cityleo) |
| 2024 · NAACL 2024 Industry Track | <a id="entry-zhang2024optllm"></a>**OptLLM**<br>Solving General Natural-Language-Description Optimization Problems with Large Language Models | Supports natural-language optimization through clarification, formulation/code conversion, external solvers, and explanations, with Qwen fine-tuning. | Method · Data · Model | [Agent](#tech-agent) · [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r197] · [![Paper 2][b002]][r198] · [![MindOpt Trial (International) (related)][b057]][r199] · [![MindOpt Trial (CN) (related)][b058]][r200] · [Details](#paper-zhang2024optllm) |
| 2024 · arXiv preprint | <a id="entry-tang2024ragdys"></a>**RAGDyS**<br>Automated Conversion of Static to Dynamic Scheduler via Natural Language | Uses retrieval-augmented generation to modify existing static scheduling models dynamically according to natural-language constraints. | Method · Application | [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r201] · [Details](#paper-tang2024ragdys) |
| 2023 · arXiv preprint | <a id="entry-li2023optiguide"></a>**OptiGuide** (Core)<br>Large Language Models for Supply Chain Optimization | Translates natural-language what-if queries into analyses of existing optimization programs to explain supply-chain decisions. | Method · Application | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r202] · [![Code][b012]][r064] · [Details](#paper-li2023optiguide) |

#### Stochastic and robust modeling

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-robustreform2026"></a>**AutoREM / AutoRO-Bench**<br>Automated Reformulation of Robust Optimization via Memory-Augmented Large Language Models | Uses failure-experience memory for deterministic reformulation of robust optimization and introduces AutoRO-Bench. | Method · Benchmark · Data | [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r203] · [Details](#paper-robustreform2026) |
| 2025 · arXiv preprint | <a id="entry-daopt2025"></a>**DAOpt / OptU**<br>DAOpt: Modeling and Evaluation of Data-Driven Optimization under Uncertainty with LLMs | Combines uncertainty modeling, multiple agents, and simulation to evaluate out-of-sample feasibility and robustness. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r204] · [Details](#paper-daopt2025) |
| 2025 · arXiv preprint | <a id="entry-llmsuc2025"></a>**LLM-SUC** (Exploratory)<br>Can Large Language Model Agents Balance Energy Systems? | Combines LLM agents with multi-scenario stochastic unit commitment for operational decisions under high wind-power uncertainty. | Method · Application | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r205] · [![Code][b012]][r206] · [Details](#paper-llmsuc2025) |
| 2025 · arXiv preprint | <a id="entry-talebi2025stochastic"></a>**LLMs for Stochastic Modeling**<br>Large Language Model-Based Automatic Formulation for Stochastic Optimization Models | Generates chance-constrained and two-stage stochastic programs through structured prompts, checking model structure with soft scores. | Method | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r207] · [![Code][b012]][r208] · [Details](#paper-talebi2025stochastic) |

#### Constraint programming

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · LLM4Code 2026 Workshop @ ICSE | <a id="entry-cpagent2025"></a>**CP-Agent**<br>CP-Agent: Agentic Constraint Programming | Executes and iteratively repairs constraint models with a persistent IPython kernel and concise domain prompts. | Method · Data | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r209] · [![Paper 2][b002]][r210] · [![Author Coding Agent (related)][b059]][r211] · [![Evaluation Archive v2][b060]][r212] · [Details](#paper-cpagent2025) |
| 2026 · arXiv preprint | <a id="entry-cpsync2026"></a>**CP-SynC**<br>CP-SynC: Multi-Agent Zero-Shot Constraint Modeling in MiniZinc with Synthesized Checkers | Uses modeling, checking, and selection agents to explore MiniZinc models in parallel and synthesizes semantic checkers to aggregate evidence. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r213] · [![Benchmark & Evaluation][b061]][r214] · [Details](#paper-cpsync2026) |
| 2026 · arXiv preprint | <a id="entry-roy2026rag"></a>**RAG for Optimization & CP Modeling**<br>Optimization and Constraint Modeling using LLMs with a Retrieval Augmented Generation Process | Synthesizes 500 problems from Text2Zinc seeds and role descriptions, using retrieved examples to generate optimization and constraint-model code. | Method · Data | [Data synthesis](#tech-data-synthesis) · [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r215] · [Details](#paper-roy2026rag) |
| 2026 · arXiv preprint | <a id="entry-text2model2026"></a>**Text2Model**<br>Text2Model: Modeling Copilots for Text-to-Model Translation | Provides multiple MiniZinc modeling copilots, an interactive editor, and an online leaderboard. | Method · Platform | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | [![Paper][b009]][r216] · [![Code][b012]][r217] · [![Text2Zinc (reused)][b062]][r218] · [![Editor (related)][b063]][r219] · [![Leaderboard (related)][b064]][r220] · [![Python Package (related)][b065]][r221] · [Details](#paper-text2model2026) |
| 2025 · arXiv preprint | <a id="entry-globalconstraint2025"></a>**Gala**<br>Gala: Global LLM Agents for Text-to-Model Translation | Assigns agents by global-constraint type and combines their outputs into complete MiniZinc models with an assembly agent. | Method | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | [![Paper][b009]][r222] · [![Gala in Text2Model][b066]][r217] · [![Author Project (related)][b067]][r223] · [Details](#paper-globalconstraint2025) |
| 2023 · arXiv preprint | <a id="entry-kadioglu2023holygrail"></a>**Holy Grail 2.0**<br>Holy Grail 2.0: From Natural Language to Constraint Models | Discusses decomposed prompting for natural-language-to-constraint modeling and reports early GPT results. | Method · Foundational |  | [![Paper][b009]][r224] · [Details](#paper-kadioglu2023holygrail) |

#### Dynamic programming

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2025 · arXiv preprint | <a id="entry-dpdlm2025"></a>**DPLM / DP-Bench**<br>Auto-Formulating Dynamic Programming Problems with Large Language Models | Introduces DP-Bench and bidirectionally reflected synthetic training data to train DPLM for natural-language-to-dynamic-programming modeling. | Method · Benchmark · Data · Model | [Data synthesis](#tech-data-synthesis) · [Reflection](#tech-reflection) · [SFT / distillation](#tech-sft) · [CoT / structured reasoning](#tech-cot) | [![Paper][b009]][r225] · [Details](#paper-dpdlm2025) |


[Back to contents](#contents)

<a id="verification"></a>

### Model verification, diagnosis, and repair

Verification, explanation, or repair as the research objective, distinguishing execution errors, infeasibility, mathematical equivalence, and behavioral diagnostics.

#### Execution debugging and code repair

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-mirror2026"></a>**MIRROR**<br>MIRROR: A Multi-Agent Framework with Iterative Adaptive Revision and Hierarchical Retrieval for Optimization Modeling in Operations Research | Retrieves modeling and code examples hierarchically and repairs optimization models through execution-driven iterative revision. | Method | [Agent](#tech-agent) · [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r226] · [Details](#paper-mirror2026) |

#### Infeasibility diagnosis and optimization explanations

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · INFORMS Journal on Data Science 5(3):199–220 | **OptiChat**<br>OptiChat: Bridging Optimization Models and Practitioners with Large Language Models | Supports natural-language queries over existing optimization models for infeasibility diagnosis, sensitivity, what-if analysis, and counterfactual explanations. | Method · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r189] · [![Paper 2][b002]][r190] · [![Code][b012]][r191] · [Details](#paper-chen2025optichat) |
| 2026 · arXiv preprint | <a id="entry-optirepair2026"></a>**OptiRepair** (Exploratory)<br>OptiRepair: Closed-Loop Diagnosis and Repair of Supply Chain Optimization Models with LLM Agents | Combines IIS analysis and operational plausibility checks in a two-stage supply-chain repair loop, introducing OptiRepair-SC and P1/P2 models. | Method · Benchmark · Data · Model · Application | [Agent](#tech-agent) · [LLM RL](#tech-llm-rl) · [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r227] · [Details](#paper-optirepair2026) |
| 2026 · ICML 2026 | <a id="entry-ao2026orloopbench"></a>**ORLoopBench**<br>ORLoopBench: Solver-in-the-Loop Benchmarks for Self-Correction and Behavioral Rationality in Operations Research | Defines infeasible-model repair loops using IIS and solver re-execution, with ORDebug and ORBias evaluations. | Method · Benchmark · Data · Model | [LLM RL](#tech-llm-rl) · [Process rewards](#tech-prm) · [Execution / solver feedback](#tech-solver-feedback) | [![Publication][b006]][r228] · [![Paper 2][b002]][r229] · [![Data and validation code][b068]][r230] · [Details](#paper-ao2026orloopbench) |
| 2025 · ICLR 2025 | <a id="entry-zhang2025decisioninfo"></a>**EOR / Decision Information**<br>Decision Information Meets Large Language Models: The Future of Explainable Operations Research | Uses what-if decision information and bipartite graphs to compare model changes and generate actionable optimization explanations. | Method · Benchmark · Data | [Agent](#tech-agent) | [![Paper 1][b001]][r231] · [![Paper 2][b002]][r232] · [![Code][b012]][r233] · [Details](#paper-zhang2025decisioninfo) |
| 2025 · arXiv preprint | <a id="entry-moid2025"></a>**MOID**<br>Multi-Objective Infeasibility Diagnosis for Routing Problems Using Large Language Models | Optimizes route cost and constraint violations jointly, then uses LLMs to analyze adjustments that could restore feasibility. | Method · Data · Application | [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r234] · [![Diagnosis Data][b069]][r235] · [Details](#paper-moid2025) |
| 2024 · INFOR 2024 | <a id="entry-chen2023diagnosing"></a>**OptiChat / Infeasibility Diagnosis**<br>Diagnosing Infeasible Optimization Problems Using Large Language Models | Combines GPT-4, solver IIS analysis, and a conversational interface to explain infeasibility and suggest model repairs. | Method | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b003]][r236] · [![Publication][b006]][r237] · [![Code][b012]][r191] · [Details](#paper-chen2023diagnosing) |

#### Equivalence and fidelity checks

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | **CP-SynC**<br>CP-SynC: Multi-Agent Zero-Shot Constraint Modeling in MiniZinc with Synthesized Checkers | Uses modeling, checking, and selection agents to explore MiniZinc models in parallel and synthesizes semantic checkers to aggregate evidence. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r213] · [![Benchmark & Evaluation][b061]][r214] · [Details](#paper-cpsync2026) |
| 2026 · arXiv preprint | <a id="entry-optarcus2026"></a>**OptArgus** (Exploratory)<br>OptArgus: A Multi-Agent System to Detect Hallucinations in LLM-based Optimization Modeling | Uses a hallucination taxonomy and expert agents to audit consistency among problem descriptions, mathematical models, and solver implementations. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | [![Paper][b009]][r238] · [Details](#paper-optarcus2026) |
| 2026 · Findings of ACL 2026 | <a id="entry-optiverse2026"></a>**OptiVerse / DVA-Agent**<br>OptiVerse: A Comprehensive Benchmark towards Optimization Problem Solving | Evaluates modeling and solving on 1,000 multi-paradigm optimization tasks, with dual-view auditing agents comparing requirements and code semantics. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | [![Paper 1][b001]][r239] · [![Paper 2][b002]][r240] · [![Inference, Auditor & Evaluation][b070]][r241] · [![OptiVerse 1K][b071]][r242] · [Details](#paper-optiverse2026) |
| 2026 · ICML 2026 · PMLR 306 | <a id="entry-ma2025sacopt"></a>**SAC-Opt**<br>SAC-Opt: Semantic Anchors for Iterative Correction in Optimization Modeling | Back-translates generated code into semantic anchors, aligns them with original requirements, and selectively repairs constraints and objectives. | Method | [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r243] · [![Paper 2][b002]][r244] · [![Code][b012]][r245] · [Details](#paper-ma2025sacopt) |
| 2026 · Findings of EMNLP 2026 | <a id="entry-bhattacharyya2026sover"></a>**SOVER / NLEquiv-150**<br>SOVER: Formal Certification of Optimization Reformulations via LLM-Assisted SMT Verification | Uses LLMs to extract reformulation mappings, then Z3 or dReal to verify feasibility and objective relationships between formulations. | Method · Benchmark · Data | [Formal verification](#tech-formal) | [![Publication][b006]][r246] · [![Paper 2][b002]][r247] · [![Code][b012]][r248] · [![EquivaFormulation (used for evaluation) (related)][b072]][r249] · [![NLP4LP (used for evaluation) (related)][b073]][r185] · [Details](#paper-bhattacharyya2026sover) |
| 2026 · ICML 2026 · PMLR 306 | <a id="entry-verisimpl2026"></a>**VeriSimpl**<br>VeriSimpl: Robust Optimization Modeling from Natural Language using Simplification-based Verification | Uses a solver to construct simplified diagnostic problems that help LLMs assess whether models match natural-language problem intent. | Method | [Execution / solver feedback](#tech-solver-feedback) | [![Publication][b006]][r250] · [![Paper 2][b002]][r251] · [![Conference][b042]][r252] · [![Project (related)][b074]][r253] · [Details](#paper-verisimpl2026) |
| 2025 · ICML 2025 | <a id="entry-zhai2025equivamap"></a>**EquivaMap** (Core)<br>EquivaMap: Leveraging LLMs for Automatic Equivalence Checking of Optimization Formulations | Uses LLMs to find decision-variable mappings for Quasi-Karp equivalence checks and introduces EquivaFormulation. | Method · Benchmark · Data |  | [![Paper 1][b001]][r254] · [![arXiv][b020]][r255] · [![Code][b012]][r256] · [![Dataset][b018]][r249] · [Details](#paper-zhai2025equivamap) |
| 2025 · arXiv; related ICML 2026 workshop version | <a id="entry-ding2026orgeval"></a>**ORGEval / Bench4Opt** (Core)<br>ORGEval: Graph-Theoretic Evaluation of LLMs in Optimization Modeling | Represents optimization formulations as graphs, evaluating structural equivalence through graph isomorphism and WL tests under symmetric decomposability conditions. | Method · Benchmark · Data |  | [![Paper][b009]][r257] · [![ICML workshop poster (related)][b075]][r258] · [Details](#paper-ding2026orgeval) |

#### Behavioral audits and perturbation diagnostics

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · Findings of EMNLP 2026 | <a id="entry-constraintinjection2026"></a>**Constraint Injection / VRPCoder**<br>Beyond Objective Equivalence: Constraint Injection for LLM-Based Optimization Modeling on Vehicle Routing Problems | Tests VRP code with feasible and single-constraint-violating solutions to detect missing constraints even when optimal values match. | Method · Benchmark · Data · Model · Application | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | [![Publication][b006]][r259] · [![Paper 2][b002]][r260] · [![Benchmark Data][b076]][r261] · [Details](#paper-constraintinjection2026) |
| 2026 · arXiv preprint | <a id="entry-li2026falsification"></a>**Falsification-Based Verification**<br>Falsification-Based Verification of LLM-Generated Optimization Models: Sound Test Batteries and Their Detection Limits | Tests generated models with numerical-role perturbations, duality, and sensitivity relations, characterizing detectable errors and blind spots. | Method | [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r262] · [Details](#paper-li2026falsification) |
| 2026 · ICML 2026 · PMLR 306 | **NEMO**<br>NEMO: Execution-Aware Optimization Modeling via Autonomous Coding Agents | Uses autonomous coding agents to generate optimizers and simulators, refining models through cross-execution, experience reuse, and candidate consistency. | Method | [Agent](#tech-agent) · [Memory](#tech-memory) · [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r124] · [![Paper 2][b002]][r125] · [![Evaluation Artifacts][b038]][r126] · [Details](#paper-nemo2026) |
| 2026 · arXiv preprint | <a id="entry-optiloop2026"></a>**OptiLoop**<br>OptiLoop: Coordination-in-the-Loop Verification and Repair for LLM-Generated Optimization Agents | Tests local optimization agents through bounded ADMM-style coordination, using behavioral and static evidence to repair code or formulations. | Method | [Agent](#tech-agent) · [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r263] · [Details](#paper-optiloop2026) |
| 2026 · NeurIPS 2026 (accepted; publication pending) | <a id="entry-lian2026reloop"></a>**ReLoop / RetailOpt-190** (Exploratory)<br>ReLoop: Structured Modeling and Behavioral Verification for Reliable LLM-Based Optimization | Combines structured modeling chains and solver parameter-perturbation checks to locate silent errors and perform diagnosis-guided repair. | Method · Benchmark · Data | [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b003]][r264] · [![Conference][b042]][r265] · [![Code][b012]][r266] · [![Dataset][b018]][r267] · [Details](#paper-lian2026reloop) |
| 2025 · ACL 2025 Industry Track | **ORMind**<br>ORMind: A Cognitive-Inspired End-to-End Reasoning Framework for Operations Research | Uses cognitively inspired role collaboration, execution-based repair, and counterfactual checks for optimization modeling. | Method | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r165] · [![Paper 2][b002]][r166] · [![Code][b012]][r167] · [Details](#paper-ormind2025) |


[Back to contents](#contents)

<a id="direct-solving"></a>

### Direct solution generation and optimization decisions

LLMs directly produce candidate solutions, schedules, numerical decisions, or operational policies. Solver-program generation belongs to modeling.

#### Discrete solutions and schedules

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | **DScheLLM**<br>DScheLLM: Enabling Dynamic Scheduling through a Fine-Tuned Dual-System Large language Model | Synthesizes fast/slow-thinking demonstrations from solver schedules and LoRA-tunes a dual-system LLM for dynamic disruptions. | Method · Data · Model · Application | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) · [CoT / structured reasoning](#tech-cot) | [![Paper][b009]][r028] · [Details](#paper-zhang2026dschellm) |
| 2026 · arXiv preprint | <a id="entry-infeasibilityaware2026"></a>**Infeasibility-Aware CO Models**<br>Infeasibility Aware Large Language Models for Combinatorial Optimization | Builds feasible/infeasible training examples with exact optimization and certified filtering, fine-tunes solution/infeasibility outputs, and assists local search. | Method · Data · Model | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r268] · [![Author Code / Data Archive (related)][b077]][r269] · [Details](#paper-infeasibilityaware2026) |
| 2026 · arXiv preprint | <a id="entry-jiang2026poweratlas"></a>**PowerAtlas / ECBench**<br>PowerAtlas: Feasibility-Aware Language Models for Electricity-Computing Co-Scheduling | Trains LLMs with feasibility feedback to generate electricity–computing co-schedules, introducing ECBench and deterministic scoring. | Method · Benchmark · Data · Model · Application | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r270] · [![Code & Sample Data][b078]][r271] · [Details](#paper-jiang2026poweratlas) |
| 2025 · NeurIPS 2025 | <a id="entry-jiang2025e2eco"></a>**LLMCoSolver / E2E CO Solver**<br>Large Language Models as End-to-end Combinatorial Optimization Solvers | Trains LLMs through SFT and feasibility/optimality-aware FOARL to output combinatorial optimization solutions directly from problem descriptions. | Method · Model · Data | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r272] · [![Paper 2][b002]][r273] · [![Code][b012]][r274] · [![SFT Data][b079]][r275] · [![RL Data][b080]][r276] · [Details](#paper-jiang2025e2eco) |
| 2025 · Proceedings of the Design Society 5 · ICED25 (2025) | <a id="entry-dsmco2024"></a>**LLMs for DSM Sequencing**<br>Large language models for combinatorial optimization of design structure matrix | Supplies network topology and domain knowledge to LLMs to iteratively search orderings for design structure matrices. | Method · Application |  | [![Paper 1][b001]][r277] · [![Paper 2][b002]][r278] · [Details](#paper-dsmco2024) |
| 2025 · arXiv preprint | <a id="entry-abgaryan2025starjob"></a>**Starjob**<br>Starjob: Dataset for LLM-Driven Job Shop Scheduling | Releases job-shop scheduling training data and uses LoRA to fine-tune LLMs to output schedules directly. | Method · Data · Model · Application | [SFT / distillation](#tech-sft) | [![Paper][b009]][r279] · [![Code][b012]][r280] · [![Dataset][b018]][r281] · [Details](#paper-abgaryan2025starjob) |
| 2025 · arXiv preprint | <a id="entry-bridgingviz2025"></a>**Visual Graph Optimization with MLLMs** (Exploratory)<br>Bridging Visualization and Optimization: Multimodal Large Language Models on Graph-Structured Combinatorial Optimization | Renders graph structures as images and combines multimodal LLMs with simple search for influence maximization, dismantling, and graph tasks. | Method · Evaluation analysis | [Multimodal input](#tech-multimodal) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r282] · [Details](#paper-bridgingviz2025) |
| 2024 · arXiv preprint | <a id="entry-wang2024raremip"></a>**Rare MIP Challenges**<br>Leveraging Large Language Models for Solving Rare MIP Challenges | Combines fine-tuning, chain-of-thought reasoning, and recursive dynamic temperatures to generate feasible solutions for rare MIP scenarios. | Method | [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) · [CoT / structured reasoning](#tech-cot) | [![Paper][b009]][r283] · [Details](#paper-wang2024raremip) |

#### Operational policies and interactive decisions

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-beergame2026"></a>**GenAI Beer Game Reliability**<br>Reliability and Effectiveness of Autonomous AI Agents in Supply Chain Management | Studies decision volatility in the multi-echelon Beer Game and compares reliability from RL post-training and operational guardrails. | Method · Evaluation analysis · Application | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [LLM RL](#tech-llm-rl) | [![Paper][b009]][r284] · [Details](#paper-beergame2026) |
| 2025 · arXiv preprint | <a id="entry-alas2025"></a>**ALAS**<br>ALAS: A Stateful Multi-LLM Agent Framework for Disruption-Aware Planning | Handles operational disruptions in schedules through role-based agents, persistent state, and history-aware local compensation. | Method · Application | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Memory](#tech-memory) | [![Paper][b009]][r285] · [Details](#paper-alas2025) |
| 2025 · arXiv (2026 revision) | <a id="entry-cao2025reflecsched"></a>**ReflecSched** (Exploratory)<br>ReflecSched: Solving Dynamic Flexible Job-Shop Scheduling via LLM-Powered Hierarchical Reflection | Distills strategic experience from multi-horizon heuristic simulations to guide dynamic flexible job-shop scheduling. | Method · Application | [Memory](#tech-memory) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r286] · [Details](#paper-cao2025reflecsched) |
| 2024 · arXiv preprint | <a id="entry-quan2024invagent"></a>**InvAgent** (Exploratory)<br>InvAgent: A Large Language Model based Multi-Agent System for Inventory Management in Supply Chains | Uses multiple zero-shot LLM agents to manage supply-chain inventory and adapt to changing demand. | Method · Application | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | [![Paper][b009]][r287] · [![Code][b012]][r288] · [Details](#paper-quan2024invagent) |
| 2024 · EMNLP 2024 Industry Track | <a id="entry-tang2024itinerary"></a>**ITINERA**<br>ItiNera: Integrating Spatial Optimization with Large Language Models for Open-domain Urban Itinerary Planning | Decomposes city-walk requests, selects points of interest, and uses cluster-aware spatial optimization for personalized itineraries. | Method · Application | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r289] · [![Paper 2][b002]][r290] · [![Code][b012]][r291] · [Details](#paper-tang2024itinerary) |

#### Numerical optimization and parameter decisions

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · Findings of ACL 2026 | <a id="entry-li2026optbench"></a>**OPT-BENCH / OPT-Agent**<br>OPT-BENCH: Evaluating the Iterative Self-Optimization of LLM Agents in Large-Scale Search Spaces | Evaluates iterative self-optimization on machine-learning tuning and NP problems, with OPT-Agent reusing historical feedback to revise solutions. | Method · Benchmark · Data | [Agent](#tech-agent) · [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r292] · [![Paper 2][b002]][r293] · [![Revised Preprint][b081]][r294] · [![Code][b012]][r295] · [![Dataset][b018]][r296] · [Details](#paper-li2026optbench) |
| 2024 · ICLR 2024 | <a id="entry-yang2024opro"></a>**OPRO** (Exploratory)<br>Large Language Models as Optimizers | Prompts LLMs with prior candidates and numerical evaluations to generate new solutions for direct optimization and prompt optimization. | Method · Foundational |  | [![Publication][b006]][r297] · [![Paper 2][b002]][r298] · [![Code][b012]][r299] · [Details](#paper-yang2024opro) |


[Back to contents](#contents)

<a id="algorithms"></a>

### Heuristic and algorithm discovery

Generating and improving complete algorithms, heuristic programs, neighborhood operators, or optimization methods.

#### Heuristic program discovery

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · ICML 2026 | <a id="entry-chen2026a2dept"></a>**A2DEPT**<br>A2DEPT: Large Language Model-Driven Automated Algorithm Design via Evolutionary Program Trees | Searches complete algorithms through tree-structured evolution, hybrid selection, and hierarchical operations, repairing programs with execution feedback. | Method | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Publication][b006]][r300] · [![Paper 2][b050]][r301] · [![Paper 3][b082]][r302] · [Details](#paper-chen2026a2dept) |
| 2026 · ICLR 2026 | <a id="entry-zhang2026afl"></a>**AFL**<br>An Agentic Framework with LLMs for Solving Complex Vehicle Routing Problems | Uses four specialized agents to autonomously generate and collaboratively repair solving programs from raw VRP inputs. | Method · Application | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Publication][b006]][r303] · [![Paper 2][b050]][r304] · [![Paper 3][b082]][r305] · [![Code][b012]][r306] · [Details](#paper-zhang2026afl) |
| 2026 · arXiv preprint | <a id="entry-invpolicy2026"></a>**Automated Inventory Policy Design**<br>Automated Design of Inventory Policy with Large Language Models: An Exploratory Study | Iteratively generates inventory-policy function classes with LLMs, then tunes each class with an external optimizer and cost feedback. | Method · Application | [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r307] · [Details](#paper-invpolicy2026) |
| 2026 · ICLR 2026 | <a id="entry-huang2025calm"></a>**CALM (Algorithm–LM Co-evolution)**<br>CALM: Co-evolution of Algorithms and Language Model for Automatic Heuristic Design | Uses generated-heuristic quality as an RL signal to co-evolve candidate algorithms and the underlying language model. | Method · Model | [Program evolution](#tech-evolution) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r308] · [![Paper 2][b002]][r309] · [![Code][b012]][r310] · [Details](#paper-huang2025calm) |
| 2026 · Inteligencia Artificial 29 (2026) | <a id="entry-co4all2025"></a>**Combinatorial Optimization for All**<br>Combinatorial Optimization for All: Using LLMs to Aid Non-Experts in Improving Optimization Algorithms | Uses prompts requiring limited expertise to improve ten existing TSP algorithms, comparing quality, runtime, and code complexity. | Method · Evaluation analysis | [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r311] · [![Paper 2][b050]][r312] · [![Paper 3][b082]][r313] · [![Prompts & Algorithms][b083]][r314] · [![Project (related)][b084]][r315] · [Details](#paper-co4all2025) |
| 2026 · arXiv preprint | <a id="entry-dsevolve2026"></a>**DSevolve**<br>DSevolve: Enabling Real-Time Adaptive Scheduling on Dynamic Flexible Job Shop with LLM-Evolved Heuristic Portfolios | Evolves a complementary scheduling-rule library offline and uses a state-conditioned neural selector to respond to flexible-job-shop disruptions online. | Method · Application | [Program evolution](#tech-evolution) · [Auxiliary / NCO learning](#tech-auxiliary-learning) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r316] · [Details](#paper-dsevolve2026) |
| 2026 · arXiv preprint | <a id="entry-epoch2026"></a>**EPOCH**<br>EPOCH: Coverage-Aware Evolution with Experiential Preference Optimization for LLM-based Automated Heuristic Design | Selects complementary heuristics by instance coverage and updates the generator with teacher-reflection preferences, DPO, and reflection self-distillation. | Method · Model | [Program evolution](#tech-evolution) · [Reflection](#tech-reflection) · [Preference optimization](#tech-preference) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r317] · [Details](#paper-epoch2026) |
| 2026 · ICIST 2026 (accepted) | <a id="entry-es2026ahd"></a>**ES-AHD**<br>ES-AHD: An Evolution Strategy Framework for Automatic Heuristic Design | Extracts semantic centers from elite programs and controls the search range with momentum-based temperature sampling. | Method | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b003]][r318] · [![Conference][b042]][r319] · [![Code][b012]][r320] · [Details](#paper-es2026ahd) |
| 2026 · ICLR 2026 | <a id="entry-chen2025hifoprompt"></a>**HiFo-Prompt**<br>HiFo-Prompt: Prompting with Hindsight and Foresight for LLM-based Automatic Heuristic Design | Accumulates heuristic-design principles in a hindsight knowledge pool and selects forward-looking search prompts by population dynamics. | Method | [Program evolution](#tech-evolution) · [Memory](#tech-memory) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r321] · [![Paper 2][b002]][r322] · [![Code][b012]][r323] · [Details](#paper-chen2025hifoprompt) |
| 2026 · arXiv preprint | <a id="entry-invevolve2026"></a>**InvEvolve** (Exploratory)<br>InvEvolve: Evolving White-Box Inventory Policies via Large Language Models with Performance Guarantees | Evolves white-box inventory policies with LLMs and studies safe deployment and improvement through confidence-interval certification. | Method · Application | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r324] · [Details](#paper-invevolve2026) |
| 2026 · arXiv preprint | <a id="entry-hsplo2026"></a>**LaGO**<br>Heuristic Search as Language-Guided Program Optimization | Separates heuristic discovery into execution evaluation, language feedback, and program updates, allowing components to improve independently. | Method | [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r325] · [Details](#paper-hsplo2026) |
| 2026 · LION 20 / 2026 (accepted) | <a id="entry-latentheuristic2026"></a>**Latent Heuristic Search**<br>Latent Heuristic Search: Continuous Optimization for Automated Algorithm Design | Learns program encodings, performance surrogates, invertible flows, and soft-prompt mappings to optimize continuous latent representations and decode heuristics. | Method | [Auxiliary / NCO learning](#tech-auxiliary-learning) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b003]][r326] · [![Conference][b042]][r327] · [![Code][b012]][r328] · [Details](#paper-latentheuristic2026) |
| 2026 · IEEE TEVC 30 (2026) | <a id="entry-ma2024llamoco"></a>**LLaMoCo**<br>LLaMoCo: Instruction Tuning of Large Language Models for Optimization Code Generation | Builds problem–optimization-code instructions and combines contrastive warm-up with instruction tuning to generate optimization programs from problem code. | Method · Model · Data | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r329] · [![Paper 2][b002]][r330] · [![LLaMoCo-S Example][b085]][r331] · [![LLaMoCo-S][b086]][r332] · [Details](#paper-ma2024llamoco) |
| 2026 · arXiv preprint | <a id="entry-efficientfrontier2026"></a>**LLM Agents for Efficient Frontiers**<br>LLM Agents for Combinatorial Efficient Frontiers: Investment Portfolio Optimization | Uses agents to automate heuristic development and efficient-frontier construction for cardinality-constrained mean–variance portfolios. | Method · Application | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r333] · [Details](#paper-efficientfrontier2026) |
| 2026 · arXiv preprint | <a id="entry-meevo2026"></a>**MeEvo**<br>MeEvo: Metacognitive Evolution Combined with Natural Evolution for Automatic Heuristic Design | Alternates code recombination/mutation with metacognitive reflection on reasoning history, feeding both stages into subsequent iterations. | Method | [Program evolution](#tech-evolution) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r334] · [![Code][b012]][r335] · [Details](#paper-meevo2026) |
| 2026 · Expert Systems with Applications 330 (December 2026 issue scheduled) | <a id="entry-chen2025mela"></a>**MeLA**<br>MeLA: A metacognitive LLM-driven architecture for automatic heuristic design | Evolves heuristic-generation prompts through problem analysis, error diagnosis, and metacognitive search rather than code mutation alone. | Method | [Program evolution](#tech-evolution) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r336] · [![Paper 2][b002]][r337] · [Details](#paper-chen2025mela) |
| 2026 · AAAI 2026 | <a id="entry-ha2025paretogrid"></a>**MPaGE**<br>Pareto-Grid-Guided Large Language Models for Fast and High-Quality Heuristics Design in Multi-Objective Combinatorial Optimization | Guides LLM heuristic evolution with Pareto-front grids and semantic clustering to balance multi-objective quality, speed, and diversity. | Method | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r338] · [![Paper 2][b002]][r339] · [![Code][b012]][r340] · [Details](#paper-ha2025paretogrid) |
| 2026 · ICML 2026 · PMLR 306 | <a id="entry-pathwise2026"></a>**PathWise**<br>PathWise: Planning through World Model for Automated Heuristic Design via Self-Evolving LLMs | Plans evolutionary actions on implication graphs preserving search history, coordinating policy, world-model, and critic agents for heuristic generation. | Method | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r341] · [![Paper 2][b002]][r342] · [![Code][b012]][r343] · [Details](#paper-pathwise2026) |
| 2026 · ICLR 2026 | <a id="entry-lange2026shinka"></a>**ShinkaEvolve**<br>ShinkaEvolve: Towards Open-Ended and Sample-Efficient Program Evolution | Combines parent sampling, novelty-based rejection sampling, and bandit model selection for more sample-efficient program evolution. | Method · Platform | [Program evolution](#tech-evolution) · [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r344] · [![Paper 2][b002]][r345] · [![Code][b012]][r346] · [Details](#paper-lange2026shinka) |
| 2026 · arXiv preprint | <a id="entry-chen2026tide"></a>**TIDE**<br>TIDE: Tuning-Integrated Dynamic Evolution for LLM-Based Automated Heuristic Design | Searches program structures with an outer island model, tunes numerical parameters through inner differential mutation, and schedules prompts with UCB. | Method | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r347] · [Details](#paper-chen2026tide) |
| 2025 · arXiv preprint | <a id="entry-li2025ars"></a>**ARS / RoutBench** (Core)<br>ARS: Automatic Routing Solver with Large Language Models | Generates constraint-aware routing heuristics from problem descriptions and introduces the multi-variant VRP benchmark RoutBench. | Method · Benchmark · Data | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r348] · [![Code][b012]][r349] · [Details](#paper-li2025ars) |
| 2025 · arXiv preprint | <a id="entry-bomer2025emerging"></a>**CEoH**<br>Leveraging Large Language Models to Develop Heuristics for Emerging Optimization Problems | Adds problem context to EoH prompts to discover heuristics for understudied tasks such as warehouse unit-load premarshalling. | Method · Application | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r350] · [![Code][b012]][r351] · [Details](#paper-bomer2025emerging) |
| 2025 · arXiv preprint | <a id="entry-viktorin2025ease"></a>**EASE**<br>Solve it with EASE | Supports algorithm evolution through modular generation, testing, analysis, and evaluation, with complementary roles for multiple LLMs. | Method · Platform | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r352] · [![Framework][b087]][r353] · [![Frontend][b088]][r354] · [Details](#paper-viktorin2025ease) |
| 2025 · arXiv preprint | <a id="entry-luo2025efs"></a>**EFS**<br>Evolutionary Factor Searching for Sparse Portfolio Optimization Using Large Language Models | Uses LLMs and evolutionary search to generate ranking factors, combining redundancy-aware weight allocation for sparse portfolios. | Method · Application | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r355] · [Details](#paper-luo2025efs) |
| 2025 · arXiv preprint | <a id="entry-ucfunsearch2025"></a>**FunSearch for Unit Commitment** (Exploratory)<br>Automated Heuristic Design for Unit Commitment Using Large Language Models | Applies LLM program search and evaluation to automatic design of unit-commitment heuristics. | Method · Application | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r356] · [Details](#paper-ucfunsearch2025) |
| 2025 · arXiv preprint | <a id="entry-yang2025heuragenix"></a>**HeurAgenix**<br>HeurAgenix: Leveraging LLMs for Solving Complex Combinatorial Optimization Challenges | Generates and evolves a heuristic library, then selects operators by problem state using a general LLM or a domain-tuned selector. | Method · Model | [Program evolution](#tech-evolution) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r357] · [![Code][b012]][r358] · [![CO Instances][b089]][r359] · [Details](#paper-yang2025heuragenix) |
| 2025 · AAAI 2025 | <a id="entry-dat2024hsevo"></a>**HSEvo**<br>HSEvo: Elevating Automatic Heuristic Design with Diversity-Driven Harmony Search and Genetic Algorithm Using LLMs | Analyzes heuristic evolution with diversity metrics and combines harmony search with genetic search to improve exploration. | Method · Evaluation analysis | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r360] · [![Paper 2][b002]][r361] · [![Code][b012]][r362] · [Details](#paper-dat2024hsevo) |
| 2025 · arXiv preprint | <a id="entry-zhang2025instspechh"></a>**InstSpecHH**<br>LLM-Driven Instance-Specific Heuristic Generation and Selection | Partitions instances by features, evolves specialized heuristics offline, and selects algorithms with LLMs or lightweight classifiers. | Method | [Program evolution](#tech-evolution) · [Auxiliary / NCO learning](#tech-auxiliary-learning) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r363] · [Details](#paper-zhang2025instspechh) |
| 2025 · IEEE CEC 2025 | <a id="entry-xie2025llmns"></a>**LHNS**<br>LLM-Driven Neighborhood Search for Efficient Heuristic Design | Organizes LLM rewrites as neighborhood search over heuristic programs, introducing three search strategies to reduce discovery cost. | Method | [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r364] · [![Paper 2][b050]][r365] · [![LLM4AD: LHNS][b090]][r366] · [Details](#paper-xie2025llmns) |
| 2025 · IEEE TEVC 29(2):331–345 | <a id="entry-vanstein2024llamea"></a>**LLaMEA** (Core)<br>LLaMEA: A Large Language Model Evolutionary Algorithm for Automatically Generating Metaheuristics | Uses LLMs to generate, mutate, and select metaheuristics, iteratively improving algorithms with execution-based feedback. | Method | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r367] · [![Code][b012]][r368] · [Details](#paper-vanstein2024llamea) |
| 2025 · arXiv preprint | <a id="entry-cetinkaya2025mipsmtt"></a>**LLM-discovered EDDC / MDDC**<br>Discovering Heuristics with Large Language Models (LLMs) for Mixed-Integer Programs: Single-Machine Scheduling | Uses LLM-driven evolution to discover EDDC and MDDC single-machine total-tardiness heuristics, comparing quality and runtime with classical rules. | Method · Application | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r369] · [![Code][b012]][r370] · [Details](#paper-cetinkaya2025mipsmtt) |
| 2025 · ICML 2025 | <a id="entry-zheng2025mctsahd"></a>**MCTS-AHD** (Core)<br>Monte Carlo Tree Search for Comprehensive Exploration in LLM-Based Automatic Heuristic Design | Organizes generated heuristics in an MCTS tree to explore the potential of candidates with initially low scores. | Method | [MCTS](#tech-mcts) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r371] · [![arXiv][b020]][r372] · [![Code][b012]][r373] · [Details](#paper-zheng2025mctsahd) |
| 2025 · AAAI 2025 | <a id="entry-yao2025meoh"></a>**MEoH**<br>Multi-Objective Evolution of Heuristic Using Large Language Model | Searches for Pareto heuristics across solution quality, efficiency, and scalability, selecting candidates by dominance and diversity. | Method | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r374] · [![Paper 2][b002]][r375] · [![LLM4AD: MEoH][b091]][r376] · [Details](#paper-yao2025meoh) |
| 2025 · ICLR 2025 Agentic AI Workshop | <a id="entry-tran2025llmneural"></a>**NCO-LLM for VRP**<br>Large Language Models powered Neural Solvers for Generalized Vehicle Routing Problems | Evolves LLM-generated structural biases for attention scores, then fine-tunes LEHD / POMO neural routing policies. | Method · Model · Application | [Program evolution](#tech-evolution) · [Auxiliary / NCO learning](#tech-auxiliary-learning) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b013]][r377] · [![Code][b012]][r378] · [Details](#paper-tran2025llmneural) |
| 2025 · arXiv preprint | <a id="entry-thach2025redahd"></a>**RedAHD**<br>RedAHD: Reduction-Based End-to-End Automatic Heuristic Design with Large Language Models | Uses LLMs to design problem and solution reductions to more familiar problems, then evolves solution heuristics. | Method | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r379] · [Details](#paper-thach2025redahd) |
| 2025 · arXiv preprint | <a id="entry-xu2025roco"></a>**RoCo**<br>RoCo: Role-Based LLMs Collaboration for Automatic Heuristic Design | Coordinates explorer, developer, critic, and integrator roles to generate, review, and revise heuristics. | Method | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r380] · [Details](#paper-xu2025roco) |
| 2025 · NeurIPS 2025 | <a id="entry-li2025strcmp"></a>**STRCMP**<br>STRCMP: Integrating Graph Structural Priors with Language Models for Combinatorial Optimization | Integrates graph-neural structural priors into language models, using training and evolution to generate solver-specific algorithm code. | Method · Model | [Program evolution](#tech-evolution) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Auxiliary / NCO learning](#tech-auxiliary-learning) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r381] · [![Paper 2][b002]][r382] · [![Code][b012]][r383] · [Details](#paper-li2025strcmp) |
| 2024 · ICML 2024 | <a id="entry-liu2024eoh"></a>**EoH** (Core)<br>Evolution of Heuristics: Towards Efficient Automatic Algorithm Design Using Large Language Model | Co-evolves natural-language heuristic ideas and executable code using performance feedback for automatic algorithm design. | Method · Foundational | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r384] · [![arXiv][b020]][r385] · [![Code][b012]][r386] · [Details](#paper-liu2024eoh) |
| 2024 · NeurIPS 2024 | <a id="entry-ye2024reevo"></a>**ReEvo** (Core)<br>ReEvo: Large Language Models as Hyper-Heuristics with Reflective Evolution | Combines evolutionary search and LLM reflection, using language feedback to improve hyper-heuristic programs. | Method | [Program evolution](#tech-evolution) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r387] · [![arXiv][b020]][r388] · [![Code][b012]][r389] · [Details](#paper-ye2024reevo) |
| 2023 · arXiv preprint | <a id="entry-liu2023ael"></a>**AEL** (Core)<br>Algorithm Evolution Using Large Language Model | Generates, selects, and rewrites algorithms with LLMs in an evolutionary loop, demonstrating algorithm-level evolution with TSP construction heuristics. | Method · Foundational | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r390] · [Details](#paper-liu2023ael) |
| 2023 · Nature (online 2023) | <a id="entry-romera2023funsearch"></a>**FunSearch** (Core)<br>Mathematical discoveries from program search with large language models | Combines LLM program generation, evolutionary search, and automated evaluation to discover mathematical constructions and bin-packing heuristics. | Method · Foundational | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b013]][r391] · [![Code][b012]][r392] · [Details](#paper-romera2023funsearch) |

#### Neighborhood and operator design

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-xie2026ailsahd"></a>**AILS-AHD**<br>Enhancing CVRP Solver through LLM-driven Automatic Heuristic Design | Evolves ruin heuristics within adaptive iterated local search, with LLM-assisted acceleration for CVRP solving. | Method · Application | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r393] · [Details](#paper-xie2026ailsahd) |
| 2026 · arXiv preprint | <a id="entry-yu2026alns"></a>**Full-Component ALNS Evolution**<br>Large Language Model-Driven Full-Component Evolution of Adaptive Large Neighborhood Search | Decomposes and evolves seven ALNS components, balancing solution quality and strategy diversity through a multidimensional elite archive. | Method | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r394] · [![Evolved ALNS (related)][b092]][r395] · [Details](#paper-yu2026alns) |
| 2026 · arXiv preprint | <a id="entry-zhao2026glns"></a>**G-LNS**<br>G-LNS: Generative Large Neighborhood Search for LLM-Based Automatic Heuristic Design | Co-evolves LNS destroy/repair operator pairs, using collaborative evaluation to capture their complementarity. | Method | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r396] · [![Code][b012]][r397] · [Details](#paper-zhao2026glns) |
| 2026 · NeurIPS 2026 (accepted; publication pending) | <a id="entry-yan2026pall"></a>**PALL**<br>Process-Aware LNS for Large-Scale MILP via Context-Enhanced Fine-Tuned LLM-driven Selector | Evolves LNS operator combinations offline and fine-tunes an 8B LLM selector on hindsight-oracle trajectories for online selection. | Method · Model | [Program evolution](#tech-evolution) · [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b013]][r398] · [Details](#paper-yan2026pall) |
| 2026 · AAMAS 2026 | <a id="entry-pyvrpplus2026"></a>**PyVRP+ / MEP**<br>PyVRP+: LLM-Driven Metacognitive Heuristic Evolution for Hybrid Genetic Search in Vehicle Routing Problems | Evolves routing-heuristic components in HGS through Reason–Act–Reflect diagnosis and design hypotheses. | Method · Application | [Reflection](#tech-reflection) · [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r399] · [![Paper 2][b002]][r400] · [![Proceedings][b093]][r401] · [Details](#paper-pyvrpplus2026) |
| 2026 · arXiv preprint | <a id="entry-lai2026specahd"></a>**SpecAHD**<br>SpecAHD: Localize to Specialize for Automated Heuristic Design in Large-Scale Routing Problems | Uses two-level search to select local repair regions and evolve complementary heuristic libraries adapted to regional differences. | Method · Application | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r402] · [Details](#paper-lai2026specahd) |
| 2026 · arXiv preprint | <a id="entry-spo2026"></a>**SPO**<br>SPO: Discovering Adaptive Large Neighborhood Search Operators via Stackelberg Program Optimization | Discovers state-dependent destroy/repair programs through a Stackelberg leader–follower formulation, co-updating program populations and the generator. | Method · Model · Application | [LLM RL](#tech-llm-rl) · [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r403] · [Details](#paper-spo2026) |
| 2026 · Transactions on Machine Learning Research (2026) | <a id="entry-vrpagent2025"></a>**VRPAgent**<br>VRPAgent: LLM-Driven Discovery of Heuristic Operators for Vehicle Routing Problems | Embeds LLM-generated routing operators in a shared LNS framework, improving candidates with code-length-penalized genetic search. | Method · Application | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r404] · [![Paper 2][b002]][r405] · [![Generated Operators (related)][b094]][r406] · [Details](#paper-vrpagent2025) |
| 2025 · ICML 2025 | <a id="entry-ye2025llmlns"></a>**LLM-LNS** (Core)<br>Large Language Model-driven Large Neighborhood Search for Large-Scale MILP Problems | Uses two-level self-evolving LLM agents to design LNS neighborhood policies and studies transfer to large-scale MILPs. | Method | [Agent](#tech-agent) · [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b013]][r407] · [![Code][b012]][r408] · [Details](#paper-ye2025llmlns) |
| 2025 · arXiv preprint | <a id="entry-ali2025pair"></a>**PAIR**<br>PAIR: A Novel Large Language Model-Guided Selection Strategy for Evolutionary Algorithms | Prompts LLMs to pair evolutionary individuals by fitness, diversity, and crossover compatibility, evaluated on TSP. | Method |  | [![Paper][b009]][r409] · [![Code][b012]][r410] · [Details](#paper-ali2025pair) |

#### General optimization algorithm design

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-autoopt2026"></a>**AutoOPT** (Exploratory)<br>A Domain-Specific Harness for End-to-End Automation of Optimization Research | Connects numerical-method design, LLM symbolic derivation, Lean 4 verification, and human interpretation to study optimal first-order algorithms. | Method · Platform | [Agent](#tech-agent) · [Formal verification](#tech-formal) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r411] · [![Code][b012]][r412] · [![Skills][b095]][r413] · [![Lean Proofs][b096]][r414] · [Details](#paper-autoopt2026) |
| 2026 · ICLR 2026 | <a id="entry-moh2025"></a>**MoH**<br>Generalizable Heuristic Generation Through LLMs with Meta-Optimization | Evolves self-invoking meta-optimization programs that construct heuristic optimizers to evolve heuristics for multiple downstream problems. | Method | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r415] · [![Paper 2][b002]][r416] · [![Code][b012]][r417] · [![CO Task Data][b097]][r418] · [Details](#paper-moh2025) |
| 2025 · Technical report | <a id="entry-novikov2025alphaevolve"></a>**AlphaEvolve** (Core)<br>AlphaEvolve: A coding agent for scientific and algorithmic discovery | Improves algorithms through LLM-driven evolutionary code changes, spanning scientific problems and computing infrastructure optimization. | Method | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r419] · [![Official results (related)][b098]][r420] · [![Official problem collection (related)][b099]][r421] · [Details](#paper-novikov2025alphaevolve) |


[Back to contents](#contents)

<a id="solver-enhancement"></a>

### Solver components and configuration

Improving cuts, branching, node selection, propagation, solver configurations, and the efficiency of existing formulations.

#### Cutting planes

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · IJCAI 2026 · AI4Tech | <a id="entry-zheng2026cutmgmt"></a>**LLM-guided Cutting-plane Management**<br>LLM-guided Cutting-plane Management for Mixed-integer Linear Programming | Combines instance-level separator configuration with solving-stage-aware cut selection to reduce manual MILP tuning. | Method | [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b013]][r422] · [![Code][b012]][r423] · [Details](#paper-zheng2026cutmgmt) |
| 2026 · arXiv preprint | <a id="entry-milpevo2026"></a>**MILP-Evo**<br>MILP-Evo: Closed-Loop Fully Automatic Design of MILP Solvers | Co-evolves cut-selection and branching callbacks in PySCIPOpt with execution-based repair, diagnostic reflection, and diversity maintenance. | Method | [Program evolution](#tech-evolution) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r424] · [Details](#paper-milpevo2026) |
| 2025 · arXiv (SAGE revision, 2026) | <a id="entry-yazdani2025evocut"></a>**SAGE / formerly EvoCut**<br>LLM-Guided Evolution of Symbolic Acceleration Inequality Families for MILP | Uses LLMs and evolutionary search to discover reusable MILP-accelerating inequalities, filtered by empirical acceptability and performance. | Method | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r425] · [![Code (earlier EvoCut)][b100]][r426] · [![Code (SAGE v3)][b101]][r427] · [Details](#paper-yazdani2025evocut) |

#### Branching and node selection

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-bife2026"></a>**BiFE**<br>BiFE: Search-Efficient Discovery of CPU-Only Branching Policies via LLM-based Bi-Fidelity Evolution | Prescreens branching rules with low-fidelity imitation scores, then runs high-fidelity branch-and-bound evaluation on elite candidates. | Method | [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r428] · [Details](#paper-bife2026) |
| 2026 · arXiv preprint | <a id="entry-chen2026evobb"></a>**Evo-B&B**<br>Evo-B&B: Behavior-Aware LLM-Guided Joint Evolution of Branching and Node Selection Policies for MILP | Co-evolves branching and node-selection policies using end-to-end SCIP feedback, preserving diversity through behavioral similarity. | Method | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r429] · [Details](#paper-chen2026evobb) |
| 2026 · ICML 2026 | <a id="entry-llm4branch2026"></a>**LLM4Branch** (Exploratory)<br>LLM4Branch: Large Language Model for Discovering Efficient Branching Policies of Integer Programs | Generates branching-policy program skeletons with LLMs and optimizes their parameters using end-to-end solving feedback. | Method | [Execution / solver feedback](#tech-solver-feedback) | [![Publication][b006]][r430] · [![Paper 2][b002]][r431] · [![Code][b012]][r432] · [Details](#paper-llm4branch2026) |

#### Solver configuration and algorithm selection

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-luo2026grimip"></a>**GRIMIP**<br>GRIMIP: A General Framework for Instance-Specific Configuration of MIP Solvers Using LLMs | Uses LLMs as probabilistic surrogates within Bayesian optimization to search solver configurations for individual MIP instances. | Method | [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r433] · [Details](#paper-luo2026grimip) |
| 2026 · NeurIPS 2026 MLxOR Workshop (accepted; event forthcoming) | <a id="entry-zhang2026autoconfig"></a>**LLM MIP Configuration**<br>Automating MIP Solver Configuration with Large Language Models | Iteratively proposes MIP parameter settings from solver feedback and aggregates them into problem-class configurations. | Method | [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b013]][r434] · [Details](#paper-zhang2026autoconfig) |
| 2026 · arXiv preprint | <a id="entry-warehouseformsel2026"></a>**Multi-Warehouse Formulation Selection**<br>Large Language Model for Operations Research Formulation Selection in Multi-Warehouse Inventory Allocation | Selects instance-appropriate MIP formulation experts for multi-warehouse inventory allocation, training the selector with solution-quality feedback. | Method · Model · Application | [SFT / distillation](#tech-sft) · [Preference optimization](#tech-preference) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r435] · [Details](#paper-warehouseformsel2026) |
| 2025 · CPAIOR 2025 | <a id="entry-lawless2024cuts"></a>**Cold-Start Separator Configuration**<br>LLMs for Cold-Start Cutting Plane Separator Configuration | Generates configurations from problem descriptions and separator documentation, clustering them into a compact configuration portfolio. | Method | [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b003]][r436] · [![Publication][b006]][r437] · [![Code][b012]][r438] · [Details](#paper-lawless2024cuts) |
| 2025 · EMNLP 2025 Main, pp. 19286–19304 | <a id="entry-yuan2025magts"></a>**MA-GTS / G-REAL**<br>MA-GTS: A Multi-Agent Framework for Solving Complex Graph Problems in Real-World Applications | Recovers structured graphs from implicit textual graph information and uses multiple agents to select algorithms by constraints and scale. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | [![Paper 1][b003]][r439] · [![Paper 2][b050]][r440] · [![Code][b012]][r441] · [Details](#paper-yuan2025magts) |

#### Reformulation and preprocessing

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | **EvoOpt-LLM**<br>EvoOpt-LLM: Evolving industrial optimization models with large language models | Uses a 7B model and LoRA for industrial MILP modeling, new business-constraint injection, and variable pruning. | Method · Model | [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r029] · [![Code][b012]][r030] · [Details](#paper-he2026evoopt) |
| 2026 · EMNLP 2026 | <a id="entry-yuan2026formuevo"></a>**FormuEvo**<br>FormuEvo: LLM-Guided Evolution for Discovering Solver-Efficient Mixed-Integer Programming Formulations | Evolves stronger MIP formulations in modeling-program space, guiding rewrites with solver-statistics diagnostics and structured memory. | Method | [Program evolution](#tech-evolution) · [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | [![Publication][b006]][r442] · [![Paper 2][b002]][r443] · [![Code][b012]][r444] · [Details](#paper-yuan2026formuevo) |

#### Propagation and other solver components

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-xu2026agenticmip"></a>**Agentic MIP Research**<br>Agentic MIP Research: Accelerated Constraint Handler Generation | Uses a solver-aware agent workspace to recover global-constraint structures and generate SCIP propagation-based constraint handlers. | Method | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r445] · [Details](#paper-xu2026agenticmip) |
| 2026 · Nature Communications (2026) | <a id="entry-sun2025satheur"></a>**AutoModSAT**<br>Discovering heuristics in a complex SAT solver with large language models | Combines modular SAT solvers, prompt optimization, and evolutionary search to discover effective heuristics within complex solvers. | Method · Data | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r446] · [![Paper 2][b002]][r447] · [![Code Archive][b102]][r448] · [![Evaluation Data][b103]][r449] · [Details](#paper-sun2025satheur) |
| 2026 · JAIR 86 (2026) | <a id="entry-sun2024autosat"></a>**AutoSAT**<br>AutoSAT: Automatically Optimize SAT Solvers via Large Language Models | Searches and replaces heuristics in a modular CDCL solver with LLM-generated code and iterative evaluation. | Method | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r450] · [![Paper 2][b002]][r451] · [![Code][b012]][r452] · [Details](#paper-sun2024autosat) |
| 2025 · arXiv preprint | <a id="entry-dheevo2025"></a>**DHEvo**<br>DHEvo: Data-Algorithm Based Heuristic Evolution for Generalizable MILP Solving | Co-evolves representative instances and diving heuristics to improve generalization within MILP instance classes. | Method | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r453] · [Details](#paper-dheevo2025) |


[Back to contents](#contents)

<a id="benchmarks"></a>

## Benchmarks and evaluation

Benchmarks, evaluation data, scoring protocols, and systematic evaluation analyses, grouped by evaluation target.

### Modeling and code-generation evaluation

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | **AutoREM / AutoRO-Bench**<br>Automated Reformulation of Robust Optimization via Memory-Augmented Large Language Models | Uses failure-experience memory for deterministic reformulation of robust optimization and introduces AutoRO-Bench. | Method · Benchmark · Data | [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r203] · [Details](#paper-robustreform2026) |
| 2026 · LION 19 / LNCS 15745 (published 2026) | **CHORUS**<br>CHORUS: Zero-shot Hierarchical Retrieval and Orchestration for Generating Linear Programming Code | Supplies knowledge for Gurobi LP code generation through hierarchical document chunking, metadata retrieval, and reranking. | Method · Benchmark · Data | [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | [![Publication][b006]][r115] · [![Paper 2][b002]][r116] · [Details](#paper-lporch2025) |
| 2026 · arXiv preprint | **CIR / R2C**<br>Canonical Intermediate Representation for LLM-based optimization problem formulation and code generation | Encodes complex rules in a canonical intermediate representation before retrieving knowledge and generating constraint implementations. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r117] · [Details](#paper-canonicalir2026) |
| 2026 · Findings of EMNLP 2026 | **Constraint Injection / VRPCoder**<br>Beyond Objective Equivalence: Constraint Injection for LLM-Based Optimization Modeling on Vehicle Routing Problems | Tests VRP code with feasible and single-constraint-violating solutions to detect missing constraints even when optimal values match. | Method · Benchmark · Data · Model · Application | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | [![Publication][b006]][r259] · [![Paper 2][b002]][r260] · [![Benchmark Data][b076]][r261] · [Details](#paper-constraintinjection2026) |
| 2026 · arXiv preprint | **CP-SynC**<br>CP-SynC: Multi-Agent Zero-Shot Constraint Modeling in MiniZinc with Synthesized Checkers | Uses modeling, checking, and selection agents to explore MiniZinc models in parallel and synthesizes semantic checkers to aggregate evidence. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r213] · [![Benchmark & Evaluation][b061]][r214] · [Details](#paper-cpsync2026) |
| 2026 · arXiv; NeurIPS 2026 workshop version | <a id="entry-wang2026formalize"></a>**Formalize, Don't Optimize**<br>Formalize, Don't Optimize: The Heuristic Trap in LLM-Generated Combinatorial Solvers | Uses CP-SynC-XL to compare native search, Python solver APIs, and MiniZinc, auditing errors introduced by search optimization. | Benchmark · Data |  | [![Paper 1][b003]][r454] · [![Workshop][b104]][r455] · [Details](#paper-wang2026formalize) |
| 2026 · arXiv preprint | <a id="entry-jorbench2026"></a>**JOR-Bench**<br>JOR-Bench: Japanese Operations Research Benchmarks for Large Language Models | Translates five existing English OR evaluation sets into Japanese to compare cross-language modeling and solving. | Benchmark · Data |  | [![Paper][b009]][r456] · [![Japanese / English OR Data][b105]][r457] · [Details](#paper-jorbench2026) |
| 2026 · arXiv preprint | **LEAN-LLM-OPT**<br>Large-Scale Optimization Model Auto-Formulation: Harnessing LLM Flexibility via Structured Workflow | Builds modeling workflows dynamically and delegates data processing to tools for large-scale optimization and airline revenue management. | Method · Benchmark · Data · Application | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r120] · [![Code][b012]][r121] · [Details](#paper-liang2026leanllmopt) |
| 2026 · ICML 2026 | <a id="entry-li2026miplibnl"></a>**MIPLIB-NL** (Core)<br>Constructing Industrial-Scale Optimization Modeling Benchmark | Recovers reusable structures from real MIPLIB 2017 MILPs, separating problems from data to build a natural-language modeling benchmark. | Benchmark · Data |  | [![Publication][b006]][r458] · [![Paper 2][b002]][r459] · [![Code][b012]][r460] · [![GitHub dataset][b106]][r461] · [Details](#paper-li2026miplibnl) |
| 2026 · NeurIPS 2026 (accepted; publication pending) | <a id="entry-zhu2026mmoptbench"></a>**MM-OptBench**<br>MM-OptBench: A Solver-Grounded Benchmark for Multimodal Optimization Modeling | Evaluates optimization formulation and solver-code generation from text and visual inputs including tables, graphs, and maps. | Benchmark · Data | [Multimodal input](#tech-multimodal) | [![Paper 1][b001]][r462] · [![Paper 2][b002]][r463] · [Details](#paper-zhu2026mmoptbench) |
| 2026 · ICML 2026 · PMLR 306 | <a id="entry-chen2026optengine"></a>**OPT-Engine**<br>OPT-Engine: Benchmarking the Limits of LLMs in Optimization Modeling via Complexity Scaling | Varies OR problem complexity controllably to compare textual reasoning, tool use, and solver integration. | Benchmark · Data |  | [![Paper 1][b001]][r464] · [![Paper 2][b002]][r465] · [![Code][b012]][r466] · [![Dataset][b018]][r467] · [Details](#paper-chen2026optengine) |
| 2026 · arXiv preprint | **OptiDSL**<br>Not All Problems Are Best Modeled as MILP: A DSL-Centric Framework for Flexible and Accurate Optimization Modeling | Maps natural language to domain DSLs and specialized solvers rather than forcing every problem into MILP. | Method · Benchmark · Data | [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r129] · [Details](#paper-dslmilp2026) |
| 2026 · Findings of ACL 2026 | **OptiVerse / DVA-Agent**<br>OptiVerse: A Comprehensive Benchmark towards Optimization Problem Solving | Evaluates modeling and solving on 1,000 multi-paradigm optimization tasks, with dual-view auditing agents comparing requirements and code semantics. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | [![Paper 1][b001]][r239] · [![Paper 2][b002]][r240] · [![Inference, Auditor & Evaluation][b070]][r241] · [![OptiVerse 1K][b071]][r242] · [Details](#paper-optiverse2026) |
| 2026 · Artificial Intelligence for Transportation 6 (2026) | **ORThought / LogiOR**<br>ORThought: Benchmarking and automating logistics optimization modeling via structured LLM reasoning | Guides structured two-agent reasoning with expert modeling principles and introduces the logistics modeling benchmark LogiOR. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [CoT / structured reasoning](#tech-cot) | [![Publication][b006]][r043] · [![Paper 2][b002]][r044] · [![Code][b012]][r045] · [![Dataset][b018]][r046] · [Details](#paper-yang2025orthought) |
| 2026 · ICML 2026 | <a id="entry-shen2026proopf"></a>**ProOPF**<br>ProOPF: Benchmarking and Improving LLMs for Professional-Grade Power Systems Optimization Modeling | Introduces professional optimal-power-flow modeling data and benchmarks, distinguishing parameter changes from structural extensions. | Benchmark · Data · Application |  | [![Publication][b006]][r468] · [![Paper 2][b050]][r469] · [![Paper 3][b082]][r470] · [![Evaluation Code & Data][b107]][r471] · [Details](#paper-shen2026proopf) |
| 2026 · NeurIPS 2026 (accepted; publication pending) | **ReLoop / RetailOpt-190** (Exploratory)<br>ReLoop: Structured Modeling and Behavioral Verification for Reliable LLM-Based Optimization | Combines structured modeling chains and solver parameter-perturbation checks to locate silent errors and perform diagnosis-guided repair. | Method · Benchmark · Data | [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b003]][r264] · [![Conference][b042]][r265] · [![Code][b012]][r266] · [![Dataset][b018]][r267] · [Details](#paper-lian2026reloop) |
| 2025 · ACL 2025, Volume 1: Long Papers, pp. 821–838 | **BPP-Search / StructuredOR**<br>BPP-Search: Enhancing Tree of Thought Reasoning for Mathematical Modeling Problem Solving | Introduces BPP-Search, combining beam search, process reward models, and pairwise preferences in tree-of-thought reasoning. | Method · Benchmark · Data | [Tree / beam search](#tech-tree-search) · [Preference optimization](#tech-preference) · [Process rewards](#tech-prm) · [CoT / structured reasoning](#tech-cot) | [![Paper][b013]][r059] · [![Code][b012]][r060] · [![Dataset][b018]][r061] · [Details](#paper-wang2025bppsearch) |
| 2025 · ECAI 2025 | <a id="entry-michailidis2025cpbench"></a>**CP-Bench / DCP-Bench-Open**<br>CP-Bench: Evaluating Large Language Models for Constraint Modelling | Evaluates LLM constraint modeling across discrete combinatorial domains, with ongoing extensions in DCP-Bench-Open. | Benchmark · Data |  | [![Paper 1][b003]][r472] · [![Related version][b108]][r473] · [![Publication][b006]][r474] · [![Code (current extension)][b109]][r475] · [![Dataset (archived original)][b110]][r476] · [![Archived original CP-Bench][b111]][r477] · [Details](#paper-michailidis2025cpbench) |
| 2025 · arXiv preprint | **DAOpt / OptU**<br>DAOpt: Modeling and Evaluation of Data-Driven Optimization under Uncertainty with LLMs | Combines uncertainty modeling, multiple agents, and simulation to evaluate out-of-sample feasibility and robustness. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r204] · [Details](#paper-daopt2025) |
| 2025 · arXiv preprint | **DPLM / DP-Bench**<br>Auto-Formulating Dynamic Programming Problems with Large Language Models | Introduces DP-Bench and bidirectionally reflected synthetic training data to train DPLM for natural-language-to-dynamic-programming modeling. | Method · Benchmark · Data · Model | [Data synthesis](#tech-data-synthesis) · [Reflection](#tech-reflection) · [SFT / distillation](#tech-sft) · [CoT / structured reasoning](#tech-cot) | [![Paper][b009]][r225] · [Details](#paper-dpdlm2025) |
| 2025 · ICLR 2025 | **DRoC**<br>DRoC: Elevating Large Language Models for Complex Vehicle Routing via Decomposed Retrieval of Constraints | Decomposes complex VRP constraints, retrieves documents separately, and dynamically chooses RAG or self-debugging to generate solver programs. | Method · Data · Application | [RAG](#tech-rag) · [Execution / solver feedback](#tech-solver-feedback) | [![Publication][b006]][r153] · [![Paper 2][b050]][r154] · [![Code][b012]][r155] · [Details](#paper-jiang2025droc) |
| 2025 · Findings NAACL 2025 | <a id="entry-huang2024mamo"></a>**Mamo** (Core)<br>LLMs for Mathematical Modeling: Towards Bridging the Gap between Natural and Mathematical Languages | Introduces Mamo for solver-assisted process evaluation of language-to-mathematical modeling across LP, MILP, and ODE tasks. | Benchmark · Data |  | [![Paper 1][b003]][r478] · [![Paper 2][b050]][r479] · [![Code][b012]][r480] · [![Dataset (third-party mirror)][b112]][r481] · [Details](#paper-huang2024mamo) |
| 2025 · ICML 2025; PMLR 267:40769–40802 | **OptMATH** (Core)<br>OptMATH: A Scalable Bidirectional Data Synthesis Framework for Optimization Modeling | Synthesizes modeling data bidirectionally from mathematical models through problem data to natural language, filtered by forward modeling and rejection sampling. | Method · Benchmark · Data · Model | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b013]][r070] · [![Code][b012]][r071] · [![Model 7B][b022]][r072] · [![Model 32B][b023]][r073] · [![Dataset][b018]][r074] · [Details](#paper-lu2025optmath) |
| 2025 · arXiv preprint | **OR-LLM-Agent / BWOR**<br>OR-LLM-Agent: Automating Modeling and Solving of Operations Research Optimization Problems with Reasoning LLM | Assigns modeling, code generation, and debugging to reasoning agents and introduces the BWOR evaluation set. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r162] · [![Code][b012]][r163] · [![Dataset][b018]][r164] · [Details](#paper-zhang2025bwor) |
| 2025 · Operations Research 73(6):2986–3009 | **ORLM** (Core)<br>ORLM: A Customizable Framework in Training Large Models for Automated Optimization Modeling | Trains optimization-domain models on OR-Instruct synthetic data and introduces the industrial benchmark IndustryOR. | Method · Benchmark · Data · Model | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b003]][r075] · [![Journal][b004]][r076] · [![Code][b012]][r077] · [![Model][b021]][r078] · [![IndustryOR][b024]][r079] · [![OR-Instruct-3K][b025]][r080] · [Details](#paper-huang2025orlm) |
| 2025 · AAAI 2025 | <a id="entry-mostajabdaveh2025orqa"></a>**ORQA**<br>Evaluating LLM Reasoning in the Operations Research Domain with ORQA | Uses OR expert-designed questions to evaluate modeling knowledge and multi-step reasoning. | Benchmark · Data |  | [![Proceedings][b093]][r482] · [![Paper 2][b002]][r483] · [![Code][b012]][r484] · [Details](#paper-mostajabdaveh2025orqa) |
| 2025 · ICLR 2025 | **ReSocratic / OptiBench** (Core)<br>OptiBench Meets ReSocratic: Measure and Improve LLMs for Optimization Modeling | Synthesizes mathematical formulations and solution demonstrations before generating problems in reverse, alongside OptiBench and ReSocratic-29k. | Method · Benchmark · Data | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r081] · [![arXiv][b020]][r082] · [![Code][b012]][r083] · [Details](#paper-yang2025resocratic) |
| 2025 · arXiv preprint | **Teaching LLMs to Think Mathematically**<br>Teaching LLMs to Think Mathematically: A Critical Study of Decision-Making via Optimization | Combines a systematic review and meta-analysis with comparisons of three prompting strategies on newly constructed network-optimization problems. | Survey · Evaluation analysis · Data |  | [![Paper][b009]][r019] · [Details](#paper-abedi2025thinkmath) |
| 2025 · arXiv preprint | <a id="entry-singirikonda2025text2zinc"></a>**Text2Zinc**<br>Text2Zinc: A Cross-Domain Dataset for Modeling Optimization and Satisfaction Problems in MiniZinc | Uses MiniZinc to represent natural-language constraint satisfaction and optimization problems uniformly. | Benchmark · Data |  | [![Paper][b009]][r485] · [![Dataset][b018]][r218] · [![Author project portal (related)][b113]][r223] · [Details](#paper-singirikonda2025text2zinc) |
| 2025 · Preprint | <a id="entry-parashar2025wiqor"></a>**WIQOR**<br>WIQOR: A dataset for what-if analysis of Operations Research problems | Evaluates natural-language what-if modifications to existing mathematical programming models. | Benchmark · Data |  | [![Paper PDF][b114]][r486] · [![Institution record][b115]][r487] · [Details](#paper-parashar2025wiqor) |
| 2024 · ICLR 2024 | **Chain-of-Experts** (Core)<br>Chain-of-Experts: When LLMs Meet Complex Operations Research Problems | Assigns OR expertise to agents coordinated by a conductor for forward reasoning and backward reflection on modeling and coding. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Reflection](#tech-reflection) · [Execution / solver feedback](#tech-solver-feedback) · [CoT / structured reasoning](#tech-cot) | [![Paper][b013]][r087] · [![Code][b012]][r088] · [Details](#paper-xiao2024coe) |
| 2024 · INFOR 62 (2024) | **LM4OPT**<br>LM4OPT: Unveiling the potential of Large Language Models in formulating mathematical optimization problems | Adapts models to mathematical corpora before LP-modeling fine-tuning, using noisy embeddings for small models and comparing zero/one-shot prompts. | Method · Model · Evaluation analysis | [SFT / distillation](#tech-sft) | [![Paper 1][b001]][r089] · [![Paper 2][b002]][r090] · [Details](#paper-ahmed2024lm4opt) |
| 2024 · INFOR 62(4):599–617 | **Multi-Stage Modeling & Verification**<br>Optimization modeling and verification from problem specifications using a multi-agent multi-stage LLM framework | Generates mathematical models and Zimpl code from specifications in stages, with cross-checks by multiple LLM agents. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b013]][r181] · [Details](#paper-mostajabdaveh2024multiagent) |
| 2024 · ICML 2024 | **OptiMUS** (Core)<br>OptiMUS: Scalable Optimization Modeling with (MI)LP Solvers and Large Language Models | Uses modular agents for MILP modeling, code generation, debugging, and evaluation, and introduces NLP4LP. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r182] · [![arXiv][b020]][r183] · [![Code][b012]][r184] · [![Dataset][b018]][r185] · [Details](#paper-teshnizi2024optimus) |
| 2023 · NeurIPS 2022 Competition Track / PMLR 220 | <a id="entry-ramamonjison2023nl4opt"></a>**NL4Opt** (Core)<br>NL4Opt Competition: Formulating Optimization Problems Based on Their Natural Language Descriptions | Splits natural-language optimization into entity recognition and intermediate-form generation, with LP word problems and a competition evaluation. | Benchmark · Data · Foundational |  | [![Paper 1][b001]][r488] · [![arXiv][b020]][r489] · [![Code][b012]][r112] · [Details](#paper-ramamonjison2023nl4opt) |
| 2022 · EMNLP 2022 Industry | **Auto-formulation (2022)** (Core)<br>Augmenting Operations Research with Auto-Formulation of Optimization Models From Problem Descriptions | Uses controlled generation to suggest optimization models from problem descriptions, with an interface for user validation and revision. | Method · Benchmark · Data · Foundational |  | [![Paper][b013]][r111] · [![Code & Data (NL4Opt)][b036]][r112] · [Details](#paper-ramamonjison2022augmenting) |

### Verification, explanation, and repair evaluation

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | **OptArgus** (Exploratory)<br>OptArgus: A Multi-Agent System to Detect Hallucinations in LLM-based Optimization Modeling | Uses a hallucination taxonomy and expert agents to audit consistency among problem descriptions, mathematical models, and solver implementations. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | [![Paper][b009]][r238] · [Details](#paper-optarcus2026) |
| 2026 · INFORMS Journal on Data Science 5(3):199–220 | **OptiChat**<br>OptiChat: Bridging Optimization Models and Practitioners with Large Language Models | Supports natural-language queries over existing optimization models for infeasibility diagnosis, sensitivity, what-if analysis, and counterfactual explanations. | Method · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r189] · [![Paper 2][b002]][r190] · [![Code][b012]][r191] · [Details](#paper-chen2025optichat) |
| 2026 · arXiv preprint | **OptiRepair** (Exploratory)<br>OptiRepair: Closed-Loop Diagnosis and Repair of Supply Chain Optimization Models with LLM Agents | Combines IIS analysis and operational plausibility checks in a two-stage supply-chain repair loop, introducing OptiRepair-SC and P1/P2 models. | Method · Benchmark · Data · Model · Application | [Agent](#tech-agent) · [LLM RL](#tech-llm-rl) · [Behavioral testing](#tech-behavioral) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r227] · [Details](#paper-optirepair2026) |
| 2026 · ICML 2026 | **ORLoopBench**<br>ORLoopBench: Solver-in-the-Loop Benchmarks for Self-Correction and Behavioral Rationality in Operations Research | Defines infeasible-model repair loops using IIS and solver re-execution, with ORDebug and ORBias evaluations. | Method · Benchmark · Data · Model | [LLM RL](#tech-llm-rl) · [Process rewards](#tech-prm) · [Execution / solver feedback](#tech-solver-feedback) | [![Publication][b006]][r228] · [![Paper 2][b002]][r229] · [![Data and validation code][b068]][r230] · [Details](#paper-ao2026orloopbench) |
| 2026 · Findings of EMNLP 2026 | **SOVER / NLEquiv-150**<br>SOVER: Formal Certification of Optimization Reformulations via LLM-Assisted SMT Verification | Uses LLMs to extract reformulation mappings, then Z3 or dReal to verify feasibility and objective relationships between formulations. | Method · Benchmark · Data | [Formal verification](#tech-formal) | [![Publication][b006]][r246] · [![Paper 2][b002]][r247] · [![Code][b012]][r248] · [![EquivaFormulation (used for evaluation) (related)][b072]][r249] · [![NLP4LP (used for evaluation) (related)][b073]][r185] · [Details](#paper-bhattacharyya2026sover) |
| 2025 · ICLR 2025 | **EOR / Decision Information**<br>Decision Information Meets Large Language Models: The Future of Explainable Operations Research | Uses what-if decision information and bipartite graphs to compare model changes and generate actionable optimization explanations. | Method · Benchmark · Data | [Agent](#tech-agent) | [![Paper 1][b001]][r231] · [![Paper 2][b002]][r232] · [![Code][b012]][r233] · [Details](#paper-zhang2025decisioninfo) |
| 2025 · ICML 2025 | **EquivaMap** (Core)<br>EquivaMap: Leveraging LLMs for Automatic Equivalence Checking of Optimization Formulations | Uses LLMs to find decision-variable mappings for Quasi-Karp equivalence checks and introduces EquivaFormulation. | Method · Benchmark · Data |  | [![Paper 1][b001]][r254] · [![arXiv][b020]][r255] · [![Code][b012]][r256] · [![Dataset][b018]][r249] · [Details](#paper-zhai2025equivamap) |
| 2025 · arXiv preprint | **MOID**<br>Multi-Objective Infeasibility Diagnosis for Routing Problems Using Large Language Models | Optimizes route cost and constraint violations jointly, then uses LLMs to analyze adjustments that could restore feasibility. | Method · Data · Application | [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r234] · [![Diagnosis Data][b069]][r235] · [Details](#paper-moid2025) |
| 2025 · arXiv; related ICML 2026 workshop version | **ORGEval / Bench4Opt** (Core)<br>ORGEval: Graph-Theoretic Evaluation of LLMs in Optimization Modeling | Represents optimization formulations as graphs, evaluating structural equivalence through graph isomorphism and WL tests under symmetric decomposability conditions. | Method · Benchmark · Data |  | [![Paper][b009]][r257] · [![ICML workshop poster (related)][b075]][r258] · [Details](#paper-ding2026orgeval) |

### Direct solving and decision evaluation

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-constraintbench2026"></a>**ConstraintBench**<br>ConstraintBench: Benchmarking LLM Constraint Reasoning on Direct Optimization | Requires structured solutions directly from LLMs, checking each constraint deterministically and comparing against Gurobi optima. | Benchmark · Data |  | [![Paper][b009]][r490] · [Details](#paper-constraintbench2026) |
| 2026 · ICML 2026 · PMLR 306 | <a id="entry-dynaschedbench2026"></a>**DynaSchedBench**<br>DynaSchedBench: Calibrated Dynamic Scheduling Benchmarks and Observability Paradox in LLM-based Scheduling Agents | Calibrates dynamic flexible-job-shop instance difficulty and unifies simulation, trajectory evaluation, and agent comparisons under different observations. | Method · Benchmark · Data · Application |  | [![Paper 1][b001]][r491] · [![Paper 2][b002]][r492] · [![Code][b012]][r493] · [![Project (related)][b084]][r494] · [Details](#paper-dynaschedbench2026) |
| 2026 · arXiv preprint | **GenAI Beer Game Reliability**<br>Reliability and Effectiveness of Autonomous AI Agents in Supply Chain Management | Studies decision volatility in the multi-echelon Beer Game and compares reliability from RL post-training and operational guardrails. | Method · Evaluation analysis · Application | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [LLM RL](#tech-llm-rl) | [![Paper][b009]][r284] · [Details](#paper-beergame2026) |
| 2026 · arXiv preprint | <a id="entry-invbench2026"></a>**InventoryBench**<br>AI Agents for Inventory Control: Human-LLM-OR Complementarity | Introduces inventory-decision benchmarks and human experiments to study complementarity among OR, LLMs, and human decisions. | Method · Benchmark · Data · Application |  | [![Paper][b009]][r495] · [![InventoryBench][b116]][r496] · [![Human–AI experiment platform][b117]][r497] · [Details](#paper-invbench2026) |
| 2026 · Findings of ACL 2026 | <a id="entry-jiang2026nlco"></a>**NLCO**<br>Reasoning in a Combinatorial and Constrained World: Benchmarking LLMs on Natural-Language Combinatorial Optimization | Evaluates direct discrete-solution generation from natural-language scenarios, analyzing variables, constraints, global structure, and objectives. | Benchmark · Data |  | [![Paper 1][b001]][r498] · [![Paper 2][b002]][r499] · [![Code][b012]][r500] · [![Dataset][b018]][r501] · [Details](#paper-jiang2026nlco) |
| 2026 · arXiv preprint | <a id="entry-opf2026reason"></a>**OPF Constrained Reasoning Study**<br>Can Large Language Models Reason and Optimize Under Constraints? | Tests direct reasoning and optimization on optimal power flow under structured inputs, arithmetic, and physical constraints. | Evaluation analysis |  | [![Paper][b009]][r502] · [Details](#paper-opf2026reason) |
| 2026 · arXiv preprint | **PowerAtlas / ECBench**<br>PowerAtlas: Feasibility-Aware Language Models for Electricity-Computing Co-Scheduling | Trains LLMs with feasibility feedback to generate electricity–computing co-schedules, introducing ECBench and deterministic scoring. | Method · Benchmark · Data · Model · Application | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r270] · [![Code & Sample Data][b078]][r271] · [Details](#paper-jiang2026poweratlas) |
| 2026 · arXiv preprint | <a id="entry-zhang2026retailbench"></a>**RetailBench**<br>RetailBench: Evaluating Long-Horizon Autonomous Decision-Making and Strategy Stability of LLM Agents in Realistic Retail Environments | Evaluates sustained decisions about pricing, replenishment, suppliers, and cash flow in a single-supermarket simulation. | Benchmark · Data · Platform |  | [![Paper][b009]][r503] · [![Code][b012]][r504] · [Details](#paper-zhang2026retailbench) |
| 2025 · arXiv preprint | <a id="entry-zhao2025aimbench"></a>**AIM-Bench**<br>AIM-Bench: Evaluating Decision-making Biases of Agentic LLM as Inventory Manager | Studies LLM-agent decision biases and information-sharing effects in uncertain inventory-replenishment experiments. | Benchmark · Data · Evaluation analysis |  | [![Paper][b009]][r505] · [Details](#paper-zhao2025aimbench) |
| 2025 · EMNLP 2025 Main, pp. 19286–19304 | **MA-GTS / G-REAL**<br>MA-GTS: A Multi-Agent Framework for Solving Complex Graph Problems in Real-World Applications | Recovers structured graphs from implicit textual graph information and uses multiple agents to select algorithms by constraints and scale. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | [![Paper 1][b003]][r439] · [![Paper 2][b050]][r440] · [![Code][b012]][r441] · [Details](#paper-yuan2025magts) |
| 2025 · arXiv preprint | **Visual Graph Optimization with MLLMs** (Exploratory)<br>Bridging Visualization and Optimization: Multimodal Large Language Models on Graph-Structured Combinatorial Optimization | Renders graph structures as images and combines multimodal LLMs with simple search for influence maximization, dismantling, and graph tasks. | Method · Evaluation analysis | [Multimodal input](#tech-multimodal) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r282] · [Details](#paper-bridgingviz2025) |

### Algorithm and solver-efficiency evaluation

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · Nature Communications (2026) | **AutoModSAT**<br>Discovering heuristics in a complex SAT solver with large language models | Combines modular SAT solvers, prompt optimization, and evolutionary search to discover effective heuristics within complex solvers. | Method · Data | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r446] · [![Paper 2][b002]][r447] · [![Code Archive][b102]][r448] · [![Evaluation Data][b103]][r449] · [Details](#paper-sun2025satheur) |
| 2026 · AAAI 2026 | <a id="entry-sun2026cobench"></a>**CO-Bench** (Core)<br>CO-Bench: Benchmarking Language Model Agents in Algorithm Search for Combinatorial Optimization | Provides a benchmark for combinatorial optimization algorithm search, comparing LLM agents with human-designed algorithms. | Benchmark · Data |  | [![Proceedings][b093]][r506] · [![Paper 2][b002]][r507] · [![Code][b012]][r508] · [![Dataset][b018]][r509] · [Details](#paper-sun2026cobench) |
| 2026 · Inteligencia Artificial 29 (2026) | **Combinatorial Optimization for All**<br>Combinatorial Optimization for All: Using LLMs to Aid Non-Experts in Improving Optimization Algorithms | Uses prompts requiring limited expertise to improve ten existing TSP algorithms, comparing quality, runtime, and code complexity. | Method · Evaluation analysis | [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r311] · [![Paper 2][b050]][r312] · [![Paper 3][b082]][r313] · [![Prompts & Algorithms][b083]][r314] · [![Project (related)][b084]][r315] · [Details](#paper-co4all2025) |
| 2026 · NeurIPS 2026 (accepted; publication pending) | <a id="entry-kong2026frontieror"></a>**FrontierOR**<br>FrontierOR: Benchmarking LLMs' Capacity for Efficient Algorithm Design in Large-Scale Optimization | Evaluates LLMs on generating efficient, feasible algorithms for large-scale, literature-driven OR tasks. | Benchmark · Data |  | [![Paper 1][b001]][r510] · [![Paper 2][b002]][r511] · [![Code][b012]][r512] · [![Dataset][b018]][r513] · [Details](#paper-kong2026frontieror) |
| 2026 · ICLR 2026 | <a id="entry-chen2025heurigym"></a>**HeuriGym**<br>HeuriGym: An Agentic Benchmark for LLM-Crafted Heuristics in Combinatorial Optimization | Uses code-execution feedback to iteratively generate combinatorial optimization heuristics, evaluating both quality and productive output. | Benchmark · Platform | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Publication][b006]][r514] · [![Paper 2][b002]][r515] · [![Code][b012]][r516] · [![Leaderboard (related)][b118]][r517] · [Details](#paper-chen2025heurigym) |
| 2026 · Computers & Operations Research 196 (December 2026 issue scheduled) | <a id="entry-behaviorrep2025"></a>**LLM Representations for Algorithm Selection**<br>Behavior and representation in open-weight Large Language Models for combinatorial optimization: From feature extraction to algorithm selection | Compares information available for explicit feature extraction, hidden-layer probing, and per-instance algorithm selection in frozen open-weight LLMs. | Evaluation analysis | [Auxiliary / NCO learning](#tech-auxiliary-learning) | [![Paper 1][b001]][r518] · [![Paper 2][b002]][r519] · [![Code & Analysis Data][b119]][r520] · [Details](#paper-behaviorrep2025) |
| 2026 · Findings of ACL 2026 | **OPT-BENCH / OPT-Agent**<br>OPT-BENCH: Evaluating the Iterative Self-Optimization of LLM Agents in Large-Scale Search Spaces | Evaluates iterative self-optimization on machine-learning tuning and NP problems, with OPT-Agent reusing historical feedback to revise solutions. | Method · Benchmark · Data | [Agent](#tech-agent) · [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r292] · [![Paper 2][b002]][r293] · [![Revised Preprint][b081]][r294] · [![Code][b012]][r295] · [![Dataset][b018]][r296] · [Details](#paper-li2026optbench) |
| 2025 · arXiv preprint | **ARS / RoutBench** (Core)<br>ARS: Automatic Routing Solver with Large Language Models | Generates constraint-aware routing heuristics from problem descriptions and introduces the multi-variant VRP benchmark RoutBench. | Method · Benchmark · Data | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r348] · [![Code][b012]][r349] · [Details](#paper-li2025ars) |
| 2025 · EvoApplications 2025 · LNCS | <a id="entry-sim2025beyondhype"></a>**Beyond the Hype: Bin Packing**<br>Beyond the Hype: Benchmarking LLM-Evolved Heuristics for Bin Packing | Re-evaluates LLM-evolved heuristics across diverse bin-packing instances and metrics, identifying instance regions favoring different algorithms. | Evaluation analysis · Data |  | [![Paper 1][b001]][r521] · [![Paper 2][b002]][r522] · [![Evaluation Data][b103]][r523] · [Details](#paper-sim2025beyondhype) |
| 2025 · GECCO 2025 Workshop / Companion | <a id="entry-vanstein2025blade"></a>**BLADE**<br>BLADE: Benchmark suite for LLM-driven Automated Design and Evolution of iterative optimisation heuristics | Provides continuous black-box optimization problems, instance generation, standard logging, and behavior-analysis tools for LLM algorithm discovery. | Benchmark · Platform |  | [![Paper 1][b001]][r524] · [![Paper 2][b002]][r525] · [![Code][b012]][r526] · [Details](#paper-vanstein2025blade) |
| 2025 · AAAI 2025 | **HSEvo**<br>HSEvo: Elevating Automatic Heuristic Design with Diversity-Driven Harmony Search and Genetic Algorithm Using LLMs | Analyzes heuristic evolution with diversity metrics and combines harmony search with genetic search to improve exploration. | Method · Evaluation analysis | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r360] · [![Paper 2][b002]][r361] · [![Code][b012]][r362] · [Details](#paper-dat2024hsevo) |
| 2025 · arXiv preprint | <a id="entry-liu2025fitness"></a>**LLM Algorithm-search Fitness Landscapes**<br>Fitness Landscape of Large Language Model-Assisted Automated Algorithm Search | Builds landscapes with algorithms as nodes and LLM transformations as edges, studying search ruggedness and similarity across tasks and models. | Evaluation analysis |  | [![Paper][b009]][r527] · [Details](#paper-liu2025fitness) |
| 2025 · arXiv preprint | <a id="entry-vanstein2025behaviour"></a>**LLM Heuristic Behaviour-space Analysis**<br>Behaviour Space Analysis of LLM-driven Meta-heuristic Discovery | Compares LLaMEA prompt variants on BBOB using exploration, exploitation, convergence, and stagnation behavior metrics. | Evaluation analysis |  | [![Paper][b009]][r528] · [![Behaviour Metrics Code][b120]][r529] · [Details](#paper-vanstein2025behaviour) |
| 2025 · arXiv preprint | <a id="entry-quan2025reeval3d"></a>**Re-evaluating Heuristic Search: 3D Packing**<br>Re-evaluating LLM-based Heuristic Search: A Case Study on the 3D Packing Problem | Uses constraint scaffolding and self-repair for 3D bin-packing programs, analyzing score-function search biases and limitations under tight constraints. | Evaluation analysis |  | [![Paper][b009]][r530] · [![Study Code][b121]][r531] · [Details](#paper-quan2025reeval3d) |

### Interaction and workflow evaluation

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | **Interactive Optimization Conversations**<br>Let's Have a Conversation: Designing and Evaluating LLM Agents for Interactive Optimization | Uses decision agents with internal utility functions as stakeholders to evaluate multi-turn interactive optimization beyond single-answer quality. | Method · Data · Application | [Agent](#tech-agent) | [![Paper][b009]][r187] · [![Code][b012]][r188] · [Details](#paper-conversation2026) |
| 2026 · arXiv preprint | <a id="entry-optiagentbench2026"></a>**Opti-Agent-Bench**<br>Opti-Agent-Bench: Benchmarking End-to-End Optimization R&D Agents on Real-World Business Problems | Evaluates business understanding, formalization, implementation, and reporting, including cross-module consistency and scoring validity. | Benchmark · Data |  | [![Paper][b009]][r532] · [Details](#paper-optiagentbench2026) |
| 2026 · arXiv preprint | <a id="entry-zhou2026orspace"></a>**OR-Space**<br>OR-Space: A Full-Lifecycle Workspace Benchmark for Industrial Optimization Agents | Uses persistent multi-file workspaces to evaluate model construction, requirement changes, and evidence-based explanations across the modeling lifecycle. | Benchmark · Data |  | [![Paper][b009]][r533] · [![Code][b012]][r534] · [![Dataset][b018]][r535] · [Details](#paper-zhou2026orspace) |
| 2026 · arXiv preprint | <a id="entry-oragentbench2026"></a>**ORAgentBench**<br>ORAgentBench: Can LLM Agents Solve Challenging Operations Research Tasks End to End? | Evaluates complete OR tasks from business briefs and multi-file materials to verifiable decisions in isolated workspaces. | Benchmark · Data |  | [![Paper][b009]][r536] · [![Code][b012]][r537] · [Details](#paper-oragentbench2026) |
| 2025 · NeurIPS 2025 | <a id="entry-liu2025mmagent"></a>**MM-Agent / MM-Bench (mathematical modeling)** (Exploratory)<br>MM-Agent: LLM as Agents for Real-world Mathematical Modeling Problem | Decomposes mathematical modeling into analysis, formulation, computation, and report generation, introducing MM-Bench from MCM/ICM problems. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r538] · [![Paper 2][b002]][r539] · [![Paper 3][b122]][r540] · [![Code & MM-Bench][b123]][r541] · [![Expert Skills (2026 add-on)][b124]][r542] · [![HF Demo (related)][b028]][r543] · [Details](#paper-liu2025mmagent) |
| 2025 · Findings of EMNLP 2025 | <a id="entry-qian2025modelingagent"></a>**ModelingAgent / ModelingBench** (Exploratory)<br>ModelingAgent: Bridging LLMs and Mathematical Modeling for Real-World Challenges | Coordinates tools and iterative revisions through multiple agents for open-ended modeling, evaluating reports with ModelingBench and ModelingJudge. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r544] · [![Paper 2][b002]][r545] · [![Code & ModelingBench][b125]][r546] · [Details](#paper-qian2025modelingagent) |

### Data quality and evaluation protocols

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | **Agora-Opt**<br>From Soliloquy to Agora: Memory-Enhanced LLM Agents with Decentralized Debate for Optimization Modeling | Uses independent modeling teams and outcome-driven debate, with read/write memory to reuse solving experience and revisions arising from disagreements. | Method · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r113] · [![Code & Cleaned Data][b037]][r114] · [Details](#paper-soliloquy2026) |
| 2026 · LLM4Code 2026 Workshop @ ICSE | **CP-Agent**<br>CP-Agent: Agentic Constraint Programming | Executes and iteratively repairs constraint models with a persistent IPython kernel and concise domain prompts. | Method · Data | [Agent](#tech-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r209] · [![Paper 2][b002]][r210] · [![Author Coding Agent (related)][b059]][r211] · [![Evaluation Archive v2][b060]][r212] · [Details](#paper-cpagent2025) |
| 2026 · ICLR 2026 | **OR-PRM**<br>OR-PRM: A Process Reward Model for Algorithmic Problem in Operations Research | Cleans existing synthetic data, builds OR-ProcessQA with MCTS and stepwise checks, and trains a process reward model for modeling reasoning. | Method · Data · Model | [Data synthesis](#tech-data-synthesis) · [MCTS](#tech-mcts) · [SFT / distillation](#tech-sft) · [Preference optimization](#tech-preference) · [Process rewards](#tech-prm) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b013]][r039] · [Details](#paper-wang2026orprm) |
| 2025 · arXiv preprint | <a id="entry-peering2025"></a>**Component-Level Evaluation**<br>Peering Inside the Black Box: Uncovering LLM Errors in Optimization Modelling through Component-Level Evaluation | Evaluates coverage and numerical errors in variables, constraints, and objectives, complementing optimal-value and runtime metrics. | Method |  | [![Paper][b009]][r547] · [Details](#paper-peering2025) |
| 2025 · IEEE PESGM 2025 | <a id="entry-zhou2024elecbench"></a>**ElecBench** (Exploratory)<br>ElecBench: a Power Grid Dispatch Evaluation Benchmark for Large Language Models | Evaluates factuality, logic, and stability on text tasks covering power-system knowledge, monitoring, dispatch, and black start. | Benchmark · Data |  | [![Paper 1][b001]][r548] · [![Paper 2][b002]][r549] · [![Public Test Subset][b126]][r550] · [Details](#paper-zhou2024elecbench) |
| 2025 · IJCAI 2025 Survey Track | **LLM4OR Survey** (Core)<br>A Survey of Optimization Modeling Meets LLMs: Progress and Future Directions | Surveys the optimization modeling pipeline, analyzes and annotates benchmark errors, and provides cleaned data and an evaluation portal. | Survey · Data |  | [![Paper][b009]][r015] · [![Official resource repository (related)][b005]][r016] · [![Cleaned Benchmarks][b011]][r017] · [Details](#paper-xiao2025survey) |
| 2025 · arXiv preprint | **OptiTrust**<br>Toward a Trustworthy Optimization Modeling Agent via Verifiable Synthetic Data Generation | Synthesizes demonstrations from symbolic problems with known optima and trains modeling agents with cross-language voting and stepwise reasoning. | Method · Data · Model | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r069] · [Details](#paper-lima2025optitrust) |
| 2025 · NeurIPS 2025 | **SIRL** (Core)<br>Solver-Informed RL: Grounding Large Language Models for Authentic Optimization Modeling | Checks code and LP instances with a solver to construct verifiable RL rewards, releasing models and revised evaluation data. | Method · Data · Model | [Data synthesis](#tech-data-synthesis) · [LLM RL](#tech-llm-rl) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r168] · [![arXiv][b020]][r169] · [![Code][b012]][r170] · [![Model Gurobi-7B][b051]][r171] · [![Model COPT-7B][b052]][r172] · [![Model Gurobi-32B][b053]][r173] · [![Model COPT-32B][b054]][r174] · [![Revised evaluation set][b055]][r175] · [Details](#paper-chen2025sirl) |
| 2025 · Findings of EMNLP 2025 | **Step-Opt**<br>Training LLMs for Optimization Modeling via Iterative Data Synthesis and Structured Validation | Progressively increases synthetic problem complexity, validates training data structurally, and fine-tunes optimization modeling models. | Method · Data · Model | [Data synthesis](#tech-data-synthesis) · [SFT / distillation](#tech-sft) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r084] · [![Paper 2][b002]][r085] · [![Code][b012]][r086] · [Details](#paper-wu2025stepopt) |
| 2024 · LREC-COLING 2024 | <a id="entry-xing2024lpwp"></a>**Human-aligned LPWP Evaluation**<br>Towards Human-aligned Evaluation for Linear Programming Word Problems | Compares LP models using graph edit distance and human ratings to study alignment between evaluation metrics and human judgments. | Method · Evaluation analysis |  | [![Paper][b013]][r551] · [Details](#paper-xing2024lpwp) |


[Back to contents](#contents)

<a id="foundational-resources"></a>

<a id="resources"></a>

## Models, data, and tools

Resources are grouped by artifact type; a paper can contribute both a method and resources.

### Resource and platform papers

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | **Text2Model**<br>Text2Model: Modeling Copilots for Text-to-Model Translation | Provides multiple MiniZinc modeling copilots, an interactive editor, and an online leaderboard. | Method · Platform | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) | [![Paper][b009]][r216] · [![Code][b012]][r217] · [![Text2Zinc (reused)][b062]][r218] · [![Editor (related)][b063]][r219] · [![Leaderboard (related)][b064]][r220] · [![Python Package (related)][b065]][r221] · [Details](#paper-text2model2026) |
| 2025 · arXiv preprint | **EASE**<br>Solve it with EASE | Supports algorithm evolution through modular generation, testing, analysis, and evaluation, with complementary roles for multiple LLMs. | Method · Platform | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r352] · [![Framework][b087]][r353] · [![Frontend][b088]][r354] · [Details](#paper-viktorin2025ease) |
| 2025 · ICLR 2025 | <a id="entry-li2025milpevolve"></a>**MILP-Evolve** (Core)<br>Towards Foundation Models for Mixed Integer Linear Programming | Evolves diverse MILP classes and instances with LLMs for gap prediction, learned branching, and language alignment. | Method · Data | [Data synthesis](#tech-data-synthesis) · [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r552] · [![arXiv][b020]][r553] · [![Code][b012]][r554] · [![Dataset][b018]][r555] · [![GitHub Data][b127]][r556] · [Details](#paper-li2025milpevolve) |
| 2024 · arXiv preprint | <a id="entry-liu2024llm4ad"></a>**LLM4AD** (Core)<br>LLM4AD: A Platform for Algorithm Design with Large Language Model | Provides a modular algorithm-design platform with unified search methods, tasks, LLM interfaces, and evaluation sandboxes. | Platform |  | [![Paper][b009]][r557] · [![Code][b012]][r376] · [Details](#paper-liu2024llm4ad) |

[Models and weights](#model-weights) · [Evaluation benchmarks](#evaluation-benchmarks) · [Training data](#training-data) · [Revised evaluation data](#evaluation-data) · [Skill libraries](#skills)

<a id="model-weights"></a>

### Models and weights

| Resource | Paper | Access |
|---|---|---|
| LLaMoCo-S (CodeGen 350M) | [LLaMoCo](#entry-ma2024llamoco) | [![HF Weights][b128]][r332] |
| LLMOPT-Qwen2.5-14B | [LLMOPT](#entry-jiang2025llmopt) | [![HF Model][b129]][r159] |
| ner4opt-roberta-v1 | [Ner4Opt](#entry-dakle2023ner4opt) | [![HF Model][b129]][r093] |
| ner4opt-roberta-v2 | [Ner4Opt](#entry-dakle2023ner4opt) | [![HF Model][b129]][r094] |
| OptiMind-SFT | [OptiMind](#entry-zhang2025optimind) | [![HF Model][b129]][r065] |
| OptMATH Qwen2.5 7B / 32B | [OptMATH](#entry-lu2025optmath) | [![Model 7B][b022]][r072] · [![Model 32B][b023]][r073] |
| ORLM-LLaMA-3-8B | [ORLM](#entry-huang2025orlm) | [![HF Model][b129]][r078] |
| PEARL-Qwen3-4B-Instruct-2507 | [PEARL](#entry-lu2026pearl) | [![HF Model][b129]][r138] |
| SDRL-Qwen3-4B | [SDRL](#entry-sdrl2026) | [![HF Weights][b128]][r143] |
| SIRL Gurobi / COPT 7B / 32B | [SIRL](#entry-chen2025sirl) | [![Model Gurobi-7B][b051]][r171] · [![Model COPT-7B][b052]][r172] · [![Model Gurobi-32B][b053]][r173] · [![Model COPT-32B][b054]][r174] |
| SOLID-Qwen3 | [SOLID](#entry-solid2026) | [![HF Model][b129]][r146] |
| SOLID-StepORLM | [SOLID](#entry-solid2026) | [![HF Model][b129]][r147] |
| StepORLM policy / GenPRM 8B | [StepORLM](#entry-zhou2026steporlm) | [![Policy 8B][b048]][r151] · [![GenPRM 8B][b049]][r152] |

<a id="evaluation-benchmarks"></a>

### Evaluation benchmarks

| Resource | Paper | Access |
|---|---|---|
| RoutBench | [ARS / RoutBench](#entry-li2025ars) | [![GitHub][b130]][r349] |
| LPWP / early NL4Opt data (1,101 examples) | [Auto-formulation (2022)](#entry-ramamonjison2022augmenting) | [![GitHub Data][b127]][r112] |
| BLADE | [BLADE](#entry-vanstein2025blade) | [![GitHub Suite][b131]][r526] |
| StructuredOR | [BPP-Search / StructuredOR](#entry-wang2025bppsearch) | [![HF Data][b132]][r061] |
| ComplexOR (original repository release) | [Chain-of-Experts](#entry-xiao2024coe) | [![GitHub][b130]][r088] |
| CO-Bench | [CO-Bench](#entry-sun2026cobench) | [![HF Data][b132]][r509] |
| VRPBench | [Constraint Injection / VRPCoder](#entry-constraintinjection2026) | [![GitHub Data][b127]][r261] |
| CP-Bench (archived original) | [CP-Bench / DCP-Bench-Open](#entry-michailidis2025cpbench) | [![HF Dataset][b133]][r476] |
| DCP-Bench-Open (extension) | [CP-Bench / DCP-Bench-Open](#entry-michailidis2025cpbench) | [![GitHub][b130]][r475] |
| CP-SynC Benchmark | [CP-SynC](#entry-cpsync2026) | [![GitHub Data & Evaluation][b134]][r214] |
| DynaSchedBench | [DynaSchedBench](#entry-dynaschedbench2026) | [![GitHub Benchmark][b135]][r493] |
| ElecBench (public test subset) | [ElecBench](#entry-zhou2024elecbench) | [![GitHub Subset][b136]][r550] |
| EOR industrial explanation evaluation set | [EOR / Decision Information](#entry-zhang2025decisioninfo) | [![GitHub][b130]][r233] |
| EquivaFormulation | [EquivaMap](#entry-zhai2025equivamap) | [![HF Data][b132]][r249] |
| FrontierOR-v1 (released 2026-09-27) | [FrontierOR](#entry-kong2026frontieror) | [![HF Dataset][b133]][r513] · [![Evaluation code][b137]][r512] |
| HeuriGym | [HeuriGym](#entry-chen2025heurigym) | [![GitHub Benchmark][b135]][r516] |
| InventoryBench | [InventoryBench](#entry-invbench2026) | [![GitHub][b130]][r496] |
| JOR-Bench (five Japanese translations with English counterparts) | [JOR-Bench](#entry-jorbench2026) | [![HF Dataset][b133]][r457] |
| Large-Scale-OR | [LEAN-LLM-OPT](#entry-liang2026leanllmopt) | [![GitHub: Test_Dataset][b138]][r121] |
| Air-NRM | [LEAN-LLM-OPT](#entry-liang2026leanllmopt) | [![GitHub: Test_Dataset][b138]][r121] |
| G-REAL | [MA-GTS / G-REAL](#entry-yuan2025magts) | [![GitHub][b130]][r441] |
| Mamo | [Mamo](#entry-huang2024mamo) | [![GitHub][b130]][r480] · [![HF mirror (third-party field adaptation)][b139]][r481] |
| MIPLIB-NL | [MIPLIB-NL](#entry-li2026miplibnl) | [![GitHub][b130]][r460] |
| MM-Bench (mathematical modeling competitions) | [MM-Agent / MM-Bench (mathematical modeling)](#entry-liu2025mmagent) | [![GitHub Data][b127]][r541] |
| ModelingBench | [ModelingAgent / ModelingBench](#entry-qian2025modelingagent) | [![GitHub Data][b127]][r546] |
| NL4Opt | [NL4Opt](#entry-ramamonjison2023nl4opt) | [![GitHub][b130]][r112] |
| NLCO | [NLCO](#entry-jiang2026nlco) | [![HF Dataset][b133]][r501] · [![Code][b012]][r500] |
| OPT-BENCH | [OPT-BENCH / OPT-Agent](#entry-li2026optbench) | [![HF Dataset][b133]][r296] · [![Code][b012]][r295] |
| OPT-Engine / C³-Bench | [OPT-Engine](#entry-chen2026optengine) | [![HF Dataset][b133]][r467] · [![Evaluation code][b137]][r466] |
| NLP4LP | [OptiMUS](#entry-teshnizi2024optimus) | [![HF Data][b132]][r185] |
| OptiVerse | [OptiVerse / DVA-Agent](#entry-optiverse2026) | [![HF Dataset][b133]][r242] · [![Evaluation Code][b140]][r241] |
| OptMATH-Bench | [OptMATH](#entry-lu2025optmath) | [![GitHub][b130]][r071] |
| BWOR | [OR-LLM-Agent / BWOR](#entry-zhang2025bwor) | [![HF Dataset][b133]][r164] |
| OR-Space | [OR-Space](#entry-zhou2026orspace) | [![HF Dataset][b133]][r535] · [![Evaluation Code][b140]][r534] |
| ORAgentBench | [ORAgentBench](#entry-oragentbench2026) | [![GitHub Benchmark][b135]][r537] |
| IndustryOR | [ORLM](#entry-huang2025orlm) | [![IndustryOR][b024]][r079] |
| ORDebug / OR-Debug-Bench | [ORLoopBench](#entry-ao2026orloopbench) | [![GitHub][b130]][r230] |
| ORBias / OR-Bias-Bench | [ORLoopBench](#entry-ao2026orloopbench) | [![GitHub][b130]][r230] |
| ORQA | [ORQA](#entry-mostajabdaveh2025orqa) | [![GitHub][b130]][r484] |
| LogiOR | [ORThought / LogiOR](#entry-yang2025orthought) | [![HF Data][b132]][r046] |
| ECBench (generator and public samples) | [PowerAtlas / ECBench](#entry-jiang2026poweratlas) | [![GitHub][b130]][r271] |
| ProOPF-B | [ProOPF](#entry-shen2026proopf) | [![GitHub: ProOPF_B][b141]][r471] |
| RetailOpt-190 | [ReLoop / RetailOpt-190](#entry-lian2026reloop) | [![HF Dataset][b133]][r267] |
| OptiBench | [ReSocratic / OptiBench](#entry-yang2025resocratic) | [![GitHub][b130]][r083] |
| RetailBench | [RetailBench](#entry-zhang2026retailbench) | [![GitHub Environment][b142]][r504] |
| NLEquiv-150 | [SOVER / NLEquiv-150](#entry-bhattacharyya2026sover) | [![GitHub Benchmark][b135]][r248] |
| Text2Zinc (reused existing benchmark) | [Text2Model](#entry-text2model2026) | [![HF Dataset][b133]][r218] |
| Text2Zinc | [Text2Zinc](#entry-singirikonda2025text2zinc) | [![HF Dataset][b133]][r218] |

<a id="training-data"></a>

### Training data

| Resource | Paper | Access |
|---|---|---|
| AI-Copilot scheduling training samples | [AI-Copilot for Business Optimisation](#entry-alahakoon2023copilot) | [![GitHub Data][b127]][r099] |
| AI-Copilot industrial-case training samples | [AI-Copilot for Business Optimisation](#entry-alahakoon2023copilot) | [![GitHub Case Data][b143]][r101] |
| DeepOR seeds and SFT/RL samples | [DeepOR](#entry-xiao2026deepor) | [![Official seeds and sample data][b014]][r027] |
| Infeasibility-aware graph-optimization training data | [Infeasibility-Aware CO Models](#entry-infeasibilityaware2026) | [![Author Archive (related)][b144]][r269] |
| LLMCoSolver SFT Data | [LLMCoSolver / E2E CO Solver](#entry-jiang2025e2eco) | [![SFT Data][b079]][r275] |
| LLMCoSolver RL Data | [LLMCoSolver / E2E CO Solver](#entry-jiang2025e2eco) | [![RL Data][b080]][r276] |
| MILP-Evolve | [MILP-Evolve](#entry-li2025milpevolve) | [![HF Data][b132]][r555] |
| MILP training/test materials extending NL4Opt | [Multi-stage MILP Synthesis](#entry-li2023synthesizing) | [![GitHub Data][b127]][r106] |
| OptMATH-Train | [OptMATH](#entry-lu2025optmath) | [![HF Data][b132]][r074] |
| OR-Instruct-Data-3K (public subset) | [ORLM](#entry-huang2025orlm) | [![OR-Instruct-3K][b025]][r080] |
| ProOPF-D (public few-shot examples) | [ProOPF](#entry-shen2026proopf) | [![GitHub (ProOPF_D subset)][b145]][r471] |
| ReSocratic-29k | [ReSocratic / OptiBench](#entry-yang2025resocratic) | [![GitHub][b130]][r083] |
| SAGE multi-strategy SFT data | [SAGE (Strategy-Aware Modeling)](#entry-strategyaware2026) | [![HF Dataset][b133]][r050] |
| Starjob training set | [Starjob](#entry-abgaryan2025starjob) | [![HF Dataset][b133]][r281] |
| Step-Opt-Instruct training data | [Step-Opt](#entry-wu2025stepopt) | [![GitHub: Step/Dataset][b146]][r086] |

<a id="evaluation-data"></a>

### Revised evaluation data

| Resource | Paper | Access |
|---|---|---|
| Agora-Opt revised and standardized existing OR evaluation data | [Agora-Opt](#entry-soliloquy2026) | [![GitHub Data][b127]][r114] |
| AutoModSAT evaluation data (generated and industrial EDA instances) | [AutoModSAT](#entry-sun2025satheur) | [![Zenodo Data][b147]][r449] |
| Bin-packing evaluation data and evolved instances | [Beyond the Hype: Bin Packing](#entry-sim2025beyondhype) | [![Zenodo Data][b147]][r523] |
| City-LEO shared e-bike data and code | [City-LEO](#entry-jiao2024cityleo) | [![HF: Data & Code][b148]][r196] |
| Revised CP-Bench evaluation materials (CP-Agent, Zenodo v2) | [CP-Agent](#entry-cpagent2025) | [![Zenodo v2][b149]][r212] |
| DRoC VRP evaluation instances | [DRoC](#entry-jiang2025droc) | [![GitHub: problems][b150]][r155] |
| CO instance collection used by HeurAgenix | [HeurAgenix](#entry-yang2025heuragenix) | [![HF Instances][b151]][r359] |
| Interactive school-timetabling evaluation and dialogue materials | [Interactive Optimization Conversations](#entry-conversation2026) | [![GitHub][b130]][r188] |
| Representation / probing experimental materials | [LLM Representations for Algorithm Selection](#entry-behaviorrep2025) | [![Zenodo Archive][b152]][r520] |
| LLM4OR cleaned/error-annotated existing modeling benchmarks | [LLM4OR Survey](#entry-xiao2025survey) | [![GitHub Data][b127]][r017] |
| Stochastic optimization evaluation cases (including literature adaptations) | [LLMs for Stochastic Modeling](#entry-talebi2025stochastic) | [![GitHub: dataset.zip][b153]][r208] |
| CO task data archive used by MoH | [MoH](#entry-moh2025) | [![Google Drive Data][b154]][r418] |
| MOID routing-infeasibility diagnostic cases and solutions | [MOID](#entry-moid2025) | [![GitHub Data][b127]][r235] |
| NEMO per-problem outputs and traces (existing benchmarks) | [NEMO](#entry-nemo2026) | [![HF Artifacts][b155]][r126] |
| Opt-Miner third-party base-model reproduction outputs | [Opt-Miner](#entry-optminer2026) | [![HF (third-party results)][b156]][r036] |
| OptiChat model-explanation QA evaluation | [OptiChat](#entry-chen2025optichat) | [![GitHub][b130]][r191] |
| ORLMBenchmark (revised existing benchmarks) | [SIRL](#entry-chen2025sirl) | [![Revised evaluation set][b055]][r175] |
| Revised NL4Opt / MAMO / IndustryOR evaluation data | [Step-Opt](#entry-wu2025stepopt) | [![GitHub: Step/test][b157]][r086] |

<a id="skills"></a>

### Skill libraries

| Resource | Paper | Access |
|---|---|---|
| AutoOPT domain research skills | [AutoOPT](#entry-autoopt2026) | [![GitHub Skills][b158]][r413] |
| MM-Agent Expert Skills | [MM-Agent / MM-Bench (mathematical modeling)](#entry-liu2025mmagent) | [![GitHub Skills][b158]][r542] |
| OptSkills workflow skill library | [OptSkills](#entry-yang2026optskills) | [![Official skill library (related)][b041]][r134] |

[Back to contents](#contents)

<a id="agents"></a>

<a id="training"></a>

<a id="techniques"></a>

## Techniques and topic index

Find papers by explicit mechanisms. Technique tags are independent of research tasks and contribution types.

<a id="tech-agent"></a>

<details>
<summary>Agent (62 papers)</summary>

[AFL](#entry-zhang2026afl) · [Agentic MIP Research](#entry-xu2026agenticmip) · [Agora-Opt](#entry-soliloquy2026) · [AutoOPT](#entry-autoopt2026) · [CIR / R2C](#entry-canonicalir2026) · [COOPA](#entry-coopa2026) · [CP-Agent](#entry-cpagent2025) · [CP-SynC](#entry-cpsync2026) · [EvoOR-Agent](#entry-coevolve2026) · [GenAI Beer Game Reliability](#entry-beergame2026) · [HeuriGym](#entry-chen2025heurigym) · [Interactive Optimization Conversations](#entry-conversation2026) · [LEAN-LLM-OPT](#entry-liang2026leanllmopt) · [LLM Agents for Efficient Frontiers](#entry-efficientfrontier2026) · [LLM-MAS for Service Operations](#entry-wang2026llmmas) · [MIRROR](#entry-mirror2026) · [NEMO](#entry-nemo2026) · [OPT-BENCH / OPT-Agent](#entry-li2026optbench) · [Opt-Miner](#entry-optminer2026) · [OptArgus](#entry-optarcus2026) · [OptGraph](#entry-xiu2026optgraph) · [OptiAgent](#entry-optiagent2026) · [OptiChat](#entry-chen2025optichat) · [OptiLoop](#entry-optiloop2026) · [OptiRepair](#entry-optirepair2026) · [OptiVerse / DVA-Agent](#entry-optiverse2026) · [OptSkills](#entry-yang2026optskills) · [ORThought / LogiOR](#entry-yang2025orthought) · [PathWise](#entry-pathwise2026) · [PEARL](#entry-lu2026pearl) · [RLEA](#entry-rlvrpagents2026) · [Text2Model](#entry-text2model2026) · [ALAS](#entry-alas2025) · [ARS / RoutBench](#entry-li2025ars) · [Ask, Clarify, Optimize](#entry-askclarify2026) · [C-DSS](#entry-kaleta2025cdss) · [DAOpt / OptU](#entry-daopt2025) · [EASE](#entry-viktorin2025ease) · [EOR / Decision Information](#entry-zhang2025decisioninfo) · [Gala](#entry-globalconstraint2025) · [LLM-LNS](#entry-ye2025llmlns) · [LLM-SUC](#entry-llmsuc2025) · [LLMs for Stochastic Modeling](#entry-talebi2025stochastic) · [MA-GTS / G-REAL](#entry-yuan2025magts) · [MM-Agent / MM-Bench (mathematical modeling)](#entry-liu2025mmagent) · [ModelingAgent / ModelingBench](#entry-qian2025modelingagent) · [MURKA](#entry-xie2025murka) · [OptimAI](#entry-thind2025optimai) · [OptiTrust](#entry-lima2025optitrust) · [OR-LLM-Agent / BWOR](#entry-zhang2025bwor) · [ORMind](#entry-ormind2025) · [RoCo](#entry-xu2025roco) · [Chain-of-Experts](#entry-xiao2024coe) · [City-LEO](#entry-jiao2024cityleo) · [InvAgent](#entry-quan2024invagent) · [ITINERA](#entry-tang2024itinerary) · [Multi-Stage Modeling & Verification](#entry-mostajabdaveh2024multiagent) · [OptiChat / Infeasibility Diagnosis](#entry-chen2023diagnosing) · [OptiMUS](#entry-teshnizi2024optimus) · [OptLLM](#entry-zhang2024optllm) · [LLMs for Power Engineering](#entry-li2023power) · [OptiGuide](#entry-li2023optiguide)

</details>

<a id="tech-multi-agent"></a>

<details>
<summary>Multi-agent (35 papers)</summary>

[AFL](#entry-zhang2026afl) · [Agora-Opt](#entry-soliloquy2026) · [CIR / R2C](#entry-canonicalir2026) · [COOPA](#entry-coopa2026) · [CP-SynC](#entry-cpsync2026) · [EvoOR-Agent](#entry-coevolve2026) · [GenAI Beer Game Reliability](#entry-beergame2026) · [LEAN-LLM-OPT](#entry-liang2026leanllmopt) · [OptArgus](#entry-optarcus2026) · [OptiAgent](#entry-optiagent2026) · [OptiChat](#entry-chen2025optichat) · [OptiVerse / DVA-Agent](#entry-optiverse2026) · [ORThought / LogiOR](#entry-yang2025orthought) · [PathWise](#entry-pathwise2026) · [RLEA](#entry-rlvrpagents2026) · [Text2Model](#entry-text2model2026) · [ALAS](#entry-alas2025) · [C-DSS](#entry-kaleta2025cdss) · [DAOpt / OptU](#entry-daopt2025) · [EASE](#entry-viktorin2025ease) · [Gala](#entry-globalconstraint2025) · [LLMs for Stochastic Modeling](#entry-talebi2025stochastic) · [MA-GTS / G-REAL](#entry-yuan2025magts) · [MM-Agent / MM-Bench (mathematical modeling)](#entry-liu2025mmagent) · [ModelingAgent / ModelingBench](#entry-qian2025modelingagent) · [MURKA](#entry-xie2025murka) · [OptimAI](#entry-thind2025optimai) · [OptiTrust](#entry-lima2025optitrust) · [OR-LLM-Agent / BWOR](#entry-zhang2025bwor) · [ORMind](#entry-ormind2025) · [RoCo](#entry-xu2025roco) · [Chain-of-Experts](#entry-xiao2024coe) · [InvAgent](#entry-quan2024invagent) · [Multi-Stage Modeling & Verification](#entry-mostajabdaveh2024multiagent) · [OptiMUS](#entry-teshnizi2024optimus)

</details>

<a id="tech-cot"></a>

<details>
<summary>CoT / structured reasoning (9 papers)</summary>

[DeepOR](#entry-xiao2026deepor) · [DScheLLM](#entry-zhang2026dschellm) · [MiniOpt](#entry-zhao2026miniopt) · [ORThought / LogiOR](#entry-yang2025orthought) · [StepORLM](#entry-zhou2026steporlm) · [BPP-Search / StructuredOR](#entry-wang2025bppsearch) · [DPLM / DP-Bench](#entry-dpdlm2025) · [Chain-of-Experts](#entry-xiao2024coe) · [Rare MIP Challenges](#entry-wang2024raremip)

</details>

<a id="tech-rag"></a>

<details>
<summary>RAG (12 papers)</summary>

[CHORUS](#entry-lporch2025) · [CIR / R2C](#entry-canonicalir2026) · [MIRROR](#entry-mirror2026) · [Opt-Miner](#entry-optminer2026) · [OptGraph](#entry-xiu2026optgraph) · [OptSkills](#entry-yang2026optskills) · [RAG for Optimization & CP Modeling](#entry-roy2026rag) · [RLEA](#entry-rlvrpagents2026) · [C-DSS](#entry-kaleta2025cdss) · [Cold-Start Separator Configuration](#entry-lawless2024cuts) · [DRoC](#entry-jiang2025droc) · [RAGDyS](#entry-tang2024ragdys)

</details>

<a id="tech-memory"></a>

<details>
<summary>Memory (16 papers)</summary>

[Agora-Opt](#entry-soliloquy2026) · [AutoREM / AutoRO-Bench](#entry-robustreform2026) · [FormuEvo](#entry-yuan2026formuevo) · [HiFo-Prompt](#entry-chen2025hifoprompt) · [NEMO](#entry-nemo2026) · [OPT-BENCH / OPT-Agent](#entry-li2026optbench) · [OptGraph](#entry-xiu2026optgraph) · [OptSkills](#entry-yang2026optskills) · [PathWise](#entry-pathwise2026) · [RLEA](#entry-rlvrpagents2026) · [SAC-Opt](#entry-ma2025sacopt) · [ShinkaEvolve](#entry-lange2026shinka) · [ALAS](#entry-alas2025) · [AlphaOPT](#entry-kong2025alphaopt) · [OptiTree](#entry-liu2025optitree) · [ReflecSched](#entry-cao2025reflecsched)

</details>

<a id="tech-reflection"></a>

<details>
<summary>Reflection (14 papers)</summary>

[EPOCH](#entry-epoch2026) · [HiFo-Prompt](#entry-chen2025hifoprompt) · [LaGO](#entry-hsplo2026) · [MeEvo](#entry-meevo2026) · [MeLA](#entry-chen2025mela) · [MILP-Evo](#entry-milpevo2026) · [PyVRP+ / MEP](#entry-pyvrpplus2026) · [CALM / STORM](#entry-calm2025storm) · [DPLM / DP-Bench](#entry-dpdlm2025) · [OptimAI](#entry-thind2025optimai) · [ReflecSched](#entry-cao2025reflecsched) · [RoCo](#entry-xu2025roco) · [Chain-of-Experts](#entry-xiao2024coe) · [ReEvo](#entry-ye2024reevo)

</details>

<a id="tech-mcts"></a>

<details>
<summary>MCTS (4 papers)</summary>

[OR-PRM](#entry-wang2026orprm) · [Autoformulation](#entry-astorga2025autoformulation) · [MCTS-AHD](#entry-zheng2025mctsahd) · [SolverLLM](#entry-solverllm2025)

</details>

<a id="tech-tree-search"></a>

<details>
<summary>Tree / beam search (2 papers)</summary>

[BPP-Search / StructuredOR](#entry-wang2025bppsearch) · [OptiTree](#entry-liu2025optitree)

</details>

<a id="tech-evolution"></a>

<details>
<summary>Program evolution (49 papers)</summary>

[A2DEPT](#entry-chen2026a2dept) · [AILS-AHD](#entry-xie2026ailsahd) · [AutoModSAT](#entry-sun2025satheur) · [AutoSAT](#entry-sun2024autosat) · [CALM (Algorithm–LM Co-evolution)](#entry-huang2025calm) · [DSevolve](#entry-dsevolve2026) · [EPOCH](#entry-epoch2026) · [ES-AHD](#entry-es2026ahd) · [Evo-B&B](#entry-chen2026evobb) · [EvoOR-Agent](#entry-coevolve2026) · [FormuEvo](#entry-yuan2026formuevo) · [Full-Component ALNS Evolution](#entry-yu2026alns) · [G-LNS](#entry-zhao2026glns) · [HiFo-Prompt](#entry-chen2025hifoprompt) · [InvEvolve](#entry-invevolve2026) · [MeEvo](#entry-meevo2026) · [MeLA](#entry-chen2025mela) · [MILP-Evo](#entry-milpevo2026) · [MoH](#entry-moh2025) · [MPaGE](#entry-ha2025paretogrid) · [PALL](#entry-yan2026pall) · [PyVRP+ / MEP](#entry-pyvrpplus2026) · [ShinkaEvolve](#entry-lange2026shinka) · [SpecAHD](#entry-lai2026specahd) · [SPO](#entry-spo2026) · [TIDE](#entry-chen2026tide) · [VRPAgent](#entry-vrpagent2025) · [AlphaEvolve](#entry-novikov2025alphaevolve) · [CEoH](#entry-bomer2025emerging) · [DHEvo](#entry-dheevo2025) · [EASE](#entry-viktorin2025ease) · [EFS](#entry-luo2025efs) · [FunSearch for Unit Commitment](#entry-ucfunsearch2025) · [HeurAgenix](#entry-yang2025heuragenix) · [HSEvo](#entry-dat2024hsevo) · [InstSpecHH](#entry-zhang2025instspechh) · [LLaMEA](#entry-vanstein2024llamea) · [LLM-discovered EDDC / MDDC](#entry-cetinkaya2025mipsmtt) · [LLM-LNS](#entry-ye2025llmlns) · [MEoH](#entry-yao2025meoh) · [MILP-Evolve](#entry-li2025milpevolve) · [NCO-LLM for VRP](#entry-tran2025llmneural) · [RedAHD](#entry-thach2025redahd) · [SAGE / formerly EvoCut](#entry-yazdani2025evocut) · [STRCMP](#entry-li2025strcmp) · [EoH](#entry-liu2024eoh) · [ReEvo](#entry-ye2024reevo) · [AEL](#entry-liu2023ael) · [FunSearch](#entry-romera2023funsearch)

</details>

<a id="tech-data-synthesis"></a>

<details>
<summary>Data synthesis (29 papers)</summary>

[AutoOR](#entry-autoor2026) · [Constraint Injection / VRPCoder](#entry-constraintinjection2026) · [DeepOR](#entry-xiao2026deepor) · [DScheLLM](#entry-zhang2026dschellm) · [EvoOptiGraph](#entry-evooptigraph2026) · [Infeasibility-Aware CO Models](#entry-infeasibilityaware2026) · [LLaMoCo](#entry-ma2024llamoco) · [MIND](#entry-mind2026) · [Opt-Miner](#entry-optminer2026) · [OR-PRM](#entry-wang2026orprm) · [PALL](#entry-yan2026pall) · [PowerAtlas / ECBench](#entry-jiang2026poweratlas) · [RAG for Optimization & CP Modeling](#entry-roy2026rag) · [SAGE (Strategy-Aware Modeling)](#entry-strategyaware2026) · [SDRL](#entry-sdrl2026) · [CALM / STORM](#entry-calm2025storm) · [DPLM / DP-Bench](#entry-dpdlm2025) · [LLMCoSolver / E2E CO Solver](#entry-jiang2025e2eco) · [MILP-Evolve](#entry-li2025milpevolve) · [OptiTrust](#entry-lima2025optitrust) · [OptMATH](#entry-lu2025optmath) · [ORLM](#entry-huang2025orlm) · [ReSocratic / OptiBench](#entry-yang2025resocratic) · [SIRL](#entry-chen2025sirl) · [Step-Opt](#entry-wu2025stepopt) · [OptLLM](#entry-zhang2024optllm) · [To the Globe / TTG](#entry-ju2024ttg) · [AI-Copilot for Business Optimisation](#entry-alahakoon2023copilot) · [CodeT5 Mathematical Program Synthesis](#entry-synth2023)

</details>

<a id="tech-sft"></a>

<details>
<summary>SFT / distillation (40 papers)</summary>

[AutoOR](#entry-autoor2026) · [Constraint Injection / VRPCoder](#entry-constraintinjection2026) · [DeepOR](#entry-xiao2026deepor) · [DScheLLM](#entry-zhang2026dschellm) · [EPOCH](#entry-epoch2026) · [EvoOpt-LLM](#entry-he2026evoopt) · [EvoOptiGraph](#entry-evooptigraph2026) · [Infeasibility-Aware CO Models](#entry-infeasibilityaware2026) · [LLaMoCo](#entry-ma2024llamoco) · [MIND](#entry-mind2026) · [Multi-Warehouse Formulation Selection](#entry-warehouseformsel2026) · [OR-PRM](#entry-wang2026orprm) · [OR-R1](#entry-ding2026orr1) · [PALL](#entry-yan2026pall) · [PowerAtlas / ECBench](#entry-jiang2026poweratlas) · [SAGE (Strategy-Aware Modeling)](#entry-strategyaware2026) · [Ask, Clarify, Optimize](#entry-askclarify2026) · [CALM / STORM](#entry-calm2025storm) · [DPLM / DP-Bench](#entry-dpdlm2025) · [LLMCoSolver / E2E CO Solver](#entry-jiang2025e2eco) · [LLMOPT](#entry-jiang2025llmopt) · [MURKA](#entry-xie2025murka) · [OptiMind](#entry-zhang2025optimind) · [OptiTrust](#entry-lima2025optitrust) · [OptMATH](#entry-lu2025optmath) · [ORLM](#entry-huang2025orlm) · [ReSocratic / OptiBench](#entry-yang2025resocratic) · [Starjob](#entry-abgaryan2025starjob) · [Step-Opt](#entry-wu2025stepopt) · [STRCMP](#entry-li2025strcmp) · [LM4OPT](#entry-ahmed2024lm4opt) · [Ner4Opt](#entry-dakle2023ner4opt) · [OptLLM](#entry-zhang2024optllm) · [Rare MIP Challenges](#entry-wang2024raremip) · [To the Globe / TTG](#entry-ju2024ttg) · [AI-Copilot for Business Optimisation](#entry-alahakoon2023copilot) · [CodeT5 Mathematical Program Synthesis](#entry-synth2023) · [Multi-stage MILP Synthesis](#entry-li2023synthesizing) · [NL4Opt: Auto-Formulation Approach](#entry-iflytek2023autoformulation) · [OPD@NL4Opt](#entry-wang2023opdnl4opt)

</details>

<a id="tech-llm-rl"></a>

<details>
<summary>LLM RL (26 papers)</summary>

[AutoOR](#entry-autoor2026) · [CALM (Algorithm–LM Co-evolution)](#entry-huang2025calm) · [Constraint Injection / VRPCoder](#entry-constraintinjection2026) · [DeepOR](#entry-xiao2026deepor) · [EVOM](#entry-guan2026evom) · [EvoOptiGraph](#entry-evooptigraph2026) · [GenAI Beer Game Reliability](#entry-beergame2026) · [MiniOpt](#entry-zhao2026miniopt) · [Multi-Warehouse Formulation Selection](#entry-warehouseformsel2026) · [Opt-Miner](#entry-optminer2026) · [OptiRepair](#entry-optirepair2026) · [OR-R1](#entry-ding2026orr1) · [ORLoopBench](#entry-ao2026orloopbench) · [PEARL](#entry-lu2026pearl) · [PowerAtlas / ECBench](#entry-jiang2026poweratlas) · [SAGE (Strategy-Aware Modeling)](#entry-strategyaware2026) · [SDRL](#entry-sdrl2026) · [SOLID](#entry-solid2026) · [SPO](#entry-spo2026) · [StepORLM](#entry-zhou2026steporlm) · [CALM / STORM](#entry-calm2025storm) · [HeurAgenix](#entry-yang2025heuragenix) · [LLMCoSolver / E2E CO Solver](#entry-jiang2025e2eco) · [MURKA](#entry-xie2025murka) · [SIRL](#entry-chen2025sirl) · [STRCMP](#entry-li2025strcmp)

</details>

<a id="tech-preference"></a>

<details>
<summary>Preference optimization (5 papers)</summary>

[EPOCH](#entry-epoch2026) · [MIND](#entry-mind2026) · [Multi-Warehouse Formulation Selection](#entry-warehouseformsel2026) · [OR-PRM](#entry-wang2026orprm) · [BPP-Search / StructuredOR](#entry-wang2025bppsearch)

</details>

<a id="tech-prm"></a>

<details>
<summary>Process rewards (4 papers)</summary>

[OR-PRM](#entry-wang2026orprm) · [ORLoopBench](#entry-ao2026orloopbench) · [StepORLM](#entry-zhou2026steporlm) · [BPP-Search / StructuredOR](#entry-wang2025bppsearch)

</details>

<a id="tech-solver-feedback"></a>

<details>
<summary>Execution / solver feedback (157 papers)</summary>

[A2DEPT](#entry-chen2026a2dept) · [AFL](#entry-zhang2026afl) · [Agentic MIP Research](#entry-xu2026agenticmip) · [Agora-Opt](#entry-soliloquy2026) · [AILS-AHD](#entry-xie2026ailsahd) · [Automated Inventory Policy Design](#entry-invpolicy2026) · [AutoModSAT](#entry-sun2025satheur) · [AutoOPT](#entry-autoopt2026) · [AutoOR](#entry-autoor2026) · [AutoREM / AutoRO-Bench](#entry-robustreform2026) · [AutoSAT](#entry-sun2024autosat) · [BiFE](#entry-bife2026) · [CALM (Algorithm–LM Co-evolution)](#entry-huang2025calm) · [CHORUS](#entry-lporch2025) · [CIR / R2C](#entry-canonicalir2026) · [Combinatorial Optimization for All](#entry-co4all2025) · [Constraint Injection / VRPCoder](#entry-constraintinjection2026) · [CP-Agent](#entry-cpagent2025) · [CP-SynC](#entry-cpsync2026) · [DeepOR](#entry-xiao2026deepor) · [DScheLLM](#entry-zhang2026dschellm) · [DSevolve](#entry-dsevolve2026) · [EPOCH](#entry-epoch2026) · [ES-AHD](#entry-es2026ahd) · [Evo-B&B](#entry-chen2026evobb) · [EVOM](#entry-guan2026evom) · [EvoOpt-LLM](#entry-he2026evoopt) · [EvoOptiGraph](#entry-evooptigraph2026) · [EvoOR-Agent](#entry-coevolve2026) · [Falsification-Based Verification](#entry-li2026falsification) · [FormuEvo](#entry-yuan2026formuevo) · [Full-Component ALNS Evolution](#entry-yu2026alns) · [G-LNS](#entry-zhao2026glns) · [GRIMIP](#entry-luo2026grimip) · [HeuriGym](#entry-chen2025heurigym) · [HiFo-Prompt](#entry-chen2025hifoprompt) · [Infeasibility-Aware CO Models](#entry-infeasibilityaware2026) · [InvEvolve](#entry-invevolve2026) · [LaGO](#entry-hsplo2026) · [Latent Heuristic Search](#entry-latentheuristic2026) · [LEAN-LLM-OPT](#entry-liang2026leanllmopt) · [LLaMoCo](#entry-ma2024llamoco) · [LLM Agents for Efficient Frontiers](#entry-efficientfrontier2026) · [LLM MIP Configuration](#entry-zhang2026autoconfig) · [LLM-guided Cutting-plane Management](#entry-zheng2026cutmgmt) · [LLM4Branch](#entry-llm4branch2026) · [MeEvo](#entry-meevo2026) · [MeLA](#entry-chen2025mela) · [MILP-Evo](#entry-milpevo2026) · [MIND](#entry-mind2026) · [MiniOpt](#entry-zhao2026miniopt) · [MIRROR](#entry-mirror2026) · [MoH](#entry-moh2025) · [MPaGE](#entry-ha2025paretogrid) · [Multi-Warehouse Formulation Selection](#entry-warehouseformsel2026) · [NEMO](#entry-nemo2026) · [OPT-BENCH / OPT-Agent](#entry-li2026optbench) · [Opt-Miner](#entry-optminer2026) · [OptGraph](#entry-xiu2026optgraph) · [OptiAgent](#entry-optiagent2026) · [OptiChat](#entry-chen2025optichat) · [OptiDSL](#entry-dslmilp2026) · [OptiLoop](#entry-optiloop2026) · [OptiRepair](#entry-optirepair2026) · [OptSkills](#entry-yang2026optskills) · [OR-PRM](#entry-wang2026orprm) · [OR-R1](#entry-ding2026orr1) · [ORLoopBench](#entry-ao2026orloopbench) · [PALL](#entry-yan2026pall) · [PathWise](#entry-pathwise2026) · [PEARL](#entry-lu2026pearl) · [PowerAtlas / ECBench](#entry-jiang2026poweratlas) · [PyVRP+ / MEP](#entry-pyvrpplus2026) · [RAG for Optimization & CP Modeling](#entry-roy2026rag) · [ReLoop / RetailOpt-190](#entry-lian2026reloop) · [RLEA](#entry-rlvrpagents2026) · [SAC-Opt](#entry-ma2025sacopt) · [SAGE (Strategy-Aware Modeling)](#entry-strategyaware2026) · [SDRL](#entry-sdrl2026) · [ShinkaEvolve](#entry-lange2026shinka) · [SOLID](#entry-solid2026) · [SpecAHD](#entry-lai2026specahd) · [SPO](#entry-spo2026) · [StepORLM](#entry-zhou2026steporlm) · [TIDE](#entry-chen2026tide) · [VeriSimpl](#entry-verisimpl2026) · [VRPAgent](#entry-vrpagent2025) · [AlphaEvolve](#entry-novikov2025alphaevolve) · [AlphaOPT](#entry-kong2025alphaopt) · [ARS / RoutBench](#entry-li2025ars) · [Ask, Clarify, Optimize](#entry-askclarify2026) · [C-DSS](#entry-kaleta2025cdss) · [CALM / STORM](#entry-calm2025storm) · [CEoH](#entry-bomer2025emerging) · [Cold-Start Separator Configuration](#entry-lawless2024cuts) · [DAOpt / OptU](#entry-daopt2025) · [DHEvo](#entry-dheevo2025) · [DINN](#entry-dinn2025) · [DRoC](#entry-jiang2025droc) · [EASE](#entry-viktorin2025ease) · [EFS](#entry-luo2025efs) · [FunSearch for Unit Commitment](#entry-ucfunsearch2025) · [HeurAgenix](#entry-yang2025heuragenix) · [HSEvo](#entry-dat2024hsevo) · [InstSpecHH](#entry-zhang2025instspechh) · [LHNS](#entry-xie2025llmns) · [LLaMEA](#entry-vanstein2024llamea) · [LLM-discovered EDDC / MDDC](#entry-cetinkaya2025mipsmtt) · [LLM-LNS](#entry-ye2025llmlns) · [LLM-SUC](#entry-llmsuc2025) · [LLMCoSolver / E2E CO Solver](#entry-jiang2025e2eco) · [LLMOPT](#entry-jiang2025llmopt) · [LLMs for Stochastic Modeling](#entry-talebi2025stochastic) · [MCTS-AHD](#entry-zheng2025mctsahd) · [MEoH](#entry-yao2025meoh) · [MILP-Evolve](#entry-li2025milpevolve) · [MM-Agent / MM-Bench (mathematical modeling)](#entry-liu2025mmagent) · [ModelingAgent / ModelingBench](#entry-qian2025modelingagent) · [MOID](#entry-moid2025) · [MURKA](#entry-xie2025murka) · [NCO-LLM for VRP](#entry-tran2025llmneural) · [OptimAI](#entry-thind2025optimai) · [OptiTrust](#entry-lima2025optitrust) · [OptMATH](#entry-lu2025optmath) · [OR-LLM-Agent / BWOR](#entry-zhang2025bwor) · [ORLM](#entry-huang2025orlm) · [ORMind](#entry-ormind2025) · [RedAHD](#entry-thach2025redahd) · [ReflecSched](#entry-cao2025reflecsched) · [ReSocratic / OptiBench](#entry-yang2025resocratic) · [RoCo](#entry-xu2025roco) · [SAGE / formerly EvoCut](#entry-yazdani2025evocut) · [SIRL](#entry-chen2025sirl) · [SolverLLM](#entry-solverllm2025) · [Step-Opt](#entry-wu2025stepopt) · [STRCMP](#entry-li2025strcmp) · [Validation-in-the-Loop Power Modeling](#entry-nl2ps2025) · [Visual Graph Optimization with MLLMs](#entry-bridgingviz2025) · [CAFA](#entry-deng2024cafa) · [Chain-of-Experts](#entry-xiao2024coe) · [City-LEO](#entry-jiao2024cityleo) · [EoH](#entry-liu2024eoh) · [ITINERA](#entry-tang2024itinerary) · [Multi-Stage Modeling & Verification](#entry-mostajabdaveh2024multiagent) · [OptiChat / Infeasibility Diagnosis](#entry-chen2023diagnosing) · [OptiMUS](#entry-teshnizi2024optimus) · [OptLLM](#entry-zhang2024optllm) · [RAGDyS](#entry-tang2024ragdys) · [Rare MIP Challenges](#entry-wang2024raremip) · [ReEvo](#entry-ye2024reevo) · [To the Globe / TTG](#entry-ju2024ttg) · [AEL](#entry-liu2023ael) · [AI-Copilot for Business Optimisation](#entry-alahakoon2023copilot) · [CodeT5 Mathematical Program Synthesis](#entry-synth2023) · [FunSearch](#entry-romera2023funsearch) · [LLMs for Power Engineering](#entry-li2023power) · [OptiGuide](#entry-li2023optiguide)

</details>

<a id="tech-formal"></a>

<details>
<summary>Formal verification (2 papers)</summary>

[AutoOPT](#entry-autoopt2026) · [SOVER / NLEquiv-150](#entry-bhattacharyya2026sover)

</details>

<a id="tech-behavioral"></a>

<details>
<summary>Behavioral testing (7 papers)</summary>

[Constraint Injection / VRPCoder](#entry-constraintinjection2026) · [Falsification-Based Verification](#entry-li2026falsification) · [NEMO](#entry-nemo2026) · [OptiLoop](#entry-optiloop2026) · [OptiRepair](#entry-optirepair2026) · [ReLoop / RetailOpt-190](#entry-lian2026reloop) · [ORMind](#entry-ormind2025)

</details>

<a id="tech-auxiliary-learning"></a>

<details>
<summary>Auxiliary / NCO learning (9 papers)</summary>

[DSevolve](#entry-dsevolve2026) · [Latent Heuristic Search](#entry-latentheuristic2026) · [LLM Representations for Algorithm Selection](#entry-behaviorrep2025) · [LLM-MAS for Service Operations](#entry-wang2026llmmas) · [RLEA](#entry-rlvrpagents2026) · [DINN](#entry-dinn2025) · [InstSpecHH](#entry-zhang2025instspechh) · [NCO-LLM for VRP](#entry-tran2025llmneural) · [STRCMP](#entry-li2025strcmp)

</details>

<a id="tech-multimodal"></a>

<details>
<summary>Multimodal input (2 papers)</summary>

[MM-OptBench](#entry-zhu2026mmoptbench) · [Visual Graph Optimization with MLLMs](#entry-bridgingviz2025)

</details>


[Back to contents](#contents)

<a id="applications"></a>

## Application index

Browse core application settings and jump to complete paper entries.

| Application | Count | Papers |
|---|---|---|
| <a id="app-scheduling"></a>Scheduling and production | 12 | [DScheLLM](#entry-zhang2026dschellm) · [DSevolve](#entry-dsevolve2026) · [DynaSchedBench](#entry-dynaschedbench2026) · [Interactive Optimization Conversations](#entry-conversation2026) · [PowerAtlas / ECBench](#entry-jiang2026poweratlas) · [SMILO](#entry-li2025smilo) · [ALAS](#entry-alas2025) · [LLM-discovered EDDC / MDDC](#entry-cetinkaya2025mipsmtt) · [ReflecSched](#entry-cao2025reflecsched) · [Starjob](#entry-abgaryan2025starjob) · [RAGDyS](#entry-tang2024ragdys) · [AI-Copilot for Business Optimisation](#entry-alahakoon2023copilot) |
| <a id="app-routing"></a>Routing and logistics | 17 | [AFL](#entry-zhang2026afl) · [AILS-AHD](#entry-xie2026ailsahd) · [Combinatorial Optimization for All](#entry-co4all2025) · [Constraint Injection / VRPCoder](#entry-constraintinjection2026) · [ORThought / LogiOR](#entry-yang2025orthought) · [PyVRP+ / MEP](#entry-pyvrpplus2026) · [RLEA](#entry-rlvrpagents2026) · [SpecAHD](#entry-lai2026specahd) · [SPO](#entry-spo2026) · [VRPAgent](#entry-vrpagent2025) · [ARS / RoutBench](#entry-li2025ars) · [DRoC](#entry-jiang2025droc) · [MOID](#entry-moid2025) · [NCO-LLM for VRP](#entry-tran2025llmneural) · [City-LEO](#entry-jiao2024cityleo) · [ITINERA](#entry-tang2024itinerary) · [To the Globe / TTG](#entry-ju2024ttg) |
| <a id="app-inventory"></a>Inventory, retail, and supply chains | 15 | [Automated Inventory Policy Design](#entry-invpolicy2026) · [GenAI Beer Game Reliability](#entry-beergame2026) · [InventoryBench](#entry-invbench2026) · [InvEvolve](#entry-invevolve2026) · [LLM-MAS for Service Operations](#entry-wang2026llmmas) · [Multi-Warehouse Formulation Selection](#entry-warehouseformsel2026) · [OptiRepair](#entry-optirepair2026) · [ORLoopBench](#entry-ao2026orloopbench) · [ReLoop / RetailOpt-190](#entry-lian2026reloop) · [RetailBench](#entry-zhang2026retailbench) · [AIM-Bench](#entry-zhao2025aimbench) · [Ask, Clarify, Optimize](#entry-askclarify2026) · [EOR / Decision Information](#entry-zhang2025decisioninfo) · [InvAgent](#entry-quan2024invagent) · [OptiGuide](#entry-li2023optiguide) |
| <a id="app-energy"></a>Energy and power systems | 9 | [OPF Constrained Reasoning Study](#entry-opf2026reason) · [PowerAtlas / ECBench](#entry-jiang2026poweratlas) · [ProOPF](#entry-shen2026proopf) · [Smart Grids Agentic AI Tutorial](#entry-smartgrid2026) · [ElecBench](#entry-zhou2024elecbench) · [FunSearch for Unit Commitment](#entry-ucfunsearch2025) · [LLM-SUC](#entry-llmsuc2025) · [Validation-in-the-Loop Power Modeling](#entry-nl2ps2025) · [LLMs for Power Engineering](#entry-li2023power) |
| <a id="app-finance"></a>Finance and portfolios | 5 | [LEAN-LLM-OPT](#entry-liang2026leanllmopt) · [LLM Agents for Efficient Frontiers](#entry-efficientfrontier2026) · [DINN](#entry-dinn2025) · [EFS](#entry-luo2025efs) · [LLM–Black-Litterman](#entry-llmbl2025) |
| <a id="app-warehousing"></a>Warehousing and loading | 1 | [CEoH](#entry-bomer2025emerging) |
| <a id="app-networks"></a>Networks and graph optimization | 5 | [Infeasibility-Aware CO Models](#entry-infeasibilityaware2026) · [LLMs for DSM Sequencing](#entry-dsmco2024) · [MA-GTS / G-REAL](#entry-yuan2025magts) · [Teaching LLMs to Think Mathematically](#entry-abedi2025thinkmath) · [Visual Graph Optimization with MLLMs](#entry-bridgingviz2025) |

[Back to contents](#contents)

<a id="adjacent"></a>

## Related research

General program and scientific discovery, open-ended mathematical modeling, and prediction- or simulation-driven decision support.

### General program and scientific discovery

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · ICLR 2026 | **ShinkaEvolve**<br>ShinkaEvolve: Towards Open-Ended and Sample-Efficient Program Evolution | Combines parent sampling, novelty-based rejection sampling, and bandit model selection for more sample-efficient program evolution. | Method · Platform | [Program evolution](#tech-evolution) · [Memory](#tech-memory) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r344] · [![Paper 2][b002]][r345] · [![Code][b012]][r346] · [Details](#paper-lange2026shinka) |
| 2025 · Technical report | **AlphaEvolve** (Core)<br>AlphaEvolve: A coding agent for scientific and algorithmic discovery | Improves algorithms through LLM-driven evolutionary code changes, spanning scientific problems and computing infrastructure optimization. | Method | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r419] · [![Official results (related)][b098]][r420] · [![Official problem collection (related)][b099]][r421] · [Details](#paper-novikov2025alphaevolve) |
| 2023 · Nature (online 2023) | **FunSearch** (Core)<br>Mathematical discoveries from program search with large language models | Combines LLM program generation, evolutionary search, and automated evaluation to discover mathematical constructions and bin-packing heuristics. | Method · Foundational | [Program evolution](#tech-evolution) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b013]][r391] · [![Code][b012]][r392] · [Details](#paper-romera2023funsearch) |

### Open-ended mathematical modeling

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2025 · NeurIPS 2025 | **MM-Agent / MM-Bench (mathematical modeling)** (Exploratory)<br>MM-Agent: LLM as Agents for Real-world Mathematical Modeling Problem | Decomposes mathematical modeling into analysis, formulation, computation, and report generation, introducing MM-Bench from MCM/ICM problems. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r538] · [![Paper 2][b002]][r539] · [![Paper 3][b122]][r540] · [![Code & MM-Bench][b123]][r541] · [![Expert Skills (2026 add-on)][b124]][r542] · [![HF Demo (related)][b028]][r543] · [Details](#paper-liu2025mmagent) |
| 2025 · Findings of EMNLP 2025 | **ModelingAgent / ModelingBench** (Exploratory)<br>ModelingAgent: Bridging LLMs and Mathematical Modeling for Real-World Challenges | Coordinates tools and iterative revisions through multiple agents for open-ended modeling, evaluating reports with ModelingBench and ModelingJudge. | Method · Benchmark · Data | [Agent](#tech-agent) · [Multi-agent](#tech-multi-agent) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper 1][b001]][r544] · [![Paper 2][b002]][r545] · [![Code & ModelingBench][b125]][r546] · [Details](#paper-qian2025modelingagent) |

### Prediction, representations, and behavioral simulation

| Year / Venue | Paper | Contribution summary | Contributions | Techniques | Resources |
|---|---|---|---|---|---|
| 2026 · arXiv preprint | <a id="entry-wang2026llmmas"></a>**LLM-MAS for Service Operations**<br>Optimizing Service Operations via LLM-Powered Multi-Agent Simulation | Simulates participant responses with interactive LLMs and optimizes service design using trajectory-based gradient estimates and variance reduction. | Method · Application | [Agent](#tech-agent) · [Auxiliary / NCO learning](#tech-auxiliary-learning) | [![Paper][b009]][r558] · [Details](#paper-wang2026llmmas) |
| 2025 · arXiv preprint / submitted paper | <a id="entry-dinn2025"></a>**DINN** (Exploratory)<br>Decision-informed Neural Networks with Large Language Model Integration for Portfolio Optimization | Combines LLM representations and decision-focused training through a differentiable convex optimization layer aligned with portfolio objectives. | Method · Application | [Auxiliary / NCO learning](#tech-auxiliary-learning) · [Execution / solver feedback](#tech-solver-feedback) | [![Paper][b009]][r559] · [![Code][b012]][r560] · [Details](#paper-dinn2025) |
| 2025 · IEEE PESGM 2025 | **ElecBench** (Exploratory)<br>ElecBench: a Power Grid Dispatch Evaluation Benchmark for Large Language Models | Evaluates factuality, logic, and stability on text tasks covering power-system knowledge, monitoring, dispatch, and black start. | Benchmark · Data |  | [![Paper 1][b001]][r548] · [![Paper 2][b002]][r549] · [![Public Test Subset][b126]][r550] · [Details](#paper-zhou2024elecbench) |
| 2025 · CIKM 2025 Financial AI Workshop | <a id="entry-llmbl2025"></a>**LLM–Black-Litterman** (Exploratory)<br>LLM-Enhanced Black-Litterman Portfolio Optimization | Converts LLM return forecasts and uncertainty into Black–Litterman investment views and confidence estimates. | Method · Application |  | [![Paper 1][b003]][r561] · [![Workshop][b104]][r562] · [![Code][b012]][r563] · [Details](#paper-llmbl2025) |


<a id="contributing"></a>

## Scope and contributions

Contributions through Issues or Pull Requests are welcome. Please provide the title, authors, year, publication status, paper link, a concise contribution summary, and confirmed resource links. Each work has one stable ID, with related versions recorded together. Papers may belong to multiple modules; see the [Classification guide](#classification).

- **Scope:** Prioritizes optimization modeling, solvers, OR algorithms, and relevant evaluation; adjacent research is explicitly labeled.
- **Accuracy:** Distinguishes publication, author-reported acceptance, preprints, and workshops. A resource's existence does not establish an official release. Checks cover metadata, method summaries, and link-level evidence; they do not imply experimental reproduction.
- **Citations and versions:** See this page's [paper information](#paper-info) for authors, related versions, and resource scope. Cite formal paper records or original citations with explicit version information.

Related collections: [LLM4OR][r016] · [awesome-fm4co][r564] · [LLM4AlgorithmDesign][r005]. This collection checks entries individually and applies its own multi-label taxonomy; inclusion in external lists alone does not establish verification.

<a id="paper-info"></a>

## Authors, versions, and resource notes

Records follow formal publications or specified preprints. Each work retains one ID; authors, titles, and experimental scope may differ between related versions.

| Paper and authors | Version and resource notes |
|---|---|
| <a id="paper-chen2026a2dept"></a>**A2DEPT**<br>Bin Chen; Shouliang Zhu; Beidan Liu; Yong Zhao; Tianle Pu; Huichun Li; Zhengqiu Zhu | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2604.24043v1<br>Program-tree evolution is classified separately from LLM parameter training. |
| <a id="paper-zhang2026afl"></a>**AFL**<br>Zhang, Ni; Cao, Zhiguang; Zhou, Jianan; Zhang, Cong; Ong, Yew-Soon | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2510.16701v2<br>Distinct from DRoC's external-solver/document-retrieval approach. High experimental feasibility does not guarantee correctness for arbitrary new constraints. |
| <a id="paper-xu2026agenticmip"></a>**Agentic MIP Research**<br>Xu, Liding; Zhou, Yugeng; Pokutta, Sebastian | Primary focus: Solver components and configuration<br>Summary version: 2605.09186v1<br>The author homepage lists the paper as submitted. Framework tests and solving evaluations do not mathematically prove every generated propagation rule valid. Other author SCIP repositories lack explicit attribution and are omitted. |
| <a id="paper-soliloquy2026"></a>**Agora-Opt**<br>Jianghao Lin; Zi Ling; Chenyu Zhou; Tianyi Xu; Ruoqing Jiang; Zizhuo Wang; Dongdong Ge | Primary focus: Optimization modeling and code generation<br>Summary version: 2604.25847v1<br>Revised data use seven existing benchmark groups; solution agreement is distinguished from full fidelity to problem intent. |
| <a id="paper-xie2026ailsahd"></a>**AILS-AHD**<br>Zhuoliang Xie; Fei Liu; Zhenkun Wang; Qingfu Zhang | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2602.23092v2<br>AILS-CVRP and PyHygese serve as baselines or underlying tools. |
| <a id="paper-invpolicy2026"></a>**Automated Inventory Policy Design**<br>Yang, Fenghua; Baxi, Preet; Zhang, Yi; Jasin, Stefanus; Lei, Yanzhe; Liu, Mo; Pakiman, Parshan | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2609.08071v1 |
| <a id="paper-sun2025satheur"></a>**AutoModSAT**<br>Sun, Yiwen; Ye, Furong; Chen, Zhihan; Wei, Ke; Cai, Shaowei | Primary focus: Solver components and configuration<br>Summary version: 2507.22876v2<br>Automatically Discovering Heuristics in a Complex SAT Solver with Large Language Models [![Version][b159]][r447]: Preprint title includes Automatically; the current formal title omits it<br>The final title changed from Automatically discovering to Discovering, following Nature Communications. AutoSAT is a related independent paper and retains its own record. |
| <a id="paper-autoopt2026"></a>**AutoOPT**<br>Heechang Kim; Ernest K. Ryu; Shuvomoy Das Gupta | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2608.07407v1<br>An adjacent direction in continuous optimization algorithm research. Formal claims for the two case studies depend on specific assumptions; the workflow still includes human review. |
| <a id="paper-autoor2026"></a>**AutoOR**<br>Motwani, Sumeet Ramesh; Du, Chuan; Petrov, Aleksander; Davis, Christopher; Torr, Philip; Papania-Davis, Antonio; Yan, Weishi | Primary focus: Optimization modeling and code generation<br>Summary version: 2604.16804v4<br>The ICML 2026 page identifies the RLxF (RL from World Feedback) Workshop, not the main conference. arXiv uses Autoformulate; the conference page uses Autoformalize. Standard verifiers / TRL libraries are not the method's implementation. |
| <a id="paper-robustreform2026"></a>**AutoREM / AutoRO-Bench**<br>Chen, Jinbiao; Jin, Shuang; Zhang, Guoyun; Zhang, Junyu; Wang, Guanyi; Qin, Hanzhang | Primary focus: Optimization modeling and code generation<br>Summary version: 2605.11813v1<br>Uses offline-adapted experience memory. |
| <a id="paper-sun2024autosat"></a>**AutoSAT**<br>Sun, Yiwen; Ye, Furong; Zhang, Xianyin; Huang, Shiyu; Zhang, Bingzhen; Wei, Ke; Cai, Shaowei | Primary focus: Solver components and configuration<br>Summary version: 2402.10705v3<br>DOI metadata confirms JAIR publication in 2026; the historical 2024 ID remains. SAT solver enhancement is distinguished from MILP propagation components. |
| <a id="paper-bife2026"></a>**BiFE**<br>Zhang, Ce; Zhang, Bin; Xu, Zhiwei; Chen, Hao; Lu, Xinyue; Fan, Shanwei; Teng, Yingxuan; Fan, Guoliang | Primary focus: Solver components and configuration<br>Summary version: 2609.36735v1 |
| <a id="paper-huang2025calm"></a>**CALM (Algorithm–LM Co-evolution)**<br>Ziyao Huang; Weiwei Wu; Kui Wu; Wei-Bin Lee; Jianping Wang | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2505.12285v1<br>CALM: Co-evolution of Algorithms and Language Model for Automatic Heuristic Design [![Version][b159]][r309]: Preprint version; formal citation follows proceedings metadata; Authors: Ziyao Huang; Weiwei Wu; Kui Wu; Jianping Wang; Wei-Bin Lee<br>The formal citation follows ICLR proceedings; the repository provides GRPO code. Distinct from CALM Before the STORM. |
| <a id="paper-lporch2025"></a>**CHORUS**<br>Tasnim Ahmed; Salimur Choudhury | Primary focus: Optimization modeling and code generation<br>Summary version: 2505.01485v1<br>LION 19 took place in 2025; the formal chapter appeared on 2026-01-02. Citations use 2026 and the historical ID remains. Objective matching is the evaluation's operational criterion. |
| <a id="paper-canonicalir2026"></a>**CIR / R2C**<br>Lyu, Zhongyuan; Hu, Shuoyu; Liu, Lujie; Yang, Hongxia; LI, Ming | Primary focus: Optimization modeling and code generation<br>Summary version: 2602.02029v1<br>The intermediate representation supports constraint semantics and modeling-paradigm selection; it does not automatically guarantee correctness across solvers. |
| <a id="paper-sun2026cobench"></a>**CO-Bench**<br>Sun, Weiwei; Feng, Shengyu; Li, Shanda; Yang, Yiming | Primary focus: Benchmarks and evaluation<br>Published at AAAI 2026; the HF data resource is CO-Bench/CO-Bench. |
| <a id="paper-co4all2025"></a>**Combinatorial Optimization for All**<br>Camilo Chacón Sartori; Christian Blum | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2503.10968v1<br>Combinatorial Optimization for All: Using LLMs to Aid Non-Experts in Improving Optimization Algorithms [![Version][b159]][r313]: Preprint version; formal citation follows DOI registration metadata; Authors: Camilo Chacón Sartori; Christian Blum<br>Author resources include prompts, generated algorithms, instances, and results; these are not labeled a new general-purpose CO benchmark. |
| <a id="paper-lco2026review"></a>**Combinatorial Optimization Systematic Review**<br>Francesca Da Ros; Michael Soprano; Luca Di Gaspero; Kevin Roitero | Primary focus: Surveys<br>Summary version: 2507.03637v1<br>Large Language Models for Combinatorial Optimization: A Systematic Review [![Version][b159]][r002]: Preprint version; formal citation follows DOI registration metadata; Authors: Francesca Da Ros; Michael Soprano; Luca Di Gaspero; Kevin Roitero |
| <a id="paper-constraintinjection2026"></a>**Constraint Injection / VRPCoder**<br>Luo, Xizi; He, Changhong; Geng, Dongdong; Shi, Chenggong; Mei, Yu | Primary focus: Model verification, diagnosis, and repair<br>Summary version: 2606.04816v2<br>The VRPBench repository provides problems and reference optima. |
| <a id="paper-constraintbench2026"></a>**ConstraintBench**<br>Tso, Joseph; Schmittou, Preston; Huynh, Quan; Hutchins, Jibran | Primary focus: Benchmarks and evaluation<br>Summary version: 2602.22465v2 |
| <a id="paper-coopa2026"></a>**COOPA**<br>Chuanhao Li; Xiaoan Xu; Dirk Bergemann; Ethan X. Fang; Yehua Wei; Zhuoran Yang | Primary focus: Optimization modeling and code generation<br>Summary version: 2606.27611v1<br>Confidence is self-assessed by the model. Traceable provenance does not guarantee formal correctness or probabilistic calibration. |
| <a id="paper-cpagent2025"></a>**CP-Agent**<br>Szeider, Stefan | Primary focus: Optimization modeling and code generation<br>Summary version: 2508.07468v3<br>Published at ICSE 2026's LLM4Code Workshop; the historical 2025 ID remains. The Zenodo concept DOI resolves to v2 (2026-07-14), which reports fixes to validation issues found by mutation auditing. Original and revised experimental results remain separate.<br>Author Coding Agent: Author's general coding agent and CPMpy template; experimental and revised evaluation materials are released separately on Zenodo. |
| <a id="paper-cpsync2026"></a>**CP-SynC**<br>Song, Yuliang; Cohen, Eldan | Primary focus: Optimization modeling and code generation<br>Summary version: 2605.01675v1<br>The official repository provides benchmarks and eval.py.<br>Benchmark & Evaluation: Provides data and evaluation code. |
| <a id="paper-xiao2026deepor"></a>**DeepOR**<br>Ziyang Xiao; Yuan Jessica Wang; Xiongwei Han; Shisi Guan; Jingyan Zhu; Jingrong Xie; Lilin Xu; Han Wu; Wing Yin Yu; Zehua Liu; Xiaojin Fu; Gang Chen; Dongxiang Zhang | Primary focus: Optimization modeling and code generation<br>Publication metadata follows the formal AAAI 2026 paper page.<br>Official seeds and sample data: The README provides seeds and SFT/RL samples. |
| <a id="paper-zhang2026dschellm"></a>**DScheLLM**<br>Zhang, Lixiang; Zhao, Chenggong; Gao, Qing; Zhao, Xiaoke; Bai, Gengyi; Lv, Jinhu | Primary focus: Direct solution generation and optimization decisions<br>Summary version: 2601.09100<br>The data statement identifies research data as part of the article. |
| <a id="paper-dsevolve2026"></a>**DSevolve**<br>Zhou, XinLei; Huang, Jin; Yang, Jie; Li, Xinyu; Gao, Liang | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2603.27628v2<br>Title and method follow arXiv v2. Neural-selector training is not automatically LLM fine-tuning; results from other versions remain separate. |
| <a id="paper-dynaschedbench2026"></a>**DynaSchedBench**<br>Cao, Shijie; Yuan, Yuan; Liu, Jing | Primary focus: Benchmarks and evaluation<br>Summary version: 2605.27566v1<br>The repository releases instance generators, data, simulation, and evaluation code. ICML 2026 proceedings publication is confirmed. |
| <a id="paper-epoch2026"></a>**EPOCH**<br>Oguzhan Gungordu; Ayse Tursucular; Siheng Xiong; Faramarz Fekri | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2610.17379v1 |
| <a id="paper-es2026ahd"></a>**ES-AHD**<br>Yutao Lai; Kezhao Lai; Hai-Lin Liu; Yuping Wang; Ping Guo | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2609.00023v1<br>The official final ICIST 2026 program lists the title and Hai-Lin Liu, confirming acceptance but not a formal proceedings record. Full authors follow the preprint; the speaker does not replace the author list. The repository contains run_es_ahd.py and llm4ad implementation directories. |
| <a id="paper-chen2026evobb"></a>**Evo-B&B**<br>Chen, Jiayu; Chen, Chentong; Liu, Yuhan; Fan, Ye; Sun, Jianyong; Shi, Jialong | Primary focus: Solver components and configuration<br>Summary version: 2610.22861v1 |
| <a id="paper-guan2026evom"></a>**EVOM**<br>Guan, Runda; Shen, Xiangqing; Zhang, Jiajun; Zhang, Yifan; Cheng, Jian; Xia, Rui | Primary focus: Optimization modeling and code generation<br>Summary version: 2604.00442v1<br>Successful execution and matching objectives are distinguished from mathematical proofs of fidelity to problem intent. |
| <a id="paper-he2026evoopt"></a>**EvoOpt-LLM**<br>Yiliu He; Tianle Li; Binghao Ji; Zhiyuan Liu; Di Huang | Primary focus: Optimization modeling and code generation<br>Summary version: 2602.01082<br>Code uses the Openpangu-7B base model; base-model downloads are not EvoOpt fine-tuned weights. Empirical pruning classification metrics do not guarantee preservation of optimality in general. |
| <a id="paper-evooptigraph2026"></a>**EvoOptiGraph**<br>Qingcan Kang; Mingyang Liu; Xiaojin Fu; Shixiong Kai; Tao Zhong; Mingxuan Yuan | Primary focus: Optimization modeling and code generation<br>Summary version: 2606.26578v1<br>Graph operations, compilation, and back-translation checks depend on the paper's assumptions. NeurIPS 2026 acceptance is confirmed by the official poster schedule. |
| <a id="paper-coevolve2026"></a>**EvoOR-Agent**<br>Jiahao Huang; Peilan Xu; Xiaoya Nan; Wenjian Luo | Primary focus: Optimization modeling and code generation<br>Summary version: 2604.17708v2<br>Evolution targets agent architectures and reasoning programs. |
| <a id="paper-li2026falsification"></a>**Falsification-Based Verification**<br>Li, Haifeng; Hai, Mo | Primary focus: Model verification, diagnosis, and repair<br>Summary version: 2607.16646v2<br>Follows arXiv v2; this is a conditional falsification audit whose scope depends on the paper's assumptions. |
| <a id="paper-wang2026formalize"></a>**Formalize, Don't Optimize**<br>Wang, Haoyu; Song, Yuliang; Li, Tao; Deng, Zhiwei; Wang, Yaqing; Ramachandran, Deepak; Cohen, Eldan; Roth, Dan | Primary focus: Benchmarks and evaluation<br>Summary version: 2605.12421v1<br>Associated with the NeurIPS 2026 Who Verifies the Agents? Workshop; introduces CP-SynC-XL evaluation. |
| <a id="paper-yuan2026formuevo"></a>**FormuEvo**<br>Yuan, Haofeng; Peng, Jianing; Bi, Jieyi; Zhang, Ni; Song, Shiji; Cao, Zhiguang | Primary focus: Solver components and configuration<br>Summary version: 2608.23353v2<br>Runtime feedback supports empirical diagnosis; formal equivalence requires separate verification. |
| <a id="paper-kong2026frontieror"></a>**FrontierOR**<br>Kong, Minwei; Jiang, Chonghe; Qu, Ao; Ouyang, Wenbin; Zeng, Zhaoming; Guo, Xiaotong; Li, Zhekai; Li, Junyi; Fan, Yi; Zheng, Xinshou; Jing, Xi; Zhang, Yikai; Liang, Zhiwei; Kim, Seonghoo; Yang, Runqing; Zhou, Zijian; Li, Sirui; Zheng, Han; Ying, Wangyang; Zheng, Ou; Wang, Chonghuan; Zhao, Jinglong; Qin, Hanzhang; Wu, Cathy; Liang, Paul Pu; Zhao, Jinhua; Wang, Hai | Primary focus: Benchmarks and evaluation<br>Summary version: 2605.25246v3<br>Related version [![Version][b160]][r513]: FrontierOR-v1, 180 tasks; released 2026-09-27<br>Related version [![Version][b161]][r510]: Conference abstract describes 110 tasks; version-specific scope remains separate<br>Current arXiv and official data contain 180 tasks; the NeurIPS abstract describes 110. Counts remain version-specific. Acceptance is confirmed by the official poster schedule. |
| <a id="paper-yu2026alns"></a>**Full-Component ALNS Evolution**<br>Yu, Shaohua; Chen, Tianyu; Liu, Linyan; Puchinger, Jakob | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2603.06996v2<br>The official repository provides evolved ALNS programs and summaries.<br>Evolved ALNS: The data statement and directory tree confirm evolved outputs, not release of the complete framework. |
| <a id="paper-zhao2026glns"></a>**G-LNS**<br>Zhao, Baoyun; Wang, He; Zeng, Liang | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2602.08253v1 |
| <a id="paper-beergame2026"></a>**GenAI Beer Game Reliability**<br>Long, Carol Xuan; Simchi-Levi, David; Zhu, Feng; Su, Huangyuan; Calmon, Andre P.; Calmon, Flavio P. | Primary focus: Direct solution generation and optimization decisions<br>Summary version: 2605.17036v4<br>Uses the existing Beer Game to study reliability, rather than automatically introducing a new inventory benchmark. Results depend on specific configurations and demand trajectories. |
| <a id="paper-luo2026grimip"></a>**GRIMIP**<br>Luo, Yidong; Chen, Xuemin; Wang, Chenguang; Zhu, Fangzhou; Zhong, Tao; Yu, Tianshu | Primary focus: Solver components and configuration<br>Summary version: 2606.23299v2 |
| <a id="paper-chen2025heurigym"></a>**HeuriGym**<br>Chen, Hongzheng; Wang, Yingheng; Cai, Yaohui; Hu, Hins; Li, Jiajie; Huang, Shirley; Deng, Chenhui; Liang, Rongjian; Kong, Shufeng; Ren, Haoxing; Samaranayake, Samitha; Gomes, Carla P.; Zhang, Zhiru | Primary focus: Benchmarks and evaluation<br>Summary version: 2506.07972v2<br>Published at ICLR 2026. |
| <a id="paper-chen2025hifoprompt"></a>**HiFo-Prompt**<br>Chentong Chen; Mengyuan Zhong; Jialong Shi; Jianyong Sun; Ye Fan | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2508.13333v2<br>HiFo-Prompt: Prompting with Hindsight and Foresight for LLM-based Automatic Heuristic Design [![Version][b159]][r322]: Preprint version; formal citation follows proceedings metadata; Authors: Chentong Chen; Mengyuan Zhong; Ye Fan; Jialong Shi; Jianyong Sun |
| <a id="paper-infeasibilityaware2026"></a>**Infeasibility-Aware CO Models**<br>Yakun Wang; Min Chen; Zeguan Wu; Junyu Liu; Sitao Zhang; Zhenwen Shao | Primary focus: Direct solution generation and optimization decisions<br>Summary version: 2604.01455v1<br>Data certification and filtering theorems have explicit conditions; Google Drive provides graph-coloring and embedding folders.<br>Author Code / Data Archive: Paper-linked code and data archive. |
| <a id="paper-conversation2026"></a>**Interactive Optimization Conversations**<br>Drossman, Joshua; Jacquillat, Alexandre; Martin, Sébastien | Primary focus: Optimization modeling and code generation<br>Summary version: 2604.02666v1<br>The paper's repository has an empty README, but its tree includes decision_agent and evaluation code. An empty README does not imply no implementation. |
| <a id="paper-invbench2026"></a>**InventoryBench**<br>Baek, Jackie; Fu, Yaopeng; Ma, Will; Peng, Tianyi | Primary focus: Benchmarks and evaluation<br>Summary version: 2602.12631v2 |
| <a id="paper-invevolve2026"></a>**InvEvolve**<br>Huang, Chenyu; Lin, Jianghao; Tang, Zhengyang; Jiang, Bo; Jiang, Ruoqing; Wang, Benyou; Wei, Lai | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2605.00369v4 |
| <a id="paper-jorbench2026"></a>**JOR-Bench**<br>Yuu Jinnai | Primary focus: Benchmarks and evaluation<br>Summary version: 2607.16777v1<br>Japanese translations are derived resources, not five newly introduced source benchmarks. HF's 2,638 rows include both languages, not 2,638 distinct source problems. Matching solutions does not establish full semantic correctness. |
| <a id="paper-hsplo2026"></a>**LaGO**<br>Mingxin Yu; Ruixiao Yang; Chuchu Fan | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2602.16038v1<br>Forward / backward / update denote evaluation, feedback, and program rewriting, not necessarily LLM backpropagation or training. The cited ReEvo repository is not listed as this method's code. |
| <a id="paper-latentheuristic2026"></a>**Latent Heuristic Search**<br>Cheikh Ahmed; Mahdi Mostajabdaveh; Zirui Zhou | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2605.17137v1<br>The official LION 20 list and schedule confirm acceptance; code is available. Training targets auxiliary encoding/surrogate/mapping modules while the generating LLM stays frozen. |
| <a id="paper-liang2026leanllmopt"></a>**LEAN-LLM-OPT**<br>Liang, Kuo; Lu, Yuhang; Mao, Jianming; Sun, Shuyi; Yang, Chunwei; Zeng, Congcong; Jin, Xiao; Qin, Hanzhang; Zhu, Ruihao; Teo, Chung-Piaw | Primary focus: Optimization modeling and code generation<br>Summary version: 2601.09635v3 |
| <a id="paper-ma2024llamoco"></a>**LLaMoCo**<br>Zeyuan Ma; Yue-Jiao Gong; Hongshu Guo; Jiacheng Chen; Yining Ma; Zhiguang Cao; Jun Zhang | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2403.01131v2<br>LLaMoCo: Instruction Tuning of Large Language Models for Optimization Code Generation [![Version][b159]][r330]: Preprint version; formal citation follows DOI registration metadata; Authors: Zeyuan Ma; Hongshu Guo; Jiacheng Chen; Guojun Peng; Zhiguang Cao; Yining Ma; Yue-Jiao Gong<br>Authors are listed separately for TEVC 2026 and the 2024 preprint. LLaMoCo-S examples and CodeGen weights are available. |
| <a id="paper-efficientfrontier2026"></a>**LLM Agents for Efficient Frontiers**<br>Paquette-Greenbaum, Simon; Yu, Jiangbo | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2601.00770v1 |
| <a id="paper-zhang2026autoconfig"></a>**LLM MIP Configuration**<br>Michael Zhang; Justin Okamoto; Antonia Chmiela; Oleksandr Radomskyi; Christian Schulz; Jeremy L Wyatt | Primary focus: Solver components and configuration<br>NeurIPS explicitly labels this a poster in the Second Workshop on MLxOR, not evidence of main-conference acceptance. Authors follow that official page. |
| <a id="paper-behaviorrep2025"></a>**LLM Representations for Algorithm Selection**<br>Francesca Da Ros; Luca Di Gaspero; Kevin Roitero | Primary focus: Benchmarks and evaluation<br>Summary version: 2512.13374v2<br>Behavior and Representation in Open-Weight Large Language Models for Combinatorial Optimization: From Feature Extraction to Algorithm Selection [![Version][b159]][r519]: Preprint version; formal citation follows DOI registration metadata; Authors: Francesca Da Ros; Luca Di Gaspero; Kevin Roitero<br>The publisher record is scheduled for the December 2026 issue; Zenodo archives code, data, activations, and probing experiments.<br>Code & Analysis Data: Approximately 1.32 GB archive with code, data, activations, and probing experiments described in its file list and README; no new domain-model weights are claimed. |
| <a id="paper-zheng2026cutmgmt"></a>**LLM-guided Cutting-plane Management**<br>Zheng, Zetao; Wang, Zhe; Shao, Jie | Primary focus: Solver components and configuration |
| <a id="paper-wang2026llmmas"></a>**LLM-MAS for Service Operations**<br>Wang, Yanyuan; Zhang, Xiaowei | Primary focus: Related research<br>Summary version: 2604.04383v1<br>LLMs simulate behavior while an outer algorithm updates design parameters; this is not direct numerical optimization by the LLM. |
| <a id="paper-liu2024systematic"></a>**LLM4AD Survey**<br>Liu, Fei; Yao, Yiming; Guo, Ping; Yang, Zhiyuan; Zhao, Zhe; Lin, Xi; Tong, Xialiang; Mao, Kun; Lu, Zhichao; Wang, Zhenkun; Yuan, Mingxuan; Zhang, Qingfu | Primary focus: Surveys<br>ACM records formal publication on 2026-02-10. The historical 2024 ID remains; the record uses publication year 2026 and arXiv authors. |
| <a id="paper-llm4branch2026"></a>**LLM4Branch**<br>Hou, Zhinan; Li, Xingchen; Zhang, Yankai; Li, Tianxun; You, Keyou | Primary focus: Solver components and configuration<br>Summary version: 2605.10401v1 |
| <a id="paper-llmasopt2026"></a>**LLMs as Optimizers Survey**<br>Roko Peran; Luka Hobor; Mihael Kovac; Mario Brcic | Primary focus: Surveys<br>Summary version: 2606.15577v1 |
| <a id="paper-sysevo2025"></a>**LLMs for Evolutionary Optimization Survey**<br>Yisong Zhang; Ran Cheng; Guoxing Yi; Kay Chen Tan | Primary focus: Surveys<br>Summary version: 2509.08269v7<br>The IEEE CIM journal record lists four authors and pages 1–21; method scope follows the listed arXiv version. |
| <a id="paper-meevo2026"></a>**MeEvo**<br>Zishang Qiu; Xinan Chen; Rong Qu; Ruibin Bai | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2606.14202v5 |
| <a id="paper-chen2025mela"></a>**MeLA**<br>Zishang Qiu; Xinan Chen; Long Chen; Wenjie Yi; Ruibin Bai | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2507.20541v4<br>MeLA: A Metacognitive LLM-Driven Architecture for Automatic Heuristic Design [![Version][b159]][r337]: Preprint version; formal citation follows DOI registration metadata; Authors: Zishang Qiu; Xinan Chen; Long Chen; Ruibin Bai<br>The ESWA record is scheduled for the December 2026 issue and adds Wenjie Yi. Preprint authors are listed separately; methods follow the preprint. |
| <a id="paper-milpevo2026"></a>**MILP-Evo**<br>Nie, Jinbiao; Feng, Kewei; Zhang, Xiaoyuan; Yin, Shan; Wang, Zizhuo; Dong, Bin | Primary focus: Solver components and configuration<br>Summary version: 2607.18252v1<br>Specifically implements SCIP cut-selection and branching rules; solver auto-design does not mean rebuilding the entire MILP solver. Distinct from microsoft/MILP-Evolve instance generation; its HF data are not linked here. |
| <a id="paper-mind2026"></a>**MIND**<br>Liu, Weiting; Wu, Han; Kuang, Yufei; Han, Xiongwei; Zhong, Tao; Feng, Jianfeng; Lu, Wenlian | Primary focus: Optimization modeling and code generation<br>Summary version: 2602.11164v1 |
| <a id="paper-zhao2026miniopt"></a>**MiniOpt**<br>Ke Zhao; Zixiang Di; Hong Qian; Xiang Shu; Yaolin Wen; Qitao Shi; Bingdong Li; Xingyu Lu; Xiangfeng Wang; Jun Zhou; Ke Tang; Yang Yu | Primary focus: Optimization modeling and code generation<br>Summary version: 2606.25832v2<br>Provides training and inference code with sample data. |
| <a id="paper-li2026miplibnl"></a>**MIPLIB-NL**<br>Li, Zhong; Lu, Hongliang; Wei, Tao; Chen, Yuxuan; Liu, Wenyu; Lan, Yuan; Zhang, Fan; Wen, Zaiwen | Primary focus: Benchmarks and evaluation<br>GitHub dataset: The official README describes instance.json, model.md, solve.py, and data files under dataset/<problem>/. |
| <a id="paper-mirror2026"></a>**MIRROR**<br>Shi, Yifan; Wang, Jiayi; Wu, Minyi; Fan, Ye; Shi, Jialong; Sun, Jianyong | Primary focus: Model verification, diagnosis, and repair<br>Summary version: arXiv:2602.03318v4<br>Authors follow arXiv v4 dated 2026-08-24; older search indexes differ in author count and order. |
| <a id="paper-zhu2026mmoptbench"></a>**MM-OptBench**<br>Li, Zhong; Huang, Qi; Zhu, Yuxuan; Amiri, Mohammad Mohammadi; van Stein, Niki; Bäck, Thomas; van Leeuwen, Matthijs; Wen, Zaiwen; Yang, Lincen | Primary focus: Benchmarks and evaluation<br>Summary version: 2605.12154v1<br>NeurIPS 2026 acceptance is confirmed by the official poster schedule. |
| <a id="paper-moh2025"></a>**MoH**<br>Yiding Shi; Jianan Zhou; Wen Song; Jieyi Bi; Yaoxin Wu; Zhiguang Cao; Jie Zhang | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2505.20881<br>Generalizable Heuristic Generation Through LLMs with Meta-Optimization [![Version][b159]][r416]: Preprint version; formal citation follows proceedings metadata; Authors: Yiding Shi; Jianan Zhou; Wen Song; Jieyi Bi; Yaoxin Wu; Zhiguang Cao; Jie Zhang<br>Multi-task training refers to search and evaluation of meta-optimization programs; Google Drive provides the task-data archive.<br>CO Task Data: Author-provided data.zip archive; not a complete training framework. |
| <a id="paper-ha2025paretogrid"></a>**MPaGE**<br>Ha Minh Hieu; Hung Phan; Tung Duy Doan; Tung Dao; Cong Dao Tran; Huynh Thi Thanh Binh | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2507.20923v3<br>Pareto-Grid-Guided Large Language Models for Fast and High-Quality Heuristics Design in Multi-Objective Combinatorial Optimization [![Version][b159]][r339]: Preprint version; formal citation follows DOI registration metadata; Authors: Minh Hieu Ha; Hung Phan; Tung Duy Doan; Tung Dao; Dao Tran; Huynh Thi Thanh Binh |
| <a id="paper-warehouseformsel2026"></a>**Multi-Warehouse Formulation Selection**<br>Xu, Jintao; Ma, Yingzheng; Dong, Jiong; Qi, Yongzhi; Zhang, Jianshen | Primary focus: Solver components and configuration<br>Summary version: 2607.25956v1<br>Experiments use JD multi-warehouse inventory-allocation instances. |
| <a id="paper-nemo2026"></a>**NEMO**<br>Yang Song; Anoushka Vyas; Zirui Wei; Sina Khoshfetrat Pakazad; Henrik Ohlsson; Graham Neubig | Primary focus: Optimization modeling and code generation<br>Summary version: 2601.21372v3<br>HF provides seven groups of per-problem outputs and traces plus two result tables. Execution checks support diagnostics; fidelity to problem intent is assessed separately. |
| <a id="paper-jiang2026nlco"></a>**NLCO**<br>Xia Jiang; Jing Chen; Cong Zhang; Jie Gao; Chengpeng Hu; Chenhao Zhang; Yaoxin Wu; Yingqian Zhang | Primary focus: Benchmarks and evaluation<br>Summary version: 2602.02188v2<br>The broken ACL preview URL has been replaced with the formal Findings page. Evaluated models such as Ministral are not new weights from this paper. |
| <a id="paper-opf2026reason"></a>**OPF Constrained Reasoning Study**<br>Bernier, Fabien; Ghamizi, Salah; Dogoulis, Pantelis; Cordy, Maxime | Primary focus: Benchmarks and evaluation<br>Summary version: 2603.23004v1 |
| <a id="paper-li2026optbench"></a>**OPT-BENCH / OPT-Agent**<br>Xiaozhe Li; Jixuan Chen; Xinyu Fang; Shengyuan Ding; Haodong Duan; Qingwen Liu; Kai Chen | Primary focus: Benchmarks and evaluation<br>Summary version: 2506.10764v1<br>OPT-BENCH: Evaluating LLM Agent on Large-Scale Search Spaces Optimization Problems [![Version][b159]][r293]: Original preprint<br>OPT-BENCH: Evaluating the Iterative Self-Optimization of LLM Agents in Large-Scale Search Spaces [![Version][b159]][r294]: Revised preprint linked by the official repository<br>The final publication changed title. The repository explicitly links the original 2025 preprint and revised 2605.08904 preprint as the same OPT-BENCH; no additional ID is created. |
| <a id="paper-chen2026optengine"></a>**OPT-Engine**<br>Chen, Yitian; Cheng, Cheng; Sun, Yinan; Ling, Zi; Ge, Dongdong | Primary focus: Benchmarks and evaluation<br>Summary version: 2601.19924v2<br>Official HF cards and the repository link chenyitian-shanshu/OPTEngine. The similarly named chengcheng2k4/OPT-Engine lacks confirmed attribution and is omitted. Listed SIRL checkpoints belong to another training work, not new models from this paper. |
| <a id="paper-optminer2026"></a>**Opt-Miner**<br>Haoyang Liu; Yuyang Cai; Jie Wang; Xiongwei Han; Minyang Hu; Shuqi Liu; Mingxuan Yuan; Jianye Hao; Feng Wu | Primary focus: Optimization modeling and code generation<br>Code, HF results, and demos are limited third-party reproductions, primarily evaluating base Qwen3-8B. |
| <a id="paper-optarcus2026"></a>**OptArgus**<br>Li, Zhong; Guo, Zihan; Lu, Xiaohan; Wang, Juntao; Song, Jie; Shen, Chao; Wu, Jiageng; Sun, Mingyang | Primary focus: Model verification, diagnosis, and repair<br>Summary version: 2605.11738v1<br>The title uses OptArgus and the stable ID is optarcus2026; the evaluation suite has three parts. |
| <a id="paper-xiu2026optgraph"></a>**OptGraph**<br>Xianchao Xiu; Jianhao Li; Huangyue Chen; Wanquan Liu | Primary focus: Optimization modeling and code generation<br>Summary version: 2607.27918v1<br>Releases the main workflow, seed knowledge graph, and update tools. |
| <a id="paper-optiagentbench2026"></a>**Opti-Agent-Bench**<br>Fu, Yongchang; Huang, Xinjie; Dai, Chengjun; Feng, Chengzhe; Zhang, Junshao; Zhu, Hong | Primary focus: Benchmarks and evaluation<br>Summary version: 2607.10768v1 |
| <a id="paper-optiagent2026"></a>**OptiAgent**<br>Monteiro, Adriana Laurindo; Fagundes, Nayse; Langeloh, Gabriel Mattos; Kanno, Gustavo de Oliveira; Aguirre, Priscila Louise; da Rocha, Thiago Costa Rizuti; Beltran, Victor Leme | Primary focus: Optimization modeling and code generation<br>Summary version: 2607.05346v1<br>Evaluated on four existing benchmark groups. |
| <a id="paper-chen2025optichat"></a>**OptiChat**<br>Chen, Hao; Constante-Flores, Gonzalo Esteban; Mantri, Krishna Sri Ipsit; Kompalli, Sai Madhukiran; Ahluwalia, Akshdeep Singh; Li, Can | Primary focus: Model verification, diagnosis, and repair<br>Summary version: 2501.08406v2<br>Extends earlier infeasibility-diagnosis research but has its own title and arXiv ID, so remains a separate paper. Crossref confirms journal publication in 2026; the historical 2025 ID remains. |
| <a id="paper-dslmilp2026"></a>**OptiDSL**<br>Zhang, Shaofeng; Su, Hongyuan; Peng, Qingwen; Zong, Zefang; Liu, Shengcai; Tang, Ke; Li, Yong | Primary focus: Optimization modeling and code generation<br>Summary version: 2608.07040v1<br>Introduces both a method and a benchmark; cross-paradigm execution is distinct from a proof of solver equivalence. |
| <a id="paper-optiloop2026"></a>**OptiLoop**<br>Xu, Yujia; Wang, Zhiheng; Dinh, Thi | Primary focus: Model verification, diagnosis, and repair<br>Summary version: 2605.27630v1<br>Behavioral checks cover limited scenarios and coordination rounds. Local success or matching objectives do not establish formal correctness for arbitrary collaborative optimization problems. |
| <a id="paper-optirepair2026"></a>**OptiRepair**<br>Ao, Ruicheng; Simchi-Levi, David; Wang, Xinshang | Primary focus: Model verification, diagnosis, and repair<br>Summary version: 2602.19439v2<br>OptiRepair-SC and P1/P2 models retain their respective artifact types; this paper and ORLoopBench have separate IDs. |
| <a id="paper-optiverse2026"></a>**OptiVerse / DVA-Agent**<br>Xinyu Zhang; Boxuan Zhang; Yuchen Wan; Lingling Zhang; YiXing Yao; Bifan Wei; Yaqiang Wu; Jun Liu | Primary focus: Benchmarks and evaluation<br>Summary version: 2604.21510v1<br>OptiVerse: A Comprehensive Benchmark towards Optimization Problem Solving [![Version][b159]][r240]: Preprint version; formal citation follows proceedings metadata; Authors: Xinyu Zhang; Boxuan Zhang; Yuchen Wan; Lingling Zhang; YiXing Yao; Bifan Wei; Yaqiang Wu; Jun Liu<br>DVA-Agent relies on extraction and cross-comparison, not formal proofs for arbitrary models. Executables are under evaluation/; inference, auditing, and scoring scripts are confirmed. |
| <a id="paper-yang2026optskills"></a>**OptSkills**<br>Yang, Haochen; Zhao, Ke; Ma, Mengyuan; Lu, Xingyu; Wang, Xiangfeng; Qian, Hong | Primary focus: Optimization modeling and code generation<br>Summary version: arXiv:2605.29829v2<br>The formal version appears in Findings of EMNLP 2026. Method and skill-library descriptions follow the listed preprint version.<br>Resources: Author-team repository with matching paper and authors in its README, associated with author account fujiwaranoM0kou. |
| <a id="paper-wang2026orprm"></a>**OR-PRM**<br>Wang, Yilin; Zhou, Heng; Mao, Dongxing; Li, Linjie; Tan, Jingru; Han, Haochen; Yang, Zhengyuan; Wang, Alex Jinpeng; Li, Min | Primary focus: Optimization modeling and code generation<br>OR-PRM is trained from Qwen2.5-7B-Coder with SFT and DPO; Qwen3-8B validates data. OR-ProcessQA provides process data. |
| <a id="paper-ding2026orr1"></a>**OR-R1**<br>Zezhen Ding; Zhen Tan; Jiheng Zhang; Tianlong Chen | Primary focus: Optimization modeling and code generation<br>Summary version: 2511.09092v1<br>OR-R1: Automating Modeling and Solving of Operations Research Optimization Problem via Test-Time Reinforcement Learning [![Version][b159]][r041]: Preprint version; formal citation follows DOI registration metadata; Authors: Zezhen Ding; Zhen Tan; Jiheng Zhang; Tianlong Chen<br>The formal version is in the AAAI proceedings. The repository provides SFT, GRPO, LoRA merging, and evaluation code. |
| <a id="paper-zhou2026orspace"></a>**OR-Space**<br>Zhou, Chenyu; Lu, Xinyun; Zhao, Jiangyue; Lin, Jianghao; Ge, Dongdong; Ye, Yinyu | Primary focus: Benchmarks and evaluation<br>Summary version: 2605.28158v1 |
| <a id="paper-oragentbench2026"></a>**ORAgentBench**<br>Li, Jiajun; Cai, Mingshu; Li, Yixuan; Ding, Yu; Hou, Ran; Nie, Guanyu; Han, Xiongwei; Wang, Wanyuan | Primary focus: Benchmarks and evaluation<br>Summary version: 2606.19787v1 |
| <a id="paper-ao2026orloopbench"></a>**ORLoopBench**<br>Ao, Ruicheng; Simchi-Levi, David; Wang, Xinshang | Primary focus: Model verification, diagnosis, and repair<br>Summary version: 2601.21008v3<br>The repository provides ORDebug / ORBias data and validation scripts; release schemas and the paper's generation layout remain version-specific. |
| <a id="paper-yang2025orthought"></a>**ORThought / LogiOR**<br>Beinuo Yang; Qishen Zhou; Junyi Li; Chenxing Su; Panagiotis Angeloudis; Simon Hu | Primary focus: Optimization modeling and code generation<br>Summary version: arXiv:2508.14410v3<br>ORThought: Benchmarking and Automating Logistics Optimization Modeling [![Version][b159]][r565]: 2025; Preprint, v3 revised 2026-04-18; v3, 2026-04-18; earlier title was Automated Optimization Modeling through Expert-Guided Large Language Model Reasoning.; Authors: Beinuo Yang; Qishen Zhou; Junyi Li; Chenxing Su; Panagiotis Angeloudis; Simon Hu<br>The journal version records 2026, volume 6, article 100059, and six authors. The historical ID follows the 2025 preprint debut; methods follow arXiv v3.<br>arXiv v3: Pinned version underlying the method summary; main title, authors, and year follow formal journal metadata. |
| <a id="paper-yan2026pall"></a>**PALL**<br>An Yan; Huigen Ye; Hua Xu; Jiahao Zhang | Primary focus: Heuristic and algorithm discovery<br>NeurIPS 2026 acceptance is confirmed by the official poster schedule. |
| <a id="paper-pathwise2026"></a>**PathWise**<br>Oguzhan Gungordu; Siheng Xiong; Faramarz Fekri | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2601.20539v3<br>PathWise: Planning through World Model for Automated Heuristic Design via Self-Evolving LLMs [![Version][b159]][r342]: Preprint version; formal citation follows proceedings metadata; Authors: Oguzhan Gungordu; Siheng Xiong; Faramarz Fekri<br>Self-evolving refers to search states, actions, and programs; it does not establish LLM weight updates. |
| <a id="paper-lu2026pearl"></a>**PEARL**<br>Lu, Hongliang; Li, Zhong; Chen, Yuxuan; Lan, Yuan; Zhang, Fan; Wen, Zaiwen | Primary focus: Optimization modeling and code generation<br>The official poster schedule confirms NeurIPS 2026 acceptance; the conference is scheduled for December 2026. |
| <a id="paper-jiang2026poweratlas"></a>**PowerAtlas / ECBench**<br>Jiang, Kaiwen; Xu, Siya; Zhu, Ziyue; Xue, Kaiwen; Yang, Chao; Luu, Anh Tuan; Luo, Haoran | Primary focus: Direct solution generation and optimization decisions<br>Summary version: 2607.26710v2<br>PowerAtlas: Towards Electricity-Computing Co-Scheduling for Power Systems [![Version][b159]][r270]: Historical title; current record follows the revised paper title<br>The current title is Feasibility-Aware Language Models for Electricity-Computing Co-Scheduling. The paper reports residual supply gaps; the repository provides generators, samples, and training/evaluation code. |
| <a id="paper-shen2026proopf"></a>**ProOPF**<br>Shen, Chao; Guo, Zihan; Wan, Xu; Yang, Zhenghao; Zhang, Yifan; Huang, Wenqi; Song, Jie; Zhang, Zongyan; Sun, Mingyang | Primary focus: Benchmarks and evaluation<br>Summary version: 2602.03070v5<br>ProOPF_D provides few-shot training examples. Wenqi Huang follows ICML metadata; arXiv citation metadata spells the name Wengi. |
| <a id="paper-pyvrpplus2026"></a>**PyVRP+ / MEP**<br>Manuj Malik; Jianan Zhou; Shashank Reddy Chirra; Zhiguang Cao | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2604.07872v1<br>PyVRP$^+$: LLM-Driven Metacognitive Heuristic Evolution for Hybrid Genetic Search in Vehicle Routing Problems [![Version][b159]][r400]: Preprint version; Authors: Manuj Malik; Jianan Zhou; Shashank Reddy Chirra; Zhiguang Cao<br>The AAMAS 2026 proceedings list four authors and starting page 2800. |
| <a id="paper-roy2026rag"></a>**RAG for Optimization & CP Modeling**<br>Prateek Roy; Akash Singirikonda | Primary focus: Optimization modeling and code generation<br>Summary version: 2608.00015v1<br>Each evaluation uses 25 held-out queries and one base model; results apply to that experimental setting. |
| <a id="paper-lian2026reloop"></a><a id="paper-liang2026reloop"></a>**ReLoop / RetailOpt-190**<br>Lian, Junbo Jacob; Sun, Yujun; Chen, Huiling; Zhang, Chaoyu; Qin, Hanzhang; Teo, Chung-Piaw | Primary focus: Model verification, diagnosis, and repair<br>Summary version: 2602.15983v6<br>Follows arXiv v6 (2026-10-12). NeurIPS's official schedule lists six authors and a 2026-12-08 poster, confirming acceptance with publication pending. RetailOpt-190 HF and GitHub resources are confirmed. Behavioral perturbation tests provide diagnostics, not complete semantic correctness proofs. |
| <a id="paper-zhang2026retailbench"></a>**RetailBench**<br>Zhang, Linghua; Wang, Jun; Wu, Jingtong; Zhang, Zhisong | Primary focus: Benchmarks and evaluation<br>Summary version: 2603.16453v3<br>RetailBench: Benchmarking Long Horizon Reasoning and Coherent Decision Making of LLM Agents in Realistic Retail Environments [![Version][b159]][r503]: Historical title; current record follows the revised paper title<br>The record uses the revised title; the paper evaluation horizon is distinguished from the environment's maximum simulation capability. |
| <a id="paper-rlvrpagents2026"></a>**RLEA**<br>Chen, Yi; Yu, Zikang; Wang, Jiahai; Chen, Jinbiao; Zhou, Jianpeng; Zhang, Zizhen | Primary focus: Optimization modeling and code generation<br>Summary version: 2609.00859v1<br>The paper's Zenodo URL currently contains Appendix_RELA.pdf, listed as an appendix rather than training code, data, or weights. The latest Zenodo record 20484739 likewise lists only two appendix PDFs. |
| <a id="paper-ma2025sacopt"></a>**SAC-Opt**<br>Zhang, Yansen; Kang, Qingcan; Chen, Yujie; Wang, Yufei; Han, Xiongwei; Zhong, Tao; Yuan, Mingxuan; Ma, Chen | Primary focus: Model verification, diagnosis, and repair<br>Summary version: 2510.05115v3<br>Semantic-anchor checks differ from SOVER's SMT-encoding guarantees. Formal ICML 2026 proceedings publication is confirmed. |
| <a id="paper-strategyaware2026"></a>**SAGE (Strategy-Aware Modeling)**<br>Ruiqing Zhao; Fengzhi Li; Yuan Zuo; Rui Liu; Yansong Liu; Yunfei Ma; Fanyu Meng; Junlan Feng | Primary focus: Optimization modeling and code generation<br>Summary version: 2605.02545v1<br>Strategy-Aware Optimization Modeling with Reasoning LLMs [![Version][b159]][r048]: Preprint version; formal citation follows proceedings metadata; Authors: Ruiqing Zhao; Fengzhi Li; Yuan Zuo; Rui Liu; Yansong Liu; Yunfei Ma; Fanyu Meng; Junlan Feng<br>Distinct from SAGE / formerly EvoCut on cutting inequalities; authors and resources are listed separately. |
| <a id="paper-sdrl2026"></a>**SDRL**<br>Shihao Zhang; Weiting Liu; Siyu Shao; Yitian Chen; Jianfeng Feng; Dongdong Ge; Yinyu Ye | Primary focus: Optimization modeling and code generation<br>Summary version: 2609.34427v1<br>GitHub provides benchmark inference code; HF provides SDRL-Qwen3-4B safetensors weights. |
| <a id="paper-lange2026shinka"></a>**ShinkaEvolve**<br>Robert Lange; Yuki Imajuku; Edoardo Cetin | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2509.19349v1<br>ShinkaEvolve: Towards Open-Ended And Sample-Efficient Program Evolution [![Version][b159]][r345]: Preprint version; formal citation follows proceedings metadata; Authors: Robert Tjarko Lange; Yuki Imajuku; Edoardo Cetin<br>Bandit selection chooses which LLM to call; it does not train its weights. The current repository includes later extensions, whose experimental claims should remain separate. |
| <a id="paper-smartgrid2026"></a>**Smart Grids Agentic AI Tutorial**<br>Rojas, Daniela; Albassam, Abdulwahab; Leung, Aidan G.; Ngo, Jett; Luo, Ryan; Quawas, Peter R.; Kim, Junpyung; Liang, Kangkai; Nanavati, Mansi; Mai, Jonathan; Tsai, Meng-Chi; Tsai, Yun-Tong; Chen, Yize; Shi, Yuanyuan | Primary focus: Surveys<br>Summary version: 2607.18147v1 |
| <a id="paper-li2025smilo"></a>**SMILO**<br>Li, Qingyang; Zhang, Lele; Mak-Hau, Vicky | Primary focus: Optimization modeling and code generation<br>Summary version: 2511.02364v1<br>The journal version appeared online on 2026-05-03; the historical 2025 ID remains. |
| <a id="paper-solid2026"></a>**SOLID**<br>Zhu, Rui; Cao, Minglong; Zhou, Chenyu; Lin, Jianghao; Ge, Dongdong | Primary focus: Optimization modeling and code generation<br>Summary version: 2609.09957v1<br>Objective clustering produces pseudo-references. The author homepage links code and models; Qwen3 and StepORLM checkpoints retain separate experimental results. |
| <a id="paper-bhattacharyya2026sover"></a>**SOVER / NLEquiv-150**<br>Bhattacharyya, Swapnil; Baranwal, Mayank | Primary focus: Model verification, diagnosis, and repair<br>Summary version: 2609.00728v1<br>Guarantees depend on parsing, candidate mappings, and encoding assumptions. Z3 linear/mixed-integer checks differ from dReal's tolerance-dependent nonlinear checks. Numerical diagnostics are not SMT proofs, and inter-formulation verification does not completely prove fidelity to natural-language intent.<br>EquivaFormulation (used for evaluation): External evaluation data used by the paper, not a new SOVER release.<br>NLP4LP (used for evaluation): External evaluation data used by the paper, not a new SOVER release. |
| <a id="paper-lai2026specahd"></a>**SpecAHD**<br>Kezhao Lai; Yutao Lai; Hai-Lin Liu | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2607.23676v1<br>The greedy approximation guarantee applies to library selection with a fixed upper-level program, repair tasks, and candidate pool, rather than a global routing approximation ratio. |
| <a id="paper-spo2026"></a>**SPO**<br>Xinyi Ke; Kai Li; Junliang Xing; Yifan Zhang; Jian Cheng | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2609.31179v1<br>The method includes LLM parameter updates. |
| <a id="paper-zhou2026steporlm"></a>**StepORLM**<br>Zhou, Chenyu; Xu, Tianyi; Lin, Jianghao; Ge, Dongdong | Primary focus: Optimization modeling and code generation |
| <a id="paper-text2model2026"></a>**Text2Model**<br>Kadioglu, Serdar; Uppuluri, Karthik; Singirikonda, Akash | Primary focus: Models, data, and tools<br>Summary version: 2604.12955v3<br>arXiv lists AAAI 2025 Bridge Program and CPAIOR 2026 Master Class activities; the platform reuses Text2Zinc data. |
| <a id="paper-chen2026tide"></a>**TIDE**<br>Chentong Chen; Mengyuan Zhong; Ye Fan; Jialong Shi; Jianyong Sun | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2601.21239v2<br>Tuning refers to heuristic numerical parameters. |
| <a id="paper-verisimpl2026"></a>**VeriSimpl**<br>Rahman, Sumaya Abdul; Cuellar, Seckhen Ariel Andrade; Raissov, Ghani; Raza, Mohammad | Primary focus: Model verification, diagnosis, and repair<br>Summary version: 2607.20474v2<br>Formal citation is PMLR 306:103091–103123; the project homepage is suabar/VeriSimple. Methods follow arXiv v2; simplified diagnostics are distinct from formal correctness proofs.<br>Project: Project homepage. |
| <a id="paper-vrpagent2025"></a>**VRPAgent**<br>André Hottung; Federico Berto; Chuanbo Hua; Nayeli Gast Zepeda; Daniel Wetzel; Michael Römer; Haoran Ye; Davide Zago; Michael Poli; Stefano Massaroli; Jinkyoo Park; Kevin Tierney | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2510.07073v2<br>Published in TMLR in October 2026; the author repository provides generated heuristics and sample populations.<br>Generated Operators: Early official release of generated heuristics and sample populations; excludes the full discovery pipeline. |
| <a id="paper-zhao2025aimbench"></a>**AIM-Bench**<br>Zhao, Xuhua; Xie, Yuxuan; Chen, Caihua; Sun, Yuxiang | Primary focus: Benchmarks and evaluation<br>Summary version: 2508.11416v1 |
| <a id="paper-alas2025"></a>**ALAS**<br>Edward Y. Chang; Longling Geng | Primary focus: Direct solution generation and optimization decisions<br>Summary version: 2505.12501v1<br>ACID-like behavior is a framework design goal whose guarantees depend on the specific framework assumptions. |
| <a id="paper-novikov2025alphaevolve"></a>**AlphaEvolve**<br>Novikov, Alexander; Vũ, Ngân; Eisenberger, Marvin; Dupont, Emilien; Huang, Po-Sen; Wagner, Adam Zsolt; Shirobokov, Sergey; Kozlovskii, Borislav; Ruiz, Francisco J. R.; Mehrabian, Abbas; Kumar, M. Pawan; See, Abigail; Chaudhuri, Swarat; Holland, George; Davies, Alex; Nowozin, Sebastian; Kohli, Pushmeet; Balog, Matej | Primary focus: Related research<br>DeepMind provides research results and a problem collection. |
| <a id="paper-kong2025alphaopt"></a>**AlphaOPT**<br>Kong, Minwei; Qu, Ao; Guo, Xiaotong; Ouyang, Wenbin; Jiang, Chonghe; Zheng, Han; Ma, Yining; Zhuang, Dingyi; Tang, Yuhan; Li, Junyi; Wang, Shenhao; Koutsopoulos, Haris; Wang, Hai; Wu, Cathy; Zhao, Jinhua | Primary focus: Optimization modeling and code generation<br>Summary version: 2510.18428v4<br>A NeurIPS 2025 ScaleOpt Workshop paper; current authors follow the revised arXiv metadata. |
| <a id="paper-li2025ars"></a>**ARS / RoutBench**<br>Li, Kai; Liu, Fei; Wang, Zhenkun; Tong, Xialiang; Han, Xiongwei; Yuan, Mingxuan; Zhang, Qingfu | Primary focus: Heuristic and algorithm discovery<br>arXiv comments mention author discussions; this record follows the inspected author list. GitHub data and paper versions must be pinned separately. |
| <a id="paper-askclarify2026"></a>**Ask, Clarify, Optimize**<br>Duan, Yaqi; Hu, Yichun; Jiang, Jiashuo | Primary focus: Optimization modeling and code generation<br>Summary version: 2601.00121v1 |
| <a id="paper-astorga2025autoformulation"></a>**Autoformulation**<br>Nicolás Astorga; Tennison Liu; Yuanzhang Xiao; Mihaela Van Der Schaar | Primary focus: Optimization modeling and code generation |
| <a id="paper-sim2025beyondhype"></a>**Beyond the Hype: Bin Packing**<br>Sim, Kevin; Renau, Quentin; Hart, Emma | Primary focus: Benchmarks and evaluation<br>Summary version: 2501.11411v1 |
| <a id="paper-vanstein2025blade"></a>**BLADE**<br>van Stein, Niki; Kononova, Anna V.; Yin, Haoran; Bäck, Thomas | Primary focus: Benchmarks and evaluation<br>Summary version: 2504.20183v1<br>Published in the GECCO 2025 Workshop / Companion proceedings. |
| <a id="paper-wang2025bppsearch"></a>**BPP-Search / StructuredOR**<br>Teng Wang; Wing Yin Yu; Zhenqi He; Zehua Liu; Hailei Gong; Han Wu; Xiongwei Han; Wei Shi; Ruifeng She; Fangzhou Zhu; Tao Zhong | Primary focus: Optimization modeling and code generation<br>The ACL abstract links official GitHub/HF resources. The HF page exists but its preview reports FeaturesError; data loading and code execution have not been verified. |
| <a id="paper-kaleta2025cdss"></a>**C-DSS**<br>Mariusz Kaleta | Primary focus: Optimization modeling and code generation<br>Empirical evaluation focuses on modeling and coding. |
| <a id="paper-calm2025storm"></a>**CALM / STORM**<br>Tang, Zhengyang; Ye, Zihan; Huang, Chenyu; Huang, Xuhan; Li, Chengpeng; Li, Sihang; Chen, Guanhua; Yan, Ming; Wang, Zizhuo; Zha, Hongyuan; Liu, Dayiheng; Wang, Benyou | Primary focus: Optimization modeling and code generation<br>Summary version: 2510.04204v1<br>Distinct from the CALM work on algorithm co-evolution. |
| <a id="paper-bomer2025emerging"></a>**CEoH**<br>Thomas Bömer; Nico Koltermann; Max Disselnmeyer; Laura Dörr; Anne Meyer | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2503.03350v1<br>The preprint notes review at LION19. |
| <a id="paper-lawless2024cuts"></a>**Cold-Start Separator Configuration**<br>Lawless, Connor; Li, Yingxi; Wikum, Anders; Udell, Madeleine; Vitercik, Ellen | Primary focus: Solver components and configuration<br>Summary version: 2412.12038v2<br>The formal version is CPAIOR 2025, pp. 51–69. The ID retains the 2024 preprint year. The paper supplies the code link. |
| <a id="paper-peering2025"></a>**Component-Level Evaluation**<br>Refai, Dania; Ahmed, Moataz | Primary focus: Benchmarks and evaluation<br>Summary version: 2510.16943v1 |
| <a id="paper-michailidis2025cpbench"></a>**CP-Bench / DCP-Bench-Open**<br>Michailidis, Kostis; Tsouros, Dimos; Guns, Tias | Primary focus: Benchmarks and evaluation<br>Summary version: 2506.06052v2 (original metadata); extension linked separately<br>CP-Bench: Evaluating Large Language Models for Constraint Modelling [![Version][b159]][r472]: ECAI 2025; DOI confirmed<br>DCP-Bench-Open: Evaluating LLMs for Constraint Modelling of Discrete Combinatorial Problems [![Version][b159]][r473]: under review (paper comments)<br>Original CP-Bench is archived; its HF card points to DCP-Bench-Open. The old LLM-CP-Modeling URL returns 404; original and extension repositories replace it, with results kept separate. Published status applies to original CP-Bench; the under-review statement concerns only DCP-Bench-Open v3. |
| <a id="paper-daopt2025"></a>**DAOpt / OptU**<br>Zhu, WenZhuo; Cui, Zheng; Lu, Wenhan; Liu, Sheng; Zhao, Yue | Primary focus: Optimization modeling and code generation<br>Summary version: 2511.11576v1 |
| <a id="paper-dheevo2025"></a>**DHEvo**<br>Zhang, Zhihao; Li, Siyuan; Li, Chenxi; Liu, Feifan; Chen, Mengjing; Li, Kai; Zhong, Tao; An, Bo; Liu, Peng | Primary focus: Solver components and configuration<br>Summary version: 2507.15615v1<br>Data–algorithm co-evolution supports heuristic discovery; it does not establish LLM weight training or the release of a new benchmark. |
| <a id="paper-dinn2025"></a>**DINN**<br>Hwang, Yoontae; Kong, Yaxuan; Zohren, Stefan; Lee, Yongjae | Primary focus: Related research<br>Summary version: 2502.00828v1<br>The author repository provides a PyTorch implementation; experimental data require a WRDS account.<br>Resources: Repository associated with author Yoontae Hwang; its README identifies the original PyTorch implementation and cites the paper. |
| <a id="paper-wasserkrug2024manifesto"></a><a id="paper-wasserkrug2025aaai"></a>**DOCP Research Manifesto**<br>Segev Wasserkrug; Leonard Boussioux; Dick Den Hertog; Farzaneh Mirzazadeh; Ş. İlker Birbil; Jannis Kurtz; Donato Maragno | Primary focus: Surveys<br>Summary version: 2402.16269v1<br>From Large Language Models and Optimization to Decision Optimization CoPilot: A Research Manifesto [![Version][b159]][r014]: Early detailed 2024 version; relationship confirmed by footnote 1 in the formal paper<br>Enhancing Decision Making Through the Integration of Large Language Models and Operations Research Optimization [![Version][b161]][r013]: Formal AAAI 2025 version<br>Footnote 1 on page 2 of the formal AAAI version explicitly identifies the 2024 Manifesto as an earlier version. They share one ID, retaining titles, versions, and original records. |
| <a id="paper-dpdlm2025"></a>**DPLM / DP-Bench**<br>Zhou, Chenyu; Yang, Jingyuan; Xin, Linwei; Chen, Yitian; He, Ziyan; Ge, Dongdong | Primary focus: Optimization modeling and code generation<br>Summary version: 2507.11737v2 |
| <a id="paper-jiang2025droc"></a>**DRoC**<br>Xia Jiang; Yaoxin Wu; Chenhao Zhang; Yingqian Zhang | Primary focus: Optimization modeling and code generation |
| <a id="paper-viktorin2025ease"></a>**EASE**<br>Adam Viktorin; Tomas Kadavy; Jozef Kovac; Michal Pluhacek; Roman Senkerik | Primary focus: Models, data, and tools<br>Summary version: 2509.18108v1<br>Also supports generation tasks beyond algorithms, so it is listed as an adjacent platform, not a new OR benchmark or trained model. |
| <a id="paper-luo2025efs"></a>**EFS**<br>Chen, Jiandong; Luo, Haochen; Zhang, Yuan; Liu, Chen; Zhang, Qingfu | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2507.17211v2<br>Title and method follow the current revision. |
| <a id="paper-zhou2024elecbench"></a>**ElecBench**<br>Xiyuan Zhou; Huan Zhao; Yuheng Cheng; Gaoqi Liang; Guolong Liu; Wenxuan Liu; Yan Xu; Junhua Zhao | Primary focus: Related research<br>Summary version: 2407.05365v2<br>ElecBench: a Power Dispatch Evaluation Benchmark for Large Language Models [![Version][b159]][r549]: Preprint version; Authors: Zhou, Xiyuan; Zhao, Huan; Cheng, Yuheng; Cao, Yuji; Liang, Gaoqi; Liu, Guolong; Liu, Wenxuan; Xu, Yan; Zhao, Junhua<br>The repository provides a public test subset; PESGM 2025 and preprint titles/authors are listed separately. |
| <a id="paper-zhang2025decisioninfo"></a>**EOR / Decision Information**<br>Zhang, Yansen; Kang, Qingcan; Yu, Wing Yin; Gong, Hailei; Fu, Xiaojin; Han, Xiongwei; Zhong, Tao; Ma, Chen | Primary focus: Model verification, diagnosis, and repair<br>Summary version: 2502.09994v1 |
| <a id="paper-zhai2025equivamap"></a>**EquivaMap**<br>Haotian Zhai; Connor Lawless; Ellen Vitercik; Liu Leqi | Primary focus: Model verification, diagnosis, and repair |
| <a id="paper-ucfunsearch2025"></a>**FunSearch for Unit Commitment**<br>Lv, Junjin; Cui, Chenggang; Zhang, Shaodi; Chen, Hui; Gong, Chunyang; Liu, Jiaming | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2506.12495v1 |
| <a id="paper-globalconstraint2025"></a>**Gala**<br>Cai, Junyang; Kadioglu, Serdar; Dilkina, Bistra | Primary focus: Optimization modeling and code generation<br>Summary version: 2509.08970v2<br>The gala strategy in the shared Text2Model platform implements this paper. |
| <a id="paper-yang2025heuragenix"></a>**HeurAgenix**<br>Xianliang Yang; Ling Zhang; Haolong Qian; Lei Song; Jiang Bian | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2506.15196v2<br>Official download scripts link the HF collection of existing CO instances. |
| <a id="paper-dat2024hsevo"></a>**HSEvo**<br>Pham Vu Tuan Dat; Long Doan; Huynh Thi Thanh Binh | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2412.14995v1<br>HSEvo: Elevating Automatic Heuristic Design with Diversity-Driven Harmony Search and Genetic Algorithm Using LLMs [![Version][b159]][r361]: Preprint version; formal citation follows DOI registration metadata; Authors: Pham Vu Tuan Dat; Long Doan; Huynh Thi Thanh Binh |
| <a id="paper-zhang2025instspechh"></a>**InstSpecHH**<br>Shaofeng Zhang; Shengcai Liu; Ning Lu; Jiahao Wu; Ji Liu; Yew-Soon Ong; Ke Tang | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2506.00490v3<br>An optional neural classifier selects algorithms; its training is distinct from LLM SFT. |
| <a id="paper-xie2025llmns"></a>**LHNS**<br>Zhuoliang Xie; Fei Liu; Zhenkun Wang; Qingfu Zhang | Primary focus: Heuristic and algorithm discovery<br>Searches heuristic programs. IEEE, author-institution pages, and the LLM4AD module link the method. |
| <a id="paper-vanstein2024llamea"></a>**LLaMEA**<br>van Stein, Niki; Bäck, Thomas | Primary focus: Heuristic and algorithm discovery<br>IEEE TEVC online publication was in 2024; the volume/issue appeared in 2025. This record uses 2025; author documentation provides the full citation. |
| <a id="paper-liu2025fitness"></a>**LLM Algorithm-search Fitness Landscapes**<br>Fei Liu; Qingfu Zhang; Jialong Shi; Xialiang Tong; Kun Mao; Mingxuan Yuan | Primary focus: Benchmarks and evaluation<br>Summary version: 2504.19636v3 |
| <a id="paper-vanstein2025behaviour"></a>**LLM Heuristic Behaviour-space Analysis**<br>Niki van Stein; Haoran Yin; Anna V. Kononova; Thomas Bäck; Gabriela Ochoa | Primary focus: Benchmarks and evaluation<br>Summary version: 2507.03605v1<br>Zenodo provides behaviour_metrics.py behavior-metric code. |
| <a id="paper-cetinkaya2025mipsmtt"></a>**LLM-discovered EDDC / MDDC**<br>İbrahim Oğuz Çetinkaya; İ. Esra Büyüktahtakın; Parshin Shojaee; Chandan K. Reddy | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2510.24013v1 |
| <a id="paper-ye2025llmlns"></a>**LLM-LNS**<br>Huigen Ye; Hua Xu; An Yan; Yaoyang Cheng | Primary focus: Heuristic and algorithm discovery |
| <a id="paper-llmsuc2025"></a>**LLM-SUC**<br>Ren, Xinxing; Lai, Chun Sing; Taylor, Gareth; Guo, Zekun | Primary focus: Optimization modeling and code generation<br>Summary version: 2502.10557v2<br>Method descriptions follow arXiv v2. Cost and load-shedding statistics differ across versions and remain separate. |
| <a id="paper-xiao2025survey"></a>**LLM4OR Survey**<br>Xiao, Ziyang; Xie, Jingrong; Xu, Lilin; Guan, Shisi; Zhu, Jingyan; Han, Xiongwei; Fu, Xiaojin; Yu, WingYin; Wu, Han; Shi, Wei; Kang, Qingcan; Duan, Jiahui; Zhong, Tao; Yuan, Mingxuan; Zeng, Jia; Wang, Yuan; Chen, Gang; Zhang, Dongxiang | Primary focus: Surveys<br>Provides cleaned or error-annotated ComplexOR, IndustryOR, Mamo, NL4LP, NL4Opt, and ReSocratic materials. These revise existing evaluation resources rather than introduce those benchmarks.<br>Cleaned Benchmarks: Error annotations / cleaned existing ComplexOR, IndustryOR, Mamo, NL4LP, NL4Opt, and ReSocratic materials; not their original benchmark releases. |
| <a id="paper-jiang2025e2eco"></a>**LLMCoSolver / E2E CO Solver**<br>Xia Jiang; Yaoxin Wu; Minshuo Li; Zhiguang Cao; Yingqian Zhang | Primary focus: Direct solution generation and optimization decisions<br>Summary version: 2509.16865v1<br>Large Language Models as End-to-end Combinatorial Optimization Solvers [![Version][b159]][r273]: Preprint version; formal citation follows proceedings metadata; Authors: Xia Jiang; Yaoxin Wu; Minshuo Li; Zhiguang Cao; Yingqian Zhang<br>Provides code and SFT / RL data on Google Drive. |
| <a id="paper-jiang2025llmopt"></a>**LLMOPT**<br>jiang, caigao; Shu, Xiang; Qian, Hong; Lu, Xingyu; ZHOU, JUN; Zhou, Aimin; Yu, Yang | Primary focus: Optimization modeling and code generation<br>Code is in antgroup/LLMOPT. Public HF models use Qwen2.5-14B; the paper also trained from Qwen1.5, so experimental checkpoints remain version-specific. |
| <a id="paper-dsmco2024"></a>**LLMs for DSM Sequencing**<br>Shuo Jiang; Min Xie; Jianxi Luo | Primary focus: Direct solution generation and optimization decisions<br>Summary version: 2411.12571v1<br>Large Language Models for Combinatorial Optimization of Design Structure Matrix [![Version][b159]][r278]: Preprint version; formal citation follows DOI registration metadata; Authors: Shuo Jiang; Min Xie; Jianxi Luo<br>Follows the formal ICED25 version. |
| <a id="paper-talebi2025stochastic"></a>**LLMs for Stochastic Modeling**<br>Talebi, Amirreza | Primary focus: Optimization modeling and code generation<br>Summary version: 2508.17200v3<br>Public evaluation cases include adaptations from the literature, not a newly named benchmark. The README mainly cites existing Chain-of-Experts; attribution follows this paper's explicit data/code statement. |
| <a id="paper-wang2025lor"></a>**LLMs in OR: Methods & Challenges**<br>Yang Wang; Kai Li | Primary focus: Surveys<br>Summary version: 2509.18180v3 |
| <a id="paper-llmbl2025"></a>**LLM–Black-Litterman**<br>Lee, Youngbin; Kim, Yejin; Kim, Juhyeong; Kim, Suin; Lee, Yongjae | Primary focus: Related research<br>Summary version: 2504.14345v2<br>The organizer's accepted-paper list includes the title and five authors, confirming a Financial AI Workshop presentation, not CIKM main-conference publication. Code and data are in the repository explicitly linked by the paper. |
| <a id="paper-yuan2025magts"></a>**MA-GTS / G-REAL**<br>Yuan, Zike; Liu, Ming; Wang, Hui; Qin, Bing | Primary focus: Solver components and configuration<br>G-REAL figures differ between arXiv v2 and the conference abstract; version-specific results remain separate. |
| <a id="paper-huang2024mamo"></a>**Mamo**<br>Huang, Xuhan; Shen, Qingning; Hu, Yan; Gao, Anningzhe; Wang, Benyou | Primary focus: Benchmarks and evaluation<br>The historical 2024 ID remains stable; the record year follows formal publication in 2025.<br>Dataset (third-party mirror): The data card explicitly copies Mamo EasyLP / ComplexLP with renamed fields; a third-party adaptation, not an original-author release. |
| <a id="paper-zheng2025mctsahd"></a>**MCTS-AHD**<br>Zhi Zheng; Zhuoliang Xie; Zhenkun Wang; Bryan Hooi | Primary focus: Heuristic and algorithm discovery |
| <a id="paper-yao2025meoh"></a>**MEoH**<br>Shunyu Yao; Fei Liu; Xi Lin; Zhichao Lu; Zhenkun Wang; Qingfu Zhang | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2409.16867v2<br>Multi-objective Evolution of Heuristic Using Large Language Model [![Version][b159]][r375]: Preprint version; formal citation follows DOI registration metadata; Authors: Shunyu Yao; Fei Liu; Xi Lin; Zhichao Lu; Zhenkun Wang; Qingfu Zhang<br>LLM4AD's meoh module explicitly cites this paper. It is an implementation within a shared platform, not a new standalone platform introduced by this paper. |
| <a id="paper-li2025milpevolve"></a>**MILP-Evolve**<br>Li, Sirui; Kulkarni, Janardhan; Menache, Ishai; Wu, Cathy; Li, Beibin | Primary focus: Models, data, and tools<br>Implementation is in microsoft/OptiGuide's milp-evolve directory. microsoft/MILP-Evolve is a separate dataset-card repository, not the complete algorithm implementation. |
| <a id="paper-liu2025mmagent"></a>**MM-Agent / MM-Bench (mathematical modeling)**<br>Fan LIU; Zherui Yang; Cancheng Liu; Tianrui Song; Xiaofeng Gao; Hao Liu | Primary focus: Related research<br>Summary version: 2505.14148v1<br>MM-Agent: LLM as Agents for Real-world Mathematical Modeling Problem [![Version][b159]][r539]: Preprint version; formal citation follows proceedings metadata; Authors: Fan Liu; Zherui Yang; Cancheng Liu; Tianrui Song; Xiaofeng Gao; Hao Liu<br>Covers general mathematical modeling, distinct from the identically named multimodal MM-Bench. Competition awards refer to assisted student teams. Expert Skills is a 2026 version; paper experiments follow the 2025 version.<br>HF Demo: Online demo; service availability does not validate functionality or experimental results. |
| <a id="paper-qian2025modelingagent"></a>**ModelingAgent / ModelingBench**<br>Cheng Qian; Hongyi Du; Hongru Wang; Xiusi Chen; Yuji Zhang; Avirup Sil; ChengXiang Zhai; Kathleen McKeown; Heng Ji | Primary focus: Related research<br>Summary version: 2505.15068v1<br>ModelingAgent: Bridging LLMs and Mathematical Modeling for Real-World Challenges [![Version][b159]][r545]: Preprint version; formal citation follows proceedings metadata; Authors: Cheng Qian; Hongyi Du; Hongru Wang; Xiusi Chen; Yuji Zhang; Avirup Sil; Chengxiang Zhai; Kathleen McKeown; Heng Ji<br>Covers data analysis, prediction, interdisciplinary modeling, and reporting, rather than a pure OR benchmark. Scores include LLM judgments, distinct from solver objective-value or feasibility checks. |
| <a id="paper-moid2025"></a>**MOID**<br>Li, Kai; Zheng, Ruihao; Hao, Xinye; Wang, Zhenkun | Primary focus: Model verification, diagnosis, and repair<br>Summary version: 2508.03406v1<br>The linked repository currently contains only 50 VRP&100 solution.json and a minimal README. It is listed as diagnostic data, not a complete solving and diagnosis implementation. |
| <a id="paper-xie2025murka"></a>**MURKA**<br>Wantong Xie; Yi-Xiang Hu; Jieyang Xu; Feng Wu; Xiangyang Li | Primary focus: Optimization modeling and code generation<br>Follows the 2025 conference version. |
| <a id="paper-tran2025llmneural"></a>**NCO-LLM for VRP**<br>Cong Dao Tran; Quan Nguyen-Tri; Huynh Thi Thanh Binh; Hoang Thanh-Tung | Primary focus: Heuristic and algorithm discovery<br>Presented at the ICLR 2025 Towards Agentic AI for Science Workshop. The repository provides code; fine-tuning targets NCO routing policies. |
| <a id="paper-thind2025optimai"></a>**OptimAI**<br>Thind, Raghav; Sun, Youran; Liang, Ling; Yang, Haizhao | Primary focus: Optimization modeling and code generation<br>Summary version: 2504.16918v3 |
| <a id="paper-zhang2025optimind"></a><a id="paper-chen2025optimind"></a>**OptiMind**<br>Zhang, Xinzhi; Chen, Zeyi; Zope, Humishka; Barbalho, Hugo; Mellou, Konstantina; Molinaro, Marco; Kulkarni, Janardhan; Menache, Ishai; Li, Sirui | Primary focus: Optimization modeling and code generation<br>The official OptiMind-SFT model card links the shared microsoft/OptiGuide repository. |
| <a id="paper-liu2025optitree"></a>**OptiTree**<br>Liu, Haoyang; Wang, Jie; Cai, Yuyang; Han, Xiongwei; Kuang, Yufei; Hao, Jianye | Primary focus: Optimization modeling and code generation |
| <a id="paper-lima2025optitrust"></a>**OptiTrust**<br>Lima, Vinicius; Phan, Dzung T.; Kalagnanam, Jayant; Patel, Dhaval; Zhou, Nianjun | Primary focus: Optimization modeling and code generation<br>Summary version: 2508.03117v1 |
| <a id="paper-lu2025optmath"></a>**OptMATH**<br>Hongliang Lu; Zhonglin Xie; Yaoyu Wu; Can Ren; Yuxuan Chen; Zaiwen Wen | Primary focus: Optimization modeling and code generation<br>Uses optsuite/OptMATH linked from the PMLR proceedings and Aurora-Gem models and data linked from the official README.<br>Model 7B: The official README links the model; its card and HF files are accessible.<br>Model 32B: The official README links the model; its card and HF files are accessible. |
| <a id="paper-zhang2025bwor"></a>**OR-LLM-Agent / BWOR**<br>Zhang, Bowen; Luo, Pengcheng; Yang, Genke; Soong, Boon-Hee; Yuen, Chau | Primary focus: Optimization modeling and code generation<br>Summary version: 2503.10009v3 |
| <a id="paper-ding2026orgeval"></a>**ORGEval / Bench4Opt**<br>Wang, Zhuohan; Zhu, Ziwei; Li, Ziniu; Chen, Congliang; Han, Yizhou; Lin, Yufeng; Lin, Zhihang; Gu, Angyang; Hu, Xinglin; Sun, Ruoyu; Ding, Tian | Primary focus: Model verification, diagnosis, and repair<br>ORGEval: Graph-Theoretic Evaluation of LLMs in Optimization Modeling [![Version][b159]][r257]: 2025<br>Certified Evaluation for LLMs in Optimization Modeling: From Graph Isomorphism to Formulation Isomorphism [![Version (related)][b162]][r258]: 2026; Poster in Workshop: Combining Theory and Benchmarks; Titles and authors differ; both abstracts use ORGEval and Bench4Opt, so they are listed as related versions.<br>The ICML 2026 page identifies a workshop poster, correcting an earlier main-conference attribution. The historical 2026 ID remains; the year follows the confirmed 2025 arXiv debut. |
| <a id="paper-huang2025orlm"></a>**ORLM**<br>Huang, Chenyu; Tang, Zhengyang; Hu, Shixi; Jiang, Ruoqing; Zheng, Xin; Ge, Dongdong; Wang, Benyou; Wang, Zizhuo | Primary focus: Optimization modeling and code generation<br>Journal status and volume/issue follow publisher records. Author order follows arXiv metadata and differs from the repository's example citation. |
| <a id="paper-ormind2025"></a>**ORMind**<br>Wang, Zhiyuan; Chen, Bokui; Huang, Yinya; Cao, Qingxing; He, Ming; Fan, Jianping; Liang, Xiaodan | Primary focus: Optimization modeling and code generation<br>Summary version: 2506.01326v2<br>Published in the ACL 2025 Industry Track; experiments use the paper implementation version in the repository. |
| <a id="paper-mostajabdaveh2025orqa"></a>**ORQA**<br>Mostajabdaveh, Mahdi; Yu, Timothy T.; Dash, Samarendra Chandan Bindu; Ramamonjison, Rindranirina; Byusa, Jabo Serge; Carenini, Giuseppe; Zhou, Zirui; Zhang, Yong | Primary focus: Benchmarks and evaluation<br>The official AAAI 2025 page confirms publication. Author abbreviations differ; this record follows the inspected arXiv citation, while the proceedings list Timothy Tin Long Yu / Rindra Ramamonjison. |
| <a id="paper-ali2025pair"></a>**PAIR**<br>Ali, Shady; Ashraf, Mahmoud; Hegazy, Seif; Salem, Fatty; Mokhtar, Hoda; Gaber, Mohamed Medhat; Alrefaie, Mohamed Taher | Primary focus: Heuristic and algorithm discovery<br>A short link in the author's public introduction leads to SHIXOOM/PAIR. Its README explicitly identifies the paper's experiments and links the paper. |
| <a id="paper-quan2025reeval3d"></a>**Re-evaluating Heuristic Search: 3D Packing**<br>Quan, Guorui; Sun, Mingfei; López-Ibáñez, Manuel | Primary focus: Benchmarks and evaluation<br>Summary version: 2509.02297v1 |
| <a id="paper-thach2025redahd"></a>**RedAHD**<br>Nguyen Thach; Aida Riahifar; Nathan Huynh; Hau Chan | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2505.20242v1<br>Empirical reduction checks do not prove every generated transformation correct. ReEvo / MCTS-AHD cited in the paper are not implementations of this work. |
| <a id="paper-cao2025reflecsched"></a>**ReflecSched**<br>Cao, Shijie; Yuan, Yuan | Primary focus: Direct solution generation and optimization decisions<br>Summary version: 2508.01724v3<br>Methods follow arXiv v3 dated 2026-01-19. |
| <a id="paper-yang2025resocratic"></a>**ReSocratic / OptiBench**<br>Yang, Zhicheng; Wang, Yiwei; Huang, Yinya; Guo, Zhijiang; Shi, Wei; Han, Xiongwei; Feng, Liang; Song, Linqi; Liang, Xiaodan; Tang, Jing | Primary focus: Optimization modeling and code generation<br>The old code URL redirects to the publicly accessible yangzhch6/PRIVATE-RS repository. ICLR author metadata lists Shi, Shi, whereas arXiv lists Shi, Wei; this record follows arXiv consistently. |
| <a id="paper-xu2025roco"></a>**RoCo**<br>Jiawei Xu; Feng-Feng Wei; Wei-Neng Chen | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2512.03762v2<br>Collaboration and population evolution support program discovery. |
| <a id="paper-yazdani2025evocut"></a>**SAGE / formerly EvoCut**<br>Yazdani, Milad; Mostajabdaveh, Mahdi; Aref, Samin; Zhou, Zirui | Primary focus: Solver components and configuration<br>Summary version: 2508.11850v3<br>LLM-Guided Evolution of Symbolic Acceleration Inequality Families for MILP [![Version][b159]][r425]: Revised 2026-10-19; framework named SAGE<br>EvoCut: Strengthening Integer Programs via Evolution-Guided Language Models [![Version][b163]][r426]: Earlier title EvoCut; its code repository is retained.<br>Follows the inspected v3 abstract and claims. Candidate inequalities pass empirical acceptability checks, without mathematical validity proofs. Old EvoCut and newer SAGE code remain linked under one paper ID. |
| <a id="paper-chen2025sirl"></a>**SIRL**<br>Chen, Yitian; Xia, Jingfan; Shao, Siyu; Ge, DongDong; Ye, Yinyu | Primary focus: Optimization modeling and code generation<br>ORLMBenchmark revises existing benchmarks; it is not the first release of every constituent dataset and is distinct from the original IndustryOR release in ORLM. |
| <a id="paper-solverllm2025"></a>**SolverLLM**<br>Li, Dong; Zhao, Xujiang; Yu, Linlin; Liu, Yanchi; Cheng, Wei; Chen, Zhengzhang; Chen, Zhong; Chen, Feng; Zhao, Chen; Chen, Haifeng | Primary focus: Optimization modeling and code generation<br>Summary version: 2510.16916v2 |
| <a id="paper-abgaryan2025starjob"></a>**Starjob**<br>Abgaryan, Henrik; Cazenave, Tristan; Harutyunyan, Ararat | Primary focus: Direct solution generation and optimization decisions<br>Summary version: 2503.01877v2<br>Starjob training data are in mideavalwisard/Starjob; the author repository provides training scripts. arXiv carries an administrator note on substantial text overlap. |
| <a id="paper-wu2025stepopt"></a>**Step-Opt**<br>Yang Wu; Yifan Zhang; Yurong Wu; Yuran Wang; Junkai Zhang; Jian Cheng | Primary focus: Optimization modeling and code generation<br>Summary version: 2506.17637v1<br>Step-Opt: Boosting Optimization Modeling in LLMs through Iterative Data Synthesis and Structured Validation [![Version][b159]][r085]: Preprint title<br>The formal version uses a revised title; the earlier arXiv title is retained in version information. Data and implementation are under Step/. |
| <a id="paper-li2025strcmp"></a>**STRCMP**<br>Xijun Li; Jiexiang Yang; Jinghao Wang; Bo Peng; Jianguo Yao; Haibing Guan | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2506.11057v1<br>STRCMP: Integrating Graph Structural Priors with Language Models for Combinatorial Optimization [![Version][b159]][r382]: Preprint version; formal citation follows proceedings metadata; Authors: Xijun Li; Jiexiang Yang; Jinghao Wang; Bo Peng; Jianguo Yao; Haibing Guan |
| <a id="paper-abedi2025thinkmath"></a>**Teaching LLMs to Think Mathematically**<br>Mohammad J. Abdel-Rahman; Yasmeen Alslman; Dania Refai; Amro Saleh; Malik A. Abu Loha; Mohammad Yahya Hamed | Primary focus: Surveys<br>Summary version: 2508.18091v1<br>Authors include Mohammad J. Abdel-Rahman; the historical ID remains. |
| <a id="paper-singirikonda2025text2zinc"></a>**Text2Zinc**<br>Singirikonda, Akash; Kadioglu, Serdar; Uppuluri, Karthik | Primary focus: Benchmarks and evaluation<br>Summary version: 2503.10642v1<br>Text2Zinc @ AAAI 2025 is an Invited Talk; the paper and author portal link the HF data. |
| <a id="paper-nl2ps2025"></a>**Validation-in-the-Loop Power Modeling**<br>Hu, Yunkai; Zhao, Tianqiao; Yue, Meng | Primary focus: Optimization modeling and code generation<br>Summary version: 2508.08147v1 |
| <a id="paper-bridgingviz2025"></a>**Visual Graph Optimization with MLLMs**<br>Jie Zhao; Kang Hao Cheong; Witold Pedrycz | Primary focus: Direct solution generation and optimization decisions<br>Summary version: 2501.11968 |
| <a id="paper-parashar2025wiqor"></a>**WIQOR**<br>Aditya Parashar; Ari Kobren; Natalia Kosilova | Primary focus: Benchmarks and evaluation<br>Summary version: Oracle institution-hosted anonymous submission, DOC_ID 4780<br>The institution-hosted preprint is an anonymous submission; authors follow the named institutional record.<br>Paper PDF: Institution-hosted anonymous preprint.<br>Institution record: Named institutional research record. |
| <a id="paper-deng2024cafa"></a>**CAFA**<br>Haoxuan Deng; Bohao Zheng; Yirui Jiang; Trung Hieu Tran | Primary focus: Optimization modeling and code generation<br>Presented at the NeurIPS 2024 MATH-AI Workshop. Authors follow the official repository citation; code and results remain version-specific. |
| <a id="paper-xiao2024coe"></a>**Chain-of-Experts**<br>Ziyang Xiao; Dongxiang Zhang; Yangjun Wu; Lilin Xu; Yuan Wang; Xiongwei Han; Xiaojin Fu; Tao Zhong; Jia Zeng; Mingli Song; Gang Chen | Primary focus: Optimization modeling and code generation<br>The formal version is in the ICLR proceedings; the repository provides the original ComplexOR release. |
| <a id="paper-jiao2024cityleo"></a>**City-LEO**<br>Jiao, Zihao; Sha, Mengyi; Zhang, Haoyu; Jiang, Xinyu; Qi, Wei | Primary focus: Optimization modeling and code generation<br>Summary version: 2406.10958v2<br>City-LEO code and data are in BTBUzhy/JOC on HF, including data and Python files. |
| <a id="paper-liu2024eoh"></a>**EoH**<br>Fei Liu; Tong Xialiang; Mingxuan Yuan; Xi Lin; Fu Luo; Zhenkun Wang; Zhichao Lu; Qingfu Zhang | Primary focus: Heuristic and algorithm discovery |
| <a id="paper-xing2024lpwp"></a>**Human-aligned LPWP Evaluation**<br>Linzi Xing; Xinglu Wang; Yuxi Feng; Zhenan Fan; Jing Xiong; Zhijiang Guo; Xiaojin Fu; Rindra Ramamonjison; Mahdi Mostajabdaveh; Xiongwei Han; Zirui Zhou; Yong Zhang | Primary focus: Benchmarks and evaluation<br>Studies metrics and human evaluation on existing NL4Opt data, distinguishing structural scores, representation-level equivalence, and mathematical equivalence proofs. |
| <a id="paper-quan2024invagent"></a>**InvAgent**<br>Quan, Yinzhu; Liu, Zefang | Primary focus: Direct solution generation and optimization decisions<br>Summary version: 2407.11384v2 |
| <a id="paper-tang2024itinerary"></a>**ITINERA**<br>Yihong Tang; Zhaokai Wang; Ao Qu; Yihao Yan; Zhaofeng Wu; Dingyi Zhuang; Jushi Kai; Kebing Hou; Xiaotong Guo; Jinhua Zhao; Zhan Zhao; Wei Ma | Primary focus: Direct solution generation and optimization decisions<br>Summary version: 2402.07204v5<br>ITINERA: Integrating Spatial Optimization with Large Language Models for Open-domain Urban Itinerary Planning [![Version][b159]][r290]: Preprint version; Authors: Tang, Yihong; Wang, Zhaokai; Qu, Ao; Yan, Yihao; Wu, Zhaofeng; Zhuang, Dingyi; Kai, Jushi; Hou, Kebing; Guo, Xiaotong; Zheng, Han; Luo, Tiange; Zhao, Jinhua; Zhao, Zhan; Ma, Wei<br>Published in the EMNLP 2024 Industry Track. Its KDD UrbComp workshop presentation is not KDD main-conference publication. Authors follow ACL's formal record, which differs from the preprint. |
| <a id="paper-liu2024llm4ad"></a>**LLM4AD**<br>Liu, Fei; Zhang, Rui; Xie, Zhuoliang; Sun, Rui; Li, Kai; Hu, Qinglong; Guo, Ping; Lin, Xi; Tong, Xialiang; Yuan, Mingxuan; Wang, Zhenkun; Lu, Zhichao; Zhang, Qingfu | Primary focus: Models, data, and tools |
| <a id="paper-yu2024deep"></a>**LLM–EA Automated Optimization Insights**<br>He Yu; Jing Liu | Primary focus: Surveys<br>Summary version: 2410.20848v1 |
| <a id="paper-ahmed2024lm4opt"></a>**LM4OPT**<br>Tasnim Ahmed; Salimur Choudhury | Primary focus: Optimization modeling and code generation<br>Summary version: 2403.01342v1<br>LM4OPT: Unveiling the Potential of Large Language Models in Formulating Mathematical Optimization Problems [![Version][b159]][r090]: Preprint version; formal citation follows DOI registration metadata; Authors: Tasnim Ahmed; Salimur Choudhury<br>The formal INFOR version expands the small-model comparison. |
| <a id="paper-mostajabdaveh2024multiagent"></a>**Multi-Stage Modeling & Verification**<br>Mahdi Mostajabdaveh; Timothy T. Yu; Rindranirina Ramamonjison; Giuseppe Carenini; Zirui Zhou; Yong Zhang | Primary focus: Optimization modeling and code generation<br>Publisher and author pages link the method and publication metadata. |
| <a id="paper-dakle2023ner4opt"></a>**Ner4Opt**<br>Serdar Kadıoğlu; Parag Pravin Dakle; Karthik Uppuluri; Regina Politi; Preethi Raghavan; SaiKrishna Rallabandi; Ravisutha Srinivasamurthy | Primary focus: Optimization modeling and code generation<br>The formal Constraints 2024 version lists Serdar Kadıoğlu as first author; the historical dakle2023ner4opt ID remains. The author repository also lists an earlier CPAIOR 2023 version. |
| <a id="paper-yang2024opro"></a><a id="paper-yang2025opro"></a>**OPRO**<br>Yang, Chengrun; Wang, Xuezhi; Lu, Yifeng; Liu, Hanxiao; Le, Quoc V.; Zhou, Denny; Chen, Xinyun | Primary focus: Direct solution generation and optimization decisions |
| <a id="paper-chen2023diagnosing"></a>**OptiChat / Infeasibility Diagnosis**<br>Chen, Hao; Constante-Flores, Gonzalo E.; Li, Can | Primary focus: Model verification, diagnosis, and repair<br>Summary version: 2308.12923v1<br>The preprint debuted in 2023 and the journal version appeared in 2024; the historical ID remains. OptiChat work in the shared repository is distinguished by version. |
| <a id="paper-teshnizi2024optimus"></a>**OptiMUS**<br>Ali Ahmaditeshnizi; Wenzhi Gao; Madeleine Udell | Primary focus: Optimization modeling and code generation<br>Summary version: ICML 2024 / OptiMUS v0.2<br>OptiMUS: Optimization Modeling Using MIP Solvers and large language models [![Version][b159]][r566]: 2023; v0.1; 2023 preprint, checked through arXiv v2.; Authors: AhmadiTeshnizi, Ali; Gao, Wenzhi; Udell, Madeleine<br>OptiMUS: Scalable Optimization Modeling with (MI)LP Solvers and Large Language Models [![Version][b159]][r183]: 2024; v0.2; main ICML 2024 version, retaining its authors and citation.; Authors: AhmadiTeshnizi, Ali; Gao, Wenzhi; Udell, Madeleine<br>OptiMUS-0.3: Using Large Language Models to Model and Solve Optimization Problems at Scale [![Version][b159]][r567]: 2024; v0.3 extension; arXiv v4 (2026-06-26) lists six authors including Connor Lawless. The repository's example BibTeX still lists five and does not override the current paper. Benchmarks and results remain distinct from ICML 2024.; Authors: AhmadiTeshnizi, Ali; Gao, Wenzhi; Brunborg, Herman; Talaei, Shayan; Lawless, Connor; Udell, Madeleine<br>The author repository links v0.1, v0.2, and v0.3. The main record follows ICML 2024 v0.2; the six authors of v0.3 are listed in version information. Reproduction requires matching paper, code, and data versions.<br>OptiMUS v0.1: Version explicitly linked by the author repository and paper; does not replace the main ICML 2024 citation or experimental scope.<br>OptiMUS v0.3: Version explicitly linked by the author repository and paper; does not replace the main ICML 2024 citation or experimental scope. |
| <a id="paper-zhang2024optllm"></a>**OptLLM**<br>Jihai Zhang; Wei Wang; Siyan Guo; Li Wang; Fangquan Lin; Cheng Yang; Wotao Yin | Primary focus: Optimization modeling and code generation<br>Summary version: 2407.07924v1<br>Solving General Natural-Language-Description Optimization Problems with Large Language Models [![Version][b159]][r198]: Preprint version; formal citation follows proceedings metadata; Authors: Jihai Zhang; Wei Wang; Siyan Guo; Li Wang; Fangquan Lin; Cheng Yang; Wotao Yin<br>Published in the NAACL 2024 Industry Track, with a cloud trial page.<br>MindOpt Trial (International): Cloud trial linked by the paper; page access checked without logging in or submitting tasks.<br>MindOpt Trial (CN): Cloud trial linked by the paper; page access checked without logging in or submitting tasks. |
| <a id="paper-tang2024ragdys"></a>**RAGDyS**<br>Tang, Paul Mingzheng; Leong, Kenji Kah Hoe; Shaik, Nowshad; Lau, Hoong Chuin | Primary focus: Optimization modeling and code generation<br>Summary version: 2405.06697v1 |
| <a id="paper-wang2024raremip"></a>**Rare MIP Challenges**<br>Wang, Teng; Yu, Wing-Yin; She, Ruifeng; Yang, Wenhan; Chen, Taijie; Zhang, Jianping | Primary focus: Direct solution generation and optimization decisions<br>Summary version: 2409.04464v2 |
| <a id="paper-ye2024reevo"></a>**ReEvo**<br>Ye, Haoran; Wang, Jiarui; Cao, Zhiguang; Berto, Federico; Hua, Chuanbo; Kim, Haeyeon; Park, Jinkyoo; Song, Guojie | Primary focus: Heuristic and algorithm discovery |
| <a id="paper-ju2024ttg"></a>**To the Globe / TTG**<br>JU, Da; Jiang, Song; Cohen, Andrew; Foss, Aaron; Mitts, Sasha; Zharmagambetov, Arman; Amos, Brandon; Li, Xian; Kao, Justine T; Fazel-Zarandi, Maryam; Tian, Yuandong | Primary focus: Optimization modeling and code generation<br>Summary version: 2410.16456v1 |
| <a id="paper-liu2023ael"></a>**AEL**<br>Fei Liu; Xialiang Tong; Mingxuan Yuan; Qingfu Zhang | Primary focus: Heuristic and algorithm discovery<br>Summary version: 2311.15249v1<br>A related predecessor to EoH, retained as a separate paper. |
| <a id="paper-alahakoon2023copilot"></a>**AI-Copilot for Business Optimisation**<br>Amarasinghe, Pivithuru Thejan; Nguyen, Su; Sun, Yuan; Alahakoon, Damminda | Primary focus: Optimization modeling and code generation<br>Summary version: 2309.13218v5<br>AI-Copilot for Business Optimisation: A Framework and a Case Study in Production Scheduling [![Version][b159]][r098]: Historical title; current record follows arXiv v5<br>The current title follows arXiv v5; the debut year and historical ID remain. The artifacts repository provides generated optimization formulations. |
| <a id="paper-synth2023"></a>**CodeT5 Mathematical Program Synthesis**<br>Ganesh Prasath; Shirish Karande | Primary focus: Optimization modeling and code generation<br>Summary version: 2304.03287v1<br>CodeT5 is an early small code model; the paper follows the ICLR 2023 DL4C Workshop / arXiv version. |
| <a id="paper-romera2023funsearch"></a>**FunSearch**<br>Romera-Paredes, Bernardino; Barekatain, Mohammadamin; Novikov, Alexander; Balog, Matej; Kumar, M. Pawan; Dupont, Emilien; Ruiz, Francisco J. R.; Ellenberg, Jordan S.; Wang, Pengming; Fawzi, Omar; Kohli, Pushmeet; Fawzi, Alhussein | Primary focus: Heuristic and algorithm discovery<br>Nature online publication was in 2023; the volume appeared in 2024. |
| <a id="paper-kadioglu2023holygrail"></a>**Holy Grail 2.0**<br>Dimos Tsouros; Hélène Verhaeghe; Serdar Kadıoğlu; Tias Guns | Primary focus: Optimization modeling and code generation<br>Summary version: 2308.01589v1<br>The paper is a position paper. |
| <a id="paper-li2023power"></a>**LLMs for Power Engineering**<br>Li, Ran; Pu, Chuanqing; Tao, Junyi; Li, Canbing; Fan, Feilong; Xiang, Yue; Chen, Sijie | Primary focus: Optimization modeling and code generation |
| <a id="paper-li2023synthesizing"></a>**Multi-stage MILP Synthesis**<br>Qingyang Li; Lele Zhang; Vicky Mak-Hau | Primary focus: Optimization modeling and code generation<br>Summary version: 2311.15271v1<br>A separate predecessor cited by SMILO; the repository provides data. |
| <a id="paper-ramamonjison2023nl4opt"></a>**NL4Opt**<br>Rindranirina Ramamonjison; Timothy Yu; Raymond Li; Haley Li; Giuseppe Carenini; Bissan Ghaddar; Shiqi He; Mahdi Mostajabdaveh; Amin Banitalebi-Dehkordi; Zirui Zhou; Yong Zhang | Primary focus: Benchmarks and evaluation |
| <a id="paper-iflytek2023autoformulation"></a>**NL4Opt: Auto-Formulation Approach**<br>Yuting Ning; Jiayu Liu; Longhu Qin; Tong Xiao; Shangzi Xue; Zhenya Huang; Qi Liu; Enhong Chen; Jinze Wu | Primary focus: Optimization modeling and code generation<br>Summary version: 2302.04643v1 |
| <a id="paper-wang2023opdnl4opt"></a>**OPD@NL4Opt**<br>Wang, Kangxu; Chen, Ze; Zheng, Jiewen | Primary focus: Optimization modeling and code generation |
| <a id="paper-li2023optiguide"></a>**OptiGuide**<br>Li, Beibin; Mellou, Konstantina; Zhang, Bo; Pathuri, Jeevan; Menache, Ishai | Primary focus: Optimization modeling and code generation<br>The official monorepo hosts several optimization research projects. |
| <a id="paper-ramamonjison2022augmenting"></a>**Auto-formulation (2022)**<br>Rindra Ramamonjison; Haley Li; Timothy Yu; Shiqi He; Vishnu Rengan; Amin Banitalebi-Dehkordi; Zirui Zhou; Yong Zhang | Primary focus: Optimization modeling and code generation<br>The original PDF's first page links NL4Opt competition code and data. The 1,101 examples split into 713/99/289 train/development/test cases. Shares data lineage with the later competition report; papers retain separate IDs without counting two independent datasets.<br>Code & Data (NL4Opt): The paper's first page links shared competition code and data. generation_data, ner_data, and evaluation scripts are available; a complete interactive UI is not confirmed. |

[Back to contents](#contents)

<a id="classification"></a>

## Classification guide

Each paper has one primary focus. Research tasks, techniques, contribution types, and application settings are recorded separately. Independent contributions determine cross-module entries; totals count unique IDs.

- **Research tasks:** Modeling/code generation, verification/repair, direct solution generation, algorithm discovery, and solver enhancement are distinguished by their target outputs.
- **Techniques:** Agent, RAG, SFT, RL, and MCTS provide topic indexes. Reflection or execution feedback alone does not establish a separate research-task contribution.
- **Cross-module contributions:** Papers introducing both methods and new benchmarks appear in both modules. Methods tested only on existing benchmarks remain in the relevant method modules.
- **Resource types:** Training data, evaluation data, domain models, skills, and tools are listed separately; access indexes show available resources.
- **Training targets:** LLM weight updates, auxiliary-network training, neural routing-policy training, and algorithm-program evolution receive distinct tags.
- **Verification evidence:** Execution success, feasibility, matching objectives, structural consistency, formulation relationships, and fidelity to problem intent are distinguished. Verification claims depend on specific assumptions.
- **Applications:** Entries follow core research settings; a single example task does not automatically establish an application classification.

| Work | Research methods | Techniques | Resources or evaluation |
|---|---|---|---|
| ORLM | Optimization modeling and code generation | Data synthesis · SFT / distillation | IndustryOR, training data, and domain models |
| OptiMUS | Optimization modeling and code generation | Agent · Multi-agent · Solver feedback | NLP4LP |
| ReEvo | Heuristic and algorithm discovery | Program evolution · Reflection | Official code |
| Starjob | Direct solution generation and optimization decisions | SFT / distillation | Scheduling training data and models |
| SOVER | Model verification, diagnosis, and repair | Formal verification | Verification evaluation |

Reading tiers support selection: Core marks representative research directions, foundational methods, or important evaluation resources. Other entries are supplementary or exploratory. Tiers are not quality rankings.

[Back to contents](#contents)

[b001]: https://img.shields.io/static/v1?label=&message=Paper+1&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b002]: https://img.shields.io/static/v1?label=arXiv&message=Paper+2&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[b003]: https://img.shields.io/static/v1?label=arXiv&message=Paper+1&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[b004]: https://img.shields.io/static/v1?label=&message=Journal&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b005]: https://img.shields.io/static/v1?label=GitHub&message=Official+resource+repository+%28related%29&color=181717&style=flat&logo=github&logoColor=white
[b006]: https://img.shields.io/static/v1?label=&message=Publication&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b007]: https://img.shields.io/static/v1?label=&message=Journal+record&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b008]: https://img.shields.io/static/v1?label=GitHub&message=Literature+Collection+%28related%29&color=181717&style=flat&logo=github&logoColor=white
[b009]: https://img.shields.io/static/v1?label=arXiv&message=Paper&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[b010]: https://img.shields.io/static/v1?label=GitHub&message=Case-study+Code&color=181717&style=flat&logo=github&logoColor=white
[b011]: https://img.shields.io/static/v1?label=GitHub&message=Cleaned+Benchmarks&color=181717&style=flat&logo=github&logoColor=white
[b012]: https://img.shields.io/static/v1?label=GitHub&message=Code&color=181717&style=flat&logo=github&logoColor=white
[b013]: https://img.shields.io/static/v1?label=&message=Paper&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b014]: https://img.shields.io/static/v1?label=GitHub&message=Official+seeds+and+sample+data&color=181717&style=flat&logo=github&logoColor=white
[b015]: https://img.shields.io/static/v1?label=GitHub&message=Reproduction+Code+%28third-party%29&color=181717&style=flat&logo=github&logoColor=white
[b016]: https://img.shields.io/static/v1?label=HF&message=Reproduction+Results+%28third-party%29&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b017]: https://img.shields.io/static/v1?label=HF&message=Demo+%28third-party%29&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b018]: https://img.shields.io/static/v1?label=HF&message=Dataset&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b019]: https://img.shields.io/static/v1?label=HF&message=SAGE+SFT+100K&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b020]: https://img.shields.io/static/v1?label=&message=arXiv&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[b021]: https://img.shields.io/static/v1?label=HF&message=Model&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b022]: https://img.shields.io/static/v1?label=HF&message=Model+7B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b023]: https://img.shields.io/static/v1?label=HF&message=Model+32B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b024]: https://img.shields.io/static/v1?label=HF&message=IndustryOR&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b025]: https://img.shields.io/static/v1?label=HF&message=OR-Instruct-3K&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b026]: https://img.shields.io/static/v1?label=HF&message=ner4opt-roberta-v1&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b027]: https://img.shields.io/static/v1?label=HF&message=ner4opt-roberta-v2&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b028]: https://img.shields.io/static/v1?label=HF&message=HF+Demo+%28related%29&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b029]: https://img.shields.io/static/v1?label=GitHub&message=Training+Data&color=181717&style=flat&logo=github&logoColor=white
[b030]: https://img.shields.io/static/v1?label=GitHub&message=Generated+Formulations+%28related%29&color=181717&style=flat&logo=github&logoColor=white
[b031]: https://img.shields.io/static/v1?label=GitHub&message=Industrial+Case+Data&color=181717&style=flat&logo=github&logoColor=white
[b032]: https://img.shields.io/static/v1?label=GitHub&message=Industrial+Outputs+%28related%29&color=181717&style=flat&logo=github&logoColor=white
[b033]: https://img.shields.io/static/v1?label=GitHub&message=LPWP+Evaluation+Data+%28related%29&color=181717&style=flat&logo=github&logoColor=white
[b034]: https://img.shields.io/static/v1?label=GitHub&message=Modeling+Data&color=181717&style=flat&logo=github&logoColor=white
[b035]: https://img.shields.io/static/v1?label=&message=Competition+results+%28related%29&color=009BD5&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0ibm9uZSIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyLjUiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgZD0ibTEwIDE0IDQtNG0tNiAxLTIgMmE0IDQgMCAwIDAgNiA2bDItMm0tNC0xMCAyLTJhNCA0IDAgMCAxIDYgNmwtMiAyIi8%2BPC9zdmc%2B&logoColor=white
[b036]: https://img.shields.io/static/v1?label=GitHub&message=Code+%26+Data+%28NL4Opt%29&color=181717&style=flat&logo=github&logoColor=white
[b037]: https://img.shields.io/static/v1?label=GitHub&message=Code+%26+Cleaned+Data&color=181717&style=flat&logo=github&logoColor=white
[b038]: https://img.shields.io/static/v1?label=HF&message=Evaluation+Artifacts&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b039]: https://img.shields.io/static/v1?label=GitHub&message=Code+1&color=181717&style=flat&logo=github&logoColor=white
[b040]: https://img.shields.io/static/v1?label=GitHub&message=Code+2&color=181717&style=flat&logo=github&logoColor=white
[b041]: https://img.shields.io/static/v1?label=GitHub&message=Official+skill+library+%28related%29&color=181717&style=flat&logo=github&logoColor=white
[b042]: https://img.shields.io/static/v1?label=&message=Conference&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b043]: https://img.shields.io/static/v1?label=&message=Appendix+%28related%29&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b044]: https://img.shields.io/static/v1?label=GitHub&message=Benchmark+Inference&color=181717&style=flat&logo=github&logoColor=white
[b045]: https://img.shields.io/static/v1?label=HF&message=SDRL+Qwen3+4B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b046]: https://img.shields.io/static/v1?label=HF&message=SOLID-Qwen3&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b047]: https://img.shields.io/static/v1?label=HF&message=SOLID-StepORLM&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b048]: https://img.shields.io/static/v1?label=HF&message=Policy+8B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b049]: https://img.shields.io/static/v1?label=HF&message=GenPRM+8B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b050]: https://img.shields.io/static/v1?label=&message=Paper+2&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b051]: https://img.shields.io/static/v1?label=HF&message=Model+Gurobi-7B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b052]: https://img.shields.io/static/v1?label=HF&message=Model+COPT-7B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b053]: https://img.shields.io/static/v1?label=HF&message=Model+Gurobi-32B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b054]: https://img.shields.io/static/v1?label=HF&message=Model+COPT-32B&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b055]: https://img.shields.io/static/v1?label=HF&message=Revised+evaluation+set&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b056]: https://img.shields.io/static/v1?label=HF&message=Data+%26+Code&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b057]: https://img.shields.io/static/v1?label=&message=MindOpt+Trial+%28International%29+%28related%29&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b058]: https://img.shields.io/static/v1?label=&message=MindOpt+Trial+%28CN%29+%28related%29&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b059]: https://img.shields.io/static/v1?label=GitHub&message=Author+Coding+Agent+%28related%29&color=181717&style=flat&logo=github&logoColor=white
[b060]: https://img.shields.io/static/v1?label=&message=Evaluation+Archive+v2&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b061]: https://img.shields.io/static/v1?label=GitHub&message=Benchmark+%26+Evaluation&color=181717&style=flat&logo=github&logoColor=white
[b062]: https://img.shields.io/static/v1?label=HF&message=Text2Zinc+%28reused%29&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b063]: https://img.shields.io/static/v1?label=HF&message=Editor+%28related%29&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b064]: https://img.shields.io/static/v1?label=HF&message=Leaderboard+%28related%29&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b065]: https://img.shields.io/static/v1?label=&message=Python+Package+%28related%29&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b066]: https://img.shields.io/static/v1?label=GitHub&message=Gala+in+Text2Model&color=181717&style=flat&logo=github&logoColor=white
[b067]: https://img.shields.io/static/v1?label=&message=Author+Project+%28related%29&color=009BD5&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0ibm9uZSIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyLjUiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgZD0ibTEwIDE0IDQtNG0tNiAxLTIgMmE0IDQgMCAwIDAgNiA2bDItMm0tNC0xMCAyLTJhNCA0IDAgMCAxIDYgNmwtMiAyIi8%2BPC9zdmc%2B&logoColor=white
[b068]: https://img.shields.io/static/v1?label=GitHub&message=Data+and+validation+code&color=181717&style=flat&logo=github&logoColor=white
[b069]: https://img.shields.io/static/v1?label=GitHub&message=Diagnosis+Data&color=181717&style=flat&logo=github&logoColor=white
[b070]: https://img.shields.io/static/v1?label=GitHub&message=Inference%2C+Auditor+%26+Evaluation&color=181717&style=flat&logo=github&logoColor=white
[b071]: https://img.shields.io/static/v1?label=HF&message=OptiVerse+1K&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b072]: https://img.shields.io/static/v1?label=HF&message=EquivaFormulation+%28used+for+evaluation%29+%28related%29&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b073]: https://img.shields.io/static/v1?label=HF&message=NLP4LP+%28used+for+evaluation%29+%28related%29&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b074]: https://img.shields.io/static/v1?label=GitHub&message=Project+%28related%29&color=181717&style=flat&logo=github&logoColor=white
[b075]: https://img.shields.io/static/v1?label=&message=ICML+workshop+poster+%28related%29&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b076]: https://img.shields.io/static/v1?label=GitHub&message=Benchmark+Data&color=181717&style=flat&logo=github&logoColor=white
[b077]: https://img.shields.io/static/v1?label=&message=Author+Code+%2F+Data+Archive+%28related%29&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b078]: https://img.shields.io/static/v1?label=GitHub&message=Code+%26+Sample+Data&color=181717&style=flat&logo=github&logoColor=white
[b079]: https://img.shields.io/static/v1?label=&message=SFT+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b080]: https://img.shields.io/static/v1?label=&message=RL+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b081]: https://img.shields.io/static/v1?label=arXiv&message=Revised+Preprint&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[b082]: https://img.shields.io/static/v1?label=arXiv&message=Paper+3&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[b083]: https://img.shields.io/static/v1?label=GitHub&message=Prompts+%26+Algorithms&color=181717&style=flat&logo=github&logoColor=white
[b084]: https://img.shields.io/static/v1?label=&message=Project+%28related%29&color=009BD5&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0ibm9uZSIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyLjUiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgZD0ibTEwIDE0IDQtNG0tNiAxLTIgMmE0IDQgMCAwIDAgNiA2bDItMm0tNC0xMCAyLTJhNCA0IDAgMCAxIDYgNmwtMiAyIi8%2BPC9zdmc%2B&logoColor=white
[b085]: https://img.shields.io/static/v1?label=GitHub&message=LLaMoCo-S+Example&color=181717&style=flat&logo=github&logoColor=white
[b086]: https://img.shields.io/static/v1?label=HF&message=LLaMoCo-S&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b087]: https://img.shields.io/static/v1?label=GitHub&message=Framework&color=181717&style=flat&logo=github&logoColor=white
[b088]: https://img.shields.io/static/v1?label=GitHub&message=Frontend&color=181717&style=flat&logo=github&logoColor=white
[b089]: https://img.shields.io/static/v1?label=HF&message=CO+Instances&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b090]: https://img.shields.io/static/v1?label=GitHub&message=LLM4AD%3A+LHNS&color=181717&style=flat&logo=github&logoColor=white
[b091]: https://img.shields.io/static/v1?label=GitHub&message=LLM4AD%3A+MEoH&color=181717&style=flat&logo=github&logoColor=white
[b092]: https://img.shields.io/static/v1?label=GitHub&message=Evolved+ALNS+%28related%29&color=181717&style=flat&logo=github&logoColor=white
[b093]: https://img.shields.io/static/v1?label=&message=Proceedings&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b094]: https://img.shields.io/static/v1?label=GitHub&message=Generated+Operators+%28related%29&color=181717&style=flat&logo=github&logoColor=white
[b095]: https://img.shields.io/static/v1?label=GitHub&message=Skills&color=181717&style=flat&logo=github&logoColor=white
[b096]: https://img.shields.io/static/v1?label=GitHub&message=Lean+Proofs&color=181717&style=flat&logo=github&logoColor=white
[b097]: https://img.shields.io/static/v1?label=&message=CO+Task+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b098]: https://img.shields.io/static/v1?label=GitHub&message=Official+results+%28related%29&color=181717&style=flat&logo=github&logoColor=white
[b099]: https://img.shields.io/static/v1?label=GitHub&message=Official+problem+collection+%28related%29&color=181717&style=flat&logo=github&logoColor=white
[b100]: https://img.shields.io/static/v1?label=GitHub&message=Code+%28earlier+EvoCut%29&color=181717&style=flat&logo=github&logoColor=white
[b101]: https://img.shields.io/static/v1?label=GitHub&message=Code+%28SAGE+v3%29&color=181717&style=flat&logo=github&logoColor=white
[b102]: https://img.shields.io/static/v1?label=&message=Code+Archive&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b103]: https://img.shields.io/static/v1?label=&message=Evaluation+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b104]: https://img.shields.io/static/v1?label=&message=Workshop&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b105]: https://img.shields.io/static/v1?label=HF&message=Japanese+%2F+English+OR+Data&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b106]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+dataset&color=181717&style=flat&logo=github&logoColor=white
[b107]: https://img.shields.io/static/v1?label=GitHub&message=Evaluation+Code+%26+Data&color=181717&style=flat&logo=github&logoColor=white
[b108]: https://img.shields.io/static/v1?label=arXiv&message=Related+version&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[b109]: https://img.shields.io/static/v1?label=GitHub&message=Code+%28current+extension%29&color=181717&style=flat&logo=github&logoColor=white
[b110]: https://img.shields.io/static/v1?label=HF&message=Dataset+%28archived+original%29&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b111]: https://img.shields.io/static/v1?label=GitHub&message=Archived+original+CP-Bench&color=181717&style=flat&logo=github&logoColor=white
[b112]: https://img.shields.io/static/v1?label=HF&message=Dataset+%28third-party+mirror%29&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b113]: https://img.shields.io/static/v1?label=&message=Author+project+portal+%28related%29&color=009BD5&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0ibm9uZSIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyLjUiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgZD0ibTEwIDE0IDQtNG0tNiAxLTIgMmE0IDQgMCAwIDAgNiA2bDItMm0tNC0xMCAyLTJhNCA0IDAgMCAxIDYgNmwtMiAyIi8%2BPC9zdmc%2B&logoColor=white
[b114]: https://img.shields.io/static/v1?label=&message=Paper+PDF&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b115]: https://img.shields.io/static/v1?label=&message=Institution+record&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b116]: https://img.shields.io/static/v1?label=GitHub&message=InventoryBench&color=181717&style=flat&logo=github&logoColor=white
[b117]: https://img.shields.io/static/v1?label=GitHub&message=Human%E2%80%93AI+experiment+platform&color=181717&style=flat&logo=github&logoColor=white
[b118]: https://img.shields.io/static/v1?label=&message=Leaderboard+%28related%29&color=009BD5&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0ibm9uZSIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyLjUiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgZD0ibTEwIDE0IDQtNG0tNiAxLTIgMmE0IDQgMCAwIDAgNiA2bDItMm0tNC0xMCAyLTJhNCA0IDAgMCAxIDYgNmwtMiAyIi8%2BPC9zdmc%2B&logoColor=white
[b119]: https://img.shields.io/static/v1?label=&message=Code+%26+Analysis+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b120]: https://img.shields.io/static/v1?label=&message=Behaviour+Metrics+Code&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b121]: https://img.shields.io/static/v1?label=GitHub&message=Study+Code&color=181717&style=flat&logo=github&logoColor=white
[b122]: https://img.shields.io/static/v1?label=&message=Paper+3&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b123]: https://img.shields.io/static/v1?label=GitHub&message=Code+%26+MM-Bench&color=181717&style=flat&logo=github&logoColor=white
[b124]: https://img.shields.io/static/v1?label=GitHub&message=Expert+Skills+%282026+add-on%29&color=181717&style=flat&logo=github&logoColor=white
[b125]: https://img.shields.io/static/v1?label=GitHub&message=Code+%26+ModelingBench&color=181717&style=flat&logo=github&logoColor=white
[b126]: https://img.shields.io/static/v1?label=GitHub&message=Public+Test+Subset&color=181717&style=flat&logo=github&logoColor=white
[b127]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+Data&color=181717&style=flat&logo=github&logoColor=white
[b128]: https://img.shields.io/static/v1?label=HF&message=HF+Weights&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b129]: https://img.shields.io/static/v1?label=HF&message=HF+Model&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b130]: https://img.shields.io/static/v1?label=&message=GitHub&color=181717&style=flat&logo=github&logoColor=white
[b131]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+Suite&color=181717&style=flat&logo=github&logoColor=white
[b132]: https://img.shields.io/static/v1?label=HF&message=HF+Data&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b133]: https://img.shields.io/static/v1?label=HF&message=HF+Dataset&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b134]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+Data+%26+Evaluation&color=181717&style=flat&logo=github&logoColor=white
[b135]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+Benchmark&color=181717&style=flat&logo=github&logoColor=white
[b136]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+Subset&color=181717&style=flat&logo=github&logoColor=white
[b137]: https://img.shields.io/static/v1?label=GitHub&message=Evaluation+code&color=181717&style=flat&logo=github&logoColor=white
[b138]: https://img.shields.io/static/v1?label=GitHub&message=GitHub%3A+Test_Dataset&color=181717&style=flat&logo=github&logoColor=white
[b139]: https://img.shields.io/static/v1?label=HF&message=HF+mirror+%28third-party+field+adaptation%29&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b140]: https://img.shields.io/static/v1?label=GitHub&message=Evaluation+Code&color=181717&style=flat&logo=github&logoColor=white
[b141]: https://img.shields.io/static/v1?label=GitHub&message=GitHub%3A+ProOPF_B&color=181717&style=flat&logo=github&logoColor=white
[b142]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+Environment&color=181717&style=flat&logo=github&logoColor=white
[b143]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+Case+Data&color=181717&style=flat&logo=github&logoColor=white
[b144]: https://img.shields.io/static/v1?label=&message=Author+Archive+%28related%29&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b145]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+%28ProOPF_D+subset%29&color=181717&style=flat&logo=github&logoColor=white
[b146]: https://img.shields.io/static/v1?label=GitHub&message=GitHub%3A+Step%2FDataset&color=181717&style=flat&logo=github&logoColor=white
[b147]: https://img.shields.io/static/v1?label=&message=Zenodo+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b148]: https://img.shields.io/static/v1?label=HF&message=HF%3A+Data+%26+Code&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b149]: https://img.shields.io/static/v1?label=&message=Zenodo+v2&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b150]: https://img.shields.io/static/v1?label=GitHub&message=GitHub%3A+problems&color=181717&style=flat&logo=github&logoColor=white
[b151]: https://img.shields.io/static/v1?label=HF&message=HF+Instances&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b152]: https://img.shields.io/static/v1?label=&message=Zenodo+Archive&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b153]: https://img.shields.io/static/v1?label=GitHub&message=GitHub%3A+dataset.zip&color=181717&style=flat&logo=github&logoColor=white
[b154]: https://img.shields.io/static/v1?label=&message=Google+Drive+Data&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b155]: https://img.shields.io/static/v1?label=HF&message=HF+Artifacts&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b156]: https://img.shields.io/static/v1?label=HF&message=HF+%28third-party+results%29&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b157]: https://img.shields.io/static/v1?label=GitHub&message=GitHub%3A+Step%2Ftest&color=181717&style=flat&logo=github&logoColor=white
[b158]: https://img.shields.io/static/v1?label=GitHub&message=GitHub+Skills&color=181717&style=flat&logo=github&logoColor=white
[b159]: https://img.shields.io/static/v1?label=arXiv&message=Version&color=B31B1B&style=flat&logo=arxiv&logoColor=white
[b160]: https://img.shields.io/static/v1?label=HF&message=Version&color=FFD21E&style=flat&logo=huggingface&logoColor=FFD21E
[b161]: https://img.shields.io/static/v1?label=&message=Version&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b162]: https://img.shields.io/static/v1?label=&message=Version+%28related%29&color=B31B1B&style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik01IDJoOWw1IDV2MTVINVYyem05IDEuNVY4aDQuNUwxNCAzLjV6TTggMTF2Mmg4di0ySDh6bTAgNHYyaDh2LTJIOHoiLz48L3N2Zz4%3D&logoColor=white
[b163]: https://img.shields.io/static/v1?label=GitHub&message=Version&color=181717&style=flat&logo=github&logoColor=white

[r001]: https://doi.org/10.1145/3801961
[r002]: https://arxiv.org/abs/2507.03637
[r003]: https://arxiv.org/abs/2410.14716
[r004]: https://doi.org/10.1145/3787585
[r005]: https://github.com/FeiLiu36/LLM4AlgorithmDesign
[r006]: https://doi.org/10.1109/MIPRO70003.2026.11591581
[r007]: https://arxiv.org/abs/2606.15577
[r008]: https://doi.org/10.1109/MCI.2026.3727078
[r009]: https://arxiv.org/abs/2509.08269
[r010]: https://github.com/ishmael233/LLM4OPT
[r011]: https://arxiv.org/abs/2607.18147
[r012]: https://github.com/d2rojas/LLMs-Agents-For-SmartGrids-Code
[r013]: https://ojs.aaai.org/index.php/AAAI/article/view/35090
[r014]: https://arxiv.org/abs/2402.16269
[r015]: https://arxiv.org/abs/2508.10047
[r016]: https://github.com/LLM4OR/LLM4OR
[r017]: https://github.com/LLM4OR/LLM4OR/tree/master/static/clean_benchmarks
[r018]: https://arxiv.org/abs/2509.18180
[r019]: https://arxiv.org/abs/2508.18091
[r020]: https://arxiv.org/abs/2410.20848
[r021]: https://icml.cc/virtual/2026/78174
[r022]: https://arxiv.org/abs/2604.16804
[r023]: https://arxiv.org/abs/2606.27611
[r024]: https://github.com/xxxxxa-hub/COOPA
[r025]: https://ojs.aaai.org/index.php/AAAI/article/view/40699
[r026]: https://github.com/xzymustbexzy/DeepOR
[r027]: https://github.com/xzymustbexzy/DeepOR/tree/main/data
[r028]: https://arxiv.org/abs/2601.09100
[r029]: https://arxiv.org/abs/2602.01082
[r030]: https://github.com/WillowHe/EvoOpt_oppangu_optimization_model
[r031]: https://neurips.cc/virtual/2026/poster/155640
[r032]: https://arxiv.org/abs/2606.26578
[r033]: https://arxiv.org/abs/2602.11164
[r034]: https://proceedings.mlr.press/v306/liu26d.html
[r035]: https://github.com/ernikhildhaka-arch/OptMiner-Reproduction
[r036]: https://huggingface.co/datasets/ernikhil411/OptMiner-Reproduction
[r037]: https://huggingface.co/spaces/ernikhil411/repro-opt-miner
[r038]: https://arxiv.org/abs/2607.05346
[r039]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/4624803ce92f6c44d8cabe085d8d9d96-Abstract-Conference.html
[r040]: https://doi.org/10.1609/aaai.v40i1.36983
[r041]: https://arxiv.org/abs/2511.09092
[r042]: https://github.com/SCUTE-ZZ/OR-R1
[r043]: https://doi.org/10.1016/j.ait.2026.100059
[r044]: https://arxiv.org/abs/2508.14410
[r045]: https://github.com/ZJU-TSELab/ORThought
[r046]: https://huggingface.co/datasets/LabMem012/LogiOR
[r047]: https://proceedings.mlr.press/v306/zhao26z.html
[r048]: https://arxiv.org/abs/2605.02545
[r049]: https://github.com/rachhhhing/SAGE
[r050]: https://huggingface.co/datasets/Rachhhhing/SAGE-SFT-100K
[r051]: https://doi.org/10.1080/00207543.2026.2663386
[r052]: https://arxiv.org/abs/2511.02364
[r053]: https://neurips.cc/virtual/2025/133378
[r054]: https://arxiv.org/abs/2510.18428
[r055]: https://github.com/Minw913/AlphaOPT
[r056]: https://proceedings.mlr.press/v267/astorga25a.html
[r057]: https://arxiv.org/abs/2411.01679
[r058]: https://github.com/jumpynitro/AutoFormulator
[r059]: https://aclanthology.org/2025.acl-long.40/
[r060]: https://github.com/LLM4OR/StructuredOR
[r061]: https://huggingface.co/datasets/LLM4OR/StructuredOR
[r062]: https://arxiv.org/abs/2510.04204
[r063]: https://arxiv.org/abs/2509.22979
[r064]: https://github.com/microsoft/OptiGuide
[r065]: https://huggingface.co/microsoft/OptiMind-SFT
[r066]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/aeaf9b454f4670d5bf2f02b4b6e5bffd-Abstract-Conference.html
[r067]: https://arxiv.org/abs/2510.22192
[r068]: https://github.com/MIRALab-USTC/OptiTree
[r069]: https://arxiv.org/abs/2508.03117
[r070]: https://proceedings.mlr.press/v267/lu25o.html
[r071]: https://github.com/optsuite/OptMATH
[r072]: https://huggingface.co/Aurora-Gem/OptMATH-Qwen2.5-7B
[r073]: https://huggingface.co/Aurora-Gem/OptMATH-Qwen2.5-32B-Instruct
[r074]: https://huggingface.co/datasets/Aurora-Gem/OptMATH-Train
[r075]: https://arxiv.org/abs/2405.17743
[r076]: https://pubsonline.informs.org/doi/10.1287/opre.2024.1233
[r077]: https://github.com/Cardinal-Operations/ORLM
[r078]: https://huggingface.co/CardinalOperations/ORLM-LLaMA-3-8B
[r079]: https://huggingface.co/datasets/CardinalOperations/IndustryOR
[r080]: https://huggingface.co/datasets/CardinalOperations/OR-Instruct-Data-3K
[r081]: https://proceedings.iclr.cc/paper_files/paper/2025/hash/3deb687c44d3687ace0729e5db3b4efd-Abstract-Conference.html
[r082]: https://arxiv.org/abs/2407.09887
[r083]: https://github.com/yangzhch6/PRIVATE-RS
[r084]: https://aclanthology.org/2025.findings-emnlp.691/
[r085]: https://arxiv.org/abs/2506.17637
[r086]: https://github.com/samwu-learn/Step
[r087]: https://proceedings.iclr.cc/paper_files/paper/2024/hash/d45ee77826332c100a1e15f7765b99ff-Abstract-Conference.html
[r088]: https://github.com/xzymustbexzy/Chain-of-Experts
[r089]: https://doi.org/10.1080/03155986.2024.2388452
[r090]: https://arxiv.org/abs/2403.01342
[r091]: https://doi.org/10.1007/s10601-024-09376-5
[r092]: https://github.com/skadio/ner4opt
[r093]: https://huggingface.co/skadio/ner4opt-roberta-v1
[r094]: https://huggingface.co/skadio/ner4opt-roberta-v2
[r095]: https://huggingface.co/spaces/skadio/Ner4Opt
[r096]: https://aclanthology.org/2024.emnlp-demo.25/
[r097]: https://arxiv.org/abs/2410.16456
[r098]: https://arxiv.org/abs/2309.13218
[r099]: https://github.com/pivithuruthejanamarasinghe/AI-Copilot-Data
[r100]: https://github.com/pivithuruthejanamarasinghe/AI-Copilot-Artifacts
[r101]: https://github.com/pivithuruthejanamarasinghe/AI-Copilot-Data-Real-World-Scenario
[r102]: https://github.com/pivithuruthejanamarasinghe/AI-Copilot-Artifacts-Real-World-Scenario
[r103]: https://github.com/pivithuruthejanamarasinghe/LPWP
[r104]: https://arxiv.org/abs/2304.03287
[r105]: https://arxiv.org/abs/2311.15271
[r106]: https://github.com/yangyangyang777/Datasets-for-automatic-modeling.git
[r107]: https://arxiv.org/abs/2302.04643
[r108]: https://github.com/bigdata-ustc/nl4opt
[r109]: https://arxiv.org/abs/2301.02459
[r110]: https://nl4opt.github.io/results/
[r111]: https://aclanthology.org/2022.emnlp-industry.4/
[r112]: https://github.com/nl4opt/nl4opt-competition
[r113]: https://arxiv.org/abs/2604.25847
[r114]: https://github.com/CHIANGEL/Agora-Opt
[r115]: https://link.springer.com/chapter/10.1007/978-3-032-09192-5_5
[r116]: https://arxiv.org/abs/2505.01485
[r117]: https://arxiv.org/abs/2602.02029
[r118]: https://arxiv.org/abs/2604.00442
[r119]: https://arxiv.org/abs/2604.17708
[r120]: https://arxiv.org/abs/2601.09635
[r121]: https://github.com/CoraLiang01/lean-llm-opt
[r122]: https://arxiv.org/abs/2606.25832
[r123]: https://github.com/Hsiang-1/MiniOpt
[r124]: https://proceedings.mlr.press/v306/song26z.html
[r125]: https://arxiv.org/abs/2601.21372
[r126]: https://huggingface.co/datasets/c3aiia3c/nemo-icml2026
[r127]: https://arxiv.org/abs/2607.27918
[r128]: https://github.com/xianchaoxiu/OptGraph
[r129]: https://arxiv.org/abs/2608.07040
[r130]: https://aclanthology.org/2026.findings-emnlp.394/
[r131]: https://arxiv.org/abs/2605.29829
[r132]: https://github.com/fujiwaranoM0kou/OptSkills
[r133]: https://github.com/HQian-AI/OptSkills
[r134]: https://github.com/HQian-AI/OptSkills/tree/main/skill_library
[r135]: https://arxiv.org/abs/2607.18256
[r136]: https://neurips.cc/virtual/2026/poster/152032
[r137]: https://github.com/AuroraLHL/PEARL
[r138]: https://huggingface.co/Aurora-Gem/PEARL-Qwen3-4B-Instruct-2507
[r139]: https://arxiv.org/abs/2609.00859
[r140]: https://doi.org/10.5281/zenodo.19134435
[r141]: https://arxiv.org/abs/2609.34427
[r142]: https://github.com/tokentideAI/LLMMetaSolver
[r143]: https://huggingface.co/tokentideAI/SDRL-Qwen3-4B
[r144]: https://arxiv.org/abs/2609.09957
[r145]: https://github.com/AIOR-Research/SOLID
[r146]: https://huggingface.co/AIOR-Research/SOLID-Qwen3
[r147]: https://huggingface.co/AIOR-Research/SOLID-StepORLM
[r148]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/0bcfb525c8f8f07ae10a93d0b2a40e00-Abstract-Conference.html
[r149]: https://arxiv.org/abs/2509.22558
[r150]: https://github.com/0xzhouchenyu/StepORLM
[r151]: https://huggingface.co/Chenyu-Zhou/StepORLM-Qwen3-8B
[r152]: https://huggingface.co/Chenyu-Zhou/StepORLM-GenPRM-Qwen3-8B
[r153]: https://proceedings.iclr.cc/paper_files/paper/2025/hash/73d6c3e4b214deebbbf8256e26d2cf45-Abstract-Conference.html
[r154]: https://iclr.cc/virtual/2025/poster/28142
[r155]: https://github.com/Summer142857/DRoC
[r156]: https://proceedings.iclr.cc/paper_files/paper/2025/hash/fbe6dd68b0cf2b1d43b458d2b8ca31b0-Abstract-Conference.html
[r157]: https://arxiv.org/abs/2410.13213
[r158]: https://github.com/antgroup/LLMOPT
[r159]: https://huggingface.co/ant-opt/LLMOPT-Qwen2.5-14B
[r160]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/31e89283741f8f70ad2290b5c197ae18-Abstract-Conference.html
[r161]: https://arxiv.org/abs/2504.16918
[r162]: https://arxiv.org/abs/2503.10009
[r163]: https://github.com/bwz96sco/or_llm_agent
[r164]: https://huggingface.co/datasets/SJTU/BWOR
[r165]: https://aclanthology.org/2025.acl-industry.10/
[r166]: https://arxiv.org/abs/2506.01326
[r167]: https://github.com/XiaoAI1989/ORMind
[r168]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/98555b92e5dedbdad5921049281995bc-Abstract-Conference.html
[r169]: https://arxiv.org/abs/2505.11792
[r170]: https://github.com/Cardinal-Operations/SIRL
[r171]: https://huggingface.co/chenyitian-shanshu/SIRL-Gurobi
[r172]: https://huggingface.co/chenyitian-shanshu/SIRL-COPT
[r173]: https://huggingface.co/chenyitian-shanshu/SIRL-Gurobi32B
[r174]: https://huggingface.co/chenyitian-shanshu/SIRL-COPT32B
[r175]: https://huggingface.co/datasets/chenyitian-shanshu/ORLMBenchmark
[r176]: https://proceedings.nips.cc/paper_files/paper/2025/hash/903475a4d33d21bfd75d4fa0d124abfe-Abstract-Conference.html
[r177]: https://arxiv.org/abs/2510.16916
[r178]: https://arxiv.org/abs/2508.08147
[r179]: https://neurips.cc/virtual/2024/98475
[r180]: https://github.com/BlueAsuka/CAFA
[r181]: https://doi.org/10.1080/03155986.2024.2381306
[r182]: https://proceedings.mlr.press/v235/ahmaditeshnizi24a.html
[r183]: https://arxiv.org/abs/2402.10172
[r184]: https://github.com/teshnizi/OptiMUS
[r185]: https://huggingface.co/datasets/udell-lab/NLP4LP
[r186]: https://arxiv.org/abs/2305.11202
[r187]: https://arxiv.org/abs/2604.02666
[r188]: https://github.com/joshddrossman/LLMforIO
[r189]: https://doi.org/10.1287/ijds.2025.0074
[r190]: https://arxiv.org/abs/2501.08406
[r191]: https://github.com/li-group/OptiChat
[r192]: https://arxiv.org/abs/2601.00121
[r193]: https://doi.org/10.15439/2025F5420
[r194]: https://annals-csis.org/Volume_43/drp/5420.html
[r195]: https://arxiv.org/abs/2406.10958
[r196]: https://huggingface.co/datasets/BTBUzhy/JOC
[r197]: https://aclanthology.org/2024.naacl-industry.42/
[r198]: https://arxiv.org/abs/2407.07924
[r199]: https://opt.alibabacloud.com/chat
[r200]: https://opt.aliyun.com/chat
[r201]: https://arxiv.org/abs/2405.06697
[r202]: https://arxiv.org/abs/2307.03875
[r203]: https://arxiv.org/abs/2605.11813
[r204]: https://arxiv.org/abs/2511.11576
[r205]: https://arxiv.org/abs/2502.10557
[r206]: https://github.com/drzekunguo/LLM_Agent_Power_System_Balance
[r207]: https://arxiv.org/abs/2508.17200
[r208]: https://github.com/Amirreza-96/LLM-SO-manuscript
[r209]: https://doi.org/10.1145/3786181.3788711
[r210]: https://arxiv.org/abs/2508.07468
[r211]: https://github.com/szeider/agentic-python-coder
[r212]: https://doi.org/10.5281/zenodo.21361220
[r213]: https://arxiv.org/abs/2605.01675
[r214]: https://github.com/Yuliang795/LLMs-CP-CPSynC
[r215]: https://arxiv.org/abs/2608.00015
[r216]: https://arxiv.org/abs/2604.12955
[r217]: https://github.com/skadio/text2model
[r218]: https://huggingface.co/datasets/skadio/text2zinc
[r219]: https://huggingface.co/spaces/skadio/text2zinc-editor
[r220]: https://huggingface.co/spaces/skadio/text2model-leaderboard
[r221]: https://pypi.org/project/text2model/
[r222]: https://arxiv.org/abs/2509.08970
[r223]: https://skadio.github.io/text2model/
[r224]: https://arxiv.org/abs/2308.01589
[r225]: https://arxiv.org/abs/2507.11737
[r226]: https://arxiv.org/abs/2602.03318
[r227]: https://arxiv.org/abs/2602.19439
[r228]: https://proceedings.mlr.press/v306/ao26a.html
[r229]: https://arxiv.org/abs/2601.21008
[r230]: https://github.com/Archer222arc/ORLoopBench
[r231]: https://proceedings.iclr.cc/paper_files/paper/2025/hash/a48e5877c7bf86a513950ab23b360498-Abstract-Conference.html
[r232]: https://arxiv.org/abs/2502.09994
[r233]: https://github.com/Forrest-Stone/EOR
[r234]: https://arxiv.org/abs/2508.03406
[r235]: https://github.com/Ahalikai/MOID-Diagnosis
[r236]: https://arxiv.org/abs/2308.12923
[r237]: https://doi.org/10.1080/03155986.2024.2385189
[r238]: https://arxiv.org/abs/2605.11738
[r239]: https://aclanthology.org/2026.findings-acl.150/
[r240]: https://arxiv.org/abs/2604.21510
[r241]: https://github.com/Waichenbxx/OptiVerse
[r242]: https://huggingface.co/datasets/Waicheng/OptiVerse
[r243]: https://proceedings.mlr.press/v306/zhang26cb.html
[r244]: https://arxiv.org/abs/2510.05115
[r245]: https://github.com/Forrest-Stone/SAC-Opt
[r246]: https://aclanthology.org/2026.findings-emnlp.1886/
[r247]: https://arxiv.org/abs/2609.00728
[r248]: https://github.com/baranwa2/SOVER
[r249]: https://huggingface.co/datasets/humainlab/EquivaFormulation
[r250]: https://proceedings.mlr.press/v306/rahman26a.html
[r251]: https://arxiv.org/abs/2607.20474
[r252]: https://icml.cc/virtual/2026/poster/65537
[r253]: https://github.com/suabar/VeriSimple
[r254]: https://proceedings.mlr.press/v267/zhai25a.html
[r255]: https://arxiv.org/abs/2502.14760
[r256]: https://github.com/HumainLab/EquivaMap
[r257]: https://arxiv.org/abs/2510.27610
[r258]: https://icml.cc/virtual/2026/68291
[r259]: https://aclanthology.org/2026.findings-emnlp.1787/
[r260]: https://arxiv.org/abs/2606.04816
[r261]: https://github.com/ccccziiii/VRPBench
[r262]: https://arxiv.org/abs/2607.16646
[r263]: https://arxiv.org/abs/2605.27630
[r264]: https://arxiv.org/abs/2602.15983
[r265]: https://neurips.cc/virtual/2026/poster/153462
[r266]: https://github.com/junbolian/ReLoop
[r267]: https://huggingface.co/datasets/Jacoblian/RetailOpt-190
[r268]: https://arxiv.org/abs/2604.01455
[r269]: https://drive.google.com/drive/folders/1P7ixNFALdlZHyGm3vc8eGNRy8681W2jY?usp=drive_link
[r270]: https://arxiv.org/abs/2607.26710
[r271]: https://github.com/JAVA-Jiang/PowerAtlas
[r272]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/f0c6c93e1dbff84daf6082fef7e1a094-Abstract-Conference.html
[r273]: https://arxiv.org/abs/2509.16865
[r274]: https://github.com/Summer142857/LLMCoSolver
[r275]: https://drive.google.com/drive/folders/1bE1coGUa00gfuMkPXnfvldi1-WHGNnEb?usp=sharing
[r276]: https://drive.google.com/drive/folders/1VN9crftdW7DTsMQupbc06u6PzRT-Bwnx?usp=sharing
[r277]: https://doi.org/10.1017/pds.2025.10234
[r278]: https://arxiv.org/abs/2411.12571
[r279]: https://arxiv.org/abs/2503.01877
[r280]: https://github.com/starjob42/Starjob
[r281]: https://huggingface.co/datasets/mideavalwisard/Starjob
[r282]: https://arxiv.org/abs/2501.11968
[r283]: https://arxiv.org/abs/2409.04464
[r284]: https://arxiv.org/abs/2605.17036
[r285]: https://arxiv.org/abs/2505.12501
[r286]: https://arxiv.org/abs/2508.01724
[r287]: https://arxiv.org/abs/2407.11384
[r288]: https://github.com/zefang-liu/InvAgent
[r289]: https://aclanthology.org/2024.emnlp-industry.104/
[r290]: https://arxiv.org/abs/2402.07204
[r291]: https://github.com/YihongT/ITINERA
[r292]: https://aclanthology.org/2026.findings-acl.1417/
[r293]: https://arxiv.org/abs/2506.10764
[r294]: https://arxiv.org/abs/2605.08904
[r295]: https://github.com/OliverLeeXZ/OPT-BENCH
[r296]: https://huggingface.co/datasets/OPT-Bench/OPT-Bench
[r297]: https://proceedings.iclr.cc/paper_files/paper/2024/hash/3339f19c5fcee3ad74502947a32be9e6-Abstract-Conference.html
[r298]: https://arxiv.org/abs/2309.03409
[r299]: https://github.com/google-deepmind/opro
[r300]: https://proceedings.mlr.press/v306/chen26hb.html
[r301]: https://icml.cc/virtual/2026/poster/64869
[r302]: https://arxiv.org/abs/2604.24043
[r303]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/b9c91701ff28d480f186e4643e71ad11-Abstract-Conference.html
[r304]: https://iclr.cc/virtual/2026/poster/10010957
[r305]: https://arxiv.org/abs/2510.16701
[r306]: https://github.com/ZHANG-NI/AFL.git
[r307]: https://arxiv.org/abs/2609.08071
[r308]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/75ed738c083f8941cfc990245e4f6265-Abstract-Conference.html
[r309]: https://arxiv.org/abs/2505.12285
[r310]: https://github.com/whxru/CALM
[r311]: https://journal.iberamia.org/index.php/intartif/article/view/2584
[r312]: https://doi.org/10.4114/intartif.vol29iss77pp108-132
[r313]: https://arxiv.org/abs/2503.10968
[r314]: https://github.com/camilochs/comb-opt-for-all
[r315]: https://camilochs.github.io/comb-opt-for-all/
[r316]: https://arxiv.org/abs/2603.27628
[r317]: https://arxiv.org/abs/2610.17379
[r318]: https://arxiv.org/abs/2609.00023
[r319]: https://conference.cs.cityu.edu.hk/icist/program/ICIST%202026%20Program%20v3.pdf
[r320]: https://github.com/Mriya0306/ES-AHD
[r321]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/be36e50757bf9cd280aa74f89a7d1c23-Abstract-Conference.html
[r322]: https://arxiv.org/abs/2508.13333
[r323]: https://github.com/Challenger-XJTU/HiFo-Prompt
[r324]: https://arxiv.org/abs/2605.00369
[r325]: https://arxiv.org/abs/2602.16038
[r326]: https://arxiv.org/abs/2605.17137
[r327]: https://www.lion20.org/papers/
[r328]: https://github.com/cheikh025/LHS
[r329]: https://doi.org/10.1109/tevc.2026.3656374
[r330]: https://arxiv.org/abs/2403.01131
[r331]: https://github.com/MetaEvo/LLaMoCo
[r332]: https://huggingface.co/steven-0419/LLaMoCo
[r333]: https://arxiv.org/abs/2601.00770
[r334]: https://arxiv.org/abs/2606.14202
[r335]: https://github.com/Qzs1335/MeEvo
[r336]: https://doi.org/10.1016/j.eswa.2026.133022
[r337]: https://arxiv.org/abs/2507.20541
[r338]: https://doi.org/10.1609/aaai.v40i43.41024
[r339]: https://arxiv.org/abs/2507.20923
[r340]: https://github.com/langkhachhoha/MPaGE
[r341]: https://proceedings.mlr.press/v306/gungordu26a.html
[r342]: https://arxiv.org/abs/2601.20539
[r343]: https://github.com/oguzhangungordu/PathWise
[r344]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/7886b9bafe76c52fd568db10ff9772df-Abstract-Conference.html
[r345]: https://arxiv.org/abs/2509.19349
[r346]: https://github.com/SakanaAI/ShinkaEvolve
[r347]: https://arxiv.org/abs/2601.21239
[r348]: https://arxiv.org/abs/2502.15359
[r349]: https://github.com/Ahalikai/ARS-Routbench
[r350]: https://arxiv.org/abs/2503.03350
[r351]: https://github.com/nico-koltermann/contextual-evolution-of-heuristics
[r352]: https://arxiv.org/abs/2509.18108
[r353]: https://github.com/TBU-AILab/EASE
[r354]: https://github.com/TBU-AILab/frontEASE
[r355]: https://arxiv.org/abs/2507.17211
[r356]: https://arxiv.org/abs/2506.12495
[r357]: https://arxiv.org/abs/2506.15196
[r358]: https://github.com/microsoft/HeurAgenix
[r359]: https://huggingface.co/datasets/VictorYXL/HeurAgenixDataset
[r360]: https://doi.org/10.1609/aaai.v39i25.34898
[r361]: https://arxiv.org/abs/2412.14995
[r362]: https://github.com/datphamvn/HSEvo
[r363]: https://arxiv.org/abs/2506.00490
[r364]: https://doi.org/10.1109/CEC65147.2025.11043025
[r365]: https://scholars.cityu.edu.hk/en/publications/llm-driven-neighborhood-search-for-efficient-heuristic-design/
[r366]: https://github.com/Optima-CityU/LLM4AD/tree/main/llm4ad/method/lhns
[r367]: https://arxiv.org/abs/2405.20132
[r368]: https://github.com/XAI-liacs/LLaMEA
[r369]: https://arxiv.org/abs/2510.24013
[r370]: https://github.com/ibrahimoguzc/DiscoverHeuristics
[r371]: https://proceedings.mlr.press/v267/zheng25o.html
[r372]: https://arxiv.org/abs/2501.08603
[r373]: https://github.com/zz1358m/MCTS-AHD-master
[r374]: https://doi.org/10.1609/aaai.v39i25.34922
[r375]: https://arxiv.org/abs/2409.16867
[r376]: https://github.com/Optima-CityU/LLM4AD
[r377]: https://iclr.cc/virtual/2025/33144
[r378]: https://github.com/Fsoft-AIC/NCO-LLM
[r379]: https://arxiv.org/abs/2505.20242
[r380]: https://arxiv.org/abs/2512.03762
[r381]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/57f2d605790f01cc2d89699b0bf3b33e-Abstract-Conference.html
[r382]: https://arxiv.org/abs/2506.11057
[r383]: https://github.com/Y-Palver/L2O-STRCMP
[r384]: https://proceedings.mlr.press/v235/liu24bs.html
[r385]: https://arxiv.org/abs/2401.02051
[r386]: https://github.com/FeiLiu36/EoH
[r387]: https://proceedings.neurips.cc/paper_files/paper/2024/hash/4ced59d480e07d290b6f29fc8798f195-Abstract-Conference.html
[r388]: https://arxiv.org/abs/2402.01145
[r389]: https://github.com/ai4co/reevo
[r390]: https://arxiv.org/abs/2311.15249
[r391]: https://doi.org/10.1038/s41586-023-06924-6
[r392]: https://github.com/google-deepmind/funsearch
[r393]: https://arxiv.org/abs/2602.23092
[r394]: https://arxiv.org/abs/2603.06996
[r395]: https://github.com/Shaohua-Yu/LLM-ALNS
[r396]: https://arxiv.org/abs/2602.08253
[r397]: https://github.com/zboyn/G-LNS
[r398]: https://neurips.cc/virtual/2026/poster/150513
[r399]: https://doi.org/10.65109/ISFV2587
[r400]: https://arxiv.org/abs/2604.07872
[r401]: https://ifaamas.org/Proceedings/aamas2026/forms/contents.htm
[r402]: https://arxiv.org/abs/2607.23676
[r403]: https://arxiv.org/abs/2609.31179
[r404]: https://openreview.net/forum?id=2cYbzycSbz
[r405]: https://arxiv.org/abs/2510.07073
[r406]: https://github.com/ai4co/vrpagent
[r407]: https://proceedings.mlr.press/v267/ye25j.html
[r408]: https://github.com/thuiar/LLM-LNS
[r409]: https://arxiv.org/abs/2503.03239
[r410]: https://github.com/SHIXOOM/PAIR
[r411]: https://arxiv.org/abs/2608.07407
[r412]: https://github.com/Shuvomoy/AutoOPT
[r413]: https://github.com/Shuvomoy/AutoOPT/tree/main/Skills
[r414]: https://github.com/Shuvomoy/AutoOPT/tree/main/Lean-Related
[r415]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/c1e67cde895c3c91edb43569ad0df260-Abstract-Conference.html
[r416]: https://arxiv.org/abs/2505.20881
[r417]: https://github.com/yiding-s/MoH
[r418]: https://drive.google.com/file/d/1e4T8Yiz-qvHcChys2Tk841pbXumGVYu2/view?usp=sharing
[r419]: https://arxiv.org/abs/2506.13131
[r420]: https://github.com/google-deepmind/alphaevolve_results
[r421]: https://github.com/google-deepmind/alphaevolve_repository_of_problems
[r422]: https://doi.org/10.24963/ijcai.2026/736
[r423]: https://github.com/BeeeeenWANG/LLM-guided-cutting-plane-management
[r424]: https://arxiv.org/abs/2607.18252
[r425]: https://arxiv.org/abs/2508.11850
[r426]: https://github.com/milad1378yz/EvoCut
[r427]: https://github.com/milad1378yz/sage
[r428]: https://arxiv.org/abs/2609.36735
[r429]: https://arxiv.org/abs/2610.22861
[r430]: https://proceedings.mlr.press/v306/hou26d.html
[r431]: https://arxiv.org/abs/2605.10401
[r432]: https://github.com/hzn18/LLM4Branch
[r433]: https://arxiv.org/abs/2606.23299
[r434]: https://neurips.cc/virtual/2026/171741
[r435]: https://arxiv.org/abs/2607.25956
[r436]: https://arxiv.org/abs/2412.12038
[r437]: https://doi.org/10.1007/978-3-031-95976-9_4
[r438]: https://github.com/OptiMUS-optimization-modeling/LLM-Solver-Configuration
[r439]: https://arxiv.org/abs/2502.18540
[r440]: https://aclanthology.org/2025.emnlp-main.973/
[r441]: https://github.com/ZIKEYUAN/MA-GTS
[r442]: https://aclanthology.org/2026.emnlp-main.221/
[r443]: https://arxiv.org/abs/2608.23353
[r444]: https://github.com/Xyz-yuanhf/formuevo
[r445]: https://arxiv.org/abs/2605.09186
[r446]: https://www.nature.com/articles/s41467-026-74949-2
[r447]: https://arxiv.org/abs/2507.22876
[r448]: https://doi.org/10.5281/zenodo.17856395
[r449]: https://doi.org/10.5281/zenodo.17856423
[r450]: https://doi.org/10.1613/jair.1.20499
[r451]: https://arxiv.org/abs/2402.10705
[r452]: https://github.com/YiwenAI/AutoSAT
[r453]: https://arxiv.org/abs/2507.15615
[r454]: https://arxiv.org/abs/2605.12421
[r455]: https://neurips.cc/virtual/2026/173061
[r456]: https://arxiv.org/abs/2607.16777
[r457]: https://huggingface.co/datasets/cyberagent/JOR-Bench
[r458]: https://proceedings.mlr.press/v306/li26dz.html
[r459]: https://arxiv.org/abs/2602.10450
[r460]: https://github.com/optsuite/MIPLIB-NL
[r461]: https://github.com/optsuite/MIPLIB-NL/tree/main/dataset
[r462]: https://neurips.cc/virtual/2026/poster/139697
[r463]: https://arxiv.org/abs/2605.12154
[r464]: https://proceedings.mlr.press/v306/chen26o.html
[r465]: https://arxiv.org/abs/2601.19924
[r466]: https://github.com/Cardinal-Operations/OPTEngine
[r467]: https://huggingface.co/datasets/chenyitian-shanshu/OPTEngine
[r468]: https://proceedings.mlr.press/v306/shen26h.html
[r469]: https://icml.cc/virtual/2026/poster/63658
[r470]: https://arxiv.org/abs/2602.03070
[r471]: https://github.com/shenchao188/ProOPF-Benchamrk-Dataset
[r472]: https://arxiv.org/abs/2506.06052v2
[r473]: https://arxiv.org/abs/2506.06052
[r474]: https://doi.org/10.3233/faia250890
[r475]: https://github.com/DCP-Bench/DCP-Bench-Open
[r476]: https://huggingface.co/datasets/kostis-init/CP-Bench
[r477]: https://github.com/kostis-init/CP-Bench
[r478]: https://arxiv.org/abs/2405.13144
[r479]: https://aclanthology.org/2025.findings-naacl.146/
[r480]: https://github.com/FreedomIntelligence/Mamo
[r481]: https://huggingface.co/datasets/CardinalOperations/MAMO
[r482]: https://ojs.aaai.org/index.php/AAAI/article/view/34673
[r483]: https://arxiv.org/abs/2412.17874
[r484]: https://github.com/nl4opt/ORQA
[r485]: https://arxiv.org/abs/2503.10642
[r486]: https://apexapps.oracle.com/pls/apex/f?p=LABS%3A0%3A108770064556151%3AAPPLICATION_PROCESS%3DGETDOC_INLINE%3A%3A%3ADOC_ID%3A4780
[r487]: https://labs.oracle.com/pls/apex/f?p=94065%3A10%3A18082377147334%3A11529
[r488]: https://proceedings.mlr.press/v220/ramamonjison23a.html
[r489]: https://arxiv.org/abs/2303.08233
[r490]: https://arxiv.org/abs/2602.22465
[r491]: https://proceedings.mlr.press/v306/cao26z.html
[r492]: https://arxiv.org/abs/2605.27566
[r493]: https://github.com/dsbx7/DynaSchedBench
[r494]: https://dsbx7.github.io/
[r495]: https://arxiv.org/abs/2602.12631
[r496]: https://github.com/TianyiPeng/InventoryBench
[r497]: https://github.com/TianyiPeng/AI-human-inventory-game
[r498]: https://aclanthology.org/2026.findings-acl.1529/
[r499]: https://arxiv.org/abs/2602.02188
[r500]: https://github.com/jing12e/nlco
[r501]: https://huggingface.co/datasets/summer142857jiang/NLCO
[r502]: https://arxiv.org/abs/2603.23004
[r503]: https://arxiv.org/abs/2603.16453
[r504]: https://github.com/linghuazhang01/RetailBench
[r505]: https://arxiv.org/abs/2508.11416
[r506]: https://ojs.aaai.org/index.php/AAAI/article/view/40596
[r507]: https://arxiv.org/abs/2504.04310
[r508]: https://github.com/sunnweiwei/CO-Bench
[r509]: https://huggingface.co/datasets/CO-Bench/CO-Bench
[r510]: https://neurips.cc/virtual/2026/poster/139096
[r511]: https://arxiv.org/abs/2605.25246
[r512]: https://github.com/Minw913/FrontierOR
[r513]: https://huggingface.co/datasets/frontieror/FrontierOR
[r514]: https://proceedings.iclr.cc/paper_files/paper/2026/hash/2e49934cac6cb8604b0c67cfa0828718-Abstract-Conference.html
[r515]: https://arxiv.org/abs/2506.07972
[r516]: https://github.com/cornell-zhang/heurigym
[r517]: https://cornell-zhang.github.io/heurigym/
[r518]: https://doi.org/10.1016/j.cor.2026.107603
[r519]: https://arxiv.org/abs/2512.13374
[r520]: https://doi.org/10.5281/zenodo.21891840
[r521]: https://doi.org/10.1007/978-3-031-90065-5_24
[r522]: https://arxiv.org/abs/2501.11411
[r523]: https://zenodo.org/records/14162744
[r524]: https://doi.org/10.1145/3712255.3734347
[r525]: https://arxiv.org/abs/2504.20183
[r526]: https://github.com/XAI-liacs/BLADE
[r527]: https://arxiv.org/abs/2504.19636
[r528]: https://arxiv.org/abs/2507.03605
[r529]: https://doi.org/10.5281/zenodo.15675581
[r530]: https://arxiv.org/abs/2509.02297
[r531]: https://github.com/quangr/EoH
[r532]: https://arxiv.org/abs/2607.10768
[r533]: https://arxiv.org/abs/2605.28158
[r534]: https://github.com/0xzhouchenyu/OR-Space
[r535]: https://huggingface.co/datasets/Chenyu-Zhou/OR-Space
[r536]: https://arxiv.org/abs/2606.19787
[r537]: https://github.com/ORAgentBench/ORAgentBench
[r538]: https://proceedings.neurips.cc/paper_files/paper/2025/hash/1ddd6c6909c2a7acf877ce0f84abf6eb-Abstract-Conference.html
[r539]: https://arxiv.org/abs/2505.14148
[r540]: https://doi.org/10.52202/085713-0704
[r541]: https://github.com/usail-hkust/LLM-MM-Agent
[r542]: https://github.com/luckyfan-cs/mm-agent-expert
[r543]: https://huggingface.co/spaces/MathematicalModelingAgent/MathematicalModelingAgent
[r544]: https://aclanthology.org/2025.findings-emnlp.85/
[r545]: https://arxiv.org/abs/2505.15068
[r546]: https://github.com/qiancheng0/ModelingAgent
[r547]: https://arxiv.org/abs/2510.16943
[r548]: https://doi.org/10.1109/PESGM52009.2025.11225826
[r549]: https://arxiv.org/abs/2407.05365
[r550]: https://github.com/xiyuan-zhou/ElecBench-a-Power-Dispatch-Evaluation-Benchmark-for-Large-Language-Models
[r551]: https://aclanthology.org/2024.lrec-main.1438/
[r552]: https://proceedings.iclr.cc/paper_files/paper/2025/hash/dc594b8712f5d3ea1904092d74739d25-Abstract-Conference.html
[r553]: https://arxiv.org/abs/2410.08288
[r554]: https://github.com/microsoft/OptiGuide/tree/main/milp-evolve
[r555]: https://huggingface.co/datasets/microsoft/MILP-Evolve
[r556]: https://github.com/microsoft/MILP-Evolve
[r557]: https://arxiv.org/abs/2412.17287
[r558]: https://arxiv.org/abs/2604.04383
[r559]: https://arxiv.org/abs/2502.00828
[r560]: https://github.com/Yoontae6719/Decision-informed-Neural-Networks-with-Large-Language-Model-Integration-for-Portfolio-Optimization
[r561]: https://arxiv.org/abs/2504.14345
[r562]: https://advancesinfinancialai.com/#accepted-paper
[r563]: https://github.com/youngandbin/LLM-BLM
[r564]: https://github.com/ai4co/awesome-fm4co
[r565]: https://arxiv.org/abs/2508.14410v3
[r566]: https://arxiv.org/abs/2310.06116
[r567]: https://arxiv.org/abs/2407.19633
