---
title: "AliO: Output Alignment Matters in Long-Term Time Series Forecasting"
title_zh: AliO：长期时间序列预测中的输出对齐至关重要
authors: "Kwangryeol Park, Jaeho Kim, Seulki Lee"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=AuOZDp4gy7"
tags: ["query:qf"]
score: 5.0
evidence: 长期时间序列预测的输出对齐方法
tldr: AliO 针对长期时间序列预测中相同时间戳跨滞后输入输出不一致的问题，提出对齐方法降低预测波动。该方法提升了模型可靠性，可应用于金融时序预测的稳定性增强。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 773, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 237, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 339, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 618, \"height\": 312, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 674, \"height\": 244, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 689, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 748, \"height\": 248, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 699, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1292, \"height\": 805, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1295, \"height\": 806, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1298, \"height\": 814, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1301, \"height\": 815, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1173, \"height\": 1186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 704, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 704, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 684, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 703, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 684, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 684, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 683, \"height\": 307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 684, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 704, \"height\": 307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 682, \"height\": 307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 703, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-auozdp4gy7/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 683, \"height\": 309, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 849, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 563, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 839, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1444, \"height\": 766, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1397, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1370, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1365, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1480, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1534, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1531, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1034, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1371, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1213, \"height\": 2244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 703, \"height\": 2288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 925, \"height\": 2189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 880, \"height\": 2253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 927, \"height\": 2207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 707, \"height\": 2245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1050, \"height\": 2227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 880, \"height\": 2248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 970, \"height\": 2226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 938, \"height\": 2212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 700, \"height\": 2273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1067, \"height\": 2222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 707, \"height\": 2240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 925, \"height\": 2184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-auozdp4gy7/table-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 709, \"height\": 2246, \"label\": \"Table\"}]"
motivation: 现有长期预测模型在相同时间戳上输出不一致，影响可靠性。
method: 设计输出对齐损失，减少同一时间戳不同输入下的预测差异。
result: 在多个长期预测数据集上提升了输出一致性与预测精度。
conclusion: 输出对齐是提升长时预测可靠性的重要因素。
---

## Abstract
Long-term Time Series Forecasting (LTSF) tasks, which leverage the current data sequence as input to predict the future sequence, have become increasingly crucial in real-world applications such as weather forecasting and planning of electricity consumption. However, state-of-the-art LTSF models often fail to achieve prediction output alignment for the same timestamps across lagged input sequences. Instead, these models exhibit low output alignment, resulting in fluctuation in prediction outputs for the same timestamps, undermining the model's reliability. To address this, we propose AliO (Align Outputs), a novel approach designed to improve the output alignment of LTSF models by reducing the discrepancies between prediction outputs for the same timestamps in both the time and frequency domains. To measure output alignment, we introduce a new metric, TAM (Time Alignment Metric), which quantifies the alignment between prediction outputs, whereas existing metrics such as MSE only capture the distance between prediction outputs and ground truths. Experimental results show that AliO effectively improves the output alignment, i.e., up to 58.2\% in TAM, while maintaining or enhancing the forecasting performance (up to 27.5\%). This improved output alignment increases the reliability of the LTSF models, making them more applicable in real-world scenarios. The code implementation is on an anonymous GitHub repository.

---

## 论文详细总结（自动生成）

# 长期时间序列预测中的输出对齐：AliO 方法详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题背景**：长期时间序列预测（LTSF）在电力需求预测、天气预报等领域至关重要。现有最优模型（如 Autoformer、iTransformer、PatchTST 等）通常只关注最小化预测值与真实值之间的误差（如 MSE），却忽略了**跨滞后输入序列的预测输出一致性**问题。
- **核心问题**：当使用具有部分重叠的时间窗口的滞后输入序列进行预测时，同一时间戳的预测结果往往不一致，即**输出对齐（Output Alignment）差**。例如，用电预测中，不同月份输入的预测在重叠月份出现波动，导致预算重排和资源浪费。
- **重要性**：低一致性会降低用户信任、增加规划和决策成本（如沉没成本、机会成本）。现有研究未充分认识和解决这一问题。
- **目标**：本文首次提出提升输出对齐的方法 AliO，并引入量化指标 TAM，同时保持或提升预测准确率。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
AliO 通过最小化**多个滞后输入预测在重叠时间戳上的差异**来实现输出对齐，同时在时间和频率两个域中进行对齐，并采用**回归拉动（Regression Pulling）** 技术保持回归性能。

### 关键技术细节

#### (1) 时间对齐指标（TAM）
- 用于量化输出对齐程度，计算多个重叠输出序列之间所有两两 MAE 的平均值。
- 定义：给定 N 个重叠输出序列 Pⁿ（长度 h′），TAM_N = 所有对 (Pⁿ, Pᵐ) 的 MAE 的平均值。
- 优点：能评估预测之间的一致性，而传统指标（MSE、MAE）仅衡量预测与真实值的距离。

#### (2) AliO 算法流程（Algorithm 1）
- 输入：N 个连续预测 Yⁿ（时间滞后 l）及其真实值 Ŷⁿ。
- 对每对预测 (n, m)：
  - 提取重叠部分 Pⁿ_T、Pᵐ_T 和对应真实值 GT_T。
  - **时间域对齐**：计算每个时间点上哪个预测离真实值更远（idx_T），对更远的点使用 stop-gradient 操作，使其向另一个预测靠拢（Regression Pulling），从而保持回归方向。
  - **频率域对齐**：将时间域信号通过 FFT 变换到频域，同样计算 idx_F 并应用回归拉动，对齐相位和幅度。
- 损失函数：L_AliO = λ_T * L_T + λ_F * L_F，与回归损失 L_reg 相加得到总损失 L_total。
- 距离函数：时间和频率域均采用 MSE。

#### (3) 回归拉动（Regression Pulling）
- 对于重叠部分的每个时间点，比较两个预测与真实值的距离；将较远的那个预测“拉向”较近的那一个（通过 stop-gradient 固定较近的预测），从而既保持回归损失方向又减少预测间差异。

#### (4) 频率域对齐的理论保证
- Theorem 4.1：最小化频域 MSE 会减小相位差。
- Theorem 4.2：相位对齐后，最小化频域 MSE 会减小幅度差。

## 3. 实验设计

### 使用的数据集
- **主要数据集**（7个）：ETTh1、ETTh2、ETTm1、ETTm2、Electricity (ECL)、Traffic、Weather。
- **额外数据集**：ILI（流感样疾病）、Exchange Rate、Solar、PEMS03/04/07/08。
- **数据特点**：涵盖温度、电力、交通、天气、健康、经济、能源等多个领域；采样频率从分钟级到周级。

### Benchmark 设置
- 预测长度：一般为 {96, 192, 336, 720}，ILI 为 {24, 36, 48, 60}，PEMS 为 {12, 24, 48, 96}，Autoformer 在 ETT 上使用 {24, 48, 168, 336, 720}。
- 上下文长度：不同模型按官方设置（如 PatchTST 和 DLinear 为 336，其余为 96；ILI 上特殊处理）。
- 评估指标：MSE、TAM、MAE、MAPE、RMSE。

### 对比的方法（baselines）
- **7 种模型**：Autoformer、DLinear、PatchTST、TimesNet、iTransformer、GPT4TS、CycleNet。
- 覆盖：Transformer 类、线性类、CNN 类、LLM 类模型。

### 对比方式
- 每个模型在基线（仅使用 MSE 回归损失）和加入 AliO 后进行比较，报告 MSE 和 TAM 的平均性能（多次随机种子）。

## 4. 资源与算力

- 文中明确说明：所有实验在 **NVIDIA RTX 3090 和 A6000 GPU** 上运行。
- 同一模型在同一 GPU 上比较基线和 AliO 以保证公平。
- 未给出具体训练总时长或 GPU 数量，仅提到使用官方默认超参数、Adam 优化器。

## 5. 实验数量与充分性

- **实验数量**：涵盖 7 个主要数据集 × 7 种模型 × 多个预测长度，加上额外数据集（ILI、Exchange、Solar、PEMS）的验证，每组实验使用 3 个随机种子取平均值和标准差，报告了标准偏差。
- **超参数分析**：对时间系数 λ_T（{1.0, 2.0, 5.0}）和频率系数 λ_F（{0.0, 0.5, 1.0, 2.0}）进行了热力图分析；对重叠预测数量 N 和滞后 l 进行了分析；还研究了 λ_T=0 的情况。
- **消融与可视化**：在多个模型上可视化预测结果与频域对齐效果。
- **公平性**：采用官方代码、相同超参数、相同随机种子；使用 AWL 自动调优系数并报告最佳结果。
- **充分性**：实验规模较大，涵盖了多领域、多模型、多指标，且进行了参数敏感性分析，但缺乏在极端噪声或非平稳序列上的额外验证（已在局限部分提及）。

## 6. 主要结论与发现

- AliO 显著提升输出对齐：TAM 最高提升 58.2%，平均提升约 20-40%。
- 同时，预测性能（MSE）保持或提升：最高提升 27.5%（在 ILI 数据集上达 17.4%），且初始对齐越差，MSE 提升越明显（相关系数 0.33）。
- 时间域系数 λ_T 越大，TAM 改善越明显；频率域系数 λ_F 在 λ_T 不足时提供补充效果。
- 较小的滞后 l 和较多的重叠序列数 N 有利于 TAM 改进，但过大窗口可能导致 MSE 下降。
- 可视化证实：AliO 减少了时间域预测漂移，且对齐了频域相位和幅度。

## 7. 优点

- **新颖性**：首次明确识别并解决 LTSF 中的输出对齐问题，提出新指标 TAM 和通用方法 AliO。
- **通用性**：可作为损失函数附加到任意 LTSF 模型上，无需修改模型架构，且不增加推理复杂度。
- **理论支撑**：证明了频率域对齐对相位和幅度的一致性作用。
- **验证充分**：覆盖 7 种主流模型、多个领域数据集、多次随机种子和标准偏差报告，并进行了超参数分析和可视化。
- **实用价值**：提升模型可靠性，对需要滚动预测的实际场景（如预算规划、资源调度）具有显著经济意义。

## 8. 不足与局限

- **对波动性数据的应用需谨慎**：TAM 假设预测序列相对稳定，对于受突发外部冲击的高度波动数据集（如汇率），其有效性可能受限。但文中在 Exchange Rate 上的结果仍显示一定潜力。
- **距离函数局限**：AliO 目前使用 MSE 作为距离函数，未来可探索形状感知的距离（如 DTW、Soft-DTW）以进一步提升性能。
- **超参数敏感**：λ_T 和 λ_F 需手动搜索（文中使用 AWL 自动调参，但搜索范围有限），可能在不同任务上需调整。
- **实验未覆盖极端非平稳场景**：未在突变事件、异常点或领域偏移场景下充分测试（文中在局限性部分提及）。
- **计算开销**：虽然方法简便，但需要同时计算多个滞后预测，可能增加训练时间（文中未量化）。

（完）
