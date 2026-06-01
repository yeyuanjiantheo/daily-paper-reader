---
title: "Enhancing Time Series Forecasting through Selective Representation Spaces: A Patch Perspective"
title_zh: 通过选择性表示空间增强时间序列预测：一种分块视角
authors: "Xingjian Wu, Xiangfei Qiu, Hanyin Cheng, Zhengyu Li, Jilin Hu, Chenjuan Guo, Bin Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=BirE0jYKt0"
tags: ["query:qf"]
score: 7.0
evidence: 选择性分块用于时间序列预测表示
tldr: 现有时间序列分块技术采用固定相邻分块，导致表示空间有限。本文提出选择性表示空间（SRS），通过可学习的选择性分块从序列中灵活选取信息量最大的片段，构建更丰富的表示。实验表明，SRS在长期预测任务上优于固定分块方法，提升了模型表达能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-bire0jykt0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 724, \"height\": 785, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bire0jykt0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bire0jykt0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bire0jykt0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bire0jykt0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1449, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bire0jykt0/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1450, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bire0jykt0/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1440, \"height\": 505, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-bire0jykt0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bire0jykt0/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1451, \"height\": 479, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bire0jykt0/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 735, \"height\": 506, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bire0jykt0/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 730, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bire0jykt0/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 703, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bire0jykt0/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 706, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bire0jykt0/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1451, \"height\": 845, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bire0jykt0/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1449, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bire0jykt0/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1447, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bire0jykt0/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1449, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bire0jykt0/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1451, \"height\": 757, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bire0jykt0/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1452, \"height\": 730, \"label\": \"Table\"}]"
motivation: 固定分块导致表示空间受限，难以充分捕捉时序语义。
method: 提出可学习的选择性分块和表示空间构建模块。
result: 在多个长期预测数据集上取得改进，验证了选择性表示的有效性。
conclusion: 为时序分块技术提供了更灵活的表达方式。
---

## Abstract
Time Series Forecasting has made significant progress with the help of Patching technique, which partitions time series into multiple patches to effectively retain contextual semantic information into a representation space beneficial for modeling long-term dependencies. However, conventional patching partitions a time series into adjacent patches, which causes a fixed representation space, thus resulting in insufficiently expressful representations. In this paper, we pioneer the exploration of constructing a selective representation space to flexibly include the most informative patches for forecasting. Specifically, we propose the Selective Representation Space (SRS) module, which utilizes the learnable Selective Patching and Dynamic Reassembly techniques to adaptively select and shuffle the patches from the contextual time series, aiming at fully exploiting the information of contextual time series to enhance the forecasting performance of patch-based models. To demonstrate the effectiveness of SRS module, we propose a simple yet effective SRSNet consisting of SRS and an MLP head, which achieves state-of-the-art performance on real-world datasets from multiple domains. Furthermore, as a novel plug-and-play module, SRS can also enhance the performance of existing patch-based models. The resources are available at https://github.com/decisionintelligence/SRSNet.

---

## 论文详细总结（自动生成）

# 论文总结：Enhancing Time Series Forecasting through Selective Representation Spaces: A Patch Perspective

## 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：现有基于分块（Patching）技术的时间序列预测方法（如PatchTST、Crossformer等）采用固定的相邻分块（adjacent patching），即使用固定步长将上下文时间序列均匀切分为若干子序列块。这种固定表示空间假设所有对预测有用的信息在上下文时间序列中均匀分布，但在实际场景中，由于周期变化、时间偏移、异常扰动等现象，均匀分块可能破坏周期语义、包含有害信息（如异常值或偏移过程），导致表示空间表达能力不足，限制预测性能。
- **研究动机**：受此启发，作者提出构建**选择性表示空间（Selective Representation Space, SRS）**，允许模型自适应地从所有候选补丁中选取最相关的补丁，并灵活排序，从而更充分地利用上下文时间序列中的信息，提升预测精度。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：SRS模块作为即插即用组件，可嵌入现有基于分块的模型中。它通过两个可学习的操作——**选择性分块（Selective Patching）**和**动态重组（Dynamic Reassembly）**——在补丁层面自适应地构建表示空间，再通过**自适应融合（Adaptive Fusion）**将传统相邻分块和SRS分块的嵌入结合，最后加上位置编码输入后续主干网络。
- **关键技术细节**：
  - **选择性分块**：以步长为1扫描上下文时间序列，获取所有潜在补丁（共K个）。用MLP评分器（Scorer_s）为每个补丁生成n个采样分数（允许重复选择），通过argmax选出分数最高的n个补丁。为解决argmax不可导问题，采用“梯度硬连接”技巧：将最大分数除以其自身（detach后），使得梯度可通过分数流向评分器。
  - **动态重组**：对选出的n个补丁，用另一个MLP评分器（Scorer_r）为每个补丁生成一个排序分数，按分数降序排序，同样利用梯度硬连接保持可导性。
  - **自适应融合**：对传统相邻分块的嵌入Ec和SRS分块的嵌入Es，通过可学习参数α进行凸组合：Ẽ = α⊙Ec + (1-α)⊙Es，使两者互补。
  - 最后添加位置编码得到最终表示E，输入任意基于分块的主干网络（如MLP、Transformer等）。
- **整体模型SRSNet**：将SRS模块与简单的MLP头（≤2层）组合，先flatten嵌入，再通过MLP预测未来L步。

## 3. 实验设计
- **数据集**：8个真实世界基准数据集，涵盖电力、天气、交通、太阳能等领域：ETTh1、ETTh2、ETTm1、ETTm2（电力变压器）、Weather、Electricity、Solar、Traffic。时间粒度从15分钟到1小时不等，通道数从7到862，序列长度范围广。
- **预测设置**：采用4种预测视界F∈{96,192,336,720}；回溯窗口大小在{96,336,512}中选择最优结果。
- **评价指标**：MSE和MAE。
- **对比方法**：共10种SOTA方法，包括：
  - Transformer类：FEDformer、Non-stationary Transformer（Stationary）、Crossformer、PatchTST、iTransformer、TimeMixer
  - CNN/MLP类：TimesNet、DLinear、Amplifier、TimeKAN
- **实验充分性**：报告了所有数据集和视界的详细结果，并标注了最佳和第二佳；提供了标准偏差（5个随机种子）；进行了全面的消融实验和插件实验。

## 4. 资源与算力
- 论文中**未明确说明**训练使用的具体GPU型号、数量及总训练时长。只在实验设置中提到：“所有SRSNet实验使用PyTorch 3.8，在NVIDIA Tesla-A800 GPU上执行”以及“初始batch size设为64，遇到OOM时减半（最小8）”。没有给出完整的算力消耗统计。

## 5. 实验数量与充分性评价
- **实验组数**：主实验结果（表2/表8）涵盖8个数据集×4个视界×10+种方法，约320+个结果。消融实验包括：
  - 关键组件消融（表4/表9-10）：在4个数据集上逐项去除选择性分块、动态重组、自适应融合。
  - 插件实验（表3/表11-12）：将SRS分别集成到MLP、PatchTST、Crossformer、PatchMLP、xPatch中，验证普适性。
  - 效率分析（表5-6）：对比GPU内存、训练时间和MACs。
  - 参数敏感性分析（图4）：研究补丁大小、回溯窗口、隐藏层数及维度的影响。
- **充分性与公平性**：实验覆盖多个领域和不同规模的数据集，对比方法均为近年SOTA，且统一使用TFB代码库进行公平比较（如不采用“Drop Last”技巧）。消融实验设计合理，插件实验验证了SRS模块的通用性。总体实验较为充分、客观。

## 6. 主要结论与发现
- SRSNet（SRS + MLP）在多数数据集和预测视界上取得最佳或次佳结果，尤其在ETTh2、Solar、Traffic上提升显著。
- SRS模块能有效提升多种基于分块的模型（PatchTST、Crossformer、PatchMLP、xPatch）的预测精度，平均提升约2%~16%。
- 选择性分块是三个组件中影响最大的，动态重组和自适应融合也均有正向贡献。
- 效率分析表明，SRS模块引入的额外开销可控（约10%左右），SRSNet整体轻量高效。

## 7. 优点
- **方法创新**：首次提出从“构建选择性表示空间”的视角改进分块技术，突破了固定分块的局限性；设计简单而有效的可微分选择机制。
- **模块化与通用性**：SRS是即插即用模块，可无缝集成到多种现存的基于分块的模型中，适用性广。
- **实验扎实**：覆盖多领域大规模数据集，详细的主实验、消融、插件、效率分析，并用5次随机种子报告标准差，结果可靠。
- **性能与效率平衡**：SRSNet以简单MLP头获得SOTA性能，同时保持较低的计算开销，有利于实际应用。

## 8. 不足与局限
- **适用范围有限**：SRS模块仅适用于采用分块技术的模型，对于非分块模型（如iTransformer、DLinear）无法直接使用（补丁大小=1时会失去语义并增加计算复杂度）。
- **可扩展性未验证**：在大规模预训练场景（如时间序列基础模型）下，SRS是否遵循缩放定律（scaling law）尚待实践验证。
- **可解释性不足**：虽然SRS可自适应选择补丁，但具体选择哪些补丁及为何选择难以解释，缺乏显式的环境感知机制。
- **初始化敏感性**：自适应融合参数α的初始化对收敛和稳定性有影响，论文虽提出基于先验知识手动初始化的建议，但缺乏自动更新机制。
- **实验细节缺失**：未明确报告完整训练硬件配置、总运行时间等，影响可复现性；未提及对比方法是否使用相同超参数搜索策略。

（完）
