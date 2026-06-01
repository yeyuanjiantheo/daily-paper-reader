---
title: "OPHR: Mastering Volatility Trading with Multi-Agent Deep Reinforcement Learning"
title_zh: OPHR：用多智能体深度强化学习掌握波动率交易
authors: "Zeting Chen, Xinyu Cai, Molei Qin, Bo An"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=2p4AtivyZz"
tags: ["query:qf"]
score: 9.0
evidence: 基于多智能体深度强化学习的期权波动率交易，聚焦隐含与实现波动率差
tldr: 本文提出首个专门针对期权波动率交易的强化学习框架OPHR，包含期权头寸智能体（OP-Agent）进行波动率择时，以及对冲路由智能体（HR-Agent）管理风险并优化路径收益。在加密货币期权数据上评估，直接利用隐含波动率与实现波动率之差来获利。该工作为波动率交易、期权对冲及风险管理提供了新的范式，与用户需求直接相关。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-2p4ativyzz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2p4ativyzz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1347, \"height\": 721, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2p4ativyzz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2p4ativyzz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1431, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2p4ativyzz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1434, \"height\": 706, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-2p4ativyzz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1398, \"height\": 465, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2p4ativyzz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1330, \"height\": 493, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2p4ativyzz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1209, \"height\": 143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2p4ativyzz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 1136, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2p4ativyzz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1127, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2p4ativyzz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1082, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2p4ativyzz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1477, \"height\": 770, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2p4ativyzz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1468, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2p4ativyzz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1254, \"height\": 458, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2p4ativyzz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 742, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2p4ativyzz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1022, \"height\": 455, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2p4ativyzz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1377, \"height\": 599, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2p4ativyzz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1475, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2p4ativyzz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1495, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2p4ativyzz/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1476, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2p4ativyzz/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1030, \"height\": 298, \"label\": \"Table\"}]"
motivation: 现有方法缺乏针对波动率交易的强化学习框架，尤其利用期权隐含与实现波动率差异。
method: 提出多智能体RL架构，包含持仓智能体与时序对冲路由智能体。
result: 在加密货币期权上验证了框架盈利能力和风险管理效果。
conclusion: 为期权波动率交易和风险管理提供了端到端的学习解决方案。
---

## Abstract
Options markets represent one of the most sophisticated segments of the financial ecosystem, with prices that directly reflect market uncertainty. In this paper, we introduce the first reinforcement learning (RL) framework specifically designed for volatility trading through options, focusing on profit from the difference between implied volatility and realized volatility. Our multi-agent architecture consists of an Option Position Agent (OP-Agent) responsible for volatility timing by controlling long/short volatility positions, and a Hedger Routing Agent (HR-Agent) that manages risk and maximizes path-dependent profits by selecting optimal hedging strategies with different risk preferences. Evaluating our approach using cryptocurrency options data from 2021-2024, we demonstrate superior performance on BTC and ETH, significantly outperforming traditional strategies and machine learning baselines across all profit and risk-adjusted metrics while exhibiting sophisticated trading behavior. The code framework and sample data of this paper have been released on https://github.com/Edwicn/OPHR-MasteringVolatilityTradingwithMultiAgentDeepReinforcementLearning

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：期权波动率交易，即利用期权隐含波动率（IV）与标的资产实现波动率（RV）之间的差异获利。传统方法（如 Black-Scholes 模型）假设理想市场（连续交易、无成本、恒定波动率等），无法捕捉现实市场的动态特性；而基于 RV 预测的机器学习方法（如 GARCH、LSTM）虽能预测波动率，但难以优化路径依赖的期权交易损益。
- **整体含义**：本文首次提出专门用于期权波动率交易的强化学习（RL）框架 OPHR，旨在通过多智能体协作实现波动率择时（何时做多/做空波动率）和动态对冲策略选择，从而在加密货币期权市场（BTC、ETH）上获取超额收益并有效管理风险。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：将波动率交易建模为双智能体合作马尔可夫决策过程（Cooperative MDP）。
  - **OP-Agent（期权头寸智能体）**：负责在每个时间步选择期权头寸方向（long volatility / short volatility / neutral），即进行波动率择时。
  - **HR-Agent（对冲路由智能体）**：每 N 步从预定义的一组对冲器（Hedgers）中选择最优的一个，以管理 Delta 风险并最大化路径依赖收益。
- **关键技术细节**：
  - **OP-Agent 训练**：
    - 采用 n-step TD 学习（n=12），利用较长轨迹更新 Q 值，以捕获延迟奖励（如 Gamma 收益需等待价格大幅波动，Theta 收益需时间积累）。
    - 损失函数（式5）：L(θ) = E[ (∑γ^k r + γ^n Q_target(s_{t+n}, argmax Q(s_{t+n}, a)) - Q(s_t, a_t) )² ]。
  - **HR-Agent 训练**：
    - 候选对冲器包括：Delta-based Hedger（设定 Delta 阈值）、Price-based Hedger（设定价格变动阈值）、Deep Hedger（用 Actor-Critic 训练不同风险厌恶参数 λ）。
    - 奖励设计：r_hr = V_t+n - V_hat_t+n，即所选对冲器相对于基准线对冲器（Delta 阈值 0.1）的超额净值变化。
  - **两阶段训练**：
    - **阶段 1（离线初始化）**：使用 Oracle 策略（利用未来 RV 与当前 IV 比较，带容忍阈值 β）生成经验轨迹，预训练 OP-Agent，降低探索负担。
    - **阶段 2（迭代在线训练）**：固定一个智能体，更新另一个，交替进行。先训练 HR-Agent，再训练 OP-Agent，循环多次。
- **算法流程**（文字描述）：
  1. 初始化 replay buffer 和 Q 网络（OP 和 HR 各自）。
  2. Phase 1：用 Oracle 策略和基准对冲器收集轨迹，预训练 OP-Agent。
  3. Phase 2：交替训练：
     - 固定 OP-Agent，用 Algorithm 2（HR-Agent 训练）更新 HR-Agent（每 n_hr 步选择对冲器，并在孪生环境执行基准对冲器计算奖励）。
     - 固定 HR-Agent，用 Algorithm 1（OP-Agent 训练）更新 OP-Agent（每步按 n-step TD 误差更新）。

## 3. 实验设计：数据集、benchmark、对比方法
- **数据集**：从 Deribit 交易所获取的 BTC 和 ETH 期权数据（2019/04/01 – 2024/07/01）。训练集 2019/04 – 2022/12，验证集 2023/01 – 2023/06，测试集 2023/07 – 2024/07。采用小时级数据，涵盖全到期日合约链、隐含波动率曲面、成交量、未平仓量等。
- **Benchmark 对比方法**：
  - **方向性波动率策略**：纯 Long Volatility（买入 ATM 跨式组合）、纯 Short Volatility。
  - **单因子模型**：均值回归（MR）、动量（MOM）——基于 RV 百分位数信号。
  - **机器学习模型**：GBDT (CatBoost)、MLP、LSTM（预测未来 RV，与 IV 比较决策）；GARCH（经典波动率预测）；DeepVol（深度学习波动率预测）。
  - **端到端深度学习**：DLOT（直接预测期权 PnL，无对冲）。
  - **消融对比**：OP（仅 OP-Agent + 规则对冲器）vs OPHR（完整框架）。
- **评估指标**：总回报（TR）、年化波动率（AVOL）、最大回撤（MDD）、年化夏普比率（ASR）、年化卡玛比率（ACR）、年化索提诺比率（ASoR）、胜率（WR）、盈亏比（PLR）、平均持有期（HP）。

## 4. 资源与算力
- **硬件**：4× NVIDIA RTX 4090 GPU（24GB 显存），AMD Ryzen Threadripper PRO 5995WX CPU。
- **训练时长**：阶段 1（OP-Agent 离线预训练）约 12 小时；阶段 2（HR-Agent 训练）约 3 小时；每次交替训练约 12+3 小时，未给出总迭代次数，但推测总耗时约数十小时。
- **说明**：算力使用合理，但未详细说明消融实验等额外计算开销。

## 5. 实验数量与充分性
- **实验数量**：两大市场（BTC、ETH），每个市场对比 14 种方法（Table 2），含消融实验（OP vs OPHR）。另提供交易行为分析（Table 3，区分多/空头）、交易成本分析（Table 4）、PnL 分解（附录 Table 14）、Oracle 策略影响（未详细展示但提及）、超参数敏感性（附录列出表格）。
- **充分性与公平性**：
  - 所有基线均采用统一对冲规则（Delta 阈值 0.1），避免偏差。
  - 对比方法丰富，覆盖方向性、因子、经典计量、深度学习、端到端方法。
  - 测试集为未来数据（2023/07 – 2024/07），确保前瞻性。
  - 但实验仅局限在加密货币期权市场（BTC/ETH），未验证传统股票或指数期权；且未进行多次随机种子重复实验（金融回测中通常只跑一次历史路径，无法计算统计显著性），论文承认这一点（附录指出“statistical significance is not applicable”）。

## 6. 论文的主要结论与发现
- OPHR 在 BTC 和 ETH 测试集上均获得最高总回报（BTC: 33.10%, ETH: 44.89%），并在所有风险调整指标（ASR、ACR、ASoR）上排名第一，显著优于传统策略和 ML 基线。
- OPHR 相比仅使用规则对冲的 OP 模型，总回报提升约 50%（BTC: 21.43%→33.10%，ETH: 23.49%→44.89%），风险指标也大幅改善，证明 HR-Agent 的动态对冲选择有效。
- 交易行为分析（Table 3）显示 OPHR 具有自适应波动率择时能力：多头持有期短（9-21 小时）捕捉波动率尖峰，空头持有期长（~50 小时）赚取时间价值。
- 交易成本仅占 PnL 的 5.75%–9.36%，表明策略真实盈利不受过高交易成本侵蚀。
- PnL 分解（Table 14）验证了策略逻辑：多头 Gamma 主要盈利来源为 Gamma 和 Vega，空头 Gamma 盈利来自 Theta 和 Vega。

## 7. 优点
- **创新性**：首个专门针对期权波动率交易的 RL 框架，将问题分解为波动率择时和对冲策略选择两个子任务，多智能体架构设计精巧。
- **方法论充分**：两阶段训练（Oracle 初始化 + 交替在线优化）有效解决 RL 在金融领域的高延迟奖励和探索困难问题。
- **实验全面**：覆盖两种主流加密货币、多种基线（传统因子、机器学习、端到端）、多指标评估，并深入分析交易行为、成本、PnL 分解，透明度高。
- **实用价值**：代码与示例数据已开源，便于复现和扩展；交易成本分析确保结论真实可靠。

## 8. 不足与局限
- **市场局限性**：仅使用加密货币期权（BTC/ETH），未在传统股票或指数期权上验证，通用性待确认。
- **策略覆盖不足**：仅考虑 ATM 跨式组合的方向性波动率交易，未探索波动率微笑（skew）斜率、期限结构异象等更多套利机会。
- **对冲器设计局限**：HR-Agent 仅从预定义集合中选择，而非直接学习连续对冲动作；对冲器的训练基于模拟数据，可能与真实市场存在差距。
- **统计显著性**：金融回测只能运行一条历史路径，无法报告误差条，但可考虑通过 bootstrap 或不同子区间测试增加可信度。
- **计算资源成本**：训练耗时较长（单次交替约 15 小时），实际部署可能需要更高效的在线更新策略。
- **未来工作方向**：论文自身也指出可探索更多波动率交易模式、并让对冲器直接融入市场特征进行更精确决策。

（完）
