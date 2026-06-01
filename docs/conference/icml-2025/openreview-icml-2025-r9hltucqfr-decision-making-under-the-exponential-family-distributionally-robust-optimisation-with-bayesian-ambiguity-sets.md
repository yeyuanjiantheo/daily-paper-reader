---
title: "Decision Making under the Exponential Family: Distributionally Robust Optimisation with Bayesian Ambiguity Sets"
title_zh: 指数族下的决策：基于贝叶斯模糊集的分布鲁棒优化
authors: "Charita Dellaporta, Patrick O'Hara, Theodoros Damoulas"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=r9HlTuCQfr"
tags: ["query:qf"]
score: 7.0
evidence: 基于贝叶斯模糊集的分布鲁棒优化
tldr: 本文提出基于贝叶斯模糊集的分布鲁棒优化（DRO-BAS），在数据生成过程未知的情况下，通过后验信息构建模糊集并优化最坏情况风险。该方法同时考虑了模型后验期望和后验预测两种模糊集，理论上保证了最优解的存在性，为资产配置和风险管理中的鲁棒优化提供了新工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-r9hltucqfr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 677, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r9hltucqfr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1497, \"height\": 1705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r9hltucqfr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 835, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r9hltucqfr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1758, \"height\": 1150, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r9hltucqfr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1754, \"height\": 572, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r9hltucqfr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1751, \"height\": 743, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r9hltucqfr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1763, \"height\": 1020, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r9hltucqfr/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1763, \"height\": 1139, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r9hltucqfr/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1758, \"height\": 575, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-r9hltucqfr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 751, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r9hltucqfr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1751, \"height\": 589, \"label\": \"Table\"}]"
motivation: 贝叶斯决策中忽视模型不确定性可能导致次优决策。
method: 构建后验信息驱动的模糊集，并求解最坏情况风险最小化问题。
result: 理论证明和实验表明该方法能有效对冲模型不确定性。
conclusion: 为组合优化和风险管理提供了鲁棒决策框架。
---

## Abstract
Decision making under uncertainty is challenging as the data-generating process (DGP) is often unknown. Bayesian inference proceeds by estimating the DGP through posterior beliefs on the model’s parameters. However, minimising the expected risk under these beliefs can lead to suboptimal decisions due to model uncertainty or limited, noisy observations. To address this, we introduce Distributionally Robust Optimisation with Bayesian Ambiguity Sets (DRO-BAS) which hedges against model uncertainty by optimising the worst-case risk over a posterior-informed ambiguity set. We provide two such sets, based on the posterior expectation (DRO-BAS(PE)) or the posterior predictive (DRO-BAS(PP)) and prove that both admit, under conditions, strong dual formulations leading to efficient single-stage stochastic programs which are solved with a sample average approximation. For DRO-BAS(PE), this covers all conjugate exponential family members while for DRO-BAS(PP) this is shown under conditions on the predictive's moment generating function. Our DRO-BAS formulations outperform existing Bayesian DRO on the Newsvendor problem and achieve faster solve times with comparable robustness on the Portfolio problem.

---

## 论文详细总结（自动生成）

# 论文中文总结：基于贝叶斯模糊集的指数族分布鲁棒优化

## 1. 核心问题与整体含义

- **研究动机**：在数据生成过程未知、观测数据有限或存在噪声的情况下，贝叶斯推断虽能通过后验分布估计模型参数，但直接最小化后验期望风险会导致“优化者诅咒”——决策过于乐观、泛化能力差。
- **整体思路**：将分布鲁棒优化（DRO）与贝叶斯推断结合，构建后验信息驱动的模糊集（Ambiguity Set），通过最小化最坏情况风险来对冲模型不确定性，从而提高决策的鲁棒性。

## 2. 方法论述

- **核心思想**：定义两类贝叶斯模糊集：
  - **BAS(PP)**：基于后验预测分布构建KL散度球，约束分布与后验预测的KL散度≤ϵ。
  - **BAS(PE)**：基于后验期望构建KL散度球，约束分布与模型家族中每个成员（加权后验）的KL散度的期望≤ϵ。
- **关键技术细节**：
  - 对于指数族模型与共轭先验，DRO-BAS(PE)可解析化简为基于后验期望点估计的KL模糊集，并得到强对偶形式（单阶段随机规划）。
  - DRO-BAS(PP)在矩母函数存在条件下也具有强对偶性。
  - 容忍度ϵ的最优选择可通过理论公式（如式(20)）或交叉验证确定。
- **公式/算法流程**：
  - 对偶形式（例：DRO-BAS(PE)）：
    \[
    \min_{x} \, \inf_{\gamma\ge0} \left\{ \gamma(\epsilon - G(\hat{\tau},\hat{\nu})) + \gamma \ln \mathbb{E}_{p(\xi|\hat{\eta})} \left[ e^{f_x(\xi)/\gamma} \right] \right\}
    \]
    其中 \(G\) 为后验调整项，\(\hat{\eta}\) 为后验期望参数。
  - 实际求解采用样本平均近似（SAA），将连续期望离散化。

## 3. 实验设计

- **场景与数据集**：
  - **Newsvendor问题**：模拟单变量Exponential、5维多元正态、截断正态以及受污染指数四种DGP；使用n=20训练样本，T=50测试样本。
  - **Portfolio问题**：基于DowJones 28只股票的每周收益率（1363周），使用滑动时间窗口构造109组训练/测试集（n=52，T=12）。
- **基准方法**：对比方法包括：
  - 现有贝叶斯DRO（BDRO, Shapiro et al. 2023）
  - 经验KL DRO（Hu & Hong 2013）
  - Wasserstein DRO（Kuhn et al. 2019）
  - Markowitz均值-方差模型和DowJones指数（仅Portfolio）
- **评估指标**：不同ϵ下的样本外均值与方差（out-of-sample mean & variance），以及求解时间。

## 4. 资源与算力

- 论文未明确说明使用的GPU型号或数量。
- 实验使用三台双路Intel Xeon E5-2643 v3 CPU（共12核/24线程，128GB RAM），通过SLURM调度，每任务分配1核和10GB内存，最多12个任务并行。
- 该算力配置足以处理所涉及的小规模优化问题，但未涉及大规模深度学习/GPU训练。

## 5. 实验数量与充分性

- **实验数量**：在Newsvendor上共涉及4种DGP，3种SAA样本量（M=25,100,900），24个ϵ值，500次随机重复；在Portfolio上涉及109个时间窗口。此外还进行了交叉验证选择ϵ的补充实验。
- **充分性**：
  - 覆盖了不同维度（1D/5D）、不同形状（对称/偏态/截断/污染）的DGP，验证了方法在指定与非指定模型下的表现。
  - 对比了三种贝叶斯DRO变体及两种经验DRO方法，比较全面。
  - 但未进行大规模高维实验（如D>28），也未系统性研究模型严重误指定的情况。整体实验设计合理、结论稳健。

## 6. 主要结论与发现

- DRO-BAS在样本外均值-方差Pareto前沿上普遍优于或等同于BDRO，尤其在SAA样本量较小时优势更明显。
- DRO-BAS(PE)在指数族模型下可得到闭式或高效对偶，求解时间远快于BDRO（Portfolio问题中快2~3个数量级）。
- DRO-BAS(PP)在后验预测非指数族时可能违反矩母函数存在性条件，导致性能受限；而DRO-BAS(PE)通过解析化简避免了该问题。
- 在指数族模型下，BAS(PE)等价于以“后验期望参数”为中心的KL模糊集，具有明确概率解释。
- 容忍度ϵ的选择可通过理论公式（包含G项）或交叉验证完成。

## 7. 优点

- **方法创新性**：首次系统地将贝叶斯后验不确定性融入DRO模糊集构建，既保留了贝叶斯推断的优势，又提供了鲁棒保护。
- **理论完整性**：给出了强对偶性证明、最优容忍度公式、最坏分布形式；对指数族模型实现了解析简化。
- **计算效率**：单阶段随机规划避免了BDRO的两阶段嵌套采样，显著降低求解时间。
- **实验公平性**：控制总SAA样本数M，确保DRO-BAS和BDRO在近似精度方面可比；使用多种DGP（含误指定情形）验证泛化性。

## 8. 不足与局限

- **假设限制**：DRO-BAS(PE)仅在共轭指数族下具有解析闭式；DRO-BAS(PP)需要后验预测的矩母函数有限，限制了其应用范围。
- **高维扩展**：实验中最高维度仅为28（Portfolio），未测试更高维场景（如数百维资产配置），KL模糊集在高维下体积增长快，可能导致过度保守决策。
- **模型误指定处理**：虽然展示了截断正态/受污染指数等误指定情形，但未提供针对严重误指定的理论保证或鲁棒后验替代方案。
- **ϵ选择依赖先验知识**：理论最优ϵ公式需要知道真参数，实际中仅能通过交叉验证近似，缺乏自动校准机制。
- **缺失GPU实验细节**：未说明是否使用GPU，限制了在大规模优化问题上的复现参考价值。

（完）
