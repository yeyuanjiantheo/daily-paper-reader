---
title: "Beyond Expectations: Quantile-Guided Alignment for Risk-Calibrated Language Models"
title_zh: 超越期望：风险校准语言模型的分位数引导对齐
authors: "Xinran Wang, Jin Du, Azal Ahmad Khan, Qi Le, Enmao Diao, Jiawei Zhou, Jie Ding, Ali Anwar"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=R7HJj1YvJH"
tags: ["query:qf"]
score: 4.0
evidence: 分位数引导的对齐方法用于尾部事件风险控制
tldr: 大语言模型可能生成罕见但灾难性的输出，传统RLHF仅优化平均奖励，对尾部风险控制不足。本文提出分位数引导对齐框架，通过增强奖励函数施加分位数约束，使用户能指定任意分位数的改进目标，从而更精细地控制输出分布。实验表明，该方法显著降低有害对话和不安全代码等尾部事件概率，为LLM安全对齐提供了新的风险导向思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-r7hjj1yvjh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r7hjj1yvjh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1431, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r7hjj1yvjh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 708, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r7hjj1yvjh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1437, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r7hjj1yvjh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1444, \"height\": 400, \"label\": \"Figure\"}]"
motivation: 现有RLHF仅优化平均奖励，无法充分抑制高风险的尾部事件输出。
method: 提出分位数引导对齐框架，通过增强奖励函数施加分位数约束，可指定多个奖励维度的分位数改进目标。
result: 在对话和代码生成任务上，分位数对齐显著降低了有害输出的发生率。
conclusion: 分位数引导对齐为LLM安全提供了一种可量化的风险管理方法。
---

## Abstract
Large language models can generate rare but catastrophic outputs, such as harmful conversations or insecure code. Existing Reinforcement Learning from Human Feedback (RLHF) typically maximizes average reward, leaving high-risk tail events insufficiently controlled. We introduce Quantile‑Guided Alignment (QA), a framework that allows users to specify desired improvements at any quantile—individually or across multiple reward dimensions—thus shifting the distribution of outputs with finer control toward safer, more desirable outcomes. The method extends standard RLHF via an augmented reward formulation that enforces quantile constraints. Experiments on conversation and code‐generation tasks show that quantile alignment significantly enhances quality at targeted tails while maintaining overall performance. The results position QA as a principled route to risk‑calibrated language models with tail‑focused alignment.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：大型语言模型（LLM）在生成文本或代码时，可能产生罕见但具有灾难性后果的输出（如有害对话、不安全代码）。传统的基于人类反馈的强化学习（RLHF）方法优化的是**平均奖励**，导致高风险尾部事件（如最差5%的输出）得不到有效控制。在安全关键场景中（如AI个人助理、安全敏感代码生成），仅关注平均行为是不够的。
- **研究动机**：需要一种能够显式控制输出分布中特定分位数（尤其是极端尾部）的对齐方法，从而减少罕见但严重的错误。作者提出**分位数引导对齐（Quantile-Guided Alignment, QA）**框架，允许用户指定多个奖励维度上的分位数改进目标，将输出分布向更安全、更期望的方向迁移。
- **整体含义**：QA 是 RLHF 的一个**风险校准**扩展，通过约束分位数而非均值，提供了对模型输出风险的更精细控制。

## 2. 方法论

### 核心思想
- 将分位数约束转化为等价的期望约束：对每个约束 \( Q_{\tau,p}(r) \ge c \)，等价于 \( E_p[ \tau - I\{r(x,y) < c\} ] \ge 0 \)。定义**基于指示器的分位数奖励** \( \rho_{\tau,c}(r) = \tau - I\{r < c\} \)。
- 将多个分位数约束作为正则化项，加入 KL-散度最小化目标中，形成一个凸优化问题（在分布空间上）。

### 关键技术细节
1. **单值多分位数约束**：给定单个奖励函数 \( r \)，约束 \( Q_{\tau_j,p}(r) \ge Q_{\kappa_j,p_0}(r) \)（即把 \( \tau_j \)-分位数提升到原始模型 \( \kappa_j \)-分位数水平）。优化目标：
   \[
   \min_{p} E_p[ D_{KL}(p\|p_0) ] \quad \text{s.t.} \quad E_p[ \rho_{\tau_j,\kappa_j}(r) ] \ge 0, \; j=1\ldots m
   \]
2. **解的形式（定理4.2）**：最优解为指数族形式：
   \[
   p(y|x) \propto p_0(y|x) \exp\left( \sum_{j=1}^m \lambda_j \rho_{\tau_j,\kappa_j}(r(x,y)) \right)
   \]
   其中 \( \lambda_j \ge 0 \) 是拉格朗日乘子，通过对偶问题求解：\( \max_{\lambda \ge 0} -\log C(\lambda) \)，\( C(\lambda) \) 为归一化常数。
3. **数值求解**：
   - 从原始模型 \( p_0 \) 中采样 \( n \) 个 \( (x,y) \) 样本。
   - 计算每个样本的各分位数指示奖励 \( \rho_{\tau_j,\kappa_j} \)（阈值 \( c_j \) 取原始样本的经验 \( \kappa_j \)-分位数）。
   - 用蒙特卡洛近似对偶目标，执行梯度上升更新 \( \lambda \)（带非负投影）。
   - 得到最优 \( \lambda^* \) 后，构造有效奖励 \( R(x,y)=\sum \lambda_j^* \rho_{\tau_j,\kappa_j}(r) \)，然后按标准 RLHF（PPO）用该奖励微调模型。
4. **多值多分位数扩展**：类似地，对多个奖励函数 \( r_1,\ldots,r_K \) 各自施加约束，最终奖励为所有指示器奖励的加权和，维度等于约束总数。
5. **连续分位数对齐**：进一步扩展到在整个 \( \tau \in [0,1] \) 上施加约束，需要积分形式的拉格朗日乘子函数 \( \lambda(\tau) \)，并给出敏感性分析（定理5.1）。

### 与标准 RLHF 的关系
- 当所有 \( \lambda_j \) 退化为单个标量时，可视为 RLHF 的特例。

## 3. 实验设计

### 使用数据集/场景
- **对话任务**：Anthropic Harmless 数据集（安全对话）。
- **代码生成任务**：HumanEval 数据集 + 自定义200个涵盖八大软件质量类别（文件访问、网络调用、安全风险、可维护性等）的提示，设置了不同质量等级和负面控制语句（如“不要处理边界情况”、“使变量名混淆”）。

### 评价指标
- **对齐值**：对话任务：Helpfulness 和 Harmlessness（使用 GPT-2 价值头模型评分）；代码生成：Simplicity 和 Security（使用 GPT-4o 自动评分，0-1连续值）。
- **基线性能指标**：Diversity（n-gram多样性）、Coherence（SimCSE句子相似度）、Perplexity（流畅性）。

### 对比方法
- **多目标强化学习（MORL）**：通过随机采样权重向量（λ = s·u，s均匀采样于(0,6)，u采样于概率单纯形）优化期望奖励，作为对比基线。

### 实验组数概览
1. **实验1：单值分位数增强**（仅约束 Helpfulness，9个分位数提升对）。
2. **实验2：多值分位数增强**（增加 Harmlessness 约束：5%→50%）。
3. **实验3：QA 与 MORL 对比**（在对话任务上比较各分位点性能）。
4. **附录**：代码生成的两个实验（仅对齐 Simplicity、仅对齐 Security），并给出两个具体代码生成示例的定性比较。

## 4. 资源与算力

- **硬件**：单张 NVIDIA A100 GPU（40GB）。
- **模型**：OPT-1.3B（对话）、CodeGen-350M（代码生成）。
- **训练时长**：每个对齐运行约需 **14 GPU-hours**（含对偶优化和PPO微调）。
- **说明**：由于 GPU 资源限制，使用了小型模型；未报告更大模型上的实验。

## 5. 实验数量与充分性

- **数量**：主实验3组 + 附录2组，加上2个代码生成示例分析。覆盖了单值、多值、对比基线以及代码任务。
- **充分性**：
  - **积极方面**：实验结果通过 QQ 图、基线指标表、对比散点图等清晰展示了分位数提升效果；多样性、连贯性、困惑度基本保持稳定，表明未牺牲整体性能。
  - **不足**：
    - 仅测试了小模型（1.3B和350M），未在更大模型（如7B、70B）或不同系列（Llama等）上验证。
    - 每个实验只运行了一次（未报告误差线），作者声称“使用完整评估集，抽样变异性可忽略”，但在随机性较大的 PPO 训练中，多次重复的稳定性未考察。
    - 对 MORL 的对比中，MORL 的权重采样方式是否充分（仅20个随机样本）不够详尽，可能未覆盖整个帕累托前沿。
    - 自定义代码提示的质量和代表性未详细分析。

## 6. 主要结论与发现

- QA 能够有效提升**指定分位数**上的奖励值（如 Helpfulness 的1%→5%等），同时保持整体分布形状。
- 在多值对齐中，存在**权衡**：提升 Helpfulness 可能导致 Harmlessness 下降（反之亦然）；但联合约束可同时改善两者（如 QA 将点移向散点图右上）。
- 相比于 MORL（仅优化期望），QA 更稳定地同时改善多个目标，MORL 常牺牲一个目标。
- 代码任务中，对齐 Simplicity 或 Security 可在不显著降低其他指标的情况下提升尾部；且观察到**协同效应**（对齐 Security 也提升了 Simplicity）。
- 生成的代码示例显示，对齐后的输出在逻辑性和任务相关性上明显优于原始模型。

## 7. 优点

- **方法论创新**：将分位数约束转化为凸 KL-正则化问题，有严格的数学证明（强对偶、指数族解），为风险控制提供了理论保证。
- **实现兼容性**：求解出的有效奖励可直接插入现有 RLHF 工具链（PPO/TRL），无需修改算法。
- **灵活性**：可同时处理多个奖励维度和多个分位数点，甚至连续分位数约束，用户可自定义改进目标。
- **高效性**：对偶优化仅需前向传播，无需反向传播；蒙特卡洛样本可复用，计算复杂度为 \(O(n m)\)（n为样本数，m为约束数）。
- **实验验证充分**：从对话到代码场景，从单值到多值，从定性到定量，展示了效果和稳定性。

## 8. 不足与局限

- **模型规模限制**：仅实验了 OPT-1.3B 和 CodeGen-350M，未在大模型（如70B）上验证，可能无法直接推广。
- **计算成本**：每个对齐需约14 GPU-hours，对大规模迭代不够经济；文中提到需分布式或低秩近似改进。
- **采样方差**：对于极端尾部（如0.1%分位数），蒙特卡洛方差较大，可能导致乘子发散或过冲；虽采用重要性采样和步长衰减缓解，但样本复杂度分析缺失。
- **实验复现性**：未提供多次运行的误差棒，随机性（PPO采样、梯度更新）可能影响结论稳定性。
- **对齐值评分**：对话任务使用 GPT-2 价值头，代码任务使用 GPT-4o 自动评分，评分模型本身的偏差和可靠性未被探讨。
- **数据集范围**：仅覆盖对话和简单代码生成，未涉及多轮对话、工具调用、视觉或具身场景。
- **安全风险**：论文主要关注减少有害输出，但未讨论分位数对齐是否可能被恶意利用（如故意使模型在大部分情况下“安全”但保留少数“不安全”输出）。

（完）
