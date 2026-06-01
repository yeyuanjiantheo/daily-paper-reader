---
title: Non-stationary Diffusion For Probabilistic Time Series Forecasting
title_zh: 非平稳扩散用于概率时间序列预测
authors: "Weiwei Ye, Zhuopeng Xu, Ning Gui"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=afpc1MFMYU"
tags: ["query:qf"]
score: 8.0
evidence: 使用扩散模型进行概率时间序列预测以捕捉非平稳不确定性
tldr: 现有扩散模型在时间序列预测中因固定方差假设难以捕捉动态不确定性。本文提出非平稳扩散（NsDiff），利用位置-尺度噪声模型（LSNM）替代传统加性噪声模型，结合条件生成模型与预训练条件均值，有效建模时变不确定性模式。在多个数据集上展示优于基线，为金融时间序列波动率建模提供了可迁移的概率预测框架。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-afpc1mfmyu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 861, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afpc1mfmyu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1595, \"height\": 997, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afpc1mfmyu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1613, \"height\": 274, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afpc1mfmyu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 781, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afpc1mfmyu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1606, \"height\": 1096, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-afpc1mfmyu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 790, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-afpc1mfmyu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 958, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-afpc1mfmyu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 804, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-afpc1mfmyu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 785, \"height\": 419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-afpc1mfmyu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1604, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-afpc1mfmyu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 741, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-afpc1mfmyu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 865, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-afpc1mfmyu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1662, \"height\": 710, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-afpc1mfmyu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 766, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-afpc1mfmyu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 511, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-afpc1mfmyu/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1715, \"height\": 362, \"label\": \"Table\"}]"
motivation: 现有扩散模型在时间序列预测中假设恒定方差，无法捕捉不确定性随时间变化的非平稳特性。
method: 提出非平稳扩散（NsDiff）框架，利用位置-尺度噪声模型放松固定方差假设，结合去噪扩散条件生成模型与预训练条件均值实现概率预测。
result: 在多个标准时间序列数据集上，NsDiff在预测准确性和不确定性量化上超越现有扩散模型及经典方法。
conclusion: NsDiff为时变不确定性下的概率时间序列预测提供了有效方案，可推广至金融波动预测等应用。
---

## Abstract
Due to the dynamics of underlying physics and external influences, the uncertainty of time series often varies over time. However, existing Denoising Diffusion Probabilistic Models (DDPMs) often fail to capture this non-stationary nature, constrained by their constant variance assumption from the additive noise model (ANM). In this paper, we innovatively utilize the Location-Scale Noise Model (LSNM) to relax the fixed uncertainty assumption of ANM. A diffusion-based probabilistic forecasting framework, termed Non-stationary Diffusion (NsDiff), is designed based on LSNM that is capable of modeling the changing pattern of uncertainty. Specifically, NsDiff combines a denoising diffusion-based conditional generative model with a pre-trained conditional mean and variance estimator, enabling adaptive endpoint distribution modeling. Furthermore, we propose an uncertainty-aware noise schedule, which dynamically adjusts the noise levels to accurately reflect the data uncertainty at each step and integrates the time-varying variances into the diffusion process. Extensive experiments conducted on nine real-world and synthetic datasets demonstrate the superior performance of NsDiff compared to existing approaches. Code is available at https://github.com/wwy155/NsDiff.

---

## 论文详细总结（自动生成）

### 论文详细中文总结

#### 1. 核心问题与整体含义（研究动机和背景）

- **背景**：概率时间序列预测需要估计未来分布及其不确定性。去噪扩散概率模型（DDPM）在生成高维数据上表现优异，但现有DDPM基于加性噪声模型（ANM），假设噪声方差恒定（如 $\mathcal{N}(0,I)$ 或 $\mathcal{N}(f(X), I)$），无法捕捉非平稳时间序列中随时间变化的不确定性。
- **核心问题**：如何使扩散模型能够显式建模动态不确定性，从而适应时变方差的数据分布。
- **整体含义**：本文首次将位置-尺度噪声模型（LSNM）引入概率时间序列预测，提出非平稳扩散框架（NsDiff），放松了固定方差假设，使模型能同时学习条件均值和条件方差，显著提升了非平稳场景下的不确定性估计质量。

#### 2. 方法论

- **核心思想**：用LSNM替换传统ANM，建模为 $Y = f_\phi(X) + \sqrt{g_\psi(X)}\epsilon$，其中 $f$ 估计条件期望，$g$ 估计条件方差。将扩散过程的端点分布设为 $\mathcal{N}(f_\phi(X), g_\psi(X))$，并设计不确定性感知噪声调度，使前向过程的方差从真实数据方差 $\sigma_{Y_0}$ 逐步变化到端点方差 $g_\psi(X)$。
- **关键技术细节**：
  - **前向过程**：$q(Y_t | Y_{t-1}) = \mathcal{N}\left(\sqrt{\alpha_t}Y_{t-1} + (1-\sqrt{\alpha_t})f_\phi(X),\; \beta_t^2 g_\psi(X) + \alpha_t\beta_t\sigma_{Y_0}\right)$。通过推导得到闭式采样 $q(Y_t | Y_0) = \mathcal{N}\left(\sqrt{\bar{\alpha}_t}Y_0 + (1-\sqrt{\bar{\alpha}_t})f_\phi(X),\; (\bar{\beta}_t - \tilde{\beta}_t)g_\psi(X) + \tilde{\beta}_t\sigma_{Y_0}\right)$。
  - **反向过程**：后验 $q(Y_{t-1}|Y_t,Y_0)$ 为正态分布，均值 $\tilde{\mu} = \gamma_0 Y_0 + \gamma_1 Y_t + \gamma_2 f_\phi(X)$，方差 $\tilde{\sigma}$ 由参数组合给出。训练时用网络 $\xi_\theta(Y_t, f, g, t)$ 同时预测噪声 $\eta_\theta$ 和方差 $\sigma_\theta$。
  - **损失函数**：$\mathcal{L} = \mathbb{E}\left[ \|\eta - \eta_\theta\|_2^2 + \sum_i \frac{\tilde{\sigma}_i}{\sigma_{\theta,i}} - \sum_i \log\left(\frac{\tilde{\sigma}_i}{\sigma_{\theta,i}}\right) \right]$，第一项为噪声匹配，后两项为不确定性优化。
  - **推理**：初始化 $Y_T \sim \mathcal{N}(f_\phi(X), g_\psi(X))$，在每一步需要估计 $\sigma_{Y_0}$。利用 $\tilde{\sigma}$ 关于 $\sigma_{Y_0}$ 的二次方程求解（式18），保证有唯一正根。然后计算 $\hat{Y}_0$ 并采样。
  - **预训练**：$f_\phi$ 使用非平稳Transformer训练，$g_\psi$ 使用滑动窗口提取地面真实方差并训练三层MLP（softplus激活）。
- **公式/算法流程**：见Algorithm 1（训练）和Algorithm 2（推理），用文字概括如上。

#### 3. 实验设计

- **数据集**：
  - 9个真实世界数据集：Electricity (ECL)、ILI、ETT {h1, h2, m1, m2}、ExchangeRate (EXG)、Traffic、SolarEnergy (Solar)。特征维度、时间步长、预测步长及不确定性变化比（测试集方差/训练集方差）各异，Traffic变化比最大（181.83）。
  - 2个合成数据集：线性增长方差（1→10）和二次增长方差（1→100），由LSNM生成。
- **Benchmark与对比方法**：
  - 基准线：TimeGrad (2021)、CSDI (2022)、TimeDiff (2023)、DiffusionTS (2024)、TMDM (2024)。
  - 评估指标：连续排名概率分数（CRPS）和分位数区间覆盖率误差（QICE），数值越小越好。
- **实验设置**：输入长度168，预测长度（ETT系列192，ILI 36，其他192），时间步T=20，线性噪声调度（β1=1e-4, βT=0.02），学习率0.001，batch size 32，训练10个epoch。推理时生成100个样本估计分布。所有实验跑种子1/2/3，取验证集最优结果。

#### 4. 资源与算力

- **论文未明确说明**所使用的GPU型号、数量及训练时长。仅提及学习率、batch size和epoch数。因此无法准确评估算力开销。从计算效率比较表（Table 9）中可知，NsDiff在ETTh1上的训练内存68.20 MB，推理内存57.75 MB，训练时间32.13 ms/iter，推理时间208.07 ms（估计为单样本耗时）。相比TMDM（221.58 MB, 33.26 ms, 237.37 ms）更高效，但未说明硬件配置。

#### 5. 实验数量与充分性

- **实验数量**：
  - 主实验：9个真实数据集 + 2个合成数据集，共11个场景。
  - 消融实验：在ETTh1上对比w/o LSNM、w/o UANS和完整NsDiff，每组3个种子，报告均值和标准差。
  - 额外实验：点预测结果（MSE/MAE，表6/7）、计算效率对比（表9）、预训练影响（表8）。
- **充分性评价**：
  - 真实数据集覆盖了不同领域、不同变化程度，特别是Traffic（最高变化比）上NsDiff提升最大，验证了方法优势。
  - 合成数据明确控制方差变化模式，定量说明QICE提升78.3%~88.3%，因果清晰。
  - 消融实验分离了LSNM端点和不确定性感知噪声调度的贡献，证明两者均必要。
  - 基线选择全面，包括最新SOTA TMDM。
  - **尚可改进**：未在更多样化的非平稳模式（如周期方差、突变）上验证；合成数据仅线性和二次，未涵盖更复杂分布；点预测结果表中TimeDiff在某些MSE/MAE上更好，但NsDiff总体最优。

#### 6. 主要结论与发现

- NsDiff在大多数真实数据集上取得最佳CRPS和QICE，尤其在不确定性变化大的数据集（Traffic QICE降低66.3%）上优势显著。
- 在合成数据上，NsDiff的QICE比TMDM分别降低78.3%（线性）和88.3%（二次），证明其能准确捕捉方差变化。
- 不确定性感知噪声调度（UANS）优于固定噪声或仅依赖完美估计器（w/o UANS），因为后者可能过拟合。
- 消融实验显示LSNM端点（预训练均值+方差）和动态噪声调度均对性能有贡献，完整模型鲁棒性最强。
- 计算效率上，NsDiff训练和推理时间均低于TMDM，内存消耗适中。

#### 7. 优点

- **方法创新性**：首次将LSNM融入DDPM，突破固定方差假设，为概率预测提供更灵活的不确定性建模框架。
- **噪声调度可解释性**：不确定性感知噪声调度使前向过程方差从实际数据方差平滑过渡到估计端点方差，符合直觉且数学推导严谨（闭式解、二次方程求解）。
- **推理自适应**：通过反向过程预测的方差 $\sigma_\theta$ 反推 $\sigma_{Y_0}$，不依赖完美预训练方差估计器，提升了鲁棒性。
- **框架模块化**：均值估计器 $f$ 和方差估计器 $g$ 均为预训练的可替换模块，选择非平稳Transformer作为主干，但兼容其他模型（如DLinear）。
- **实验充分且公平**：多个种子、标准指标、消融对比、计算效率分析，代码开源，可复现。

#### 8. 不足与局限

- **预训练依赖**：需要额外预训练 $f$ 和 $g$ 两个网络，增加了训练流程复杂度。端到端训练也可行（表8显示仅1.86%退化），但论文未深入讨论。
- **方差估计偏差**：$g_\psi$ 使用滑动窗口估计 $\sigma_{Y_0}$，窗口大小固定（96），可能不适用于所有尺度或突变场景。
- **理论限制**：推理时求解二次方程要求 $\lambda_2 < 0$（式17），论文声称在默认β设置下满足，但未严格证明所有情况均成立，理论保证稍弱。
- **实验局限性**：仅限于长期预测（预测长度192或36），未测试短中期或极高维场景；合成数据模式简单，未覆盖更复杂非平稳性（如漂移、跳跃）；未在更大规模数据集（如气象、经济）上验证。
- **计算效率描述模糊**：未提供具体GPU型号，比较表9中内存和时间可能因实现差异不可直接复现。
- **应用限制**：依赖方差可估的场合，对于噪声完全未知或方差极不合理的数据（如接近常数），$g$ 可能失效。

（完）
