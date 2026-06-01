---
title: In-Context Fine-Tuning for Time-Series Foundation Models
title_zh: 时间序列基础模型的上下文微调
authors: "Matthew Faw, Rajat Sen, Yichen Zhou, Abhimanyu Das"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=uxzgGLWPj2"
tags: ["query:qf"]
score: 7.0
evidence: 时间序列基础模型的上下文微调提升预测
tldr: 本文提出时间序列基础模型的上下文微调方法，在推理时通过输入多个相关时间序列示例使模型适应目标领域分布。该方法无需额外训练即可提升预测精度。在多个流行预测基准上，使用上下文示例的模型显著优于纯零样本预测，为金融时间序列波动率预测提供了灵活且高效的适配工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-uxzgglwpj2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 861, \"height\": 270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uxzgglwpj2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 612, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uxzgglwpj2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1156, \"height\": 826, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uxzgglwpj2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 795, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uxzgglwpj2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 769, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uxzgglwpj2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 683, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uxzgglwpj2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1584, \"height\": 1103, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uxzgglwpj2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1768, \"height\": 2174, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uxzgglwpj2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1336, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uxzgglwpj2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1292, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uxzgglwpj2/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1060, \"height\": 882, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-uxzgglwpj2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uxzgglwpj2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 114, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uxzgglwpj2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1011, \"height\": 1795, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uxzgglwpj2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1708, \"height\": 1096, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uxzgglwpj2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1561, \"height\": 832, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uxzgglwpj2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1770, \"height\": 401, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uxzgglwpj2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1772, \"height\": 432, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uxzgglwpj2/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1232, \"height\": 613, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uxzgglwpj2/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1771, \"height\": 599, \"label\": \"Table\"}]"
motivation: 零样本时间序列基础模型缺乏对目标领域分布的适配能力。
method: 设计可在推理时接收多个相关时间序列示例的预训练基础模型，利用上下文窗口进行领域适应。
result: 在多个预测数据集上，上下文微调显著提升了预测性能。
conclusion: 为时间序列预测提供了一种无需重训练的领域适应方法，可扩展至金融波动率预测。
---

## Abstract
Motivated by the recent success of time-series foundation models for zero-shot forecasting, we present a methodology for _in-context fine-tuning_ of a time-series foundation model. In particular, we design a pretrained foundation model that can be prompted (at inference time) with multiple time-series examples, in order to forecast a target time-series into the future. Our foundation model is specifically trained to utilize examples from multiple related time-series in its context window (in addition to the history of the target time-series) to help it adapt to the specific distribution of the target domain at inference time.  We show that such a foundation model that uses in-context examples at inference time can obtain much better performance on popular forecasting benchmarks compared to supervised deep learning methods, statistical models, and other time series foundation models.  Interestingly, our in-context fine-tuning approach even matches the performance of a foundation model that is explicitly fine-tuned on the target domain.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有的时间序列基础模型（如TimesFM、Chronos等）在零样本预测中表现出色，但它们缺乏像大语言模型（LLM）那样的**上下文学习**能力——即通过推理时提供相关示例来适应目标领域分布。传统的域微调（fine-tuning）虽然能提升性能，但破坏了零样本范式，需要额外的训练数据和计算资源。
- **核心问题**：能否设计一种方法，使时间序列基础模型在**推理阶段**，通过在其上下文窗口中提供多个相关时间序列示例，来达到类似显式微调的效果，同时保持零样本的便捷性？
- **整体含义**：本文首次系统研究了时间序列基础模型的“上下文微调”（In-Context Fine-Tuning, ICF），并提出一种实用的训练和推理框架，使得模型能够从上下文示例中“学习”目标域的模式，从而提高预测精度。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：让预训练的基础模型（基于TimesFM）在推理时接收一个包含多个相关时间序列示例的“提示”（prompt），这些示例与目标时间序列的历史一起输入模型，模型通过因果注意力机制从中提取统计规律，从而自适应目标域分布。
- **关键技术细节**：
  - **模型架构**：基于解码器-only的Transformer，将每个示例（包括目标序列）分割为长度为p=32的非重叠patch，通过共享的输入残差块（MLP+跳跃连接）嵌入为token。在序列末尾插入可学习的**分隔符token**，以区分不同示例。
  - **跨示例注意力**：允许Transformer的因果注意力跨越所有示例和分隔符，从而使模型能感知不同示例的边界。
  - **位置编码**：使用**无位置编码（NoPE）**替代原始TimesFM的绝对位置编码，以增强长度泛化能力，并使继续预训练时位置语义一致。
  - **继续预训练**：从预训练的TimesFM（base）检查点开始，在包含多个示例的上下文中继续训练（称“continued pretraining”）。训练数据来自与基础模型相同的语料（除Wiki数据集外），采用两种分组策略：**时间序列级**（同一长序列的连续段）和**数据集级**（同一数据集的不同序列段）。每个上下文包含最多n=50个示例（其中5个来自目标序列的近期历史，其余随机选取）。
  - **推理**：在测试时，对每个预测任务，构造包含目标历史及若干相关示例的上下文（最多50个示例，长度不超过512个时间步），直接输入模型获得预测。无需梯度更新。

### 3. 实验设计：数据集、基准与对比方法

- **数据集与基准**：
  - **OOD Benchmark**：来自Chronos零样本基准的23个未用于训练的数据集（涵盖金融、能源、交通、医疗等不同领域和频率，如M1/M3/M4、ETT、Dominick、ERCOT等）。评估指标为**MASE**（归一化后的几何均值）和加权分位数损失（WQL）。
  - **长期预测基准（ETT）**：4个ETT数据集（ETTh1/h2, ETTm1/m2），预测长度96/192/336/720，采用滑动窗口评估。指标为**MAE**。
- **对比方法**：
  - **零样本基础模型**：TimesFM（base）、Chronos-T5（4种规模）、LLMTime、ForecastPFN、Lag-Llama、Moirai（3种规模，但注意其预训练数据与OOD Benchmark重叠>80%，故在主实验中排除）。
  - **监督深度学习方法**：PatchTST、DeepAR、WaveNet、TFT、DLinear、N-HiTS、N-BEATS、GPT4TS等。
  - **统计方法**：AutoETS、AutoARIMA、AutoTheta、季节性朴素等等。
  - **显式微调基线**：TimesFM-FT（在目标数据集训练集上微调，包括全量微调和线性探测）。
- **实验设置**：每个评估重复10次随机种子，报告均值与标准误差。

### 4. 资源与算力

- 论文未明确列出训练TimesFM-ICF所使用的具体GPU/TPU型号、数量及总训练时长。但提供了以下算力相关信息：
  - 基础模型TimesFM（base）有50层Transformer，16个注意力头，模型维度1280，参数量未公布。
  - 推理实验在TPUv5e上进行（8个tensor core）。
  - 在OOD Benchmark上，TimesFM-ICF完成全部推理耗时**25分钟**，而TimesFM-FT需要**418分钟**（包括每个数据集上的微调时间）。
- 结论：尽管算力细节不足，但相对效率对比明确。

### 5. 实验数量与充分性

- **实验数量**：覆盖了27个数据集（OOD 23个 + ETT 4个），每个数据集上进行了多次重复（10次或5次）。此外进行了多种消融实验：
  1. **上下文示例数量消融**（图6）：在短上下文数据集上，变化示例数从0到50，观察MASE与推理时间。
  2. **长历史对比消融**（表2）：与拥有2048历史长度的TimesFM（LH）比较。
  3. **示例选择策略消融**（图10）：测试随机选择、近期历史选择、DTW相似度选择等。
  4. **验证集超参数调优**（图11）：通过网格搜索最优的序列内示例数与总示例数。
- **充分性**：实验设计较为全面，覆盖了多种数据类型、预测步长和基线方法。消融实验验证了核心组件的贡献。但当前方法仅基于TimesFM一种基础模型，未在其他时间序列基础模型（如Lag-Llama、Chronos）上验证ICF的泛化性，这是主要不足。

### 6. 论文的主要结论与发现

- **ICF显著提升零样本性能**：在OOD Benchmark上，TimesFM-ICF的归一化MASE几何均值为0.777，比TimesFM（base）（0.834）提升**6.8%**，比次优基线PatchTST（0.818）提升**5%**。
- **ICF能达到甚至超越显式微调**：TimesFM-ICF与TimesFM-FT（在目标域上微调的最优结果）性能几乎相同（0.777 vs 0.776），但推理速度快**16倍以上**（25分钟 vs 418分钟）。
- **上下文示例的有效性**：增加示例数量持续提升性能，同时线性增加推理时间。示例选择策略简单（近期历史+随机）已足够有效，更复杂的DTW选择未带来显著增益。
- **ICF优于仅扩展历史长度**：同样参数量的TimesFM（较长的2048历史）只能提升2.4%，而ICF提升6.8%，因为短序列可在上下文窗口中高效打包为多个示例。

### 7. 优点

- **方法创新性**：首次将LLM的上下文学习思想系统性地引入时间序列基础模型，提出可训练的分隔符、跨示例注意力和无位置编码等关键技术。
- **实用性强**：无需额外训练即可适应新领域，直接匹配微调性能，降低了落地成本。
- **消融实验充分**：对示例数量、历史长度、选择策略等进行了详细分析，验证了方法的鲁棒性。
- **与现有基准全面对比**：涵盖了20多种代表性方法，包括监督、统计和基础模型，评估指标和设置公允。

### 8. 不足与局限

- **基础模型依赖**：方法仅在TimesFM上验证，是否适用于其他架构（如Chronos、Moirai）未知，泛化性待进一步研究。
- **示例选择策略简单**：虽当前策略已有效，但更智能化（如基于相似度或任务类型）的示例筛选可能进一步提升性能，文中未深入探索。
- **上下文长度限制**：最大支持50个示例，每个示例最长512时间步，可能无法覆盖更长或更复杂的依赖关系。
- **计算开销**：推理时上下文较长，会线性增加计算量，对于实时性要求高的场景可能受限（文中已指出 trade-off）。
- **实验数据集偏重表现稳定**：未充分讨论ICF在极度非平稳或稀疏数据上的表现。
- **缺乏对多变量场景的深入分析**：文中指出Moirai的多变量模式本质不同，但未对比ICF在多变量数据上的直接收益。

（完）
