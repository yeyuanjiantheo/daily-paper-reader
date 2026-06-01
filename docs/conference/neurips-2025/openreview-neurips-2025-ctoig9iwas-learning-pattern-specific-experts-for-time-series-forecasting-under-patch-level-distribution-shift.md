---
title: Learning Pattern-Specific Experts for Time Series Forecasting Under Patch-level Distribution Shift
title_zh: 学习模式特定专家进行补丁级分布漂移下的时间序列预测
authors: "Yanru Sun, Zongxia Xie, Emadeldeen Eldele, Dongyue Chen, Qinghua Hu, Min Wu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=CtoIG9Iwas"
tags: ["query:qf"]
score: 5.0
evidence: 针对补丁级分布漂移的模式特定专家时间序列预测
tldr: 真实时间序列常表现出跨区段的异质模式演化，单一模型难以适应。本文提出TFPS，通过模式特定专家架构和动态选择机制处理补丁级分布漂移。在多个基准上验证了更准确的预测性能，可应用于金融时间序列在不同市场状态下的波动率预测。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ctoig9iwas/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1306, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ctoig9iwas/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ctoig9iwas/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ctoig9iwas/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1238, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ctoig9iwas/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 635, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ctoig9iwas/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 687, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ctoig9iwas/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1074, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ctoig9iwas/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1008, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ctoig9iwas/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 800, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ctoig9iwas/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 795, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ctoig9iwas/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 800, \"height\": 379, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctoig9iwas/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 1127, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctoig9iwas/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctoig9iwas/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 738, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctoig9iwas/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 682, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctoig9iwas/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1377, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctoig9iwas/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1423, \"height\": 782, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctoig9iwas/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1021, \"height\": 1000, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctoig9iwas/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1092, \"height\": 893, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctoig9iwas/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1093, \"height\": 833, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctoig9iwas/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 948, \"height\": 693, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctoig9iwas/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 950, \"height\": 693, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctoig9iwas/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1375, \"height\": 157, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctoig9iwas/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1019, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctoig9iwas/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1164, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctoig9iwas/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1020, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctoig9iwas/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1019, \"height\": 220, \"label\": \"Table\"}]"
motivation: 传统单模型难以捕获时间序列中区段间的异质模式演化。
method: 提出TFPS架构，利用模式特定专家和动态选择机制处理分布漂移。
result: 在标准数据集上显著提升预测准确性。
conclusion: 为时间序列预测提供处理模式漂移的有效方法。
---

## Abstract
Time series forecasting, which aims to predict future values based on historical data, has garnered significant attention due to its broad range of applications. However, real-world time series often exhibit heterogeneous pattern evolution across segments, such as seasonal variations, regime changes, or contextual shifts, making accurate forecasting challenging. Existing approaches, which typically train a single model to capture all these diverse patterns, often struggle with the pattern drifts between patches and may lead to poor generalization. To address these challenges, we propose TFPS, a novel architecture that leverages pattern-specific experts for more accurate and adaptable time series forecasting. TFPS employs a dual-domain encoder to capture both time-domain and frequency-domain features, enabling a more comprehensive understanding of temporal dynamics. It then performs subspace clustering to dynamically identify distinct patterns across data segments. Finally, these patterns are modeled by specialized experts, allowing the model to learn multiple predictive functions. Extensive experiments on real-world datasets demonstrate that TFPS outperforms state-of-the-art methods, particularly on datasets exhibiting significant distribution shifts. The data and code are available: https://github.com/syrGitHub/TFPS.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：真实世界的时间序列数据通常表现出跨区段的异质模式演化，例如季节性变化、制度转换（regime change）或上下文漂移（contextual shift）。这些变化导致不同时间补丁（patch）之间的分布存在显著差异，即**补丁级分布漂移**（patch-level distribution shift）。
- **现有局限**：主流方法（如PatchTST、DLinear等）通常采用**统一分布建模**（Uniform Distribution Modeling, UDM）策略，将所有补丁视为来自同一分布的样本，忽略了补丁间的结构异质性和时间演变，难以泛化到分布漂移场景。
- **研究动机**：需要一种能够动态识别不同模式并为其分配专门预测函数的架构，从而更准确地适应非平稳时间序列中的概念漂移。

## 2. 论文提出的方法论

### 核心思想
- 提出 **TFPS**（Time-Frequency Pattern-Specific）架构，通过**双域编码**、**子空间聚类模式识别**和**模式专家混合**三个核心组件，实现对补丁级分布漂移的专门化建模。

### 关键技术细节
1. **双域编码器（Dual-Domain Encoder, DDE）**：
   - **时域分支**：基于补丁的Transformer编码器，利用自注意力捕获全局趋势特征，输出时域特征 \( z_t \in \mathbb{R}^{C \times N \times D} \)。
   - **频域分支**：使用2D快速傅里叶变换（FFT）替换自注意力子层，捕获周期性模式和频谱特征，输出频域特征 \( z_f \in \mathbb{R}^{C \times N \times D} \)。
   - 双域信息互补，提供更全面的时间动态理解。

2. **模式识别器（Pattern Identifier, PI）**：
   - 基于**子空间聚类**，将每个补丁的嵌入表示 \( z \) 与可学习的子空间基 \( \mathbf{D} = [\mathbf{D}^{(1)},\dots,\mathbf{D}^{(K)}] \) 进行相似度计算。
   - **子空间亲和度**（subspace affinity）计算：\( s_{ij} = \frac{\|z_i^\top \mathbf{D}^{(j)}\|_F^2 + \eta d}{\sum_j (\|z_i^\top \mathbf{D}^{(j)}\|_F^2 + \eta d)} \)。
   - **细化亲和度**：\( \hat{s}_{ij} = \frac{s_{ij}^2 / \sum_i s_{ij}}{\sum_j (s_{ij}^2 / \sum_i s_{ij})} \) 以增强高置信度分配。
   - 聚类损失为KL散度：\( \mathcal{L}_{\text{sub}} = \text{KL}(\hat{\mathbf{S}} \| \mathbf{S}) \)。
   - 加入正则化项 \( \mathcal{R} \) 确保子空间基的正交性和差异度。
   - 总聚类损失：\( \mathcal{L}_{\text{PI}} = \mathcal{R} + \beta \mathcal{L}_{\text{sub}} \)。

3. **模式专家混合（Mixture of Pattern Experts, MoPE）**：
   - 设专家数 \( K \)，每个专家为两层MLP（含ReLU）。
   - 门控网络：基于细化亲和度 \( \hat{s} \) 进行Top-K选择，生成门控权重 \( G(s) = \text{Softmax}(\text{TopK}(s)) \)。
   - 最终输出：\( h = \sum_{k=1}^K G(s)_k E_k(z) \)。
   - 时域和频域输出 \( h_t, h_f \) 拼接后通过线性层得到预测 \( \hat{Y} \in \mathbb{R}^{H \times C} \)。

### 损失函数
- 总损失：\( \mathcal{L} = \mathcal{L}_{\text{MSE}} + \mathcal{L}_{\text{PI}}^t + \mathcal{L}_{\text{PI}}^f \)，其中 \( \mathcal{L}_{\text{MSE}} \) 为预测值与真值的均方误差。

### 算法流程（文字描述）
1. 输入时间序列 \( X \in \mathbb{R}^{L \times C} \)，进行补丁分割并添加位置编码。
2. 通过时域Transformer编码器得到时域特征 \( z_t \)；通过频域FFT编码器得到频域特征 \( z_f \)。
3. 分别计算时域和频域的子空间亲和度 \( s_t, s_f \)，并细化得到 \( \hat{s}_t, \hat{s}_f \)。
4. 利用门控网络选择Top-K专家，分别对 \( z_t \) 和 \( z_f \) 进行专家加权聚合，得到 \( h_t \) 和 \( h_f \)。
5. 拼接后线性投影得到预测结果。

## 3. 实验设计

### 数据集与场景
- **9个真实多变量时间序列数据集**：ETTh1、ETTh2、ETTm1、ETTm2、Exchange、Weather、Electricity、Traffic、ILI。
- **预测长度**：除ILI为24/36/48/60外，其余均为96/192/336/720。
- **输入长度**：默认96（ILI为104），超参数搜索时也考察了192/336/512。

### Benchmark与对比方法
- **时间域方法**：PatchTST、DLinear、TimesNet、iTransformer
- **频域方法**：FEDformer、FITS
- **时频域方法**：TFDNet-IK、TSLANet
- **基础模型**：AutoTimes、Moment、Timer
- **归一化方法**：SIN、SAN、Dish-TS、RevIN（与DLinear/FEDformer结合）
- **MoE方法**：MoLE、MoU、KAN4TSF
- **分布漂移方法**：Koopa、SOLID、OneNet
- 所有基线均使用官方代码重新运行，确保公平。

### 评价指标
- 均方误差（MSE）和平均绝对误差（MAE），数值越低越好。
- 改进百分比（IMP）：相对于所有基线平均MSE的改善比例。

## 4. 资源与算力

- **GPU**：单张 NVIDIA RTX 3090（24GB显存）。
- **实现框架**：PyTorch。
- **训练时长**：论文未明确给出具体训练时长，但在附录I中提供了推理时间对比（表12），例如TFPS在ETTh1（H=192）上平均推理时间6.114ms，GPU内存9.643MB。
- **超参数搜索**：使用网格搜索优化学习率、时域专家数 \( K_t \) 和频域专家数 \( K_f \)。

## 5. 实验数量与充分性

- **主实验**：在72个（9数据集×8预测长度）设置中，TFPS获得57次第一，覆盖所有数据集。
- **消融实验**：
  - 组件消融（表2）：比较完整模型、替换PI为线性层、仅使用编码器等，在ETTh1/ETTh2上验证每部分有效性。
  - 双域重要性消融（表2）：分别去除时域或频域分支。
  - 正则项消融（表15）：移除R1或R2。
  - PI消融（表14）：仅时域PI、仅频域PI、无PI。
  - 专家数量实验（图6/图7）：变化 \( K_t \) 和 \( K_f \)（1,2,4,8）。
  - 替换MoPE为多输出预测器或注意力层（表16）。
- **对比范围**：包含当前SOTA方法、基础模型、归一化方法、MoE方法、分布漂移方法，共十余种基线。
- **参数敏感性**（图11）：对超参数α和β进行网格搜索分析。
- **可视化分析**：Wasserstein距离热图、t-SNE嵌入、专家分配分布、预测曲线对比等。
- **公平性**：所有基线均使用官方代码重新运行；基础模型搜索最优输入长度。

**评价**：实验设计非常充分，覆盖主流基准，消融分析全面，可视化佐证方法可解释性，结论客观可靠。

## 6. 论文的主要结论与发现

1. TFPS在9个数据集、72个设置中57次取得第一，平均MSE相比时间域方法提升9.5%，相比频域方法提升16.9%，相比时频域方法提升5.2%。
2. 在分布漂移严重的场景（如Weather、Electicity、ILI）中提升尤为显著，表明模式专家设计有效处理概念漂移。
3. 双域编码互补：时域捕获趋势，频域捕获周期性，共同提升鲁棒性。
4. 子空间聚类（PI）能动态划分不同模式，且比简单线性层更好地区分补丁间分布差异。
5. 专家数量需与数据漂移程度匹配：漂移越严重（如Weather，Wasserstein距离大），所需专家数越多。
6. 可视化显示不同专家自发专业化（如Expert0专注下降趋势，Expert4专注抛物线趋势），提供可解释性。

## 7. 优点

- **创新性**：首次将子空间聚类与专家混合结合，专门应对补丁级分布漂移，突破统一建模局限。
- **技术完整性**：双域编码、聚类损失、Top-K专家选择及正则化项设计环环相扣，逻辑自洽。
- **实验充分性**：多种对比、消融、敏感性、可视化全覆盖，且重新运行所有基线代码确保公平。
- **可解释性**：专家分配可视化揭示了可理解的模式（如下降、抛物线），有助于实际应用诊断。
- **实用性**：代码开源，单GPU即可训练，推理速度和内存均优于部分复杂模型（如FEDformer）。

## 8. 不足与局限

- **补丁长度选择**：当前采用启发式固定补丁长度，无法处理不可分长度或多周期特征，缺乏自动选择机制。
- **新模式适应**：方法假设模式库在训练时覆盖所有可能，但真实世界可能出现前所未见的模式（如新流行病爆发），此时模型需要在线扩展能力，论文未涉及。
- **计算成本**：虽在单GPU上可训练，但相比线性模型（如DLinear）仍需更多资源，且专家数量需要网格搜索调优。
- **实验覆盖**：虽然数据集多样，但均为公开基准，缺少对极端长序列、极高维度（如金融市场微观数据）的验证。
- **潜在偏差风险**：专家分配基于聚类，若初始聚类质量不佳可能影响后续训练；子空间基的初始化（随机高斯）可能带来一定方差。

（完）
