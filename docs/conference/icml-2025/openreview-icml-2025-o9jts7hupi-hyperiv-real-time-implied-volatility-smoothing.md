---
title: "HyperIV: Real-time Implied Volatility Smoothing"
title_zh: HyperIV：实时隐含波动率平滑
authors: "Yongxin Yang, Wenqi Chen, Chao Shu, Timothy Hospedales"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=o9jtS7HupI"
tags: ["query:qf"]
score: 9.0
evidence: 使用超网络进行期权市场隐含波动率实时平滑
tldr: 现有隐含波动率曲面构建依赖繁琐校准过程。本文提出HyperIV，利用超网络生成紧凑神经网络的参数，仅需9个市场观测即可在2毫秒内构建无静态套利的完整波动率曲面。在8个指数期权上实现了更优精度和跨资产泛化能力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-o9jts7hupi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 837, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o9jts7hupi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o9jts7hupi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o9jts7hupi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1680, \"height\": 1540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o9jts7hupi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1491, \"height\": 2072, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-o9jts7hupi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 812, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o9jts7hupi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o9jts7hupi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 865, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o9jts7hupi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 796, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o9jts7hupi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 841, \"height\": 377, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o9jts7hupi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 544, \"height\": 153, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o9jts7hupi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 810, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o9jts7hupi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1313, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o9jts7hupi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1384, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o9jts7hupi/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1166, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o9jts7hupi/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1288, \"height\": 410, \"label\": \"Table\"}]"
motivation: 传统波动率曲面校准耗时且需大量数据。
method: 采用超网络为小型神经网络生成参数，快速构建无套利波动率曲面。
result: 在8个指数期权上精度优于现有方法，且计算速度极快，跨资产泛化良好。
conclusion: HyperIV实现了实时、准确且无套利的波动率曲面估计。
---

## Abstract
We propose HyperIV, a novel approach for real-time implied volatility smoothing that eliminates the need for traditional calibration procedures. Our method employs a hypernetwork to generate parameters for a compact neural network that constructs complete volatility surfaces within 2 milliseconds, using only 9 market observations. Moreover, the generated surfaces are guaranteed to be free of static arbitrage. Extensive experiments across 8 index options demonstrate that HyperIV achieves superior accuracy compared to existing methods while maintaining computational efficiency. The model also exhibits strong cross-asset generalization capabilities, indicating broader applicability across different market instruments. These key features -- rapid adaptation to market conditions, guaranteed absence of arbitrage, and minimal data requirements -- make HyperIV particularly valuable for real-time trading applications. We make code available at https://github.com/qmfin/hyperiv.

---

## 论文详细总结（自动生成）

# 中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- 隐含波动率曲面是期权定价和风险管理的基础工具，但其构建过程面临三大挑战：
    - **套利约束**：曲面必须无静态套利（日历价差套利和蝶式套利），简单插值不可行；
    - **实时性要求**：市场快速变化，需要频繁校准，传统优化方法耗时；
    - **数据稀疏性**：在高频交易（如分钟级）中，仅有极少数合约（<10个）具有可靠报价，很难支撑传统模型拟合。
- 现有方法（如SSVI、SABR、深度神经网络）要么要求大量观测数据，要么校准时间较长，无法同时满足稀疏数据、实时和无套利的苛刻需求。
- 本文提出 **HyperIV**，利用**超网络**（hypernetwork）从仅9个市场观测出发，在**2毫秒**内生成无静态套利的完整波动率曲面，解决了上述矛盾，填补了高频实时应用与机器学习方法之间的空白。

## 2. 论文提出的方法论

### 核心思想
- 定义一个由**参考集** \( Z = \{(k_i, t_i, \sigma_i)\}_{i=1..9} \) 到波动率曲面的映射 \( \sigma = f_\theta(k,t|Z) \)。其中 \( k \) 为对数远期资金率，\( t \) 为到期时间。
- 将 \( f_\theta \) 分解为**超网络** \( g_\theta \) 和**紧凑网络** \( h_\omega \)：
  \[
  \omega = g_\theta(Z),\quad \sigma = h_\omega(k,t)
  \]
  - \( g_\theta \)：采用 Transformer 编码器（无位置嵌入）处理 \( Z \)，输出扁平向量，再分割为 \( h_\omega \) 的权重参数。
  - \( h_\omega \)：一个两层MLP（输入2→16→16→1，共337个参数），最后一层使用 Softplus 保证非负输出。

### 关键技术细节
- **数据输入**：参考集 \( Z \) 选择流动性最好的9个合约：{At-the-Money, 25Δ Call, 25Δ Put} × {7天, 1月, 3月}。
- **训练目标**：在历史数据上优化 \( g_\theta \) 的参数，最小化预测隐含波动率与真实值的均方误差（式8）。
- **无套利约束**：添加辅助损失（式14~17），包括：
  - 日历套利约束（式15）：确保总隐含方差随到期时间单调不减；
  - 蝶式套利约束（式16、17）：保证对应密度非负且积分为1。
  辅助损失在训练末期趋近于 \( 10^{-8} \)，测试时约 \( 10^{-6} \)，近似实现了无套利条件。
- **推理**：对新市场观测只需一次前向传播即可得到完整曲面，无需额外优化。

### 算法流程（文字说明）
1. 对每个时间间隔，从历史数据中提取9个参考合约的 \( (k, t, \sigma) \) 作为参考集 \( Z \)。
2. 将 \( Z \) 输入超网络 \( g_\theta \)，得到紧凑网络 \( h_\omega \) 的参数向量 \( \omega \)。
3. 对于任意查询点 \( (k, t) \)，通过 \( h_\omega \) 计算隐含波动率 \( \sigma \)。
4. 训练时联合优化式8（拟合损失）和式14（无套利损失），仅更新 \( g_\theta \)。

## 3. 实验设计

### 数据集与场景
- **数据来源**：指数期权（欧洲期权），包括8种资产：
  - 1分钟频：SPX（标普500）、NDX（纳斯达克100）；
  - 1天频（EOD）：SPX、NDX、RUT（罗素2000）、VIX（波动率指数）、MXWLD（MSCI世界）、MXEF（MSCI新兴市场）。
- 数据时段：训练集与测试集按时间划分，1分钟数据训练至2023-08-01，之后测试；1天数据训练至2023-01-01，之后测试。共超过15万个曲面、5000万合约。

### 对比方法（Baselines）
- **SSVI**：直接对9个观测点校准SSVI参数模型（4个参数）。
- **VAE**：改编自Bergeron et al. (2021) 的变分自编码器，使用固定网格虚拟期权作为输入。
- **GNO**：改编自Gonon et al. (2024) 的图神经算子，将参考集构造为图结构进行预测。
- 所有方法均经过适配，使其能处理仅9个观测点的稀疏输入场景。

### 评估指标
- 测试集上的**平均绝对误差（MAE）**：隐含波动率（表4）和期权价格（表5）。
- 还进行了定性展示（图1-3）、误差分解（图4、5）、跨资产泛化（表6、7）以及辅助损失分析。

## 4. 资源与算力

- **硬件**：单张 NVIDIA A100 GPU（80GB VRAM），SSVI在 Intel Xeon CPU上运行。
- **训练成本**：每步（batch size=128）耗时约2.82秒（HyperIV），共500个epoch，每个epoch处理所有interval。训练内存约821 MiB。
- **推理成本**：生成一张含10,000个点的曲面仅需2.09毫秒（A100），在M2芯片上约为8毫秒。
- 对比：VAE训练内存9.7 GiB、GNO训练内存77.8 GiB，推理时间分别为0.34 ms和7.86 ms（A100）。
- **代码开源**：https://github.com/qmfin/hyperiv 。

## 5. 实验数量与充分性

- **实验数量**：覆盖8个资产×2个时间频率共8个主实验（1分钟频2个，1天频6个）；跨资产泛化实验（任意资产间转移共8×8个组合）；误差维度分析（时间、资金率、到期时间）；辅助损失消融（无套利约束的效果）。总体实验规模充分。
- **公平性**：所有基线均针对稀疏数据场景进行了适配（如VAE需生成虚拟固定网格期权；GNO限制参考集节点），且对比时采用相同9个观测点。评估使用独立测试集，未出现数据泄露。
- **充分性**：定量结果清晰显示HyperIV在绝大多数情况下最优，且在困难资产（VIX、MXEF）上显著优于基线。泛化实验也表明其鲁棒性。

## 6. 论文的主要结论与发现

- **精度**：HyperIV在8个数据集中7个取得隐含波动率MAE最低（表4），在价格MAE中同样占优（表5），仅1分钟SPX上略逊于GNO。
- **速度**：推理2毫秒，满足实时交易需求。
- **无套利保证**：辅助损失趋近于零，实际生成的曲面无日历套利和蝶式套利（图3验证）。
- **跨资产泛化**：除VIX外，HyperIV在资产之间迁移（如SPX→NDX）的误差甚至低于直接在目标资产上校准SSVI的误差（表6、7）。
- **数据需求量小**：仅需9个合约即可构造完整曲面，尤其适合流动性差的市场。

## 7. 优点（方法/实验设计的亮点）

1. **定义全新问题**：首次将极稀疏数据（<10个观测）下的实时波动率曲面平滑作为独立问题研究，具有重要的实践意义。
2. **超网络架构创新**：利用超网络绕过传统校准流程，将参考集直接映射为网络参数，实现一次性推理，避免了每时刻的二次优化。
3. **无套利约束的软实现**：通过辅助损失而非硬编码参数域，既保持神经网络灵活性又实际规避套利。
4. **计算效率极高**：模型隐式曲面网络仅337参数，推理速度快，内存占用低（训练仅821 MiB）。
5. **实验全面公正**：对比多种现有方法并合理适配，包含多资产、多频率、跨泛化以及误差分解，验证了方法的鲁棒性。
6. **代码开源**：便于复现和后续研究。

## 8. 不足与局限

1. **可解释性差**：与SSVI等参数模型不同，HyperIV生成的参数（337个）没有直观的金融含义，难以为交易员提供直接见解。
2. **算力依赖**：虽然推理很快，但训练需要GPU（A100），且推理在GPU上更优（M2上2ms→8ms），相比SSVI可在CPU上运行构成一定限制。
3. **数据许可限制**：无法公开训练数据，仅能引用商业数据库（WRDS OptionMetrics），学术复现需依赖机构订阅。
4. **辅助损失并非硬约束**：虽然实证接近零，但理论上仍存在微小套利可能，不过论文指出实际交易成本会使套利不可行。
5. **未考虑时序动态**：当前模型仅利用当前时刻的观测，未引入历史时间序列信息（如隐含波动率的演化），未来可扩展。
6. **无解释模型**：未包含与更多现代深度学习方法（如物理信息神经网络、神经微分方程）的对比，可能遗漏更优方案。

（完）
