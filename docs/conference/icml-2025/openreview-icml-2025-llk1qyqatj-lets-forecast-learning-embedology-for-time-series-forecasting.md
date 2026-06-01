---
title: "LETS Forecast: Learning Embedology for Time Series Forecasting"
title_zh: LETS预测：时间序列预测的嵌入学习
authors: "Abrar Majeedi, Viswanatha Reddy Gajjala, Satya Sai Srinath Namburi GNVV, Nada Magdi Elkordi, Yin Li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=LLk1qYQatJ"
tags: ["query:qf"]
score: 7.0
evidence: 基于深度嵌入的时间序列预测方法
tldr: 针对现有深度时间序列预测模型未显式建模动态系统的问题，提出DeepEDM框架，结合Takens定理与深度学习，通过时延嵌入学习潜在空间，利用核回归近似动态，并结合注意力机制实现高效预测，在多个基准上达到先进水平。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-llk1qyqatj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1547, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-llk1qyqatj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 620, \"height\": 863, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-llk1qyqatj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 817, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-llk1qyqatj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1761, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-llk1qyqatj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1696, \"height\": 1644, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-llk1qyqatj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1760, \"height\": 1650, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-llk1qyqatj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 843, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-llk1qyqatj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1780, \"height\": 488, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-llk1qyqatj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 870, \"height\": 304, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-llk1qyqatj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1766, \"height\": 590, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-llk1qyqatj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1769, \"height\": 1606, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-llk1qyqatj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1423, \"height\": 1058, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-llk1qyqatj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 892, \"height\": 1019, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-llk1qyqatj/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 719, \"height\": 1324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-llk1qyqatj/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1075, \"height\": 465, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-llk1qyqatj/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1767, \"height\": 1330, \"label\": \"Table\"}]"
motivation: 现有深度学习方法不显式建模时间序列的潜在非线性动力学。
method: 基于Takens定理，使用时延嵌入学习潜在状态，并通过核回归和softmax注意力近似动态。
result: 在多个时间序列数据集上取得更准确的预测结果。
conclusion: 显式建模潜在动态能有效提升时间序列预测性能。
---

## Abstract
Real-world time series are often governed by complex nonlinear dynamics. Understanding these underlying dynamics is crucial for precise future prediction. While deep learning has achieved major success in time series forecasting, many existing approaches do not explicitly model the dynamics. To bridge this gap, we introduce DeepEDM, a framework that integrates nonlinear dynamical systems modeling with deep neural networks. Inspired by empirical dynamic modeling (EDM) and rooted in Takens' theorem, DeepEDM presents a novel deep model that learns a latent space from time-delayed embeddings, and employs kernel regression to approximate the underlying dynamics, while leveraging efficient implementation of softmax attention and allowing for accurate prediction of future time steps. To evaluate our method, we conduct comprehensive experiments on synthetic data of nonlinear dynamical systems as well as real-world time series across domains. Our results show that DeepEDM is robust to input noise, and outperforms state-of-the-art methods in forecasting accuracy. Our code is available at: https://abrarmajeedi.github.io/deep_edm.

---

## 论文详细总结（自动生成）

# 论文《LETS Forecast: Learning Embedology for Time Series Forecasting》详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：实际时间序列通常由复杂的非线性动力学系统生成，而现有深度学习方法虽然预测精度高，但大多将时间序列视为抽象模式，**没有显式建模其背后的潜在动力学**，导致对生成过程的盲点。
- **整体含义**：理解并利用系统动力学可以解锁更有效的预测策略。论文旨在结合**经验动态建模（EDM）**与深度学习，提出一个既能捕捉非线性动力学、又能利用深度模型扩展性和鲁棒性的新框架。
- **背景**：EDM基于Takens定理，通过时延嵌入重建状态空间并用于预测，但存在三大限制：假设无噪声、每个序列独立建模、预测视界受限。现有深度方法在噪声鲁棒性、跨序列泛化及长预测方面更有优势，但缺乏动力学视角。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将EDM的核心步骤（时延嵌入、核回归预测）替换为可学习的深度模块，实现**端到端训练**，同时克服EDM的三大局限。
- **整体架构**：DeepEDM由三部分组成：
  1. **基础预测模型（Base Predictor）**：一个简单的MLP或线性模型，从历史窗口 $y_{1:T}$ 生成初始预测 $y^p_{T+1:T+H}$，用于延长预测视界并解除EDM中 $H \ll T$ 的约束。
  2. **DeepEDM块**（可堆叠）：
     - **时延与编码**：对拼接后的序列 $[y_{1:T}, y^p_{T+1:T+H}]$ 进行时延操作（延迟步数 $\delta_T$），得到时延嵌入 $\hat{y}$；然后由一个共享的线性编码器 $\text{Enc}(\cdot)$ 将其投影到更高维的潜在空间 $z$，增强对噪声的鲁棒性。
     - **核回归（类似Simplex投影）**：在潜在空间使用加权平均（Nadaraya–Watson估计器）预测未来时延向量。权重由softmax核 $k(z_t, z_{t'}) = \exp(\langle z_t, z_{t'}\rangle / \tau)$ 给出，可通过高效的softmax注意力实现。
     - **解码**：解码器 $\text{Dec}(\cdot)$（轻量MLP）将预测的时延向量映射回原始时间序列值，同时具有去噪功能。
  3. **可堆叠性与跳连**：多个DeepEDM块可堆叠，第一个块的输出作为下一个块的输入，并引入门控跳连使梯度更容易流动。
- **关键技术细节**：
  - 训练损失函数 $L = \lambda L_{\text{err}} + (1-\lambda)L_{\text{td}}$，其中 $L_{\text{err}}$ 是预测误差，$L_{\text{td}}$ 是时间差分误差（帮助捕捉趋势变化），$\lambda$ 根据符号变化自适应调整。
  - 所有组件可微，共享参数跨变量（channel-wise），支持多变量预测。
  - 方法在理论上与Transformer模型有联系：时延嵌入类似局部窗口patching，核回归类似自注意力，整体结构类似Transformer块。

## 3. 实验设计：数据集、基准、对比方法

- **合成数据**：
  - 从非线性动力系统生成：非混沌Lorenz、混沌Lorenz、混沌Rössler。
  - 加入不同强度高斯噪声（$\sigma_{\text{noise}} \in \{0.0,0.5,1.0,1.5,2.0,2.5\}$），共18个数据集。
  - 对比方法：EDM Simplex（经典）、Koopa（基于Koopman理论的深度模型）、iTransformer（Transformer基）。
- **多变量预测基准**：
  - 10个真实世界数据集：ETTh1, ETTh2, ETTm1, ETTm2, ILI, Solar-Energy, Electricity, Traffic, Weather, Exchange。
  - 预测视界 $H \in \{48,96,144,192\}$（ILI为24,36,48,60），回看窗口 $T=2H$。
  - 对比11种方法：Koopa, Attraos, CycleNet, iTransformer, PatchTST, TimeMixer, DLinear, FITS, MICN, 朴素预测（Naïve）。
- **跨序列泛化实验**：将数据集按变量（通道）分开训练和测试（如ETT取3个序列训练，另外3个测试），评估模型对新序列的泛化能力。
- **单变量短时预测**：M4数据集（6个频率子集），采用SMAPE, MAPE, MASE, OWA指标，对比N-BEATS, N-HiTS, Koopa, TimeMixer等。
- **消融与敏感性分析**：
  - 组件消融：线性→MLP→MLP+EDM块→完整模型（含优化损失）。
  - 损失函数对比（MSE vs 完整损失）。
  - 回看长度、嵌入维度 $\delta_T$、延迟间隔 $\tau$ 的敏感性试验。
- **噪声鲁棒性分析**：在混沌Lorenz系统上评估时延嵌入与学习到的潜在空间的近邻检索召回率。

## 4. 资源与算力

- 论文正文和附录**未明确报告**具体的GPU型号、数量、训练时长等算力信息。这可能是目前许多实证论文的常见遗漏。

## 5. 实验数量与充分性

- **实验数量**：非常丰富。包括：
  - 合成数据3种系统×6噪声水平×4预测长度 = 72组条件×多个方法。
  - 多变量真实数据10个数据集×4视界 = 40组主表结果，每个重复5次取平均。
  - 跨序列泛化实验5个数据集×4视界×4方法 = 80组。
  - M4单变量6个子集×多种指标。
  - 消融实验：组件消融在9个数据集×4视界×3种子；损失函数对比；超参数敏感性。
- **充分性与公平性**：
  - 使用了统一的时间序列库（Time-Series-Library）保证预处理、分割一致性。
  - 重复多次运行报告标准差，显示结果稳定。
  - 对比了多种类型基线（经典动力系统模型、Koopman基、Transformer基、MLP基、朴素基线），覆盖全面。
  - 泛化实验设计新颖，验证了模型学习跨序列动力学的能力。
- **结论**：实验充分、客观，设计合理，结论可信。

## 6. 论文的主要结论与发现

- DeepEDM在**多变量预测基准**上取得**36个第一**（其次CycleNet 11个），尤其MAE指标优势明显，说明其更擅长捕捉趋势而非异常值。
- 在**合成数据**上，DeepEDM对噪声鲁棒性显著优于经典EDM，在混沌和高噪声情况下性能明显优于Koopa和iTransformer。
- **跨序列泛化**实验显示，DeepEDM在39/48设置下最优，证明了动力学建模有助于学到通用动力学规律。
- **模型设计消融**证实：引入EDM块带来最大提升，完整的损失函数进一步改善。
- **噪声鲁棒性机理**：学习到的潜在空间能更准确地保持真实状态空间的结构，近邻召回率远高于原始时延嵌入。
- **局限性**：在Exchange（股价）数据集上，朴素基线甚至优于所有模型，揭示金融时间序列高度随机性对预测模型的挑战。

## 7. 优点

- **方法创新**：成功将Takens定理和EDM与深度学习端到端融合，弥补了深度模型忽略动力学的缺陷，同时克服EDM的三大局限（噪声、单序列、预测视界短）。
- **理论联系**：揭示了所提结构与Transformer的相似性，为理解Transformer基时间序列模型提供了动力学视角。
- **实验扎实**：覆盖合成数据和多个真实基准，包含跨序列泛化、噪声鲁棒性、组件消融等深入分析，对比公平、结果可靠。
- **代码开源**：提供了可复现代码，促进后续研究。

## 8. 不足与局限

- **算力信息缺失**：未报告训练所需GPU型号、数量、时间等，不利于资源预算。
- **超参数依赖**：时延步数 $\delta_T$ 需根据数据集手动选择，论文虽做了敏感性分析，但未提出自动选择策略。
- **对高度随机的时间序列效果有限**：在外汇数据集上表现与朴素基线相当，表明完全随机或噪声过大的序列不适合动力学假设。
- **与Transformer的联系仅为定性讨论**，未做严格数学证明或系统性比较（如不同patching策略、注意力头数的等价性）。
- **模型复杂度**：多个堆叠EDM块可能增加计算成本，论文未与基线进行速度或参数量的对比。
- **仅限离散时间系统**：推导虽可推广至连续系统，但实验仅覆盖了离散步长。

（完）
