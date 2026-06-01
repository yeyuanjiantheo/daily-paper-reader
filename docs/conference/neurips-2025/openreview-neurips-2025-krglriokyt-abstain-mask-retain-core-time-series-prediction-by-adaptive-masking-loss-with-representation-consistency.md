---
title: "Abstain Mask Retain Core: Time Series Prediction by Adaptive Masking Loss with Representation Consistency"
title_zh: 放弃掩码保留核心：通过自适应掩码损失与表示一致性的时间序列预测
authors: "Renzhao Liang, Sizhe Xu, Chenggang Xie, Jingru Chen, Feiyang Ren, Shu Yang, Takahiro Yabe"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=KrglRiOKYT"
tags: ["query:qf"]
score: 5.0
evidence: 时间序列预测方法，在金融市场上评估
tldr: 长序列预测中可能存在冗余噪声。本文基于信息瓶颈理论，提出自适应掩码损失和表示一致性方法，截断历史数据以提取有效信号。在金融市场数据上验证了预测精度提升，直接支持金融时间序列预测任务。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 长序列中冗余噪声降低预测准确性，需要更有效的历史利用方法。
method: 提出自适应掩码损失和表示一致性约束，剪枝冗余历史信息。
result: 在多个时间序列数据集（含金融）上提升预测性能，优于基线。
conclusion: 适当截断历史数据可增强预测效果，打破长序列信息增益假设。
---

## Abstract
Time series forecasting plays a pivotal role in critical domains such as energy management and financial markets. Although deep learning-based approaches (e.g., MLP, RNN, Transformer) have achieved remarkable progress, the prevailing "long-sequence information gain hypothesis" exhibits inherent limitations. Through systematic experimentation, this study reveals a counterintuitive phenomenon: appropriately truncating historical data can paradoxically enhance prediction accuracy, indicating that existing models learn substantial redundant features (e.g., noise or irrelevant fluctuations) during training, thereby compromising effective signal extraction. Building upon information bottleneck theory, we propose an innovative solution termed Adaptive Masking Loss with Representation Consistency (AMRC), which features two core components: 1) Dynamic masking loss, which adaptively identified highly discriminative temporal segments to guide gradient descent during model training; 2) Representation consistency constraint, which stabilized the mapping relationships among inputs, labels, and predictions. Experimental results demonstrate that AMRC effectively suppresses redundant feature learning while significantly improving model performance. This work not only challenges conventional assumptions in temporal modeling but also provides novel theoretical insights and methodological breakthroughs for developing efficient and robust forecasting models. We have made our code available at \url{https://github.com/MazelTovy/AMRC}.

---

## 论文详细总结（自动生成）

# 论文总结：Adaptive Masking Loss with Representation Consistency (AMRC)

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当前主流时间序列预测模型（MLP、RNN、Transformer）遵循“长序列信息增益假设”——即增加历史输入长度能提供更多时间依赖信息从而提升预测精度。但论文通过系统实验发现一个**反直觉现象**：适当截断历史数据的前缀部分反而能提高预测精度，表明模型在学习大量**冗余特征**（如噪声、无关波动），这些特征干扰了有效信号的提取。
- **研究背景**：基于信息瓶颈理论（Information Bottleneck, IB），模型的目标是学习一个压缩表示 \(Z\)，最大化与目标 \(Y\) 的互信息 \(I(Z;Y)\)，同时最小化与输入 \(X\) 的互信息 \(I(Z;X)\)。然而现有模型只关注前者（通过迭代训练提升预测性能），忽略了后者（抑制冗余信息），导致性能瓶颈。
- **整体含义**：该工作挑战了传统假设，提出通过显式抑制冗余特征来释放模型潜力，为时间序列预测提供新的理论视角和实用方法。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
基于信息瓶颈理论，设计**自适应掩码损失（Adaptive Masking Loss, AML）** 和**嵌入相似性惩罚（Embedding Similarity Penalty, ESP）**，共同构成 **AMRC** 框架。AML 通过动态识别并压制输入中的冗余前缀段，减少 \(I(Z;X)\)；ESP 通过保持嵌入空间与输出空间的几何一致性，稳定映射关系并提升泛化能力。

### 关键技术细节

#### 2.1 输入截断优化实验（Motivation）
- 定义掩码算子 \(M_k(\cdot)\)：将输入序列的前 \(k\) 个时间步置零。
- 最优掩码长度 \(k^*\) 通过最小化预测 MSE 选择：
  \[
  k^* = \arg\min_{k} \mathbb{E}\left[\|f_\theta(M_k(X_t^{(L)})) - Y_t^{(H)}\|^2\right]
  \]
- 实验证明，最优掩码后的模型 MSE 显著低于原始模型，且超过 50% 的样本受益，说明冗余特征普遍存在。

#### 2.2 自适应掩码损失（AML）
- **动机**：最优掩码产生的表示 \(Z_{k^*}\) 包含更少冗余，更接近最小充分统计量。AML 通过迫使原始表示 \(Z\) 逼近 \(Z_{k^*}\) 来显式减少 \(I(X,Z)\)。
- **实现步骤（随机采样策略避免穷举）**：
  1. 从均匀分布 \(\text{Uniform}\{1,\dots,L\}\) 中独立采样 \(m\) 个掩码长度 \(\{k_s\}_{s=1}^m\)，生成对应的掩码变体 \(\tilde{X}_{t,s} = M_{k_s}(X_t)\)。
  2. 计算每个变体和原始输入的预测损失：\(\ell_s = \mathcal{L}(f_\theta(\tilde{X}_{t,s}), Y_t)\)，\(\ell = \mathcal{L}(f_\theta(X_t), Y_t)\)。
  3. 若存在 \(\ell_s < \ell\)，则选取损失降低最大的变体 \(s^* = \arg\max_s (\ell - \ell_s)\)，其表示 \(\tilde{Z}_{s^*}\) 用作引导目标。
- **损失公式**：
  \[
  \mathcal{L}_{\text{AML}} = \beta \cdot \frac{1}{D_1 D_2} \|Z - \tilde{Z}_{s^*}\|^2
  \]
  其中自适应权重 \(\beta = \max(0, (\ell - \ell_{s^*})/\ell)\)，仅在掩码变体表现更好时激活。

#### 2.3 嵌入相似性惩罚（ESP）
- **目的**：解决语义不一致和表示崩溃问题——语义相似的输入应产生相似的预测，反之亦然。
- **方法**：对 mini-batch 内样本对，分别计算嵌入空间和输出空间的标准化 Frobenius 距离，然后惩罚两者差异：
  \[
  \Delta^E_{ij} = \frac{1}{L D} \|Z_i - Z_j\|_F^2, \quad \Delta^O_{ij} = \frac{1}{P D} \|Y_i - Y_j\|_F^2
  \]
  \[
  P_{ij} = |\Delta^E_{ij} - \Delta^O_{ij}|_+
  \]
  \[
  \mathcal{L}_{\text{ESP}} = \frac{1}{n^2} \sum_{i,j} P_{ij}
  \]
- 该损失促使嵌入流形与输出流形几何对齐。

#### 2.4 总体训练目标
\[
\mathcal{L}_{\text{total}} = \mathcal{L}_{\text{pred}} + \lambda_{\text{AML}} \mathcal{L}_{\text{AML}} + \lambda_{\text{ESP}} \mathcal{L}_{\text{ESP}}
\]
默认 \(\lambda_{\text{AML}} = \lambda_{\text{ESP}} = 1\)。AMRC 不增加推理开销，仅在训练时引入额外的正则项。

## 3. 实验设计

### 数据集（7 个）
- **ETT 系列**：ETTh1, ETTh2, ETTm1, ETTm2（电力变压器指标，7 个变量）
- **Weather**：21 个气象指标
- **Solar-Energy**：137 个光伏电站输出
- **Electricity (ECL)**：321 个用户小时用电量
- **额外验证**：ExchangeRate（汇率）、Illness（发病率，低数据量场景）

### 基准与对比方法
- **5 种代表性基线**：SOFTS、iTransformer、PatchTST、TSMixer、TimeMixer（覆盖 MLP、Transformer 架构）
- 所有基线使用官方代码和推荐超参，在相同实验条件下对比“原始”与“+AMRC”版本。

### 任务设置
- 固定输入长度 \(L=48\)，预测长度 \(H \in \{48, 72, 96, 120, 144, 168, 192\}\)（多步预测）
- 指标：MSE 和 MAE

### 实验类型
1. **主实验**：全部 7 个数据集 × 5 个模型 × 7 个预测长度，报告平均值（共 35 组 × 7 长度 = 245 个配置）。
2. **消融实验**：在 ETTh1、ETTh2、Solar-Energy、Weather 四个数据集上，对每个模型分别测试“仅 AML”、“仅 ESP”、“AML+ESP”三种变体。
3. **统计显著性**：对每个主实验进行 10 次重复运行，报告均值±标准差，并给出置信水平（Confidence Level）。
4. **冗余特征抑制效果量化**：比较原始模型和 AMRC 模型下“受掩码受益样本比例”（Ratio vs Ratio*），证明 AMRC 减少了冗余依赖。
5. **超参敏感性**：对掩码采样数 \(m\) 进行分析（从 1/8 到 3/4 输入长度）。
6. **附加实验**：在低数据 Illness 和 ExchangeRate 上验证鲁棒性。

## 4. 资源与算力

- **GPU**：单张 NVIDIA A100 80GB。
- **训练时长**：每个模型训练最多 100 epoch，使用 Adam 优化器（初始学习率 1e-4，余弦退火调度），batch size = 32，早停 patience = 20 epoch。
- **说明**：论文未报告具体总训练时间或每个实验的耗时，但指出 AML 的 mask 搜索使训练成本增加约 \(m\) 倍（默认 m=12）。对于延迟敏感应用，这可能是一个限制。

## 5. 实验数量与充分性

- **实验数量充分**：共覆盖 7 个数据集、5 种架构、7 种预测长度，进行了完整的消融、统计显著性、超参分析和额外验证。
- **公平性**：所有对比在相同超参、相同输入长度（\(L=48\)）下进行，基线使用官方实现；AMRC 是 plug-and-play 模块，不改变模型结构，保证了公平比较。
- **客观性**：报告了 10 次运行的平均值和标准差，并给出了置信水平（大部分为 99% 或 95%），结果可靠。
- **不足**：未在更多异构场景（如多变量极端长序列、分布式训练）下测试；未与专门去噪或对比学习方法（如 TS-CoT、DECL）直接比较——但这些方法属于不同的技术路线，论文将其归入相关工作范畴。

## 6. 论文的主要结论与发现

1. **反直觉现象验证**：截断历史前缀可提升预测精度，证实模型存在严重的冗余特征学习问题，挑战了“长序列信息增益假设”。
2. **AMRC 有效抑制冗余**：通过 AML 减少输入与表示之间的互信息，通过 ESP 保持表示几何一致性，两个组件互补，在几乎所有配置下均优于基线。
3. **架构无关性**：无论 Transformer 还是 MLP 模型，AMRC 均带来一致提升（如 iTransformer 在 Electricity 数据集 MSE 从 0.176 降至 0.163；TSMixer 在 ETTh1 从 0.402 降至 0.386）。
4. **泛化能力**：在低维（ETT 系列）和高维（Solar-Energy, Weather）数据上均有效，在低数据场景（Illness）也有改善。
5. **实用性**：作为优化框架可即插即用，不增加推理开销。

## 7. 优点

- **理论清晰**：以信息瓶颈理论为支撑，揭示了冗余特征的根源，并提供了可操作的优化目标（最小化 \(I(X,Z)\)）。
- **方法简洁有效**：AML 通过随机采样实现高效近似，自适应权重确保不会干扰正常训练；ESP 通过对比样本对实现几何对齐，无需额外数据或标签。
- **实验严谨**：涵盖多数据集、多架构、重复运行、消融、统计检验，论证充分。
- **开源代码**：提供匿名 GitHub 仓库，促进可复现性。
- **实用性强**：不修改模型结构，训练完成后推理无额外成本，易于迁移到现有基线。

## 8. 不足与局限

- **AML 的前提假设**：假设冗余主要位于输入序列的前缀部分。如果关键预测信息位于前缀而冗余在后缀，则 AML 无法起作用（此时 \(\beta=0\) 不生效）。
- **掩码机制缺乏可解释性**：被屏蔽的究竟是噪声、异常值还是过时趋势？目前是“黑箱”，无法明确回答。
- **ESP 在高维数据上收益有限**：在 137 通道的 Solar-Energy 数据集上，单独使用 ESP 效果弱于 AML。高维空间中几何对齐的优化方向指数增长，可能导致训练不稳定。
- **训练成本增加**：每 batch 需要额外评估 \(m\) 个掩码变体，训练时间约为原来的 \(m\) 倍（默认 m=12），在延迟敏感场景下不友好。
- **随机采样近似**：用 \(m\) 个随机掩码代替穷举搜索，可能漏掉最优掩码，导致部分冗余残留。
- **实验范围局限**：未在极端长序列（如 \(L > 192\)）或多步长输入（如动态输入长度）上验证；未与先进去噪/对比学习方法（TS2Vec、DECL、TS-CoT）进行直接性能对比（这些方法同样处理噪声但机制不同，论文可补充比较以增强说服力）。

（完）
