---
title: "Small Resamples, Sharp Guarantees: Convergence Rates for Resampled Studentized Quantile Estimators"
title_zh: 小样本重抽样，精确保证：重抽样学生化分位数估计的收敛速度
authors: "Imon Banerjee, Sayak Chakrabarty"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=VwjHVS4zZN"
tags: ["query:qf"]
score: 8.0
evidence: 重尾数据下重抽样分位数估计的理论保证
tldr: 重尾数据下分位数估计的Bootstra方法缺乏严格理论保证。本文分析了m-out-of-n自助法在样本分位数估计中的收敛速度，首次给出无参数假设的严格保证。该结果适用于经济计量和生物统计中的稳健推断，为尾部风险度量（如VaR）的可靠性提供了理论支撑。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vwjhvs4zzn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1056, \"height\": 442, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vwjhvs4zzn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1057, \"height\": 441, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vwjhvs4zzn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1057, \"height\": 443, \"label\": \"Table\"}]"
motivation: m-out-of-n自助法分位数估计缺乏严格的收敛速度保证。
method: 分析m-out-of-n自助法学生化分位数估计的收敛速度，给出参数无关界。
result: 建立了无参数假设下的收敛率，适用于重尾分布。
conclusion: 为基于自助法的尾部风险推断提供了理论基础。
---

## Abstract
The m-out-of-n bootstrap—proposed by \cite{bickel1992resampling}—approximates the distribution of a statistic by repeatedly drawing $m$ subsamples ($m \ll n$) without replacement from an original sample of size n; it is now routinely used for robust inference with heavy-tailed data, bandwidth selection, and other large-sample applications. Despite this broad applicability across econometrics, biostatistics, and machine-learning workflows, rigorous parameter-free guarantees for the soundness of the m-out-of-n bootstrap when estimating sample quantiles have remained elusive.

This paper establishes such guarantees by analysing the estimator of sample quantiles obtained from m-out-of-n resampling of a dataset of length n. We first prove a central limit theorem for a fully data-driven version of the estimator that holds under a mild moment condition and involves no unknown nuisance parameters. We then show that the moment assumption is essentially tight by constructing a counter-example in which the CLT fails. Strengthening the assumptions slightly, we derive an Edgeworth expansion that delivers exact convergence rates and, as a corollary, a Berry–Esséen bound on the bootstrap approximation error. Finally, we illustrate the scope of our results by obtaining parameter-free asymptotic distributions for practical statistics, including the quantiles for random walk MH, and rewards of ergodic MDP's, thereby demonstrating the usefulness of our theory in modern estimation and learning tasks.

---

## 论文详细总结（自动生成）

### 论文详细中文总结

#### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：m-out-of-n 自助法（Bootstrap）被广泛用于重尾数据、带宽选择等场景的稳健推断，但针对**样本分位数估计**的严格无参数保证（parameter-free guarantees）长期缺失。现有研究存在方差公式错误（如 Cheung & Lee 2005）以及不正确理论（如 Gribkova & Helmers 2007 仅适用 m≫n 的非经典情形）。本文旨在补全 m≪n 这一实际常用场景下的理论基础。
- **整体含义**：为基于重抽样的分位数置信区间、假设检验提供严格收敛速度与渐近分布理论，从而支撑在经济计量、生物统计、机器学习（特别是 MCMC 和离线强化学习）中的稳健推断应用，例如尾部风险度量的可靠性。

#### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：利用二项式表示（binomial representation）建立 m-out-of-n 自助法估计学生化分位数的中心极限定理（CLT）与 Edgeworth 展开，并给出 Berry–Esseen 界。
- **关键技术细节**：
  - **CLT（定理 1）**：要求分布 F 在分位数 μ 处一阶 Sobolev 光滑且存在有限 α 阶矩（α>0），得到学生化统计量 `T_m^{(boot)}(μ) → N(0,1)`。证明分四步：极值控制（Borel–Cantelli）、均匀可积性（中偏差与大偏差尾界）、非学生化 CLT、Slutsky 定理。
  - **Edgeworth 展开（定理 2）**：在更强假设（F 二阶 Sobolev 光滑、m=o(n^λ), λ∈(0,1)）下给出精确 O(m^{-1/2}) 阶展开，并得到对称的二阶项（区别于传统自助法的非对称）。
  - **方差一致性（引理 7）**：给出闭式方差公式并修正前人错误（Cheung & Lee 2005），证明 `σ̂_m^{(boot)}² → p(1-p)/f²(μ)` 的速度为 O_p(m^{-3/4}n^{-1/2})。
  - **马尔可夫链扩展（定理 3）**：利用再生链（regenerative Markov chain）和 VC 维数技巧，建立 DKW 不等式，将 CLT 推广到几何遍历的马尔可夫链（如随机游走 Metropolis–Hastings、离线 MDP 奖励）。
- **公式/流程**：文中给出学生化统计量定义、方差闭式解（式 B.2），以及 Edgeworth 展开的明确形式。

#### 3. 实验设计
- **模拟场景**：论文在附录 H 中进行了蒙特卡洛模拟，未使用真实数据集，而是三种生成机制：
  1. i.i.d. 高斯观测；
  2. 简单随机游走反射到 [-1,1] 得到的马尔可夫链；
  3. 以拉普拉斯提议分布对标准正态目标进行随机游走 Metropolis–Hastings（RWMH）生成的马尔可夫链。
- **基准（Benchmark）**：未与其他方法比较，而是检验学生化统计量 T 的经验分布与标准正态分布的吻合程度，使用 Kolmogorov–Smirnov (KS) 距离作为度量。
- **对比方法**：无。本文为理论验证性模拟，仅展示不同 n 和不同块大小 m 下的表现。

#### 4. 资源与算力
- **文中未明确说明**使用的 GPU 型号、数量、训练时长等；仅提及蒙特卡洛模拟，推测为 CPU 运行，具体算力未知。

#### 5. 实验数量与充分性
- **实验数量**：三种样本量 n ∈ {10000, 20000, 50000}，每种样本量下考虑三种块大小 m = log n, n^{1/3}, √n，每种组合对应三种数据生成机制，共 9 种配置。各配置结果在表 1-3 中给出 KS 距离及均值、方差。
- **充分性评价**：
  - **优点**：覆盖了不同 n 和不同 m 尺度，验证了 CLT 近似在 i.i.d. 和马尔可夫链上的有效性；KS 距离普遍较小（多数 <0.07），支持理论结论。
  - **不足**：仅有一个度量 KS 距离，未提供置信区间覆盖率、误差条等更精细的评估；未与全样本自助法（n-out-of-n）比较；未在更高维度或更强重尾分布上测试；缺乏消融实验（如不同光滑度、矩条件不满足时的表现）。

#### 6. 论文的主要结论与发现
- **理论结论**：
  - 在仅需有限 α 阶矩（α>0）的弱条件下，学生化 m-out-of-n 分位数估计量依分布收敛到标准正态。
  - 矩条件本质上紧：构造反例（Proposition 1）显示，若分布尾部长到一定水平，方差发散，CLT 失败。
  - 在稍强条件下 (F ∈ S²(μ))，获得精确的 O(m^{-1/2}) Edgeworth 展开及 Berry–Esseen 界；该展开是对称的（二阶项为偶函数），便于构造双边参数无关检验。
  - 将结果扩展到再生马尔可夫链，首次给出 MCMC 和离线 MDP 中分位数置信区间的参数无关保证。
- **模拟结论**：三种数据生成机制下，学生化统计量的经验分布与标准正态分布吻合良好，KS 距离大多在 0.02–0.07 之间，且 m 选择为 n^{1/3} 时表现稳定。

#### 7. 优点
- **理论深度与严谨性**：从最基本的矩条件出发，逐步建立 CLT、Edgeworth 展开、Berry–Esseen 界，证明清晰且回补了前人在方差公式和 Edgeworth 分析中的错误。
- **实用性**：为无参数假设的 bootstrap 推断提供了可操作的收敛速度，并给出 m 的实用选择建议（m=O(n^{1/3})）。
- **扩展性**：将 i.i.d. 结果推广到再生马尔可夫链，覆盖 MCMC 和强化学习等现代应用场景。
- **反例构造**：通过 Construction 1 证明矩条件接近必要，增强了理论的完整性。

#### 8. 不足与局限
- **实验局限**：模拟仅覆盖三种简单分布，未验证强重尾、高维或非再生链；缺乏与全样本自助法或其它重抽样方法的比较；仅使用 KS 距离一个指标，未提供置信区间覆盖概率或经验误差棒。
- **理论局限**：
  - 矩条件虽弱但仍假设有限 α 阶矩，超重尾分布（如 Cauchy）不在覆盖范围内。
  - 马尔可夫链的结果依赖指数型再生时间矩条件（几何遍历性），未能涵盖多项式混合的更弱条件。
  - Edgeworth 展开需要二阶光滑性，并且要求 m=o(n^λ), λ<1，对 m 的选择有一定限制。
  - 未考虑联合渐近正态性或多分位数同时推断。
  - 对于马尔可夫链，缺少 Edgeworth 展开（文中指出因缺少相应工具而留作未来工作）。
- **偏差风险**：所有结论均为渐近性质，有限样本表现仅通过模拟验证，且模拟样本量较大（≥10,000），小样本行为未知。

（完）
