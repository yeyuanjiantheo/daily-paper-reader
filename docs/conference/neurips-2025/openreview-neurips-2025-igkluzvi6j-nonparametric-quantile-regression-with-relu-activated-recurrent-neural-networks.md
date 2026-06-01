---
title: Nonparametric Quantile Regression with ReLU-Activated Recurrent Neural Networks
title_zh: 使用ReLU激活的循环神经网络进行非参数分位数回归
authors: "Hang Yu, Lyumin Wu, Wenxin Zhou, Zhao Ren"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=IGKluZvI6J"
tags: ["query:qf"]
score: 8.0
evidence: 分位数回归用于尾部风险预测
tldr: 本文研究使用ReLU激活的循环神经网络（RNN）进行非参数分位数回归，针对平稳的β混合过程建立了最优收敛速率。通过将条件分位数函数建模为层次交互结构，推导了RNN和稀疏RNN的逼近误差界。理论上证明了所提估计量达到最优非参数速率，实验验证了其有效性。该方法可用于金融时间序列的尾部风险预测，如VaR和ES的估计。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-igkluzvi6j/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igkluzvi6j/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 965, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igkluzvi6j/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1423, \"height\": 585, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-igkluzvi6j/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 985, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igkluzvi6j/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 988, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igkluzvi6j/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1036, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igkluzvi6j/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1118, \"height\": 137, \"label\": \"Table\"}]"
motivation: 非参数分位数回归在金融风险度量中重要，但现有方法的理论性质不清晰。
method: 利用ReLU激活的RNN和稀疏RNN逼近条件分位数函数，基于层次交互模型推导逼近误差界。
result: 在平稳β混合假设下，所提估计器达到了最优非参数收敛速率。
conclusion: 为RNN在分位数回归中的应用提供了坚实的理论保证，可推广至金融时间序列的尾部风险建模。
---

## Abstract
This paper investigates nonparametric quantile regression using recurrent neural networks (RNNs) and sparse recurrent neural networks (SRNNs) to approximate the conditional quantile function, which is assumed to follow a compositional hierarchical interaction model. We show that RNN- and SRNN-based estimators with rectified linear unit (ReLU) activation and appropriately designed architectures achieve the optimal nonparametric convergence rate, up to a logarithmic factor, under stationary, exponentially $\boldsymbol{\beta}$-mixing processes. To establish this result, we derive sharp approximation error bounds for functions in the hierarchical interaction model using RNNs and SRNNs, exploiting their close connection to sparse feedforward neural networks (SFNNs). Numerical experiments and an empirical study on the Dow Jones Industrial Average (DJIA) further support our theoretical findings.

---

## 论文详细总结（自动生成）

# 论文总结：Nonparametric Quantile Regression with ReLU-Activated Recurrent Neural Networks

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：非参数分位数回归（Quantile Regression, QR）相比均值回归能够更全面地揭示条件分布特征，尤其适用于尾部分析和异方差场景。然而，现有深度学习方法（如前馈神经网络 FNN）缺乏处理时序依赖的能力，而循环神经网络（RNN）天然适合序列建模，但其在 QR 框架下的统计理论性质尚不清晰。本文旨在为 ReLU 激活的 RNN 及其稀疏变体（SRNN）在非参数 QR 中建立严格的收敛速率理论保证。
- **背景假设**：条件分位数函数被假定属于**层次交互模型**（Hierarchical Interaction Model），该模型通过组合低维成分函数缓解维数灾难；数据生成过程为平稳的 **β 混合**（β-mixing）序列，涵盖非线性自回归模型。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：使用 RNN/SRNN 作为函数逼近器，通过经验风险最小化（ERM）估计条件分位数函数。利用层次交互模型的低维结构，证明 RNN 和 SRNN 能够以最优速率逼近目标函数，并进一步在 β 混合依赖下导出整体估计的收敛速率。
- **关键技术细节**：
  - **网络架构**：RNN 定义为重复单元 `r(t)_l = σ(A_l r(t-1)_l + B_l v(t)_{l-1} + c_l)`，输出层取序列最后一步；SRNN 进一步对参数施加稀疏性约束（总非零参数数 ≤ s）。
  - **逼近误差界**：通过将 RNN/SRNN 与稀疏前馈网络（SFNN）建立等价关系，证明对层次交互模型中的函数，RNN 的逼近误差为 O((W_0 L_0)^{-2γ*})（定理 1），SRNN 的逼近误差为 O(W_0 2^{-L_0} + W_0^{-γ*})（定理 2），其中 γ* 为固有光滑度。
  - **Oracle 不等式**：针对检查损失（check loss），在 β 混合条件下建立概率不等式（定理 3），将估计误差分解为逼近误差、随机误差和依赖调整项。关键技术包括“甜甜圈形”分解、改进的块划分技术和锐化的经验过程不等式。
  - **收敛速率**：在指数 β 混合下，RNN 和 SRNN 估计量均达到 **n^{-γ*/(2γ*+1)}**（平方 L2 范数下）的对数因子内最优速率；在代数 β 混合下速率略慢，但随混合速率 r→∞ 趋近最优。

## 3. 实验设计：数据集、benchmark 与对比方法

- **合成数据集**：
  - Model 1：非线性 AR 模型 `Y_t = (Φ(-Z_t)-0.5)Y_{t-1} + (Φ(2Z_t)-0.6)Y_{t-2} + ε_t`，其中 Z_t 为前 10 项组合。
  - Model 2：更复杂的非线性 AR 模型，包含 cos、sigmoid、多项式等成分。
  - **噪声分布**：标准正态 N(0,1) 和重尾 t 分布（自由度为 2.25）。
  - **分位数水平**：τ = 0.1 和 0.5。
- **真实数据**：
  - **DJIA 数据**：2000-2020 年道琼斯指数日收益率，进行 30 个交易日超前预测。
  - **GDP 数据**（附录 C）：美国实际 GDP 季度增长率（1947-2024），进行单步超前预测。
- **Benchmark 与对比方法**：
  - 分位数随机森林（QRF，scikit-garden）
  - 前馈神经网络（FNN，2 层宽 200）
  - 全连接 RNN（L=3, W=100）
  - SRNN（剪枝 40% 参数后微调）
- **评估指标**：MSE（合成数据）、平均检查损失（真实数据）。

## 4. 资源与算力

- **未明确说明**：文中仅提及实验使用 Python、PyTorch 实现，未提供 GPU 型号、数量或训练时长等算力细节。所有神经网路采用早停法，数据集规模较小（仿真数据约 11 万样本，真实数据时间序列长度有限），计算资源需求较低，可在普通个人计算机上复现。

## 5. 实验数量与充分性

- **实验数量**：
  - 合成数据：两个模型 × 两种噪声 × 两个分位数 ≈ 8 个场景，每个场景做 500 次蒙特卡洛重复。
  - 真实数据：DJIA 数据在 5 个分位数上对比 4 种方法；GDP 数据做 in-sample/out-of-sample 对比及分位数估计可视化。
  - 超参数敏感性分析（附录 D）：改变深度 L（2-7）、宽度 W（16-1024）和剪枝率（0.2-0.8）。
- **充分性与公平性**：
  - 对比方法包括传统树模型（QRF）和常见神经网络（FNN），且超参数提前固定，避免过度调优。
  - 使用早停防止过拟合，并在验证集上进行 Stopping，流程标准化。
  - 500 次重复提供了统计稳健性；敏感性分析验证了架构选择的影响。
  - **客观性**：实验结果报告了 MSE 分布和均值，SRNN 与 RNN 表现相当，且优于 FNN 和 QRF，证据充分。

## 6. 论文的主要结论与发现

- **理论发现**：
  - RNN 和 SRNN 在层次交互模型下达到逼近误差最优界，进而通过 ERM 得到收敛速率 n^{-γ*/(2γ*+1)}（对数因子内），该速率与 Schmidt-Hieber (2020) 中 minimax 最优速率一致。
  - 依赖数据的 β 混合性质仅导致对数因子增加，不影响本质速率。
- **实验发现**：
  - RNN/SRNN 在合成数据和真实金融数据上均显著优于 QRF 和 FNN，方差更小。
  - SRNN 在保持稀疏性的同时性能几乎不损失，验证了理论优势。
  - 在 GDP 预测中，RNN/SRNN 的 out-of-sample 与 in-sample 估计值高度吻合，即使在金融危机的极端事件下也表现稳健。

## 7. 优点

- **理论创新**：首次为 RNN 在分位数回归中提供完整的统计收敛性证明，包括逼近误差、经验过程不等式和 β 混合依赖下的 oracle 不等式。
- **技术深度**：建立了 RNN/SRNN 与 SFNN 之间的等价关系，为后续理论分析提供新工具；开发了“甜甜圈形”分解和改进的块划分方法，克服了检查损失非光滑性的困难。
- **实验设计合理**：覆盖不同噪声分布和分位数水平，包含真实数据和敏感性分析，验证了理论结果的稳健性。
- **实用性**：SRNN 具有稀疏性，资源消耗低，适用于高维时间序列场景。

## 8. 不足与局限

- **理论假设较强**：层次交互模型、条件密度正则性和 β 混合假设在复杂现实数据中可能难以完全满足，限制了结果的直接推广。
- **实验覆盖有限**：仅使用两个仿真模型和两个真实数据集（DJIA 和 GDP），未与近期先进的深度分位数方法（如 DeepAR、Transformer、N-BEATS）对比。
- **超参数选择**：RNN 的深度和宽度固定，未系统调优；SRNN 的剪枝率（40%）未在不同任务中自适应选择。
- **分位数范围局限**：仅考虑固定 τ，未涉及分位数过程回归（quantile process regression）或非交叉分位数约束。
- **算力细节缺失**：未报告 GPU 型号、训练时间等资源信息，可重复性受一定影响。
- **非平稳性风险**：虽然 GDP 数据尝试了非平稳场景，但理论假设依赖平稳性；实证结果虽表现良好，但缺乏严格理论保证。

（完）
