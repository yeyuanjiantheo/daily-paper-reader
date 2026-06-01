---
title: Conditional Diffusion Model with Nonlinear Data Transformation for Time Series Forecasting
title_zh: 带非线性数据变换的条件扩散模型用于时间序列预测
authors: "J Rishi, GVS Mothish, Deepak Subramani"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=kcUNMKqrCg"
tags: ["query:qf"]
score: 7.0
evidence: 使用条件扩散模型的时间序列预测生成框架
tldr: 时间序列预测在金融等领域有广泛应用。本文提出CN-Diff，一种条件扩散模型，通过非线性数据变换和可学习条件改进前向过程，简化逆向过程，提升捕捉复杂时间序列模式的能力。新损失函数有助于学习高效先验分布，在多个领域时间序列预测上表现良好。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-kcunmkqrcg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 751, \"height\": 904, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kcunmkqrcg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1424, \"height\": 645, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kcunmkqrcg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1616, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kcunmkqrcg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1613, \"height\": 685, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 864, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 867, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1612, \"height\": 1004, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 799, \"height\": 380, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1609, \"height\": 1007, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 966, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1257, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1066, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1389, \"height\": 465, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1610, \"height\": 1004, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1609, \"height\": 1004, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1759, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1587, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1236, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1213, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1084, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1376, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1287, \"height\": 327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1021, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1018, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kcunmkqrcg/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1043, \"height\": 402, \"label\": \"Table\"}]"
motivation: 扩散模型在时间序列预测中需更好捕捉复杂模式。
method: 提出CN-Diff，引入非线性变换和可学习条件，设计新损失函数训练扩散模型。
result: 在多个时间序列数据集上提升了预测性能，尤其在模式复杂场景。
conclusion: CN-Diff为时间序列预测提供了有效的生成式方法，可拓展至金融领域。
---

## Abstract
Time-series forecasting finds application across domains such as finance, climate science, and energy systems. We introduce the Conditional Diffusion  with Nonlinear Data Transformation Model (CN-Diff), a generative framework that employs novel nonlinear transformations and learnable conditions in the forward process for time series forecasting. A new loss formulation for training is proposed, along with a detailed derivation of both forward and reverse process. The new additions improve the diffusion model's capacity to capture complex time series patterns, thus simplifying the reverse process. Our novel condition facilitates learning an efficient prior distribution. This also reduces the gap between the true negative log-likelihood and its variational approximation. CN-Diff is shown to perform better than other leading time series models on nine real-world datasets. Ablation studies are conducted to elucidate the role of each component of CN-Diff.

---

## 论文详细总结（自动生成）

## 论文结构化总结

### 1. 论文的核心问题与整体含义（研究动机和背景）

时间序列预测在金融、气候科学、能源系统等众多领域具有广泛应用。传统方法（如 ARIMA、RNN、Transformer）和现有扩散模型（如 TimeDiff、CSDI）在处理时间序列时存在两个主要局限：

- **前向过程固定不可学习**：标准扩散模型采用固定的线性高斯噪声加噪，缺乏对数据分布的适应性。
- **先验分布过于简单**：将复杂的时间序列模式强制映射到各向同性高斯先验（`N(0, I)`），导致逆向生成过程困难。

为此，作者提出 **CN-Diff（Conditional Diffusion with Nonlinear Data Transformation）**，通过在前向过程中引入非线性数据变换和可学习条件，使模型能够更好地捕捉时间序列中的复杂模式，简化逆向过程，并缩小真实负对数似然与其变分近似之间的差距。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

**核心思想**：  
将标准扩散模型的前向过程改造为**非马尔可夫过程**，其中每个潜变量 `x_t` 由数据经过一个**非线性时间依赖变换** `T_ϕ(x, t)` 后再添加噪声得到，并引入一个**可学习的条件向量 `c`** 来偏移均值。这样使得逆向过程能够从一个更合适的先验 `N(c, I)` 出发，降低逆向学习难度。

**关键技术细节**：

- **非线性数据变换** `T_ϕ(x, t)`：一个参数为 `ϕ` 的神经网络算子，接收原始数据 `x` 和时间步 `t`，输出变换后的数据，作用于特征维和/或时间窗维。
- **可学习条件 `c`**：由一个单层全连接网络从历史数据 `x_{-L+1:0}` 中生成，作为前向和逆向过程的均值偏移。
- **前向边际分布**（公式1）：  
  `q_ϕ(x_t | x, c) = N(x_t; √ᾱ_t T_ϕ(x, t) + (1 - √ᾱ_t) c, (1 - ᾱ_t) I)`
- **前向后验分布**（可解析推导）：  
  `q_ϕ(x_{t-1} | x_t, x, c)` 通过非马尔可夫链导出，其均值表达式涉及 `T_ϕ(x, t)` 和 `T_ϕ(x, t-1)`。
- **逆向过程定义**（非马尔可夫）：  
  `p_θ(x_{0:T}) = p(x_T) ∏ p_θ(x_{t-1} | x_t) p_θ(x_0 | x_t)`，其中 `p(x_T) = N(c, I)`。
- **损失函数**（公式4）：  
  包含三项：`L_prior`（KL 散度于最终潜变量）、`L_rec`（重建项，对所有 t 求和）、`L_diff`（各步前向后验与逆向分布之间的 KL 散度）。其中 `L_diff` 项优化 `T_ϕ(x, t)` 与 `T_ϕ(ˆx_θ, t)` 之间的差异。
- **训练算法**（Algorithm 1）：采样噪声 `ϵ` 和时间 `t`，前向生成 `x_t`，计算损失并梯度更新 `θ` 和 `ϕ`。
- **推理算法**（Algorithm 2）：从 `N(c, I)` 采样 `x_T`，循环执行去噪步骤，利用 `T_ϕ(ˆx, t)` 和 `T_ϕ(ˆx, t-1)` 更新潜变量。

**独特之处**：  
CN-Diff 的损失函数需要同时预测原始数据 `x` 和变换后的数据 `T_ϕ(x, t)`，这不同于 DDPM 仅预测 `x` 或噪声 `ϵ`。

### 3. 实验设计：数据集、基准测试、对比方法

- **数据集**（9个真实世界多变量/单变量时间序列）：  
  - Wind、Caiso、Traffic、Electricity、Weather、NorPool、Exchange、ETTh1、ETTm1  
  - 涵盖不同频率（15分钟/小时/天）和预测长度（14步到720步）。
- **基准测试**：  
  按照标准拆分（train:validation:test 比例 7:1:2 或 6:2:2）进行多步预测。
- **对比方法**（共23个基线）：  
  - 扩散模型：mr-Diff、TimeDiff、TimeGrad、CSDI、SSSD、D3VAE  
  - 基础扩展模型：N-Hits、FiLM、Depts、NBeats  
  - 生成模型：CPF、PSA-GAN  
  - Transformer 系列：PatchTST、FedFormer、Autoformer、Pyraformer、Informer、Transformer、Scaleformer  
  - 其他深度模型：SCINet、NLinear、DLinear、LSTMa  
  注意：CSDI 在 Traffic 和 Electricity 上因内存溢出未报告结果。

### 4. 资源与算力

论文明确说明：  
- **GPU**：单张 Nvidia RTX A6000（48GB vRAM）  
- **训练参数**：Adam 优化器，学习率 1e-3，batch size 64，最大 epochs 100（early stopping），扩散步数 `T=100`，β 二次方差计划（β_1=1e-4, β_T=0.1）。  
- **训练/推理时间**：附录 G 列出了各模型的训练和推理耗时（毫秒级）。例如 CN-Diff 在 ETTh1 单变量预测中，当 `H=96` 时训练时间 0.21 ms，推理时间 6.2 ms；同等条件下远快于 mr-Diff、TimeDiff、CSDI 等。  
- 未提及总训练时长或 GPU 总量。

### 5. 实验数量与充分性

- **主要实验**：两个大表（Table 1 多变量 MSE，Table 3 单变量 MSE），每个表覆盖 9 个数据集 × 24 个方法。  
- **消融实验**（充分且系统）：  
  - 条件组件消融（Table 4）：DDPM vs 条件 DDPM vs CN-Diff 条件，在3个数据集上展示 MSE/MAE 提升。  
  - 非线性变换消融（Table 5）：无 Tϕ、仅特征维、仅时间窗维、两者皆用，在4个数据集上展示效果。  
  - 联合消融（附录 E.1）：分析单独加 Tϕ、单独加条件、两者都加的贡献。  
  - 超参数消融（附录 E.2/E.3）：回看窗口长度（96/192/336/720/1440）、扩散步数（50/100/200/500）、方差上限 β_T（0.001/0.01/0.1/0.9）。  
  - 额外实验（附录 H）：在股票数据集（CSI-300）和合成数据上对比，以及对比图模型（SageFormer）。  
- **定性分析**：可视化预测结果（图3、图4），并与 Informer、DLinear、FiLM 等比较。  
- **公平性**：大部分基线结果直接引用自 Shen et al. (2024) 的论文，保证了对比的一致性。CN-Diff 的平均排名（多变量 1.7，单变量 2.0）显著优于所有对比方法。

**评价**：实验覆盖了多变量/单变量、不同频率、不同预测长度、多种基线（包括当前 SOTA 扩散模型 mr-Diff），消融实验全面，结果客观可信。

### 6. 论文的主要结论与发现

- CN-Diff 在多变量预测中取得 **6/9 数据集最优**，平均排名 1.7，优于 mr-Diff（平均排名 3.0）等所有基线。  
- 在单变量预测中取得 **4/9 数据集最优**（另有 2 个第二），平均排名 2.0，与 mr-Diff 并列领先。  
- 非线性变换和可学习条件两者结合效果最佳，单独使用任一个都有显著提升。  
- 条件组件在高维度数据集（Traffic 862维、Electricity 321维）上效果更明显，表明其缓解了高维数据从各向同性先验生成的困难。  
- 非线性变换在特征维和时间窗维同时使用时效果最好，说明其能同时捕捉变量间和时序间的相关性。

### 7. 优点

- **方法创新性**：首次在前向过程中同时引入**非线性数据变换**和**可学习条件**，打破标准扩散模型固定前向过程的限制。  
- **理论贡献**：推导了非马尔可夫前向过程下的变分下界，并明确其与 DDPM 目标的联系（Lemma A.1）。  
- **计算效率**：尽管增加了可学习参数，但训练和推理时间远低于其他扩散模型（如 mr-Diff、CSDI），因为非线性变换仅由简单全连接层实现。  
- **广泛的实验验证**：在 9 个真实数据集、23 个基线、多种消融设置下进行了充分验证，结果稳健。  
- **可解释性分析**（附录 H.3）：通过特征相关矩阵展示了 `T_ϕ` 学习到的潜在表示增强了特征间相关性，有利于扩散过程。

### 8. 不足与局限

- **对高波动数据的表现**：在 Wind 数据集上排名第四（多变量），作者归因于 wind 数据的多尺度特征，未来可考虑多分辨率 CN-Diff，但当前未验证。  
- **条件生成依赖历史数据**：条件 `c` 仅从历史数据 `x_{-L+1:0}` 学习，对于非平稳或突发变化可能不够鲁棒。  
- **未讨论不确定性量化**：虽然扩散模型可生成多组样本，但论文未提供预测区间或校准评估。  
- **计算开销分析有限**：虽然给出了单次训练/推理时间，但未提供完整训练总时长或内存峰值占用。  
- **局限性陈述简短**：主要依赖消融实验说明各组件贡献，但对更复杂的现实场景（如缺失值、多步递推误差累积）未作进一步分析。

（完）
