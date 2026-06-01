---
title: Extreme Value Policy Optimization for Safe Reinforcement Learning
title_zh: 面向安全强化学习的极值策略优化
authors: "Shiqing Gao, Yihang Zhou, Shuai Shao, Haoyu Luo, Yiheng Bing, Jiaxin Ding, Luoyi Fu, Xinbing Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=3aC94m0wbF"
tags: ["query:qf"]
score: 7.0
evidence: 极值理论应用于尾部风险管理
tldr: 针对约束强化学习中期望成本约束忽略尾部极端事件的问题，提出极值策略优化（EVO）算法，利用极值理论对极端成本样本建模，优化极端分位数，从而减少罕见但严重的约束违规，在安全关键任务中表现优于基线。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-3ac94m0wbf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 861, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3ac94m0wbf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 830, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3ac94m0wbf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1778, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3ac94m0wbf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1781, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3ac94m0wbf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1770, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3ac94m0wbf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 756, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3ac94m0wbf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1774, \"height\": 798, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3ac94m0wbf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1763, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3ac94m0wbf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1776, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3ac94m0wbf/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1777, \"height\": 654, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3ac94m0wbf/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1780, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3ac94m0wbf/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1786, \"height\": 514, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-3ac94m0wbf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1813, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3ac94m0wbf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1343, \"height\": 557, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3ac94m0wbf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1154, \"height\": 711, \"label\": \"Table\"}]"
motivation: 期望成本约束无法处理尾部极端事件，导致安全违规。
method: 将极值理论融入策略优化，通过极端分位数目标显式捕获极端样本。
result: 在多个安全RL任务中显著降低了约束违规。
conclusion: 极值理论可有效增强约束强化学习的安全性。
---

## Abstract
Ensuring safety is a critical challenge in applying Reinforcement Learning (RL) to real-world scenarios. Constrained Reinforcement Learning (CRL) addresses this by maximizing returns under predefined constraints, typically formulated as the expected cumulative cost. However, expectation-based constraints overlook rare but high-impact extreme value events in the tail distribution, such as black swan incidents, which can lead to severe constraint violations. To address this issue, we propose the Extreme Value policy Optimization (EVO) algorithm, leveraging Extreme Value Theory (EVT) to model and exploit extreme reward and cost samples, reducing constraint violations. EVO introduces an extreme quantile optimization objective to explicitly capture extreme samples in the cost tail distribution. Additionally, we propose an extreme prioritization mechanism during replay, amplifying the learning signal from rare but high-impact extreme samples. Theoretically, we establish upper bounds on expected constraint violations during policy updates, guaranteeing strict constraint satisfaction at a zero-violation quantile level. Further, we demonstrate that EVO achieves a lower probability of constraint violations than expectation-based methods and exhibits lower variance than quantile regression methods. Extensive experiments show that EVO significantly reduces constraint violations during training while maintaining competitive policy performance compared to baselines.

---

## 论文详细总结（自动生成）

# 论文总结：Extreme Value Policy Optimization for Safe Reinforcement Learning

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：在安全强化学习（Safe RL）中，传统的约束强化学习（CRL）方法使用期望累积成本作为约束，忽略了尾部极端事件（如黑天鹅事件）导致的严重违规。即使期望成本满足阈值，仍可能因极端样本而频繁发生约束违规。
- **背景**：现有方法分为期望约束（如CPO）和概率约束（如WCSAC、QCPO）。期望约束无法捕捉成本分布的尾部变异性；概率约束方法（如使用条件风险价值CVaR）依赖高斯近似，无法准确刻画尾部行为，且忽视极端样本的高方差问题。
- **本文目标**：利用极值理论（EVT）对极端成本样本建模，并将其融入策略优化，以在训练过程中显著减少约束违规，同时保持较高的回报。

## 2. 论文提出的方法论
- **核心思想**：将极值理论（EVT）引入CRL，通过广义帕累托分布（GPD）对成本分布的尾部进行建模，并提出极端分位数约束来显式控制尾部风险。同时设计极端优先级采样机制，优先重放低概率但高信息量的极端样本，并采用离轨重要性重采样来扩充极端样本，降低方差。
- **关键技术细节**：
  - **极端分位数约束**：将约束目标从期望成本 \(J_C(\pi) \le d\) 改为极端分位数约束 \(q_{\mu+\nu} \le d\)，其中 \(q_\mu\) 是安全边界（由期望成本确定），\(q_{\mu+\nu}\) 是风险边界。尾部超出部分 \(z = q_{\mu+\nu} - q_\mu\) 用GPD建模，得到 \(q_{\mu+\nu} = q_\mu + q_H^{\nu/(1-\mu)}\)，其中 \(q_H\) 是GPD的分位数。
  - **GPD拟合**：收集超过安全边界的峰值样本 \(Y_\mu\)，用极大似然估计形状参数 \(\xi\) 和尺度参数 \(\sigma\)，进而计算风险边界。
  - **极端优先级重放**：对奖励和成本分别用EVT检测极端样本，根据其在GPD中的分位水平 \(\omega_r\) 和 \(\omega_c\) 计算优先级 \(p = \omega_r + \omega_c\)，按概率 \(P(s_i) = p(s_i)/\sum p(s_k)\) 进行重放。
  - **离轨重要性重采样**：利用历史策略样本，通过重要性权重 \(\pi(a|s)/\pi_0(a|s)\) 调整回报和成本，扩充极端样本集以降低GPD拟合方差。
  - **优化流程**：在信任区域内用线性近似求解带极端分位数约束的优化问题，类似于CPO的求解方法（公式(32)-(36)）。

## 3. 实验设计
- **使用场景**：
  - **Safety Gymnasium**：Point和Car机器人的Goal和Circle导航任务（如SafetyPointGoal1-v0, SafetyCarCircle1-v0等），模拟自动驾驶避障。
  - **Safety MuJoCo**：Ant、HalfCheetah、Humanoid、Swimmer的速度控制任务（如SafetyHalfCheetahVelocity-v1），要求保持速度上限。
- **基准方法**：
  - 期望约束方法：CPO（Constrained Policy Optimization）
  - 概率约束方法：WCSAC（Worst-Case Soft Actor-Critic）
  - 状态增强方法：Saute、Simmer（强调零违规）
  - 额外基线：PPO-Lagrangian、RCPO（附录C.1.1）
- **对比指标**：平均回报、约束违规率（或平均成本）、训练曲线（均值±标准差）。还设计了综合指标 ratio = 平均回报 / (违规率 + 常数)（附录C.2）。

## 4. 资源与算力
- **明确说明**：论文在附录C.4中描述实验环境为 Ubuntu 20.04.2 LTS，单块 GPU（GeForce RTX 3090），PyTorch 2.0.0，CUDA 11.3。
- **训练时长**：在附录C.1.2表1中给出EVO与CPO的训练时间对比。例如，SafetyPointCircle1-v0中CPO约11h23m，EVO（20样本）约11h52m（含GPD拟合约8s）；SafetyPointGoal1-v0类似。表明EVO增加的计算开销很小。

## 5. 实验数量与充分性
- **实验数量**：
  - 主要实验：8个环境（4个Safety Gym + 4个Safety MuJoCo），每个方法使用6个随机种子，报告均值和标准差。
  - 消融实验：
    1. 消去EVT约束目标（改用常分位数约束）
    2. 消去极端优先级重放
    3. 消去离轨重要性重放（图6）
  - 成本阈值敏感性实验（图5c,d）：3个不同阈值（0, 25, 35）。
  - GPD拟合准确性验证：8个环境下的KS检验（图7）。
  - 样本量对GPD拟合的影响：不同样本量（10, 20, 50, 100）的实验（图8）。
  - 额外基线对比：PPO-Lagrangian和RCPO（附录C.1.1，图9-10）。
  - 训练时间对比（表1）。
- **充分性与公平性**：
  - 实验覆盖了多种任务类型（导航、速度控制），多种机器人（Point、Car、Ant等），且初始策略可行与不可行情况均涉及。
  - 所有方法采用相同的超参数设置（表3），但各方法可能有自身特殊超参（如信任域大小、学习率等），文中未明确说明是否对基线进行调优，但遵循统一条件。
  - 随机种子数6个，可接受但不算非常大，不过足以展示统计趋势。
  - 消融实验和敏感性分析较全面，验证了各组件作用。

## 6. 论文的主要结论与发现
- EVO在几乎所有任务上实现了训练过程中近乎零约束违规，同时保持了与CPO相当的回报，显著优于WCSAC、Saute、Simmer等方法。
- 理论证明：
  - 约束违规上界比CPO更紧（定理4.1），且存在零违规的极小范围 \(\nu_0\) 使预期严格满足约束。
  - 违规概率低于期望约束方法（定理4.2）。
  - 方差低于分位数回归方法（定理4.3）。
- GPD比高斯分布更准确拟合成本尾部（图7），并且离轨重要性重采样有效降低GPD方差（图6）。
- 极端优先级重放有助于利用极端样本信息，提升策略性能（图5a,b消融结果）。
- 算法对成本阈值具有鲁棒性（图5c,d）。

## 7. 优点
- **方法创新**：首次将极值理论（EVT）系统性地融入CRL，解决了尾部风险建模问题，弥补了期望约束和现有概率约束方法的不足。
- **理论完整**：提供了约束违规上界、违规概率和方差的理论保证，并给出了零违规的显式条件。
- **实验扎实**：在多个任务上对比多种基线，进行了充分的消融和敏感性分析，验证了各模块作用。
- **计算高效**：GPD拟合仅需几秒，总训练时间相比CPO增加很少。
- **鲁棒性**：对样本量（低至10-20个）仍有较好表现，且对不同成本阈值适应良好。

## 8. 不足与局限
- **实验覆盖**：
  - 仅涉及连续动作空间的任务（Safety Gymnasium和MuJoCo），未在离散动作空间或更具挑战性的真实机器人平台上验证。
  - 环境中的障碍物和速度约束相对简单，复杂动态场景（如多智能体、高维状态空间）未测试。
- **偏差风险**：
  - GPD拟合依赖阈值选择（安全边界 \(q_\mu\)），论文中以期望成本作为阈值，但期望成本本身随策略变化，可能导致阈值不稳定。文中通过自适应 \(\nu\) 缓解，但未深入分析其他阈值策略。
  - 极端优先级重放可能引入采样偏差，虽然重要性重采样可部分纠正，但未直接对比无偏采样下的性能。
- **应用限制**：
  - 需要存储大量历史样本用于离轨重采样，可能增加内存开销。
  - EVT要求阈值足够高以保证GPD近似成立，若成本分布尾部与GPD偏差较大，拟合精度可能下降（论文已讨论，建议使用非线性变换）。
- **理论假设**：定理4.1依赖于信任区域和KL散度约束，实际中线性近似可能导致更新超出约束范围，但实验表明可行。

（完）
