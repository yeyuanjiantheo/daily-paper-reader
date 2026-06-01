---
title: Contextual Online Decision Making with Infinite-Dimensional Functional Regression
title_zh: 基于无限维函数回归的上下文在线决策
authors: "Haichen Hu, Rui Ai, Stephen Bates, David Simchi-Levi"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=hFnM9AqT5A"
tags: ["query:qf"]
score: 4.0
evidence: 序贯决策中的分布估计，可应用于风险控制
tldr: 本文针对上下文在线决策问题提出统一框架，通过学习完整分布实现期望、方差和分位数等统计量的统一处理。该方法通过无限维函数回归近似累积分布函数，解决了现有算法在无限维设置下的无穷遗憾问题。实验表明该框架在赌博机、假设检验等任务中有效，为金融风险控制中的在线决策提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-hfnm9aqt5a/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 848, \"height\": 309, \"label\": \"Figure\"}]"
motivation: 现有上下文在线决策算法依赖于特定的统计量（如期望），无法统一处理多种决策目标。
method: 提出无限维函数回归原语，学习上下文累计分布函数，进而统一支持期望、方差和分位数决策。
result: 在赌博机、序贯假设检验等任务上实现了理论上的有限遗憾和实际有效性能。
conclusion: 该方法为通用上下文在线决策提供了理论基础，可扩展至金融风险控制等实际应用。
---

## Abstract
Contextual sequential decision-making is fundamental to machine learning, with applications in bandits, sequential hypothesis testing, and online risk control. These tasks often rely on statistical measures like expectation, variance, and quantiles. In this paper, we propose a universal algorithmic framework that learns the full underlying distribution, enabling a unified approach to all contextual online decision-making problems. The challenge lies in the uncountably infinite-dimensional regression, where existing contextual bandit algorithms all yield infinite regret. We innovatively propose an efficient infinite-dimensional functional regression oracle for contextual cumulative distribution functions (CDFs) and model every datum as a combination of context-dependent CDF basis functions. Our analysis reveals that the decay rate of the eigenvalue sequence of the design integral operator governs the regression error rate, and consequently, the utility regret rate. Specifically, when the eigenvalue sequence exhibits a polynomial decay of order $\frac{1}{\gamma}\ge 1$, the utility regret is bounded by $\tilde{O}( T^{\frac{3\gamma+2}{2(\gamma+2)}})$. The case that $\gamma=0$ can recover the existing optimal rate in contextual bandits literature with finite-dimensional regression and so as exponential decay. We also provide a numerical method to compute the eigenvalue sequence of integral operators, enabling the practical implementation of our framework.

---

## 论文详细总结（自动生成）

## 基于无限维函数回归的上下文在线决策：论文详细总结

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：上下文在线决策（如多臂赌博机、序贯假设检验、在线风险控制）通常依赖于特定的统计量（期望、方差、分位数）。已有算法分别针对不同统计量设计，缺乏统一的框架。学习完整的潜在分布（即累积分布函数CDF）可以自然地支持所有统计量，但面临无限维函数回归的挑战。
- **背景**：现有上下文赌博机算法在无限维设定下会产生无限遗憾（infinite regret）。高维模型（如Transformer）的成功也凸显了有限维分析无法解释的现象，因此需要直接研究无限维回归问题。
- **核心问题**：能否基于无限维函数回归建立一个通用、鲁棒的在线决策框架，使其在理论上保证次线性遗憾，并能恢复现有最优率？

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：将每个上下文-动作对对应的CDF假设为未知权重函数θ*与一组已知基函数Φ（指数为紧集Ω）的积分（线性组合）。通过设计积分算子谱分解来有效估计θ*，进而估计CDF及任意Lipschitz连续的效用泛函T。
- **关键技术细节**：
  - **模型设定**：每个上下文x和动作a对应一个随机变量Y，其CDF为 \(F^*(x,a,s)=\int_\Omega \theta^*(w)\phi(x,a,w,s)\,d\nu(w)\)。θ*满足非负、积分归一、L2有界。基函数族Φ满足Lipschitz连续性。
  - **设计积分算子**：基于数据集D定义算子 \(U_D(\theta)(w)=\sum_{j=1}^n L_{x_j,a_j}(\theta)(w)\)，其中 \(L_{x,a}\)是具有正定、自伴、Hilbert-Schmidt性质的积分算子。其特征值序列记为λ_i(U_D)。
  - **特征值衰减假设**：假设算子集合的特征值能被一个γ-主导序列τ_i控制，即 \(\sum_{k=1}^\infty \tau_k^\gamma \le s_0\)，且λ_k ≤ τ_k ≤ O(1/k)。参数γ∈(0,1]决定了学习速率。
  - **回归算法（Algorithm 1: FuncReg）**：
    1. 构建设计积分算子U_D，计算其谱分解。
    2. 根据γ设定截断阈值ε* = n^{-2/(γ+2)}，构造截断算子 \(\hat{U}_D\)及其伪逆 \(\hat{U}^\dagger_D\)。
    3. 在截断子空间中求解最小二乘问题得到θ_D，再通过投影算子P_D（在U_D范数下投影到可行集C）得到最终估计 \(\hat{\theta}_D\)。
  - **决策算法（Algorithm 2）**：采用批次化逆概率加权（IGW）策略。将总时间T划分为长度为2^m的epoch，每个epoch开始时调用一次FuncReg更新θ_m，然后基于估计的效用值 \(\hat{v}_m(a)=T(\int\hat{\theta}_m \phi\,d\nu)\) 定义IGW策略选择动作，收集数据供下一轮回归。
- **主要定理**：
  - **定理3.6（固定设计oracle不等式）**：以概率1-δ，回归误差 \(\|\hat{\theta}_D-\theta^*\|_{U_D} \le E_D^\delta(n)\)，其中上界由特征值对数项和nεM决定。
  - **推论3.8/定理3.10（随机设计）**：将oracle不等式转化为CDF的L2误差期望上界为 \(O(E^\delta(n)^2/n)\)，且常数与参数d、L0、η等有关。
  - **定理4.2（遗憾界）**：在随机上下文设定下，调用O(log T)次回归原语，得到的期望遗憾为 \(\tilde{O}(T^{\frac{3\gamma+2}{2(\gamma+2)}})\)，其中γ为特征值衰减参数。当γ→0（或指数衰减）时，可恢复最优率 \(\tilde{O}(\sqrt{T})\)；无先验时可取γ=1得到 \(\tilde{O}(T^{5/6})\)。

### 3. 实验设计：数据集、基准、对比方法
- **本文为纯理论论文，未包含任何数值实验或模拟**。论文仅在引言和模型设定部分列举了适用场景（上下文赌博机、序贯假设检验、均值-方差赌博机）作为例子说明，并未进行实验验证。

### 4. 资源与算力
- **文中未提及任何GPU型号、数量、训练时长等计算资源信息**，因为论文完全是理论分析，没有实现与实验。

### 5. 实验数量与充分性
- **无实验**，因此不适用。论文所有结论均为数学定理证明，缺乏实证验证。需要指出的是，这种纯理论工作在机器学习顶会中常见，但应用可行性需后续实验支撑。

### 6. 论文的主要结论与发现
- 提出了一个基于无限维函数回归的统一上下文在线决策框架，通过学习整个CDF来支持任意Lipschitz连续的效用函数。
- **核心发现**：设计积分算子的特征值衰减率γ直接决定了回归误差率和遗憾界。具体地，遗憾率为 \(\tilde{O}(T^{\frac{3\gamma+2}{2(\gamma+2)}})\)。
- 该框架可以恢复有限维或指数衰减特征值情况下的最优率 \(\tilde{O}(\sqrt{T})\)，且无需预先知道γ时仍能实现 \(\tilde{O}(T^{5/6})\)的次线性遗憾。
- 提供了数值计算特征值的退化核方法（Algorithm 3），使框架具有实际可行性。

### 7. 优点
- **统一性**：首次将多种在线决策任务（期望、方差、分位数）纳入同一学习框架，只需改变效用泛函T即可。
- **理论深入**：揭示了无限维回归中算子谱性质与学习性能的紧密联系，为高维/无限维在线学习提供理论指导。
- **算法高效**：采用批次化策略将回归原语调用次数降低到O(log T)，适合特征值计算代价高的场景。
- **鲁棒性**：即使不知道特征值衰减率，也能自动获得次线性遗憾。

### 8. 不足与局限
- **缺乏实验验证**：论文完全是数学理论推导，未在合成或真实数据集上验证算法有效性，实际表现未知。
- **假设较强**：要求基函数族Φ已知且Lipschitz连续，设计积分算子族的ε-δ性质（γ-主导特征值）在实际中难以验证或估计。
- **计算可行性**：无限维积分算子的谱分解在数值上仍需近似（论文虽给出了退化核方法，但计算复杂度未分析），实际实现可能困难。
- **仅限随机上下文**：算法假设上下文i.i.d.生成，未考虑对抗性环境，而扩展至对抗性设定是未来工作之一。
- **上界紧性未证明**：遗憾上界对γ的依赖性是否最优（minimax下界）尚未确定。

（完）
