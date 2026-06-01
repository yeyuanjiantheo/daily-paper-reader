---
title: Distributionally Robust Policy Learning under Concept Drifts
title_zh: 概念漂移下的分布鲁棒策略学习
authors: "Jingyuan Wang, Zhimei Ren, Ruohan Zhan, Zhengyuan Zhou"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=TXIWOhUTtx"
tags: ["query:qf"]
score: 5.0
evidence: 概念漂移下的分布鲁棒策略学习，采用双重稳健估计
tldr: 分布鲁棒策略学习通常考虑联合分布漂移，过于保守。本文聚焦概念漂移（仅条件分布变化），提出双重稳健估计量评估最坏情况平均奖励。理论和方法为资产配置中的鲁棒优化提供了新工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-txiwohuttx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1429, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-txiwohuttx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1771, \"height\": 596, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-txiwohuttx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1732, \"height\": 433, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-txiwohuttx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1415, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-txiwohuttx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1311, \"height\": 174, \"label\": \"Table\"}]"
motivation: 现有鲁棒策略学习考虑联合分布漂移，过于保守且不精确。
method: 提出针对概念漂移的双重稳健估计量，评估扰动条件分布下的最坏情况奖励。
result: 理论上证明了估计量的有效性，并在合成数据上验证。
conclusion: 为应对概念漂移提供了更细腻的鲁棒策略学习框架。
---

## Abstract
Distributionally robust policy learning aims to find a policy that performs well 
    under the worst-case distributional shift, and yet most existing methods for 
    robust policy learning consider the worst-case *joint* distribution of 
    the covariate and the outcome. The joint-modeling strategy can be unnecessarily conservative
    when we have more information on the source of distributional shifts. This paper studies
    a more nuanced problem --- robust policy learning under the *concept drift*, 
    when only the conditional relationship between the outcome and the covariate changes. 
    To this end, we first provide a doubly-robust estimator for evaluating
    the worst-case average reward of a given policy under a set of perturbed conditional distributions. 
    We show that the policy value estimator enjoys asymptotic normality even if the nuisance parameters 
    are estimated with a slower-than-root-$n$ rate.
    We then propose a learning algorithm that outputs the policy maximizing the 
    estimated policy value within a given policy class $\Pi$, and show
    that the sub-optimality gap of the proposed algorithm is of the order 
    $\kappa(\Pi)n^{-1/2}$, where $\kappa(\Pi)$ is the entropy integral of $\Pi$ under the Hamming distance
    and $n$ is the sample size. A matching lower bound is provided to show the optimality of the rate.
    The proposed methods are implemented and evaluated in numerical studies, 
    demonstrating substantial improvement compared with existing benchmarks.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有离线策略学习方法通常假设训练环境与目标环境相同，但在实际应用中分布偏移（distribution shift）普遍存在，导致学习到的策略性能下降。已有鲁棒策略学习大多考虑协变量与结果变量的**联合分布偏移**（joint distribution shift），这过于保守。实际上分布偏移可分为两类：协变量偏移（covariate shift）和概念漂移（concept drift，即仅结果与协变量的条件关系变化）。如果已知协变量偏移是可识别可校正的，那么仅需针对概念漂移进行鲁棒优化。
- **核心问题**：在概念漂移下，如何高效学习一个具有最优最坏情况平均性能的策略？即假设协变量分布不变，仅条件奖励分布 \(Y|X\) 在 KL 散度约束下变化，目标是最大化最坏情况平均奖励。
- **整体含义**：本文提出一种更细粒度的鲁棒策略学习框架，利用双重稳健估计和双机器学习技术，实现渐近正态性和最优的遗憾上界（\(O(\kappa(\Pi)/\sqrt{n})\)），并提供匹配下界，理论上达到极小化最优。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：
  - 利用强对偶性将最坏情况策略价值转化为一个经验风险最小化（ERM）问题，其中优化参数 \((\alpha^*(x), \eta^*(x))\) 依赖于上下文 \(x\) 和策略 \(\pi\)。
  - 采用交叉拟合（cross-fitting）和去偏（debiasing）技术构造双重稳健估计量，允许慢于 \(\sqrt{n}\) 速率的 nuisance 参数估计，仍能达到 \(\sqrt{n}\) 收敛。
  - 为降低策略学习计算复杂度，通过求解每个动作 \(a\) 对应的优化参数 \(\theta_a^*\)，避免对每个策略 \(\pi\) 分别重复求解。

- **关键技术细节**：
  - **不确定性集合**：\( \mathcal{P}(P_{Y|X}, \delta) = \{ Q_{Y|X} : D_{\text{KL}}(Q_{Y|X}\|P_{Y|X}) \leq \delta \} \)。
  - **策略价值定义**：\(V_\delta(\pi) = E_{P_X}\left[ \inf_{Q_{Y|X} \in \mathcal{P}} E_{Q_{Y|X}}[Y(\pi(X))|X] \right]\)。
  - **对偶形式**（Lemma 2.3）：内部优化等价于 \(-\min_{\alpha\ge0,\eta\in\mathbb{R}} E_P[\alpha e^{-(Y+\eta)/\alpha-1} + \eta + \alpha\delta | X=x]\)，记 \(\ell(x,y;\theta) = \alpha e^{-(y+\eta)/\alpha-1} + \eta + \alpha\delta\)。
  - **算法1（策略价值估计）**：将数据分为K折。对每折 \(k\)：
    1. 用 \(D^{(k+1)}\) 估计倾向得分 \(\hat\pi_0^{(k)}\) 和优化参数 \((\hat\alpha_\pi^{(k)},\hat\eta_\pi^{(k)})\)（通过 ERM 和样条/筛法）。
    2. 计算 \(\hat G_\pi^{(k)}(x,y) = \ell(x,y;\hat\theta_\pi^{(k)}(x))\)，然后用回归算法估计 \(\bar g_\pi^{(k)}(x) = E[\hat G_\pi^{(k)}(X,Y(\pi(X)))|X=x]\)。
    3. 在 \(D^{(k)}\) 上构造去偏估计量：\(\hat V_\delta^{(k)}(\pi) = \frac{1}{|D^{(k)}|}\sum_{i\in D^{(k)}} \frac{1\{\pi(X_i)=A_i\}}{\hat\pi_0^{(k)}(A_i|X_i)}(\hat G_\pi^{(k)}-\hat g_\pi^{(k)}) + \hat g_\pi^{(k)}(X_i)\)。
  - **算法2（策略学习）**：利用计算技巧，只需为每个动作 \(a\) 估计 \(\theta_a^*\)（与策略无关）。然后通过最大化 \(\hat V_\delta^{\text{LN}}(\pi)\) 得到最优策略 \(\hat\pi^{\text{LN}}\)。
  - **理论保证**：
    - **Theorem 3.5**：策略价值估计量渐近正态。
    - **Theorem 4.3**：遗憾上界 \(O(\kappa(\Pi)n^{-1/2})\)，其中 \(\kappa(\Pi)\) 是 Hamming 熵积分。
    - **Theorem 4.6**：匹配下界 \(\Omega(\sqrt{\text{Ndim}(\Pi)/n})\)，表明算法极小化最优。

### 3. 实验设计：数据集/场景、benchmark、对比方法

- **模拟数据集**：
  - 协变量 \(X\in \mathbb{R}^5\) 的单位闭球内均匀采样，3个动作，每个动作的奖励 \(Y(a)|X\sim N(\beta_a^\top X,\sigma_a^2)\)。
  - 行为策略 \(\pi_0\) 根据最大线性预测分配概率（0.5,0.25,0.25等）。
  - 数据集大小：\(n=7500, 13500, 16500, 19500\)。用50个随机种子生成。
  - 测试集：100个独立测试集，每个10000个样本。
- **真实世界数据集**：
  - 来自 Behaghel et al. (2014) 对法国失业人员的大规模随机实验。二元决策（公共 vs 私营辅导项目），奖励为六个月内再就业（0/1）。数据由 Kallus (2023) 提供。
- **Benchmark方法**：
  - **SNLN**（Si et al., 2023, Algorithm 2），原用于联合分布偏移，通过 KL 链式法则适配到概念漂移场景。已知倾向得分时可直接使用，但本文中倾向得分未知，因此也用随机森林估计。
- **对比指标**：
  - 经验鲁棒策略价值 \(\bar V_\delta\)（基于测试集）。
  - 在 KL 球面上扰动奖励后的最小奖励 \(\tilde V_\delta^{\min}\)（模拟更真实的概念漂移）。

### 4. 资源与算力

论文中未明确说明使用了多少 GPU 型号、数量和训练时长。仅提及实验在四种云服务器上运行（Intel Xeon Platinum/Gold 系列，CPU 型号，内存 384GB~1.5TB，CPU 核心数 56~96）。所有实验均使用 CPU 完成（因为涉及随机森林、样条优化等，未使用 GPU）。

### 5. 实验数量与充分性

- **数量**：模拟数据集上，对每个样本规模（4种）和 每个 \(\delta\) 值（0.05,0.1,0.2）进行 50 个种子重复，报告均值与 95% 置信区间。共 \(4\times 3\times 50 = 600\) 组训练-测试组合。真实数据集上，同样 50 个种子，展示 4 种样本规模下的 \(\bar V_\delta\)（图1）和 \(\tilde V_\delta^{\min}\)（表3，20个种子）。
- **充分性**：
  - 实验覆盖了不同样本大小、不同不确定性半径 \(\delta\)，以及与现有方法 SNLN 的全面对比。
  - 还额外提供了政策价值估计的 MSE 曲线（图2，固定策略）。
  - 结果一致显示本文算法优于 SNLN，且随着样本增大优势明显。
  - 但未提供消融实验（例如不同回归方法、交叉拟合折数的影响），也未分析计算时间。
- **公平性**：对比方法 SNLN 在同样设置下使用相同的倾向得分估计方法，实验设置较为公平。但由于 SNLN 原本针对联合偏移，可能在概念漂移下保守，结果符合预期。

### 6. 论文的主要结论与发现

- 提出的双重稳健估计量 \(\hat V_\delta(\pi)\) 在较弱的 nu 参数收敛条件下仍达到渐近正态性。
- 策略学习算法 \(\hat\pi^{\text{LN}}\) 的遗憾上界为 \(O(\kappa(\Pi)n^{-1/2})\)，并具有匹配下界，因此是极小化最优的。
- 数值实验表明，本文方法在模拟和真实数据上都显著优于基准方法 SNLN：获得更高的鲁棒策略价值，且在概念漂移场景下表现更稳健。
- 关键的见解：当知道分布偏移仅来自条件分布时，比考虑联合偏移能获得更少保守的策略。

### 7. 优点

- **理论贡献**：提供了概念漂移下鲁棒策略学习的第一个完整理论分析，包括渐近分布、遗憾上界和下界。
- **方法创新**：利用强对偶和计算技巧避免了为每个策略重复求解优化问题，使学习算法可行。
- **双重稳健性**：允许慢速估计 nuisance 参数，提高了实际应用中的鲁棒性。
- **实验充分**：在模拟和真实数据上均进行了系统评估，证明了方法优于现有基准。

### 8. 不足与局限

- **实验覆盖**：仅在三个动作、连续奖励（高斯）和二元奖励的数据上测试；缺少高维动作空间或非高斯奖励的验证。
- **参数选择**：不确定性半径 \(\delta\) 的选择依赖于先验知识，文中未提供数据驱动的选择方法，如交叉验证。在实际中 \(\delta\) 的选择可能影响性能。
- **计算复杂度**：虽然避免了无穷策略求解，但仍需为每个动作估计 \(\theta_a\) 并回归，可能在大规模动作空间或高维协变量时仍然昂贵。
- **假设限制**：假设了无混淆性、重叠条件、奖励有界以及 KL 约束等，在实际数据中可能不完全满足。
- **未消融**：未进行组件消融实验（如不同回归方法、不同折数、不同逼近方法），难以判断各组件贡献。
- **资源描述**：未提供具体训练时间或 GPU 使用情况，难以评估可扩展性。
- **扩展到连续动作空间**：论文提到是未来方向，目前仅适用于有限动作。

（完）
