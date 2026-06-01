---
title: "HyperIMTS: Hypergraph Neural Network for Irregular Multivariate Time Series Forecasting"
title_zh: HyperIMTS：用于不规则多元时间序列预测的超图神经网络
authors: "Boyuan Li, Yicheng Luo, Zhen Liu, Junhao Zheng, Jianming Lv, Qianli Ma"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=u8wRbX2r2V"
tags: ["query:qf"]
score: 6.0
evidence: 建模不规则多元时间序列进行预测，适用于金融多变量序列
tldr: 不规则多元时间序列（IMTS）中变量内时间间隔不规则且变量间观测未对齐，传统方法效率低或依赖关系捕捉不足。本文提出HyperIMTS，利用超图统一表示原始观测并学习依赖关系，避免填充或分步学习，有效提升预测性能，可应用于金融多元时间序列预测。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-u8wrbx2r2v/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 835, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u8wrbx2r2v/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 856, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u8wrbx2r2v/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1321, \"height\": 819, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u8wrbx2r2v/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 679, \"height\": 614, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u8wrbx2r2v/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1677, \"height\": 960, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u8wrbx2r2v/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1755, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u8wrbx2r2v/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1776, \"height\": 1559, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-u8wrbx2r2v/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1420, \"height\": 950, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u8wrbx2r2v/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u8wrbx2r2v/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1423, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u8wrbx2r2v/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1418, \"height\": 942, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u8wrbx2r2v/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1421, \"height\": 440, \"label\": \"Table\"}]"
motivation: 现有IMTS模型效率低或依赖捕捉不足，需统一表示不规则观测。
method: 提出HyperIMTS，使用超图神经网络直接从原始观测学习时间和变量依赖。
result: 在多个不规则时间序列数据集上取得优于基线方法的预测结果。
conclusion: HyperIMTS为不规则多元时间序列预测提供高效统一方案，适用于金融领域。
---

## Abstract
Irregular multivariate time series (IMTS) are characterized by irregular time intervals within variables and unaligned observations across variables, posing challenges in learning temporal and variable dependencies. 
Many existing IMTS models either require padded samples to learn separately from temporal and variable dimensions, or represent original samples via bipartite graphs or sets.
However, the former approaches often need to handle extra padding values affecting efficiency and disrupting original sampling patterns, while the latter ones have limitations in capturing dependencies among unaligned observations.
To represent and learn both dependencies from original observations in a unified form, we propose HyperIMTS, a **Hyper**graph neural network for **I**rregular **M**ultivariate **T**ime **S**eries forecasting.
Observed values are converted as nodes in the hypergraph, interconnected by temporal and variable hyperedges to enable message passing among all observations.
Through irregularity-aware message passing, HyperIMTS captures variable dependencies in a time-adaptive way to achieve accurate forecasting. 
Experiments demonstrate HyperIMTS's competitive performance among state-of-the-art models in IMTS forecasting with low computational cost.
Our code is available at [https://github.com/qianlima-lab/PyOmniTS](https://github.com/qianlima-lab/PyOmniTS).

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：不规则多元时间序列（IMTS）中，每个变量的观测时间间隔不规则，且不同变量之间的观测在时间上不对齐。这使得同时捕获**时间依赖**（同一变量不同时刻）和**变量依赖**（不同变量之间）变得困难。
- **现有方法瓶颈**：
  - **基于填充的模型**（如RNN、ODE、Transformer）需要将IMTS填充成规则矩阵，导致数据量增大、效率低，且可能破坏原始采样模式。
  - **非填充方法**（如集合、二分图）虽然避免填充，但集合无法建模观测间相关性，二分图无法在无共享时间戳的变量间传播消息，限制了依赖关系的捕获。
- **整体含义**：提出一种无需填充、能统一表示原始观测并同时学习时间和变量依赖的新框架，提升IMTS预测精度和效率。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将IMTS中的每个观测值作为超图中的一个**节点**，时间戳和变量分别建模为两类**超边**（时间超边和变量超边），通过超边连接所有观测节点，实现统一的消息传递。
- **关键技术细节**：
  1. **超图构建**：
     - 节点：每个观测值 `(t, z, u)` 映射为节点嵌入 `v_j`。
     - 超边：时间超边 `e_t` 连接同一时间戳的所有观测；变量超边 `e_u` 连接同一变量的所有观测。
     - 初始化：观测值经非线性映射得到节点嵌入；时间超边用正弦编码初始化；变量超边使用可学习参数。
  2. **消息传递机制**（三个步骤）：
     - **(a) 节点到超边更新**：使用多头注意力，将节点信息聚合到时间超边和变量超边。查询为超边嵌入，键和值为节点嵌入与另一类超边的拼接。
     - **(b) 超边到超边（变量间消息传递）**：实现不规则感知的变量依赖建模。同时计算**整体变量相似度**（基于变量超边嵌入的点积）和**时间感知相似度**（仅基于共享时间戳的观测节点的点积），通过可学习的阈值 `δ` 自适应融合二者，得到不规则感知的相似度矩阵，再进行缩放点积注意力更新变量超边。
     - **(c) 超边到节点更新**：将更新后的时间超边和变量超边信息传回节点，结合节点自注意力，最终输出预测。
  3. **预测与训练**：将更新后的节点嵌入与超边拼接，通过线性层映射为预测值；优化目标为预测值与真值之间的均方误差（MSE）。
- **算法流程（文字说明）**：
  1. 输入IMTS样本（含历史观测和未来查询时间戳/变量索引）。
  2. 构建超图：初始化节点、时间超边、变量超边嵌入。
  3. 迭代 L 层：
     - 前 L-1 层：节点→超边更新（时间+变量），然后超边→节点更新（使用未经过变量间通信的变量超边，侧重时间依赖）。
     - 第 L 层：节点→超边更新后，进行超边→超边（变量间）不规则感知通信，最后超边→节点更新（融合变量依赖）。
  4. 输出预测值。

## 3. 实验设计：数据集、benchmark、对比方法

- **数据集**：5个广泛使用的IMTS数据集，涵盖医疗、生物力学、气候：
  - MIMIC-III (ICU病人48小时临床数据)
  - MIMIC-IV (MIMIC-III升级版，采样频率更高)
  - PhysioNet’12 (ICU 48小时临床数据)
  - Human Activity (3D位置生物力学数据)
  - USHCN (美国历史气候网络150年气候数据子集)
- **Benchmark**：每个数据集按80%/10%/10%划分为训练/验证/测试集，测试集不shuffle。评估指标为MSE（主要）和MAE（附录）。
- **对比方法**：27个SOTA基线，涵盖：
  - 多元时间序列预测：FEDformer, Autoformer, TimesNet, iTransformer, FourierGNN, Mamba, TSMixer, PatchTST, Crossformer, Leddam, Reformer, Informer, Ada-MSHyper, BigST, higp。
  - 时间序列预训练：MOIRAI, PrimeNet。
  - IMTS分类/插补/预测：SeFT, mTAN, NeuralFlows, CRU, GNeuralFlow, GRU-D, Raindrop, tPatchGNN, Warpformer, GraFITi。

## 4. 资源与算力

- 文中明确说明：
  - 训练平台：Linux服务器，PyTorch 2.4.1，**两张 NVIDIA GeForce RTX 3090 GPU**。
  - 效率分析平台：另一台Linux服务器，PyTorch 2.2.2+cu118，**一张 NVIDIA GeForce RTX 2080Ti GPU**。
  - 所有实验最大epoch数300，早停耐心10个epoch。
  - 未报告具体训练总时长，但给出了每个iteration的训练时间和GPU内存占用（用于效率对比）。

## 5. 实验数量与充分性

- **主要实验结果**：在5个数据集上对比27个基线，报告MSE（5次不同随机种子的均值±标准差），结果表（Table 1）显示HyperIMTS在4个数据集上最优，1个数据集上第二（USHCN方差较大）。
- **MAE结果**：附录Table 4，同样在4个数据集最优。
- **不同预测长度和回溯长度**：附录Table 5（固定回溯，变预测长度）和Figure 5（变回溯长度），HyperIMTS总体排名第一。
- **消融实验**：5组变体（去除变量超边、去除变量间通信、替换为全局相似度、去除时间超边、替换为非可学习时间超边），在5个数据集上验证各组件必要性（Table 3）。
- **效率分析**：在MIMIC-III上对比6种代表性模型（非填充、填充、规则序列模型）的训练时间、GPU内存和MSE（Figure 4），HyperIMTS达到最低MSE且计算成本低；附录Figure 7在剩余4个数据集上补充效率对比。
- **总结**：实验设计充分，覆盖多数据集、多基线、多指标、多变量设置，并进行了消融和效率分析。公平性方面：统一了数据预处理、学习率调度、随机种子、归一化方法等，避免不公平比较。

## 6. 论文的主要结论与发现

- HyperIMTS通过超图统一表示IMTS的原始观测，避免填充，同时高效捕获时间和变量依赖。
- 不规则感知的变量间消息传递（融合时间对齐信息）显著提升了预测精度。
- 在5个标准IMTS数据集上，HyperIMTS在MSE/MAE上整体优于所有27个基线，最高比次优模型GraFITi提升11.4%。
- 计算效率方面：非填充方法（HyperIMTS、GraFITi）对回溯长度增长不敏感，在长序列场景下比填充方法更高效。
- 消融实验证实时间超边、变量超边以及不规则感知的变量间通信均不可或缺。

## 7. 优点

- **方法创新性**：首次将超图神经网络系统应用于IMTS预测，用超边自然连接同一时间或同一变量的观测，避免了填充的冗余和集合/二分图的局限。
- **不规则感知机制**：通过时间对齐的观测相似度与全局变量相似度的自适应融合，灵活处理不同对齐程度的变量关系，这一设计直观且有效。
- **统一框架**：将预测任务转化为超图上的节点预测，模型扩展性强，易于引入其他类型超边（如外部知识）。
- **实验严谨性**：
  - 构建了统一的代码管道，囊括27个来自不同领域的SOTA模型，做了公平对比。
  - 使用5个不同随机种子报告均值与标准差，确保结果稳定。
  - 进行多维度消融和效率分析。
- **开源代码**：提供完整代码库，便于复现和后续研究。

## 8. 不足与局限

- **不支持多模态数据**：文中明确承认模型目前无法整合文本笔记、医学图像等多模态信息，而这些数据在医疗IMTS中常见，可能进一步提升预测性能。
- **计算资源敏感**：虽然比填充方法高效，但注意力机制的计算仍比状态空间模型（如Mamba）更重，尤其是在大规模图中。
- **数据集覆盖有限**：实验主要集中在医疗、生物力学和气候领域，未验证在金融、工业等其他IMTS场景的泛化性。
- **对美国USHCN数据集的方差较大**：部分模型（包括HyperIMTS）在该数据集上结果不稳定，可能原因包括数据集本身的采样特性或预处理方式，文中未深入分析。
- **未讨论对缺失率的鲁棒性**：IMTS的缺失模式多样（完全随机缺失、非随机缺失等），实验未专门设计不同缺失率下的性能分析。
- **超参数调优**：文中基于默认设置和网格搜索选择部分超参数，但未提供详细的超参数敏感性分析，可能会影响实际部署时的调优效率。

（完）
