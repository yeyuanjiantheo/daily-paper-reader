---
title: Towards a General Time Series Forecasting Model with Unified Representation and Adaptive Transfer
title_zh: 面向通用时间序列预测模型：统一表示与自适应迁移
authors: "Yihang Wang, Yuying Qiu, Peng Chen, Kai Zhao, Yang Shu, Zhongwen Rao, Lujia Pan, Bin Yang, Chenjuan Guo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=6J9tJKK4YI"
tags: ["query:qf"]
score: 5.0
evidence: 通用时间序列预测，统一表示与自适应迁移，与金融预测相关
tldr: 多源时间序列数据存在异构性，现有基础模型主要扩大规模。本文另辟蹊径，首先提出分解方法从异构数据中提取统一表示，然后设计自适应迁移机制捕获领域特定特征迁移到下游场景。实验证明该模型在多个数据集上泛化性强。该框架可应用于金融时间序列的跨市场或跨资产预测。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6j9tjkk4yi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1684, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6j9tjkk4yi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1766, \"height\": 748, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6j9tjkk4yi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1745, \"height\": 638, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6j9tjkk4yi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 864, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6j9tjkk4yi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 771, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6j9tjkk4yi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6j9tjkk4yi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1617, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6j9tjkk4yi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6j9tjkk4yi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1778, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6j9tjkk4yi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1470, \"height\": 786, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6j9tjkk4yi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1459, \"height\": 789, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6j9tjkk4yi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1605, \"height\": 716, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6j9tjkk4yi/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1610, \"height\": 702, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6j9tjkk4yi/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1607, \"height\": 718, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6j9tjkk4yi/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1609, \"height\": 714, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6j9tjkk4yi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6j9tjkk4yi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6j9tjkk4yi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 862, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6j9tjkk4yi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6j9tjkk4yi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1250, \"height\": 1679, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6j9tjkk4yi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1158, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6j9tjkk4yi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1337, \"height\": 665, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6j9tjkk4yi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 895, \"height\": 480, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6j9tjkk4yi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1771, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6j9tjkk4yi/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1250, \"height\": 429, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6j9tjkk4yi/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1771, \"height\": 417, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6j9tjkk4yi/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1682, \"height\": 1770, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6j9tjkk4yi/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1681, \"height\": 1772, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6j9tjkk4yi/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1505, \"height\": 2242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6j9tjkk4yi/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1681, \"height\": 2009, \"label\": \"Table\"}]"
motivation: 现有通用时间序列基础模型未能充分处理多源数据的异构表示和领域自适应迁移。
method: 提出分解式统一表示提取方法，并结合自适应迁移机制以捕获领域特征。
result: 在多个跨域下游预测任务中，该模型在不同数据集上均取得优于专门模型的效果。
conclusion: 统一表示与自适应迁移相结合是构建通用时间序列模型的有效方向。
---

## Abstract
With the growing availability of multi-domain time series data, there is an increasing demand for general forecasting models pre-trained on multi-source datasets to support diverse downstream prediction scenarios. Existing time series foundation models primarily focus on scaling up pre-training datasets and model sizes to enhance generalization performance.  In this paper, we take a different approach by addressing two critical aspects of general forecasting models: (1) how to derive unified representations from heterogeneous multi-domain time series data, and (2) how to effectively capture domain-specific features to enable adaptive transfer across various downstream scenarios. To address the first aspect, we propose Decomposed Frequency Learning as the pre-training task, which leverages frequency-based masking and reconstruction to decompose coupled semantic information in time series, resulting in unified representations across domains. For the second aspect, we introduce the Time Series Register, which captures domain-specific representations during pre-training and enhances adaptive transferability to downstream tasks. Our model achieves the state-of-the-art forecasting performance on seven real-world benchmarks, demonstrating remarkable few-shot and zero-shot capabilities.

---

## 论文详细总结（自动生成）

# 论文总结：Towards a General Time Series Forecasting Model with Unified Representation and Adaptive Transfer

## 1. 核心问题与整体含义（研究动机与背景）

- **核心问题**：现有时间序列基础模型主要依赖扩大预训练数据集和模型规模来提升泛化能力，但忽略了两个关键挑战：(1) 如何从异构的多域时间序列中提取**统一表示**；(2) 如何捕获**领域特定特征**并实现自适应迁移到下游任务。
- **研究动机**：多源时间序列具有频率叠加的复杂时序模式，不同域数据的频率分布差异显著，且下游任务所需的领域信息往往与预训练数据中的某些域更为相关。现有模型仅学习通用表示（直接迁移），未能利用域特异性信息，限制了预测精度。
- **整体含义**：本文提出一种轻量级通用时间序列预测模型 **ROSE**，通过解耦频率学习获得统一表示，并引入时序寄存器捕获域特异性信息，实现自适应迁移，在少样本、零样本场景下表现出色。

## 2. 方法论：核心思想、关键技术细节与流程

### 核心思想
- **分解式频率学习（Decomposed Frequency Learning）**：作为预训练任务，通过多频段掩码与重构，将耦合的时序语义信息解耦，学习跨域统一表示。
- **时序寄存器（Time Series Register, TS-Register）**：在预训练中学习并存储各域的域特异性表示；在下游任务中自适应选择最相关的域向量，并通过低秩矩阵微调，实现灵活的自适应迁移。

### 关键技术细节与流程

1. **输入表示**：将输入序列切分为**块令牌（Patch Token）** 与**寄存器令牌（Register Token）**，前者保留局部时序信息，后者携带域特异性信息。
2. **分解式频率学习（预训练任务）**：
   - 使用实数快速傅里叶变换将序列转换至频域。
   - 随机采样 \(K_f\) 个阈值 \(\tau_i\) 与伯努利随机数 \(\mu_i\)，构造多频段掩码矩阵 \(\mathbf{M}\)：若 \(\mu_i=1\) 则掩码高频（高于\(\tau_i\)）；\(\mu_i=0\)则掩码低频（低于\(\tau_i\)）。
   - 将掩码后的频域信号通过逆变换恢复为时域序列，得到 \(K_f\) 个掩码序列。
   - 将这些掩码序列分别分块并输入 Transformer 编码器，输出表示经过**平均聚合**得到统一表示；再经过重构解码器还原原始序列，计算 MSE 损失。
3. **时序寄存器（TS-Register）**：
   - **预训练阶段**：维护可训练寄存器 \(\mathbf{E} \in \mathbb{R}^{H \times D_r}\) 包含 \(H\) 个聚类中心向量。输入时序经线性投影得到嵌入 \(\mathbf{x}_e\)，通过最小化 \(\|\mathbf{x}_e - \mathbf{e}_\delta\|_2^2\) 将其分配到最近簇中心 \(\mathbf{e}_\delta\)（使用 stop gradient 解决 argmin 不可导问题）。该簇中心向量经线性映射变为寄存器令牌，与块令牌拼接输入 Transformer。
   - **微调阶段**：冻结寄存器参数，采用 Top-K 策略选择与输入嵌入最相似的 \(k\) 个簇中心并取平均，得到域特异性表示 \(\mathbf{\bar{e}}_k\)。随后引入可学习低秩矩阵 \(\mathbf{A} = \mathbf{u} \times \mathbf{v}^\top\)（\(\mathbf{u} \in \mathbb{R}^{N_r}, \mathbf{v}\in \mathbb{R}^D\)）与 \(\mathbf{X}_d\) 做 Hadamard 乘积，以补充下游数据集特有信息。
4. **训练目标**：
   - **预训练**：联合优化重构损失、预测损失（四个预测长度 96/192/336/720）和寄存器聚类损失。
   - **微调**：仅使用预测任务，使用对应预测长度的预测头进行微调。

## 3. 实验设计

### 数据集
- **预训练数据集**：收集来自能源、自然、健康、交通、网络、经济等多个域的公开数据集（含 Monash、UEA、UCR 等），总时间点约 8.87 亿。
- **评估数据集**：7 个标准基准——Weather、Traffic、Electricity、ETTh1、ETTh2、ETTm1、ETTm2。
- **Benchmark 设置**：统一回看窗口 \(L=512\)，预测长度 \(\{96, 192, 336, 720\}\)；评估指标 MSE 和 MAE；避免“Drop Last”问题。

### 对比方法
- **全样本/少样本微调**：iTransformer、PatchTST、TimesNet、DLinear、GPT4TS、S2IP-LLM。
- **零样本**：Timer、MOIRAI、Chronos、TimesFM、Moment（共 5 个基础模型）。

## 4. 资源与算力
- 论文明确说明：实验在 **8 张 NVIDIA A800 80GB GPU** 上进行。
- 使用 PyTorch 框架，Adam 优化器，初始学习率 \(5\times10^{-4}\)，StepLR 衰减，批大小 8192。
- **未明确给出具体训练时长**，但提供了参数与推理时间对比（ROSE 约 0.65 秒/样本，远快于大部分基础模型）。

## 5. 实验数量与充分性

- **实验组数**：
  - **全样本微调**（表 1）和**少样本微调（10%）**：在 7 个数据集、4 个预测长度上对比 7 个基线，共 \(7\times4=28\) 种配置。
  - **零样本**（表 2）：在 7 个数据集上对比 5 个基础模型（部分数据集因被用于预训练而省略）。
  - **消融实验**：包含模型组件消融（注册器、预测任务、重构任务；表 3）、掩码方法消融（随机频率掩码、多补丁掩码、补丁掩码等；表 4）、其他预训练任务对比（Aug、Noise；附录表 14）。
  - **效率分析**（图 5）：参数数量、推理时间对比。
  - **可视化分析**（t-SNE、寄存器余弦相似度、预测结果可视化）。
  - **可扩展性分析**（模型规模与数据规模提升实验；附录图 7）。
  - **敏感性分析**（掩码数量、寄存器令牌数、阈值上界、寄存器大小、Top-K 数量；附录图 8-9）。
  - **短时预测**（M4 数据集；附录表 9）。
  - **通用性验证**（频率掩码在 Autoformer/TimesNet/PatchTST 上的提升；附录表 10）。
- **充分性评价**：实验覆盖全面，从全样本到少样本到零样本，消融细致，且控制公平性（统一 drop_last=False，输入长度固定 512）。但未进行更多跨域场景（如金融、医学）或噪声鲁棒性测试。

## 6. 主要结论与发现

1. **ROSE 在全样本微调中平均 MSE 降低 15%**，超越所有 SOTA 基线。
2. **ROSE 在 10% 少样本微调中平均 MSE 降低 12%**，甚至优于一些基线（全样本训练），验证了预训练的有效性与迁移能力。
3. **零样本性能领先**：平均 MSE 比 Timer 低 9%，比 MOIRAI 低 6%，比 Moment 低 43%。
4. **轻量高效**：仅 7.4M 参数，推理时间 0.65 秒，远小于其他基础模型（如 MOIRAI 311M, 7.9 秒），兼顾性能与成本。
5. **寄存器可视化**表明：同一域的数据选择相似的寄存器向量，不同域选择不同，证明自适应迁移有效。
6. **可扩展性**：扩大模型规模或预训练数据均可稳定提升性能。

## 7. 优点

- **创新的预训练范式**：分解式频率学习将多频段掩码与重构结合，有效解耦频率叠加的复杂时序，学习更鲁棒的通用表示。
- **首次在时间序列基础模型中引入寄存器机制**：显式捕获域特异性信息，并通过 Top-K 选择与低秩微调实现自适应迁移，避免“所有域共用同一种表示”的局限。
- **轻量化设计**：参数仅 7.4M，接近专用模型规模，却展现出基础模型的泛化能力，实用性高。
- **全面的实验验证**：覆盖全样本、少样本、零样本、短时预测、模型通用性、可扩展性等，消融充分，可视化直观。
- **报告偏差与置信区间**（附录表 11）：多次重复实验并给出标准差，提升可信度。

## 8. 不足与局限

- **实验场景局限**：主要集中于气象、交通、电力、ETT 等常见域，未涉及金融、医疗、工业等高频低信噪比场景，应用泛化性待验证。
- **未充分证明寄存器相比混合专家模型或注意力路由的本质优势**：仅可视化余弦相似度，缺乏与 MoE 等方法在相同设置下的定量对比。
- **频率掩码策略对长周期序列的适应性**：论文未探讨极长输入（>512）或极低频成分占主导时的性能。
- **零样本对比中的不公平性**：Moment 被强制用于预测（非其设计目标），且部分模型因预训练数据重叠而被排除，可能导致对比有偏。
- **缺乏对预训练数据规模与下游性能之间缩放律的深入探讨**：仅验证 2 个数据量水平，未拟合幂律曲线。
- **训练资源未完全公开**：未说明预训练总 GPU 小时数，可复现性受影响。

（完）
