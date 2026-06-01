---
title: "QuEst: Enhancing Estimates of Quantile-Based Distributional Measures Using Model Predictions"
title_zh: QuEst：利用模型预测增强分位数基分布度量的估计
authors: "Zhun Deng, Thomas P Zollo, Benjamin Eyre, Amogh Inamdar, David Madras, Richard Zemel"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=JwZVPTTEwO"
tags: ["query:qf"]
score: 9.0
evidence: 基于分位数度量的尾部风险CVaR估计
tldr: 针对现有混合推理工具只能估计均值或单个分位数的局限，提出QuEst框架，融合少量高保真观测数据与大量模型预测数据，估计分位数基分布度量（如CVaR尾风险）的点估计和置信区间，提升尾部风险评估的可靠性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jwzvpttewo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 814, \"height\": 419, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jwzvpttewo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1751, \"height\": 689, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jwzvpttewo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 839, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jwzvpttewo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 837, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jwzvpttewo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 764, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jwzvpttewo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1752, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jwzvpttewo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1760, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jwzvpttewo/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1610, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jwzvpttewo/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1611, \"height\": 369, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jwzvpttewo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 898, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jwzvpttewo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 783, \"height\": 235, \"label\": \"Table\"}]"
motivation: 现有方法无法有效利用模型预测数据估计分位数基度量如CVaR。
method: 提出QuEst框架，通过合并观测和模型输出来估计分位数基分布度量的点估计和置信区间。
result: 在合成和真实数据上验证了估计的准确性和区间覆盖能力。
conclusion: QuEst为利用机器学习模型增强尾部风险估计提供了有效工具。
---

## Abstract
As machine learning models grow increasingly competent, their predictions can supplement scarce or expensive data in various important domains. In support of this paradigm, algorithms have emerged to combine a small amount of high-fidelity observed data with a much larger set of imputed model outputs to estimate some quantity of interest. Yet current hybrid-inference tools target only means or single quantiles, limiting their applicability for many critical domains and use cases. We present QuEst, a principled framework to merge observed and imputed data to deliver point estimates and rigorous confidence intervals for a wide family of quantile-based distributional measures. QuEst covers a range of measures, from tail risk (CVaR) to population segments such as quartiles, that are central to fields such as economics, sociology, education, medicine, and more. We extend QuEst to multidimensional metrics, and introduce an additional optimization technique to further reduce variance in this and other hybrid estimators. We demonstrate the utility of our framework through experiments in economic modeling, opinion polling, and language model auto-evaluation.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有混合推理方法（如预测驱动推断 PPI）只能利用少量高保真观测数据和大量模型预测数据来估计均值或单个分位数的统计量，无法估计更丰富的分位数基分布度量（QBDM），如条件风险价值（CVaR）、区间VaR、分位段等。这些度量在经济学、社会学、教育、医学、大语言模型安全等领域至关重要（例如分析财富分布尾部、评估LLM毒性输出）。
- **整体含义**：提出QuEst框架，通过融合观测数据与模型预测数据，为QBDM提供点估计和严格的置信区间，从而支持更细粒度的分布特征推断，提升在稀缺数据场景下的统计推断可靠性。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：利用L-统计量（order statistics）理论，将QBDM表示为加权分位数积分 \( Q_\psi(F) = \int_0^1 \psi(p) F^{-1}(p) dp \)，其中 \(\psi\) 为权重函数。结合观测数据（小样本）和模型预测数据（大样本），构造无偏估计量并通过方差最小化选择最优权重 \(\lambda\)。
- **关键技术细节**：
  - **基础估计量**：\(\hat{Q}_\psi(\lambda) = \lambda Q_\psi(\tilde{F}^u_N) + [Q_\psi(F_n) - \lambda Q_\psi(\tilde{F}_n)]\)，其中 \(F_n\) 为观测经验CDF，\(\tilde{F}_n\) 和 \(\tilde{F}^u_N\) 分别为有标签/无标签的预测CDF。\(\lambda\) 平衡对预测数据的依赖。
  - **方差公式与最优 \(\lambda\)**：通过L-统计量CLT推导出渐近方差 \(\rho^2_\psi(\lambda, F, \tilde{F})\)，并解析求解最小化方差的 \(\lambda^* = \eta_\psi(F,\tilde{F})/[(1+r)\sigma^2_\psi(\tilde{F})]\)，实践中用经验版本 \(\hat{\lambda}\) 替代。
  - **多维扩展**：对多个QBDM或多个指标同时估计，构建协方差矩阵实现联合置信域。
  - **优化扩展（QuEst-Opt）**：对预测部分使用参数化权重函数 \(\tilde{\psi}(\cdot)=\xi^T\phi(\cdot)\) 替代标量 \(\lambda\)，通过凸优化进一步降低方差。
- **算法流程**（文字说明）：
  1. 输入：观测数据 \((X_i,Y_i,\tilde{Y}_i)_{i=1}^n\)，无标签预测数据 \((X^u_j,\tilde{Y}^u_j)_{j=1}^N\)。
  2. 计算经验CDF \(F_n, \tilde{F}_n, \tilde{F}^u_N\)。
  3. 对目标QBDM权重 \(\psi\)，计算 \(\hat{\lambda}\) 或优化 \(\xi\)。
  4. 输出点估计 \(\hat{Q}_\psi(\hat{\lambda})\) 及 \((1-\alpha)\) 置信区间：\(\hat{Q}_\psi(\hat{\lambda}) \pm z_{1-\alpha/2} \cdot \hat{\text{SE}}\)。

### 3. 实验设计：使用了哪些数据集/场景，它的 benchmark 是什么，对比了哪些方法

- **数据集与场景**：
  - **PovertyMap**：卫星图像预测区域财富指数，目标估计中间三分之一家庭的Interval-VaR。
  - **GeneExpression**：基因表达水平预测，目标估计顶部20%基因的CVaR。
  - **OpinionQA**：LLM模拟人类意见（使用Llama-3.1-70B），目标估计中间50%人口的意见Interval-VaR。
  - **LLM红队毒性评估**：8个候选LLM对对抗性提示的响应，使用Llama-3.1-70B（昂贵）作为观测，Llama-3.1-8B（便宜）作为预测，目标估计最毒25%响应的CVaR。
  - **新闻摘要多指标评估**：XSum数据集，由Qwen2-7B生成摘要，用Llama-3.1-70B/8B分别对连贯性、相关性、一致性评分，目标估计底部20%在三个指标上的多维区间。
- **Benchmark与对比方法**：
  - 经典方法（仅使用观测数据，\(\lambda=0\)）。
  - 仅使用预测数据（imputed-only）。
  - 对单分位数（VaR）与原始PPI方法比较（论文指出QuEst允许自适应\(\lambda\)）。
- **评价指标**：绝对估计误差、置信区间宽度、经验覆盖概率、排序相关性（模型选择任务）、置信区域体积（多维）。

### 4. 资源与算力

- 论文中未明确报告使用的GPU型号、数量或训练时长。提到“所有使用Llama或其他开源模型的实验均在哥伦比亚大学运行”，但无具体算力消耗细节。

### 5. 实验数量与充分性

- **实验数量**：
  - 每个数据集（PovertyMap, GeneExpression, OpinionQA）进行2000次随机数据划分，改变观测样本数（100,200,500,1000）。
  - 毒性评估：对8个候选模型各进行1000次试验。
  - 新闻摘要多维评估：50次试验。
  - 扩展实验（QuEst-Opt）：合成数据100次试验，两个真实数据集各100次（推测）。
  - VaR对比实验（与PPI）：两个数据集，每个试验次数未明确但应类似。
- **充分性**：实验覆盖了多种量化指标（Interval-VaR, CVaR, VaR），多个领域（经济、基因组、社科、LLM评估），并包含单变量和多变量场景；重复次数高（2000/1000次），统计稳定性好；对比了多种基线，结果客观。但缺少对偏差、异常值影响的分析，且未与贝叶斯方法（如Bayesian PPI）比较。

### 6. 论文的主要结论与发现

- QuEst始终优于仅使用观测数据或仅使用预测数据的方法，尤其在观测样本极少时（如n=100），估计误差和置信区间宽度降低约50%。
- 随着观测样本增加，优势缩小但仍保持有效。
- 在毒性评估中，QuEst获得的模型排序与真实排序的秩相关性更高，有助于模型选择决策。
- 多维QuEst相比单变量独立估计或Bootstrap方法，置信区域体积显著缩小（如7%~34%）。
- QuEst-Opt扩展在具有异方差性的合成数据和复杂真实数据上进一步提升性能，尤其在超低样本场景下更突出。

### 7. 优点：方法或实验设计上有哪些亮点

- **方法创新**：首次将混合推理扩展到通用分位数基度量（包括CVaR、Interval-VaR等），基于L-统计量推导了严格CLT和最优\(\lambda\)选择闭式解。
- **实用性强**：无需用户调节超参数（\(\lambda\)自动优化），可直接产生有效置信区间。
- **多维扩展**：支持同时估计多个QBDM或多个指标，生成联合置信区域，避免多重比较膨胀。
- **额外的优化扩展**（QuEst-Opt）进一步降低方差，理论证明仍保持渐近正态性。
- **实验覆盖广泛**：涵盖多个实际应用领域，重复次数高，结果稳健，且对模型选择任务进行了验证。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **实验覆盖**：未包含非常复杂的高维场景（如协变量偏移下的估计），也未与更近期的混合推断方法（如贝叶斯PPI, Stratified PPI）进行直接比较。
- **偏差风险**：方法假设观测数据与预测数据同分布（\(\tilde{F}^u = \tilde{F}\)），若分布偏移较大，估计可能失效；论文未详细讨论假设违例的鲁棒性。
- **应用限制**：方法依赖L-统计量的正则性条件（密度存在且光滑等），对高度离散或厚尾分布可能不适用；实际中需要足够大的无标签预测池（N远大于n）。
- **资源报告缺失**：未说明计算成本，对于实际部署中的可行性难以评估。
- **消融实验有限**：仅对\(\lambda\)自适应做了基本验证，未深入分析不同权重函数\(\psi\)选择的影响。

（完）
