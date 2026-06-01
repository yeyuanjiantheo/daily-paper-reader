---
title: Online Portfolio Selection with ML Predictions
title_zh: 基于机器学习预测的在线投资组合选择
authors: "Ziliang Zhang, Tianming Zhao, Albert Zomaya"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=zOFxp98km2"
tags: ["query:qf"]
score: 8.0
evidence: 在线投资组合选择结合机器学习预测与稳健性保证
tldr: 在线投资组合选择中，经典策略忽略预测而启发式方法在预测错误时表现差。本文提出RAM（Rebalanced Arithmetic Mean with predictions），在完美预测下能捕获后见最优财富的常数比例，即使在对抗性预测下仍能超越序列几何均值。理论证明和实验验证了该策略的鲁棒性和有效性，为预测驱动的投资组合优化提供了新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-zofxp98km2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 620, \"height\": 412, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-zofxp98km2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1415, \"height\": 356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zofxp98km2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zofxp98km2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1286, \"height\": 1071, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zofxp98km2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1117, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zofxp98km2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1050, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zofxp98km2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1319, \"height\": 288, \"label\": \"Table\"}]"
motivation: 现有在线投资组合策略要么忽略预测，要么在预测错误时表现脆弱。
method: 提出RAM策略，利用预测信息并保证最坏情况下的性能下界。
result: 在完美预测下达到后见最优财富的常数比例，在对抗预测下仍超越几何均值。
conclusion: 该方法桥接了古典策略与预测驱动方法，为在线投资组合提供鲁棒框架。
---

## Abstract
Online portfolio selection seeks to determine a sequence of allocations to maximize capital growth. Classical universal strategies asymptotically match the best constant-rebalanced portfolio but ignore potential forecasts, whereas heuristic methods often collapse when belief fails. We formalize this tension in a learning-augmented setting in which an investor observes (possibly erroneous) predictions prior to each decision moment, and we introduce the Rebalanced Arithmetic Mean portfolio with predictions (RAM). Under arbitrary return sequences, we prove that RAM captures at least a constant fraction of the hindsight-optimal wealth when forecasts are perfect while still exceeding the geometric mean of the sequence even when the predictions are adversarial. Comprehensive experiments on large-scale equity data strengthen our theory, spanning both synthetic prediction streams and production-grade machine-learning models. RAM advantages over universal-portfolio variants equipped with side information across various regimes. These results demonstrate that modest predictive power can be reliably converted into tangible gains without sacrificing worst-case guarantees.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机与背景）

在线投资组合选择需要在每个交易期将资本分配到多个资产，以最大化累积财富。现有方法分为两大流派：
- **经典通用策略**（如 Universal Portfolio, Exponential Gradient）：不依赖任何市场假设，提供最坏情况下的性能保证（与事后最优常量再平衡组合渐近匹配），但完全忽略预测信息，因此无法利用有利的市场信号。
- **启发式/预测驱动方法**（如均值回归、机器学习预测）：通过预测未来收益来提高收益，但一旦预测错误，财富可能灾难性损失。

本文旨在**融合两者的优势**，提出一种“学习增强”框架，使得投资策略在利用 ML 预测的同时，仍能保持经典策略的稳健性——即在预测完美时接近最优，在预测完全错误时也不至于崩溃。

### 2. 方法论：核心思想、关键技术细节、算法流程

**核心思想**：采用两阶段架构——基础层使用一个预测无关的保守策略（buy-and-hold）生成权重向量；然后通过 ML 预测的资产收益排序（permutation）重新分配权重，将较大的权重赋予预测收益较高的资产。

**关键技术细节**：
- 每轮开始时，投资者接收一个 ML 预测排序 σ(i)（只要求相对排序，不需具体数值）。
- 将当前权重向量按降序排列得到 b↓(i)，然后根据 σ(i) 进行“逆配对”：将第 j 大的权重赋给预测排序第 j 的资产。
- 实际回报为 b↓(i) 与预测排序对应的实际收益向量 y(i) 的内积（即 b↓(i)·y(i)）。
- 更新权重时采用乘性更新（multiplicative update）：下一轮权重正比于当前权重乘以实际收益。
- 算法复杂度为 O(m log m) 每轮，其中 m 为资产数。

**公式（文字描述）**：
- 定义预测误差因子 η(i) = (b↓(i)·x↓(i)) / (b↓(i)·y(i))，其中 x↓(i) 为真实收益的降序排列。
- 累积误差 η_n = ∏ 1/η(i) ∈ (0,1]。
- 最终财富可分解为：SRAM_n = η_n × ∏ (b↓(i)·x↓(i))。

**理论保证**：
- **最坏情况**（对抗预测）：SRAM_n ≥ (∏_{j=1}^m ∏_{i=1}^n x_j(i))^{1/m}，即不低于所有资产收益的几何均值（价值线）。
- **完美预测**（η_n=1）：SRAM_n ≥ (1/m) ∏_{i=1}^n max_j x_j(i)，即达到事后最优单一资产财富的常数比例 1/m。

### 3. 实验设计

**数据集与场景**：
- **NYSE(O)**（1962–1984，36 只股票，5651 个交易日）
- **NYSE(N)** 的延伸部分（1985–2006，21 只股票，5526 个交易日，避免重叠）
- **S&P 500**（2010–2024，501 只股票，选取两个子窗口）：
  - 高波动窗口（COVID-19 崩溃期，2019.7–2020.5）
  - 近期窗口（2022.12–2024.12）

**基准方法**：
- Universal Portfolio (UP)
- Exponential Gradient (EG)
- 带侧信息的通用组合（UPSI、EGSI）：将预测排序转化为离散状态信号。
- ML 策略（单资产全押于预测最佳资产）

**对比设置**：
- 合成预测：通过参数 p ∈ [0,1] 控制预测准确率（p=0 为完全对抗，p=0.5 完全随机，p=1 完美），每个 p 进行 1000 次蒙特卡洛模拟。
- 真实 ML 预测：使用 LightGBM LambdaMART 训练排序模型，每日用 250 天滑动窗口重训练，预测次日收益排序。
- 股票组合：从 2 只到 30 只不等，以测试可扩展性。

### 4. 资源与算力

论文明确提到：  
> “All experiments compute under 6h on one standard CPU.”  

未提供 CPU 具体型号、内存容量，也未使用 GPU。总计算开销在单个标准 CPU 上不超过 6 小时。

### 5. 实验数量与充分性

- **合成预测实验**：覆盖 12 种股票组合（从 2 只到 10+ 只），每个组合在多种 p 值下运行 1000 次独立模拟，统计均值、标准差和中位数。
- **真实 ML 实验**：在 S&P 500 上，两个市场体制（高波动与近期），三种篮子（α 流行、β 多元化、γ 大规模），对比 RAM 与 EGSI、ML 等。
- **消融/额外分析**：展示了 RAM 与 EGSI 在 p=53%~60% 时的财富对比曲线（图 2），验证单调优势。
- **充分性评价**：实验覆盖面较广，包括小资产、大资产、合成预测、真实预测、不同市场状态。对比方法合理，均采用相同预测信号保证公平。但缺乏与最新深度学习在线投资组合方法（如 DNN 直接优化）的对比，也未进行统计显著性检验（如 t 检验或置信区间）。总体充分，但可进一步扩展。

### 6. 论文的主要结论与发现

1. **理论贡献**：提出 RAM 策略，在完美预测下可捕获后见最优财富的常数比例（1/m），在对抗预测下仍不低于所有资产的几何均值（价值线）。
2. **合成预测实验**：当预测准确率略高于随机（53%），RAM 即显著优于所有基线（UP、EG、EGSI），且优势随准确率提高而指数级扩大。在完全随机（p=0.5）时，RAM 中位数与均值仍优于 UP。
3. **真实 ML 实验**：在 COVID-19 高波动期，RAM 在多数篮子中超越 EGSI；在近期平稳市场，RAM 即使在预测信号弱时（篮子 β 预测低于价值线 56%）仍保持与 EGSI 相当甚至略优。
4. **整体结论**：中等预测能力即可转化为实质性收益，且不牺牲最坏情况保证；RAM 为预测驱动投资提供了安全高效的框架。

### 7. 优点

- 理论保证强：同时提供最坏情况和最优情况下的有限界，且与预测误差显式耦合。
- 算法简洁高效：每轮 O(m log m)，适合大规模组合。
- 集成预测的方式新颖：仅需预测排序（而非数值），兼容多种 ML 模型。
- 实验设计全面：结合合成与真实预测，覆盖不同资产数量、市场状态和基准。
- 代码公开，可复现。

### 8. 不足与局限

- **未考虑交易成本**：每轮通过排列层完全再平衡，产生频繁交易，实际中交易成本不可忽略。论文仅在结论中提及作为未来工作。
- **数据集有限**：仅测试美股（NYSE 和 S&P 500），未覆盖其他市场或资产类别（如加密货币、商品、债券）。
- **仅使用排序预测**：未利用预测的幅度信息（如置信度或具体回报估计），可能限制潜在收益。
- **缺乏与最新深度学习方法比较**：如基于 LSTM、Transformer 的直接组合优化方法被排除在基准之外。
- **统计显著性未评估**：尽管有 1000 次蒙特卡洛模拟，但未提供置信区间或 P 值。
- **常数 1/m 的保守性**：当资产数 m 很大时，1/m 比例可能过低，实际中虽可超越但理论下界较弱。
- **理论最优性未证明**：论文未分析帕累托最优的 consistency–robustness 权衡，仅提供了一个工作点。

（完）
