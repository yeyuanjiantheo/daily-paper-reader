---
title: Relational Conformal Prediction for Correlated Time Series
title_zh: 相关时间序列的关系共形预测
authors: "Andrea Cini, Alexander Jenkins, Danilo Mandic, Cesare Alippi, Filippo Maria Bianchi"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=wwYDQ1vXcZ"
tags: ["query:qf"]
score: 7.0
evidence: 基于分位数回归的时间序列不确定性量化
tldr: 针对相关时间序列预测中的不确定性量化问题，提出基于共形预测和分位数回归的分布无关方法，利用相关性结构提供有效预测区间，比独立方法更精确。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-wwydq1vxcz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1768, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wwydq1vxcz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1374, \"height\": 712, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-wwydq1vxcz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1415, \"height\": 1388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-wwydq1vxcz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 872, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-wwydq1vxcz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1730, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-wwydq1vxcz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1467, \"height\": 702, \"label\": \"Table\"}]"
motivation: 现有共形预测方法未利用时间序列间的相关性。
method: 结合图表示学习和分位数回归，在共形预测框架下构造预测区间。
result: 在相关时间序列上获得更窄且有效的预测区间。
conclusion: 利用关系结构可提升共形预测的精度。
---

## Abstract
We address the problem of uncertainty quantification in time series forecasting by exploiting observations at correlated sequences. Relational deep learning methods leveraging graph representations are among the most effective tools for obtaining point estimates from spatiotemporal data and correlated time series. However, the problem of exploiting relational structures to estimate the uncertainty of such predictions has been largely overlooked in the same context. To this end, we propose a novel distribution-free approach based on the conformal prediction framework and quantile regression. Despite the recent applications of conformal prediction to sequential data, existing methods operate independently on each target time series and do not account for relationships among them when constructing the prediction interval. We fill this void by introducing a novel conformal prediction method based on graph deep learning operators. Our approach, named Conformal Relational Prediction (CoRel), does not require the relational structure (graph) to be known a priori and can be applied on top of any pre-trained predictor. Additionally, CoRel includes an adaptive component to handle non-exchangeable data and changes in the input time series. Our approach provides accurate coverage and achieves state-of-the-art uncertainty quantification in relevant benchmarks.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）
- **问题**：时间序列预测中，现有共形预测（Conformal Prediction, CP）方法仅独立处理每条时间序列，忽略了不同序列之间可能存在的相关性（如空间依赖、Granger因果关系），导致预测区间（Prediction Interval, PI）不够精确或覆盖不足。
- **背景**：图深度学习（Graph Deep Learning, GDL）已有效用于时空数据点估计，但尚未被应用于基于共形预测的不确定性量化。同时，时间序列常面临非平稳性和非可交换性，现有CP方法难以直接适用。
- **动机**：旨在利用跨序列的相关结构（图）改进预测区间构建，实现分布无关、后验（post-hoc）的不确定性量化，且无需预知图结构。

### 2. 方法论：核心思想、关键技术细节
- **核心思想**：将共形预测与分位数回归结合，通过图神经网络（STGNN）学习残差分布的分位数函数，将相邻序列的近期残差作为条件，动态估计每个时间序列每个时间步的预测区间。
- **关键技术细节**：
  - **关系分位数预测器（Relational Quantile Predictor, RelQP）**：
    - 使用混合全局-局部架构：全局共享参数（编码器、STGNN、解码器），局部使用可学习的节点嵌入（node embeddings）\( \mathbf{v}_i \) 适应每个序列。
    - 处理流程：编码层 \( \mathbf{h}_{i,t}^0 = \text{ENC}(\mathbf{r}_{i,t-1}, \mathbf{v}_i) \) → STGNN \( \mathbf{Z}_t = \text{STGNN}(\mathbf{H}_{\le t}^0, \mathbf{A}) \) → 分位数解码器 \( \hat{q}_{i,t}^{(\alpha)} = \text{QDec}(\alpha, \mathbf{z}_{i,t}, \mathbf{v}_i) \)。
    - 训练时最小化分位数损失（pinball loss），以残差为输入，输出指定置信水平的分位数。
  - **图结构学习**：
    - 假设结构稀疏，通过可学习参数矩阵 \( \Phi \) 采样 K-NN 图（使用GumbelTopK及直通梯度估计器），端到端训练学习邻接矩阵 \( \mathbf{A} \)。
  - **预测区间构建**：
    - 基础形式：\( \hat{C}_{i,t}^\alpha = [\hat{x}_{i,t+H} + \hat{q}_{i,t}^{(\alpha/2)}, \hat{x}_{i,t+H} + \hat{q}_{i,t}^{(1-\alpha/2)}] \)
    - 可选优化：搜索偏移量 \( \beta \) 使区间更窄（Eq. 16）。
  - **自适应组件**：
    - 为应对分布漂移，每隔 \( M \) 步仅微调节点嵌入 \( \mathbf{V} \)，冻结全局参数，提升计算效率。
- **理论支撑**：Proposition 3.1 借助全变差距离给出覆盖保证，表明覆盖误差受限于学习分位数函数与真实分布的近似误差。

### 3. 实验设计
- **数据集**：
  - **真实数据**：METR-LA（交通速度，207传感器，5分钟间隔），AQI（空气质量PM2.5，437站点，小时级），CER-E（电力负荷，485用户，30分钟间隔）。
  - **合成数据**：GPVAR（扩散过程图，60节点，控制参数已知）。
- **基准（Benchmark）与对比方法**：
  - 基础点预测器（Base predictors）：RNN（GRU）、Transformer、STGNN（使用预定义图）。
  - 对比的CP方法：标准SCP、SeqCP（滑动窗口）、NexCP（指数衰减权重）、SPCI（分位数随机森林）、HopCPT（现代Hopfield网络重加权）。
  - 消融：CORNN（CoRel去掉消息传递和节点嵌入）。
- **评估指标**：覆盖差（ΔCov）、预测区间宽度（PI‑Width）、Winkler分数（平衡宽度与惩罚）。

### 4. 资源与算力
- **硬件平台**：AMD EPYC 7513 CPU，NVIDIA RTX A5000 GPU。
- **典型训练时长（METR-LA）**：
  - SPCI：约3天
  - HopCPT：约11小时
  - CoRel：约5分钟
- **说明**：论文明确给出了部分对比耗时，但未统计所有实验的总GPU小时数。整体算力需求合理，CoRel高效。

### 5. 实验数量与充分性
- **实验组数**：
  - 3个真实数据集 × 3种点预测器 = 9组主要实验（表1）。
  - 1个合成数据集实验（表2）验证图学习能力。
  - 自适应实验（表3）在CER-E上进行，模拟6折迭代微调。
  - 额外消融：PI宽度优化（表4），图可视化（图2）。
- **充分性**：实验覆盖多种场景（交通、空气质量、电力、合成），对比了5种主流CP方法，并包含自身消融、超参调优、理论验证。实验设计较充分，公平性良好（基预测器与CP方法均独立训练）。
- **局限**：未在超大规模节点（如>1000）上测试，未与深度贝叶斯方法（如DeepAR）直接比较（因属于非后验方法）。

### 6. 主要结论与发现
- **CoRel在大多情况下Winkler分数最优**，预测区间更窄且覆盖接近目标水平。
- **图结构有效**：在GPVAR实验中，CoRel（无论是否使用真实图）几乎达到理论最优区间宽度（1.32 vs 理论1.315），而CORNN需更宽区间。
- **自适应组件改善覆盖**：在CER-E上，微调嵌入后覆盖差降低约0.7-1.0个百分点。
- **无需预知图**：端到端图学习模块可自动捕获相关结构，性能接近使用真实图。

### 7. 优点
- **方法创新**：首次将图深度学习引入时间序列共形预测，利用跨序列相关性提升区间质量。
- **实用性强**：后验方法，可应用于任何预训练点预测器；无需预知图结构；包含自适应机制应对分布漂移。
- **计算高效**：训练快（5分钟 vs 数天），推理可并行；共享参数降低样本复杂度。
- **理论支撑**：提供了覆盖误差的理论界（Proposition 3.1）。

### 8. 不足与局限
- **覆盖保证有限**：CoRel仅提供近似覆盖，不保证精确边际覆盖（尤其当分位数函数近似误差较大时）。
- **对STGNN基预测器优势不明显**：当基模型已充分建模时空依赖时（如表1 STGNN行），CoRel提升有限。
- **稀疏性假设**：图学习模块假设依赖稀疏，不适用于稠密连接场景（论文提到可改用伯努利分布，但未实验）。
- **非平稳适应能力有限**：自适应仅更新节点嵌入，无法适应全局分布突变；理论分析未给出动态覆盖界。
- **未建模联合分布**：仅为每个序列提供独立区间，未考虑多序列联合不确定性。
- **实验覆盖不足**：未测试异质序列（如不同物理量）、大规模节点（>2000）场景，也未与深度概率预测方法（如DeepAR）对比。

（完）
