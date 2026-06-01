---
title: "LOB-Bench: Benchmarking Generative AI for Finance - an Application to Limit Order Book Data"
title_zh: LOB-Bench：金融生成式AI基准——应用于限价订单簿数据
authors: "Peer Nagy, Sascha Yves Frey, Kang Li, Bidipta Sarkar, Svitlana Vyetrenko, Stefan Zohren, Ani Calinescu, Jakob Nicolaus Foerster"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=CXPpYJpYXQ"
tags: ["query:qf"]
score: 6.0
evidence: 限价订单簿生成数据基准，评估重尾和市场微观结构，契合复合主题的核心
tldr: 金融时间序列领域缺乏统一的生成数据评价标准。本文提出LOB-Bench，用于评估限价订单簿生成数据的质量，涵盖条件与无条件分布差异、重尾特征等统计量，支持多变量评估。基准还包含常用LOB特征如买卖价差等。该工作为金融数据生成与微观结构研究提供了标准化工具，与复合主题中的市场微观结构、尾部风险等方向紧密相关。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 861, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 588, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 865, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1772, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1760, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 855, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 862, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 852, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 839, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1657, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 706, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1717, \"height\": 991, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1773, \"height\": 2005, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1764, \"height\": 1992, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1771, \"height\": 1998, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1772, \"height\": 1998, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 887, \"height\": 1977, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1777, \"height\": 1990, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 792, \"height\": 1371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 787, \"height\": 1914, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 657, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 648, \"height\": 489, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 672, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cxppyjpyxq/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1433, \"height\": 693, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-cxppyjpyxq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1734, \"height\": 719, \"label\": \"Table\"}]"
motivation: 金融限价订单簿生成数据缺乏统一评估标准，难以衡量其真实性和统计一致性。
method: 设计基于条件与非条件分布差异的多变量统计评估框架，并集成常见LOB特征。
result: LOB-Bench能够有效区分不同生成模型的质量，并揭示生成数据与真实数据在重尾等特征上的差异。
conclusion: 该基准为金融生成式AI研究提供了可复现的评估基础，尤其适用于限价订单簿领域。
---

## Abstract
While financial data presents one of the most challenging and interesting sequence modelling tasks due to high noise, heavy tails, and strategic interactions, progress in this area has been hindered by the lack of consensus on quantitative evaluation paradigms. 
To address this, we present **LOB-Bench**, a benchmark, implemented in python, designed to evaluate the quality and realism of generative message-by-order data for limit order books (LOB) in the LOBSTER format. 
Our framework  measures distributional differences in conditional and unconditional statistics between generated and real LOB data, supporting flexible multivariate statistical evaluation. 
The benchmark also includes features commonly used LOB statistics such as spread, order book volumes, order imbalance, and message inter-arrival times, along with scores from a trained discriminator network. Lastly, LOB-Bench contains "market impact metrics", i.e. the cross-correlations and price response functions for specific events in the data. 
We benchmark generative autoregressive state-space models, a (C)GAN, as well as a parametric LOB model and find that the autoregressive GenAI approach beats traditional model classes.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：金融时间序列数据（尤其是高频限价订单簿 LOB）具有高噪声、重尾、多智能体策略交互等复杂特性，但缺乏统一的定量评估范式来评价生成式 AI 模型生成的 LOB 数据的真实性和质量。
- **现有不足**：传统方法要么依赖对“stylized facts”的定性比较（主观、不可量化），要么仅使用交叉熵损失（只衡量单步预测，不能反映自回归采样时的累积误差和分布偏移）。
- **研究目标**：提出 LOB-Bench，一个统一的、可量化的基准，用于评估和比较不同生成模型生成的逐消息级 LOB 数据与真实数据的分布相似性，从而推动该领域标准化和模型迭代。

## 2. 方法论：核心思想、关键技术细节

- **整体框架**：通过一组聚合函数 Φ 将高维 LOB 序列映射到多个一维空间；分别对真实数据和生成数据在这些一维空间上估计分布（直方图）；用距离度量（L1 范数、Wasserstein-1 距离）量化分布差异。
- **无条件评估**：对于每个聚合函数 Φ_i，计算真实分布 p{Φ_i(d)} 与生成分布 p̂{Φ_i(d)} 之间的 L1 距离和 Wasserstein-1 距离（均做归一化便于比较）。
- **条件评估**：将另一个聚合函数 Φ_j 的值分成 10 个分位数桶，在每个桶内评估 Φ_i 的条件分布，并按桶的概率加权平均得到条件距离（公式(4)）。示例：价差条件于交易时段。
- **误差累积分析**：将生成序列按预测步长分段（如 t ∈ [a,b)），计算条件于步长的分布距离，量化自回归误差的“雪球”效应（模型偏移）。
- **市场影响响应函数**：采用 Eisler et al. (2012) 的方法，将影响最优买卖价的事件分为 6 类（市价单/限价单/撤单，各分影响/不影响中间价），计算事件后中间价的平均响应曲线，用 L1 距离 ∆R 比较真实与生成的曲线（公式(6)(7)）。
- **对抗性度量**：训练一个 1D CNN + attention 的判别器（二分类器）区分真实和生成的订单簿状态序列，其 ROC 分数可作为最坏情况下的聚合函数。
- **下游任务测试**：基于 LOBCAST 实现，用 MLP 对中间价趋势进行三分类（上升/下降/平稳），比较仅用真实数据训练和同时用真实+生成数据训练的 F1 分数。
- **所用距离**：L1 范数（总变差距离，值域[0,1]）+ Wasserstein-1 距离（对分布间距离敏感）；L1 采用 Freedman-Diaconis 规则动态选择 bin 宽度。

## 3. 实验设计

- **数据集**：采用 LOBSTER 格式的 Alphabet Inc (GOOG) 和 Intel Corporation (INTC) 股票数据。训练数据为 2022 年全年，测试数据为 2023 年 1 月（子样本）。
- **基准场景**：测试 5 种生成模型：
  - **LOBS5**：自回归状态空间模型（S5 层），35M 参数，基于 Nagy et al. (2023) 缩放。
  - **RWKV-4 / RWKV-6**：基于 RNN 的自回归语言模型，170M 参数，使用字节对编码器，仅用消息序列（不带订单簿状态）。
  - **Coletta**：条件 GAN (C)GAN，原始设计适用于小 tick 股票，且训练集仅为 3 天（2019 年 1 月）。
  - **Baseline (Cont et al. 2010)**：参数化随机模型，用经验到达率代替幂律假设。
- **对比方式**：计算所有模型在上述多种聚合函数（价差、订单簿不平衡、消息间隔、订单深度、成交量、订单流不平衡 OFI 等）上的无条件/条件分布距离，并汇总平均/中位数/IQM 分数；同时比较响应函数曲线和判别器 ROC。
- **下游任务**：MLP 使用同样的真实 + 生成数据，在 GOOG 上测试不同预测视界的 F1 分数。

## 4. 资源与算力

- **LOBS5**：
  - 参数：约 35M。
  - 训练：100 epochs，数据为 2022 年全年（GOOG 和 INTC）。
  - 算力：总计 30.4 L40 days（即 3.8 天 × 8 张 L40 GPU）。
  - 优化器：Adam，余弦学习率调度。
- **RWKV-4 / RWKV-6**：
  - 参数：170M（基于开源预训练权重继续训练）。
  - 训练数据：GOOG 2022（7.5B tokens）和 INTC 2022（5.5B tokens）。
  - 算力：总计 10 L40S days（4 个模型 × 2 个架构 × 2 个数据集）。
  - 优化器：DAdapt-AdamW（无学习率调度），全局梯度范数裁剪到 1.0。
- **Coletta**：原文未明确给出算力，但提及训练和推理计算成本高。
- **Baseline**：参数化模型，计算量小，未量化。
- **判别器**：训练耗时未明确，但提到在 GOOG 2023 数据上 ROC 达到 0.83（LOBS5）和约 1（Baseline）。

**注意**：算力信息主要来自附录 B、C；正文未对 Coletta 和 Baseline 给出详细算力。

## 5. 实验数量与充分性

- **主要实验组数**：
  - 无条件分布比较：两组股票（GOOG、INTC）× 5 个模型 × 约 10 个聚合函数 ≈ 100 个 L1/Wasserstein 距离值（附录 E 图 12-18 提供）。
  - 条件分布比较：部分聚合函数（如 Spread | Hour, Spread | Volatility）在 LOBS5 上可视化（图 19-20）。
  - 响应函数比较：LOBS5 和 Baseline 在 GOOG 上（图 7），另提供 INTC 结果（图 23）。
  - 误差累积（L1 距离 vs 步长）：所有模型（图 18）。
  - 判别器 ROC：LOBS5（图 21-22）。
  - 下游任务（F1 分数）：在 GOOG 上测试多个预测视界（图 8）。
  - 消融实验：bin 尺寸敏感性测试（附录 D，图 11），仅对 LOBS5 验证了半/双倍 bin 对分数影响，表明分数变化在置信区间内，排序稳定。
- **充分性评估**：
  - **优点**：覆盖多个金融统计量、条件评估、响应函数、对抗性、下游任务，且包含两种距离和置信区间。代码开源，可复现。
  - **不足**：
    - 只用两只股票（GOOG 和 INTC），其中 INTC 属于大 tick 股票，Coletta 模型直接失败，使得公平性受限。
    - 未对不同周期（如牛市/熊市、不同年份）进行测试；未测试多资产或跨市场。
    - 消融实验有限：主要针对 bin 尺寸，未系统消融模型组件（如 S5 层数、判别器设计、损失函数）。
    - 下游任务仅测试了简单 MLP，未与更先进预测模型比较。
    - 基准本身仅提供评估框架，未设计“通过/不通过”阈值，需结合实际应用。

## 6. 主要结论与发现

1. **LOBS5 显著优于其他模型**：在多数无条件/条件分布 L1 和 Wasserstein 距离上得分最低（见图 3、4、6）；响应函数也最接近真实数据（图 7）。
2. **传统基线模型（Cont et al. 2010）表现较好但局限**：在订单深度、价格水平等离散指标上匹配良好，但在时间相关和成交量相关指标上差距大（图 6）。
3. **RWKV 模型（4/6）误差累积快**：由于仅使用消息序列（不含订单簿状态），且使用通用字节对编码，难以捕捉 LOB 结构，导致自回归采样后快速偏离真实分布（图 18）。
4. **判别器能轻易区分**：即使 LOBS5 总体最好，判别器 ROC 仍达 0.83；Baseline 更是高达约 1，说明当前生成模型仍存在可识别的系统性缺陷。
5. **生成数据对下游任务无提升**：MLP 使用合成数据训练后 F1 分数未显著高于仅用真实数据，甚至 Coletta 数据使性能下降（图 8）。
6. **误差累积（自回归陷阱）普遍存在**：所有模型随采样步长增加，分布距离逐渐增大，LOBS5 最慢但仍有向坏趋势。

## 7. 优点（方法/实验亮点）

- **首创全分布量化基准**：克服了金融生成模型领域长期缺乏定量比较的瓶颈，使得不同研究可直接对比。
- **丰富的评价维度**：涵盖无条件、条件、响应函数、对抗性、下游任务，能够暴露模型在不同层面的缺点。
- **条件评估的创新**：通过桶加权量化条件分布差异，可用于分析时间依赖、波动率依赖等动态特性。
- **市场影响响应函数**：直接对比经济学经典规律（如平方根律），具有坚实理论和实际意义。
- **对抗性判别器**：提供“最坏情况”下的分布差异度量，能发现其他统计指标不易察觉的缺陷。
- **开源与可扩展**：代码在 GitHub 发布，且允许用户自定义聚合函数和距离度量，易于复现和扩展。
- **算力报告透明**：详细给出了 LOBS5 和 RWKV 的训练资源，有利于研究者复现和比较。

## 8. 不足与局限

- **实验覆盖范围有限**：仅测试了 2 只股票（GOOG、INTC），未涉及更多市场、不同 tick 大小、不同周期。Coletta 在 INTC 上直接失败，导致比较不完全公平。
- **未验证模型泛化性**：训练集为 2022 全年，测试集为 2023 年 1 月，但未测试不同时间段（如 2024 年）或极端市场条件（如闪崩）。
- **下游任务过于简化**：仅使用简单 MLP 做短期预测，未采用更先进的预测模型或不同的下游应用（如最优执行、市场模拟）。
- **消融不足**：仅对 bin 尺寸做敏感性分析，未对模型架构、聚合函数选择、条件桶数等进行系统消融。
- **判别器设计存在偏差**：判别器仅使用订单簿状态序列（不含消息），可能忽略消息级特征；而且训练样本量有限，ROC 分数可能受模型过拟合影响。
- **自回归模型可解释性弱**：评估框架揭示了分布差异，但未能指出具体哪种特征导致差异，不利于针对性改进。
- **基准本身未定义“合格”阈值**：缺少与真实应用的映射（例如多大分布差异对交易模拟是致命的），实用性有待领域共识。

（完）
