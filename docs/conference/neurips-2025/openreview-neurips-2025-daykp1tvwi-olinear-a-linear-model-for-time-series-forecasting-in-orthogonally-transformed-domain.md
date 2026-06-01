---
title: "OLinear: A Linear Model for Time Series Forecasting in Orthogonally Transformed Domain"
title_zh: OLinear：正交变换域中的时间序列预测线性模型
authors: "Wenzhen Yue, Yong Liu, Hao Wang, Haoxuan Li, Xianghua Ying, Ruohao Guo, Bowei Xing, Ji Shi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=DAyKP1tvwI"
tags: ["query:qf"]
score: 5.0
evidence: 正交变换域中的线性时间序列预测模型
tldr: OLinear 提出在数据自适应正交变换域中执行线性预测，解决时域中步骤依赖性纠缠问题。与固定基变换相比，线性模型在变换域中更有效，可应用于金融多变量时间序列预测。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 815, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1454, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 727, \"height\": 254, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 596, \"height\": 339, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 658, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1430, \"height\": 797, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1021, \"height\": 733, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1447, \"height\": 1290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1422, \"height\": 1271, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1420, \"height\": 1271, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1423, \"height\": 1273, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1421, \"height\": 1273, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1423, \"height\": 1277, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1411, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1447, \"height\": 645, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-daykp1tvwi/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1454, \"height\": 533, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 609, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1453, \"height\": 555, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1463, \"height\": 587, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1422, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 726, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 455, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1439, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 697, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 691, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 644, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1424, \"height\": 1838, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1443, \"height\": 846, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 802, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1436, \"height\": 556, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1403, \"height\": 578, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1446, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1429, \"height\": 2214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1460, \"height\": 2026, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1458, \"height\": 2180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1452, \"height\": 1722, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1432, \"height\": 1838, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1446, \"height\": 2091, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1435, \"height\": 1823, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1419, \"height\": 1596, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1393, \"height\": 2165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1398, \"height\": 1022, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1456, \"height\": 847, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1422, \"height\": 1206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1354, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1179, \"height\": 2007, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1446, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1454, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1460, \"height\": 556, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1458, \"height\": 1492, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1456, \"height\": 1092, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1436, \"height\": 1313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1423, \"height\": 2229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1443, \"height\": 966, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 1448, \"height\": 966, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 1364, \"height\": 1070, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-041.webp\", \"caption\": \"\", \"page\": 0, \"index\": 41, \"width\": 1455, \"height\": 1453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-daykp1tvwi/table-042.webp\", \"caption\": \"\", \"page\": 0, \"index\": 42, \"width\": 1440, \"height\": 1331, \"label\": \"Table\"}]"
motivation: 时域预测受步骤依赖纠缠限制性能。
method: 提出数据自适应正交变换 OrthoTrans，在变换域进行线性预测。
result: 在多个多元时间序列数据集上超越传统时域线性模型。
conclusion: 变换域线性模型是一种有效的预测范式。
---

## Abstract
This paper presents $\mathbf{OLinear}$, a $\mathbf{linear}$-based multivariate time series forecasting model that operates in an $\mathbf{o}$rthogonally transformed domain. Recent forecasting models typically adopt the temporal forecast (TF) paradigm, which directly encode and decode time series in the time domain. However, the entangled step-wise dependencies in series data can hinder the performance of TF. To address this, some forecasters conduct encoding and decoding in the transformed domain using fixed, dataset-independent bases (e.g., sine and cosine signals in the Fourier transform). In contrast, we propose $\mathbf{OrthoTrans}$, a data-adaptive transformation based on an orthogonal matrix that diagonalizes the series' temporal Pearson correlation matrix. This approach enables more effective encoding and decoding in the decorrelated feature domain and can serve as a plug-in module to enhance existing forecasters. To enhance the representation learning for multivariate time series, we introduce a customized linear layer, $\mathbf{NormLin}$, which employs a normalized weight matrix to capture multivariate dependencies. Empirically, the NormLin module shows a surprising performance advantage over multi-head self-attention, while requiring nearly half the FLOPs. Extensive experiments on 24 benchmarks and 140 forecasting tasks demonstrate that OLinear consistently achieves state-of-the-art performance with high efficiency. Notably, as a plug-in replacement for self-attention, the NormLin module consistently enhances Transformer-based forecasters. The code and datasets are available at https://github.com/jackyue1994/OLinear.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义（研究动机和背景）

- **核心问题**：传统时域预测（TF）直接对时间序列进行编码和解码，但序列中相邻步骤之间的依赖关系通常高度纠缠，这限制了模型捕捉长期依赖和去相关特征的能力。已有的频域或小波域方法采用固定的、与数据无关的基（如傅里叶基），没有利用数据集中特有的时间相关结构。

- **整体含义**：本文提出在**数据自适应正交变换域**中执行线性预测，通过去除步骤间的线性相关性，使学习过程更简单、高效。同时设计了一个类似注意力的线性层 **NormLin**，以更低的计算成本实现跨变量依赖建模，最终构建出 **OLinear** 模型。

### 论文提出的方法论

- **核心思想**：利用训练集的时间 Pearson 相关矩阵的特征分解构造正交矩阵，将原始序列投影到去相关的特征域（即正交变换域），在该域中进行线性的跨变量学习和时序学习，再将预测结果变换回时域。

- **关键技术细节**：
  - **OrthoTrans**：计算变体平均的时间相关矩阵 `CorrMat_t`，进行特征分解得到正交矩阵 `Q_i`（输入侧）和 `Q_o`（输出侧）。变换后的特征向量线性不相关。
  - **NormLin 层**：对可学习权重矩阵 `W` 依次应用 Softplus 激活和行 L1 归一化，使权重为正且行和为 1（类似注意力权重），然后直接乘输入。该层用于跨变量学习模块（CSL）。
  - **整体流程**：输入 → RevIN → 维度扩展 → 左乘 `Q_i^T` 进入正交域 → 线性编码 → 交替堆叠 CSL（含 NormLin）和 ISL（含 GELU 的 MLP） → 线性解码 → 右乘 `Q_o` 回到时域 → 展平线性映射 → RevIN 逆归一化输出。

- **公式与算法**（文字说明）：
  - 正交变换：`Z = (RevIN(X) ⊗ φ_d) Q_i^T`，其中 `⊗` 为外积。
  - 表示学习：`˜H_l+1 = ISL( CSL( ˜H_l ))`。
  - 解码：`˜Y = LinearDecode(˜H_L) · Q_o`。
  - NormLin：`NormLin(x) = RowNormL1(Softplus(W)) x`，`W∈R^{N×N}`。

### 实验设计

- **数据集**：共 24 个真实世界基准，包括 ETT（4 子集）、Weather、ECL、Traffic、Exchange、Solar-Energy、PEMS（4 子集）、ILI、COVID-19、METR-LA、NASDAQ、Wiki、SP500、DowJones、CarSales、Power、Website、Unemp。覆盖电力、交通、能源、金融、健康、Web 等多领域。
- **预测场景**：长时预测（回看 96，预测 96/192/336/720 或 PEMS 的 12/24/48/96）和短时预测（回看 12 预测 3/6/9/12，回看 36 预测 24/36/48/60），共 140 个任务。
- **对比方法**：11 个 SOTA 模型，包括线性类（TimeMixer、FilterNet、FITS、DLinear）、Transformer 类（TimeMixer++、Leddam、CARD、Fredformer、iTransformer、PatchTST）、TCN 类（TimesNet）。此外还与注意力变体（Reformer、Flowformer、Mamba 等）以及大规模预训练模型 Timer 比较。

### 资源与算力

- 文中未明确说明使用的 GPU 型号、数量及总训练时长。
- 附录 K 中提供了详细的训练时间（ms/iter）和 GPU 内存占用（GB），OLinear 在大部分数据集上训练时间低于基线，内存占用适中。例如：ECL 上 OLinear 训练 7.75 ms/iter，显存 0.45 GB；大模型如 TimesNet 显存占用高达 5.82 GB。
- 所有实验在单卡 24 GB 的 NVIDIA GPU 上完成（来源：Implementation details 中提及）。

### 实验数量与充分性

- **数量**：极大规模——24 个数据集、140 个预测任务，主实验结果（表 2、3）已覆盖；附录中还包含 40+ 个补充表格。
- **充分性**：
  - **消融研究**：考察变换基（Fourier、Wavelet、多项式 vs OrthoTrans）、NormLin 设计（激活函数、归一化方式、pre/post 线性层）、Q 矩阵（Qi/Qo）等。
  - **鲁棒性**：7 个随机种子下的标准偏差和 99% 置信区间，与 TimeMixer++、iTransformer 对比，OLinear 波动更小。
  - **泛化性**：小样本（5% 训练数据）、零样本、变化回看长度（48∼720）、不同训练数据比例等。
  - **即插即用**：将 OrthoTrans 和 NormLin 分别插入 iTransformer、PatchTST 等模型，性能提升。
- **公平性**：与多个 SOTA 模型对比，使用官方代码或原论文结果，超参数调优，损失函数统一为加权 L1 损失。

### 论文的主要结论与发现

1. **OLinear 达到 SOTA**：在 23/24 个数据集上平均 MSE/MAE 优于所有对比方法，且计算效率高。
2. **OrthoTrans 有效**：比固定基变换（Fourier、小波等）提升明显，作为即插即用模块可增强现有模型（如 iTransformer 提升 3.97% MSE）。
3. **NormLin 超越自注意力**：在 OLinear 中，NormLin 模块相比自注意力在 8 个数据集上平均 MSE 更低，FLOPs 减少约 50%；作为即插即用替换，也一致提升 Transformer 模型。
4. **NormLin 可扩大规模**：在大模型 Timer 中替换自注意力（含因果掩码）后，零样本和小样本场景均提升，证明了其适用于预训练范式。

### 优点

- **方法简洁高效**：纯线性架构，避免了复杂的注意力机制，训练和推理速度快，显存占用低。
- **数据自适应变换**：OrthoTrans 利用了数据集特定的时间相关结构，提供了物理可解释性（能量集中、去相关）。
- **即插即用**：两个核心模块均可独立嵌入现有模型，广泛兼容。
- **实验极其充分**：覆盖多领域、多场景，消融和泛化实验全面，结果可靠。
- **开源代码**：便于复现和后续研究。

### 不足与局限

- **实验范围局限**：仅聚焦时间序列预测，未在插补、异常检测等其他任务验证。
- **复杂度**：NormLin 仍为 `O(N^2)`，对极大变量数（如 >10000）可能成为瓶颈；文中提及可探索更简单替代。
- **预计算**：OrthoTrans 需要从训练集预计算相关矩阵和特征分解，额外开销一次，但后续实验表明少量数据（10%）也可获得良好结果。
- **长期序列**：正交矩阵大小与回看窗口 `T` 相关，`T` 过大时计算和存储成本增加，文中未测试超长回看（>720）。
- **超参数敏感**：图 17 显示不同数据集对学习率和模型维度偏好不同，可能需要调参。
- **论文未讨论**：对非平稳序列的适应性、误差累积等问题。

（完）
