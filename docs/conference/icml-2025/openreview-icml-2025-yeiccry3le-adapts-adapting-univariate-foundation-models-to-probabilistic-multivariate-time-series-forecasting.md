---
title: "AdaPTS: Adapting Univariate Foundation Models to Probabilistic Multivariate Time Series Forecasting"
title_zh: AdaPTS：将单变量基础模型适配到概率多变量时间序列预测
authors: "Abdelhakim Benechehab, Vasilii Feofanov, Giuseppe Paolo, Albert Thomas, Maurizio Filippone, Balázs Kégl"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=yeICCRy3lE"
tags: ["query:qf"]
score: 6.0
evidence: 将单变量基础模型适配到多变量概率预测，直接适用于金融时间序列波动率建模
tldr: 现有单变量时间序列基础模型在多变量预测中面临特征依赖和不确定性量化的挑战。本文提出AdaPTS，通过适配器将多变量输入投影到潜在空间，再利用预训练的单变量模型独立预测每个维度，并基于贝叶斯神经网络思想给出概率预测。实验表明该方法在多变量预测任务上达到有竞争力结果。该工作为金融波动率等多变量概率预测提供了可迁移的基础模型适配方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yeiccry3le/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 846, \"height\": 669, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yeiccry3le/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 849, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yeiccry3le/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1775, \"height\": 499, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yeiccry3le/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 841, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yeiccry3le/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 356, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yeiccry3le/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 860, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yeiccry3le/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 853, \"height\": 246, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yeiccry3le/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 868, \"height\": 210, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yeiccry3le/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1764, \"height\": 379, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yeiccry3le/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1774, \"height\": 573, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yeiccry3le/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 836, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yeiccry3le/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 719, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yeiccry3le/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1479, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yeiccry3le/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 952, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yeiccry3le/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1752, \"height\": 565, \"label\": \"Table\"}]"
motivation: 现有单变量时间序列基础模型难以处理多变量特征依赖和预测不确定性。
method: 设计适配器作为特征空间变换，将多变量输入映射为单变量模型可处理的表示，并结合部分随机贝叶斯神经网络进行概率预测。
result: 在多个多变量时间序列数据集上，AdaPTS在预测准确性和不确定性量化方面优于现有基线。
conclusion: AdaPTS为利用单变量基础模型进行多变量概率预测提供了有效途径，可扩展至金融时间序列。
---

## Abstract
Pre-trained foundation models (FMs) have shown exceptional performance in univariate time series forecasting tasks. However, several practical challenges persist, including managing intricate dependencies among features and quantifying uncertainty in predictions. This study aims to tackle these critical limitations by introducing **adapters**—feature-space transformations that facilitate the effective use of pre-trained univariate time series FMs for multivariate tasks. Adapters operate by projecting multivariate inputs into a suitable latent space and applying the FM independently to each dimension. Inspired by the literature on representation learning and partially stochastic Bayesian neural networks, we present a range of adapters and optimization/inference strategies. Experiments conducted on both synthetic and real-world datasets confirm the efficacy of adapters, demonstrating substantial enhancements in forecasting accuracy and uncertainty quantification compared to baseline methods. Our framework, **AdaPTS**, positions adapters as a modular, scalable, and effective solution for leveraging time series FMs in multivariate contexts, thereby promoting their wider adoption in real-world applications. We release the code at https://github.com/abenechehab/AdaPTS.

---

## 论文详细总结（自动生成）

# AdaPTS: 将单变量基础模型适配到概率多变量时间序列预测——中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：现有预训练的时间序列基础模型（如 Chronos、Moment 等）大多针对**单变量**预测任务设计，无法有效处理多变量时间序列中的**特征间依赖关系**，也缺乏对预测**不确定性**的系统量化。
- **背景**：多变量预测在能源、金融、医疗等高风险领域极为重要，但直接扩展单变量 FM 到多变量面临维度爆炸、计算成本高、通道数可变等挑战。现有方案（如 Moirai 使用扁平化注意力）虽支持多变量，但计算复杂度高且不灵活。
- **整体意义**：论文提出 AdaPTS 框架，通过引入**适配器（adapter）**——一种可学习的特征空间变换——使得冻结的单变量 FM 能够高效、概率性地处理多变量时间序列预测，同时提供不确定性估计。

## 2. 论文提出的方法论
- **核心思想**：定义一个变换对（encoder φ 和 decoder φ⁻¹），将原始多变量输入 X 映射到低维或等维的潜在空间 Z，使 FM 在 Z 上逐通道独立预测，再将预测结果映射回原始特征空间。即预测为 dec(fFM(enc(X)))。
- **关键技术细节**：
  - **线性适配器**：用线性矩阵 W_enc、W_dec 实现，可降维（D′ ≤ D）。理论分析证明，在线性 FM 假设下，最优适配器非平凡，优于恒等映射。
  - **深度非线性适配器**：使用多层 MLP 作为 encoder/decoder。
  - **概率适配器**：
    - **VAE 适配器**：将 latent Z 视为随机变量，encoder 输出后验 qₑ(Z|X)，训练目标为 ELBO 形式（预测项 + KL 正则项）。支持 β-VAE 变体。
    - **Dropout 适配器**：在 adapter 层施加 Monte Carlo Dropout，模拟贝叶斯推断，获得预测集合并量化不确定性。
  - **理论支撑**：基于部分随机贝叶斯神经网络（Sharma et al., 2023）的理论，证明只要 encoder 引入随机性且随机单元数≥输出维度，即可实现通用条件密度估计。
- **算法流程**：
  1. 预训练 FM 保持冻结；
  2. 可选的线性探针（linear probing）训练 FM 头部（如 Moment）；
  3. 训练 adapter（encoder + decoder）最小化 MSE 损失或 ELBO；
  4. 预测时，通过 adapter 前向传播得到确定性或概率性多变量预测。

## 3. 实验设计
- **数据集**：
  - 4 个标准多变量长期预测数据集：**ETTh1**（7 维，13603 步）、**Illness**（7 维，169 步）、**Weather**（21 维，51899 步）、**ExchangeRate**（8 维，6791 步）。
  - 额外使用**合成数据**：5 个独立基信号 + 8 个线性混合通道，验证适配器在已知线性关系下的有效性。
- **基准（Baseline）**：
  - **Moment-s**（小版本）直接逐通道独立预测（无 adapter）。
  - **PCA** 作为非学习型 adapter 对比。
- **对比方法**：文中比较了多种 adapter 架构：PCA、LinearAE（线性自编码器）、dropoutLinearAE（带 Dropout 的线性 AE）、LinearVAE（线性 VAE）、VAE（深度 VAE）。
- **额外 FM 测试**：在 Illness 数据集上，针对 **TTM**（全 MLP FM）和 **TimesFM**（解码器 Transformer）也验证了 adapter 的效果。

## 4. 资源与算力
- **文中未明确说明**具体 GPU 型号、数量、训练总时长。仅提及使用 Adam 优化器、batch size 32、学习率 0.001，并在超参数搜索时使用了 Ray Tune + HEBO 求解器。k-fold 交叉验证。未提供 FLOPs 或参数量对比。

## 5. 实验数量与充分性
- **实验数量**：
  - 主表（Table 1）：4 个数据集 × 2 个预测 horizon × 5 种 adapter = 40 组 MSE/MAE 结果，每组 3 个随机种子，共约 120 次运行。
  - 消融实验：
    - 潜在维度 D′ 影响（图 4）：两个数据集，5 种 adapter，多个 D′。
    - VAE 超参数 β 和 σ 的消融（图 6）。
    - LinearAE 各组件（encoder only, decoder only）对比（图 7）。
  - 概率校准图（图 5）：一个特征 × 不同 horizon。
  - 额外 FM 实验（Table 2）：TTM 和 TimesFM 在一个数据集上。
  - 合成数据实验（图2）：线性 FM + 线性 adapter 理论验证。
- **充分性评价**：实验覆盖了多个真实数据集、不同 FM（Moment、TTM、TimesFM）、不同 adapter 变体及关键超参数，消融实验设计合理。但仅在 1 个任务上测试了 TTM 和 TimesFM，泛化验证不够充分。未包含与完整多变量模型（如 Moirai、Crossformer）的直接对比，存在一定不足。

## 6. 论文的主要结论与发现
- AdaPTS 在 **5/8** 任务上提升了 Moment 的预测精度，最高提升 15%（Illness H=24）。
- 概率适配器（尤其是 VAE）在不确定性校准和分布偏移处理上显著优于确定性适配器。
- VAE 和 Dropout 适配器能提供合理校准的概率预测（早期 horizon 良好，长 horizon 略有过度自信）。
- 降维度后（D′=2 或 5）可保持甚至超过基线性能，适合低资源场景。
- 潜在空间可视化显示 VAE 有助于对齐训练/测试分布，缓解分布偏移。

## 7. 优点
- **方法创新**：将“适配器”概念从 NLP/CV 引入时间序列，结合部分随机贝叶斯神经网络理论，为解决单变量 FM 多变量应用提供了新范式。
- **模块化与可扩展**：框架支持不同 FM、不同 adapter 架构、多种训练模式（监督/无监督/微调），并附有开源 Python 包。
- **概率输出**：明确支持不确定性量化，这在金融、能源等风险敏感场景中非常重要。
- **理论指导**：在简单线性情况下给出了最优解解析式，增强方法可信度。
- **实验设计严谨**：多次重复、报告标准差、使用 k-fold 交叉验证和贝叶斯超参数优化（HEBO）。

## 8. 不足与局限
- **实验覆盖有限**：
  - 仅对比了 Moment 基线，未与专门的多变量预测模型（如 Crossformer、PatchTST、Moirai 等）直接比较。
  - 额外 FM 测试仅在一个数据集上进行，结论需更大范围验证。
  - 未涉及超长序列（如 720）或高频金融数据场景。
- **校准问题**：随着预测 horizon 增加，概率预测变得过度自信，校准退化。
- **计算复杂度**：虽然 adapter 本身轻量，但训练 adapter 仍需完整前向传播有限 FM，大 FM 推理成本仍高。
- **局限性讨论**：论文自身承认 Normalizing Flows 作为 adapter 训练困难，未给出有效方案；MCMC 等更精确贝叶斯方法未探索。
- **风险**：方法对 FM 的选择敏感（TTM 提升大、TimesFM 提升小），通用性依赖进一步研究。

（完）
