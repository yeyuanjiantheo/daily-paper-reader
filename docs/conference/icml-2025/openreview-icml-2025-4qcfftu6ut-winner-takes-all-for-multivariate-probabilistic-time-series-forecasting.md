---
title: Winner-takes-all for Multivariate Probabilistic Time Series Forecasting
title_zh: 多变量概率时间序列预测的胜者全拿方法
authors: "Adrien Cortes, Remi Rehm, Victor Letzelter"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=4QcFfTu6UT"
tags: ["query:qf"]
score: 6.0
evidence: 使用胜者全拿损失进行多变量概率时间序列预测以生成多样化未来
tldr: 多变量时间序列预测需要生成多种可能未来。本文提出TimeMCL，将多选学习范式引入时间序列，采用多头网络和胜者全拿损失以鼓励预测多样性。在合成和真实数据上验证了其高效性和准确性，计算开销小。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-4qcfftu6ut/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 826, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4qcfftu6ut/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1768, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4qcfftu6ut/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1777, \"height\": 679, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4qcfftu6ut/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1770, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4qcfftu6ut/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 795, \"height\": 748, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4qcfftu6ut/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1765, \"height\": 1952, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4qcfftu6ut/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1739, \"height\": 1030, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4qcfftu6ut/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1737, \"height\": 1028, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-4qcfftu6ut/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1706, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4qcfftu6ut/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1281, \"height\": 148, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4qcfftu6ut/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4qcfftu6ut/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4qcfftu6ut/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1553, \"height\": 332, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4qcfftu6ut/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1765, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4qcfftu6ut/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1763, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4qcfftu6ut/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1761, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4qcfftu6ut/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1765, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4qcfftu6ut/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1591, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4qcfftu6ut/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1772, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4qcfftu6ut/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1765, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4qcfftu6ut/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 607, \"height\": 637, \"label\": \"Table\"}]"
motivation: 现有时间序列预测往往只给出单一预测，难以刻画不确定性。
method: 基于多选学习范式，设计多头网络，用胜者全拿损失训练以产生多样化预测。
result: 在合成和真实数据上，以轻量计算实现了有竞争力的预测性能。
conclusion: 多选学习框架能有效生成多样的时间序列未来场景。
---

## Abstract
We introduce $\texttt{TimeMCL}$, a method leveraging the Multiple Choice Learning (MCL) paradigm to forecast multiple plausible time series futures. Our approach employs a neural network with multiple heads and utilizes the Winner-Takes-All (WTA) loss to promote diversity among predictions. MCL has recently gained attention due to its simplicity and ability to address ill-posed and ambiguous tasks. We propose an adaptation of this framework for time-series forecasting, presenting it as an efficient method to predict diverse futures, which we relate to its implicit *quantization* objective. We provide insights into our approach using synthetic data and evaluate it on real-world time series, demonstrating its promising performance at a light computational cost.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：多变量概率时间序列预测是一个病态问题，由于输入信息不足以完全消除不确定性，需要生成多个“如果-那么”场景（即假设，hypotheses），以刻画未来条件分布的多模态特性。现有方法如参数化分布（DeepAR）依赖分布族假设，灵活性有限；而条件扩散模型（TimeGrad）计算成本高、推理慢，且在一个前向传播中难以保证假设的多样性。
- **研究背景**：近年来，多选学习（Multiple Choice Learning, MCL）范式在计算机视觉等模糊任务中通过 Winner-Takes-All（WTA）损失成功训练出多样化预测头。作者将其首次引入时间序列预测，旨在以极低计算代价获得一组有代表性、多样且平滑的未来轨迹，并将其视为对条件概率分布的一种**函数量化**（functional quantization）。

## 2. 论文提出的方法论

### 核心思想
- 采用**多头网络**：共享一个主干（基于 LSTM 的循环神经网络）处理历史序列，输出共享隐状态 $h_{t-1}$；每个头 $f^k_\theta$ 独立生成未来轨迹的一个假设（hypothesis）$\hat{x}^k_{t_0:T}$。
- **Winner-Takes-All（WTA）损失**：对于每个训练样本，计算每个头自身的负对数似然（以均方误差度量），只选择损失最小的“获胜者”头进行梯度回传，其他头的梯度被阻断。这强制不同头“竞争”以覆盖目标分布的不同区域，最终形成对轨迹空间的 Voronoi 剖分。
- **得分头**：额外增加 $K$ 个得分头 $\gamma^k_\theta$，预测每个假设成为“获胜者”的概率，通过二元交叉熵损失训练，防止某些头被过度自信或闲置。
- **总损失**：$L = L_{WTA} + \beta L_s$，其中 $\beta=0.5$。
- **推理**：一次前向传播即可得到 $K$ 个轨迹及其置信得分。可结合得分进行重采样或直接选取最优假设。

### 关键技术细节
- **隐式量化视角**：在 $L_2$ 损失下，WTA 训练等价于对条件分布 $p(x_{t_0:T} \mid x_{1:t_0-1})$ 进行**条件 Centroids Voronoi Tessellation**。Proposition 5.1 证明，最优解下每个头的预测等于其 Voronoi 单元内未来轨迹的条件均值，即：
  $$F^k_\theta(x_{1:t_0-1}) = \mathbb{E}[x_{t_0:T} \mid x_{t_0:T} \in \mathcal{X}^k(x_{1:t_0-1})]$$
  其中 $\mathcal{X}^k$ 是由该头“赢得的”轨迹集合。据此，预测趋于平滑（噪声被平均掉），且可解释为对条件分布的离散表示。
- **WTA 变体**：为缓解未充分训练的头，使用了 **Relaxed-WTA**（给非获胜头赋予小权重 $\varepsilon=0.1$）和 **Annealed MCL**（使用 softmin 分配，温度指数衰减从 $T_0=10$ 降至 $5\times10^{-4}$）。

## 3. 实验设计

### 数据集 / 场景
- **六大基准数据集**（取自 GluonTS）：Solar（太阳能输出，137维，小时，预测24步）、Electricity（电力消耗，370维，小时，24步）、Exchange（汇率，8维，日，30步）、Traffic（交通占用率，963维，小时，24步）、Taxi（出租车流量，1214维，30分钟，24步）、Wikipedia（页面浏览量，2000维，日，30步）。
- **加密货币数据集**：15个加密货币的每小时价格（对数收益率），训练/验证/测试时间区间跨2023-07至2025-03，预测步长24。
- **合成数据**：布朗运动、布朗桥、AR(5) 过程，用于验证量化解的接近最优性。

### Baseline 与对比方法
- **Baseline**：ETS（指数平滑）、DeepAR（高斯分布参数化）、TempFlow（条件归一化流）、TimeGrad（扩散模型）、Tactis2（基于 Transformer 的注意力 Copula 模型）。
- **对比指标**：
  - **Distortion**（量化误差，核心指标）：测试集上每个样本与其最近假设的欧氏距离均值。
  - **FLOPs & Run-time**：衡量推理计算成本。
  - **Total Variation（平滑度）**：相邻时间步预测差值的L2范数均值。
  - **RMSE & CRPS**：标准概率预测指标。

### 训练配置
- 共享 LSTM 主干（2层，40隐单元），预测头和得分头均为单线性层。
- 优化器：Adam，学习率 $10^{-3}$，200 epoch，每 epoch 30 个 batch（batchsize 200），随机窗口。
- 数据归一化：除 Tactis2 使用 Z-score 外，其余均采用逐维均值缩放。

## 4. 资源与算力

- 文中未明确说明使用的 GPU 型号、数量及总训练时间。
- 提及使用了 **IDRIS 的 HPC 资源**（分配编号 2024-AD011014345），并声明是在单个 NVIDIA GeForce RTX 2080 Ti 上测量推理时间（且确保为该节点唯一进程）。
- 根据实验设置（200 epoch，batch size 200，最多 2000 维序列），可推测训练需数小时至数天，但未给出具体数字。

## 5. 实验数量与充分性

### 实验数量
- 主要对比：6个数据集 × 4个训练种子 × 多种 baseline，生成 Distortion 等指标（Tables 1-3）。
- 消融实验：在 Solar 上针对不同假设数量 $K=1,2,3,4,5,8,16$ 比较方法性能（Table 4）。
- 合成数据：3个随机过程，定性/定量对比理论最优量化。
- 额外金融实验：加密货币数据集，对比多个 baseline 的 Distortion、TV、CRPS、RMSE、FLOPs（Table 12）。

### 充分性与公平性
- **充分**：涵盖多种数据维度、时间频率、预测长度；使用多个随机种子取平均；在相同骨干下比较（DeepAR、TimeGrad、TempFlow 共享 RNN 结构），并与 Transformer 类方法（Tactis2、Trf.TempFlow）保持独立对比。
- **公平**：所有基线使用官方或最佳超参数；TimeMCL 的 Relaxed 和 Annealed 变体均在同一框架下实现；评价指标标准化。
- **局限**：
  - CRPS 和 RMSE 上 TimeMCL 通常逊于 TimeGrad，说明其优化目标（Distortion）不一定直接对应于分布拟合的最优指标。
  - 种子数仅为 4，统计稳定性有限。
  - 未进行大规模的消融（如对骨干网络、损失权重 $\beta$、松弛系数 $\varepsilon$ 等的系统调优）。
  - 未在更长预测步或更高维度的数据上测试泛化性。

## 6. 论文的主要结论与发现

1. TimeMCL 通过 WTA 损失训练多头网络，能够**一次前向传播**生成多样化的未来轨迹，在 Distortion 指标上显著优于多数基线（如 DeepAR、TempFlow、TimeGrad 等），且接近甚至优于计算昂贵的 Tactis2 和 TimeGrad。
2. TimeMCL 的计算成本极低：FLOPs 和推理时间仅为 TimeGrad 的 1/300 左右，比 DeepAR 略高但仍低于其他生成式模型。
3. 理论证明 WTA 训练等价于**条件函数量化**，每个头预测其 Voronoi 单元内的条件均值，这一性质解释了解的分析平滑性（低 Total Variation）和可解释性。
4. 在合成数据上，TimeMCL 的预测与理论最优量化高度吻合。
5. 在加密货币等金融数据上，TimeMCL 同样在平滑性和多样性上表现出色，且能捕获稀有事件模式。

## 7. 优点

| 方面 | 亮点 |
|------|------|
| **方法创新** | 首次将 MCL 范式系统应用于时间序列预测，建立与函数量化的理论联系，给出了条件 centroids 的解析形式。 |
| **计算效率** | 一次前向传播即得 $K$ 个假设，推理极快（FLOPs 仅为扩散模型的 0.03%），适合实时场景。 |
| **输出可解释性** | 每个预测头代表一种“模式”，直接可解读；得分头提供置信度，便于决策。 |
| **多样性保证** | WTA 损失迫使不同头分占不同 Voronoi 区域，天然避免模式坍缩。 |
| **理论支撑** | 证明在 $L_2$ 损失下达到最优时，每个头为条件均值，这既解释了平滑性，也给出了收敛保证。 |
| **实验设计** | 在多个公开基准和合成数据上系统对比，使用了多种性能指标（Distortion、TV、FLOPs），既有定量也有可视化结果。 |

## 8. 不足与局限

| 不足 | 具体说明 |
|------|----------|
| **缩放器敏感** | 数据归一化策略（如均值缩放）可能导致假设偏向，尤其当时间序列值远离零时，影响头利用率。作者计划未来探索 Z-score 或 RevIN。 |
| **预设假设数量** | $K$ 必须在训练前固定，无法动态增减，且增加 $K$ 需要重新训练，缺乏灵活性。 |
| **部分头部可能未训练** | 即使使用 Relaxed/Annealed 变体，某些头仍可能被“冷落”，当模式分布不均衡时更明显。 |
| **分布拟合质量有限** | TimeMCL 在标准的概率指标（CRPS、RMSE）上不如 TimeGrad 和 Tactis2，说明量化目标与泛化概率分布之间仍存在差距。 |
| **实验可重复性细节不足** | 未明确披露训练所需的 GPU 类型、时长、具体能耗等；随机种子仅 4 个，可能不够稳定。 |
| **骨干单一** | 主要采用 LSTM 主干，未系统探索 Transformer 或其他架构的影响（仅 Trf.TempFlow 作为独立 baseline 出现）。 |
| **缺少超参数系统调优** | 对 $\beta$、$\varepsilon$、温度退火参数等仅凭经验设定，未报告敏感性分析。 |
| **应用限制** | 方法假设条件分布可用有限个点代表，在高度复杂或高维场景下（如 2000 维 Wikipedia）可能量化误差仍较高。 |

（完）
