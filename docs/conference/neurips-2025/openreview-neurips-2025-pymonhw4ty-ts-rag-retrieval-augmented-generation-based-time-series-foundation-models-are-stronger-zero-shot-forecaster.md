---
title: "TS-RAG: Retrieval-Augmented Generation based Time Series Foundation Models are Stronger Zero-Shot Forecaster"
title_zh: TS-RAG：基于检索增强生成的时间序列基础模型成为更强的零样本预测器
authors: "Kanghui Ning, Zijie Pan, Yu Liu, Yushan Jiang, James Y. Zhang, Kashif Rasul, Anderson Schneider, Lintao Ma, Yuriy Nevmyvaka, Dongjin Song"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=PymOnHw4Ty"
tags: ["query:qf"]
score: 5.0
evidence: 检索增强生成用于时间序列基础模型，提升零样本预测能力
tldr: 现有时间序列基础模型在非平稳和分布偏移下泛化能力不足。本文提出TS-RAG框架，通过预训练编码器检索语义相关片段，增强基础模型在零样本场景下的预测能力与可解释性。该方法可迁移至金融时间序列波动率预测，提升模型对新数据的适应性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-pymonhw4ty/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1423, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pymonhw4ty/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1412, \"height\": 680, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pymonhw4ty/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1364, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pymonhw4ty/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 695, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pymonhw4ty/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 657, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pymonhw4ty/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 554, \"height\": 794, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pymonhw4ty/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1291, \"height\": 781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pymonhw4ty/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1279, \"height\": 901, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pymonhw4ty/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1288, \"height\": 786, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pymonhw4ty/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1278, \"height\": 906, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-pymonhw4ty/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pymonhw4ty/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1229, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pymonhw4ty/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1326, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pymonhw4ty/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 617, \"height\": 138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pymonhw4ty/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 711, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pymonhw4ty/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 751, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pymonhw4ty/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1439, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pymonhw4ty/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1439, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pymonhw4ty/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1429, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pymonhw4ty/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1429, \"height\": 443, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pymonhw4ty/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1441, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pymonhw4ty/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1355, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pymonhw4ty/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1428, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pymonhw4ty/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1083, \"height\": 278, \"label\": \"Table\"}]"
motivation: 时间序列基础模型在非平稳动态和分布偏移下泛化能力有限。
method: 提出TS-RAG，利用检索增强生成提升零样本预测和可解释性。
result: 在多种数据集上展现更强的泛化性能和解释性。
conclusion: 为时间序列基础模型的适应性和可解释性提供了新范式。
---

## Abstract
Large Language Models (LLMs) and Foundation Models (FMs) have recently become prevalent for time series forecasting tasks. While fine-tuning LLMs enables domain adaptation, they often struggle to generalize across diverse and unseen datasets. Moreover, existing Time Series Foundation Models (TSFMs) still face challenges in handling non-stationary dynamics and distribution shifts, largely due to the lack of effective mechanisms for adaptation. To this end, we present TS-RAG, a retrieval-augmented generation framework for time series forecasting that enhances the generalization and interpretability of TSFMs. Specifically, TS-RAG leverages pre-trained time series encoders to retrieve semantically relevant segments from a dedicated knowledge base, enriching the contextual representation of the input query. Furthermore, we propose an Adaptive Retrieval Mixer (ARM) module that dynamically fuses the retrieved patterns with the TSFM's internal representation, improving forecasting accuracy without requiring task-specific fine-tuning. Thorough empirical studies on seven public benchmark datasets demonstrate that TS-RAG achieves state-of-the-art zero-shot forecasting performance, outperforming the existing TSFMs by up to 6.84\% across diverse domains while also providing desirable interpretability. Our code and data are available at: https://github.com/UConn-DSIS/TS-RAG.

---

## 论文详细总结（自动生成）

# 论文总结：TS-RAG: 检索增强生成的时间序列基础模型成为更强的零样本预测器

## 1. 核心问题与整体含义（研究动机和背景）
- **背景**：时间序列预测在金融、医疗、能源等领域至关重要。传统统计方法和深度学习模型往往在特定领域表现良好，但难以在未见过的数据集上泛化。近期，大语言模型（LLMs）和时间序列基础模型（TSFMs）展示了潜力，但LLMs微调成本高且跨领域泛化差，而TSFMs缺乏动态适应机制，难以处理非平稳动态和分布偏移。此外，TSFMs可解释性有限。
- **核心问题**：如何在不进行微调的情况下，利用外部知识增强TSFMs的零样本泛化能力和可解释性？
- **整体含义**：受自然语言处理中检索增强生成（RAG）成功启发，本文提出TS-RAG框架，通过检索语义相关的时间序列片段并动态融合到预测流程中，显著提升TSFMs的零样本预测性能，同时提供可解释性。

## 2. 方法论
### 2.1 核心思想
- 使用预训练的时间序列编码器（即Chronos编码器）将查询时间序列编码为嵌入，在一个外部知识库中检索top-k个最相似的（上下文窗口, 未来地平线）对，然后通过一个可学习的Adaptive Retrieval Mixer（ARM）模块将检索到的未来模式与TSFM主干网络的内部表征动态融合，最终生成增强预测。

### 2.2 关键技术细节
- **检索知识库构建**：从Chronos预训练数据集中均匀采样子集，构建多领域知识库。每个条目为三元组（上下文序列, 其嵌入, 对应的未来地平线）。
- **检索器**：使用预训练的Chronos编码器计算查询嵌入，用欧氏距离在知识库中选取top-k最相似条目。
- **ARM模块**：
  - 对每个检索到的未来地平线，用可学习的MLP投影为d维嵌入；
  - 将TSFM主干输出的查询嵌入与k个检索嵌入拼接成(k+1)×d矩阵；
  - 通过多头注意力（MHA）加残差、FFN加残差进行交互；
  - 用可学习的评分网络生成重要性权重α（Softmax归一化）；
  - 最终表示为查询嵌入加上加权和，再经过TSFM输出投影层得到最终预测。
- **训练策略**：冻结TSFM主干和检索编码器，仅训练ARM模块和投影器参数（轻量级）。
- **零样本推理**：直接使用预训练好的ARM和知识库进行推理，无需微调。

## 3. 实验设计
### 3.1 数据集与场景
- **评估数据集**：7个公开基准：ETTh1, ETTh2, ETTm1, ETTm2, Weather, Electricity, Exchange Rate。涵盖不同领域（电力、天气、汇率）。
- **零样本设置**：在测试集上评估，预训练和知识库构建使用独立子集，测试集未见。
- **场景**：包括长时预测（预测长度64/96/192/336/720），以及不同知识库配置（域内、分布偏移、跨域、多域）的消融。

### 3.2 基准方法与对比
- **基线TSFMs**：Chronos-Bolt, MOMENT, TTM, Moirai, TimesFM, Chronos, Time-MoE等。
- **对比方法**：主要与RAF（最新检索增强零样本方法）对比。
- **评估指标**：均方误差（MSE）、平均绝对误差（MAE）。

## 4. 资源与算力
- **训练**：单块NVIDIA A6000-48G GPU，使用TF32精度，训练约10,000步，耗时约1小时。批量大小256，学习率0.0003，AdamW优化器。
- **推理**：检索（使用FAISS）每次9.2 ms，前向0.44 ms，总计9.62 ms/查询。相比RAF（3.47秒/查询）快360倍。

## 5. 实验数量与充分性
- **主要零样本预测**：在7个数据集上报告MSE/MAE，包含所有基线TSFMs，结果有统计优势。
- **消融实验**：
  - ARM vs. 简单门控融合（Gate）；
  - 不同知识库类型（域内、分布偏移、跨域、多域）；
  - 不同预测长度（96/192/336/720）；
  - 不同检索回溯长度（64/128/256/512）；
  - 不同检索数量k（4/8/16/20）；
  - 不同检索编码器（Chronos、TTM、MOMENT）；
  - 不同距离度量（欧氏、余弦、DTW）；
  - 不同主干模型（Chronos-Bolt、MOMENT）验证泛化性；
  - 与RAF对比（效果和效率）。
- **可解释性案例**：展示了检索序列的相似性和预测改进的可视化。
- **充分性评价**：实验覆盖全面，从多个维度验证了TS-RAG的鲁棒性和有效性；对比方法公平（使用相同设置和公共数据集）；消融设计合理。

## 6. 主要结论与发现
- TS-RAG在所有7个数据集上均优于最先进的TSFMs（包括其主干Chronos-Bolt），平均MSE降低3.54%，MAE降低1.43%；最大值在Exchange Rate上降低6.84%。
- ARM模块比简单门控融合效果更好，说明基于注意力的动态融合是关键。
- 域内知识库效果最佳，但跨域和多域检索也能带来增益，说明RAG的通用性。
- 检索编码器的选择对性能影响不大，表明TS-RAG对检索器鲁棒。
- 欧氏和余弦距离优于DTW，嵌入空间检索更有效。
- TS-RAG在长时预测中减少误差累积，且效率远高于同类方法RAF。

## 7. 优点
- **创新性**：将RAG成功引入时间序列基础模型，设计ARM模块实现动态融合，无需微调。
- **轻量高效**：可训练参数极少（仅ARM和投影器），训练快；推理通过FAISS实现高速检索，适合实时应用。
- **通用性**：与任意TSFM主干兼容（已验证Chronos-Bolt、MOMENT），即插即用。
- **可解释性**：通过展示检索的类比序列及其权重，提供预测的透明解释。
- **实验扎实**：涵盖多种场景和全面消融，代码开源。

## 8. 不足与局限
- **模态限制**：目前仅使用纯时间序列检索，未引入文本或外部多模态信息（如新闻、事件），这在某些场景下可能限制效果（论文附录E提及）。
- **应用场景局限**：仅在标准公开基准上评估，未在金融、医疗等真实复杂环境中验证（论文附录E提及）。
- **对数据特性敏感**：分析表明，高自相关、低噪声的数据集获益较大；而对于噪杂、高波动数据，增益有限。
- **知识库依赖性**：性能受知识库质量和覆盖度影响；若目标域与知识库差异极大，检索可能提供噪声。
- **静态检索机制**：每个查询使用固定top-k，未引入自适应选择检索数量的机制（尽管消融显示k=10左右即可），可能存在信息冗余或不足。

（完）
