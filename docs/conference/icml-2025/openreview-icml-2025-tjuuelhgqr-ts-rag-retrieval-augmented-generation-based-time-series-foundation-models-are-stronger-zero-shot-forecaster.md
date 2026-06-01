---
title: "TS-RAG: Retrieval-Augmented Generation based Time Series Foundation Models are Stronger Zero-Shot Forecaster"
title_zh: TS-RAG：基于检索增强生成的时间序列基础模型实现更强的零样本预测
authors: "Kanghui Ning, Zijie Pan, Yu Liu, Yushan Jiang, James Y. Zhang, Kashif Rasul, Anderson Schneider, Lintao Ma, Yuriy Nevmyvaka, Dongjin Song"
date: 2025-01-23
pdf: "https://openreview.net/pdf?id=TJuUelhGQr"
tags: ["query:qf"]
score: 6.0
evidence: 基于基础模型的零样本时间序列预测
tldr: 针对现有时间序列基础模型缺乏领域自适应和可解释性导致零样本预测不足的问题，提出TS-RAG框架，融合预训练时间序列基础模型与检索增强生成技术，通过检索相关时间序列片段辅助生成预测，提升了零样本泛化能力和可解释性。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tjuuelhgqr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1276, \"height\": 967, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tjuuelhgqr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 718, \"height\": 1020, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tjuuelhgqr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 831, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tjuuelhgqr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 786, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tjuuelhgqr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1053, \"height\": 646, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tjuuelhgqr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1054, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tjuuelhgqr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 995, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tjuuelhgqr/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 998, \"height\": 706, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tjuuelhgqr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1780, \"height\": 510, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tjuuelhgqr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tjuuelhgqr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tjuuelhgqr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1330, \"height\": 290, \"label\": \"Table\"}]"
motivation: 现有时间序列基础模型在零样本场景下泛化性和可解释性不佳。
method: 利用检索增强生成，从外部语料库检索相关序列片段辅助预测。
result: 在多个未见过的数据集上实现了零样本预测性能提升和可解释性增强。
conclusion: 检索增强能有效提升时间序列基础模型的零样本能力。
---

## Abstract
Recently, Large Language Models (LLMs) and Foundation Models (FMs) have become prevalent for time series forecasting tasks. However, fine-tuning large language models (LLMs) for forecasting enables the adaptation to specific domains but may not generalize well across diverse, unseen datasets. Meanwhile, existing time series foundation models (TSFMs) lack inherent mechanisms for domain adaptation and suffer from limited interpretability, making them suboptimal for zero-shot forecasting. To this end, we present TS-RAG, a retrieval-augmented generation based time series forecasting framework that enhances the generalization capability and interpretability of TSFMs. Specifically, TS-RAG leverages pre-trained time series encoders to retrieve semantically relevant time series segments from a dedicated knowledge database, incorporating contextual patterns for the given time series query. Next, we develop a learnable Mixture-of-Experts (MoE)-based augmentation module, which dynamically fuses retrieved time series patterns with the TSFM's representation of the input query, improving forecasting accuracy without requiring task-specific fine-tuning. Thorough empirical studies on seven public benchmark datasets demonstrate that TS-RAG achieves state-of-the-art zero-shot forecasting performance, outperforming TSFMs by up to 6.51\% across diverse domains and showcasing desired interpretability.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究背景**：时间序列预测在金融、医疗、能源等领域至关重要。现有方法包括传统统计模型（如ARIMA）、机器学习（如随机森林、XGBoost）、深度学习（LSTM、Transformer）等，但它们在零样本（zero-shot）场景下泛化能力不足。近期，大语言模型（LLM）和时间序列基础模型（TSFM）被广泛用于预测，但存在两个关键问题：
  - 微调LLM虽然能适应特定领域，但难以泛化到未见过的数据集，且计算成本高昂。
  - 现有TSFM（如Chronos、TimesFM、Moirai等）缺乏内在的领域自适应机制，无法动态融入外部上下文知识，且可解释性有限，导致零样本预测效果欠佳。
- **核心问题**：如何在不进行任务特定微调的情况下，提升TSFM在零样本场景下的预测准确性和可解释性？
- **动机**：受自然语言处理中检索增强生成（RAG）成功的启发，本文提出将RAG引入时间序列预测，通过检索相关历史模式来增强TSFM的预测能力。

## 2. 方法论

- **核心思想**：TS-RAG包含两个关键组件——**检索器（Retriever）** 和 **增强模块（Augmentation Module）**。通过预训练的TSFM编码器将输入查询时间序列编码为嵌入，与外部知识库中的历史序列嵌入进行相似度匹配，检索出最相似的top-k个序列及其对应的未来预测窗口。然后利用一个**可学习的基于混合专家（MoE）的增强模块**，将这些检索到的模式动态融合到TSFM的表示中，最终生成预测。
- **关键技术细节**：
  - **检索知识库构建**：使用Chronos的预训练数据集（TSMixup增强）的子集，提取上下文-未来对 `(xi, yi)`，并用Chronos编码器生成上下文嵌入`e_i`，形成三元组 `(xi, e_i, yi)` 存储。
  - **检索过程**：输入查询`x_q`，编码得`e_q`，计算欧氏距离 `d(e_q, e_i)`，选择距离最小的k个候选对。
  - **MoE融合模块**：
    - 对每个检索到的未来序列`y_i`，通过可学习MLP投影得嵌入`\hat{e}_i`。
    - 将所有检索嵌入堆叠为 `E_enc ∈ R^{k×d}`，与查询TSFM表示`\hat{e}_q`拼接得 `E_concat ∈ R^{(k+1)×d}`。
    - 通过多头注意力（MHA）学习交互，得`E_att`。
    - 门控网络计算各专家权重 `α = Softmax(W_g E_concat + b_g)`，加权求和并加上残差连接：`e_final = \hat{e}_q + Σ α_i E_att,i`。
    - 最终通过TSFM输出投影层 `f_proj` 得到预测 `\hat{y}_q`。
  - **训练与推理**：只训练MoE模块参数，TSFM参数冻结。零样本推理时直接使用预训练好的组件。
- **算法流程**（文字说明）：
  1. 输入查询时间序列`x_q`，使用Chronos编码器生成嵌入`e_q`。
  2. 在知识库中检索top-k个最相似的历史序列及其未来窗口。
  3. 将检索到的未来窗口通过MLP投影为嵌入，与查询TSFM表示拼接。
  4. 经过MHA、门控融合、残差连接，得到增强后的表示。
  5. 通过TSFM输出层生成最终预测。

## 3. 实验设计

- **数据集与场景**：使用7个公开基准数据集：
  - **ETT系列**：ETTh1、ETTh2（小时级），ETTm1、ETTm2（15分钟级），涉及油温预测。
  - **Weather**：德国气象站10分钟采样数据。
  - **Electricity**：321个客户的每小时电力消费数据。
  - **Exchange Rate**：8国每日汇率（1990-2016）。
- **Benchmark**：零样本预测，测试集上评估。数据划分：ETT为6:2:2，其他为7:1:2（训练/验证/测试）。
- **对比方法**：包括TTM、TimesFM、Moirai、Chronos、Chronos-Bolt、MOMENT等主流TSFM。
- **评价指标**：均方误差（MSE）和平均绝对误差（MAE）。
- **消融实验**：
  - 检索数量k的敏感性（k从1到20）。
  - 不同检索数据库版本（无RAG、预训练全域数据库、数据特定历史数据库）。
  - 不同检索回看长度（64、128、256、512）。
  - 更长预测Horizon（96、192、336、720）下的效果。
- **案例研究**：定性展示检索到的序列与查询的相似性，以及RAG如何改进趋势突变和峰值预测。

## 4. 资源与算力

- 文中明确说明：训练使用一块**NVIDIA A6000 48G GPU**，采用TF32精度。
- 训练参数：batch size 256，训练步数10,000步，学习率0.0003，weight decay 0.01，dropout 0.2。
- 检索加速：使用FAISS进行快速近似最近邻搜索。
- **未说明**：训练总时长、是否使用多卡并行、数据预处理及检索数据库构建的具体耗时。实验可复现性方面不够详细。

## 5. 实验数量与充分性

- **实验数量**：
  - 主要零样本对比实验：1张表（表1），覆盖7个数据集，对比6种基线方法。
  - 消融实验：4张表/图（k敏感性图2，数据库版本表2，lookback长度表3，长horizon表4）。
  - 案例研究：2张图（图3、4）及附录中更多案例。
- **充分性分析**：
  - 正面：覆盖了多个领域（电力、天气、汇率等），消融实验考虑了关键设计变量（k、数据库、回看长度），并验证了长Horizon下的有效性。案例研究增强了可解释性。
  - 不足：
    - 所有实验仅验证了以Chronos-Bolt为骨干的情况，未验证与其他TSFM（如TimesFM、Moirai）组合的泛化性。
    - 零样本实验仅使用各数据集自身的训练集作为历史数据库（仅用于检索，不微调），未探索跨领域检索的效果。
    - 未与基于LLM的微调方法（如Time-LLM）对比，仅比了TSFM。
    - 未报告统计显著性检验（如p值或置信区间）。
    - 数据集规模较小（仅有7个），代表性有限。

## 6. 主要结论与发现

- TS-RAG在7个数据集上均**优于所有对比TSFM**，包括其骨干Chronos-Bolt，平均MSE降低3.54%，MAE降低1.43%。
- 最大提升出现在ETTm1数据集，MSE下降**6.51%**。
- 检索到的序列在趋势和周期性上与查询高度相似，提供了可解释的预测依据。
- 消融实验表明：
  - 适当增加检索数量k（6-10）可改善性能，过多则收益递减。
  - 使用数据集自身历史数据库比全域预训练数据库略优，但局部情况（如ETTh2）下全域数据库更好。
  - 较长的回看长度（256或512）一般更优，但过长的回看可能引入噪声。
  - 在更长预测horizon（96-720）下，RAG仍能有效缓解误差累积。

## 7. 优点

- **创新性**：首次将RAG系统性地应用于时间序列零样本预测，提出检索-融合-生成框架。
- **实用性**：无需微调骨干模型，仅训练少量MoE参数，计算开销低，适合资源受限场景。
- **可解释性**：检索到的历史片段可作为预测的“证据”，帮助理解模型行为。
- **模块化设计**：可替换不同的TSFM骨干和检索编码器，具有灵活性。
- **充分的消融实验**：对关键超参数（k、检索数据库、回看长度）进行了系统分析，提供了实践指导。

## 8. 不足与局限

- **骨干单一**：仅以Chronos-Bolt为骨干验证，未证明与其他TSFM（如TimesFM、Moirai）兼容，泛化性存疑。
- **数据库构建局限**：零样本实验中使用自身训练集作为历史数据库，本质上是利用了领域内信息，与“零样本”定义存在一定偏差（尽管未微调）。跨领域检索效果未充分探索。
- **实验覆盖不足**：仅7个数据集，且多为单变量预测场景；未涉及多变量预测、分类、异常检测等其他时间序列任务。
- **计算开销未量化**：检索过程（FAISS）在推理时的额外时间成本未报告，可能影响实时性。
- **公平性对比**：未与基于LLM微调的强基线（如Time-LLM、LLM-Time）对比，仅在TSFM之间比较，结论的竞争力受限。
- **可重复性细节缺失**：随机种子、数据切分具体方式、检索数据库构建的具体采样策略等未完全公开。
- **应用限制**：对于极长预测horizon（如720），虽然RAG有改进，但绝对误差仍较大，可能不适合高精度需求场景。

（完）
