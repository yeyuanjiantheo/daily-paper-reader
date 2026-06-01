---
title: "WAVE: Weighted Autoregressive Varying Gate for Time Series Forecasting"
title_zh: WAVE：加权自回归变门控时间序列预测
authors: "Jiecheng Lu, Xu Han, Yan Sun, Shihao Yang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Qqn5ktBUxH"
tags: ["query:qf"]
score: 7.0
evidence: 将ARMA结构融入注意力机制进行时间序列预测，与GARCH、HAR等波动率模型密切相关
tldr: 时间序列预测中，传统注意力机制难以同时捕捉长程和局部模式。本文提出WAVE注意力，受ARMA模型启发，在注意力中引入自回归和滑动平均成分，增强对时序模式的解耦捕获。实验表明，采用适当token化和训练方法的解码器自回归Transformer在预测任务上可达到最佳基线水平。该ARMA结构可直接迁移至金融波动率模型的深度学习实现。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1748, \"height\": 485, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 830, \"height\": 312, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 823, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 831, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1742, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1727, \"height\": 764, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1260, \"height\": 2264, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1714, \"height\": 956, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1377, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1376, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1378, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1402, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1388, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1395, \"height\": 628, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1384, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1385, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1391, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1386, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1386, \"height\": 622, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqn5ktbuxh/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1388, \"height\": 623, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-qqn5ktbuxh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1776, \"height\": 370, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqn5ktbuxh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 498, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqn5ktbuxh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1764, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqn5ktbuxh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1761, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqn5ktbuxh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1761, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqn5ktbuxh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 850, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqn5ktbuxh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1774, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqn5ktbuxh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1240, \"height\": 2032, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqn5ktbuxh/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1761, \"height\": 1324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqn5ktbuxh/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 876, \"height\": 2165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqn5ktbuxh/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1761, \"height\": 749, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqn5ktbuxh/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1745, \"height\": 1392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqn5ktbuxh/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1762, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqn5ktbuxh/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1764, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqn5ktbuxh/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1321, \"height\": 610, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqn5ktbuxh/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1310, \"height\": 914, \"label\": \"Table\"}]"
motivation: 现有注意力机制在时间序列预测中难以兼顾长期和局部时序模式。
method: 在自回归注意力中嵌入完整的ARMA结构，包括加权自回归和滑动平均门控。
result: 在多个时间序列基准上，WAVE增强的模型在长短期预测均优于或持平强基线。
conclusion: ARMA结构可有效增强注意力模型的时间序列预测能力，适用于波动率建模等金融任务。
---

## Abstract
We propose a Weighted Autoregressive Varying gatE (WAVE) attention mechanism equipped with both Autoregressive (AR) and Moving-average (MA) components. It can adapt to various attention mechanisms, enhancing and decoupling their ability to capture long-range and local temporal patterns in time series data. In this paper, we first demonstrate that, for the time series forecasting (TSF) task, the previously overlooked decoder-only autoregressive Transformer model can achieve results comparable to the best baselines when appropriate tokenization and training methods are applied. Moreover, inspired by the ARMA model from statistics and recent advances in linear attention, we introduce the full ARMA structure into existing autoregressive attention mechanisms. By using an indirect MA weight generation method, we incorporate the MA term while maintaining the time complexity and parameter size of the underlying efficient attention models. We further explore how indirect parameter generation can produce implicit MA weights that align with the modeling requirements for local temporal impacts. Experimental results show that WAVE attention that incorporates the ARMA structure consistently improves the performance of various AR attentions on TSF tasks, achieving state-of-the-art results.

---

## 论文详细总结（自动生成）

# WAVE：加权自回归变门控时间序列预测 — 中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：时间序列预测（TSF）中的注意力机制（如标准 softmax 注意力、线性注意力、门控线性注意力等）在捕获长程依赖和局部模式时存在能力不足或失衡的问题。例如，门控线性注意力中的指数衰减因子虽增强了局部建模，但会削弱对稳定季节性等长程模式的捕获。现有 TSF 研究多集中于编码器-解码器或编码器-only 结构，对解码器-only 自回归 Transformer 的关注较少，且其性能是否可与 SOTA 基线匹敌尚待验证。
- **背景**：经典的 ARMA（自回归滑动平均）模型在统计时序分析中能同时处理历史数据和预测误差的累积影响，从而解耦长短期效应。受此启发，论文尝试将完整的 ARMA 结构引入注意力机制，以提升 TSF 性能。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 将经典的 ARMA 模型结构嵌入现有的自回归注意力机制中，使注意力输出同时包含自回归（AR）项和滑动平均（MA）项。
- 通过**间接 MA 权重生成**方法，在保持线性注意力 O(N) 时间复杂度和原始参数量（通过权重共享）的前提下，实现 MA 项的高效计算。

### 关键技术细节
1. **基础 AR 注意力形式**：各种注意力（softmax、线性、元素级线性、门控线性、固定权重）均可表示为对过去值 vi 的加权和：  
   `oAR_t = Σ_{i=1}^{t} w_{t,i} ⊙ v_i`
2. **引入 MA 项**：将 AR 误差扩展为 MA 形式，得到完整 ARMA 输出：  
   `v_{t+1} = oAR_t + oMA_t + ϵ_t`，其中 `oMA_t = Σ_{j=1}^{t-1} θ_{t-1,j} ⊙ ϵ_j`
3. **间接 MA 权重生成**：为避免显式计算 Θ 矩阵（复杂度 O(N²)），利用线性注意力的高效性，将 MA 项的计算转化为对残差 r_j = v_{j+1} - oAR_j 的加权和，即：  
   `oMA_t ≈ Σ_{j=1}^{t-1} β_{t-1,j} ⊙ r_j`  
   其中 β 通过 query 和 key 的 kernel 函数生成：`β_{t-1,j} = ϕ_q(qMA_{t-1}) ϕ_k(kMA_j)`。通过选择合适的激活函数（ϕ_q 使用负 LeakyReLU，ϕ_k 使用缩放 sigmoid），确保隐式 MA 权重 Θ 呈对角线附近大、远处衰减的特性，从而有效捕获短期效应。
4. **权重共享与复杂度**：AR 和 MA 共享 W_q，并将 W_v 设为恒等矩阵，使 WAVE 参数量与纯 AR 模型相同。计算复杂度仍为 O(N d²)，线性于序列长度。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：12 个广泛使用的真实时间序列数据集，包括 Weather、Solar、Electricity (ECL)、ETTs (ETTh1, ETTh2, ETTm1, ETTm2)、Traffic、PEMS (PEMS03, PEMS04, PEMS07, PEMS08)。
- **预测长度**：主要实验采用 `LP ∈ {12, 24, 48, 96}`，长程预测扩展到 `LP ∈ {96, 192, 336, 720}` 和更长的输入长度 `LI ∈ {512, 1024, 2048, 4096}`。
- **对比方法**：
  - **纯 AR Transformers**：使用 5 种注意力机制（标准 softmax 注意力、线性注意力、元素级线性注意力、门控线性注意力、固定注意力）。
  - **WAVE 增强版**：对应加上 MA 项的 WAVE 注意力。
  - **外部基线**：FITS、iTransformer、CATS、PatchTST、DLinear、Encoder-only Transformer（修改版）、MEGA（专门对比）、TimesNet（消融实验中添加）。
- **评价指标**：MSE 和 MAE，报告平均测试集结果及平均排名、第一名次数。

## 4. 资源与算力

论文明确说明：所有训练任务均可使用**单张 Nvidia RTX 4090 GPU** 完成。此外，文中给出了 ETTm1 上的 FLOPs 和参数量对比表：纯 AR/WAVE 模型 FLOPs 在 7~47M 之间、参数量约 45~50K，远小于传统基线（如 EncFormer 的 1.6M 参数、FLOPs 1.2G+）。未提及具体训练时长。

## 5. 实验数量与充分性

- **实验数量**：非常充分。主实验包含 12 个数据集 × 4 种预测长度 × (5 种 AR 注意力 + 5 种 WAVE + 6 种外部基线) 共 48×16 = 768 个实验点（加上消融和长程预测等总计超过 1000 个实验配置）。附录中提供了所有完整结果表格（表 8-16）。
- **实验充分性**：
  - 对比了多种注意力机制及不同层数（m=1~8），证明 WAVE 提升归因于结构而非参数增加。
  - 长输入消融：LI 从 512 到 4096，AR/WAVE 性能提升，基线下降。
  - 消融实验包括：去掉 AR 损失、多变量 tokenization、与 MEGA 对比、不同随机种子下的稳定性。
  - 可视化分析：展示了注意力权重矩阵 B 和 Θ，验证了 MA 权重有效聚焦局部效应。
- **公平性**：所有模型使用相同优化器（AdamW）、相同数据划分，基线超参数按原论文设置，且 AdamW 训练基线比原论文默认 Adam 效果更好，故基线结果可能比原文更高。

## 6. 论文的主要结论与发现

1. 通过合适的 tokenization（PatchTST 样式非重叠分片）和训练方法，解码器-only 自回归 Transformer 可达到现有 SOTA 基线的水平。
2. WAVE 注意力（ARMA 结构）在**所有 5 种注意力机制**上均一致且显著地提升 TSF 性能，线性注意力 + WAVE 获得最佳平均排名（2.333）和最多第一名次数（25）。
3. 门控线性注意力提升最大（因其原本过度衰减长程信息，MA 项补足局部效应）。
4. WAVE 在长输入（LI 达 4096）性能持续提升，而基线普遍退化。
5. 与 MEGA（使用 EMA）相比，WAVE 更优，说明全 ARMA 结构比简单 EMA 更有效。
6. 可视化确认 AR 权重专注于长程/周期模式，MA 权重捕获短期波动，实现了有效解耦。
7. WAVE 的计算开销（FLOPs、参数量）与对应 AR 模型几乎相同，优于大部分基线。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：首次将完整 ARMA 结构引入主流注意力机制，通过间接权重生成技巧保持线性复杂度，设计巧妙。
- **理论分析**：给出了隐式 MA 权重的闭式解（简化后 θ_ij = b(1+b)^(i-j-1)），并据此指导激活函数选择（负 LeakyReLU + 缩放 sigmoid），使权重符合短期效应衰减规律。
- **实验全面**：覆盖 12 个数据集、多种注意力、多种超参数（层数、输入长度、预测长度），消融实验和可视化丰富，结论稳健。
- **公平对比**：统一优化器，基线性能甚至比原论文更高；权重共享确保 WAVE 参数不增加；对比了纯 AR 模型在相同层数下的表现，说明提升来自结构而非计算量。
- **资源消耗低**：所有实验在单张 RTX 4090 即可完成，模型轻量（< 50K 参数），实用性强。

## 8. 不足与局限

- **未探索多变量间的通道依赖**：当前采用 channel-independent 方法，未将 WAVE 扩展到考虑跨序列关系的多变量预测模型。
- **仅聚焦 TSF**：论文指出未来可推广到 NLP 等更通用的序列建模任务，但本文未验证。
- **训练细节**：使用了 next-token loss 加权（最后 token 乘以 N），该技巧仅在小数据集（ETTs）有细微影响，但未充分讨论其普遍必要性。
- **激活函数选择依赖启发式**：虽然理论分析和实验验证了负 LeakyReLU 的有效性，但缺乏对更多激活函数的系统搜索。
- **计算效率**：虽然复杂度同阶，但两阶段结构（先算 AR 再算 MA）仍会引入常数倍额外计算，对于超长序列的实时推理可能带来开销。

（完）
