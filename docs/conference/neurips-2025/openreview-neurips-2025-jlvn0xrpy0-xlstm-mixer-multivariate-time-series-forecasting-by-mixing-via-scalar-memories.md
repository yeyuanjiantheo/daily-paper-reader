---
title: "xLSTM-Mixer: Multivariate Time Series Forecasting by Mixing via Scalar Memories"
title_zh: "xLSTM-Mixer: 通过标量记忆混合的多元时间序列预测"
authors: "Maurice Kraus, Felix Divo, Devendra Singh Dhami, Kristian Kersting"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=JlVn0XRpy0"
tags: ["query:qf"]
score: 5.0
evidence: 多元时间序列预测模型，结合LSTM和Mixer
tldr: 多元时间序列预测需同时捕捉时序内和变量间模式。本文提出xLSTM-Mixer，利用xLSTM块混合标量记忆，整合双重视角。在多个基准上表现优异，为金融等多变量序列预测提供了强大工具。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-jlvn0xrpy0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 769, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jlvn0xrpy0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1459, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jlvn0xrpy0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1456, \"height\": 536, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jlvn0xrpy0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1426, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jlvn0xrpy0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1430, \"height\": 901, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jlvn0xrpy0/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1465, \"height\": 1769, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-jlvn0xrpy0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jlvn0xrpy0/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 932, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jlvn0xrpy0/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 463, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jlvn0xrpy0/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1336, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jlvn0xrpy0/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1393, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jlvn0xrpy0/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1409, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jlvn0xrpy0/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1449, \"height\": 1120, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jlvn0xrpy0/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 905, \"height\": 1501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jlvn0xrpy0/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 932, \"height\": 1507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jlvn0xrpy0/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 932, \"height\": 1507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jlvn0xrpy0/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 685, \"height\": 1180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jlvn0xrpy0/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 720, \"height\": 899, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jlvn0xrpy0/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1283, \"height\": 665, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jlvn0xrpy0/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1435, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jlvn0xrpy0/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1443, \"height\": 465, \"label\": \"Table\"}]"
motivation: 现有预测模型未能有效整合时序与变量间信息。
method: 使用xLSTM块混合标量记忆，结合共享线性预测和双视角融合。
result: 在多个数据集上超越现有方法，证明混合机制的有效性。
conclusion: 标量记忆混合能有效提升多元时间序列预测的鲁棒性和准确性。
---

## Abstract
Time series data is prevalent across numerous fields, necessitating the development of robust and accurate forecasting models.
 Capturing patterns both within and between temporal and multivariate components is crucial for reliable predictions.
  We introduce xLSTM-Mixer, a model designed to effectively integrate temporal sequences, joint time-variate information, and multiple perspectives for robust forecasting.
    Our approach begins with a linear forecast shared across variates, which is then refined by xLSTM blocks.
    They serve as key elements for modeling the complex dynamics of challenging time series data.
   xLSTM-Mixer ultimately reconciles two distinct views to produce the final forecast.
    Our extensive evaluations demonstrate its superior long-term forecasting performance compared to recent state-of-the-art methods while requiring very little memory.
    A thorough model analysis provides further insights into its key components and confirms its robustness and effectiveness.
    This work contributes to the resurgence of recurrent models in forecasting by combining them, for the first time, with mixing architectures.

---

## 论文详细总结（自动生成）

### 论文的中文总结

#### 1. 核心问题与整体含义（研究动机和背景）

- **问题**：多元时间序列预测需要同时捕捉时间维度的模式以及多变量间的依赖关系。现有模型（如 Transformer）虽表现优秀，但存在显存开销大、对长序列效率低等局限。同时，循环神经网络（RNN）和状态空间模型（SSM）正重新受到关注，但尚未与混合架构（mixing architectures）有效结合。
- **动机**：作者希望设计一种兼具高预测精度和高效率（低内存、低计算量）的模型，能够通过标量记忆（scalar memories）混合时间与变量信息，并整合多视角预测，以推动循环模型在时序预测中的复兴。

#### 2. 方法论：核心思想、关键技术细节

- **整体架构**：xLSTM-Mixer 由三个阶段组成：
  1. **初始线性预测**（Time Mixing）：对每个变量独立使用 NLinear（一种带归一化的线性层），共享参数，产生初步的预测嵌入。
  2. **联合混合（Joint Mixing）**：将初始嵌入通过上投影层（FC up）映射到更高维的隐藏空间，然后使用多个 sLSTM 块（堆叠）以**变量维度为序列步进**（即按变量顺序逐 token 处理），同时混合时间和变量信息。这里使用 sLSTM 而非 mLSTM，因为 sLSTM 保留了循环门控间的记忆混合能力，能更好地跟踪状态变化。
  3. **视角混合（View Mixing）**：对原始嵌入和逆序嵌入分别通过 sLSTM 栈得到两个潜在预测视角，然后通过一个全连接层（FC view）将两者融合为最终预测。
- **关键技术细节**：
  - **sLSTM 单元**：引入指数门控和记忆混合，通过细胞状态 `c_t`、归一化状态 `n_t`、稳定状态 `m_t` 等更新，并采用多头（multi-head）块对角循环矩阵以提高效率。
  - **可学习初始嵌入 token η**：在 sLSTM 处理前，将 η 作为额外的初始 token 拼接到每个序列前，类似软提示（soft prompt），用于适应数据集特征。
  - **可逆实例归一化（RevIN）**：对输入进行归一化，预测后还原，以减轻分布漂移。
  - **权重共享**：NLinear 层和上投影层在各变量间共享参数，起到正则化作用并减少参数数量。
- **数学表示**：省略具体公式，可概括为：
  - `x_norm = RevIN(x)`
  - `x_initial = NLinear(x_norm)` （共享参数）
  - `x_up = FC_up(x_initial)` （共享参数）
  - `y', y'' = S(x_up), S(reverse(x_up))` （S 为 sLSTM 栈）
  - `y_norm = FC_view(y', y'')` （每个变量共享参数）
  - `y = RevIN^{-1}(y_norm)`

#### 3. 实验设计

- **数据集**：使用 7 个常见基准数据集：Weather、Electricity、Traffic、ETTh1、ETTh2、ETTm1、ETTm2，涵盖气象、电力、交通、能源等领域，预测长度包括 96、192、336、720 四个 horizon。
- **基准方法**：对比了 14 类共约 15 种方法：
  - 循环模型：xLSTMTime、LSTM
  - 混合模型（Mixer）：TimeMixer++、TimeMixer、TSMixer
  - MLP 模型：CycleNet、DLinear、TiDE
  - 状态空间模型（SSM）：S-Mamba、Chimera
  - Transformer：PatchTST、iTransformer
  - 卷积模型：ModernTCN、TimesNet
  - 预训练零样本模型：Timer-XL、Moirai Base（仅在部分任务对比）
- **评估指标**：MSE 和 MAE，三次不同随机种子取平均。
- **额外实验**：
  - 在 GIFT-Eval 全品类通用时序预测基准上评估概率预测（CRPS 和 MASE）
  - 在时序分类任务上通过替换分类头验证模型通用性
  - 模型分析：初始 token 可视化、对隐藏维度 D 和回看长度 T 的敏感性、变量排列鲁棒性、多视角数量的影响
- **消融实验**：对 13 种不同配置进行消融，包括替换 sLSTM 为 mLSTM/LSTM/GRU、取消时间混合、取消初始 token、取消视角混合、改变循环顺序等。

#### 4. 资源与算力

- **文中提到**：使用单张 NVIDIA A100 80GB GPU，基于 PyTorch 和 Lightning 框架，使用了自定义 CUDA 实现（要求计算能力≥8.0）。优化器为 Adam，余弦退火学习率调度，梯度裁剪最大范数 1.0，训练最多 60 个 epoch。未给出总训练时长或总 GPU 小时数，但指出 xLSTM-Mixer 内存占用远低于 Transformer 模型（图 1 显示显存与时间开销极低）。

#### 5. 实验数量与充分性

- **实验数量充分**：
  - 主长期预测实验：7 数据集 × 4 预测长度 = 28 个设置，每个设置三次重复。
  - GIFT-Eval 基准：39 个模型对比，涵盖多变量、单变量、多领域。
  - 分类实验：8 个 UCR 数据集平均准确率。
  - 消融实验：13 种变体在 2 个数据集（Weather 和 ETTm1）上各 4 个 horizon。
  - 敏感性分析：对 D 和 T 的扫描，变量排列测试等。
- **公平性**：代码已开源，遵循标准数据处理流程；对基线使用了作者提供的超参数，或自行调优（如 xLSTMTime）。统计显著性检验（Friedman + Conover/Holm）显示 xLSTM-Mixer 显著优于除 xLSTMTime 外的所有方法。

#### 6. 主要结论与发现

- **核心性能**：xLSTM-Mixer 在 7 个数据集上的 28 个长期预测设置中取得 11 个 MSE 第一、16 个 MAE 第一，平均排名领先所有基线。在 GIFT-Eval 上排名第二（无预训练模型中最优）。
- **效率优势**：相比 Transformer（如 PatchTST），内存占用降低 1-2 个数量级，时间开销几乎不随回看长度增加。
- **组件有效性**：消融实验证实，每个组件（时间混合、sLSTM、初始 token、视角混合）均贡献正向效果，其中 sLSTM 和视角混合最关键。
- **跨变量学习**：通过变量排列实验和 SHAP 归因分析，证明模型能有效捕捉变量间依赖（尽管受限于因果顺序）。

#### 7. 优点

- **方法创新**：首次将循环神经网络（xLSTM）与混合架构（mixing）成功结合，并引入双视角预测融合，设计精巧且高效。
- **实验全面**：涵盖了主流基准、丰富对比基线、深度消融和统计检验，结果可靠。
- **效率突出**：低内存、低延迟，适合边缘计算和实时场景。
- **通用性**：不仅适用于长期点预测，在概率预测（GIFT-Eval）和分类任务上同样表现强劲，表明其作为时序通用 backbone 的潜力。
- **可解释性分析**：可视化初始 token、SHAP 归因等提供了对模型行为的深入理解。

#### 8. 不足与局限

- **假设局限**：要求时间序列在均匀时间网格上采样，无法直接处理不规则时间戳或缺失值（需预处理）。
- **变量维数瓶颈**：由于按变量顺序循环，运行时间和内存与变量数量成正比，在极高维度（如 >1000 变量）时可能成为瓶颈。
- **因果关系限制**：sLSTM 按固定变量顺序步进，导致每个变量只能从之前变量获得信息；虽然顺序影响不显著，但仍可能存在最优顺序问题，论文未深入探索自动排序。
- **无预训练能力**：当前模型仅作监督训练，未探索大规模预训练或零样本迁移（对比的 Timer-XL 等预训练模型在部分任务上优于 xLSTM-Mixer）。
- **实验覆盖度**：分类实验仅使用 8 个 UCR 数据集，规模较小；未涉及异常检测、插值等常见下游任务。
- **可扩展性**：虽然内存开销小，但未见在小样本或极长序列场景下的系统测试。

（完）
