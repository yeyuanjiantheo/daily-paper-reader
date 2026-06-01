---
title: Nested Expectations with Kernel Quadrature
title_zh: 核求积法求解嵌套期望
authors: "Zonghao Chen, Masha Naslidnyk, Francois-Xavier Briol"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=OKbECHtO4S"
tags: ["query:qf"]
score: 6.0
evidence: 核求积法估计嵌套期望，应用于期权定价
tldr: 估计嵌套期望（如期权定价中的期望）传统上需要大量内层和外层样本。本文提出嵌套核求积估计器，利用高斯核和稀疏网格技术，在积分函数光滑性充足时获得更快的收敛速度。在期权定价和贝叶斯优化等任务中，所需样本数远少于嵌套蒙特卡洛方法。为隐含波动率校准和波动率曲面建模等金融计算提供了高效工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-okbechto4s/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 804, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okbechto4s/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 765, \"height\": 813, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okbechto4s/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 770, \"height\": 788, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okbechto4s/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1761, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okbechto4s/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1765, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okbechto4s/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1758, \"height\": 514, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-okbechto4s/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 688, \"height\": 418, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-okbechto4s/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1072, \"height\": 922, \"label\": \"Table\"}]"
motivation: 嵌套蒙特卡洛估计期权定价等期望需大量样本，收敛慢。
method: 提出嵌套核求积估计器，利用核方法和高斯求积加速内外层积分计算。
result: 理论证明收敛速度优于嵌套蒙特卡洛，期权定价实验中大幅减少样本量。
conclusion: 为期权定价和相关嵌套期望问题提供了高效、精确的数值方法。
---

## Abstract
This paper considers the challenging computational task of estimating nested expectations. Existing algorithms, such as nested Monte Carlo or multilevel Monte Carlo, are known to be consistent but require a large number of samples at both inner and outer levels to converge. Instead, we propose a novel estimator consisting of nested kernel quadrature estimators and we prove that it has a faster convergence rate than all baseline methods when the integrands have sufficient smoothness. We then demonstrate empirically that our proposed method does indeed require the fewest number of samples to estimate nested expectations over a range of real-world application areas from Bayesian optimisation to option pricing and health economics.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **目标问题**：估计嵌套期望（nested expectation），形如 \( I = \mathbb{E}_{\theta\sim Q}[f(\mathbb{E}_{X\sim P_\theta}[g(X,\theta)])] \)，其中内外层均涉及难以解析计算的积分。
- **典型应用**：贝叶斯优化中的前瞻采集函数、金融期权定价中的预期损失、医疗决策中的预期信息价值（EVPPI）等。
- **现有方法瓶颈**：
  - 嵌套蒙特卡洛（NMC）需要 \( O(\Delta^{-3}) \) 或 \( O(\Delta^{-4}) \) 次函数求值才能达到误差 \(\Delta\)。
  - 准蒙特卡洛（NQMC）需 \( O(\Delta^{-2.5}) \) 但要求 \( f \) 二阶导数单调等强正则性。
  - 多级蒙特卡洛（MLMC）需 \( O(\Delta^{-2}) \) 但未利用被积函数的光滑性，设计复杂。
- **本文贡献**：提出嵌套核求积（NKQ），利用核方法同时加速内外层估计，在光滑性足够时达到更快的收敛率，减少所需样本数。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

- **核心思想**：将内外层期望的估计替换为核求积（KQ），利用被积函数属于再生核希尔伯特空间（RKHS）的性质，通过最小化RKHS范数误差得到最优加权和。
- **两阶段算法（NKQ）**：
  - **阶段 I**（内层）：对每个外样本 \(\theta_t\)，使用 \( N \) 个内样本 \(\{x^{(t)}_n\}\)，用 KQ 估计 \( J(\theta_t) = \mathbb{E}_{X\sim P_{\theta_t}}[g(X,\theta_t)] \)：
    \[
    \hat{J}_{\text{KQ}}(\theta_t) = \mu_{P_{\theta_t}}(x^{(t)}_{1:N}) (K_X^{(t)} + N\lambda_X I_N)^{-1} g(x^{(t)}_{1:N},\theta_t)
    \]
    其中 \(\mu_{P_{\theta_t}}\) 是核均值嵌入，\(K_X^{(t)}\) 是Gram矩阵，\(\lambda_X\) 为正则化参数。
    然后计算 \(\hat{F}_{\text{KQ}}(\theta_t) = f(\hat{J}_{\text{KQ}}(\theta_t))\)。
  - **阶段 II**（外层）：用 KQ 估计外层期望：
    \[
    \hat{I}_{\text{NKQ}} = \mu_Q(\theta_{1:T}) (K_\Theta + T\lambda_\Theta I_T)^{-1} \hat{F}_{\text{KQ}}(\theta_{1:T})
    \]
- **技术细节**：
  - 使用 Sobolev 核（如 Matérn 核）以匹配被积函数的平滑度 \(s_X, s_\Theta\)。
  - 正则化参数取 \(\lambda_X \asymp N^{-2s_X/d_X}(\log N)^{(2s_X+2)/d_X}\)，\(\lambda_\Theta \asymp T^{-2s_\Theta/d_\Theta}(\log T)^{(2s_\Theta+2)/d_\Theta}\)。
  - 可通过“变量变换技巧”将复杂分布映射到均匀分布，以获得闭式核均值嵌入并降低计算复杂度至 \(O(N+T)\)。
- **理论结果**（Theorem 1）：在适当正则性条件下，以高概率有
  \[
  |\hat{I}_{\text{NKQ}} - I| \lesssim \tau \left( N^{-s_X/d_X}(\log N)^{(s_X+1)/d_X} + T^{-s_\Theta/d_\Theta}(\log T)^{(s_\Theta+1)/d_\Theta} \right)
  \]
  从而所需总成本为 \(\tilde{O}(\Delta^{-(d_X/s_X + d_\Theta/s_\Theta)})\)，当 \(d_X/s_X + d_\Theta/s_\Theta < 2\) 时优于所有基线方法。

### 3. 实验设计：数据集/场景、基准、对比方法

- **合成实验**：\(d_X=d_\Theta=1\)，\(Q=U[0,1]\)，\(P_\theta=U[0,1]\)，\(g(x,\theta)=x^{5/2}+\theta^{5/2}\)，\(f(z)=z^2\)，真值 \(I=0.4115\)。验证理论收敛率；并扩展到高维（\(d=1,10,20\)）。
- **金融风险管理**：Black-Scholes框架下蝶式看涨期权受冲击时的期望损失，\(d_X=d_\Theta=1\)，真值已知。条件部分不满足 \(f\) 的光滑性假设（含 max 函数）。
- **医疗决策（EVPPI）**：来自 Giles & Goda (2019) 的二元治疗方案，\(d_X=17, d_\Theta=2\)，真值 I=538。部分假设不满足。
- **贝叶斯优化**：三组标准测试函数（Dropwave、Ackley、Cosine8）上的两步前瞻采集函数，\(d_X=d_\Theta=2\)，实时记录累积时间与归一化均方误差（NMSE）。
- **对比方法**：NMC、NQMC（随机QMC）、MLMC、NKQ、NKQ+QMC、MLKQ（多级NKQ）。所有方法在相同成本下比较绝对误差或NMSE。
- **基准**：以理论真值（前三个实验）或初始化后的最优值（贝叶斯优化）为基准。

### 4. 资源与算力

- **文中未明确说明**使用的 GPU 型号、数量或训练时长。
- 仅在贝叶斯优化实验中给出了“wall clock time”作为计算效率指标，但未提及具体硬件配置。
- 其他实验（合成、金融、医疗）主要报告函数求值次数（cost = N×T）与误差关系，未提及算力消耗。

### 5. 实验数量与充分性

- **实验组数**：
  - 合成实验：重复 1000 次，报告 25%-75% 分位数。额外消融研究（正则化系数、核长度尺度、核类型）各一次。
  - 金融与医疗实验：重复 100 次。
  - 贝叶斯优化：重复 100 次，报告平均 NMSE 与阴影区间。
- **充分性评价**：
  - **覆盖范围广**：从低维到高维、从光滑到非光滑、从简单到复杂应用。
  - **消融实验充分**：研究了正则化参数 \(\lambda_0\)、长度尺度、核类型（Matern-0.5/1.5, Gaussian）的影响。
  - **对比公平**：在相同成本（N×T）下比较，且对 NMC/MLMC 也采用了理论推荐的样本分配方案。
  - **客观性**：报告误差的分布（分位数），而非仅平均值；在部分不满足假设的条件下依然汇报观察到的性能。
  - 但有改进空间：未与深度学习方法（如神经网络的近似）对比；仅针对特定几类应用。

### 6. 论文的主要结论与发现

- NKQ 在所有实验中均达到**最低的绝对误差**，且收敛速率符合理论预测（合成实验中 \(r\approx 1\) vs NMC 的 \(r\approx 3\)）。
- 即使在高维（d=20）或违反平滑性假设时，NKQ 仍优于或持平于基线方法。
- 与 QMC 结合（NKQ+QMC）进一步改善，且无需额外理论假设。
- 多级 NKQ（MLKQ）性能不如 NKQ，但优于 MLMC，未来可改进样本分配策略。
- 贝叶斯优化中，NKQ 在给定时间内达到最低 NMSE，表明真实场景下计算效率优势明显。
- **核心结论**：当问题具备适当光滑性时，NKQ 是求解嵌套期望最有效的通用方法（按所需函数求值次数计）；即使不满足假设，仍具竞争力。

### 7. 优点

- **理论严谨**：给出了高概率误差上界，并证明了渐近收敛率优于所有现有方法（在光滑性足够时）。
- **方法新颖**：首次将核求积系统地应用于嵌套期望的两阶段估计，并与 QMC/MLMC 结合，提供灵活性。
- **实验设计全面**：覆盖多个实际应用领域，包含消融研究和违反假设的鲁棒性测试。
- **实用性**：通过变量变换技巧降低计算复杂度至线性，代码开源（GitHub），易于复现。
- **可解释性**：通过 RKHS 框架提供了误差分解与超参数选择指南。

### 8. 不足与局限

- **理论假设较强**：需要密度函数有界、被积函数具有指定的 Sobolev 平滑度、f 高阶导数有界等，部分实际场景（如含 max 函数）不满足，但实验中仍有效。
- **超参数选择依赖经验**：正则化系数 \(\lambda_0\)、核类型和长度尺度需手动调节（文中使用中位数启发式 + 网格搜索），可能不易于自动化。
- **计算复杂度仍较高**：原始 KQ 需要矩阵求逆 \(O(N^3+T^3)\)，虽有变量变换技巧但仅在可构造可逆变换时适用（如高斯→均匀），通用性受限。
- **未与最新深度学习方法对比**：如基于神经网络的变分推断或深度嵌套 MC，可能在某些场景下更具可扩展性。
- **MLKQ 性能欠佳**：文中承认当前样本分配可能次优，其理论率劣于 NKQ，未来需更细致分析。
- **未讨论算力开销**：缺乏 GPU 资源报告，使得计算效率比较仅基于函数求值次数，而未考虑实际硬件差异。

（完）
