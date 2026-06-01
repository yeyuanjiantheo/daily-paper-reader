---
title: "Not All Data are Good Labels: On the Self-supervised Labeling for Time Series Forecasting"
title_zh: 并非所有数据都是好标签：时间序列预测的自监督标注
authors: "Yuxuan Yang, Dalin Zhang, Yuxuan Liang, Hua Lu, Gang Chen, Huan Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=kQokjfoGjk"
tags: ["query:qf"]
score: 6.0
evidence: 时间序列预测的自监督标注方法
tldr: 现有时间序列预测模型过度依赖高质量数据且未能充分利用所有可用数据。本文提出了一种自监督标注方法，通过简单重构网络的中间结果作为伪标签，并引入自适应掩码的自我纠正机制和谱范数正则化，以提升任何预测器的泛化能力。该方法有效缓解了过拟合，在多个数据集上验证了其有效性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1411, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 656, \"height\": 303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 415, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 656, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 703, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 728, \"height\": 260, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 569, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 867, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1458, \"height\": 262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1449, \"height\": 270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1436, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1446, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1441, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 519, \"height\": 176, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 512, \"height\": 169, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 516, \"height\": 170, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 516, \"height\": 171, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1083, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1444, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1437, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 212, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kqokjfogjk/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 441, \"height\": 368, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-kqokjfogjk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kqokjfogjk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 717, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kqokjfogjk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 715, \"height\": 157, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kqokjfogjk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1444, \"height\": 131, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kqokjfogjk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1071, \"height\": 573, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kqokjfogjk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 494, \"height\": 196, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kqokjfogjk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1426, \"height\": 662, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kqokjfogjk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1427, \"height\": 1100, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kqokjfogjk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1426, \"height\": 1098, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kqokjfogjk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 839, \"height\": 764, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kqokjfogjk/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 842, \"height\": 766, \"label\": \"Table\"}]"
motivation: 现有时间序列预测模型过度依赖高质量数据，未能充分利用所有数据，导致泛化能力受限。
method: 提出自监督标注框架SCAM，利用重构网络的中间结果作为伪标签，并通过自适应掩码和谱范数正则化提升预测器泛化能力。
result: 在多个时间序列数据集上验证了该方法能显著提升预测精度和鲁棒性。
conclusion: 自监督标注是一种有效的提升时间序列预测模型泛化能力的策略。
---

## Abstract
Time Series Forecasting (TSF) is a crucial task in various domains, yet existing TSF models rely heavily on high-quality data and insufficiently exploit all available data. This paper explores a novel self-supervised approach to re-label time series datasets by inherently constructing candidate datasets. During the optimization of a simple reconstruction network, intermediates are used as pseudo labels in a self-supervised paradigm, improving generalization for any predictor. We introduce the Self-Correction with Adaptive Mask (SCAM), which discards overfitted components and selectively replaces them with pseudo labels generated from reconstructions. Additionally, we incorporate Spectral Norm Regularization (SNR) to further suppress overfitting from a loss landscape perspective. Our experiments on eleven real-world datasets demonstrate that SCAM consistently improves the performance of various backbone models. This work offers a new perspective on constructing datasets and enhancing the generalization of TSF models through self-supervised learning. The code is available at https://github.com/SuDIS-ZJU/SCAM.

---

## 论文详细总结（自动生成）

## 论文总结：Not All Data are Good Labels: On the Self-supervised Labeling for Time Series Forecasting

### 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现有时间序列预测（TSF）模型过度依赖高质量标注数据，且未能充分利用已有数据中的信息。原始数据中的噪声和异常导致标签质量低下，进而引发过拟合和泛化能力不足。
- **研究动机**：作者提出两个关键问题：(1) 能否缓解对高质量标签的依赖？(2) 能否更好地挖掘现有数据潜力？
- **整体含义**：本文通过自监督方式重新定义标签生成过程，利用一个简单重构网络的中间结果作为伪标签，并在监督学习中自适应地替换过拟合的原始标签，从而提升任意预测器的泛化能力。

### 2. 方法论

- **核心思想**：在训练预测器 \( f(\cdot;\theta) \) 的同时，利用一个辅助重构网络 \( g(\cdot;\phi) \) 对原始标签 \( y \) 进行重构得到 \( \tilde{y} \)。\( \tilde{y} \) 作为候选伪标签，与预测值 \( \hat{y} \) 及原始 \( y \) 共同构成联合损失。通过分析损失分解，识别出过拟合分量，并用自适应掩码舍弃它们。
- **关键技术细节**：
  - **重构网络 \( g(\cdot;\phi) \)**：由4个卷积层、跨层拼接（concatenation）和轻量级前馈网络（FFN）组成，用于生成不同保真度的候选数据集。
  - **联合训练损失**：初始为 \( L = \|\tilde{y}-y\| + \|\tilde{y}-\hat{y}\| \)，后推导出掩码形式：
    \[
    L = \underbrace{\|y-\hat{y}\| \odot M}_{\text{ masked Lsup}} + 2\left(\|\tilde{y}-\hat{y}\| \odot M_{<} + \|\tilde{y}-y\| \odot M_{<}\right) \odot M
    \]
    其中 \( M \) 由 \( m = (\tilde{y}-\hat{y})(\tilde{y}-y) > 0 \) 决定，\( M_{<} \) 指示 \( |\tilde{y}-\hat{y}| < |\tilde{y}-y| \)。
  - **自适应掩码（SCAM）**：通过掩码 \( M \) 将损失分解为过拟合部分（\( L_{\text{target}} \odot M \)）和非过拟合部分；训练时仅保留非过拟合部分，从而平滑损失景观。
  - **谱范数正则化（SNR）**：对 Transformer 等复杂模型的线性嵌入层和投影层施加谱范数正则化，代替梯度惩罚，抑制过拟合。
- **算法流程**（文字描述）：
  1. 初始化预测器 \( f \) 和重构网络 \( g \)。
  2. 每个mini-batch中，用 \( g \) 生成重构 \( \tilde{y} \)，用 \( f \) 生成预测 \( \hat{y} \)。
  3. 根据 \( m \) 计算自适应掩码 \( M \)。
  4. 计算带掩码的联合损失，仅更新不影响泛化的部分。
  5. 对 \( f \) 的线性层施加 SNR。
  6. 交替更新 \( f \) 和 \( g \) 直至收敛。
- **推理时**：仅使用更新后的 \( f \) 进行预测，无额外成本。

### 3. 实验设计

- **数据集**：7个主流基准数据集（ETTh1, ETTh2, ETTm1, ETTm2, Electricity, Traffic, Weather）以及4个大规模 PeMS 子集（PeMS03/04/07/08）。
- **Benchmark 设置**：
  - 预测长度 \( H \in \{96, 192, 336, 720\} \)，回溯长度固定为96。
  - 数据划分：ETT按0.6/0.2/0.2，Electricity/Traffic/Weather按0.7/0.1/0.2，PeMS按0.6/0.2/0.2。
- **对比方法**：
  - **骨干模型**：MLP（2层+RevIN）、CycleNet（MLP基，含周期建模）、PatchTST（通道独立Transformer）、iTransformer（通道依赖Transformer）。
  - **消融实验**：单独加SCAM、单独加SNR、两者都加。

### 4. 资源与算力

- **硬件**：2张 Nvidia RTX A5000 Ada（32GB VRAM）和2张 RTX A6000（48GB VRAM）。
- **训练时间**：在Electricity数据集上（batch size=32），MLP + SCAM 每迭代约30.451 ms，iTransformer + SCAM 约44.357 ms。总训练时长文中未明确报告，采用early stopping（patience=20）。
- **说明**：文中指出SCAM仅在训练阶段引入额外计算，推理无额外开销。

### 5. 实验数量与充分性

- **主实验**：4个骨干模型 × 7个主要数据集 × 4个预测长度 = 112组结果（表1），另有PeMS 4个数据集 × 4个长度（表7），总计约144组对比。
- **消融实验**：针对CycleNet和iTransformer，在5个数据集上测试SCAM和SNR的单独/联合效果（表2-3），共约40组。
- **附加分析**：掩码可视化、损失景观锐度分析、重构网络特性分析、SNR变体对比（图18）、效率对比（表6）。
- **充分性与公平性**：
  - 实验覆盖主流MLP和Transformer基座，数据集多样化（小规模噪声数据、大规模规律数据）。
  - 基准结果同时引用了原始论文和作者重现的结果（表8-9），并指出微小差异。
  - 消融实验验证了各组件贡献，补充分析解释了工作原理。
  - **不足**：未提供误差棒或统计显著性检验；PeMS数据集上存在复现差异（文中已讨论）。

### 6. 主要结论与发现

- SCAM 能一致提升所有骨干模型的性能，尤其在噪声大、样本少的ETT数据集上提升显著。
- SCAM 的主要贡献来自自适应掩码；SNR 作为补充正则化，对MLP基模型更有效。
- SCAM 通过重构网络实现分布对齐（通道间）和特征放大，从而增强训练标签质量。
- 从多实例学习（MIL）视角看，SCAM 自适应地处理不同噪声水平的数据点，避免过拟合。
- 该方法缩小了MLP基与Transformer基模型在困难数据集上的性能差距。

### 7. 优点

- **创新视角**：从“标签质量”入手，将自监督重构引入TSF，提出替代原始标签的新范式。
- **简洁有效**：重构网络设计轻量，自适应掩码自动识别过拟合分量，无需手动调参。
- **通用性强**：即插即用，适用于多种骨干模型（MLP、Transformer），且在11个数据集上验证。
- **理论支撑**：损失分解分析+损失景观锐度测量，为掩码设计提供理论依据。
- **可解释性**：通过掩码可视化（图8、15）直观展示模型如何区分可靠与不可靠标签。

### 8. 不足与局限

- **架构覆盖不全**：未测试Mamba、ModernTCN等新兴架构，也未验证在LLM-scale模型（如Chronos）上的效果。
- **实验细节缺失**：未报告误差棒或置信区间，统计显著性未说明；PeMS数据集因复现差异无法完全对齐原始结果。
- **资源限制**：文中指出受限于计算成本，未在更大规模模型上实验。
- **重构网络局限性**：当前g(·;ϕ)设计简单，可能存在更优结构，但作者承认并未探索（声明“not claimed superior”）。
- **潜在偏差**：自适应掩码可能在某些混沌数据集（如Weather）上效果较弱；掩码二值化可能导致信息丢失（作者提到未来计划探索更平滑策略）。

（完）
