---
title: Multi-Modal View Enhanced Large Vision Models for Long-Term Time Series Forecasting
title_zh: 多模态视图增强的大视觉模型用于长期时间序列预测
authors: "ChengAo Shen, Wenchao Yu, Ziming Zhao, Dongjin Song, Wei Cheng, Haifeng Chen, Jingchao Ni"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=PMdHrorFMF"
tags: ["query:qf"]
score: 5.0
evidence: 使用多模态视图和大视觉模型进行长期时间序列预测
tldr: 时间序列可转化为图像和文本等多模态形式。本文提出DMMV框架，利用趋势-季节分解和自适应残差分解，结合大视觉模型进行长期预测。该方法有效解决了LVM的周期归纳偏置，在长期预测任务中达到最优性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-pmdhrorfmf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1405, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pmdhrorfmf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 713, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pmdhrorfmf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1429, \"height\": 243, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pmdhrorfmf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 689, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pmdhrorfmf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1387, \"height\": 239, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pmdhrorfmf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1438, \"height\": 301, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pmdhrorfmf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1312, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pmdhrorfmf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1223, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pmdhrorfmf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1170, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pmdhrorfmf/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1420, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pmdhrorfmf/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1303, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pmdhrorfmf/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1298, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pmdhrorfmf/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1222, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pmdhrorfmf/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1082, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pmdhrorfmf/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1077, \"height\": 344, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-pmdhrorfmf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1419, \"height\": 1209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pmdhrorfmf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1313, \"height\": 558, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pmdhrorfmf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1221, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pmdhrorfmf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1040, \"height\": 2357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pmdhrorfmf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1269, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pmdhrorfmf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1293, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pmdhrorfmf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1309, \"height\": 1396, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pmdhrorfmf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1301, \"height\": 914, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pmdhrorfmf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 869, \"height\": 627, \"label\": \"Table\"}]"
motivation: 现有基于大视觉模型的预测器存在偏向周期预测的归纳偏置。
method: 提出DMMV框架，结合趋势-季节分解和自适应分解，将时间序列的多模态视图融入大视觉模型。
result: 在长期时间序列预测基准上，DMMV超越了现有基于LVM的方法。
conclusion: 多模态融合和分解策略能有效利用大视觉模型进行时间序列预测。
---

## Abstract
Time series, typically represented as numerical sequences, can also be transformed into images and texts, offering multi-modal views (MMVs) of the same underlying signal. These MMVs can reveal complementary patterns and enable the use of powerful pre-trained large models, such as large vision models (LVMs), for long-term time series forecasting (LTSF). However, as we identified in this work, the state-of-the-art (SOTA) LVM-based forecaster poses an inductive bias towards "forecasting periods". To harness this bias, we propose DMMV, a novel decomposition-based multi-modal view framework that leverages trend-seasonal decomposition and a novel backcast-residual based adaptive decomposition to integrate MMVs for LTSF. Comparative evaluations against 14 SOTA models across diverse datasets show that DMMV outperforms single-view and existing multi-modal baselines, achieving the best mean squared error (MSE) on 6 out of 8 benchmark datasets. The code for this paper is available at: https://github.com/D2I-Group/dmmv.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **长期时间序列预测（LTSF）** 在能源、医疗、交通等领域至关重要。传统方法多基于数值序列，但近年来研究者尝试将时间序列转化为图像（如TimesNet）或文本，以利用预训练的大模型（如LVMs、LLMs）增强预测能力。
- **现有方法的局限**：虽然基于大视觉模型（LVM）的预测器（如VisionTS）表现出色，但本文发现其存在**强烈的周期归纳偏置**：当图像分段的长度与时间序列周期匹配时预测准确，否则性能显著下降（见图3及附录D.2）。这导致模型过于关注周期性模式而忽视全局趋势。
- **核心动机**：如何利用多模态视图（数值、图像）的互补性，尤其是结合LVM对周期性的建模能力和数值模型对趋势的捕捉能力，设计一个能有效克服LVM偏置的预测框架。

## 2. 论文提出的方法论

### 核心思想
- 提出 **DMMV**（Decomposition-based Multi-Modal View）框架，将时间序列分解为**趋势**和**季节（周期）** 两部分，分别交由**数值预测器（fnum）** 和**视觉预测器（fvis，即LVM）** 处理，最后通过门控融合输出最终预测。
- 针对LVM的周期归纳偏置，设计两种分解策略：
  - **DMMV-S（简单分解）**：使用移动平均从原始序列中提取趋势（数值预测器）和季节（视觉预测器）。
  - **DMMV-A（自适应分解）**：通过**回测-残差机制**，让LVM先对输入图像进行全窗口重建（回测），利用其偏置提取周期性成分；原始序列减去回测结果得到趋势残差，再输入数值预测器。该机制自动将序列分解为与LVM对齐的周期部分和趋势部分。

### 关键技术细节
- **时间序列成像**：采用基于周期（通过FFT获取）的分段堆叠技术，将一元时间序列形成2D图像，再缩放至224×224×3以适应MAE等LVM的输入要求。
- **视觉预测器（fvis）**：默认使用MAE（Masked Autoencoder）作为LVM，仅微调其归一化层。
- **数值预测器（fnum）**：默认使用简单线性模型（也可选Transformer如PatchTST风格）。
- **融合方式**：轻量化门控机制 \( \hat{y} = g \circ \hat{y}_{season} + (1-g) \circ \hat{y}_{trend} \)，其中g由可学习标量通过sigmoid得到。
- **BCMASK策略**（仅DMMV-A）：高效的两步掩码策略，分别掩码图像的左半和右半，用另一半重建，仅需两次LVM前向即可完成全窗口回测。

### 训练流程（算法1）
1. **阶段1**：冻结fvis，单独训练fnum（预热约30个epoch）。
2. **阶段2**：解冻fvis的归一化层，联合微调两者（约5个epoch，早停）。

## 3. 实验设计

### 数据集与基准
- **8个基准数据集**：ETTh1/2、ETTm1/m2（电力变压器温度）、Weather（气象）、Illness（流感疾病）、Traffic（交通）、Electricity（电力）。涵盖不同采样频率、变量数、周期性强度。
- **预测长度**：Illness为{24,36,48,60}，其余为{96,192,336,720}。默认回看窗口T=336。
- **评估指标**：MSE和MAE。

### 对比方法（共16种）
- 多模态：Time-VLM
- 纯视觉：VisionTS
- 基于语言：GPT4TS、Time-LLM、CALF
- 基于数值：PatchTST、FEDformer、Autoformer、Stationary、ETSformer、Informer、DLinear、TimesNet、CycleNet

### 实验充分性分析
- **主实验**（表1）：所有方法在全部8个数据集上的完整结果，DMMV-A取得43个最优（#Wins 43）。
- **消融实验**（表2、表6、表7、表8）：对DMMV-A和DMMV-S分别进行了7种消融：数值预测器类型、LVM类型、融合方式、掩码策略、是否冻结fvis、是否使用分解等，覆盖所有设计选择。
- **鲁棒性分析**：变化回看窗口长度（图9、图15）、变化图像分段长度（图10）、标准偏差报告（表9）。
- **可视化分析**：分解结果对比（图7、图11、图12）、掩码效果对比（图8、图13、图14）。
- **计算资源**：明确说明使用8×NVIDIA RTX 6000 Ada GPU（48GB），PyTorch 2.5.1，CUDA 12.4。

## 4. 资源与算力

- **GPU型号及数量**：8×NVIDIA RTX 6000 Ada（48GB）。
- **训练时长**：未给出精确小时数；但描述了两阶段训练：阶段1最多50个epoch（早停耐心10），阶段2最多5个epoch（早停耐心2）。实际耗时取决于数据集大小。
- **评估**：实验在单台Linux服务器上完成，足够支撑全量实验。

## 5. 实验数量与充分性

- **实验组数**：主表包含8个数据集×4个预测长度×16种方法=512个性能数据点；消融实验覆盖4个代表性数据集，每个变体有4个预测长度；还进行了变化回看窗口（4种长度）、变化分段长度（6个比例）、标准偏差（5次运行）等。
- **充分性**：非常充分。
  - 对比基线全面：包括近期SOTA（CycleNet、Time-LLM、VisionTS等）。
  - 消融覆盖所有关键设计：fnum类型、fvis类型、门控vs求和、掩码策略、冻结策略、分解有无。
  - 补充了附录中的全部详细数值，可复现。
  - 数据划分采用标准协议（60/20/20或70/10/20），时间顺序分割，保证公平。

## 6. 论文的主要结论与发现

1. **DMMV-A显著超越所有单视图和多模态基线**，在6/8数据集上取得最佳平均MSE，综合排名第一（CD图图5）。
2. **自适应的回测-残基分解（DMMV-A）优于固定移动平均分解（DMMV-S）**，能更好提取纯周期信号供LVM建模。
3. **门控融合优于简单求和**，赋予模型自适应平衡两个视图输出的能力。
4. **BCMASK策略优于无掩码或随机掩码**，能有效提取周期性成分，提升趋势残差质量。
5. **数值预测器（哪怕简单线性）至关重要**：纯视觉模型VisionTS在弱周期数据集上表现不佳，而DMMV通过引入趋势建模弥补了该缺陷。
6. **LVM的周期归纳偏置可被利用而非对抗**：通过设计专用分解，LVM专注于周期模式，数值模型专注趋势，整体性能优于各自单独使用。

## 7. 优点

- **创新视角**：首次将LVMs在时间序列中的偏置作为设计切入点，提出面向MMV的分解框架，而非简单堆叠多模态特征。
- **技术优雅**：回测-残基机制仅用两次LVM前向完成全窗口周期提取，计算高效。
- **性能卓越**：在8个标准数据集上全面超越14种SOTA方法，包括同样使用LVMs的VisionTS和Time-VLM。
- **消融充分**：所有设计选择均有论证，结论可靠。
- **可解释性**：门控权重可揭示视觉和数值预测器的贡献占比（图6），分解结果可视化清晰。

## 8. 不足与局限

1. **对分段长度仍然敏感**：虽然DMMV-A比VisionTS更鲁棒（在ETTh1和Weather上），但在ETTm1和Illness上敏感度相当（附录D.2），门控机制可能让LVM的偏置部分传递。
2. **计算开销**：BCMASK需要三次LVM前向（一次预测、两次回测），在大规模多变量数据上仍显昂贵，作者也承认需要进一步优化效率。
3. **成像分辨率限制**：时间序列先压缩成小图像再放大至224×224，可能引入结构失真，尤其对短周期或高频信号不利。
4. **文本视图被排除**：实验表明文本视图（如Time-VLM中使用）收益有限且计算代价高，因此DMMV未包含。但未来某些场景下文本知识可能仍有价值（如引入天气预报文字）。
5. **实验覆盖**：虽然8个数据集涵盖多种场景，但未在极端长期（如预测长度>720）或超高频数据上验证；标准偏差报告仅基于5次运行，统计稳健性有限。
6. **假设**：需要已知或可计算的时间序列周期（通过FFT），对于非平稳或无明显周期的序列可能成像效果不佳。

（完）
