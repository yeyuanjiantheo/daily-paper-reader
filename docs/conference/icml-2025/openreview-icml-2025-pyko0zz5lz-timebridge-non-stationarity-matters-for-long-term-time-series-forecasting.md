---
title: "TimeBridge: Non-Stationarity Matters for Long-term Time Series Forecasting"
title_zh: TimeBridge：非平稳性对长期时间序列预测至关重要
authors: "Peiyuan Liu, Beiliang Wu, Yifan Hu, Naiqi Li, Tao Dai, Jigang Bao, Shu-Tao Xia"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=pyKO0ZZ5lz"
tags: ["query:qf"]
score: 6.0
evidence: 解决长期时间序列预测中的非平稳性问题
tldr: 长期时间序列预测中非平稳性带来挑战。TimeBridge框架区分短期和长期建模需求，分别消除或保留非平稳性，避免伪回归并揭示协整关系。实验证明其在长期预测任务上的有效性，可应用于金融资产价格预测。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-pyko0zz5lz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 844, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pyko0zz5lz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pyko0zz5lz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1749, \"height\": 752, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pyko0zz5lz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1742, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pyko0zz5lz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1754, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pyko0zz5lz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1775, \"height\": 801, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pyko0zz5lz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1673, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pyko0zz5lz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1665, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pyko0zz5lz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1675, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pyko0zz5lz/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1766, \"height\": 781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pyko0zz5lz/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1769, \"height\": 776, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pyko0zz5lz/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1772, \"height\": 774, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pyko0zz5lz/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1686, \"height\": 808, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pyko0zz5lz/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1695, \"height\": 773, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1740, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1673, \"height\": 461, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1682, \"height\": 446, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 854, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 853, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1762, \"height\": 1141, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1775, \"height\": 602, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1766, \"height\": 1897, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1765, \"height\": 753, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1764, \"height\": 1192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1763, \"height\": 924, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1763, \"height\": 927, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1763, \"height\": 1246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1763, \"height\": 661, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1765, \"height\": 626, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1770, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pyko0zz5lz/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1773, \"height\": 226, \"label\": \"Table\"}]"
motivation: 现有方法未区分非平稳性在短期和长期建模中的不同影响。
method: 分别处理短期和长期，消除短期非平稳性而保留长期趋势。
result: 在长期预测数据集上达到最优性能。
conclusion: 合适应对非平稳性可提升长期预测精度。
---

## Abstract
Non-stationarity poses significant challenges for multivariate time series forecasting due to the inherent short-term fluctuations and long-term trends that can lead to spurious regressions or obscure essential long-term relationships. Most existing methods either eliminate or retain non-stationarity without adequately addressing its distinct impacts on short-term and long-term modeling. Eliminating non-stationarity is essential for avoiding spurious regressions and capturing local dependencies in short-term modeling, while preserving it is crucial for revealing long-term cointegration across variates. In this paper, we propose TimeBridge, a novel framework designed to bridge the gap between non-stationarity and dependency modeling in long-term time series forecasting. By segmenting input series into smaller patches, TimeBridge applies Integrated Attention to mitigate short-term non-stationarity and capture stable dependencies within each variate, while Cointegrated Attention preserves non-stationarity to model long-term cointegration across variates. Extensive experiments show that TimeBridge consistently achieves state-of-the-art performance in both short-term and long-term forecasting. Additionally, TimeBridge demonstrates exceptional performance in financial forecasting on the CSI 500 and S&P 500 indices, further validating its robustness and effectiveness. Code is available at https://github.com/Hank0626/TimeBridge.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：多变量时间序列预测中，非平稳性（non-stationarity）会导致短期建模中的**伪回归**（spurious regression），同时可能掩盖变量间长期的**协整关系**（cointegration）。现有方法要么彻底消除非平稳性、要么完全保留，未能区分其在不同时间尺度上的差异化影响。
- **研究动机**：消除非平稳性有助于避免短期噪声带来的虚假关联，但会丢失长期趋势中蕴藏的跨变量均衡信息；保留非平稳性则有助于揭示长期协整，却容易在短期建模中引入伪回归。因此，需要**针对性地分别处理短期和长期的非平稳性**。
- **整体含义**：本文提出的时间桥（TimeBridge）框架通过“集成注意力”（Integrated Attention）消除短期非平稳性以捕捉局部依赖，通过“协整注意力”（Cointegrated Attention）保留非平稳性以建模长期协整关系，从而在长期预测中取得更优效果。

### 2. 论文提出的方法论

#### 核心思想
将输入序列划分为多个**补丁（patches）**，分别对短期（变体内部）和长期（变体之间）的非平稳性进行差异化处理：  
- **短期建模**：消除非平稳性，避免伪回归，聚焦于单变量内部的时间依赖。  
- **长期建模**：保留非平稳性，利用协整关系捕捉跨变体的长期均衡。

#### 关键技术与流程
1. **补丁嵌入（Patch Embedding）**  
   - 将每个变量的输入序列分割成非重叠的补丁（长度 S），并通过线性层映射为隐藏维度 D 的标记。
2. **集成注意力（Integrated Attention）**  
   - 对每个变量内的所有补丁进行**补丁级归一化**（减去移动平均趋势），得到去趋势的补丁序列。  
   - 使用去趋势后的序列作为 Query 和 Key，原始序列作为 Value 计算注意力，从而获得**平稳的注意力图**，消除短期非平稳性带来的伪相关。  
   - 公式：`P' = pi - AvgPool(Padding(pi))`，注意力输出经 LayerNorm 和 MLP 后更新表示。
3. **补丁下采样（Patch Downsampling）**  
   - 通过 MLP 将补丁数量从 N 减少到 M（M < N），并用注意力机制聚合全局信息，使每个补丁包含更丰富的长期特征。
4. **协整注意力（Cointegrated Attention）**  
   - 对下采样后同一时间位置的所有变量补丁（形状 C × M × D）直接执行标准自注意力，**保留非平稳性**，从而捕捉跨变量的长期协整关系。  
   - 注意力权重反映协整强度。
5. **输出投影**：将最终补丁表示重整并线性投影到预测长度 O，得到输出 Y ∈ R^{C×O}。

### 3. 实验设计

#### 数据集与场景
- **长期预测**（预测长度 ∈ {96, 192, 336, 720}）：  
  ETT（ETTh1, ETTh2, ETTm1, ETTm2）、Weather、Electricity、Traffic、Solar。
- **短期预测**（输入 96 步，输出 12 步）：  
  PeMS03、PeMS04、PeMS07、PeMS08。
- **金融预测**（预测次日收益，构建投资组合）：  
  CSI 500（中国股市502支股票）和 S&P 500（美国股市487支股票）。

#### 对比的基准方法（Baselines）
- **长期预测**：DeformableTST、ModernTCN、TimeMixer、iTransformer、PatchTST、Crossformer、Leddam、MICN、TimesNet、DLinear。
- **短期预测**：额外增加 SCINet、DUET（以及较差的 Autoformer、Informer）。
- **金融预测**：增加传统动量/反转策略（CSM、BLSW）、LSTM、Transformer、ALSTM、GRU、TRA、TSMixer 等。

#### 评价指标
- 长期：MSE、MAE（均值）。
- 短期：MAE、MAPE、RMSE。
- 金融：年化收益率（ARR）、年化波动率（AVol）、最大回撤（MDD）、夏普比率（ASR）、卡玛比率（CR）、信息比率（IR）。

### 4. 资源与算力

- **硬件**：2 块 NVIDIA RTX 3090（24 GB 显存）。
- **框架与优化器**：PyTorch，Adam 优化器。
- **训练轮数**：100 个 epoch。
- **数据与细节**：论文未给出单次训练时长或总 GPU 小时数，但指出输入长度 I 在不同任务上有不同设置（长期 720，短期 96 等），超参数通过搜索确定。

### 5. 实验数量与充分性

- **实验组数丰富**：
  - 长期预测在 8 个数据集上各 4 个预测长度，共 32 组结果（表 1，完整表 9）。
  - 短期预测在 4 个 PeMS 子集上共 4 组结果（表 2）。
  - 金融预测在 2 个指数上各 6 个指标（表 3，完整表 10）。
  - 消融实验 3 组（表 4-6）分别探讨：非平稳性保留/去除、注意力顺序、通道独立/依赖模式。
  - 下采样补丁数量 M 的敏感性分析（表 14）。
  - 损失函数对比（表 15）。
  - 统计显著性检验与标准差（表 16-18）。
- **充分性与公平性**：
  - 对比了大量最新方法，并按惯例使用超参数搜索（输入长度、学习率等）。
  - 消融实验控制了关键变量，结论清晰。
  - 金融任务还加入了传统的非深度学习策略。
- **局限性**：未包含更多非平稳类型（如突变、季节性偏移）的专项测试；部分数据集（如 ETT）通道数少，协整信号弱，模型在该任务上的优势不如通道数多的数据集明显。

### 6. 论文的主要结论与发现

1. **非平稳性具有双重影响**：短期应消除（避免伪回归），长期应保留（捕捉协整）。
2. **TimeBridge 在多个场景下达到 SOTA**：在 8 个长期预测数据集上平均 MSE/MAE 优于所有对比方法；在 PeMS 短期预测和 CSI 500/S&P 500 金融预测中也表现最佳。
3. **注意力图的可视化验证**：消除非平稳性后，短期注意力集中在相邻时间步；保留非平稳性后，跨变量注意力覆盖更广、更丰富，反映出协整关系。
4. **消融实验证实设计有效性**：只有按照“短期消除、长期保留”的顺序才能获得最优性能；通道独立（CI）更适合短期建模，通道依赖（CD）更适合长期建模（尤其是大通道数数据集）。

### 7. 优点

- **理论创新**：首次明确区分非平稳性在短期和长期建模中的不同角色，并提出针对性解决方案，具有清晰的动机和理论支撑（附录 B 给出布朗运动推导）。
- **方法设计简洁有效**：通过补丁归一化和注意力机制分离地处理两种时间尺度的依赖，无需复杂的状态空间模型。
- **实验全面且规范**：覆盖多个领域、多种预测长度、进行超参数搜索与统计显著性检验，消融实验完整，结果可信。
- **金融应用验证**：在真实股市数据上对比多种策略，展现了实际价值。

### 8. 不足与局限

- **超参数敏感性**：补丁大小 S、下采样后补丁数 M 对性能有影响，需要针对数据集手动调整（表 8），缺乏自动化方案。
- **计算成本**：使用两块 3090 训练 100 epoch，对于大型数据集（如 Traffic 862 通道）仍未给出详细的运行时间或显存占用，效率分析不足。
- **泛化范围有限**：实验集中在公开的电力、天气、交通等场景，未涉及高频金融、医学信号或极端非平稳（如金融危机）情况。
- **理论深度有限**：虽用布朗运动进行了直观解释，但未给出严格的收敛性保证或对非平稳性类型的全面分类。
- **潜在偏差风险**：金融实验仅覆盖美股和 A 股两个市场，且数据时段较短（2018-2023），可能存在市场特异性。
- **对比方法选择**：部分早期方法（如 DLinear、TimesNet）被明显超越，但对近期的状态空间模型（如 Mamba、S4）未作对比，影响力稍弱。

（完）
