---
title: "Decision Theoretic Foundations for Conformal Prediction: Optimal Uncertainty Quantification for Risk-Averse Agents"
title_zh: 共形预测的决策理论基础：风险厌恶代理的最优不确定性量化
authors: "Shayan Kiyani, George J. Pappas, Aaron Roth, Hamed Hassani"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Ukjl86EsIk"
tags: ["query:qf"]
score: 7.0
evidence: 将共形预测与风险厌恶代理的风险价值联系起来的理论基础
tldr: 风险厌恶决策者需要合适的不确定性量化。本文建立决策理论基础，证明预测集对于优化风险价值（VaR）是最优的，并提出一个最大最小决策策略。该理论为共形预测在风险管理中的应用提供了严格支撑。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ukjl86esik/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1331, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ukjl86esik/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 865, \"height\": 631, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ukjl86esik/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1751, \"height\": 786, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ukjl86esik/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 850, \"height\": 435, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ukjl86esik/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 827, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ukjl86esik/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 534, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ukjl86esik/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 824, \"height\": 228, \"label\": \"Table\"}]"
motivation: 现有不确定性量化方法缺乏对风险厌恶决策者的理论最优性保证。
method: 从决策论出发，证明预测集能优化风险价值（VaR），并推导最优映射策略为最大最小决策。
result: 理论证明预测集对VaR最优，且最大最小策略是风险厌恶代理的最佳行动映射。
conclusion: 建立了共形预测与风险厌恶决策的严格联系，提供了理论指导。
---

## Abstract
A fundamental question in data-driven decision making is how to quantify the uncertainty of predictions to inform risk-sensitive downstream actions, as often required in domains such as medicine. We develop a decision-theoretic foundation linking prediction sets to risk-averse decision-making, addressing three questions: (1) What is the correct notion of uncertainty quantification for risk-averse decision makers? We prove that prediction sets are optimal for decision makers who wish to optimize their value at risk. (2) What is the optimal policy that a risk averse decision maker should use to map prediction sets to actions? We show that a simple max-min decision policy is optimal for risk-averse decision makers. Finally, (3) How can we derive prediction sets that are optimal for such decision makers? We provide an exact characterization in the population regime and a distribution free finite-sample construction. These insights leads to *Risk-Averse Calibration (RAC)*, a principled algorithm that is both *practical*—exploiting black-box predictions to enhance downstream utility—and *safe*—adhering to user-defined risk thresholds. We experimentally demonstrate RAC's advantages in medical diagnosis and recommendation systems, showing that it substantially improves the trade-off between safety and utility, delivering higher utility than existing methods while avoiding critical errors.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **研究动机**：在医疗、金融等高风险决策场景中，预测的不确定性量化至关重要。传统期望效用最大化准则适合于风险中性代理，但风险厌恶代理需要高概率保证（即效用“风险价值”，Value-at-Risk）。当前缺乏严格的理论框架来回答：对于风险厌恶者，什么是最优的不确定性量化方式？如何从预测集得到最优行动？以及如何构造最优预测集？
- **整体贡献**：本文建立了共形预测（Conformal Prediction）与风险厌恶决策之间的决策理论基础，证明**预测集**是优化风险价值的充分统计量；**最大最小决策规则**是最优行动策略；并基于此提出**Risk-Averse Calibration (RAC)** 算法，提供分布自由的有限样本安全保证，且可结合任意黑盒预测模型。

## 2. 方法论：核心思想与关键技术细节

- **核心思想**：将传统共形预测的边际覆盖保证与风险厌恶代理的风险价值目标统一。
- **关键定义**：
  - 风险厌恶决策者目标：最大化平均效用证书 $\nu(x)$ 满足 $\Pr[u(a(X),Y) \ge \nu(X)] \ge 1-\alpha$（即边际约束下的VaR优化）。
  - 定义函数 $\theta(x,t) = \max_a \text{quantile}_{1-t}[u(a,Y)|X=x]$，表示给定条件覆盖度 $t$ 时的最优风险价值。
- **关键理论结果**：
  - **等价性定理（Theorem 2.3）**：原始风险厌恶目标（RA-DPO）与基于预测集的最大最小目标（RA-CPO）等价，说明预测集是充分统计量。
  - **最优预测集刻画（Theorem 3.2）**：最优预测集可由一维参数 $\beta$ 确定：$t^*(x) = g(x,\beta)$，其中 $g(x,\beta)=\arg\max_s\{\theta(x,s)+\beta s\}$，$\beta$ 由 $\mathbb{E}[g(X,\beta)]=1-\alpha$ 解得。
- **算法流程（RAC）**：
  1. 利用预训练模型估计条件概率 $f_x(y)$，计算 $\hat{\theta}(x,t)$ 和 $\hat{g}(x,\beta)$。
  2. 在标定集上通过二分搜索找到 $\hat{\beta}_y$ 使得每个可能标签 $y$ 对应的预测集满足边际覆盖（对称交换性保证）。
  3. 最终预测集 $\hat{C}(x)$ 由 $\{y: u(\hat{a}(x,\hat{\beta}_y),y) \ge \hat{\theta}(x,\hat{\beta}_y)\}$ 构成。
  4. 决策者执行最大最小策略：$a_{RA}(\hat{C}(x)) = \arg\max_a \min_{y\in\hat{C}(x)} u(a,y)$。

## 3. 实验设计

- **数据集与场景**：
  1. **医学诊断**：COVID-19 Radiography Database（4 类：Normal, Pneumonia, COVID-19, Lung Opacity），70% 训练、10% 标定、20% 测试。使用 Inception v3 微调后作为预测模型。效用矩阵由临床经验设计（Table 1）。
  2. **推荐系统**：MovieLens 数据集（评分 1~5），80% 训练、10% 标定、10% 测试。训练神经网络分类器估计评分概率。效用矩阵定义推荐与不推荐的效用（Table 2）。
- **对比方法**：
  - **最佳响应（Best Response）**：基于校准后的模型期望效用最大化，直接取最优动作，无安全保证。
  - **CP + 最大最小**：三种不同评分函数的共形预测集（score-1: Sadinle et al., 2019；score-2: Romano et al., 2020；score-3: Cortes-Gomez et al., 2024），然后执行最大最小策略。
- **实验指标**：
  - 平均实现最大最小值（Average realized max-min value，即 $\nu_{RA}$）。
  - 关键错误率（Critical mistakes percentage）。
  - 平均实现效用（Average realized utility）。
  - 实际错误覆盖率（Realized miscoverage）。

## 4. 资源与算力

- **未明确说明**：论文未提及训练模型所使用的 GPU 型号、数量、训练时长等具体算力信息。仅提到使用预训练 Inception v3 进行微调，以及训练推荐系统的神经网络。缺乏算力报告是常见局限。

## 5. 实验数量与充分性

- **实验数量**：共两大类型实验（医学诊断 + 推荐系统）。每个实验中，作者针对不同名义错误率 $\alpha$ 画出多条曲线，并对比四种 CP 方法及最佳响应。没有额外的消融实验（例如改变效用矩阵、测试不同模型架构、跨领域泛化等）。
- **充分性与公平性**：
  - 指标全面：覆盖了安全（关键错误、覆盖率）和效用（平均实现值与平均效用）两方面。
  - 对比方法均为近期相关最先进成果，且 RAC 在所有 $\alpha$ 上明显优于其他 CP 方法。
  - 未提供统计显著性检验或多跑几次的均值/方差，可能使结论稳健性受到一定影响。
  - 仅涉及两个领域，结论的普适性有待更多场景验证。

## 6. 主要结论与发现

- **理论结论**：
  - 预测集是风险厌恶代理实现最优风险价值的**充分且最优**的不确定性量化形式。
  - 最大最小决策规则在边际覆盖条件下是**最坏情况下最优的**。
  - 最优预测集可显式刻画，且存在一维参数化，便于有限样本构造。
- **实验结论**：
  - RAC 在所有名义 $\alpha$ 下均比现有 CP 方法获得更高的平均最大最小值（即更强的效用证书）和更高的平均效用。
  - RAC 大幅降低关键错误率（例如医学诊断中 COVID-19 患者未被处理的比例从 >60% 降至 <10%），同时仅牺牲很小平均效用。
  - RAC 满足目标覆盖率，保证边际安全。

## 7. 优点

- **理论深度**：首次从决策论视角严格证明预测集对风险价值的最优性，统一了共形预测与风险厌恶决策。
- **算法实用性**：RAC 可结合任意黑盒模型，分布自由，仅需标定数据，易于部署。
- **安全与效用平衡**：通过唯一参数 $\alpha$ 控制风险，可适应不同领域的保守程度。
- **实验验证**：在两类高风险任务中展示了明确优势，特别是对严重错误的抑制。

## 8. 不足与局限

- **边际约束**：仅提供整体边际覆盖保证，未扩展到条件验证（如组条件、标签条件等），实际应用可能需更强保证。
- **依赖性**：RAC 性能依赖于预训练模型估计的条件概率质量；若模型质量差，理论最优性会衰减。
- **计算复杂度**：需对每个可能标签 $y$ 求解 $\hat{\beta}_y$，在标签空间很大时可能成本高。
- **算力信息缺失**：未报告计算资源，影响可复现性和公平比较。
- **实验范围有限**：仅两个领域（多类分类和评分推荐），未验证回归任务或更有实际复杂度的决策问题。
- **缺乏方差分析**：未展示多次重复实验的标准差或置信区间，削弱结论的统计可靠性。

（完）
