---
title: "LightGTS: A Lightweight General Time Series Forecasting Model"
title_zh: LightGTS：轻量级通用时间序列预测模型
authors: "Yihang Wang, Yuying Qiu, Peng Chen, Yang Shu, Zhongwen Rao, Lujia Pan, Bin Yang, Chenjuan Guo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Z5FJsp1U3Z"
tags: ["query:qf"]
score: 5.0
evidence: 轻量级通用时间序列预测模型，采用周期性标记化，与金融时间序列预测相关
tldr: 现有通用时间序列模型依赖大规模预训练，计算成本高。本文提出LightGTS，从一致性周期建模角度出发，引入周期性标记化提取跨数据集的一致周期模式，并在解码阶段利用周期性信息。在多个数据集上，LightGTS以更少参数达到与大型基础模型相当的性能。该模型轻量高效，适用于金融时间序列等资源受限场景。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-z5fjsp1u3z/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 740, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z5fjsp1u3z/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1723, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z5fjsp1u3z/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1728, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z5fjsp1u3z/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 784, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z5fjsp1u3z/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 283, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z5fjsp1u3z/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1762, \"height\": 372, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-z5fjsp1u3z/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1510, \"height\": 454, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z5fjsp1u3z/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1774, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z5fjsp1u3z/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 863, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z5fjsp1u3z/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 864, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z5fjsp1u3z/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 863, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z5fjsp1u3z/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 860, \"height\": 250, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z5fjsp1u3z/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1333, \"height\": 1678, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z5fjsp1u3z/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1335, \"height\": 466, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z5fjsp1u3z/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1070, \"height\": 576, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z5fjsp1u3z/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1070, \"height\": 148, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z5fjsp1u3z/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1249, \"height\": 429, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z5fjsp1u3z/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1773, \"height\": 1997, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z5fjsp1u3z/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1771, \"height\": 1787, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z5fjsp1u3z/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1596, \"height\": 1881, \"label\": \"Table\"}]"
motivation: 现有通用时间序列基础模型规模大、计算负担重，难以在资源受限场景使用。
method: 提出周期性标记化提取多源数据中的一致周期模式，并设计周期性解码机制。
result: LightGTS在多个公共数据集上以更低参数和计算量达到与大型模型可比的预测性能。
conclusion: 轻量级通用时间序列模型LightGTS兼顾效率与准确性，适合金融等领域实际部署。
---

## Abstract
Existing works on general time series forecasting build foundation models with heavy model parameters through large-scale multi-source pretraining. These models achieve superior generalization ability across various datasets at the cost of significant computational burdens and limitations in resource-constrained scenarios. This paper introduces LightGTS, a lightweight general time series forecasting model designed from the perspective of consistent periodical modeling. To handle diverse scales and intrinsic periods in multi-source pre-training, we introduce Periodical Tokenization, which extracts consistent periodic patterns across different datasets with varying scales. To better utilize the periodicity in the decoding process, we further introduce Periodical Parallel Decoding, which leverage historical tokens to improve forecasting. Based on the two techniques above which fully leverage the inductive bias of periods inherent in time series, LightGTS uses a lightweight model to achieve outstanding performance on general time series forecasting. It achieves state-of-the-art forecasting performance on 9 real-world benchmarks in both zero-shot and full-shot setting with much better efficiency compared with existing time series foundation models

---

## 论文详细总结（自动生成）

# LightGTS: 轻量级通用时间序列预测模型 — 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有通用时间序列基础模型（TSFMs）依赖大规模多源预训练和庞大模型参数（如MOIRAI 311M、Chronos 700M、Time-MoE 453M），虽然泛化能力强，但计算负担重、资源受限场景难以部署。论文旨在利用时间序列固有的“尺度不变的内在周期”归纳偏置，设计一种轻量级模型，在保持高性能的同时大幅降低参数量和计算成本。
- **核心问题**：不同数据集具有不同采样率（尺度）和内在周期，导致固定长度分块（fixed patch）无法一致地捕获周期模式，限制了模型泛化并迫使模型增大容量。作者希望解决多源预训练中尺度多样性与周期建模不一致的问题。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 利用时间序列内在周期（如日周期）在尺度变化下保持不变的性质，通过**自适应周期分块**和**柔性投影层**实现跨尺度一致表示；在解码阶段引入**周期性并行解码**，利用历史最后一个token的周期信息同时预测未来多个周期，避免自回归误差累积并提高效率。

### 关键技术细节
1. **周期性标记化（Periodical Tokenization）**：
   - **周期分块**：对输入序列使用周期发现（如FFT）得到周期长度P，将序列分割成非重叠的周期块（每个块覆盖一个完整周期）。这使得不同尺度的数据被映射到统一的周期对齐语义空间。
   - **柔性投影层（Flex Projection Layer）**：由于不同数据集周期长度不同，固定嵌入投影无法处理变长块。作者理论分析后提出柔重置操作：`Flex-resize(θ) = δ⁻¹(A)⁺θ`，其中A为线性插值矩阵，δ为方差缩放因子。该操作使得变长块嵌入与参考块嵌入保持一致，避免线性插值引入的表示失真。实际使用时，维护一个参考尺寸P*的可学习参数，在前向传播时动态调整到当前周期长度P。

2. **编码与解码**：
   - 编码器：采用Transformer encoder，使用RoPE位置编码，不加掩码，建模输入序列的周期模式。
   - **周期性并行解码（Periodical Parallel Decoding, PPD）**：非自回归方法。将编码器最后一个token（保留周期特征并综合历史信息）复制K次（K=⌈F/P⌉），并对每个token按位置τ施加重权函数ω(τ)=e⁻ᵗ，然后全部同时输入解码器。解码器输出通过柔性投影层得到预测值。

3. **损失函数**：标准MSE。

### 公式/算法文字说明
- 周期发现：P = PeriodsFinding(x)
- 柔性投影：θ' = δ⁻¹(A)⁺θ （理论推导结果，确保token一致性）
- 编码器输出E = {eⱼ}
- 解码器输入H = replicate(eₙ, K)，加权后 ω(j)hⱼ
- 解码器输出Z = Decoder({ω(j)hⱼ}, E)
- 预测：Ŷ = Flex-resize(θd)·Z

## 3. 实验设计：数据集、基准、对比方法

- **预训练数据集**：收集了多个公开多领域数据集（Monash, UEA, UCR等），涵盖能源、自然、健康、交通、网络、经济等，与下游测试集无重叠。
- **评估数据集**：9个经典多变量数据集：Weather, Traffic, Electricity, Solar, Exchange, ETTh1/ETTh2, ETTm1/ETTm2。
- **对比方法**：
  - 零样本场景：Timer, MOIRAI, Chronos, TimesFM, Time-MoE（均为大型TSFMs）
  - 全样本场景：PDF, iTransformer, Pathformer, FITS, TimeMixer, PatchTST（均为SOTA深度学习模型）
- **评估指标**：MSE和MAE；预测长度{96,192,336,720}。

## 4. 资源与算力

- **文中明确说明**：使用PyTorch，所有实验在**一张NVIDIA A8000 80GB GPU**上运行。预训练采用Adam优化器，初始学习率5e-4，StepLR调度。具体训练时长未报告。
- **参数规模**：LightGTS-tiny 1.3M参数，LightGTS-mini 4M参数，模型尺寸比对比方法小10~100倍。
- **推理效率**：在ETTm1数据集预测长度720、batch size=1时，最大内存713MB，推理时间0.01s，与PatchTST相当，远优于大型模型。

## 5. 实验数量与充分性

- **实验数量充分**：
  - 零样本预测：在9个数据集、4个预测长度上对比5~6个大型TSFMs（共36个结果），LightGTS-tiny和mini均优于所有基线。
  - 全样本预测：同数据集对比6个SOTA小模型，LightGTS-mini全样本与零样本均优于或持平基线。
  - 消融实验：验证周期性标记化、周期性并行解码、参考周期长度P*、解码器初始token选择、不同重置方法等。
  - 鲁棒性分析：不同采样粒度下对比Timer和Time-MoE，显示LightGTS性能稳定。
  - 表示学习可视化：Token相似性矩阵展示周期分块的优势。
- **公平性**：预训练数据集与测试集严格不重叠；所有基线使用官方代码或复现；drop_last设为False避免额外误差。对比方法包括零样本和全样本设置，覆盖全面。

## 6. 论文的主要结论与发现

- LightGTS以极少的参数（1.3M/4M）在零样本和全样本场景下均达到最先进预测性能，平均MSE比最强基线降低17%~30%。
- 周期性标记化使得模型能够处理不同采样率下的周期模式，显著提升跨尺度泛化能力。
- 周期性并行解码不仅避免了自回归误差累积，而且通过利用最后一个token的周期信息提升预测质量。
- 模型对参考周期大小P*不敏感，鲁棒性强；在不同采样粒度下性能稳定，而其他TSFMs波动剧烈。

## 7. 优点

- **轻量化与高效性**：参数量比顶尖TSFMs小10~100倍，推理时间与最小模型PatchTST相当，适合资源受限场景（如边缘设备、金融实时预测）。
- **创新性强**：提出周期分块和柔性投影，巧妙解决多尺度周期建模难题；非自回归解码重用历史最后一个token，设计简洁有效。
- **理论分析扎实**：对柔性投影的数学推导解释了线性插值的缺陷并给出闭合解，增强方法可信度。
- **实验全面**：涵盖零样本、全样本、消融、鲁棒性、表示分析等多种实验，对比基线包括最新大模型和SOTA小模型，公平性强。

## 8. 不足与局限

- **周期发现依赖**：当数据周期性强时（如Solar、Electricity），FFT能准确提取周期；但周期较弱或不存在（如Exchange、部分ETT子集）时，FFT可能不准确，虽然仍能优于基线但性能略有下降。论文讨论了此问题，但未提出更鲁棒的周期发现方法。
- **单GPU训练**：仅在A800上训练，未提供多卡扩展结果或训练总时间，对于大规模预训练的算力需求评估不充分。
- **零样本场景的覆盖**：部分基线（如TimesFM）在部分数据集上未公布结果，导致比较不完全（如Traffic、Electricity）。另外LightGTS未与最新模型MOMENT、TTMs对比（后者在讨论中提及但未在主要实验中）。
- **应用限制**：模型假设时间序列具有内在周期，对于非周期性或弱周期性数据（如随机波动、突发事件）可能受限。此外，当前仅支持固定长度预测（通过⌈F/P⌉确定token数），对于任意长度预测需额外处理。
- **实验偏倚风险**：所有测试集为公开基准，可能已隐含周期性结构；在真实工业场景中数据噪声更大、周期不固定，泛化能力需进一步检验。

（完）
