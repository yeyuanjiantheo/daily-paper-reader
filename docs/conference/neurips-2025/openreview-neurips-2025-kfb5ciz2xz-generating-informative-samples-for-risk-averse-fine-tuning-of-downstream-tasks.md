---
title: Generating Informative Samples for Risk-Averse Fine-Tuning of Downstream Tasks
title_zh: 为下游任务的风险厌恶微调生成信息样本
authors: "Heasung Kim, Taekyun Lee, Hyeji Kim, Gustavo De Veciana"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=kfB5Ciz2XZ"
tags: ["query:qf"]
score: 8.0
evidence: 通过最小化条件风险价值（CVaR）生成信息样本以进行风险厌恶微调，处理尾部风险
tldr: 高风险场景中直接最小化条件风险价值（CVaR）面临极值事件估计困难。本文提出利用扩散生成模型从重加权分布中采样，合成高损失样本用于CVaR优化。该方法有效提升了模型对尾部风险的鲁棒性，可应用于金融领域风险厌恶建模、VaR和ES估计等尾部风险管理任务。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-kfb5ciz2xz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1121, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kfb5ciz2xz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 522, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kfb5ciz2xz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1378, \"height\": 409, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-kfb5ciz2xz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1385, \"height\": 258, \"label\": \"Table\"}]"
motivation: 直接最小化CVaR难以准确估计极端高损失事件。
method: 使用基于分数的扩散生成模型合成高损失样本实现CVaR优化。
result: 在多个下游任务中显著提升模型的尾部风险性能。
conclusion: 为风险厌恶建模提供了一种有效的数据增强方法。
---

## Abstract
Risk-averse modeling is critical in safety-sensitive and high-stakes applications. Conditional Value-at-Risk (CVaR) quantifies such risk by measuring the expected loss in the tail of the loss distribution, and minimizing it provides a principled framework for training robust models. However, direct CVaR minimization remains challenging due to the difficulty of accurately estimating rare, high-loss events—particularly at extreme quantiles. In this work, we propose a novel training framework that synthesizes informative samples for CVaR optimization using score-based generative models. Specifically, we guide a diffusion-based generative model to sample from a reweighted distribution that emphasizes inputs likely to incur high loss under a pretrained reference model. These samples are then incorporated via a loss-weighted importance sampling scheme to reduce noise in stochastic optimization. We establish convergence guarantees and show that the synthesized, high-loss-emphasized dataset substantially contributes to the noise reduction. Empirically, we validate the effectiveness of our approach across multiple settings, including a real-world wireless channel compression task, where our method achieves significant improvements over standard risk minimization strategies.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：在高风险应用（如医疗、无线通信、大语言模型等）中，模型必须对罕见但代价高昂的失败具有鲁棒性，而不仅仅是追求平均性能。
- **核心问题**：条件风险价值（CVaR）作为度量尾部风险的常用指标，其最小化在极端分位数（ω→1）时面临严重挑战——标准蒙特卡洛方法因高损失样本稀有，导致CVaR估计方差极大、优化效率低。
- **整体含义**：本文提出利用生成模型主动合成高损失样本，以降低CVaR优化的噪声，提升模型在尾部风险场景下的鲁棒性。

## 2. 方法论：核心思想、关键技术细节
### 核心思想
- 利用预训练任务模型（参数ϑ₀）的损失值作为指导，引导基于分数的生成模型从重加权分布 \( q(x) \propto \varsigma(\ell(\vartheta_0; x)) p(x) \) 中采样，其中 \( \varsigma \) 是非递减的权重函数（如平方根），使得采样偏向高损失区域。
- 将这些重要性样本用于CVaR最小化的重要性加权随机优化，以降低优化方差。

### 关键技术细节
- **生成模型**：采用扩散/基于分数的生成模型，通过训练免费指导（training-free guidance）技术，利用预训练损失值调整采样过程，无需重新训练生成模型。
- **重要性采样**：样本的似然比 \( p(x)/q(x) = Z / \varsigma(\ell(\vartheta_0; x)) \)，其中 \( Z = \mathbb{E}_{p}[\varsigma(\ell(\vartheta_0; X))] \)。优化目标为：
  \[
  F_\omega(\vartheta, \varrho) = \varrho + \frac{1}{1-\omega} \mathbb{E}_{q} \left[ \frac{Z}{\varsigma(\ell(\vartheta_0; X))} (\ell(\vartheta; X) - \varrho)^{+} \right].
  \]
- **算法流程**（Algorithm 1）：
  1. 使用预训练模型损失指导生成模型，生成 B_q 个重要性样本。
  2. 计算归一化因子 Z（通过基分布样本近似）。
  3. 在每次迭代中，从 q 中采样并估计 CVaR 目标，执行次梯度下降更新参数 ϑ 和阈值 ϱ。
- **理论贡献**：在凸性、光滑性、有界损失等假设下，证明了 O(1/√K) 的收敛速率，且噪声项依赖于初始损失值，表明高损失样本有助于降低优化噪声。

## 3. 实验设计
### 数据集/场景
1. **合成回归任务**：输入 x ∈ ℝ² 来自三个高斯混合分量（权重分别为 0.01, 0.001, 0.989），预测第二坐标从第一坐标，使用二次回归模型和 MSE 损失。旨在模拟极端不平衡的尾部风险场景。
2. **真实世界无线信道状态信息（CSI）压缩任务**：使用 Quadriga 模拟器生成的 256×32 复矩阵 CSI 数据集；任务模型为向量量化自编码器（VQ-VAE），用于压缩 CSI 反馈。

### Benchmark 与对比方法
- 所有方法从相同预训练检查点开始，使用相同数量的生成样本（RAMIS 使用损失引导的重要性样本，其他方法使用标准样本）。
- 对比方法：
  - **SSGM**：CVaR 的随机次梯度方法（无重要性采样）
  - **DORO**：分布鲁棒优化
  - **φ²-DRO**：基于 f-散度的分布鲁棒优化
  - **ERM**：经验风险最小化（ω=0 的 CVaR）

### 评估指标
- CVaR 在不同分位数水平 ω（0.99, 0.95, 0.9, 0.8, 0.5）下的 MSE 值，越低越好。

## 4. 资源与算力
- **文中说明**：未明确提及 GPU 型号、数量或训练时长。但提供了源代码链接（GitHub），实现基于 PyTorch 和 Hugging Face Diffusers 库。
- **备注**：作者声明实验在一台配备 GPU 的服务器上完成，但具体算力细节未披露。合成实验可快速运行，CSI 实验需要训练扩散模型和 VQ-VAE，但具体计算资源未量化。

## 5. 实验数量与充分性
- **实验组数**：
  - 合成回归：100 次随机试验（mean±std），报告了 5 个 ω 水平的结果。
  - CSI 压缩：10 次随机试验，报告了 6 个 ω 水平的结果。
  - 消融分析（附录 E）：额外研究了权重函数 ς 的选择（不同映射）以及样本生成计算成本。
  - 可视化：展示了高损失样本的典型示例。
- **充分性评价**：实验覆盖了从合成数据到真实应用的场景，对比了多个强基线，运行多次取均值和标准差，统计合理。但仅在一个真实任务上验证，跨领域泛化性未充分展示。消融实验仅部分在附录中，主文未深入分析。

## 6. 主要结论与发现
- **合成高损失样本的有效性**：损失引导的生成采样能够有效覆盖尾部区域，生成样本的损失比基分布样本高 4.7×10⁴ 数量级。
- **CVaR 性能提升**：在所有 ω 水平上，RAMIS 均取得最低的 CVaR，尤其在极端分位数（ω=0.99）上显著优于 SSGM、DORO、φ²-DRO、ERM。
- **不牺牲平均性能**：在 ω=0 时 RAMIS 与 ERM 性能接近，表明未损害平均情况。
- **理论支持**：证明了重要性采样可降低 CVaR 优化的噪声项，且高损失区域对梯度贡献大，从而更高效。

## 7. 优点
- **创新性**：首次利用生成模型主动合成针对 CVaR 优化的重要性样本，而非被动重加权已有数据。
- **框架简洁高效**：训练前一次生成重要性样本，后续优化无额外计算开销（仅标量加权）。
- **理论保证**：提供了收敛速率及噪声降低的数学证明，解释了高损失样本为何有益。
- **实用性强**：在无线通信等真实高风险任务中表现出显著改进，且与现有鲁棒方法兼容。

## 8. 不足与局限
- **实验覆盖**：仅在一个真实任务（无线 CSI 压缩）上验证，缺乏更多高风险领域（如医学、金融、自动驾驶）的测试。
- **生成模型依赖**：假设已经拥有高质量的预训练生成模型，这在某些领域可能难以获得；生成质量直接影响重要性样本的有效性。
- **预训练任务模型质量敏感**：引导依赖于预训练模型损失，若预训练模型很差，则引导可能失效。
- **权重函数 ς 的选择**：虽然论文指出按需选择（如平方根或恒等映射），但最优选择可能依赖任务，未提供通用自适应机制。
- **资源消耗**：未提供生成样本阶段的具体计算成本，大规模应用时生成大量重要性样本可能仍昂贵。
- **理论假设较强**：收敛分析依赖于凸性、光滑性、有界损失等假设，这些对于深度神经网络可能不严格成立。

（完）
