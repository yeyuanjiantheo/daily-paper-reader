---
title: "AlphaQCM: Alpha Discovery in Finance with Distributional Reinforcement Learning"
title_zh: AlphaQCM：基于分布式强化学习的金融阿尔法发现
authors: "Zhoufan Zhu, Ke Zhu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=3sXMHlhBSs"
tags: ["query:qf"]
score: 9.0
evidence: 使用分布式强化学习进行金融阿尔法发现
tldr: 金融领域寻找协同因子阿尔法至关重要但困难。本文将阿尔法发现建模为马尔可夫决策过程，提出AlphaQCM方法，利用分布式强化学习同时学习Q函数和分位数，并通过分位数条件实现高效搜索。实验证明该方法能有效发现高质量阿尔法组合。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-3sxmhlhbss/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3sxmhlhbss/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3sxmhlhbss/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1730, \"height\": 531, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-3sxmhlhbss/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 851, \"height\": 1061, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3sxmhlhbss/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 539, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3sxmhlhbss/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 872, \"height\": 490, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3sxmhlhbss/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 704, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3sxmhlhbss/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 807, \"height\": 523, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3sxmhlhbss/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1801, \"height\": 1144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3sxmhlhbss/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1149, \"height\": 878, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3sxmhlhbss/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1177, \"height\": 477, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3sxmhlhbss/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1113, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3sxmhlhbss/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1194, \"height\": 560, \"label\": \"Table\"}]"
motivation: 协同公式阿尔法发现面临非平稳和奖励稀疏挑战，传统方法效率低。
method: 将阿尔法发现视为序列决策问题，提出AlphaQCM，结合Q网络和分位数网络进行分布式强化学习。
result: 在金融数据上成功发现有效阿尔法，优于现有基线。
conclusion: 分布式强化学习为因子模型中的阿尔法发现提供了新途径。
---

## Abstract
For researchers and practitioners in finance, finding synergistic formulaic alphas is very important but challenging. In this paper, we reconsider the discovery of synergistic formulaic alphas from the viewpoint of sequential decision-making, and conceptualize the entire alpha discovery process as a non-stationary and reward-sparse Markov decision process. To overcome the challenges of non-stationarity and reward-sparsity, we propose the AlphaQCM method, a novel distributional reinforcement learning method designed to search for synergistic formulaic alphas efficiently. The AlphaQCM method first learns the Q function and quantiles via a Q network and a quantile network, respectively. Then, the AlphaQCM method applies the quantiled conditional moment method to learn unbiased variance from the potentially biased quantiles. Guided by the learned Q function and variance, the AlphaQCM method navigates the non-stationarity and reward-sparsity to explore the vast search space of formulaic alphas with high efficacy. Empirical applications to real-world datasets demonstrate that our AlphaQCM method significantly outperforms its competitors, particularly when dealing with large datasets comprising numerous stocks.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在金融量化投资中，自动发现一组 **协同公式化阿尔法（synergistic formulaic alphas）** 至关重要，但面临两大挑战：（1）**非平稳性**——随着挖掘到的阿尔法不断加入候选池，奖励函数会动态变化（相似阿尔法的奖励降低）；（2）**奖励稀疏性**——大多数生成的阿尔法无效，导致零奖励，只有完成整个表达式后才有非零奖励。
- **整体含义**：本文重新将阿尔法发现视为一个**序列决策问题**，并将其建模为**非平稳且奖励稀疏的马尔可夫决策过程（MDP）**，旨在通过强化学习高效搜索庞大的表达式空间，从而获得一组可解释、易组合的公式化阿尔法。

### 2. 论文提出的方法论

- **核心思想**：利用**分布式强化学习（Distributional RL）**同时学习累积折扣奖励的**分位数**和**均值（Q函数）**，然后通过**分位数条件矩（QCM）方法**从可能**有偏的分位数**中估计出**无偏方差**，将该方差作为**探索奖励（exploration bonus）**引导智能体探索不确定区域，从而缓解非平稳性和奖励稀疏性。
- **关键技术细节**：
  - **MDP建模**：状态为当前生成的 token 序列（RPN 表示），动作为可选 token，转移是确定性的，只有完成一个完整公式时才计算奖励（基于线性模型拟合后的 IC 增益）。
  - **分位数网络**：采用 **IQN（Implicit Quantile Networks）** 算法，将随机采样的分位数 τ 与 LSTM 提取的状态特征融合，输出各动作的 K 个分位数估计。
  - **Q 网络**：采用 **DQN（Deep Q-Network）** 算法，用另一个 LSTM 提取状态特征，输出各动作的 Q 值。
  - **QCM 方法**：基于 Cornish-Fisher 展开，将分位数估计值与矩的关系建模为线性回归（公式 4），使用 OLS 估计方差、偏度、峰度。理论保证（Proposition 3.1）即使分位数有偏，方差估计仍是一致无偏的。
  - **动作选择**：结合 Q 值和方差作为上置信界（公式 5）: \( a_t = \arg\max_a \left[ \hat{Q}(x_t,a) + \lambda \sqrt{\hat{h}(x_t,a)} \right] \)，其中 λ 控制风险偏好。
- **算法流程**：智能体与环境交互 → 收集经验（状态、动作、奖励、下一状态） → 分别训练 Q 网络（平方 TD 误差）和分位数网络（分位数 Huber 损失） → 使用优先经验回放加速学习 → 更新目标网络。

### 3. 实验设计

- **数据集**：中国 A 股市场三个股票池：
  - **CSI 300**（大盘 300 只股票）
  - **CSI 500**（中盘 500 只股票）
  - **Market**（全市场所有股票）
  训练期 2010-2019，验证期 2020，测试期 2021-2022（部分实验扩展至 2024）。
- **基准方法**：
  - 人类设计：Alpha101（Kakushadze 2016）
  - 机器学习（非公式）：MLP、XGBoost、LightGBM（基于 Qlib 库）
  - 遗传编程（公式）：GP w/o filter、GP w/ filter（互信息 IC 过滤）
  - 强化学习（公式）：PPO w/ filter、AlphaGen（Yu et al. 2023，最相关基线）
- **评估指标**：**信息系数（IC）**，即预测信号与未来收益的横截面相关性在时间上的均值。

### 4. 资源与算力

- **未明确说明**：论文未给出 GPU 型号、数量、单次训练时长等具体算力信息。
- **训练步数**：超参数表中给出了总步数（250k-400k 步，取决于 α 池大小 P）。
- **网络规模**：AlphaQCM 含约 **572,000** 个可训练参数（两个在线网络 + 两个目标网络），大于 AlphaGen 的约 298,609 个。后续消融实验通过调整参数大小排除了复杂度影响。

### 5. 实验数量与充分性

- **主要实验**：在三个中国数据集上对比 8 种方法，每种随机种子 10 次。
- **额外实验**：
  - 在 **S&P 500** 上对比 CSI 500 结果（跨市场泛化）。
  - **消融实验 1**：方差选择（无方差、原始方差、QCM 方差）搭配两种 DRL 骨干（QRDQN vs IQN）。
  - **消融实验 2**：领域知识（用 Alpha101 初始化回放记忆）的影响。
  - **消融实验 3**：参数大小（缩小 AlphaQCM、增大 AlphaGen 使参数量对等）。
  - **消融实验 4**：模型架构（LSTM vs MAMBA）。
  - **消融实验 5**：扩展测试集至 2021-2024。
- **充分性评价**：**较充分**。覆盖多个市场、多种基线、多个消融维度，且使用多随机种子报告均值和标准差，结果客观公正。但未做统计显著性检验（如 t 检验）。

### 6. 论文的主要结论与发现

1. **AlphaQCM 在所有数据集上 IC 最高**（CSI 300: 8.49%, CSI 500: 9.55%, Market: 9.16%），大幅领先 AlphaGen（8.13%, 8.08%, 6.04%）及其他方法。
2. **QCM 方差探索机制是关键**：使用 QCM 方差的 IC 始终高于使用原始方差或无方差。
3. **IQN 骨干优于 QRDQN**：在大多数情况下 IQN 表现更好，且差异微小。
4. **领域知识初期有增益**但后期可能限制探索，最终数据驱动方式更优。
5. **方法对参数规模和模型架构（LSTM vs MAMBA）不敏感**，鲁棒性强。
6. **在更复杂的市场（全市场股票）和美股市场（S&P 500）同样有效**，证明泛化能力。

### 7. 优点

- **理论创新**：首次将 QCM 方法引入强化学习用于金融阿尔法发现，从有偏分位数中学习无偏方差，从理论上为处理非平稳性和奖励稀疏性提供了依据。
- **实践效果**：在多个真实数据集上显著超越现有最先进方法，且在复杂大数据场景优势更明显。
- **实验设计严谨**：控制参数大小、骨干网络、方差形式等变量，排除混杂因素；报告均值和标准差，结果可靠。
- **可解释性强**：发现的阿尔法为公式化形式，可线性组合，保留金融可解释性，不同于黑箱 ML 模型。

### 8. 不足与局限

- **算力消耗未公开**：缺少 GPU 型号、训练时间等细节，不利于复现和成本评估。
- **市场覆盖有限**：仅测试股票市场（中国 A 股和美股 S&P 500），未涉及期货、外汇、加密货币等其他资产类别。
- **非平稳性仍有残留偏差**：Q 函数估计仍可能有偏，尽管通过高效探索缓解，但理论未完全消除。
- **领域知识注入可能误导**：论文本身指出领域知识可能导致局部最优，但未探索更智能的迁移或微调策略。
- **奖励函数设计依赖线性模型**：假设 meta-alpha 通过线性组合形成，可能限制了更复杂的非线性协同模式。
- **未提供统计显著性检验**：仅汇报均值和标准差，未给出 p 值或置信区间，难以严谨判断改善是否显著。

（完）
