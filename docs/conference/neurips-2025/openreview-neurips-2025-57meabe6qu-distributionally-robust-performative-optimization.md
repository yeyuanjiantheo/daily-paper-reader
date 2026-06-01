---
title: Distributionally Robust Performative Optimization
title_zh: 分布鲁棒性能优化
authors: "Zhuangzhuang Jia, Yijie Wang, Roy Dong, Grani A. Hanasusanto"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=57MeabE6QU"
tags: ["query:qf"]
score: 4.0
evidence: 分布鲁棒优化处理决策依赖分布，与稳健投资组合优化相关
tldr: 该论文针对决策依赖分布下的优化问题提出分布鲁棒框架，在模型误设时仍能保持稳健。虽非直接金融应用，但其处理分布不确定性的思想可迁移至投资组合风险管理和资产配置中的鲁棒优化，有助于提升模型在分布偏移下的表现。方法通过三种建模范式覆盖广泛场景，为金融稳健优化提供理论支撑。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-57meabe6qu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1169, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-57meabe6qu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-57meabe6qu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 583, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-57meabe6qu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 351, \"label\": \"Figure\"}]"
motivation: 决策者在真实世界中难以获取精确的分布映射，模型误设会导致次优解。
method: 提出分布鲁棒性能优化框架，显式建模决策依赖分布中的模糊性。
result: 框架覆盖三种建模范式，适用于多种机器学习和决策场景。
conclusion: 为处理分布不确定性的优化问题提供了理论方法，可应用于金融稳健优化。
---

## Abstract
In performative stochastic optimization, decisions can influence the distribution of random parameters, rendering the data-generating process itself decision-dependent. In practice, decision-makers rarely have access to the true distribution map and must instead rely on imperfect surrogate models, which can lead to severely suboptimal solutions under misspecification. Data scarcity or costly collection further exacerbates these challenges in real-world settings. To address these challenges, we propose a distributionally robust framework for performative optimization that explicitly accounts for ambiguity in the decision-dependent distribution. Our framework introduces three modeling paradigms that capture a broad range of applications in machine learning and decision-making under uncertainty. This latter setting has not previously been explored in the performative optimization literature. To tackle the intractability of the resulting nonconvex objectives, we develop an iterative algorithm named repeated robust risk minimization, which alternates between solving a decision-independent distributionally robust optimization problem and updating the ambiguity set based on the previous decision. This decoupling ensures computational tractability at each iteration while enhancing robustness to model uncertainty. We provide reformulations compatible with off-the-shelf solvers and establish theoretical guarantees on convergence and suboptimality. Extensive numerical experiments in strategic classification, revenue management, and portfolio optimization demonstrate significant performance gains over state-of-the-art baselines, highlighting the practical value of our approach.

---

## 论文详细总结（自动生成）

# 论文总结：《Distributionally Robust Performative Optimization》

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在性能优化（performative optimization）中，决策会影响随机参数的分布，即数据生成过程是决策依赖的。实际应用中，决策者通常无法获得真实的分布映射，只能依赖不完美的替代模型，这会导致模型误设下的严重次优解。此外，数据稀缺或收集成本高昂进一步加剧了挑战。
- **研究动机**：传统方法基于单一参考分布映射，在样本内可能表现良好，但在样本外（out-of-sample）情况下性能往往急剧下降。为了应对这一缺陷，论文引入分布鲁棒优化（Distributionally Robust Optimization, DRO）思想，显式建模决策依赖分布中的模糊性（ambiguity），从而提高对模型不确定性的鲁棒性。
- **整体含义**：为性能优化问题提供首个基于Wasserstein距离的分布鲁棒框架，使决策者在缺乏完整分布信息时仍能做出安全、可靠的决策，并适用于机器学习与不确定决策中的广泛场景。

## 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

### 核心思想
- **分布鲁棒性能优化（DRPO）**：以Wasserstein距离定义以参考分布为中心的模糊集，决策者最小化最坏情况下的期望风险，从而减轻对参考分布的过拟合，提升对其它可能分布的泛化能力。
- **三种建模范式**：
  - **模型1**：损失函数由Lipschitz连续函数与二次函数复合而成，等价于Tikhonov正则化问题。
  - **模型2**：损失函数为多个二次函数的最大值（分段二次），通过指数平滑（log-sum-exp）转化为光滑凸优化问题，可用指数锥规划求解。
  - **模型3**：损失函数为凸-凹形式，利用凸共轭表示与支持函数，转化为有限维凸规划，同时引入正则化项保证强凸性。

### 算法流程：重复鲁棒风险最小化（RRRM）
1. 从初始解θ₀开始。
2. 在第t轮，基于当前解θ_t对应的参考分布构建模糊集B(ˆP(θ_t))。
3. 求解如下分布鲁棒优化问题，得到下一轮解θ_{t+1}：
   \[
   \theta_{t+1} \in \arg\min_{\theta \in \Theta} \sup_{Q \in B(\hat{P}(\theta_t))} \mathbb{E}_Q[\ell(\tilde{z}, \theta)]
   \]
4. 重复直至收敛。该算法将决策与模糊集解耦，使每步迭代都可以高效求解（凸锥规划问题），并可借助现成求解器实现。

### 理论保证
- **收敛性**：在假设条件下（强凸性、光滑性、分布映射的ϵ-敏感性等），RRRM算法线性收敛到鲁棒性能稳定点（θ_RPS），且收敛率优于非鲁棒方法。
- **次优性界**：稳定解与鲁棒性能最优解（θ_RPO）之间的差距有界，界依赖于敏感度ϵ、强凸参数γ、正则化强度ρ等。

## 3. 实验设计：数据集/场景、benchmark、对比方法

### 实验场景
1. **策略分类（Strategic Classification）**：基于Kaggle信用评分数据集，使用逻辑回归，个体可以策略性地修改特征以获取有利分类。训练集200样本，测试约3600样本。
2. **收益管理（Revenue Management）**：为固定数量易逝品（如酒店房间、机票）定价，需求依赖于价格，存在模型误设（真实需求参数未知）。
3. **需求响应组合优化（Demand Response Portfolio Optimization）**：电力市场中的需求响应聚合器管理多个资源，目标最大化期望利润，资源性能噪声具有决策依赖性。

### Benchmark与对比方法
- **对比方法**：
  - 非鲁棒模型（Non-robust）
  - 基于KL散度模糊集的交替最小化算法（AMKL，来自Xue & Sun, 2024）
  - 鲁棒类型1（1-Wasserstein球）和鲁棒类型2（2-Wasserstein球）的论文方法
- **评估指标**：准确率（策略分类）、平均利润与最优性差距（收益管理、需求响应）

## 4. 资源与算力

论文仅简单说明：“所有实验在一台配备6核2.3 GHz Intel Core i7 CPU和16 GB RAM的笔记本电脑上运行。” **未提及GPU、训练时长等具体算力资源**。

## 5. 实验数量与充分性

- **策略分类**：50次独立试验（提供箱线图），比较四种方法在不同敏感性ϵ下的准确性。
- **收益管理**：针对不同数量q（200,300,400,500）进行100次独立测试，报告平均利润和最优性差距的10-90百分位区间。
- **需求响应**：两种需求负荷（低/高）下的实验，比较鲁棒与非鲁棒方案的平均利润。
- **附录中还包含**对鲁棒参数ρ的敏感性分析（在q=200,300,500下画曲线）。
- **充分性判断**：实验覆盖三个不同领域，多次随机试验，提供了统计信息（箱线图、置信区间），对比了主流baseline。但缺少消融实验（如不同正则化项、不同平滑参数的影响），也未在更大规模数据集上测试。总体而言，实验设计较充分，但可进一步扩展。

## 6. 论文的主要结论与发现

1. **所提出的分布鲁棒性能优化框架在所有三个实验中均显著优于非鲁棒baseline**，尤其在模型误设或数据稀缺时优势明显。
2. **基于Wasserstein的鲁棒方法优于基于KL散度的AMKL**，主要得益于Wasserstein距离能处理非重叠支撑集，且AMKL易陷入局部最优。
3. **2-Wasserstein球通常比1-Wasserstein球表现更好**，因为其提供了更宽的半径选择范围，使鲁棒解优于非鲁棒解。
4. **RRRM算法在理论上有线性收敛保证**，且鲁棒设置下收敛速度更快，这扩大了性能优化问题的适用范围（如非光滑、非强凸损失函数）。
5. **稳定解与最优解之间的次优性差距有显式理论界**，通过调整鲁棒性参数ρ可实现权衡。

## 7. 优点

- **理论贡献扎实**：首次在性能优化中建立Wasserstein分布鲁棒框架，并给出收敛性和次优性保证，弥补了之前工作缺乏收敛结果的缺陷。
- **方法通用性强**：三种建模范式覆盖了机器学习、运筹学中大量常见损失函数（线性/逻辑回归、分段二次、凸-凹），且可扩展到更广的应用。
- **算法可落地**：RRRM将非凸问题转化为序列凸锥规划，可调用现成求解器（如Gurobi、MOSEK），具有实际可行性。
- **实验设计多样**：涵盖分类、定价、电力系统等不同领域，增强了结论的普适性。
- **鲁棒参数ρ的选择有实证指导**：存在最佳ρ值，且在较宽范围内鲁棒方法优于非鲁棒方法。

## 8. 不足与局限

- **实验规模有限**：所有实验在小数据集或模拟场景上进行，未在工业级大规模系统（如大型资产组合、全国电网）上验证可扩展性。
- **缺乏对超参数ρ的自动选择方法**：论文指出ρ选择困难，但未提出自适应调整策略（如随时间收缩ρ）。
- **缺少与更多前沿方法对比**：如对比基于矩的DRO、贝叶斯鲁棒优化等。
- **假设较强**：收敛性和次优性证明依赖于强凸性、光滑性、分布映射的ϵ-敏感性等假设，实际中这些条件可能不完全满足。
- **仅考虑离散参考分布**：虽通过Wasserstein距离可处理连续分布，但模型1/2的推导依赖有限场景支撑集，对于完全连续分布需额外近似。
- **未讨论公平性、隐私等社会影响**：虽然在“Broader Impacts”中提到鲁棒性有益于高安全性部署，但未具体分析负面风险。
- **代码未公开**：仅说明“代码可应要求提供”，可复现性有待加强。

（完）
