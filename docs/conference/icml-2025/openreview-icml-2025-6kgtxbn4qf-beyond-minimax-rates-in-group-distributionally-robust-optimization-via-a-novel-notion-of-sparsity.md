---
title: Beyond Minimax Rates in Group Distributionally Robust Optimization via a Novel Notion of Sparsity
title_zh: 通过稀疏性新概念超越分组分布鲁棒优化的极小极大速率
authors: "Quan M. Nguyen, Nishant A Mehta, Cristóbal A Guzmán"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=6kGTxbn4Qf"
tags: ["query:qf"]
score: 6.0
evidence: 引入稀疏性概念用于分组分布鲁棒优化，与组合中的鲁棒优化相关
tldr: "分组分布鲁棒优化通常需要与组数相关的样本量。本文提出(λ,β)-稀疏性概念，证明在稀疏条件下，样本复杂度可独立于组数，从而更高效。该理论为金融中的鲁棒优化提供新视角。"
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6kgtxbn4qf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1160, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6kgtxbn4qf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 391, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6kgtxbn4qf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1350, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6kgtxbn4qf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 711, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6kgtxbn4qf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1265, \"height\": 691, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6kgtxbn4qf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1605, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6kgtxbn4qf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 384, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6kgtxbn4qf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 872, \"height\": 490, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6kgtxbn4qf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1182, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6kgtxbn4qf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1355, \"height\": 953, \"label\": \"Table\"}]"
motivation: 现有GDRO样本复杂度与组数线性相关，实际中组数可能很大。
method: "定义(λ,β)-稀疏性，并设计算法利用该结构降低样本复杂度。"
result: 理论分析和实验证明，稀疏性可显著降低有效样本复杂度。
conclusion: 在稀疏条件下，GDRO可超越极小极大下界。
---

## Abstract
The minimax sample complexity of group distributionally robust optimization (GDRO) has been determined up to a $\log(K)$ factor, where $K$ is the number of groups. In this work, we venture beyond the minimax perspective via a novel notion of sparsity that we call $(\lambda, \beta)$-sparsity. In short, this condition means that at any parameter $\theta$, there is a set of at most $\beta$ groups whose risks at $\theta$ are all at least $\lambda$ larger than the risks of the other groups. To find an $\epsilon$-optimal $\theta$, we show via a novel algorithm and analysis that the $\epsilon$-dependent term in the sample complexity can swap a linear dependence on $K$ for a linear dependence on the potentially much smaller $\beta$. 
This improvement leverages recent progress in sleeping bandits, showing a fundamental connection between the two-player zero-sum game optimization framework for GDRO and per-action regret bounds in sleeping bandits. 
We next show an adaptive algorithm which, up to logarithmic factors, obtains a sample complexity bound that adapts to the best $(\lambda, \beta)$-sparsity condition that holds. 
We also show how to obtain a dimension-free semi-adaptive sample complexity bound with a computationally efficient method.
Finally, we demonstrate the practicality of the $(\lambda, \beta)$-sparsity condition and the improved sample efficiency of our algorithms on both synthetic and real-life datasets.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义

- **研究动机**：在分组分布鲁棒优化（GDRO）中，现有极小极大样本复杂度上界为 \(\tilde{O}\big(\frac{G^2 D^2 + K}{\epsilon^2}\big)\)（其中 \(K\) 为组数），下界为 \(\Omega\big(\frac{G^2 D^2 + K}{\epsilon^2}\big)\)，表明在最坏情况下样本量与组数线性相关。然而，实际应用中的问题往往具有额外的结构，使得最坏情况很少出现。例如，在汽车制造中，不同车型在不同路面条件下的性能差异通常显著，即某些组的风险始终远高于其他组。
- **研究目标**：突破现有极小极大下界，利用问题内在结构（组间风险差距）来降低样本复杂度，使依赖项从 \(K\) 变为更小的参数 \(\beta\)。

## 2. 方法论

### 2.1 核心思想：\((\lambda, \beta)\)-稀疏性

- **定义**：对于任何参数 \(\theta \in \Theta\)，存在一个大小不超过 \(\beta\) 的组集合 \(S\)（称为 \(\lambda\)-主导集），使得 \(S\) 中每个组的最小风险比其余组中任意组的风险至少大 \(\lambda\)。简言之，任意模型下都有至多 \(\beta\) 个组的风险显著高于其他组，差距至少为 \(\lambda\)。
- **意义**：当 \(\lambda > 0\) 且 \(\beta \ll K\) 时，可将样本复杂度中关于 \(K\) 的线性依赖替换为关于 \(\beta\) 的线性依赖。

### 2.2 算法框架：基于两人零和博弈的睡眠强盗方法

论文提出了多个算法：

- **SB-GDRO**（已知 \(\lambda\)）：在博弈开始前，从每个组收集 \(m = O\big(\frac{n \ln(K)}{\lambda^2}\big)\) 个样本，用于估计各组的经验风险。每一轮：
  - **最小化玩家**（MinP）采用随机镜像下降（OMD）更新 \(\theta_t\)。
  - **最大化玩家**（MaxP）使用睡眠强盗算法 SB-EXP3 计算一个只在当前 \(\lambda\)-主导集 \(\hat{S}_{\theta_t}\) 上非零的概率分布 \(q_t\)，然后从中抽样组并获取样本。
- **SB-GDRO-A**（完全自适应 \(\lambda\)）：通过算法 SolveOpt 在几何序列中搜索最优 \(\lambda^*\)，利用 EstG 估计每个 \(\lambda\) 对应的 \(\beta_\lambda\)，使样本复杂度在未知 \(\lambda^*\) 时仅多一个 \(\ln(1/\epsilon)\) 因子。
- **SB-GDRO-SA**（半自适应、计算高效）：在博弈过程中动态调整 \(\lambda\)：若当前主导集大小超过 \(\ln K\) 且 \(\lambda\) 不低于阈值 \(L = \epsilon \sqrt{C/\ln K}\)，则将 \(\lambda\) 减半并重新采样；否则保持 \(\lambda\) 不变。最终样本复杂度与 \(\max(\ln K, \beta_{\lambda^*})\) 相关，且是维度无关的（主导项）。
- **SB-GDRO-DF**（完全维度无关）：将 \(T\) 轮划分为长度为 \(\sigma = O(\lambda \eta_w / G^2)\) 的片段，利用更新规则 \(\|\theta_{t+1} - \theta_t\| \le \eta_w G\) 的稳定性，在每个片段开始时采样更新主导集。样本复杂度中消除维度 \(n\)，但增加了 \(1/(\lambda \epsilon)\) 因子。

### 2.3 关键技术细节

- **睡眠强盗与每动作遗憾界**：将最大化玩家建模为睡眠强盗问题，其中“活跃臂”即当前 \(\lambda\)-主导集中的组。利用 SB-EXP3 得到每动作遗憾界 \(O(\sqrt{\sum_{t=1}^T |A_t| \ln(K/\delta)})\)，由于 \(|A_t| \le \beta\)，使得平均遗憾与 \(\sqrt{T\beta}\) 成正比。
- **主导集计算**：使用算法 DominantSet 基于经验风险排序，当第一个相邻组风险差大于 \(0.7\lambda\) 时停止，返回前序组作为主导集。通过均匀收敛确保该集是真正的 \(0.4\lambda\)-主导集且大小不超过 \(\beta_\lambda\)。
- **自适应 \(\lambda\) 搜索**：SolveOpt 维护区间 \([L, U]\)，通过在几何序列 \(\{1, 1/5, 1/25, \dots\}\) 上逐步缩小搜索范围，保证输出 \(\hat{\lambda}\) 使 \(f(\hat{\lambda}) \le 50 f(\lambda^*)\)，搜索样本开销为 \(O(f(\lambda^*) \ln(1/\epsilon))\)。

## 3. 实验设计

### 3.1 实验场景与数据集

1. **下界构造环境**：基于定理 3.5 的证明构建，\(K=10\)，\(\lambda^*=0.2\)，\(\beta_{\lambda^*}=2\)，\(\epsilon=0.005\)。每组风险仅由前两个组可达到最大。
2. **Adult 数据集**：按种族×性别划分 10 个组（\(K=10\)），使用 5 个特征（年龄、教育年数、资本收益、资本损失、工作小时数）预测年收入是否超过 5 万美元。损失函数为 hinge loss，归一化使损失在 \([0,1]\) 内。\(\epsilon=0.001\)。

### 3.2 基准方法

- **SMD-GDRO**（Zhang et al., 2023）：随机镜像下降 GDRO 算法，具有近最优的高概率保证，是现有唯一的合适基线。

### 3.3 评估指标

- **最优间隙**（Optimality gap）：\(\text{err}(\bar{\theta}) = \max_i R_i(\bar{\theta}) - L(\theta^*)\)。对于每个算法，绘制随样本数量增加的变化曲线。

### 3.4 实现细节

- 所有实验运行 \(T=10^6\) 轮，\(\delta=0.01\)，重复 5 次独立随机种子（0~4）。
- 通过运行理想玩家（已知真实分布 \(P_i\)）的博弈 \(T=10^7\) 轮来估计 \(\theta^*\) 的真实最大风险，对 Adult 数据集得到 \(L(\theta^*) \approx 0.49945\)。

## 4. 资源与算力

- 文中 **未明确说明** 使用的 GPU 型号、数量、训练时长等硬件资源。所有实验均在 CPU 上运行（线性模型，\(n=5\) 维），无需 GPU。运行时间取决于 \(T=10^6\) 轮，但未给出具体时长。可以推断，算法在低维特征和线性模型上的计算开销较小。

## 5. 实验数量与充分性

- **实验组数**：两个场景（合成 + 真实数据集），每个场景 5 次独立运行（不同随机种子）。主要展示 SB-GDRO-SA 与 SMD-GDRO 的收敛对比图（图3），以及主导集大小随时间变化图（图2）和组被选中次数对数图（图2右）。
- **充分性评价**：
  - 优点：验证了核心理论（稀疏性在真实数据中存在、算法样本效率更高）；结果与理论结论一致（SB-GDRO-SA 在 Adult 数据集上优于 SMD-GDRO）。
  - 不足：未进行消融实验（如不同 \(\lambda\) 初值、不同阈值选择的影响）；仅在两个任务上验证（一个合成、一个线性分类），缺乏对更复杂模型（如深度网络）或更多数据集（如图像、文本）的验证；未对比其他可能的方法（如基于置信区间的 GDRO 变体）。

## 6. 主要结论与发现

1. **理论贡献**：
   - 提出并形式化了 \((\lambda, \beta)\)-稀疏性，证明在此条件下样本复杂度可从 \(\tilde{O}(\frac{K}{\epsilon^2})\) 降至 \(\tilde{O}(\frac{\beta}{\epsilon^2})\)。
   - 建立了 GDRO 与睡眠强盗之间的核心联系，利用每动作遗憾界改善最大化玩家遗憾。
   - 给出了与 \(\lambda^*\) 自适应的算法（SB-GDRO-A）和半自适应算法（SB-GDRO-SA），以及对数因子代价。
   - 证明了维度无关的样本复杂度上界（SB-GDRO-DF）。
   - 推广了极小极大下界，证明 \(\Omega(\frac{\beta}{\epsilon^2})\) 的下界（\(\beta\) 为实际主导集大小）。

2. **实验验证**：
   - 在下界构造环境与 Adult 数据集上，SB-GDRO-SA 能在早期发现小的主导集（大小远小于 \(K\)），且最终 \(\lambda\) 接近最优 \(\lambda^*\)。
   - 样本效率显著优于 SMD-GDRO：在 Adult 数据集上，SB-GDRO-SA 使用约 \(4\times 10^5\) 样本即可达到 \(4\times 10^{-5}\) 的最优间隙，而 SMD-GDRO 在 \(10^6\) 样本后仍未能低于该值。
   - 观察到超过 60% 的样本来自女性美洲印第安-爱斯基摩组（仅占数据集的 0.3%），凸显 GDRO 的鲁棒性性质。

## 7. 优点

- **概念创新**：\((\lambda, \beta)\)-稀疏性简单直观，易于理解，且在实践中具有合理性（如汽车制造例子）。
- **理论深入**：从极小极大出发，系统建立了超越它的理论框架；提供了上界、下界、自适应、维度无关等多种变体，覆盖全面。
- **技术精巧**：将 GDRO 连接到睡眠强盗问题，充分利用了后者最新的每动作遗憾结果；自适应搜索 \(\lambda\) 的算法设计巧妙，仅多付出对数因子代价。
- **实验支撑**：虽然在规模上有限，但实验设计紧扣理论——验证了稀疏性在真实数据中的存在，并展示了实际样本效率提升，增强了理论的可信度。
- **代码与可复现性**：论文附录提供了算法伪代码和详细证明，容易复现。

## 8. 不足与局限

- **实验覆盖不足**：仅使用了两个任务（其中一个为合成数据），且特征维度极低（\(n=5\)）。未在更高维（如图像）、非凸损失、深度学习模型上测试。
- **缺乏消融研究**：如不同 \(\lambda\) 初值、不同阈值设定、不同采样策略的影响未讨论；未比较 SB-GDRO-DF 的实际性能。
- **全局稀疏性假设较强**：定义要求对任意 \(\theta\) 均成立，而实践中可能仅在 \(\theta^*\) 附近成立。文中提到“局部稀疏性”是未来方向，但实验的 Adult 数据集实际上只满足局部版本，作者对此做了说明但未深入分析。
- **计算复杂性**：完全自适应算法 SB-GDRO-A 需要构建覆盖集，对于高维 \(\Theta\) 计算昂贵；半自适应算法 SB-GDRO-SA 在每一轮都要计算主导集，虽然线性模型下可接受，但对复杂模型可能成为瓶颈。
- **未报告计算资源与推理时间**：缺少对算力和运行时间的定量分析，不利于评估实际适用性。
- **偏差风险**：Adult 数据集的分组方式（种族×性别）本身可能包含社会偏见，论文未讨论公平性含义（只提及 min-max 公平性可应用于此，但未具体分析）。

（完）
