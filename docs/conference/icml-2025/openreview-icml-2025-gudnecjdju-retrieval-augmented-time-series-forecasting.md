---
title: Retrieval Augmented Time Series Forecasting
title_zh: 检索增强的时间序列预测
authors: "Sungwon Han, Seungeon Lee, Meeyoung Cha, Sercan O Arik, Jinsung Yoon"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=GUDnecJdJU"
tags: ["query:qf"]
score: 6.0
evidence: 使用历史模式匹配的检索增强时间序列预测
tldr: 时间序列预测依赖历史关系。本文提出RAFT，检索训练集中与当前输入最相似的历史模式，并将其未来值作为外部信息辅助预测。在十个基准数据集上，RAFT一致超越现有方法，展现了检索增强范式的潜力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-gudnecjdju/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 840, \"height\": 257, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gudnecjdju/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1729, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gudnecjdju/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1763, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gudnecjdju/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1515, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gudnecjdju/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1677, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gudnecjdju/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1738, \"height\": 1356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gudnecjdju/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1747, \"height\": 1626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gudnecjdju/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1745, \"height\": 1636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gudnecjdju/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1742, \"height\": 1655, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1768, \"height\": 480, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 778, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 778, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 777, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1127, \"height\": 540, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1471, \"height\": 1761, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1692, \"height\": 450, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1648, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 923, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 940, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 756, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 909, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1253, \"height\": 141, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 930, \"height\": 138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 638, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1414, \"height\": 2067, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gudnecjdju/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1414, \"height\": 2063, \"label\": \"Table\"}]"
motivation: 传统时间序列模型容量有限，难以利用外部相似模式信息。
method: 在预测时从训练集中检索相似历史序列，将其未来值作为额外输入。
result: 在十个数据集中一致优于基线，验证了检索增强的有效性。
conclusion: 检索增强是一种简单有效的提升时间序列预测能力的方法。
---

## Abstract
Time series forecasting uses historical data to predict future trends, leveraging the relationships between past observations and available features. In this paper, we propose RAFT, a retrieval-augmented time series forecasting method to provide sufficient inductive biases and complement the model's learning capacity. When forecasting the subsequent time frames, we directly retrieve historical data candidates from the training dataset with patterns most similar to the input, and utilize the future values of these candidates alongside the inputs to obtain predictions. This simple approach augments the model's capacity by externally providing information about past patterns via retrieval modules. Our empirical evaluations on ten benchmark datasets show that RAFT consistently outperforms contemporary baselines with an average win ratio of 86%.

---

## 论文详细总结（自动生成）

# 论文《Retrieval Augmented Time Series Forecasting》详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：传统时间序列预测模型（如CNN、RNN、Transformer）依赖模型权重隐式记忆所有历史模式，但真实序列常包含非平稳、不频繁重现的复杂模式，模型难以泛化，且学习效率低。
- **动机**：受自然语言处理中检索增强生成（RAG）启发，尝试将外部相似历史模式显式提供给模型，降低模型学习负担，提升对罕见模式的预测能力。
- **整体含义**：提出一种**检索增强的时间序列预测范式**，通过从训练集中检索与当前输入模式最相似的历史片段，将其后续未来值作为额外输入辅助预测，显著提升预测性能。

## 2. 方法论

- **核心思想**：将整个训练序列分割为连续的“键-值”对（key: 历史窗口, value: 紧随其后的预测窗口）。对当前输入，计算其与所有键的相似度，选取top-m个最相似的键，用对应的值加权聚合得到外部信息，再与原始输入拼接后通过线性模型预测未来值。
- **关键技术细节**：
  - **预处理**：对每个patches减去最后一个时间步的值（offset），消除分布偏移，使模式对比更关注变化趋势。
  - **相似度度量**：采用Pearson相关系数，排除尺度和偏移影响。
  - **加权聚合**：对top-m个值应用SoftMax（带温度参数τ）得到权重，加权求和得到检索结果̃v。
  - **多周期扩展**：对原始序列进行下采样（周期p=1,2,4），对每个周期独立执行检索，最后将所有周期的检索结果通过线性层投影至相同维度后求和，再与输入拼接预测。
  - **最终预测**：使用线性层，恢复offset后输出。
- **公式与算法流程**（文字说明）：
  1. 从完整序列S中提取键集合K和值集合V（滑动窗口法，步长1）。
  2. 对输入x和所有键减去各自最后一个时间步值，得̂x和̂K。
  3. 计算̂x与每个̂k的Pearson相关系数ρ_i。
  4. 选取top-m的索引集合J，计算权重w_i（仅对J内做SoftMax）。
  5. ̃v = Σ w_i · ̂v_i。
  6. 多周期：对各周期p执行步骤2-5，得̃v^(p)，通过线性层g^(p)映射至相同维度后求和。
  7. 最终预测：̂y = h( f(̂x) ⊕ Σ g^(p)(̃v^(p)) )，然后恢复offset：y = {̂y_t + x_L}。
  8. 训练损失：MSE。

## 3. 实验设计

- **数据集**：10个基准数据集（ETTh1, ETTh2, ETTm1, ETTm2, Electricity, Exchange, Illness, Solar, Traffic, Weather），涵盖不同频率、变体数和长度。
- **Benchmark**：对比9种同期方法，包括Transformer类（Autoformer, Informer, Stationary, Fedformer, PatchTST）和轻量MLP类（DLinear, MICN, TimesNet, TimeMixer）。
- **评估设置**：
  - 预测长度：96, 192, 336, 720（Illness为24,36,48,60）。
  - 指标：MSE和MAE，每个实验运行3个随机种子取平均。
  - 超参数通过验证集网格搜索确定。
- **附加实验**：
  - 合成数据实验（自回归模型和随机游走模型），控制模式出现频率（1,2,4次）。
  - 消融实验（随机检索、无注意力、单周期、无检索）。
  - 超参数分析（L, m, τ）。
  - 不同相似度度量比较。
  - 对Transformer模型（Autoformer）的扩展应用。

## 4. 资源与算力

- 文中明确提到“每个实验在单个NVIDIA A100 40GB GPU上进行”。
- 未给出全部实验的精确训练时长，仅提供了ETTm1数据集上的示例：预计算42.2秒，每个epoch训练7.3秒，总训练时间未给出。
- 算力需求相对适中，但检索预计算开销为O(N²)，可通过增大滑动窗口步长降低。

## 5. 实验数量与充分性

- **实验数量**：40个主要实验设置（10数据集×4预测长度），每个3次随机种子，共120次独立运行。此外有消融（5种变体×8数据集）、合成数据（2种模型×3种频率）、超参数扫描等多个实验。
- **充分性**：覆盖了多种真实场景和合成案例，消融和对照组设计合理，证明了各组件贡献。但存在几点不足：
  - 对某些数据集（如Exchange、Illness）性能不如个别基线，论文未深入分析失败原因。
  - 多变量预测中，检索是在所有通道整体进行的，未探索按通道独立检索。
  - 合成数据仅测试了短期模式，未考虑趋势/季节的局部变化。
- **公平性**：所有方法均使用相同验证集调参，结果取自公开基准库，相对客观。

## 6. 主要结论与发现

- **核心结论**：检索增强能显著提升时间序列预测性能，平均Win Ratio为86%（10数据集上优于所有基线）。
- **检索质量与性能正相关**：高相似度的键导致高相似度的值，进而带来更大性能提升（Spearman相关系数验证）。
- **检索尤其有益于**：
  - 模式出现次数少（稀有模式）时，MSE下降9.2%–14.7%。
  - 时间相关性低（如随机游走模式）时，MSE下降16.0%–31.5%。
- **可扩展性**：检索模块可轻松附加到其他先进架构（如Autoformer），进一步提升性能。

## 7. 优点

- **简单有效**：仅需添加检索模块和线性投影，无需复杂架构改动，在10个基准上全面超越各类先进模型。
- **显式利用历史模式**：避免模型过度记忆冗余或噪声模式，降低过拟合风险。
- **多周期设计**：通过下采样捕捉不同时间尺度的模式，增强鲁棒性。
- **可解释性**：检索结果可视化为具体的历史相似片段，增加预测的可信度。
- **方法通用**：不仅可用于MLP，也适用于Transformer等架构。

## 8. 不足与局限

- **计算复杂度**：检索预计算为O(N²)，数据量巨大时可能成为瓶颈（可通过增大步长或近似最近邻搜索缓解，但文中未深入探讨）。
- **对检索依赖性强**：若训练集中无相似模式（如完全随机序列），检索可能引入噪声，导致性能下降。
- **实验覆盖有限**：
  - 未包含多步预测中的误差累积分析。
  - 未在超长序列（>10万时间步）上验证可扩展性。
  - 未与最新的大规模基础模型（如Lag-Llama）对比（发布时间差）。
- **领域假设**：假定训练集与测试集同分布，未考虑概念漂移等分布外场景。
- **多变量处理**：所有通道共用一个检索结果，可能忽略各通道的不同周期性？文中未讨论按通道独立检索的变体。

（完）
