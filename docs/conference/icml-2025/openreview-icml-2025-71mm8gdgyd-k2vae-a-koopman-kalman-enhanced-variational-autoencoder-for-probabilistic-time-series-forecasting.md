---
title: "$K^2$VAE: A Koopman-Kalman Enhanced Variational AutoEncoder for Probabilistic Time Series Forecasting"
title_zh: K^2VAE：基于Koopman-Kalman增强的变分自编码器用于概率时间序列预测
authors: "Xingjian Wu, Xiangfei Qiu, Hongfan Gao, Jilin Hu, Bin Yang, Chenjuan Guo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=71Mm8GDGYd"
tags: ["query:qf"]
score: 7.0
evidence: 基于Koopman和Kalman的概率时间序列预测
tldr: 本文提出K^2VAE模型，利用Koopman网络将非线性时间序列转化为线性动力系统，再通过Kalman网络细化预测，实现高效的长时期概率预测。该方法缓解了长预测期下非线性动力学的不良影响，并降低了生成模型的计算成本。实验表明在多个基准上优于现有方法，适用于金融时间序列波动率预测等任务。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-71mm8gdgyd/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 770, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-71mm8gdgyd/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1681, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-71mm8gdgyd/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1684, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-71mm8gdgyd/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 824, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-71mm8gdgyd/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1116, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-71mm8gdgyd/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1114, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-71mm8gdgyd/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1116, \"height\": 576, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-71mm8gdgyd/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1598, \"height\": 582, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-71mm8gdgyd/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1725, \"height\": 929, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-71mm8gdgyd/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1728, \"height\": 777, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-71mm8gdgyd/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-71mm8gdgyd/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 825, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-71mm8gdgyd/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 820, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-71mm8gdgyd/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1769, \"height\": 652, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-71mm8gdgyd/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1325, \"height\": 985, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-71mm8gdgyd/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1771, \"height\": 1123, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-71mm8gdgyd/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1772, \"height\": 1124, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-71mm8gdgyd/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1391, \"height\": 441, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-71mm8gdgyd/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1767, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-71mm8gdgyd/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1767, \"height\": 352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-71mm8gdgyd/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1772, \"height\": 286, \"label\": \"Table\"}]"
motivation: 长期概率时间序列预测面临非线性动力学和计算成本高的挑战。
method: 融合Koopman理论线性化动力学，并用Kalman滤波细化状态估计，构建高效的VAE生成模型。
result: 在长期预测任务上取得了优于现有方法的精度和效率。
conclusion: 为长时期概率预测提供了有效且高效的解决方案，可应用于金融领域。
---

## Abstract
Probabilistic Time Series Forecasting (PTSF) plays a crucial role in decision-making across various fields, including economics, energy, and transportation. Most existing methods excell at short-term forecasting, while overlooking the hurdles of Long-term Probabilistic Time Series Forecasting (LPTSF). As the forecast horizon extends, the inherent nonlinear dynamics have a significant adverse effect on prediction accuracy, and make generative models inefficient by increasing the cost of each iteration. To overcome these limitations, we introduce $K^2$VAE, an efficient VAE-based generative model that leverages a KoopmanNet to transform nonlinear time series into a linear dynamical system, and devises a KalmanNet to refine predictions and model uncertainty in such linear system, which reduces error accumulation in long-term forecasting. Extensive experiments demonstrate that $K^2$VAE outperforms state-of-the-art methods in both short- and long-term PTSF, providing a more efficient and accurate solution.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：概率时间序列预测（PTSF）在经济学、能源、交通等决策领域至关重要。现有方法在短期预测上表现良好，但面向长期概率时间序列预测（LPTSF）时面临两个主要挑战：一是时间序列固有的非线性动力学导致状态演化难以建模；二是预测时域延长后误差累积显著，且扩散/流模型迭代成本高，效率与精度同时下降。
- **整体含义**：本文旨在解决LPTSF中的非线性建模与误差累积问题，提出一种高效且准确的VAE生成模型，以支持长期不确定性下的决策。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：利用Koopman理论将非线性时间序列线性化为测量函数空间中的线性动力系统，再通过Kalman滤波思想在数据驱动框架下细化预测并建模过程不确定性，最终构建具有清晰语义的变分后验分布。
- **关键技术细节**：
  - **输入Token嵌入**：将多变量时间序列划分为非重叠patch，展平并线性投影为高维嵌入 \(X^{P'} \in \mathbb{R}^{d \times n}\)。
  - **KoopmanNet**：使用可学习MLP作为测量函数 \(\psi\)，将嵌入投影到测量空间 \(X^{P^*}\)；通过一步eDMD拟合局部Koopman算子 \(K_{\text{loc}}\)，叠加可学习全局部分 \(K_{\text{glo}}\) 得到最终算子 \(K = K_{\text{loc}} + K_{\text{glo}}\)；利用 \(K\) 迭代生成重建上下文 \(\hat{X}^C\) 和预测 \(\hat{X}^H\)。
  - **KalmanNet**：计算非线性残差 \(X^{\text{Res}} = X^{P^*} - \hat{X}^C\)，经Integrator（Transformer编码器）整合为控制输入 \(U\)；构建过程模型 \(z_k = A z_{k-1} + B u_k + w_k\) 和观测模型 \(o_k = H z_k + v_k\)；迭代执行预测步和更新步，输出精炼状态 \(Z\) 和协方差 \(P\)，形成变分分布 \(Q(Z|X) = \mathcal{N}(Z', P)\)。同时使用数值稳定形式保持协方差正定性。
  - **解码器**：利用逆测量函数 \(\psi^{-1}_\mu, \psi^{-1}_\sigma\) 将采样映射回原始空间，建模似然 \(P(Y|Z) = \mathcal{N}(\mu, \sigma)\)。
  - **损失函数**：总体目标为 \(L = L_{\text{ELBO}} + L_{\text{Rec}}\)，其中 \(L_{\text{Rec}}\) 促进测量空间线性化。

## 3. 实验设计

- **数据集**：
  - 短期：ETTh1-S, ETTh2-S, ETTm1-S, ETTm2-S, Electricity-S, Solar-S, Traffic-S, Exchange-S（共8个，上下文长度=预测长度，多为24或30）。
  - 长期：ETTh1-L, ETTh2-L, ETTm1-L, ETTm2-L, Electricity-L, Traffic-L, Exchange-L, Weather-L, ILI-L（共9个，预测长度96/192/336/720，ILI为24/36/48/60；固定上下文长度96，ILI为36）。
- **基准（Benchmark）**：基于ProbTS框架构建，确保评估一致性。
- **对比方法**：共11种，包括：
  - 点预测+分布头：FITS, PatchTST, iTransformer, Koopa。
  - 生成模型：TSDiff, D3VAE, GRU NVP, GRU MAF, Trans MAF, TimeGrad, CSDI。
- **评估指标**：CRPS（Continuous Ranked Probability Score）和NMAE（Normalized Mean Absolute Error），每个结果基于5次独立运行的均值±标准差。

## 4. 资源与算力

- 论文明确说明所有实验使用 **PyTorch**（Python 3.10）在 **NVIDIA Tesla-A800 GPU** 上运行，初始批量大小为32，可降至8以应对OOM。
- **未明确说明**：具体使用的GPU数量、总训练时长、模型参数量等细节。文中仅提到模型轻量（主要由MLP和线性层组成），但未提供FLOPs统计。

## 5. 实验数量与充分性

- **实验组数**：
  - 短期：8个数据集，每个数据集1个预测长度，共8组。
  - 长期：9个数据集 × 4个预测长度 = 36组（但部分baseline因内存/时间缺失部分结果）。
  - 消融实验：包括Koopman算子变体（3种）、KalmanNet连接变体（4种）以及整体模块消融（3种），覆盖短期和长期共10个场景。
  - 模型效率对比：在Electricity-L和ETTm1-L的多个预测长度上对比推理解释时间和峰值内存。
- **充分性与公平性**：所有baseline按原论文超参数设置并额外搜索至多8组；使用固定上下文长度和“drop last=False”避免额外误差；结果报告均值和标准差，体现稳定性。实验设计较为全面客观。

## 6. 主要结论与发现

- K2VAE在短期和长期概率预测上均显著优于所有最强baseline：短期CRPS平均降低7.3%，NMAE降低14.5%（对比第二名的CSDI）；长期CRPS平均降低20.9%，NMAE降低19.9%（对比第二名的PatchTST）。
- 在非平稳数据集（如Exchange）上优势尤为明显，表明线性化+不确定性建模的有效性。
- 随着预测长度增加，K2VAE性能下降幅度最小，体现其缓解误差累积的能力。
- 模型效率突出：在相同任务上（Electricity-L 96-96），K2VAE的推理时间约3.3秒/样本，GPU峰值内存仅0.094GB，而CSDI需388秒和1.411GB，TSDiff需4.77秒和0.255GB。

## 7. 优点

- **方法创新**：首次将Koopman理论与Kalman滤波无缝嵌入VAE框架，赋予隐空间“动力系统不确定性”的物理语义，既处理非线性又降低生成成本。
- **理论基础**：提供了KalmanNet数值稳定性定理（正定性保持）和收敛性定理（控制输入趋于零时状态转移趋近Koopman算子），增强方法可信度。
- **高效轻量**：采用单步VAE生成范式，对比多步扩散/流模型，显著减少计算和内存开销。
- **实验结果扎实**：涵盖广泛数据集、多种预测长度、多轮重复实验，并包含详尽的消融和效率分析。

## 8. 不足与局限

- **实验局限**：部分高维数据集（如Traffic-L, Electricity-L）上某些baseline（如CSDI, Trans MAF）因资源不足未能完整运行，导致对比不够全面。长期实验中ILI数据集规模较小（966时间步），可能限制泛化结论。
- **方法局限**：KalmanNet假设线性高斯噪声，对极端非线性残差（如突变、长程相依）可能仍需依赖Integrator补偿；若测量空间线性化不充分，系统偏差仍会累积。论文未讨论预测区间校准或分布偏移检测。
- **超参数敏感性**：patch大小、隐维度d、KalmanNet迭代次数等未在论文中深入探讨影响，可能存在调参偏差。
- **缺失对比**：未与最新状态空间模型（如Mamba）、时间序列基础模型（如Lag-Llama）等比较，略欠时效性。
- **明确声明**：论文未专门列出“局限性”章节，以上为基于内容的合理推断。

（完）
