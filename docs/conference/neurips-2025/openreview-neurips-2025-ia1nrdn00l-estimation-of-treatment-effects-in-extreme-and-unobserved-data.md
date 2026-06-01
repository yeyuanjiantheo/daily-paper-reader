---
title: Estimation of Treatment Effects in Extreme and Unobserved Data
title_zh: 极端与未观测数据中的处理效应估计
authors: "Jiyuan Tan, Vasilis Syrgkanis, Jose Blanchet"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Ia1nRDN00L"
tags: ["query:qf"]
score: 8.0
evidence: 极值理论用于罕见事件的处理效应估计
tldr: 标准因果推断主要关注频繁事件，对于极端事件的处理效应估计缺乏方法。本文引入极值理论（EVT），在极端数据下估计因果效应。该方法直接适用于金融尾部风险管理（如VaR、ES），为极值理论在金融风险中的新应用提供了理论基础。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ia1nrdn00l/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1160, \"height\": 925, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ia1nrdn00l/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1165, \"height\": 931, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ia1nrdn00l/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 629, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ia1nrdn00l/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1162, \"height\": 925, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ia1nrdn00l/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1166, \"height\": 929, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ia1nrdn00l/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1206, \"height\": 265, \"label\": \"Table\"}]"
motivation: 现有因果推断方法无法处理极端罕见事件的处理效应估计。
method: 引入极值理论对极端数据进行建模，提出新颖的因果效应估计框架。
result: 在合成和真实数据上验证了方法的有效性，能准确估计极端事件下的因果效应。
conclusion: 极值理论是解决极端数据因果推断问题的有力工具。
---

## Abstract
Causal effect estimation seeks to determine the impact of an intervention from observational data. However, the existing causal inference literature primarily addresses treatment effects on frequently occurring events. But what if we are interested in estimating the effects of a policy intervention whose benefits, while potentially important, can only be observed and measured in rare yet impactful events, such as extreme climate events? The standard causal inference methodology is not designed for this type of inference since the events of interest may be scarce in the observed data and some degree of extrapolation is necessary. Extreme Value Theory (EVT) provides methodologies for analyzing statistical phenomena in such extreme regimes. We introduce a novel framework for assessing treatment effects in extreme data to capture the causal effect at the occurrence of rare events of interest. In particular, we employ the theory of multivariate regular variation to model extremities. We develop a consistent estimator for extreme treatment effects and present a rigorous non-asymptotic analysis of its performance. We illustrate the performance of our estimator using both synthetic and semi-synthetic data.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

标准因果推断方法主要关注频繁发生的事件（如平均处理效应ATE），但许多关键政策干预（如防灾基建、药物）的效果只在罕见但影响巨大的事件（如特大洪水、地震）中才能体现。由于极端事件在观测数据中极其稀少，直接应用经典因果推断会导致统计误差过大，且缺乏对尾部行为的建模。本文首次将极值理论（Extreme Value Theory, EVT）与因果推断结合，提出一套在极端数据下估计处理效应的框架，旨在回答“干预如何改变罕见事件下的平均结果”。这一工作填补了因果推断在尾部风险分析中的空白，对金融风险管理、气候政策等有重要应用价值。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：利用多变量正则变化（multivariate regular variation）对极端事件建模，定义一个新的因果估计量——**标准化极端处理效应（Normalized Extreme Treatment Effect, NETE）**，量化干预在尾部区域对结果的尺度影响。
- **关键公式**：  
  \[
  \theta_{\text{NETE}} = \lim_{t \to \infty} \mathbb{E}\left[ \frac{Y(1)-Y(0)}{t^\alpha} \mid \|U\| > t \right]
  \]  
  其中 \(U\) 是极端协变量（如风速、降雨量），\(\alpha\) 为已知多项式增长指数，\(t\) 为阈值。该量通过极值理论中的谱–模分解可拆分为两项的乘积：谱期望（方向效应）与模条件矩（尺度效应）。
- **估计算法（Algorithm 1）**：
  1. 数据等分：一半用于估计倾向得分和伪结果回归（调整后的 \(Y/\|U\|^{\hat\alpha}\)）；
  2. 倾向得分：假设 \(U\) 与 \(D,X\) 独立，用逻辑回归估计 \(p(X)\)；
  3. 伪结果：用随机森林或类似方法回归 \(Y/\|U\|^{\hat\alpha} \sim (X,D,U/\|U\|)\)；
  4. 在另一半数据上，对 \(\|U\|>t\) 的样本计算两种估计量：
     - **IPW 估计量**：\(\hat\eta_{n,t}^{\text{IPW}} = \frac{1}{|I|} \sum_{i\in I} S_i \left( \frac{D_i}{\hat p(X_i)} - \frac{1-D_i}{1-\hat p(X_i)} \right)\)；
     - **双稳健（DR）估计量**：在 IPW 基础上加入结果模型残差校正；
  5. 用自适应 Hill 估计量估计极值指数 \(\gamma\)，进而得到 \(\hat\mu_n = 1/(1-\alpha\hat\gamma)\)；
  6. 最终估计 \(\hat\theta_{n,t} = \hat\eta_{n,t} \cdot \hat\mu_n\)。
- **非渐近理论**：在 Pareto 类尾部分布下，给出 DR 和 IPW 估计量的有限样本误差界（Theorem 3.8），并建议数据驱动的阈值选择规则以平衡偏差与方差（Corollary 3.9）。

### 3. 实验设计：数据集、场景、基准方法与对比方法

- **合成数据集**：
  - 数据生成：协变量 \(X\sim \text{Unif}([0,1]^5)\)，倾向得分 \(p(x)=1/(1+e^{-x^T b})\)，结果 \(Y = \|U\|^\alpha (D + U/\|U\| + \epsilon)\)。极端变量 \(U\) 有两种生成方式：
    - **线性变换 Pareto**：\(U=AZ\)，\(Z_i\sim \text{Pareto}(\beta)\)，满足 Assumption 3.7；
    - **Pareto 混合**：\(U_i\sim 0.5\text{Pareto}(\beta)+0.5\text{Pareto}(\beta+1)\)，违反严格假设。
  - 参数配置：\(\alpha,\beta,d_z,d_u\) 多种组合（图1、图2）。
  - 基准方法：Naive-IPW、Naive-DR，即不利用极值结构，仅对 \(\|U\|>t\) 的子样本直接应用标准 IPW/DR。
  - 评价指标：均方误差（MSE），重复 50 次取平均。
- **半合成数据集**：
  - 使用 **wavesurge 数据集**（英格兰西南部波浪与风暴潮观测，2894 个样本），经平移与归一化后生成结果：\(Y = (1-X+D)W^{\alpha_1} S^{\alpha_2} + N(0,1)\)。
  - 训练集 1000 样本，测试集 1894 样本；测试集上的高保真估计（利用全量数据与正确尾部模型）作为近似“真值”。
  - 对比方法同合成实验：EVT-IPW、EVT-DR vs. Naive-IPW、Naive-DR。
  - 表1列出 \((\alpha_1,\alpha_2)\) 四种配置下的估计值。

### 4. 资源与算力

论文未提供任何有关 GPU 型号、数量、训练时长的信息。实验均在个人笔记本上可复现（文中提及“All experiments can be easily reproduced using a laptop”），未提及大规模算力使用。

### 5. 实验数量与充分性

- **合成实验**：图1展示了 4 种配置（线性 Pareto），图2展示了 4 种配置（Pareto 混合），共 8 组实验，每组重复 50 次并报告 MSE。覆盖了不同维度和尾部指数。
- **半合成实验**：表1展示了 4 种 \((\alpha_1,\alpha_2)\) 组合下的估计值。
- **消融分析**：附录 B.2 补充了使用真实 α 与估计 α 的对比实验，证明启发式 α 估计有效。
- 实验设计较为全面：覆盖了假设满足和违反情形，对比了两种基线方法，且提供了统计误差条（图1、图2 中为 MSE）。结论具有统计稳定性。但缺乏对更大规模数据集或更多现实应用的验证，也没有进行超参数敏感性分析。

综合来看，实验充分性可接受，客观且公平（基线为朴素方法）。

### 6. 论文的主要结论与发现

- 提出的 EVT-DR 和 EVT-IPW 估计量在大多数合成与半合成场景下 MSE 明显低于朴素基线，尤其当样本量增大时优势更显著。
- 即使在 Pareto 混合（违反严格假设）的情况下，EVT 估计量仍保持合理性能，但某些配置下 MSE 随样本量增加反而增大（可能是阈值选择规则不适用导致方差主导）。
- 在半合成实验中，朴素估计量严重高估真实 NETE（数量级差异），而 EVT 方法估计值与测试集近似真值接近（偏差不超过 0.3）。
- 理论非渐近误差界（Theorem 3.8）与实验趋势一致，验证了方法在有限样本下的有效性。

### 7. 优点

- **方法创新性**：首次系统地将多变量极值理论与因果推断结合，提出 NETE 这一新估计量，填补了极端事件因果效应估计的空白。
- **理论严谨**：提供了非渐近误差界（Theorem 3.8）和数据驱动阈值选择指南（Corollary 3.9），理论层次完整。
- **双重稳健性**：DR 估计量在倾向得分或结果模型之一准确时仍可一致估计，增强了实用性。
- **实验涵盖面广**：包括合成（线性 Pareto 和更一般的混合分布）与真实数据衍生的半合成实验，验证了方法的鲁棒性。

### 8. 不足与局限

- **强假设**：Assumption 3.4（\(U\perp X,D\)）在现实中未必成立，且文中承认当该假设不成立时，倾向得分法不可用，但 DR 仍可工作。未提供放宽该假设的实证或理论拓展。
- **参数 α 依赖先验知识**：α 需已知或事先估计，文中的启发式线性回归方法缺乏理论保证，也未提供 α 的推断误差界。
- **极值结构假设严格**：理论非渐近分析依赖 Assumption 3.7（Pareto 类线性变换），虽然可通过更一般条件替代（Remark 3.11），但后者未理论展开，实际适用范围可能受限。
- **基准方法过弱**：仅对比了不利用极值信息的朴素方法，未与其他可能结合极值信息的替代方法（如分位数处理效应 QTE 的极端版本）比较。
- **应用验证有限**：仅用一个半合成案例（wavesurge），缺少真实世界灾难风险管理或金融尾部风险的应用案例。实验样本量不大（最大约 1000 训练样本），未展示在大规模高维数据上的表现。

（完）
