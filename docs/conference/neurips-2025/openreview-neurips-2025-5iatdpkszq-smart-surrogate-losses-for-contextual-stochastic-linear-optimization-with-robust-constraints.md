---
title: Smart Surrogate Losses for Contextual Stochastic Linear Optimization with Robust Constraints
title_zh: 面向稳健约束的上下文随机线性优化的智能替代损失
authors: "Hyungki Im, Wyame Benslimane, Paul Grigas"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=5iAtDpkSZQ"
tags: ["query:qf"]
score: 7.0
evidence: 面向稳健约束的上下文随机线性优化的智能替代损失
tldr: 在上下文随机线性优化中引入不等式约束，其不确定参数由机器学习模型预测。本文利用共形预测构造上下文不确定性集，并设计一种对可行性敏感的智能预测后优化损失SPO-RC，同时提出凸替代损失SPO-RC+并证明Fisher一致性。实验表明该方法在满足约束的同时降低了决策误差，可直接用于金融资产配置中的稳健优化问题。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-5iatdpkszq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5iatdpkszq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1433, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5iatdpkszq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5iatdpkszq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1437, \"height\": 578, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-5iatdpkszq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1123, \"height\": 107, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5iatdpkszq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1416, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5iatdpkszq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 810, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5iatdpkszq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 963, \"height\": 106, \"label\": \"Table\"}]"
motivation: 现有CSLO方法未考虑不确定参数依赖约束，导致决策在现实中可能不可行。
method: 利用共形预测构建上下文不确定性集，提出SPO-RC损失及其凸替代SPO-RC+。
result: 在合成和真实数据上，该方法在满足约束的前提下实现了更优的决策损失。
conclusion: 为带稳健约束的预测后优化任务提供了理论上严谨且实用的损失函数。
---

## Abstract
We study an extension of contextual stochastic linear optimization (CSLO) that, in contrast to most of the existing literature, involves inequality constraints that depend on uncertain parameters predicted by a machine learning model. To handle the constraint uncertainty, we use contextual uncertainty sets constructed via methods like conformal prediction. Given a contextual uncertainty set method, we introduce the "Smart Predict-then-Optimize with Robust Constraints" (SPO-RC) loss, a feasibility-sensitive adaptation of the SPO loss that measures decision error of predicted objective parameters. We also introduce a convex surrogate, SPO-RC+, and prove Fisher consistency with SPO-RC. To enhance performance, we train on truncated datasets where true constraint parameters lie within the uncertainty sets, and we correct the induced sample selection bias using importance reweighting techniques. Through experiments on fractional knapsack and alloy production problem instances, we demonstrate that SPO-RC+ effectively handles uncertainty in constraints and that combining truncation with importance reweighting can further improve performance.

---

## 论文详细总结（自动生成）

# 论文总结：Smart Surrogate Losses for Contextual Stochastic Linear Optimization with Robust Constraints

## 1. 核心问题与整体含义（研究动机和背景）

- **问题背景**：在运筹学中，许多大规模优化问题（如供应链管理、金融计划、能源系统）都涉及依赖于上下文数据（contextual data）的不确定参数。现有“上下文随机线性优化”（CSLO）研究大多假设不确定参数仅出现在**目标函数**中，而**约束条件**中的不确定性往往被忽略。
- **核心挑战**：当约束条件包含不确定参数时，决策的可行性不再保证。传统“预测后优化”（Predict-then-Optimize）方法若直接使用点预测值，会导致大量约束违反；而过于保守的鲁棒方法则可能牺牲目标性能。
- **论文目标**：提出一种能同时处理目标和约束不确定性的集成学习框架，在保证可行性的前提下最小化决策损失。该工作特别关注金融资产配置等场景，其中资产收益和风险约束均依赖于市场特征。

## 2. 方法论：核心思想、关键技术细节、算法流程

### 2.1 整体框架：鲁棒约束下的上下文随机线性优化

- 核心问题形式化为机会约束规划（chance-constrained problem），但因其难以处理，论文将其近似为**上下文鲁棒优化问题**：
  
  \[
  \min_{w \in \mathbb{R}^d} \mathbb{E}[c^\top w | x] \quad \text{s.t.} \quad h(w;a) \leq 0 \quad \forall a \in \mathcal{U}(x), \quad w \in S
  \]

  其中 \(\mathcal{U}(x)\) 是基于共形预测（conformal prediction）构造的**上下文不确定性集**，保证以概率至少 \(1-\alpha\) 覆盖真实参数 \(a\)。

### 2.2 损失函数设计：SPO-RC 与 SPO-RC+

- **SPO-RC损失**（Smart Predict-then-Optimize with Robust Constraints）：
  - 衡量预测成本向量 \(\hat{c} = f(x)\) 导致的决策误差。
  - 当真实约束参数 \(a\) 落在不确定性集内时，损失定义为 \(c^\top w^*(\hat{c},\mathcal{U}) - c^\top w^*(c,\delta_a)\)；否则设为最大可能损失 \(\Delta_S(C)\)。
  - 该损失下界为零，且对约束违反有严格惩罚。

- **SPO-RC+损失**（凸替代）：
  - 由 SPO+ 损失扩展而来，形式为：
    \[
    \text{cost}^+(\hat{c},c;\mathcal{U}) = \max_{w \in S} \{(c - 2\hat{c})^\top w + 2\hat{c}^\top w^*(c,\mathcal{U})\}
    \]
  - 具有凸性、可微性（几乎处处），且容易通过一阶方法训练。
  - **Fisher一致性**：在假设类充分指定且分布对称连续等条件下，最小化 SPO-RC+ 的期望等价于最小化 SPO-RC 的期望，且最优预测均为条件期望 \(\mathbb{E}[c|x]\)。

### 2.3 数据处理技巧：截断与重要性重加权

- **截断（Truncation）**：仅保留那些真实约束参数 \(a\) 落在不确定性集 \(\mathcal{U}(x)\) 中的训练样本，这样 SPO-RC+ 才能成为 SPO-RC 的有效上界。
- **重要性重加权（Importance Reweighting）**：截断会引入样本选择偏差（分布漂移），论文假设 \(c\) 和 \(a\) 在给定 \(x\) 下条件独立，从而将问题简化为协变量偏移。使用**核均值匹配（KMM）** 估计权重 \(\beta(x) = P_D(x)/P_{\tilde{D}}(x)\)，并训练加权后的 SPO-RC+ 损失。

### 2.4 算法流程（Algorithm 1）

1. 用共形预测构建不确定性集 \(\mathcal{U}\)。
2. 遍历训练集，若 \(a_i \in \mathcal{U}(x_i)\) 则保留，得到截断数据集 \(\tilde{D}_I\)。
3. 以截断数据为源域、原始数据（或校准集）为目标域，用 KMM 求解重要性权重 \(\hat{\beta}\)。
4. 最小化加权经验 SPO-RC+ 损失，得到最终预测模型 \(\hat{f}\)。

---

## 3. 实验设计

### 3.1 数据集与场景

- **玩具示例（Toy Example）**：两个物品的分数背包问题简化版，展示重要性重加权对决策边界的纠正效果。
- **分数背包问题（Fractional Knapsack）**：
  - 使用 ℓ₂ 范数共形分数和 ℓ₁ 范数共形分数两种设置。
  - 合成数据：\(d=5\) 个物品，\(p=10\) 个特征，成本向量和重量向量均由多项式核模型生成，成本复杂度参数 \( \text{deg}_c\) 从 2 到 8 变化。
- **合金生产问题（Alloy Production）**：鲁棒覆盖线性规划，需满足两种金属（锌、铜）的最低含量要求，浓度不确定性由共形预测建模。

### 3.2 对比方法

- **PTO（Predict-then-Optimize）**：直接用点预测值 \(\hat{a}\) 求解优化问题，不构建不确定性集。
- **MSE（均方误差回归）**：在三种数据集（原始数据 DO、截断数据 DT、重要性重加权数据 DIR）上训练线性回归模型。
- **随机森林（RF）**：仅在 ℓ₂ 范数背包实验中作为非参数方法对比。
- **SPO-RC+**：线性模型，用 SPO-RC+ 损失训练，在 DO、DT、DIR 上分别测试。

### 3.3 评估指标

- **归一化 SPORC 测试损失（NormSPORCTest）**：在测试集上计算 SPO-RC 损失之和，除以真实最优成本的绝对值之和。若解不可行，则损失设为最大损失。
- **不可行解比例**：统计解违反真实约束的样本比例。

### 3.4 实验配置

- 每次实验使用 5 个不同随机种子，报告均值和标准差。
- 训练数据规模：1000 或 5000 个样本；测试集 3000 个样本。
- 优化器：Adam，学习率根据模型调整（MSE: 1e-2~1e-3，SPO-RC+: 4e-2~5e-3），训练 50 轮，含早停和验证集。
- 共形预测置信度：\(\alpha = 0.2\)。
- KMM 参数：\(B=1000\)，\(\epsilon = (\sqrt{m}-1)/\sqrt{m}\)，采用高斯核。

---

## 4. 资源与算力

- 论文**未明确说明 GPU 型号或数量**。
- 训练环境：一台 MacBook Pro（Intel 芯片，16GB RAM）。
- 计算开销：
  - MSE 训练：数千样本在数十秒内完成（如背包问题 1000 样本约 7 秒）。
  - SPO-RC+ 训练：耗时较长（背包问题 1000 样本约 30~44 秒，5000 样本约 158~428 秒）。
  - KMM 权重计算：对 \(m=1000\) 约 1~4 秒，相对较小。
- 缓存策略实验展示：通过随机缓存解决方案可将训练时间大幅降低（如从 160 秒降至 40 秒），同时性能仅略微下降。

---

## 5. 实验数量与充分性

### 5.1 实验数量

- **玩具示例**：2 组子实验（重要性重加权示例、截断示例），均可视化决策边界。
- **分数背包（ℓ₂）**：3 种方法（MSE、RF、SPO-RC+）× 3 种数据集（DO、DT、DIR）× 4 种成本复杂度（deg_c=2,4,6,8）× 2 种训练大小（1000, 5000）= 至少 **72 组** 实验点（含随机种子重复）。
- **分数背包（ℓ₁）**：2 种方法（MSE、SPO-RC+）× 3 种数据集 × 4 种复杂度 = **24 组** 实验点。
- **合金生产问题**：2 种方法 × 3 种数据集 × 4 种复杂度 = **24 组** 实验点。
- **缓存策略实验**：在 ℓ₁ 背包上测试不同缓存命中率，评估性能与训练时间的权衡。
- **训练时间对比表**：记录 MSE 和 SPO-RC+ 在不同问题、不同规模下的耗时。

### 5.2 充分性与公平性

- **实验设计较充分**：覆盖了不同问题类型、不同复杂度、不同训练规模、不同损失函数，且分别报告了在原始、截断、重加权三种数据集上的表现，使得消融分析完整。
- **对照公平**：所有方法都使用相同的预测模型结构（线性/随机森林），相同的特征输入；优化器超参数分别调优但范围合理。
- **统计可靠性**：5 个随机种子重复并报告标准差，误差棒在图中显示，结果可信。
- **局限性**：所有实验基于合成数据，未在真实数据集上验证；缺少与其他端到端方法的直接对比（如 Wang et al. 2023 的端到端不确定性集学习）。

---

## 6. 论文的主要结论与发现

1. **SPO-RC+ 损失的有效性**：在大部分设置下，SPO-RC+ 模型的测试损失优于 MSE 模型，尤其当成本预测复杂度较高时优势明显。在简单情况下（低复杂度），两者性能接近。
2. **鲁棒约束的必要性**：PTO 方法有 30%~45% 的解不可行，而所有使用鲁棒约束的方法（无论损失函数）均将不可行比例降至 0.02%~0.2%，证明不确定性集能有效保证可行性。
3. **截断与重要性重加权的价值**：
   - 直接使用截断数据（DT）有时比原始数据（DO）稍差，但加上重要性重加权（DIR）后，性能往往达到最优或次优，特别是在训练数据较少时（n=1000）。
   - 玩具示例直观展示了重要性重加权能纠正因截断导致的决策边界偏移。
4. **Fisher 一致性理论成立**：在假设类充分指定等条件下，SPO-RC+ 可最小化真实 SPO-RC 损失。
5. **可扩展性**：结合解决方案缓存技术后，训练时间大幅缩短，性能仅轻微下降，表明方法有实际部署潜力。

---

## 7. 优点

- **理论贡献严谨**：
  - 证明了 SPO-RC+ 与 SPO-RC 的 Fisher 一致性（定理 2.4），并给出了泛化界（附录 B），将 El Balghiti et al. 的结论扩展到上下文相关可行集。
  - 展示了通过重要性重加权修正截断偏差的合理性（引理 3.3），且泛化界仍适用。
- **方法设计实用**：
  - 采用共形预测构造不确定性集，无需分布假设，模型无关。
  - SPO-RC+ 是凸的，可使用一阶优化器训练，易于集成到标准深度学习流程。
  - 数据截断和重加权策略简单有效，尤其适合数据量有限或模型容量不足时的场景。
- **实验覆盖面广**：
  - 同时测试了ℓ₂和ℓ₁两种共形分数形式，对应不同的鲁棒对应（SOCP 和 LP），展示方法的灵活性。
  - 除了基本对比，还做了缓存策略实验，关注可扩展性这一实际问题。
- **代码开源**：基于 PyEPO 库，提供可复现的代码。

---

## 8. 不足与局限

- **仅限线性目标**：论文假设目标函数是线性的（\(c^\top w\)），对非线性目标（如二次规划、一般凸优化）不适用。这限制了在更复杂金融模型（如均值-方差组合）中的应用。
- **两步骤分离学习**：不确定性集 \(\mathcal{U}(x)\) 的构建独立于成本预测模型 \(f\) 的学习，未实现端到端联合优化。最近的工作（如 Wang et al. 2023）已提出学习决策驱动的不确定性集，本文未与之对比。
- **条件独立性假设**：引理 3.3 假设 \(c\) 和 \(a\) 在给定 \(x\) 下独立。现实中两者可能高度相关（如资产收益和信用风险都受市场因素影响），违反该假设时重要性重加权的有效性需进一步验证。
- **实验数据均为合成**：虽然控制了数据生成过程的复杂性，但缺乏真实场景（如真实供应链数据、金融时间序列）的验证。合成的噪声模式和依赖结构可能过于理想化。
- **未讨论超参数敏感性**：共形预测的 \(\alpha\) 固定为 0.2，KMM 的 \(B,\epsilon\) 按经验设置，未进行系统敏感性分析。实际应用中这些参数对结果影响可能较大。
- **计算资源有限**：实验仅在单台笔记本 CPU 上运行，未报告 GPU 加速下的性能，也未在大规模（如百万级别样本）下测试。SPO-RC+ 训练在 5000 样本时尚可接受，但若问题维度或样本量进一步扩大，求解鲁棒对应问题（SOCP/LP）可能成为瓶颈。
- **对照方法不够全面**：未与其他决策驱动学习方法（如通过隐式微分训练的端到端网络、分布鲁棒优化方法）比较。仅对比了 MSE 和随机森林，baseline 略显单薄。

（完）
