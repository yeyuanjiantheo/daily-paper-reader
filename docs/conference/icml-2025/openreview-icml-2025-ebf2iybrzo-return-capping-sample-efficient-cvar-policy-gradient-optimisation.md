---
title: "Return Capping: Sample Efficient CVaR Policy Gradient Optimisation"
title_zh: 回报封顶：样本高效的CVaR策略梯度优化
authors: "Harry Mead, Clarissa Costen, Bruno Lacerda, Nick Hawes"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ebf2IYBrZO"
tags: ["query:qf"]
score: 7.0
evidence: 通过回报封顶实现样本高效的CVaR优化
tldr: 现有CVaR策略梯度方法丢弃大量轨迹导致样本效率低。本文提出回报封顶策略，将轨迹回报截断而不是丢弃，并证明与原始问题等价。在多个环境中实验表明，该方法在提升样本效率的同时获得了更优的CVaR性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ebf2iybrzo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 635, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ebf2iybrzo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 529, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ebf2iybrzo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 494, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ebf2iybrzo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1271, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ebf2iybrzo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1560, \"height\": 915, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ebf2iybrzo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1270, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ebf2iybrzo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 864, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ebf2iybrzo/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 900, \"height\": 614, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ebf2iybrzo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 860, \"height\": 612, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ebf2iybrzo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1720, \"height\": 676, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ebf2iybrzo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 945, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ebf2iybrzo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1718, \"height\": 674, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ebf2iybrzo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1714, \"height\": 678, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ebf2iybrzo/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1718, \"height\": 676, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ebf2iybrzo/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1642, \"height\": 676, \"label\": \"Table\"}]"
motivation: 传统CVaR优化丢弃大量轨迹，样本效率低。
method: 将CVaR优化重构成回报封顶问题，在训练中对轨迹回报进行截断而非丢弃。
result: 在多个环境中，该方法比基线更优，且样本效率显著提高。
conclusion: 回报封顶是一种有效的CVaR优化变形，兼顾性能与效率。
---

## Abstract
When optimising for conditional value at risk (CVaR) using policy gradients (PG), current methods rely on discarding a large proportion of trajectories, resulting in poor sample efficiency.  We propose a reformulation of the CVaR optimisation problem by capping the total return of trajectories used in training, rather than simply discarding them, and show that this is equivalent to the original problem if the cap is set appropriately. We show, with empirical results in an number of environments, that this reformulation of the problem results in consistently improved performance compared to baselines. We have made all our code available here: \url{https://github.com/HarryMJMead/cvar-return-capping}.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：在安全关键或可能发生灾难性故障的应用中，需要最小化决策的最坏情况结果，而非仅优化平均表现。条件风险价值（Conditional Value at Risk, CVaR）是一种常用的风险度量，评估最差的 α 比例轨迹的期望回报。
- **现有方法的缺陷**：标准的 CVaR 策略梯度（CVaR-PG）方法通过采样一批轨迹，然后丢弃除最差 α 比例外的所有轨迹来优化 CVaR。这导致两个严重问题：
  - **样本效率极低**：当 α 很小时（如 α=0.05），95% 的轨迹被丢弃，需要大量额外采样才能获得有效梯度。
  - **忽视成功轨迹**：被丢弃的高回报轨迹可能包含有用的学习信号，特别是当这些高回报源于好的策略动作时，政策会“盲视成功”，导致梯度消失或收敛到次优解。
- **核心目标**：提出一种新的 CVaR 优化变形，在保留所有轨迹的同时，通过截断（capping）高回报轨迹的回报值，从而显著提升样本效率，并保持与原始 CVaR 优化的等价性。

## 2. 论文提出的方法论

- **核心思想**：不丢弃轨迹，而是对每条轨迹的总回报设置一个上限 cap C，训练时使用 `min(R(τ), C)` 作为目标。直观上，这相当于将高于 cap 的回报压缩到 cap 值，使得所有轨迹都能参与梯度更新，而低回报（尾部）的样本仍保持原值。
- **等价性证明（Proposition 4.1）**：
  - 定义 capped 期望：`J_C(πθ; C) = E_{τ∼πθ}[min(R(τ), C)]`。
  - 如果设置 cap C 等于最优 CVaR 策略的 VaR 值 `VaR_α(π*)`，则可以证明最大化 `J_C` 的策略与最大化原始 CVaRα 的策略等价。证明通过将积分拆分为 α 以下和以上两部分，分别达到上界来实现。
- **关键细节**：
  - **Cap 的近似更新**：由于真实的最优 VaR 未知，采用指数移动平均更新：`C_k = C_{k-1} + η (VaR_α(π_{θ_{k-1}}) - C_{k-1})`，其中 η 为更新步长。
  - **最小 cap 值 `C_M`**：防止 cap 过低导致梯度消失。通常设置为“保守基线”（例如“什么都不做”的策略）的 CVaR，或随机策略的 CVaR，或风险中性策略的 CVaR。保证 `C_M ≤ VaR_α(π*)` 有效。
  - **奖励调整**：为了实现基于 reward-to-go 的更新，将原始奖励 `r_t` 调整为 `r_t^a = min(R_t, C) - min(R_{t-1}, C)`，其中 `R_t` 是到 t 步的累积回报。
- **算法流程（Algorithm 1）**：
  1. 初始化策略 πθ1、值函数 Vθ2、cap C = C_M。
  2. 循环训练 M 步：
     - 采样 N 条轨迹。
     - 对每条轨迹的回报进行截断（capping）得到 `τ^c_i`。
     - 使用 PPO 更新 πθ1 和 Vθ2（基于截断后的轨迹）。
     - 计算原始轨迹的 VaR_α。
     - 更新 `C = C + η (VaR - C)`，并确保 `C ≥ C_M`。

## 3. 实验设计

- **环境与场景**：
  - **Betting Game**：连续赌博游戏，每位开始 16 个 token，可下注 0%~100%，获胜概率 0.8。最优风险中性策略是全押，CVaR 最优策略是谨慎下注。目标 CVaRα=0.2。
  - **Autonomous Vehicle (AV)**：自动驾驶导航图（来自 Rigter et al. 2021），通过不同道路有不同成本分布，目标达到终点。目标 CVaRα=0.05。
  - **Guarded Maze 连续版**：连续状态空间，迷宫中有守卫区域，通过守卫会遭受高随机成本。风险中性策略走最短路径，CVaR 最优策略绕开守卫。目标 CVaRα=0.05。
  - **Guarded Maze 离散版**：离散状态空间，同样概念，但迷宫中最优路径长度差更大（6步 vs 14步）。目标 CVaRα=0.2。
  - **Lunar Lander（修改版）**：在 OpenAI Gym 的 Lunar Lander 基础上，着陆到右侧会额外获得高方差奖励（均值 70，方差 100）。风险中性策略偏向右侧，CVaR 最优策略可能选择左侧平稳着陆。目标 CVaRα=0.2。
- **Benchmark 与对比方法**：
  - **Expected Value PPO**：标准 PPO 优化期望回报。
  - **CVaR-PG**：原始 Tamar et al. 的 CVaR 策略梯度（公式 6），直接使用最差 α 比例轨迹的梯度（无 PPO 裁剪和 value baseline）。
  - **CVaR-PPO**：作者提出的 PPO 版本 CVaR 策略梯度，仅在最差 α 比例轨迹上应用 PPO 损失和值函数更新。
  - **MIX (Luo et al., 2024)**：仅在 Lunar Lander 实验中加入的基线，将风险中性策略与学习到的风险规避策略混合。
- **评估指标**：训练过程中的 **CVaR 值**（基于最近采样的轨迹计算）随**环境步数（Env Steps）** 的变化曲线。

## 4. 资源与算力

- 论文 **未明确说明** 使用的 GPU 型号、数量或训练时长。仅在致谢中提及受 EPSRC 资助。从实验设置推测（如 Betting Game 每个更新 5000 步，共 200 更新，总步数 1e6 等），这些实验可能可以在单 GPU（如 NVIDIA V100 或 RTX 3090）上完成，但具体信息缺失。

## 5. 实验数量与充分性

- **实验数量**：共在 5 个任务上进行了实验（Betting Game, AV, 连续 Guarded Maze, 离散 Guarded Maze, Lunar Lander）。每个任务均与 3-4 个基线对比，并对 Return Capping 的不同最小 cap 设置（C_M）进行了消融实验。
- **种子数**：不同任务种子数不同，例如 Betting Game 未明确说种子数，但图中置信区间表明至少 5-10 个；连续 Guarded Maze 使用了 6 个种子；Autonomous Vehicle 使用了 8 个种子（但剔除了两个 CVaR-PPO 失败种子）；离散 Guarded Maze 和 Lunar Lander 各未明确但曲线有标准差。整体看种子数适中。
- **公平性**：作者努力确保基线对比公平。例如，对于 CVaR-PG/PPO，考虑到它们丢弃轨迹，要么为它们提供更大的 batch size（以保持每更新有效样本数相同），要么减少更新次数（以与环境步数对齐）。文中指出选择表现更好的配置进行对比。此外，Return Capping 的超参数（如 η, C_M）在附录中列出，并进行了敏感性分析。
- **充分性评价**：
  - **优点**：覆盖了离散/连续状态、不同 α（0.05 和 0.2）、不同环境类型（赌博、导航、迷宫、物理仿真）。消融实验揭示了 C_M 设置的影响，具有洞察力。
  - **不足**：缺乏大规模深度 RL 基准（如 Atari、MuJoCo 连续控制）。所有环境均为中等规模（状态维度低或离散）。未与部分先进的分布强化学习方法（如 DSAC、IQN-CVaR）对比。另外，在 Autonomous Vehicle 中，作者剔除了两个 CVaR-PPO 的失败种子，这可能导致基线表现被高估（尽管提供了包含 outliers 的图 C 作为补充），但原始对比图夸大了 Return Capping 的优势，存在一定偏差风险。

## 6. 论文的主要结论与发现

- **Return Capping 在样本效率和最终 CVaR 性能上全面优于基线**：在所有五个环境中，Return Capping 的 CVaR 曲线上升更快，最终值更高，且训练更稳定。
- **CVaR-PPO 基线虽有时表现良好，但不如 Return Capping 鲁棒**：例如在 Autonomous Vehicle 中，CVaR-PPO 在 8 个种子中有 2 个从未到达目标；在连续 Guarded Maze 中，6 个种子中只有 2 个收敛到 CVaR 最优策略，而 Return Capping 全部成功。
- **CVaR-PG 基线（原始方法）表现最差**：几乎所有环境中它收敛缓慢或无法收敛到最优策略，尤其在 Guarded Maze 和 Lunar Lander 中完全失败。
- **最小 cap 值敏感但可控**：对 Guarded Maze 环境，如果 C_M 设置过高（如 VaR of optimal），策略会倾向于较短的风险中性路径；而设置较低（如保守策略的 CVaR）则能有效探索并收敛到 CVaR 最优。对 Betting Game 和 AV，不同 C_M 影响较小。Lunar Lander 中，使用保守策略 CVaR 无效（无法区分好坏），需使用风险中性策略的 CVaR 作为 C_M。
- **论文提出的“盲视成功”和“梯度消失”问题通过 Return Capping 得到缓解**，尤其是当风险中性和风险规避策略差异较大时。

## 7. 优点

- **方法简洁且具有理论保证**：通过数学证明提出将 CVaR 优化等价转化为回报截断优化，无需复杂架构或环境假设（除 bounded returns）。
- **显著提升样本效率**：由于所有轨迹均被利用，在 α 很小时也能高效学习。实验表明相同环境步数下，Return Capping 的 CVaR 值远高于丢弃式方法。
- **易于集成到现代 PG 算法**：直接基于 PPO 实现，兼容 GAE、value baseline 等常见技巧，只需修改奖励和调整目标函数。
- **实验设计细致**：考虑了不同 C_M 设置、基线对比的公平性（调整 batch size 和更新次数），并提供了剔除 outliers 的补充图表，体现了科学严谨性。
- **实用性强**：提出了按需的 cap 更新规则和最小 cap 选择策略（如基于保守基线），减少了调参难度。

## 8. 不足与局限

- **对最小 cap 高度敏感**：在 Guarded Maze 中，若 C_M 设置不当（如过高）会收敛到风险中性次优解。其他任务中相对稳健，但理论上仍需要领域知识来设置一个有效的 C_M。
- **未评估大规模、高维环境**：所有实验环境均属于中等规模问题，回报分布相对简单。在复杂连续控制或视觉驱动的任务中，Return Capping 的有效性和更新规则的稳定性尚未验证。
- **缺少与最新 SOTA 方法的全面对比**：未与 Soft Risk（Greenberg et al. 2022）、Distributional RL 的 CVaR 方法（如 Dabney et al. 2018）、基于 Gini 偏差的方法（Luo et al. 2023）等做比较。仅与 MIX 基线在 Lunar Lander 中对比，但 MIX 表现不佳（收敛到风险中性）。
- **梯度更新理论基础较弱**：虽然给出了等价性证明，但针对策略梯度更新的收敛性分析（如是否保证收敛到全局最优 CVaR 策略）没有提供。同时，cap 更新规则是启发式的，可能在某些非平稳性下出现发散。
- **实验设置中的偏差风险**：在 Autonomous Vehicle 中剔除 CVaR-PPO 的两个失败种子后重新作图，使得 CVaR-PPO 看起来更好，这种做法虽然合理（为了展示典型行为），但可能低估其对不鲁棒方法的实际表现。另外，所有实验使用固定超参数，未进行系统调优，不同方法的最优超参数可能不同，但论文未说明是否对每个基线都进行了适当调优。
- **应用限制**：该方法依赖于静态 CVaR（整条轨迹的回报），不适用于要求动态/逐时间步风险的场景。此外，需要能够定义“保守策略”以获得最小 cap，这在某些抽象环境中可能不明确。

（完）
