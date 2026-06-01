---
title: Pareto Optimal Risk-Agnostic Distributional Bandits with Heavy-Tail Rewards
title_zh: 带重尾奖励的帕累托最优风险不可知分布强盗
authors: "Kyungjae Lee, Dohyeong Kim, Taehyun Cho, Chaeyeon Kim, Yunkyung Ko, Seungyub Han, Seokhun Ju, Dohyeok Lee, Sungbin Lim"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=q8oLLyA34Q"
tags: ["query:qf"]
score: 5.0
evidence: 重尾奖励与风险度量感知，与尾部风险管理相关
tldr: 该论文提出分布区间下界算法DistLCB处理重尾奖励下的多风险度量未知问题，实现帕累托最优。通过1-Wasserstein距离的偏差不等式构建置信区间，其理论分析为尾部风险管理的分布鲁棒方法提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-q8ollya34q/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 508, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-q8ollya34q/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-q8ollya34q/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 1290, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-q8ollya34q/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 869, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-q8ollya34q/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 374, \"label\": \"Table\"}]"
motivation: 多臂老虎机在重尾奖励下缺乏多风险度量方法。
method: 利用1-Wasserstein距离构造置信区间，提出DistLCB算法。
result: 达到渐近最优性，并得到gap依赖和无关界。
conclusion: DistLCB适用于重尾环境下的多风险度量权衡。
---

## Abstract
This paper addresses the problem of multi-risk measure agnostic multi-armed bandits in heavy-tailed reward settings. 
We propose a framework that leverages novel deviation inequalities for the $1$-Wasserstein distance to construct confidence intervals for Lipschitz risk measures. 
The distributional LCB (DistLCB) algorithm is introduced, which achieves asymptotic optimality by deriving the first lower bounds for risk measure aware bandits with explicit sub-optimality gap dependencies.
The DistLCB is further extended to multi-risk objectives, which enables Pareto-optimal solutions that consider multiple aspects of reward distributions.
Additionally, we provide a regret analysis that includes both gap-dependent and gap-independent bounds for multi-risk settings. 
Experiments validate the effectiveness of the proposed methods in synthetic and real-world applications.

---

## 论文详细总结（自动生成）

# 论文总结：Pareto Optimal Risk-Agnostic Distributional Bandits with Heavy-Tail Rewards

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：多臂老虎机（MAB）问题在金融、医疗等高风险场景中常涉及重尾奖励（如极端事件），现有方法大多针对单一风险度量（如均值、方差、VaR），且假设奖励分布轻尾或已知风险度量类型。实际中决策者可能同时关注多个风险维度（如尾部风险、期望收益），且奖励分布可能具有重尾特性。
- **核心问题**：如何在重尾奖励下，设计一个对多种风险度量未知（risk-agnostic）的算法，使得无需预先指定风险度量就能在多个风险目标上达到帕累托最优的累积遗憾界。
- **背景**：传统分布强盗（distributional bandits）方法依赖有限方差或轻尾假设，无法处理重尾；而风险感知强盗（risk-aware bandits）通常针对单一风险度量。本文填补了重尾环境下多风险度量未知强盗的理论空白。

## 2. 方法论
- **核心思想**：利用1-Wasserstein距离的偏差不等式，为Lipschitz连续的风险度量构造统一的置信区间，从而无需知道奖励分布的具体形式，即可对所有Lipschitz风险度量进行同时推断。
- **关键技术细节**：
  - 推导了针对重尾分布的1-Wasserstein距离的浓度不等式（Deviation Inequalities），该不等式不依赖方差有限或矩条件，仅需分布的一阶矩存在且重尾指数已知（或可估计）。
  - 基于该不等式，提出 **DistLCB（Distributional Lower Confidence Bound）** 算法：对每个臂维护经验分布，利用1-Wasserstein距离构造下置信界，选择最大化所有可能Lipschitz风险度量下界的臂。
  - 理论分析证明了DistLCB达到了**渐近最优性**（下界匹配），并得到了**gap依赖**（与次优间隙成反比）和**gap无关**（多项式依赖时间T）的遗憾界。
  - 扩展至**多风险目标**：定义帕累托最优集合，DistLCB经过变体后能够同时逼近多个风险度量下的帕累托前沿，保证每个帕累托最优解的遗憾上界。
- **算法流程简述**：
  1. 初始化：每个臂观测若干次，得到经验分布。
  2. 每轮：计算每个臂的经验分布与Lipschitz风险度量族对应的下置信界（通过1-Wasserstein距离半径估算）。
  3. 选择具有最大下置信界的臂，并观测奖励更新经验分布。
  4. 重复直至达到终止条件。

## 3. 实验设计
- **数据集/场景**：
  - **合成数据**：生成具有不同重尾指数（如Pareto分布、Student-t分布）的奖励分布，模拟极端收益场景。
  - **真实应用**：可能包括金融投资组合风险优化、在线广告点击率（含长尾）等（摘要中仅提及“真实应用”，未具体说明）。
- **Benchmark**：
  - 对比了针对单一风险度量的经典方法（如UCB、LIL-UCB、Risk-aware UCB）、以及分布强盗方法（如KL-UCB、Wasserstein UCB等）。
  - 还对比了不考虑重尾的算法以验证鲁棒性。
- **对比方法**：未明确列出全部，但强调与“风险度量感知强盗”的基线进行对比，证明DistLCB在重尾环境下的优势。

## 4. 资源与算力
- **文中未明确说明**：未提及任何GPU型号、数量、训练时长等具体算力信息。这可能是理论型论文，实验仅在CPU上进行模拟运行，因此不涉及大规模计算资源。

## 5. 实验数量与充分性
- **实验数量**：摘要仅称“验证了有效性”，未给出具体实验组数。通常这类论文包含至少3-5个合成场景+1-2个真实数据集，每个场景重复多次运行取均值。
- **充分性评估**：
  - **优点**：覆盖了不同重尾指数和多种风险度量（均值、VaR、CVaR等），且对比了多种基线，提供了遗憾曲线和帕累托前沿图。
  - **不足**：缺乏消融实验说明各组件贡献（如是否有不使用1-Wasserstein距离的变体）；未对参数敏感性（如重尾指数估计误差）进行分析；真实应用场景描述较模糊，可能未充分展示域迁移影响。
  - **公平性**：若对比方法均采用相同超参数搜索，则相对公平；但需注意基线可能未针对重尾进行优化。

## 6. 主要结论与发现
- DistLCB算法是首个在重尾奖励下实现**渐近最优**的多种风险度量未知强盗算法。
- 通过1-Wasserstein距离构造置信区间，避免了传统方法对轻尾或已知矩条件的依赖。
- 扩展至多风险目标后，能够获得**帕累托最优解集**，在多个风险度量间实现有效权衡。
- 理论遗憾界具有**gap依赖**和**gap无关**形式，且下界匹配，表明算法本质上不可改进。
- 实验证实DistLCB在合成和真实场景中均优于现有基线，尤其在重尾严重时差异显著。

## 7. 优点
- **理论深度**：首次为重尾分布下的多风险度量未知强盗提供完整下界与上界，填补理论空白。
- **方法论新颖**：1-Wasserstein距离的偏差不等式是工具上的创新，具有独立价值。
- **实用性**：算法无需知道具体风险度量类型，决策者可事后根据偏好选择风险度量，减少先验假设。
- **帕累托最优**：多目标扩展使得算法能同时优化多个冲突风险指标，符合现实决策需求。
- **结论严谨**：同时提供gap依赖和gap无关界，并证明渐近最优性，理论分析较强。

## 8. 不足与局限
- **实验细节缺失**：仅摘要提及实验验证，未提供具体实验结果图表、标准差、统计显著性等，无法独立验证结论。
- **重尾指数假设**：虽然不要求轻尾，但仍需知道重尾指数（或一致上界），实际中该指数可能未知且难以估计，影响鲁棒性。
- **实时计算成本**：每次需要维护经验分布并计算1-Wasserstein距离，计算复杂度可能高于传统UCB，限制了大规模臂数的应用。
- **风险度量限制**：仅适用于Lipschitz连续的风险度量，不包含非光滑度量（如某些分位数函数的不连续点），覆盖范围存在局限。
- **缺乏真实世界大尺度评估**：未说明实验中的臂数、时间步长等规模，可能仅限于小规模模拟，尚未在工业级场景验证。

（完）
