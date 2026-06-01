---
title: "Adaptive Variance Inflation in Thompson Sampling: Efficiency, Safety, Robustness, and Beyond"
title_zh: 汤普森采样中的自适应方差膨胀：效率、安全性、鲁棒性及其他
authors: "Feng Zhu, David Simchi-Levi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=IBhxvINfxv"
tags: ["query:qf"]
score: 4.0
evidence: 自适应方差膨胀用于鲁棒序贯决策
tldr: 汤普森采样在安全和鲁棒性方面表现欠佳。本文提出自适应方差膨胀，在采样方差中引入时间依赖的膨胀因子，使策略在保持最优期望遗憾的同时，实现最坏情形最优的快速收敛。该方法可用于投资组合管理等序贯决策任务，提升对模型误设的鲁棒性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ibhxvinfxv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1404, \"height\": 867, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ibhxvinfxv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1403, \"height\": 867, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ibhxvinfxv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1403, \"height\": 866, \"label\": \"Figure\"}]"
motivation: 汤普森采样在安全性和鲁棒性标准下表现不佳。
method: 在高斯汤普森采样的方差中引入时间-臂依赖的膨胀因子。
result: 实现了最坏情形最优期望遗憾和快速收敛，兼具效率与鲁棒性。
conclusion: 为鲁棒序贯决策提供了简单有效的改进方法。
---

## Abstract
Thompson Sampling (TS) has emerged as a powerful algorithm for sequential decision-making, with strong empirical success and theoretical guarantees. However, it has been shown that its behavior under stringent safety and robustness criteria --- such as safety of cumulative regret distribution and robustness to model mis-specification --- can sometimes perform poorly. In this work, we try to address these aspects through the lens of adaptive variance inflation for Gaussian Thompson Sampling. Our one-line change introduces a time- and arm-dependent inflation factor into the sampling variance, and yields several compelling benefits. The resulting policy achieves provably worst-case optimal expected regret and worst-case optimal fast-decaying regret tail bounds, even in the presence of heavy-tailed (sub-exponential) noise or mis-specified environments. The policy is also robust to mis-specified noise variances. Beyond cumulative regret, we further demonstrate that our method ensures strong post-experiment guarantees: simple regret and estimation error per arm exhibit fast-decaying tail probabilities, contributing to more reliable and robust downstream decisions. Finally, we extend our policy to incorporate settings with unknown arm-specific variances and empirically validate the consistent performance of our approach across a range of environments.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景**：Thompson Sampling (TS) 是序贯决策中强大且实用的算法，具有良好的经验表现和理论保证（期望遗憾最优）。然而，近年来研究表明，TS 在**安全性**（遗憾尾部分布集中性）和**鲁棒性**（对模型误设、超参数误设的稳定性）方面表现不佳。例如，即使在标准环境下，TS 的遗憾尾部概率衰减缓慢（多项式而非指数），且在噪声方差或分布形式误设时，性能急剧恶化。
- **核心问题**：如何修改 TS，使其同时实现**效率**（最优期望遗憾）、**安全性**（遗憾尾部快速衰减）和**鲁棒性**（对超参数和环境误设不敏感），并保证“实验内”（累积遗憾）和“实验后”（简单遗憾、每臂估计误差）的优良性质？
- **整体含义**：本文提出 **TS with Variance Inflation (TS-VI)**，通过一行代码修改——在采样方差中引入自适应膨胀因子——将 TS 改造为在**最坏情形**下同时满足上述三目标的策略，为实际部署提供了可靠、安全的决策方案。

## 2. 论文提出的方法论

### 核心思想
- 在标准高斯 TS 的采样方差中引入**时间依赖和臂依赖的膨胀因子**，鼓励更多探索，从而在保证期望遗憾最优的同时，大幅改善尾部风险。

### 关键技术细节
- **标准 TS**：在时刻 \(t\)，对于臂 \(k\)，采样值 \(X_{t,k} \sim \mathcal{N}\left(\hat{\mu}_{t,k},\ \frac{\sigma_0^2}{n_{t,k}}\right)\)，其中 \(\hat{\mu}_{t,k}\) 为经验均值，\(n_{t,k}\) 为截至 \(t\) 的拉取次数，\(\sigma_0\) 为已知方差（可理解为超参数）。
- **TS-VI**：将采样方差修改为 \(\frac{t/K}{n_{t,k}^2} \sigma_0^2\)，即
  \[
  X_{t,k} \sim \mathcal{N}\left(\hat{\mu}_{t,k},\ \frac{t}{K n_{t,k}^2} \sigma_0^2\right).
  \]
  其中 \(K\) 为臂数，\(t\) 为当前时刻。
- **算法流程**：
  1. 初始化：每个臂至少拉一次（探索）。
  2. 每轮 \(t\)，对每个臂 \(k\)，从上述膨胀后验中采样。
  3. 选择采样值最大的臂执行。
  4. 更新相应臂的经验均值和计数。
- **后验更新不变**：仍按标准高斯共轭更新（经验均值 \(\hat{\mu}\) 不变，后验方差仍为 \(\sigma_0^2/n_{t,k}\)），仅采样时使用膨胀方差。这使得算法保持了贝叶斯框架的简洁性。

### 理论保证
- **实验内遗憾**：最坏情形期望遗憾 \(\tilde{O}(\sqrt{KT})\)，尾部概率以 \(\exp(-\tilde{\Omega}(x/\sqrt{KT}))\) 速度衰减（最优）。
- **实验后决策质量**：简单遗憾（最好臂识别）和每臂估计误差的尾部均以指数速率衰减，期望误差最优。
- **鲁棒性**：对超参数 \(\sigma_0\) 和噪声分布（亚高斯/亚指数）误设不敏感，仅影响常数因子。

## 3. 实验设计

### 使用场景 / 数据集
- **合成数据**：采用多臂老虎机标准框架，奖励带有噪声。
- **三种环境**：
  - **完全正确指定（Well-specified）**：高斯噪声，方差已知且与假设一致。
  - **模型误设（Mis-specified）**：指数环境 + 拉普拉斯噪声（方差不同于高斯假设），但假设噪声为高斯。
  - **未知异质方差（Unknown heterogeneous variances）**：两个臂具有不同未知方差（拉普拉斯噪声，\(b_1=1, b_2=2\)），使用 Gamma-Normal 贝叶斯更新。

### 基准对比方法
- **标准 TS**：取不同 \(\sigma_0\)（0.9σ, 1.0σ, 1.1σ）
- **UCB**：同样取不同 \(\sigma_0\)（0.9σ, 1.0σ, 1.1σ）
- **TS-VI**：取 \(\sigma_0 = 0.3σ, 0.4σ, 0.5σ\)（根据经验选择偏小值）
- 每个方法运行 10,000 条独立轨迹。

### 评估指标
1. 期望遗憾随时间变化（带95%置信区间）
2. 累积奖励小于0的对数尾部概率 vs 时间
3. 每臂平均绝对估计误差随时间变化
4. 绝对估计误差大于δ的对数尾部概率 vs 时间

### 扩展实验（附录）
- 2臂情况不同 δ=0.5
- 6臂情况 δ=0.3, 0.5

## 4. 资源与算力

- **论文中未明确说明所使用的GPU型号、数量或训练时长**。
- 仅提及每个策略收集10,000条轨迹（每条轨迹T=10000步），计算量相对较小，可在普通CPU上完成。未提及分布式训练或GPU加速。

## 5. 实验数量与充分性

- **组数**：主实验共3组（三种环境设定），每组包含4个指标图（共12个子图），外加附录中2臂δ=0.5和6臂实验。
- **对比方法**：每个环境对比了TS（三种σ₀）、UCB（三种σ₀）、TS-VI（三种σ₀），覆盖超参数敏感性。
- **充分性**：实验覆盖了正确指定、误设、异质方差等典型情况，变量控制较好。但仅使用10,000条轨迹，可能不足以精确估计极小尾部概率。此外，没有在真实数据集或更复杂的应用中验证，属于合成数据实验。
- **客观性**：所有方法在同一条件下运行，误差线（95%置信区间）报告了期望值波动，尾部概率采用对数尺度展示，结果清晰。总体上实验设计较为公平和充分。

## 6. 论文的主要结论与发现

1. **效率可接受**：TS-VI 的期望遗憾略高于标准 TS 和 UCB，但差距控制在 20~100 范围内（相对于总遗憾约几千），且在小时间范围（T≤1000）有时甚至更低。
2. **安全性显著提升**：TS-VI 的累积奖励小于0的尾部概率快速逼近0（通常到T≈5000即接近0），而标准 TS 和 UCB 的尾部衰减缓慢。尤其在大噪声或误设下，TS-VI 大幅降低了尾风险。
3. **估计准确性更好**：每臂平均绝对估计误差和尾部误差概率均优于 TS 和 UCB，得益于更充分的探索（每臂拉取至少 Ω(√T/K) 次）。
4. **鲁棒性强**：TS-VI 对超参数 σ₀ 选择不敏感，在误设或异质方差环境下仍保持稳定，而 TS 和 UCB 在欠规范（σ₀ 偏小）时尾部风险剧增，过规范（σ₀ 偏大）时改善有限。
5. **理论验证**：所有实验结果与理论最坏情形分析一致，证实了 TS-VI 兼具效率、安全性和鲁棒性。

## 7. 优点

- **方法简洁**：仅需修改一行采样方差公式，易于理解和部署。
- **理论完备**：给出了严格的最坏情形遗憾尾部指数衰减界、期望遗憾界以及后验决策误差界，填补了安全性和鲁棒性理论空白。
- **兼顾多目标**：同时优化实验内与实验后性能，不牺牲期望遗憾过多。
- **实用性**：支持未知异质方差（Gamma-Normal 扩展），可直接用于真实场景。
- **实验覆盖全面**：考虑了多种误设情况，并报告了尾部概率（通常被忽略的重要安全指标）。

## 8. 不足与局限

1. **缺乏实例依赖性分析**：所有理论均为最坏情形，未提供实例依赖性（instance-dependent）上界。实际中若子优间隙较大，TS-VI 可能过度探索，导致遗憾上升。
2. **渐近行为不明确**：未分析长时间下各臂拉取比例的极限分布。
3. **框架局限**：仅针对标准多臂老虎机，未扩展到线性 bandit、非参数模型、MDP 等更复杂环境。
4. **实验规模较小**：仅使用合成数据，轨迹数 10,000 条可能不足以捕捉极尾事件；未在真实应用（如推荐系统、临床试验）上验证。
5. **超参数选择依赖经验**：TS-VI 的 σ₀ 需小于实际噪声标准差才能获得最佳性能（文中选 0.3σ~0.5σ），但未提供理论指导如何自动选择。
6. **效率与安全性的权衡**：虽然牺牲可控，但在需要极致效率的场景（如广告投放 A/B 测试）中，TS-VI 可能不如标准 TS 受欢迎。

（完）
