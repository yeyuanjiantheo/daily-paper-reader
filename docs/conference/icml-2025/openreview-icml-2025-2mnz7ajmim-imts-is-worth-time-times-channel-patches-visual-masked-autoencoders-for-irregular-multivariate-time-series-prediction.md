---
title: "IMTS is Worth Time $\\times$ Channel Patches: Visual Masked Autoencoders for Irregular Multivariate Time Series Prediction"
title_zh: IMTS值得时间通道分块：不规则多变量时间序列预测的视觉掩码自编码器
authors: "Zhangyi Hu, Jiemin Wu, Hua XU, Mingqian Liao, Ninghui Feng, Bo Gao, Songning Lai, Yutao Yue"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=2mnZ7AjMim"
tags: ["query:qf"]
score: 6.0
evidence: 提出视觉掩码自编码器用于不规则多变量时间序列预测
tldr: 不规则多变量时间序列预测因缺失值而困难。本文借鉴视觉掩码自编码器，提出VIMTS框架，通过时间通道分块和掩码机制有效处理缺失数据，在多个基准上超越现有方法。该方法为金融时间序列中的不规则数据建模提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-2mnz7ajmim/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 819, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2mnz7ajmim/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 823, \"height\": 790, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2mnz7ajmim/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1765, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2mnz7ajmim/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1774, \"height\": 791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2mnz7ajmim/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1771, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2mnz7ajmim/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1773, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2mnz7ajmim/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1771, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2mnz7ajmim/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1772, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2mnz7ajmim/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1774, \"height\": 354, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-2mnz7ajmim/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1766, \"height\": 858, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2mnz7ajmim/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 884, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2mnz7ajmim/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1769, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2mnz7ajmim/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1769, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2mnz7ajmim/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1775, \"height\": 595, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2mnz7ajmim/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1639, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2mnz7ajmim/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 857, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2mnz7ajmim/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1764, \"height\": 329, \"label\": \"Table\"}]"
motivation: 现有方法难以从不规则多变量时间序列中提取可靠时间模式，受视觉MAE成功启发。
method: 提出VIMTS框架，将时间序列分块为类似图像形式，利用掩码自编码器建模。
result: 实验表明，VIMTS在多个现实不规则时间序列数据集上优于现有方法。
conclusion: 视觉MAE可有效迁移至不规则时间序列预测。
---

## Abstract
Irregular Multivariate Time Series (IMTS) forecasting is challenging due to the unaligned nature of multi-channel signals and the prevalence of extensive missing data. Existing methods struggle to capture reliable temporal patterns from such data due to significant missing values. While pre-trained foundation models show potential for addressing these challenges, they are typically designed for Regularly Sampled Time Series (RTS). Motivated by the visual Mask AutoEncoder's (MAE) powerful capability for modeling sparse multi-channel information and its success in RTS forecasting, we propose **VIMTS**, a framework adapting **V**isual MAE for **IMTS** forecasting. To mitigate the effect of missing values, VIMTS first processes IMTS along the timeline into feature patches at equal intervals. These patches are then complemented using learned cross-channel dependencies. Then it leverages visual MAE's capability in handling sparse multichannel data for patch reconstruction, followed by a coarse-to-fine technique to generate precise predictions from focused contexts. In addition, we integrate self-supervised learning for improved IMTS modeling by adapting the visual MAE to IMTS data. Extensive experiments demonstrate VIMTS's superior performance and few-shot capability, advancing the application of visual foundation models in more general time series tasks. Our code is available at https://github.com/WHU-HZY/VIMTS.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：不规则多变量时间序列（IMTS）预测面临两大挑战：多通道信号时间戳不对齐、大量缺失数据。现有方法如GCN和神经ODE难以捕捉可靠的时间模式，且计算成本高；而预训练基础模型（如视觉MAE）虽然擅长处理稀疏多通道数据，但主要针对规则采样时间序列（RTS），无法直接适用于IMTS。
- **整体含义**：本文提出将视觉MAE的能力迁移到IMTS预测，通过将IMTS转化为类似图像的时间×通道分块结构，利用自监督学习适应IMTS特性，实现高性能预测和少样本学习能力。

## 2. 方法论：核心思想与关键技术细节

- **核心思想**：将IMTS沿时间轴等间隔分块为特征补丁（patches），利用GCN学习跨通道依赖来补偿缺失信息，然后使用预训练视觉MAE对补丁序列进行重建，最后通过粗到细（coarse-to-fine）策略生成逐点预测。
- **关键技术细节**：
  - **Time × Channel Patchify**：将IMTS按统一时间窗口分块，每个补丁内使用Transformable Time-aware Convolutional Network（TTCN）提取特征，并加入掩码指示和通道嵌入。
  - **跨通道信息交互**：通过GCN学习动态邻接矩阵，利用混合嵌入（静态+动态）计算通道间依赖，对缺失补丁进行补偿。
  - **时间维重建**：将每个通道的补丁序列视为单通道“图像”，添加时间位置编码，输入MAE进行编码和解码重建。
  - **Patch2Point预测**：利用重建的补丁表示，结合查询时间戳的嵌入，通过MLP生成最终预测值，实现从粗粒度补丁到细粒度时间点的映射。
  - **两阶段训练策略**：
    - 阶段一（自监督学习）：随机掩码部分历史补丁，重建被掩码补丁对应的观测值。
    - 阶段二（监督微调）：对整个未来时间窗进行补丁重建，并基于补丁进行逐点预测。

## 3. 实验设计

- **数据集**：四个真实世界数据集，涵盖不同领域：
  - PhysioNet（医疗）、MIMIC（重症监护）、Human Activity（生物力学）、USHCN（气候科学）。
  - 缺失率分别为85.7%、96.7%、75.0%、77.9%，通道数分别为41、596、12、56。
- **Benchmark**：采用MSE和MAE作为评估指标，数据集划分为60%训练、20%验证、20%测试。
- **对比方法**：共20个基线模型，分为四类：
  - 多变量时间序列预测：DLinear、TimesNet、PatchTST、Crossformer、GraphWaveNet、MTGNN、StemGNN、CrossGNN、FourierGNN、VisionTS。
  - IMTS分类：GRU-D、SeFT、RainDrop、Warpformer。
  - IMTS插值：mTAND。
  - IMTS预测：Latent-ODE、CRU、Neural Flows、t-PatchGNN。

## 4. 资源与算力

- **GPU**：单个NVIDIA RTX 4090 GPU。
- **训练时间**：完整模型训练约87.8秒/epoch（Human Activity数据集，batch size=32）；推理时间约4.82毫秒/样本。
- **参数量**：总可训练参数约111.01M（其中MAE backbone占比最大，GCN约32.4k参数）。
- **未明确说明**：具体训练总epoch数未提及，但采用早停机制（验证损失15个epoch不下降则停止）。

## 5. 实验数量与充分性

- **实验组数**：
  - **主要性能对比**：在4个数据集上与20个基线模型对比，每个实验重复5次随机种子，报告均值±标准差。
  - **消融实验**：6种变体（去除预训练、去除自监督学习、同时去除、去除GCN、替换MAE为Transformer），并在4个数据集上评估。
  - **Patch2Point策略探索**：对比不同训练阶段使用/不使用粗到细预测。
  - **少样本学习**：在10%/20%/50%数据量下，对比完整VIMTS及其消融变体与t-PatchGNN。
  - **超参数敏感性**：对隐藏维度、补丁大小、掩码率、GCN层数、时间/特征嵌入维度进行系统扫描。
  - **微调策略探索**：比较全参数微调、冻结、偏置/注意力/MLP/归一化层微调等。
- **充分性评估**：实验设计全面，覆盖性能对比、组件有效性、少样本能力、计算成本、超参数鲁棒性，且均使用多次重复确保稳定性。但在大规模跨数据集零样本泛化方面未做测试。

## 6. 主要结论与发现

- VIMTS在四个数据集上均显著优于所有基线模型，包括当前最优的t-PatchGNN。
- 即使仅使用20%训练数据，VIMTS仍能匹配或超越其他基线在100%数据下的性能，展示出强大的少样本能力。
- 视觉MAE的预训练和自监督学习是性能的关键：去除任一组件均导致明显下降，同时去除则性能最差。
- GCN跨通道补偿对处理高缺失率数据至关重要（尤其MIMIC数据集96.7%缺失率）。
- 粗到细预测策略优于直接投影预测，能够聚焦相关时序上下文。
- 视觉基础模型（MAE）可通过适当适配有效迁移到IMTS预测任务，为更通用的时间序列预测开辟新方向。

## 7. 优点

- **方法论创新**：首次将视觉MAE成功应用于IMTS预测，提出时间×通道分块策略，解决了不规则性和缺失值问题。
- **高效少样本能力**：在低数据场景下性能优异，适用于实际中标注数据稀缺的场景。
- **模块化设计**：各组件（TTCN、GCN、MAE、粗到细预测）职责清晰，消融实验充分验证其必要性。
- **计算效率**：推理速度快（<5ms/样本），参数量适中，可单卡训练。
- **实验严谨**：5次重复随机种子、多数据集、多基线、全面消融、超参数扫描，确保结论可靠。

## 8. 不足与局限

- **可扩展性**：当前模型限于固定补丁大小和固定通道数，难以处理动态变化的通道数量或时间分辨率，缺乏真正零样本泛化能力。
- **未评估跨数据集迁移**：实验仅在单个数据集内训练和测试，未测试在一个数据集上预训练后迁移到另一个数据集的零样本/少样本性能。
- **算力消耗**：自监督学习阶段增加约40%训练时间，虽然可接受但对大规模预训练可能构成负担。
- **高缺失率极端情况**：虽然MIMIC缺失率96.7%表现良好，但未测试极端缺失（如>99%）下的鲁棒性。
- **缺乏与时间序列基础模型（如TimesFM、Chronos）的直接对比**：论文主要对比了视觉模型和传统方法，未包含近期专门的时间序列基础模型。

（完）
