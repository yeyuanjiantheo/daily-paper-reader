---
title: "Shifting Time: Time-series Forecasting with Khatri-Rao Neural Operators"
title_zh: 时间平移：基于Khatri-Rao神经算子的时间序列预测
authors: "Srinath Dama, Kevin Course, Prasanth B. Nair"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=emkdmORaj4"
tags: ["query:qf"]
score: 6.0
evidence: 基于连续时间平移算子的时间序列预测
tldr: 本文提出基于算子学习的时间序列预测框架，通过学习连续时间平移算子，利用Khatri-Rao神经算子实现近乎线性的计算复杂度。该方法能够处理不规则采样观测，并实现时空超分辨率预测。在多个时空数据集上取得了卓越性能，为金融时间序列中的高频或缺失数据处理提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 803, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 834, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 837, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 837, \"height\": 711, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 816, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 423, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1039, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1729, \"height\": 910, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1770, \"height\": 1653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1770, \"height\": 1617, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1711, \"height\": 784, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 899, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1699, \"height\": 1996, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1708, \"height\": 1206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1715, \"height\": 1202, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1715, \"height\": 1202, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-emkdmoraj4/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1707, \"height\": 1205, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-emkdmoraj4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 843, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-emkdmoraj4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 735, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-emkdmoraj4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 842, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-emkdmoraj4/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1337, \"height\": 800, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-emkdmoraj4/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1241, \"height\": 755, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-emkdmoraj4/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 790, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-emkdmoraj4/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 840, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-emkdmoraj4/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1594, \"height\": 1569, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-emkdmoraj4/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1679, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-emkdmoraj4/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1679, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-emkdmoraj4/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1088, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-emkdmoraj4/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1407, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-emkdmoraj4/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1773, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-emkdmoraj4/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1401, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-emkdmoraj4/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1432, \"height\": 546, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-emkdmoraj4/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 700, \"height\": 258, \"label\": \"Table\"}]"
motivation: 传统自回归模型受限于离散滞后因子，无法处理不规则采样。
method: 学习连续时间平移算子，并用Khatri-Rao神经算子参数化。
result: 在多个时空预测任务上表现优异，支持超分辨率预测。
conclusion: 为时间序列预测提供了灵活的算子学习范式。
---

## Abstract
We present an operator-theoretic framework for temporal and spatio-temporal forecasting based on learning a *continuous time-shift operator*. Our operator learning paradigm offers a continuous relaxation of the discrete lag factor used in traditional autoregressive models, enabling the history of a system up to a given time to be mapped to its future values. We parametrize the time-shift operator using Khatri-Rao neural operators (KRNOs), a novel architecture based on non-stationary integral transforms with nearly linear computational scaling. Our framework naturally handles irregularly sampled observations and enables forecasting at super-resolution in both space and time. Extensive numerical studies across diverse temporal and spatio-temporal benchmarks demonstrate that our approach achieves state-of-the-art or competitive performance with leading methods.

---

## 论文详细总结（自动生成）

# 中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

时间序列预测是机器学习和统计学中的基础问题，广泛应用于科学、工程和金融等领域。传统方法主要分为两类：自回归移动平均模型及其变体，以及基于记忆的深度自回归模型（如LSTM、Transformer）。这些方法普遍要求观测数据以恒定频率采样，这在实践中带来诸多挑战：（1）当观测间隔不规则时，通常需要近似插值或填补缺失值，这会引入额外误差；（2）在线场景中，传感器故障或系统延迟导致的缺失数据需要预处理管道，增加了系统复杂度。尽管神经ODE等方法能够处理不规则采样，但难以扩展到大规模时空数据。

本文提出将时间序列预测问题转化为学习**连续时间平移算子**的监督学习任务。该算子将系统在**过去时间窗口**内的整个连续历史映射到**未来时间窗口**内的演化，是对传统离散滞后因子的一种连续松弛。这一算子理论框架能够自然处理不规则采样观测，并在空间和时间上实现超分辨率预测，同时保持神经算子训练的稳定性。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **连续时间平移算子**：对于ODE系统 $\dot{z}(t)=F(z(t))$，定义算子 $\mathcal{A}_{t,p}^{t_f}$ 将 $z$ 在 $[t_p, t]$ 上的历史映射到 $(t, t_f]$ 上的未来值。该算子满足半群性质和连续性质，理论上可由Picard-Lindelöf定理保证存在性。对于时空系统，类似地定义时空时间平移算子。

- **Khatri-Rao神经算子（KRNO）**：为参数化时间平移算子，提出KRNO架构。其核心是**非平稳积分变换层**，假设核函数分解为元素级乘积形式：$\kappa(\{t,x\},\{t',x'\}) = \kappa^{(1)}(t,t') \odot \bigodot_{i=2}^d \kappa^{(i)}([x]_{i-1}, [x']_{i-1})$。当离散节点位于乘积网格上时，核矩阵具有Khatri-Rao积结构，从而将计算复杂度从 $O(N^2)$ 降至 $O(N^{1+1/d})$（$N$ 为节点总数，$d$ 为时空维度），且无需近似核函数，实现精确的非平稳核评估。

- **算法流程**：将时间序列数据转化为输入输出序列对（过去窗口 $[t_p,t]$ 和预测窗口 $(t,t_f]$），使用KRNO学习映射，损失函数为MSE。KRNO结构包含多个积分变换层（默认3层，每层20个通道），以及提升/投影MLP层。各分量核网络 $\kappa^{(i)}$ 由神经网络参数化，并采用输入变换和跳跃连接。

## 3. 实验设计：使用的数据集 / 场景、benchmark、对比方法

论文涵盖**39个测试用例或误差指标**，包括：

- **空间建模问题**：Darcy流（稳态）、超弹性材料（应力预测），对比FNO、DeepONet。
- **时空预测问题**：
  - 浅水模拟：在32×32网格上预测流体柱高度、两个速度场，对比FNO-3D和LOCA。
  - 气候建模：表面气温和气压，在72×72空间网格上做7天回看、7天预测，对比方法未列出但给出了误差图。
- **不规则采样时间序列**：MIMIC-III（医疗）、USHCN（气候）、Human Activity（人体活动）、MuJoCo（Hopper模拟），对比DLinear、TimesNet、PatchTST、Crossformer、Graph Wavenet、StemGNN、T-PatchGNN、Latent-ODE、CRU、Neural Flow等15+种SOTA方法。
- **规则采样时间序列**：
  - Darts数据集：8个单变量序列，对比ARIMA、TCN、N-BEATS、N-HiTS、SM-GP、LLaMA-2、GPT-3等。
  - M4数据集：6种季节性的100,000个序列，对比Montero、Smyl、Nbeats-I+G、KNF等。
  - Crypto（14种加密货币收益率）和Player Trajectory（NBA球员位置），对比VARIMA、MLP、FedFormer、LEM、KNF等。

## 4. 资源与算力

论文中提到所有计算在**单个Nvidia RTX 4090 GPU（24GB内存）**上完成。未明确说明训练总时长或每个实验的具体训练时间，但提到对于浅水问题KRNO训练100个epoch（使用默认批量大小为8），并且给出了不同分辨率下的训练/推理时间（例如32×32网格每迭代0.0279秒）。整体算力开销适中。

## 5. 实验数量与充分性

- **实验数量**：共39个测试用例，涵盖静态空间映射、时空预测、规则/不规则时间序列，数据类型包括物理模拟、气候、医疗、金融、运动轨迹等，覆盖面广。
- **充分性**：每个实验均报告了多次运行的均值与标准差（如表4、表5），并采用标准评价指标（L2相对误差、MSE、MAE、sMAPE、NMAE、RMSE等）。在大部分基准上，KRNO取得最优或前三名，且在某些数据集上（如MIMIC、USHCN、MuJoCo、浅水）大幅超越现有方法。对比方法包括传统统计模型、各类深度学习模型（Transformer、GNN、神经ODE、神经SDE等），对比全面。
- **公平性**：论文公开代码（https://github.com/srinathdama/ShiftingTime），超参数通过验证集网格搜索确定，并采用常见的训练/验证/测试划分。但缺少针对不同方法之间的超参数调优细节对比（如是否对基线方法也进行了同等调优），可能存在一定偏差。

## 6. 论文的主要结论与发现

1. **连续时间平移算子**框架提供了一种鲁棒且灵活的方式来处理不规则采样观测，并支持时空超分辨率预测。
2. **KRNO**通过Khatri-Rao积结构实现了近乎线性的计算复杂度，同时保持核函数的精确非平稳评估，参数效率远高于FNO（例如浅水问题中KRNO的参数数仅为FNO-3D的6%）。
3. 在39个测试用例中，KRNO在**17个上取得最佳性能，在30个上进入前三**，尤其在不规则采样数据（MIMIC、USHCN、MuJoCo）和复杂时空动力学（浅水、气候）上表现突出。
4. 对于规则采样时间序列，KRNO在Darts和M4数据集上与顶尖方法不相上下，在部分季节性较弱的数据集上（如M4-Weekly、Daily）排名前二。
5. 方法在超分辨率预测（图1）中展示了将低分辨率输入映射到高分辨率时空输出的能力。

## 7. 优点

- **理论创新**：将时间序列预测重新定义为连续时间平移算子学习，是自回归模型的连续松弛，具有清晰的理论基础（存在性、连续性）。
- **架构高效**：KRNO是唯一同时实现**精确非平稳核评估**和**近乎线性计算复杂度**的神经算子，参数效率极高。
- **实用性强**：天然支持不规则采样、缺失数据（通过CNN预处理模块）和超分辨率预测，无需数据插值或重采样。
- **实验充分**：涵盖多样化的应用场景和大量SOTA对比，结果具有说服力。

## 8. 不足与局限

- **缺失数据处理的局限性**：对于MIMIC、USHCN等不规则/缺失数据，当前KRNO采用CNN预处理模块，但训练时必须使用批量大小为1（因序列长度不同），限制了训练效率。论文承认这一限制，并提出未来方向：可转换为固定长度特征向量（如T-PatchGNN的做法）。
- **超参数选择**：时间窗口长度 $t_p$ 和 $t_f$ 被设为超参数，论文指出可通过交叉验证选择，但未探讨如何自动化选择或在不同时间尺度下统一训练。
- **积分方案**：当前使用梯形法则近似积分，对于高度不规则采样的数据可能不够精确，论文指出可以设计自适应求积方案来改进。
- **与基线对比的公平性**：未详细说明是否对所有基线方法进行了超参数调优，可能对部分方法不公平。
- **理论深度有限**：仅证明了时间平移算子对ODE的连续性，对于偏微分方程（时空情况）的连续性仅提及留待未来工作，缺乏严格证明。
- **可扩展性局限**：尽管KRNO在 $N$ 上几乎线性，但其仍依赖于乘积网格假设，对于非结构化网格或自适应网格可能需要额外处理。

（完）
