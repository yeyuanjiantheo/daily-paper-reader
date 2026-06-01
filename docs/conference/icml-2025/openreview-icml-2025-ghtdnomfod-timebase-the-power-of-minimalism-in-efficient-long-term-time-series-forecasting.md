---
title: "TimeBase: The Power of Minimalism in Efficient Long-term Time Series Forecasting"
title_zh: TimeBase：极简主义在高效长期时间序列预测中的力量
authors: "Qihe Huang, Zhengyang Zhou, Kuo Yang, Zhongchao Yi, Xu Wang, Yang Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=GhTdNOMfOD"
tags: ["query:qf"]
score: 6.0
evidence: 提出基于低秩结构的超轻量网络用于长期时间序列预测
tldr: 长期时间序列预测传统上需要大参数，但数据常具有低秩结构。TimeBase通过提取核心基础时间分量，将传统预测转化为轻量方法，在保持精度的同时大幅降低计算成本。为金融时间序列中的高效预测提供了新方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ghtdnomfod/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1589, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ghtdnomfod/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1577, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ghtdnomfod/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1661, \"height\": 671, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ghtdnomfod/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1755, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ghtdnomfod/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1761, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ghtdnomfod/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 874, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ghtdnomfod/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1065, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ghtdnomfod/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1759, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ghtdnomfod/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1690, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ghtdnomfod/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 883, \"height\": 359, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ghtdnomfod/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 796, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ghtdnomfod/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1771, \"height\": 1058, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ghtdnomfod/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1497, \"height\": 533, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ghtdnomfod/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1414, \"height\": 1224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ghtdnomfod/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 629, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ghtdnomfod/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1761, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ghtdnomfod/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 839, \"height\": 429, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ghtdnomfod/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1242, \"height\": 433, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ghtdnomfod/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 879, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ghtdnomfod/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1766, \"height\": 2126, \"label\": \"Table\"}]"
motivation: 传统LTSF模型参数大，效率低，但时间序列具有低秩和模式相似性。
method: 提取核心基础时间分量，将预测转化为低维变换。
result: TimeBase在多个数据集上以极少数参数达到竞争性能。
conclusion: 利用低秩结构可实现准确且高效的时间序列预测。
---

## Abstract
Long-term time series forecasting (LTSF) has traditionally relied on  large parameters to capture extended temporal dependencies, resulting in substantial computational costs and inefficiencies in both memory usage and processing time. 
However, time series data, unlike high-dimensional images or text, often exhibit temporal pattern similarity and  low-rank structures, especially in long-term horizons.  By leveraging this structure, models can be guided to focus on more essential, concise temporal data, improving both accuracy and computational efficiency. In this paper, we introduce TimeBase, an ultra-lightweight network  to harness the power of minimalism in LTSF.  TimeBase 1) extracts core basis temporal components and 2) transforms traditional point-level forecasting into efficient segment-level forecasting, achieving optimal utilization of both data and parameters. Extensive experiments on diverse  real-world datasets show that TimeBase achieves remarkable efficiency and secures competitive forecasting performance. Additionally, TimeBase can also serve as a very effective plug-and-play complexity reducer for any patch-based forecasting models. Code is available at \url{https://github.com/hqh0728/TimeBase}.

---

## 论文详细总结（自动生成）

# TimeBase：极简主义在高效长期时间序列预测中的力量——论文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **问题**：长期时间序列预测（LTSF）传统模型（如Transformer、MLP）参数庞大（百万级），计算和存储开销高。这些模型借鉴了CV/NLP大模型理念，但时间序列数据与高维图像/文本不同，具有**时序模式相似性**和**低秩结构**，尤其在长期预测中冗余信息丰富。
- **动机**：探索是否真的需要大量参数来学习这些规则模式？提出极简主义路线——利用数据内在结构，用极小模型实现高效且准确的预测。
- **含义**：TimeBase是目前已知最轻量的LTSF模型（仅0.39K参数），同时达到SOTA级性能，并可作为即插即用的复杂度缩减模块。

## 2. 方法论：核心思想、关键技术细节、算法流程

### 核心思想
- **基分量提取（Basis Component Extraction）**：利用时间序列的低秩性，通过学习少量“基础时间模式”（basis components）来表示整个序列的片段级变化。
- **分段级预测（Segment-level Forecasting）**：将传统点级预测转化为对分段（segment）的预测，大幅简化模型。

### 关键技术细节
1. **分段（Segment）**：
   - 根据数据先验周期（如P=24小时）或FFT分析确定分段长度P。
   - 将历史序列X∈R^T划分为N=⌈T/P⌉个非重叠段，得到矩阵X_his∈R^{N×P}。
2. **基分量提取**：
   - 用线性层实现：X_basis = BasisExtract(X_his) = W_his·X_his + B_his，其中X_basis∈R^{R×P}，R≪min(N,P)为基础分量个数。
   - 理论基础：矩阵低秩分解，任意段可由基分量线性组合近似。
3. **分段级预测**：
   - 用另一线性层将基分量映射到未来段：X_pred = SegmentForecast(X_basis)，X_pred∈R^{N'×P}，N'=⌈L/P⌉。
   - 最终展开为预测序列Y∈R^L。
4. **正交约束**：
   - 对基分量施加正交正则化 L_orth = ||X_basis^T X_basis - diag(·)||_F^2，鼓励各基分量去冗余，增强表达能力。
   - 总损失 L = L_prediction + λ_orth * L_orth。

### 公式（文字说明）
- 参数规模定理：参数总量 = R×P×T/P + R + 1×L/P + R，即线性于T和L。
- 相比DLinear（O(TL)）和SparseTSF（O(TL/P²)），TimeBase复杂度更低，且R通常很小（如6）。

## 3. 实验设计

### 数据集
- **17个正常规模基准**：ETTh1/h2、ETTm1/m2、Weather、Electricity、Traffic、Solar、Wind、METR-LA、Exchange Rate、AQShunyi/Wan、ZafNoo/CzeLan、PM2.5、Temp。
- **4个大规模数据集**：CA (4.52B点)、GLA (2.02B)、GBA (1.24B)、SD (0.38B)。
- 数据集划分：ETT、大规模为6:2:2；其余7:1:2。

### 基准方法（10个SOTA）
- 轻量：SparseTSF (1K参数)、FITS (10K参数)、DLinear (~1M)
- 强大：TimeMixer、iTransformer、PatchTST、TimesNet、FEDformer、Autoformer、Informer
- **统一设置**：所有模型输入长度720，输出长度96/192/336/720。

### 对比场景
- 主实验：17个数据集×4个预测长度，报告平均值。
- 大规模数据集实验。
- 效率对比（参数、MACs、内存、训练/推理时间）。
- 超长回溯窗口（720→6480）评估。
- 作为PatchTST插件（7个数据集×4长度）。
- 消融（正交约束）、超参数（R、λ_orth、段长P）分析。
- 合成数据验证、进一步预测（1080/1440/1800）、多季节扩展。

## 4. 资源与算力

- **论文未明确说明**使用的GPU型号、数量或总训练时长（小时/天）。
- 提供了详细效率指标：
  - 参数：0.39K
  - MACs：2.77M（Electricity, L=720）
  - 训练时间：20.6秒/epoch
  - 推理时间：0.98ms（CPU）
  - 峰值内存：88.89MB（batch_size=12）
- 超长窗口测试显示运行时间、内存、参数增长缓慢（9倍窗口仅增0.05秒/iter）。

## 5. 实验数量与充分性

- **总量**：主表（Table 2）覆盖17个数据集×4个预测长度×10个对比模型，共680个度量（MSE/MAE）。Table 5覆盖4大规模×4长度。
- **效率**：Table 3对比8个指标（参数、MACs、内存等），Table 4展示7个数据集×4长度的插件效果。
- **消融**：正交约束有效性（Figure 8，4个数据集×4长度），超参数R（Figure 6），λ_orth（Figure 5），段长P（Figure 9）。
- **扩展**：合成数据、超长预测、多季节、大规模数据。
- **充分性评价**：实验设计全面，覆盖多种尺度、领域和场景。统一输入长度、修正测试loader bug，确保公平。消融分析完整。但未提供统计显著性检验（如置信区间或多次运行标准差）。

## 6. 主要结论与发现

- **TimeBase以0.39K参数和2.77M MACs达到了SOTA级预测性能**：在17个正常数据集中，16个进入Top2，平均MSE/MAE优于SparseTSF、FITS、DLinear、TimeMixer、iTransformer等。
- **效率极优**：相比最轻的SparseTSF，参数减少61%，MACs减少78%，内存减少29%，训练时间减少34%。
- **即插即用有效**：作为PatchTST插件，MACs降低77.74%~93.03%，参数降低56.95%~91.43%，且预测精度几乎无损甚至略有提升（平均MSE降低1.27%）。
- **泛化良好**：在超长回溯、超长预测、大规模数据、多季节场景中均有效。
- **设计启示**：利用低秩结构和分段预测，为未来高效LTSF模型提供了新思路。

## 7. 优点

1. **极轻量**：参数仅0.39K，适合边缘设备部署。
2. **效率极高**：计算复杂度和存储开销远低于现有方法。
3. **竞争性能**：在多数数据集上达到Top2，不因轻量牺牲精度。
4. **即插即用**：可无缝集成到任何基于patch的模型，显著降低复杂度且不影响性能。
5. **理论支撑**：提供泛化误差上界，说明基分量质量对误差的影响。
6. **正交约束创新**：增强基分量多样性，提升表示能力。
7. **充分消融**：验证了关键超参数和模块的有效性。
8. **大规模验证**：在10亿级数据集上仍保持优秀效率与精度。

## 8. 不足与局限

1. **依赖周期性先验**：段长P需基于数据先验周期或FFT确定，对非平稳或变化周期数据可能不合适。
2. **Channel Independence简化**：将多变量分解为单变量，忽略跨变量相关性，可能损失信息（但文中称多元序列常均质）。
3. **超参数敏感**：λ_orth最优值因数据集而异，需调参。
4. **未提供统计显著性**：实验未报告多次运行的标准差或置信区间，结果稳定性难以评估。
5. **设置局限**：仅测试单变量预测场景（CI策略），未验证多变量直接预测；最大预测长度1800，未测试更极端场景。
6. **缺乏计算资源细节**：未提及GPU型号、训练总时长，无法准确复现计算成本。
7. **理论中泛化上界依赖于λ_min(EE^T)**，但实际中难以保证该值较大，且未在实验中验证。

（完）
