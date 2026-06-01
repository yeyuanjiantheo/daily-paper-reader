---
title: Lightweight Online Adaption for Time Series Foundation Model Forecasts
title_zh: 时间序列基础模型预测的轻量级在线自适应
authors: "Thomas L Lee, William Toner, Rajkarn Singh, Artjom Joosen, Martin Asenov"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=gAxYbvoOQz"
tags: ["query:qf"]
score: 6.0
evidence: 时间序列基础模型的轻量级在线自适应方法
tldr: 现有时间序列基础模型在部署后无法适应新数据，导致预测偏差。本文提出ELF，一种轻量级在线自适应机制，利用新到达数据的反馈调整预测。ELF包括学习当前数据分布的预测器和自适应权重。在多个基准数据集上，该方法显著提升了基础模型的预测性能，且计算成本极低。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 869, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1783, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 850, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 838, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 877, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 855, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 855, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 863, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1766, \"height\": 1319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1756, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gaxybvooqz/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1758, \"height\": 531, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1529, \"height\": 1524, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1716, \"height\": 603, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1763, \"height\": 869, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1762, \"height\": 1387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 924, \"height\": 665, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1613, \"height\": 637, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1395, \"height\": 1518, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1007, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 959, \"height\": 723, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 816, \"height\": 715, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1689, \"height\": 924, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1784, \"height\": 924, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 908, \"height\": 1446, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gaxybvooqz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1528, \"height\": 1525, \"label\": \"Table\"}]"
motivation: 基础模型在部署后无法适应新数据特性，导致预测精度下降。
method: 提出ELF机制，包含ELF预测器学习当前数据分布，以及自适应权重调整基础模型输出。
result: 在多个时间序列数据集上，ELF显著提升基础模型预测精度，且计算开销小。
conclusion: 轻量级在线自适应能有效提升时间序列基础模型的部署性能。
---

## Abstract
Foundation models (FMs) have emerged as a promising approach for time series forecasting. While effective, FMs typically remain fixed during deployment due to the high computational costs of learning them online. Consequently, deployed FMs fail to adapt their forecasts to current data characteristics, despite the availability of online feedback from newly arriving data. This raises the question of whether FM performance can be enhanced by the *efficient* usage of this feedback. We propose *ELF* to answer this question. ELF is a lightweight mechanism for the online adaption of FM forecasts in response to online feedback. ELF consists of two parts: **a)** the *ELF-Forecaster* which is used to learn the current data distribution; and **b)** the *ELF-Weighter* which is used to combine the forecasts of the FM and the ELF-Forecaster. We evaluate the performance of ELF in conjunction with several recent FMs across a suite of standard time series datasets. In *all* of our experiments we find that using ELF improves performance. This work demonstrates how efficient usage of online feedback can be used to improve FM forecasts.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

时间序列基础模型（Foundation Models, FMs）在零样本预测中表现出色，但在部署后通常保持固定，无法适应新到达数据中可能发生的分布偏移。尽管在线反馈（新数据的真实值）持续可用，但直接微调或重新训练基础模型的计算成本过高（尤其在CPU环境），且易出现灾难性遗忘。因此，如何在计算受限的部署场景下高效利用在线反馈来提升基础模型的预测性能，成为关键问题。

本文提出 **ELF**（Ensembling with online Linear Forecaster）——一种轻量级在线自适应机制，能够让固定的基础模型在部署时通过在线反馈动态调整其预测，从而在不修改基础模型参数的前提下提升预测精度。

### 2. 论文提出的方法论：核心思想、关键技术细节

**核心思想**：ELF由两个模块组成：
- **ELF-Forecaster**：一个轻量级线性预测器，在频域中建模，通过Woodbury矩阵恒等式实现高效在线更新。
- **ELF-Weighter**：一个动态加权器，结合快速和慢速指数加权，将基础模型的预测与ELF-Forecaster的预测进行加权融合，权重根据近期和全局损失自适应调整。

**关键技术细节**：
1. **ELF-Forecaster**：
   - 输入上下文向量 \(x \in \mathbb{R}^L\)，先进行离散傅里叶变换（DFT），丢弃高频分量（保留比例 \(\alpha=0.9\)），降低维度至约 \(\alpha L\)。
   - 通过复权重矩阵 \(W\) 进行线性映射，输出压缩后的频域预测，再经逆实傅里叶变换得到时域预测 \(\hat{y} \in \mathbb{R}^H\)。
   - 参数 \(W\) 通过最小化均方误差（MSE）在闭环形式下求解：\(W = (\tilde{X}^*\tilde{X} + \lambda I)^{-1} \tilde{X}^* \tilde{Y}\)。
   - 利用Woodbury矩阵恒等式实现低秩更新（每次更新仅需逆一个 \(M \times M\) 矩阵，\(M\) 为批大小，通常200），避免存储全部历史数据。
   - 采用在线标准差缩放（Welford算法）处理数值稳定性。

2. **ELF-Weighter**：
   - 慢速加权器：使用所有历史损失进行指数加权，权重 \(w^\text{slow}_\tau\) 更新规则为 \(w^\text{slow}_\tau = \frac{w^\text{slow}_{\tau-1} e^{-\eta \ell_{\tau,1}}}{w^\text{slow}_{\tau-1} e^{-\eta \ell_{\tau,1}} + (1-w^\text{slow}_{\tau-1}) e^{-\eta \ell_{\tau,2}}}\)。
   - 快速加权器：仅使用最近 \(B=5\) 个时间步的损失进行指数加权，权重 \(w^\text{fast}_\tau\)。
   - 合并加权器：再使用一个指数加权器 \(\beta^\text{merge}_\tau\) 融合快速和慢速权重：\(w_\tau = \beta^\text{merge}_\tau w^\text{fast}_\tau + (1-\beta^\text{merge}_\tau) w^\text{slow}_\tau\)。
   - 最终预测：\(\hat{y}_t = w_\tau \hat{y}_{t,\text{FM}} + (1-w_\tau) \hat{y}_{t,\text{EF}}\)。

**算法流程**：每 \(M=200\) 个时间步作为一个更新步，先计算该批次内FM和ELF-Forecaster的损失，更新快速/慢速/合并权重，再根据新权重生成后续预测。

### 3. 实验设计：数据集、基准、对比方法

**数据集**：共10个标准时间序列数据集（ETTh1, ETTh2, ETTm1, ETTm2, Weather, Traffic, ECL, Solar, US Weather）及3个高频秒级数据集（Wind-PerSec, Solar-PerSec, Cloud-PerSec）。预测长度 \(H \in \{30, 96, 336\}\)，上下文长度 \(L=520\)。

**基础模型**：Chronos (tiny), TTM (rev2), TimesFM, Moirai (small), VisionTS。所有模型以零样本方式使用。

**对比方法**：
- 不加ELF的原始FM（零样本）。
- 其他在线自适应方法：TAFAS（基于门控校准）、FSNet（改进的TCN）、OneNet（在线集成）、OneNet-TTM（用TTM替代交叉时间模型），以及直接在线微调TTM。
- 消融实验对比了ELF内部变体（仅快速/仅慢速加权器、Hedge加权、无加权平均、不同预测器如OGD、FITS、FSNet、残差预测等）。

**指标**：主要使用MASE（Mean Absolute Scaled Error），辅以RMSSE（附录C.12）。MASE能跨尺度比较，适合滚动窗口设置。

### 4. 资源与算力

论文未提及基础模型预训练所用的GPU型号、数量和时长（因为这些模型是公开的预训练模型）。实验部分明确说明：
- ELF本身仅运行在2个Intel Xeon Platinum 8168 CPU上，每次更新步（200个时间步）平均仅需0.38秒。
- 对比方法（TAFAS、FSNet、OneNet）同样在CPU上测试，但耗时分别为3.76秒、23.69秒、43.12秒（每更新步）。
- 在线微调TTM需要911.52秒每更新步（同样2 CPU），比ELF慢2506倍。

因此论文聚焦于部署阶段的**计算效率**，未提及GPU训练资源。

### 5. 实验数量与充分性

- **主实验**：表1覆盖5种FM × 10个数据集 × 3个预测长度 = 150个组合，均显示ELF提升性能（绿色数字）。
- **对比其他在线方法**：表2在9个数据集上对比TAFAS、OneNet、FSNet等，每个对比均重复3个预测长度，共27组结果。
- **消融实验**：
  - 更新频率（C.6）：改变 \(M\) 值，显示更频繁更新带来更好性能。
  - 频率丢弃比例（C.8）：在4个数据集上测试不同 \(\alpha\)，验证丢弃10-20%频率几乎不影响性能。
  - 不同预测器替代（C.9）：比较OGD、FITS、FSNet、残差预测，共5种FM × 3个预测长度 × 5种替代 = 75组。
  - 加权器消融（C.10）：比较仅快速、仅慢速、Hedge、无加权平均，共5FM × 3预测长度 × 5变体 = 75组。
  - 计算效率分析（C.7）：分别测试Woodbury加速和频率丢弃加速。
  - 附加数据集（C.1）：3个秒级数据集共45组结果。
  - 与单次微调对比（C.4）和同时微调+ELF对比（C.5）。
- 整体实验覆盖全面，消融充分，结果一致支持结论。在公平性方面，所有对比方法均使用相同滚动窗口设置，且ELF超参数固定不调，对比方法尽量采用原论文最佳设置（如OneNet等采用更频繁的每步更新以最大化性能）。

### 6. 论文的主要结论与发现

- **ELF在所有实验中都提升了基础模型的预测性能**：表1中所有150个实验组合均得到改善，平均MASE降低约5-10%，尤其在VisionTS上平均提升超10%。
- **计算效率极高**：每次更新仅需0.38秒（2 CPU），比现有在线方法快10倍以上，比在线微调快2506倍。
- **自适应加权是有效的**：慢速和快速加权器结合比单独使用更好；无加权平均或Hedge效果差。
- **在线学习的重要性**：ELF-Forecaster能够学习数据集特有的模式（如周末流量下降、云请求峰值），而基础模型可能忽略这些特征。
- **对高频数据同样有效**：在秒级数据集上性能提升依然一致。

### 7. 优点

- **轻量级与模型无关**：ELF不修改基础模型参数，可即插即用到任何时间序列FM，且仅需CPU即可运行。
- **理论支持**：指数加权融合具有遗憾界理论保证（Theorem 4.1）。
- **设计巧妙**：利用频域压缩和Woodbury更新，使得线性模型可在在线场景下高效训练，避免了深度学习在线更新中的遗忘和塑性损失问题。
- **消融全面**：对每个组件均进行了详细的消融分析，验证其必要性。
- **实验客观**：所有超参数固定，对比方法按原论文设置，结果鲁棒。

### 8. 不足与局限

- **假设基础模型本身不变**：未考虑与基础模型在线微调结合的可能性（附录C.5表明同时微调+ELF在部分数据集上略好，但计算成本高）。对于一些需要深度适应的场景，仅调整预测可能不够。
- **仅适用于滚动窗口预测**：设定为每步一个时间点前进，不适用于其他预测模式（如多步一次性预测或非时序场景）。
- **频域丢弃比例需预设**：α=0.9是固定值，不同数据集可能最优值不同，但未进行超参数搜索（虽然消融显示对性能影响小）。
- **实验未覆盖所有数据集**：例如TimesFM在Traffic和ECL上因预训练而排除，但未提供替代数据集。
- **对比方法中TAFAS的适配不完整**：由于GPU内存限制，部分FM只用了输出门控模块，可能影响其最佳性能。
- **缺乏真实部署场景验证**：所有实验基于离线回放（rolling window），但实际在线系统可能存在延迟、资源争夺等因素未考虑。
- **对极端分布偏移的适应性未深入分析**：虽然权重调整能快速响应，但未专门设计概念漂移检测机制。

（完）
