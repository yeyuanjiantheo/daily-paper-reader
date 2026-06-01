---
title: "Breaking Silos: Adaptive Model Fusion Unlocks Better Time Series Forecasting"
title_zh: 打破孤岛：自适应模型融合解锁更优时间序列预测
authors: "Zhining Liu, Ze Yang, Xiao Lin, Ruizhong Qiu, Tianxin Wei, Yada Zhu, Hendrik Hamann, Jingrui He, Hanghang Tong"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=sdFRCRk1pP"
tags: ["query:qf"]
score: 7.0
evidence: 自适应模型融合用于时间序列预测
tldr: 时间序列预测中不同模型在不同样本上各有优势，但缺乏自适应融合方法。本文提出TimeFuse框架，利用元特征描述输入时间序列，训练可学习的融合函数，在样本级别自适应整合多个异构预测模型的输出。实验显示融合模型在多个基准上持续优于单一最佳模型，为金融时间序列预测提供灵活的集成策略。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-sdfrcrk1pp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 765, \"height\": 861, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdfrcrk1pp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdfrcrk1pp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1761, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdfrcrk1pp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1750, \"height\": 296, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdfrcrk1pp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 497, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdfrcrk1pp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 813, \"height\": 646, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-sdfrcrk1pp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 757, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sdfrcrk1pp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1779, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sdfrcrk1pp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1782, \"height\": 539, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sdfrcrk1pp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1776, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sdfrcrk1pp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 841, \"height\": 574, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sdfrcrk1pp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 866, \"height\": 610, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sdfrcrk1pp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1774, \"height\": 881, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sdfrcrk1pp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1779, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sdfrcrk1pp/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1782, \"height\": 1080, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sdfrcrk1pp/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1677, \"height\": 1824, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sdfrcrk1pp/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1429, \"height\": 2128, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sdfrcrk1pp/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1778, \"height\": 2236, \"label\": \"Table\"}]"
motivation: 现有时间序列预测中不同模型对不同样本表现各异，但缺乏自适应融合方法。
method: 提出TimeFuse框架，利用元特征表征输入序列，训练可学习融合器在样本级别组合多个异构模型输出。
result: 在多个公开时间序列数据集上，自适应融合显著优于所有单一模型和传统集成方法。
conclusion: 为时间序列预测提供了一种无需先验的样本级模型自适应集成方案，可直接应用于金融预测。
---

## Abstract
Time-series forecasting plays a critical role in many real-world applications. Although increasingly powerful models have been developed and achieved superior results on benchmark datasets, through a fine-grained sample-level inspection, we find that (i) no single model consistently outperforms others across different test samples, but instead (ii) each model excels in specific cases. These findings prompt us to explore how to adaptively leverage the distinct strengths of various forecasting models for different samples. We introduce TimeFuse, a framework for collective time-series forecasting with sample-level adaptive fusion of heterogeneous models. TimeFuse utilizes meta-features to characterize input time series and trains a learnable fusor to predict optimal model fusion weights for any given input. The fusor can leverage samples from diverse datasets for joint training, allowing it to adapt to a wide variety of temporal patterns and thus generalize to new inputs, even from unseen datasets. Extensive experiments demonstrate the effectiveness of TimeFuse in various long-/short-term forecasting tasks, achieving near-universal improvement over the state-of-the-art individual models. Code is available at https://github.com/ZhiningLiu1998/TimeFuse.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现有时间序列预测模型在基准数据集上表现优异，但在细粒度样本级分析中发现：**没有任何单一模型能在所有测试样本上始终保持最优**，每个模型只在其擅长的特定类型样本上表现突出（例如，最好的模型也仅能在约23.2%的样本上获得第一）。因此，如何根据不同输入样本的时序特性，**自适应地融合多个异构模型**，成为一个关键研究问题。
- **研究动机**：希望通过一种自适应的融合策略，在测试时动态选择每个样本对应的最优模型组合，从而突破单一模型的性能天花板，实现“1+1>2”的效果。
- **整体含义**：该工作提出了一种通用框架，无需预知哪个模型对某类样本更好，而是让模型根据输入特征自动学习融合权重，从而提升整体预测准确性。

### 2. 论文提出的方法论

- **核心思想**：构建一个可学习的“融合器”（fusor），输入为时间序列的**元特征**（meta-features），输出为不同基模型的融合权重，以加权和方式得到最终预测。融合器在元训练阶段通过最小化融合预测与真实值的损失来学习，且训练过程与基模型训练解耦。
- **关键技术细节**：
  - **元特征提取器**（ℓ）：从输入时间序列提取24维元特征，涵盖四类：
    - 统计特征：均值、标准差、偏度、峰度等；
    - 时序特征：自相关、平稳性（ADF检验）、变化率等；
    - 频谱特征：主频、频谱熵、频谱偏度等；
    - 多变量特征：协方差、交叉相关性等。
  - **可学习融合器**（Ψ_Θ）：单层神经网络，输入为元特征向量 x*_in ∈ ℝ²⁴，输出为k个基模型的权重向量 w ∈ ℝᵏ，经softmax归一化。最终预测为 ˆX_fuse = Σᵢ wᵢ fᵢ(X_in)。
  - **训练目标**：使用Huber损失，最小化加权融合预测与真实值的误差：
    ```
    arg min_Θ E_{(x*_in, ˆX_out, X_out)~D*} L(Ψ(x*_in; Θ)ᵀ · ˆX_out, X_out)
    ```
  - **跨任务元训练**：因元特征与任务无关，可将多个数据集的元训练数据混合，解决维度不一致和样本不平衡问题：对每个数据集过采样至最大规模，然后在训练中交替批次来自不同任务的数据。
- **算法流程**（Algorithm 1）：
  1. 对每个训练样本，提取元特征、收集所有基模型的预测张量、地面真值，组成元训练样本；
  2. 使用元训练数据集训练融合器，更新参数Θ直至收敛；
  3. 返回训练好的融合器，用于测试时动态融合。

### 3. 实验设计

- **数据集**：
  - **长期预测**：7个基准（ETTh1, ETTh2, ETTm1, ETTm2, Weather, Electricity, Traffic），预测长度 {96,192,336,720}，输入长度96。
  - **短期预测**：
    - PEMS数据集：4个交通流数据集（PEMS03/04/07/08），预测长度 {6,12,24}；
    - EPF数据集：5个电力市场数据集（NP, PJM, BE, FR, DE），预测长度24，输入长度168。
- **对比方法**（共13个基模型 + 多种集成方法）：
  - **基模型**：TimeXer (2024), TimeMixer (2024), PAttn (2024), iTransformer (2024), TimesNet (2023), PatchTST (2023), DLinear (2023), FreTS (2023), FEDformer (2022), Non-stationary Transformer (2022), LightTS (2022), Informer (2021), Autoformer (2021)。
  - **集成基线**：均值/中位数集成（含Top-K选择）、前向选择、组合选择、零样本集成、AutoGluon-TimeSeries（AutoML）、Chronos-Bolt（预训练基础模型）。
- **评价指标**：MSE, MAE（长期/EPF）；MAE, RMSE, MAPE（PEMS）。
- **实验设置**：基模型使用TSLib实现，采用官方最优超参数；融合器在验证集上训练（与基模型训练集分离），测试集报告结果。

### 4. 资源与算力

- **文中明确说明**：所有实验使用**单个NVIDIA A100 80GB GPU**（见附录A.3）。
- 基模型训练：10个epoch，早停patience=3，Adam优化器，L2损失。
- 融合器训练：batch size=32，学习率1e-3，Adam优化器，Huber损失。
- 未报告总训练耗时，但Appendix表8给出了每个基模型及融合器的**批推理时间**（batch size=32），显示融合器非常轻量（约2-7ms vs 基模型约1-1034ms）。

### 5. 实验数量与充分性

- **实验数量多、覆盖广**：
  - 主实验：7个长期数据集 × 4个预测长度 × 13基模型 + TimeFuse（表2）；4个PEMS × 3长度（表3）；5个EPF × 1长度（表4）。
  - 与静态集成的对比：7个数据集 × 不同Top-K（图3）。
  - 模型多样性影响：逐步增加模型数量测试性能变化（图5）。
  - 零样本泛化：7个长期数据集 + 4个PEMS，每次留一个目标数据集，其余用于训练（表5）。
  - 元特征消融：移除各类特征，对比完整特征与TSFEL（表6）。
  - 权重可视化：展示不同数据集上的平均权重及与元特征的关系（图4,6）。
  - 附录额外实验：更长输入长度（336/512，表9）、与AutoML/Chronos深入对比（表10）、完整实验结果表11-12。
- **充分性评价**：实验设计充分，覆盖了不同任务类型、不同预测步长、多种集成策略和消融分析，结果具有统计说服力。对比方法为当前最先进模型，且使用官方配置确保公平。结论稳健。

### 6. 论文的主要结论与发现

- **TimeFuse在所有任务上一致优于最佳单一基模型**：在长期预测上，平均MSE/MAE优于最佳基模型（如TimeXer）3.61%；在短期预测上（PEMS），MAPE降低20%以上。
- **自适应融合优于静态集成**：与均值/中位数集成（含Top-K过滤）相比，TimeFuse始终更优。
- **模型多样性带来持续增益**：随着模型池中模型数量增多（从2个到13个），TimeFuse性能持续提升。
- **零样本泛化能力强**：在未参与元训练的数据集上，TimeFuse仍接近甚至超过最佳单一模型（表5）。
- **融合权重可解释**：通过可视化发现，融合器学习到与输入特征（如平稳性、频谱复杂性）相对应的权重分配，例如低平稳性样本给非平稳Transformer更高权重。

### 7. 优点

- **创新性**：首次提出样本级自适应融合框架用于时间序列，突破单一模型瓶颈。
- **通用性**：元特征的设计使框架可跨任务、跨模型、跨数据集使用，无需对每个任务单独训练融合器。
- **轻量高效**：融合器仅为一层神经网络，计算开销极低（毫秒级），适合在线应用。
- **可解释性**：可通过权重分析理解不同模型的适用场景，为模型选择提供洞察。
- **实验扎实**：涵盖16个数据集、13个基模型、多种集成策略和消融，结果全面且复现性强（代码开源）。

### 8. 不足与局限

- **依赖元特征的质量**：元特征的设计虽然经过消融验证，但面对极复杂或低频的时序模式可能不够充分。
- **分布偏移风险**：融合器在验证集上训练，若测试集分布与验证集差异较大，性能可能下降（论文中提及但未深入探讨）。
- **简单线性融合器的表达能力**：作者指出单层网络已足够，但某些情况下可能需要更复杂的非线性融合（如多层MLP或注意力），可能提升但降低可解释性。
- **任务样本不平衡**：采用简单过采样平衡任务，未探索更高级的课程学习或自适应采样策略。
- **缺少空间/图结构利用**：论文未考虑传感器网络等应用中的空间相关性，可能限制在交通、能源等场景的进一步优化。
- **存储和计算成本**：需要预先存储所有基模型的预测结果，当模型池很大时（如13个），存储和I/O开销显著；但融合阶段本身极快。
- **零样本性能仍低于正常训练**：虽然具有泛化性，但零样本场景下仍与正常训练存在差距（表5），在关键任务中可能不够可靠。

（完）
