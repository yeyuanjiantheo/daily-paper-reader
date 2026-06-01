---
title: "When Lower-Order Terms Dominate: Adaptive Expert Algorithms for Heavy-Tailed Losses"
title_zh: 当低阶项主导：面向重尾损失的自适应专家算法
authors: "Antoine Moulin, Emmanuel Esposito, Dirk van der Hoeven"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=idqBQnot0t"
tags: ["query:qf"]
score: 6.0
evidence: 面向重尾损失的自适应算法
tldr: 本文研究了重尾损失下在线预测的自适应专家算法，揭示了低阶项在重尾情况下可主导遗憾界这一反直觉现象。提出的算法无需预知损失方差，即可达到对重尾分布自适应的最优遗憾界。该工作为处理金融风险中常见的重尾损失（如极端市场波动）提供了理论最优的在线学习策略，对风险管理的在线决策具有指导意义。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-idqbqnot0t/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1131, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idqbqnot0t/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1131, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idqbqnot0t/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1129, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idqbqnot0t/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1131, \"height\": 571, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-idqbqnot0t/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 324, \"label\": \"Table\"}]"
motivation: 现有自适应算法在重尾损失下其低阶项可能主导遗憾界，导致性能退化。
method: 设计不依赖损失二阶矩的自适应算法，并通过理论分析证明其最优性。
result: 在理论上给出了与K和T相关的遗憾下界，并提出了达到该下界的算法。
conclusion: 为处理重尾在线学习问题提供了理论最优策略，可迁移至金融风险管理。
---

## Abstract
We consider the problem setting of prediction with expert advice with possibly heavy-tailed losses, i.e., the only assumption on the losses is an upper bound on their second moments, denoted by $\theta$. We develop adaptive algorithms that do not require any prior knowledge about the range or the second moment of the losses. Existing adaptive algorithms have what is typically considered a lower-order term in their regret guarantees. We show that this lower-order term, which is often the maximum of the losses, can actually dominate the regret bound in our setting. Specifically, we show that even with small constant $\theta$, this lower-order term can scale as $\sqrt{KT}$, where $K$ is the number of experts and $T$ is the time horizon. We propose adaptive algorithms with improved regret bounds that avoid the dependence on such a lower-order term and guarantee $\mathcal{O}(\sqrt{\theta T\log(K)})$ regret in the worst case, and $\mathcal{O}(\theta \log(KT)/\Delta_{\min})$ regret when the losses are sampled i.i.d. from some fixed distribution, where $\Delta_{\min}$ is the difference between the mean losses of the second best expert and the best expert. Additionally, when the loss function is the squared loss, our algorithm also guarantees improved regret bounds over prior results.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究问题**：在“预测与专家建议”（prediction with expert advice）的在线学习框架下，考虑损失函数可能具有**重尾分布**的情形。仅假设损失的第二矩有界（记为θ），但不知道损失的具体范围或矩的上界。
- **背景与动机**：实际应用中，如金融市场波动、电力负荷预测、局部差分隐私等场景，常出现重尾噪声或异常值。现有自适应算法（如AdaHedge、Squint等）的遗憾界中包含一个通常被视为“低阶项”的项——即损失的最大值（MT或LT）。在重尾损失下，这一低阶项可能**主导**整个遗憾界，导致O(√(KT))的遗憾，呈指数级劣于O(√(θT log K))的理想界。因此，需要设计能够自动适应未知二阶矩、避免低阶项主导的新算法。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：采用**多尺度熵正则化器**（multi-scale entropic regularizer）结合**坐标依赖的学习率**，并对瞬时遗憾进行**截断**（clipping），从而在不预知损失范围的前提下控制算法的稳定性和遗憾。
- **关键技术细节**：
    - **算法1（LoOT-Free OMD）**：基于在线镜像下降（OMD），使用多尺度正则化器ψt(x) = Σ (1/η_{t,i}) (x_i log x_i - x_i)，学习率η_{t,i} = β / sqrt(max{∑_{s≤t} vs¯, ∑_{s≤t} v_s(i)})，其中vs¯为专家损失方差的加权平均，v_s(i)为专家i的瞬时遗憾平方。对rt(i)进行截断：若|rt(i)| > 1/η_{t,i}则令eℓ_t(i)=0，否则eℓ_t(i) = -rt(i)。通过截断保证更新幅度有界，并利用截断代价的可控性。
    - **算法2（LoOT-Free FTRL）**：基于跟随正则化领导者（FTRL），使用Bregman散度形式的正则化器，并引入**缩放因子**b_{t-1}(i)/b_t(i)进一步调整截断后的损失，以匹配学习率的时间差。避免了OMD中的log T因子，但多了一项(1/K)∑√(V_T(i))。
    - **算法3（平方损失OMD）**：针对平方损失设计，将原始损失转换为线性化形式ℓ_t(i) = z_{t,i}(z_t - y_t) + 0.5(z_{t,i} - y_t)^2，然后应用与算法1相同的OMD框架。利用强凸性和极化恒等式获得更紧的界。
- **主要理论结果**：
    - 算法2在最坏情况下保证RT = O(√(θT log K))。
    - 算法1在最坏情况下保证RT = O(√(θT log(KT)))，在自限界环境（如i.i.d.损失）下保证RT = O(θ log(KT)/Δ_min)。
    - 算法3在平方损失下保证RT = O((Y^2+σ) log(KT))。

## 3. 实验设计：数据集 / 场景、benchmark、对比方法

- **数据集/场景**：采用**合成数据**模拟重尾损失。损失构造为 ℓ_t(i) = 1[i≠1] + ε_{t,i}，其中ε_{t,i}为Rademacher符号与独立同分布随机变量的乘积。第一组（重尾）：ε_{t,i}以概率1/T取√(KT)，以概率1-1/T取0，使得二阶矩为常数但最大值可达√(KT)。第二组（非重尾）：ε_{t,i}以概率1/T取2，其余取0，最大值有界。
- **Benchmark与对比方法**：
    - **Squint**（Koolen & Van Erven, 2015）：已知损失范围参数。
    - **AdaHedge**（De Rooij et al., 2014）。
    - **Exponential Weights (EW)**（Cesa-Bianchi et al., 2007）：使用学习率 η_t = min{1/ max|ℓ|, √(log K / ∑ vs¯)}，并已知最大损失。
    - 本文提出的算法：**lootOMD**（算法1）和**lootFTRL**（算法2）。
- **参数设置**：K从15到135，步长10；T = 20K。每个配置重复40次。算法参数：α=1/T，β=√log(KT)或√log K。

## 4. 资源与算力

- **文中明确说明**：所有实验在**Macbook Air with 8GB RAM and Apple M2 processor**上运行。未提及GPU型号、数量或具体训练时长。属于轻量级模拟，计算资源需求低。

## 5. 实验数量与充分性

- **实验数量**：两组实验，每组覆盖K ∈ {15,25,…,135}共13个取值，每个取值重复40次，总计约13×40×2=1040次实验。对比了4种基准算法，加上本文2种算法，共6种。
- **充分性与公平性**：
    - 实验覆盖了重尾和非重尾两种典型场景，验证了理论分析中低阶项主导的现象。
    - 重尾场景下，本文算法显著优于基线（遗憾更低且不随K发散），非重尾场景下性能相当或略优，体现了“最佳双世界”特性。
    - 基线算法均被给予充分的先验知识（如已知最大损失），但本文算法完全自适应，比较公平。
    - 不足之处：仅使用合成数据，未在真实世界数据集（如金融或电力）上验证，外部效度有限。

## 6. 论文的主要结论与发现

- **理论发现**：现有自适应算法遗憾界中的低阶项（最大损失）在重尾损失下可达到Ω(√KT)，从而主导整个界，使得遗憾随专家数K线性增长。
- **算法贡献**：
    - 提出了三种不需要预知损失范围或二阶矩的自适应算法，分别适用于线性损失（OMD和FTRL版本）和平方损失。
    - 遗憾界消除了对√KT的依赖，在最坏情况下达到O(√(θT log K))，在自限界环境下达到O(θ log(KT)/Δ_min)，平方损失下达到O((Y^2+σ) log(KT))。
- **实验验证**：合成数据实验证实了理论预测，本文算法在重尾场景下表现优于现有自适应算法。

## 7. 优点：方法或实验设计上的亮点

- **理论创新**：首次揭示了重尾损失下低阶项可主导遗憾这一反直觉现象，并提供了严格的上下界分析。
- **算法设计**：巧妙结合多尺度正则化、坐标依赖学习率、截断与缩放技术，使得分析简洁且无需预知矩信息。
- **最佳双世界**：单一算法在最坏情况和随机环境下均能达到接近最优的遗憾，无需切换策略。
- **平方损失扩展**：通过损失线性化技巧，将框架推广到平方损失，获得较现有方法更好的界。
- **实验设计清晰**：通过构造极端的重尾分布（以概率1/T出现大值），直观展示了低阶项的影响，且实验参数覆盖广泛。

## 8. 不足与局限：实验覆盖、偏差风险、应用限制

- **实验局限**：仅使用合成数据，未在真实重尾数据集（如金融收益率、网络流量）上测试，外部有效性有待验证。
- **算法计算成本**：算法更新需要线搜索求解无闭合形式的优化问题（由于坐标依赖学习率），计算成本略高于标准指数权重算法，但在K≤135时仍可接受。
- **理论假设**：假设损失二阶矩存在且一致有界θ，但实际中可能只有更低阶矩（如一阶矩）有界，算法能否扩展到更弱的矩假设尚未研究。
- **场景覆盖**：仅讨论了线性损失和平方损失，未涉及更一般的凸损失或指数凹损失。论文指出强凸损失扩展较容易，但指数凹损失可能具有挑战性。
- **随机环境假设**：自限界环境（Assumption 2.3）要求唯一最优专家且具有正间隔Δ_min，非平稳或连续漂移场景未考虑。

（完）
