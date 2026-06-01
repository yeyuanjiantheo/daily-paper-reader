---
title: Distributional Adversarial Attacks and Training in Deep Hedging
title_zh: 深度对冲中的分布对抗攻击与训练
authors: "Guangyi He, Tobias Sutter, Lukas Gonon"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=vBtfIafffU"
tags: ["query:qf"]
score: 8.0
evidence: 分布偏移下深度对冲的对抗鲁棒性
tldr: 标准深度对冲策略在分布偏移下表现脆弱。本文提出分布对抗攻击和训练框架，将点对抗攻击推广到分布层面，并将对抗优化转化为Wasserstein球上的可计算形式。实验表明，该训练方法显著提升了对冲策略对分布扰动的鲁棒性，为期权市场中的稳健对冲提供了实用工具。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-vbtfiafffu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vbtfiafffu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1412, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vbtfiafffu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1225, \"height\": 680, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vbtfiafffu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1225, \"height\": 674, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vbtfiafffu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1226, \"height\": 673, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vbtfiafffu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1051, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vbtfiafffu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1051, \"height\": 480, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vbtfiafffu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1245, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vbtfiafffu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1093, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vbtfiafffu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1327, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vbtfiafffu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1319, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vbtfiafffu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 639, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vbtfiafffu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1095, \"height\": 726, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vbtfiafffu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 586, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vbtfiafffu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 895, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vbtfiafffu/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1330, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vbtfiafffu/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1185, \"height\": 828, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vbtfiafffu/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1207, \"height\": 1567, \"label\": \"Table\"}]"
motivation: 深度对冲模型对输入分布的小扰动高度敏感，缺乏鲁棒性。
method: 提出分布级对抗攻击，并转化为Wasserstein球上的可计算优化问题。
result: 训练后的对冲策略对分布扰动显著更鲁棒，性能下降减少。
conclusion: 为深度对冲提供了对抗训练框架，增强了实际应用中的稳健性。
---

## Abstract
In this paper, we study the robustness of classical deep hedging strategies under distributional shifts by leveraging the concept of adversarial attacks. We first demonstrate that standard deep hedging models are highly vulnerable to small perturbations in the input distribution, resulting in significant performance degradation. Motivated by this, we propose an adversarial training framework tailored to increase the robustness of deep hedging strategies. Our approach extends pointwise adversarial attacks to the distributional setting and introduces a computationally tractable reformulation of the adversarial optimization problem over a Wasserstein ball. This enables the efficient training of hedging strategies that are resilient to distributional perturbations. Through extensive numerical experiments, we show that adversarially trained deep hedging strategies consistently outperform their classical counterparts in terms of out-of-sample performance and resilience to model misspecification. Additional results indicate that the robust strategies maintain reliable performance on real market data and remain effective during periods of market change. Our findings establish a practical and effective framework for robust deep hedging under realistic market uncertainties.

---

## 论文详细总结（自动生成）

# 深度对冲中的分布对抗攻击与训练：详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：深度对冲（Deep Hedging）是一种基于神经网络的模型无关对冲方法，但其性能高度依赖训练数据的分布质量。在现实金融市场中，训练分布与测试分布之间可能存在微小偏差（模型错配），导致策略性能严重下降。现有研究多关注点状对抗扰动，但未考虑对整个数据分布进行对抗攻击。
- **整体含义**：本文首次将分布级对抗攻击与深度对冲统一，揭示了标准深度对冲策略对分布偏移的脆弱性，并提出了一个可计算的对抗训练框架来增强鲁棒性，形成了一种实用的稳健对冲方法。

## 2. 论文提出的方法论

### 核心思想
- 将深度对冲的损失最小化问题（2.6）转化为分布鲁棒优化（DRO）问题（2.7），其中内层最大化是寻找Wasserstein球内的最坏情况分布。
- 直接优化无限维Wasserstein球不可行，因此利用灵敏度分析近似内层最大化，将其转化为扰动原始样本的约束优化问题（3.14），并设计迭代算法。

### 关键技术细节
1. **损失函数**：采用优化确定性等价（OCE）形式的凸风险度量，如熵风险或条件风险价值（CVaR），使得深度对冲损失可写为期望形式。
2. **分布对抗攻击的近似**：基于Bartl等（2021）的灵敏度分析，将最坏分布近似为对每个样本按梯度方向进行扰动（定理3.3），扰动公式为：
   \[
   \hat{X}_n = X_n + \delta \cdot \frac{h(\nabla_x l(\theta; X_n)) \|\nabla_x l(\theta; X_n)\|_*^{q-1}}{\Upsilon^{1-q}}
   \]
   其中 \(\Upsilon = \left( \frac{1}{N}\sum_{n=1}^N \|\nabla_x l(\theta; X_n)\|_*^q\right)^{1/q}\)。
3. **算法**：
   - **WPGD (Wasserstein Projected Gradient Descent)**：类似于PGD的迭代方法，每次迭代沿梯度方向扰动各样本，然后投影到Wasserstein球（满足平均距离约束）。
   - **WBPGD (Wasserstein Budget Projected Gradient Descent)**：将扰动分解为预算（幅度）和方向两部分独立更新，效率更高。
4. **扩展到多维输入**：对于Heston模型（价格+波动率），通过加权距离定义联合扰动，等价于分别扰动缩放后的价格和波动率（推论4.2）。

## 3. 实验设计

- **数据集/场景**：
  - **合成模型**：Black-Scholes（BS）模型、Heston随机波动模型、一般仿射扩散（GAD）模型。
  - **真实市场数据**：S&P 500成分股（AAPL, AMZN, BRK-B, GOOGL, MSFT）2008-2020年日度收盘价。构建了两个数据集：FIX（固定参数）和ROBUST（参数区间采样，类似Lütkebohmert等2022）。
- **Benchmark**：
  - 标准深度对冲（Buehler等2019）——"Clean training"。
  - 鲁棒深度对冲（Lütkebohmert等2022）——在ROBUST数据上训练的清洁策略。
- **对比方法**：
  - 清洁训练（Clean） vs. 对抗训练（Adversarial）。
  - 对抗攻击方法：WPGD vs. WBPGD。
  - 攻击类型：仅价格攻击（S-Attack） vs. 价格与波动联合攻击（SV-Attack）。
- **评估指标**：
  - 对冲损失（风险度量值）。
  - 出样本/出分布性能（在参数偏移10%的分布上测试）。
  - 协方差矩阵距离、自相关函数差异等用于量化扰动大小。

## 4. 资源与算力

- **未明确说明**：论文在附录D中提到所有计算在**无GPU**条件下完成，使用AMD EPYC 7742或Intel Ice Lake Xeon Platinum 8358处理器，内存小于64GB。未给出具体GPU型号、数量或详细训练时长。
- 训练耗时：对100,000样本，BS模型约3小时，Heston模型约10小时（对抗训练）；清洁训练仅需约十分之一时间。

## 5. 实验数量与充分性

- **实验数量**：非常丰富。包括：
  - 不同数据量（5k~100k）下对比（图1、表6-10）。
  - 多种攻击参数δ（0.01~0.5）和损失平衡系数α（0,1,10）的网格搜索。
  - 三种合成模型（BS, Heston, GAD）各独立训练与测试。
  - 真实市场数据上的两组实验（单路径评估和多路径滚动窗口评估）。
  - 添加交易成本后的额外实验（附录E.4）。
- **充分性与公平性**：
  - 实验覆盖了不同数据规模、模型复杂度、攻击强度，并提供了标准差/范围（阴影区域），统计严谨。
  - 超参数通过验证集选择，避免了过拟合。
  - 对比的清洁训练和鲁棒深度对冲方法均按原文献实现，公平。
  - 不足：仅使用三种合成模型，未涵盖更多金融模型（如跳跃扩散）或高频数据；对抗训练仅基于Wasserstein球一种歧义集。

## 6. 主要结论与发现

1. **标准深度对冲对分布扰动高度敏感**：即使微小扰动（δ=0.01）也会导致对冲损失显著增加（表1）。
2. **对抗训练显著提升鲁棒性**：在数据稀缺（N=5000）时，SV-Attack对抗训练比清洁训练损失低54%，最差情况改善66%（图1a）。
3. **出分布性能同样受益**：在参数偏移±10%的测试集上，对抗训练仍优于清洁训练（图1b）。
4. **真实市场数据验证有效**：对抗训练策略在真实价格路径上平均表现最优，尤其在FIX数据上显著优于清洁训练，且不需要引入参数区间生成（ROBUST）即可达到甚至超越鲁棒深度对冲（表3、表8）。
5. **WBPGD优于WPGD**：在攻击效果上，WBPGD在较大扰动下产生更高的对冲损失（更有效的攻击）。

## 7. 优点

- **统一框架**：首次将分布对抗训练引入深度对冲，建立了从点攻击到分布攻击的理论桥梁。
- **计算可行**：通过灵敏度分析和优化约束集，将无限维优化简化为可迭代的样本级扰动，大幅降低复杂度。
- **实用性强**：在真实市场数据和限数据场景下效果显著，方法可作为现成插件用于现有深度对冲系统。
- **实验全面**：涵盖多种模型、数据量、攻击方法、评估指标，结论稳健。

## 8. 不足与局限

- **对超参数敏感**：Wasserstein半径δ需手动选择，最优值随数据量和模型变化，缺乏自适应机制。
- **理论保证有限**：灵敏度分析依赖Lipschitz假设，且仅在一阶渐近意义下近似；深度神经网络不保证凸性，现有DRO理论不直接适用。
- **攻击类型局限**：仅考虑Wasserstein距离下的分布攻击，未探索φ散度等其他歧义集。
- **计算开销较大**：对抗训练需要20次迭代攻击，训练时间约为清洁训练的10倍，在实时/大规模场景下可能受限。
- **市场数据样本有限**：真实数据仅覆盖5只股票约10年日频数据，缺乏对不同市场机制（如金融危机、高波动期）的专门验证。
- **实验未涉及更高维标的**：论文仅考虑单标的欧式期权，未验证多资产或奇异期权场景。

（完）
