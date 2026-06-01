---
title: Improving Time Series Forecasting via Instance-aware Post-hoc Revision
title_zh: 通过实例感知的后处理修正改进时间序列预测
authors: "Zhiding Liu, Mingyue Cheng, GuanHao Zhao, Jiqian Yang, Qi Liu, Enhong Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=H7e5RpeIi4"
tags: ["query:qf"]
score: 6.0
evidence: 实例感知的后处理修正用于时间序列预测
tldr: 时间序列预测中实例级变化（分布漂移、缺失数据、长尾模式）导致模型在某些实例上表现不佳。本文提出模型无关的后处理修正框架PIR，通过识别有偏预测实例并进行修正来提升整体性能。PIR在多个数据集和模型上实现了一致的性能提升。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-h7e5rpeii4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1420, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-h7e5rpeii4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1376, \"height\": 736, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-h7e5rpeii4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1415, \"height\": 572, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-h7e5rpeii4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1436, \"height\": 632, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-h7e5rpeii4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1423, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-h7e5rpeii4/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1437, \"height\": 1074, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-h7e5rpeii4/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1422, \"height\": 820, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-h7e5rpeii4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1474, \"height\": 975, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-h7e5rpeii4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1260, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-h7e5rpeii4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1297, \"height\": 598, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-h7e5rpeii4/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1455, \"height\": 1688, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-h7e5rpeii4/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1458, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-h7e5rpeii4/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 446, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-h7e5rpeii4/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1318, \"height\": 478, \"label\": \"Table\"}]"
motivation: 时间序列预测模型在实例级变化下表现不稳定，即使整体性能良好。
method: 提出PIR框架，先识别有偏预测实例，然后对其预测结果进行修正。
result: 在多个时间序列数据集上，PIR显著提升了基础模型的预测准确性。
conclusion: 实例级后处理修正是提升时间序列预测鲁棒性的有效方法。
---

## Abstract
Time series forecasting plays a pivotal role in various real-world applications and has attracted significant attention in recent decades. While recent methods have achieved remarkable accuracy by incorporating advanced inductive biases and training strategies, we observe that instance-level variations remain a significant challenge. These variations—stemming from distribution shifts, missing data, and long-tail patterns—often lead to suboptimal forecasts for specific instances, even when overall performance appears strong. To address this issue, we propose a model-agnostic framework, PIR, designed to enhance forecasting performance through Post-forecasting Identification and Revision. Specifically, PIR first identifies biased forecast instances by estimating their predictive accuracy. Based on this, the framework revises the forecasts using contextual information, including covariates and historical time series, from both local and global perspectives in a post-processing fashion. Extensive experiments on real-world datasets with mainstream forecasting models demonstrate that PIR effectively mitigates instance-level errors and significantly improves forecasting reliability.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：时间序列预测模型在整体评估中表现良好，但面临**实例级变化**（instance-level variations）的挑战，这些变化来源于分布漂移、缺失数据和长尾模式，导致模型对某些特定实例预测失败（即预测误差远高于平均水平）。论文通过实验（PatchTST 在 ETTh1 上的每个样本 MSE 曲线和分布）验证了这一现象：误差分布呈长尾，少量实例误差极大。
- **整体含义**：本文首次强调实例级变化是时间序列预测中一个被忽视的瓶颈，并提出通过**后处理修正**（post-processing revision）来提升预测的鲁棒性和可靠性，而非修改基础模型结构。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：构建模型无关的框架 PIR（Post-forecasting Identification and Revision），先识别可能出错的预测实例，再使用局部和全局上下文信息修正其预测结果。
- **关键组件**：
  - **失败识别模块**：使用两层全连接网络 `fue` 估计每个输入-预测对的**不确定性** `δ`，将其约束为预测误差（MSE）的估计值，损失函数为 `L_ue = 1/N * sum( |δ - ||ŷ - y||^2| )`。
  - **局部修正模块**：将协变量的中间预测（`ŷ_cov`）和可用外生变量（如时间戳、文本描述）通过投影编码后拼接，输入 Transformer 进行交叉注意力，输出 `y_local`。
  - **全局修正模块**：在训练集中为当前输入检索 Top-K 最相似的历史序列（使用余弦相似度），然后对这些序列的真实未来值进行加权求和（权重为 softmax 后的相似度）作为 `y_global`。
  - **融合**：最终预测 `y_pred = ŷ + α * y_local + β * y_global`，其中 `α = σ(Linear(δ))`，`β = σ(MLP(δ, w))`。整体损失为 `L = L_pr + λ * L_ue`，`L_pr` 为 MSE。

## 3. 实验设计

- **数据集**：
  - 长期预测：ETTh1/2, ETTm1/2, Electricity, Solar, Weather, Traffic（8 个公开基准）。
  - 短期预测：PEMS03/04/07/08（4 个子集）。
  - 额外多模态：Energy, Health（含文本描述）。
- **Backbone 模型**（对比基准）：
  - PatchTST（通道独立）
  - SparseTSF（通道独立）
  - iTransformer（通道依赖）
  - TimeMixer（通道依赖）
- **对比方式**：每个 backbone 不加/加 PIR 进行对比（表 1 和 4 给出了完整结果）。
- **评估指标**：MSE 和 MAE；输入长度 96，预测长度变化。

## 4. 资源与算力

- 文中明确说明：**所有实验均在单个 NVIDIA RTX 4090 GPU 上运行**。
- 未给出具体训练时长或总计算成本，但提供了推理时间分析（表 2）：在 ETTh1 上 backbone 推理 0.164s，检索增加 0.024s，修正增加 0.096s；在 Traffic 上类似。

## 5. 实验数量与充分性

- **实验总览**：
  - 主实验表 1 涵盖 **48 个设置**（4 个 backbone × 4 个预测长度 × 3 类数据集？实际数了一下：4 backbone × 12 数据集 × 4 预测长度？但表 1 只列出了部分平均值，完整结果在表 4）。
  - 消融实验（表 6、7）：移除局部/全局修正、不同 λ 的影响、与加深模型对比、从头训练对比。
  - 定性分析（图 3、4、5、6、7）：误差估计准确性、分布改善、案例展示。
  - 推广性实验（表 5）：在 Energy、Health 上验证多模态场景。
- **充分性**：实验覆盖了多种数据规模、频率、领域；backbone 涵盖主流架构；提供了复杂度分析；消融和定性分析支撑了各组件的必要性。**实验设计客观、公平**。

## 6. 主要结论与发现

- PIR 框架在几乎所有设置下**一致提升**预测性能：PatchTST 平均 MSE 降低 8.99%，SparseTSF 降低 25.87%，iTransformer 降低 3.47%，TimeMixer 降低 2.34%。
- 失败识别模块能准确估计预测误差（图 3）；误差分布长尾被显著抑制（图 4），峰值 MSE 降低且高误差实例大幅减少。
- 局部和全局修正互补：局部修正利用协变量和外生变量，全局修正利用相似历史模式，融合后效果最佳（表 6）。
- PIR 作为模型无关插件，可以即插即用。

## 7. 优点

- **模型无关性**：不依赖 backbone 结构，可集成任意预测模型。
- **新颖问题定义**：首次系统研究实例级预测失败的修正问题。
- **双视角修正**：结合局部上下文（协变量/外生变量）和全局上下文（检索历史）进行修正，具有互补性。
- **端到端优化**：识别和修正联合训练，且识别模块使用误差作为监督，可解释性强。
- **高效实现**：检索使用余弦相似度可 GPU 并行，推理开销小（表 2）。

## 8. 不足与局限

- **仅处理输入侧实例级变化**：框架目前聚焦于输入序列导致的预测失败，未对目标序列本身（如噪声、异常值）进行识别或修正。
- **简单网络结构**：失败识别和局部修正模块仅用全连接或标准 Transformer，未融入更先进的归纳偏置（如频率分解、时序模式提取）。
- **依赖检索质量**：全局修正基于检索相似序列，对于历史中没有类似模式的实例（稀有事件）可能效果有限，尽管动态权重 β 部分缓解了这一问题（图 7）。
- **计算开销**：虽然推理时间可接受，但检索数据库构建和余弦相似度计算在极大规模场景下仍可能成为瓶颈（论文提到可以用降采样或降维缓解）。
- **缺少误差条或统计显著性检验**：论文未报告多次运行的标准差，可能受随机种子影响。

（完）
