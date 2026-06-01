---
title: Conformal Prediction for Time-series Forecasting with Change Points
title_zh: 面向带变点时间序列预测的共形预测
authors: "Sophia Huiwen Sun, Rose Yu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=HgLaVgCpCl"
tags: ["query:qf"]
score: 6.0
evidence: 时间序列变点的共形预测，提升非平稳数据的不确定性量化
tldr: 现有共形预测方法难以处理时间序列中的变点。本文提出CPTC算法，通过结合状态预测与在线共形预测，有效应对非平稳数据中的突变。理论上证明了有效性，在6个合成和真实数据集上表现更优。该方法可直接用于金融时间序列波动率预测中的不确定性量化，提升模型的适应性和可靠性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-hglavgcpcl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hglavgcpcl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1372, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hglavgcpcl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1427, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hglavgcpcl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 830, \"height\": 270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hglavgcpcl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1229, \"height\": 1415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hglavgcpcl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1448, \"height\": 749, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hglavgcpcl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 749, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hglavgcpcl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 748, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-hglavgcpcl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1409, \"height\": 872, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hglavgcpcl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hglavgcpcl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 847, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hglavgcpcl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 561, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hglavgcpcl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1164, \"height\": 577, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hglavgcpcl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 599, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hglavgcpcl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1355, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hglavgcpcl/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1285, \"height\": 189, \"label\": \"Table\"}]"
motivation: 传统共形预测在时间序列变点场景下适应性不足。
method: 提出CPTC，集成状态预测与在线共形预测处理变点不确定性。
result: 在合成和真实数据上证明有效性和适应性优于现有方法。
conclusion: 为时间序列预测提供可处理变点的稳健不确定性量化工具。
---

## Abstract
Conformal prediction has been explored as a general and efficient way to provide uncertainty quantification for time series. However, current methods struggle to handle time series data with change points — sudden shifts in the underlying data-generating process. In this paper, we propose a novel Conformal Prediction for Time-series with Change points (CPTC) algorithm, addressing this gap by integrating a model to predict the underlying state with online conformal prediction to model uncertainties in non-stationary time series. We prove CPTC's validity and improved adaptivity in the time series setting under minimum assumptions, and demonstrate CPTC's practical effectiveness on 6 synthetic and real-world datasets, showing improved validity and adaptivity compared to state-of-the-art baselines.

---

## 论文详细总结（自动生成）

# 论文总结：Conformal Prediction for Time-series Forecasting with Change Points（CPTC）

## 1. 论文的核心问题与整体含义（研究动机和背景）

时间序列预测中的不确定性量化（UQ）是构建可靠机器学习系统的关键组成部分。共形预测（CP）作为一种流行的无分布 UQ 方法，能在有限样本下提供覆盖保证，且不假设数据生成过程。然而，现有 CP 方法在处理含有**变点（change points）**——即数据生成过程中的突然漂移——的时间序列时表现不佳。传统在线 CP 算法（如 ACI）只能事后反应，当分布漂移发生时会出现覆盖不足或过度覆盖的问题，需要后续时间步来补偿，这在风险敏感场景中不可取。

论文观察到，现实世界中许多分布漂移是**可预测的**，例如电力需求预测中白天/黑夜、工作日/周末的隐藏动力学变化。因此，研究者提出利用状态空间模型（特别是切换动态系统 SDS）来预测潜在状态，并结合在线共形预测，**主动适应**而非被动反应于变点。该工作旨在为非平稳时间序列提供既有效又快速自适应的不确定性量化方法。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 利用切换动态系统（SDS）显式建模时间序列的**离散状态切换**（如不同动力学模式），预测当前时刻所处的状态 z_t。
- 为每个状态 z 独立维护一组非共形分数（nonconformity scores）S_z 和一个自适应目标错误率 α_z,t，使用在线更新（类似 ACI）进行校准。
- 在每个时间步，根据状态预测概率生成各状态的预测区间，并加权聚合（基于状态后验概率）得到最终预测区间。
- 当分布漂移与预测的状态切换一致时，CPTC 能**提前调整区间**，实现比纯在线方法更快的收敛。

### 关键技术细节
- **状态预测**：使用 SDS 模型（如 RED-SDS）输出下一时刻处于每个状态的概率 p(z_t|x_{1:t})。
- **状态特定 CP**：对每个状态 z，计算非共形分数集 S_z 的经验分位数 Q_{1-α_z,t}(S_z)，构成预测区间 Γ_{z,t}。
- **在线更新**：在每个时间步 t，采用 ACI 的更新规则：α_{ẑ_t,t+1} ← α_{ẑ_t,t} + γ·(α - err_t)，其中 err_t = 1{y_t ∉ Γ_t(x_t)}，γ 为学习率。这个更新只针对采样到的状态 ẑ_t。
- **聚合策略**：论文提供两种聚合方法：
  - **加权水平集**（精确但计算复杂）：Γ_t(x_t) = { y : Σ_z p(z_t=z|x_{1:t})·1{y ∈ Γ_{z,t}(x_t)} ≥ 1-α }
  - **并集近似**（高效）：选取概率之和达到 1-α 的最小状态集合，取这些状态区间的并集。实验表明两者效果相近。
- **模块化**：算法可看作对每个状态独立运行在线共形预测，聚合时利用状态预测概率；基础预测器可更换。

### 公式与算法流程（文字说明）
1. **初始化**：对每个状态 z，初始化分数集 S_z 为空，α_z,0 = α。如果存在 warm-start 数据，则通过状态预测采样并初始化 S_z。
2. **循环 t=1..T**：
   - 对每个状态 z，用当前 α_z,t 计算状态特定区间 Γ_{z,t}。
   - 聚合所有 Γ_{z,t} 得到最终区间 Γ_t。
   - 输出 Γ_t。
   - 采样预测状态 ẑ_t ~ p(z_t|x_{1:t})。
   - 根据真实观测更新 α_{ẑ_t,t+1}（使用 ACI 更新方程）。
   - 将新分数 A(x_t,y_t) 加入 S_{ẑ_t}。
3. **理论保证**：
   - 在可交换性下具有有限样本有效性。
   - 无需假设，实现渐近有效覆盖（平均覆盖收敛到 1-α）。
   - 对不完美状态预测具有鲁棒性，覆盖偏差上界为 ϵ·max_z δ_z,T（ϵ 为状态预测错误率）。
   - 当分布漂移与预测状态切换对齐时，CPTC 的收敛速度比 ACI 快，比例由初始目标误差差决定。

## 3. 实验设计

### 数据集
- **合成数据集**（T=200）：
  - Bouncing Ball obs.：弹跳球高度，加性观测噪声，两个状态（上升/下降）。
  - Bouncing Ball dyn.：弹跳球动力学噪声，引起相位不确定性。
  - 3-Mode System：三状态切换线性动态系统，状态持续时间服从泊松分布。
- **真实数据集**（T=300 或 60）：
  - **Electricity**：UCI 机器学习库中 370 个客户的每小时用电量。
  - **Traffic**：UCI 数据库中 963 个道路传感器的每小时占用率。
  - **Dancing Bees**：蜜蜂舞蹈轨迹（4维），三个状态（左转、右转、摇摆），平均长度约 900 帧。

### 对比方法（Baselines）
- **RED-SDS**：基础 SDS 模型（也用作 CPTC 的状态预测和基础预测器），未经共形校准的贝叶斯概率预测区间。
- **CP**：朴素在线序列分割共形预测（假设可交换性）。
- **ACI**：自适应共形推断，代表在线优化型 CP。
- **SPCI**：序列预测共形推断，使用分位数随机森林学习残差分位数。
- **HopCPT**：使用现代 Hopfield 网络的条件共形预测。
- 在补充实验中还对比了 DtACI、ECI（Error-Quantified）、L-ARC（Localized Adaptive Risk Control）。

### 实验设置
- 目标置信水平 1-α = 0.9。
- 每个实验报告均值和标准差（基于测试样本的多个随机种子）。
- 预热窗口：合成数据 50 步，真实数据 100 步（蜜蜂为 15 步）。
- 每个数据集的测试集长度：合成 200，电力/交通 300，蜜蜂 60。

## 4. 资源与算力

论文在附录 B.2 中说明了计算资源：
- 使用一台带有 **Nvidia A100 GPU** 的服务器，部分数据处理和分析在 **Apple Macbook Pro（M1 芯片）** 上完成。
- **训练 RED-SDS 基础模型**（每个种子）：2-5 小时。
- **CPTC 和 ACI、CP 等推理时间**：约 5 分钟以内。
- **SPCI 推理**：8-10 小时（最耗时）。
- **HopCPT 推理**：约 1 小时。
- 论文未明确说明 GPU 数量，推测为单卡 A100。

## 5. 实验数量与充分性

### 实验数量
- 主表（表 1）包含 6 个数据集 × 6 种方法（RED-SDS、CP、ACI、SPCI、HopCPT、CPTC）共 36 组实验，报告覆盖率和区间宽度。
- 额外提供了与 DtACI、ECI、L-ARC 的对比（附录表 4），增加了 18 组实验。
- 消融实验：
  - 状态预测准确性鲁棒性（表 2、表 3）：在 3 个合成数据集上，使用真实标签、20% 噪声、50% 噪声，分别报告覆盖率和宽度，共 9 组。
  - 聚合方法对比（附录表 6）：在 6 个数据集上比较“并集”和“网格离散化”，共 12 组。
  - 长程实验（附录表 5）：T=10000（合成）和 T=4000（电力/交通），共 7 组×6 种方法（除 RED-SDS 外），约 42 组。
- 此外有大量定性可视化（图 3、图 6-8）。

### 充分性与公平性
- 实验设计较为全面：覆盖不同难度（合成简单到真实复杂）、不同变点类型（观测噪声、动力学噪声、多状态）、不同时间序列长度（短程、长程）。
- 对比了多个先进基线，包括近期方法（SPCI、HopCPT）和在线优化方法（ACI、DtACI、ECI、L-ARC）。
- 平均和标准差报告增加了统计可靠性。
- 消融实验验证了核心假设（状态预测重要性、聚合方式）。
- **潜在不足**：部分基线（如 SPCI、HopCPT）在短序列上表现不佳，作者承认其设计面向长序列（T≥10,000），但论文主要对比的短序列长度可能对这些方法不公。不过作者在长程实验中也补充了对比，表明在长序列上 CPTC 保持有效但宽度不如 SPCI/HopCPT，这体现了公正性。

## 6. 论文的主要结论与发现

1. **CPTC 在所有数据集上均达到或接近目标覆盖率 90%**，而大多数基线（尤其是 RED-SDS、CP、SPCI、HopCPT）在短序列上严重欠覆盖或过覆盖。
2. **CPTC 能快速适应变点**：在分布漂移发生时，CPTC 的覆盖损失明显小于 ACI 等反应式方法，区间宽度在变点后也较快恢复正常。
3. **CPTC 对状态预测错误具有鲁棒性**：即使状态预测准确率下降至 50%，覆盖性能基本不变（但区间宽度增加）。
4. **聚合方式（并集 vs. 精确水平集）** 效果接近，并集方法更高效。
5. **在长序列上（T≥10,000）**，CPTC 保持有效覆盖，但区间宽度比 SPCI/HopCPT 稍宽；CPTC 的优势在于数据有限或需要快速部署的场景。
6. 理论分析证明了渐近有效性和更快的适应速度。

## 7. 优点

- **创新性**：首次将可预测的变点（通过 SDS 状态预测）与在线共形预测相结合，提出“主动适应”而非“被动反应”的 UQ 范式。
- **理论扎实**：给出了有限样本有效性、渐近有效、对不完美状态预测鲁棒、以及更快收敛的理论证明。
- **模块化设计**：状态预测、基础预测器、在线更新均可替换，易于集成到现有 SDS 或其他离散状态模型中。
- **计算高效**：推理时间与 ACI 相当（约 5 分钟内），远优于需要重训练的 SPCI/HopCPT。
- **实验充分**：涵盖合成/真实、短/长、多类型变点、多种基线，并包含消融和鲁棒性分析。
- **定性可视化好**：图 1、图 3 直观展示了 CPTC 的适应性。

## 8. 不足与局限

- **依赖状态预测模型**：算法需要离散状态预测器（如 SDS），对非离散 SSM 或没有状态信息的时间序列不适用。此外，状态数量需预设，不准确会影响区间锐度（宽度）。
- **长序列适应性有限**：在长序列上，CPTC 的区间宽度不如 SPCI 和 HopCPT 窄，因为这些方法能通过频繁重训练学习更精细的残差模式。
- **理论假设**：渐近有效定理假设状态分布的平稳性（Assumption 1），虽常见但可能在某些极端非平稳场景被违反。
- **未考虑多步联合覆盖**：论文仅处理单步预测区间，未扩展到多步或路径覆盖（如 copula CP 等）。
- **实验覆盖**：虽然数据集多样，但未包含金融、医疗等高价值应用领域；状态预测模型固定为 RED-SDS，未探索其他 SDS 变体（如 RSLDS、G-SDS）对性能的影响。
- **公平性讨论**：论文未讨论方法可能带来的公平性或偏见问题（例如，如果状态识别存在偏差，对某些群体预测区间更宽）。
- **代码与可复现性**：虽然提供了 GitHub 仓库链接，但未说明许可证或详细运行环境配置。

（完）
