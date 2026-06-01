---
title: "MoFo: Empowering Long-term Time Series Forecasting with Periodic Pattern Modeling"
title_zh: "MoFo: 通过周期模式建模增强长期时间序列预测"
authors: "Jiaming Ma, Binwu Wang, Qihe Huang, Guanjun Wang, Pengkun Wang, Zhengyang Zhou, Yang Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=sbvLts2HqR"
tags: ["query:qf"]
score: 5.0
evidence: 长期时间序列预测，周期模式建模
tldr: 长期时间序列预测依赖周期模式。本文提出MoFo，通过周期结构patch和双视角建模（周期对齐相关性、周期偏移趋势），显著提升长程预测性能。为金融等具有周期性的时间序列预测提供了新方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbvlts2hqr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbvlts2hqr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1436, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbvlts2hqr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1461, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbvlts2hqr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbvlts2hqr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 257, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbvlts2hqr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1423, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbvlts2hqr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1433, \"height\": 2064, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbvlts2hqr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1308, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbvlts2hqr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 1059, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbvlts2hqr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbvlts2hqr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 1074, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbvlts2hqr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 739, \"height\": 250, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbvlts2hqr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 722, \"height\": 449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbvlts2hqr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1027, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbvlts2hqr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 740, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbvlts2hqr/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1447, \"height\": 508, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbvlts2hqr/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 741, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbvlts2hqr/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1444, \"height\": 415, \"label\": \"Table\"}]"
motivation: 现有模型无法有效捕捉时间序列中的稳定周期模式。
method: 设计周期结构patch，同时建模周期对齐和周期偏移的时序关系。
result: 在多个长程预测数据集上取得最佳结果，证明周期建模的有效性。
conclusion: 显式周期模式建模是提升长期预测能力的重要途径。
---

## Abstract
The stable periodic patterns present in the time series data serve as the foundation for long-term forecasting. However, existing models suffer from limitations such as continuous and chaotic input partitioning, as well as weak inductive biases, which restrict their ability to capture such recurring structures. In this paper, we propose MoFo, which interprets periodicity as both the correlation of period-aligned time steps and the trend of period-offset time steps. We first design period-structured patches—2D tensors generated through discrete sampling—where each row contains only period-aligned time steps, enabling direct modeling of periodic correlations. Period-offset time steps within a period are aligned in columns. To capture trends across these offset time steps, we introduce a period-aware modulator. This modulator introduces an adaptive strong inductive bias through a regulated relaxation function, encouraging the model to generate attention coefficients that align with periodic trends. This function is end-to-end trainable, enabling the model to adaptively capture the distinct periodic patterns across diverse datasets. Extensive empirical results on widely used benchmark datasets demonstrate that MoFo achieves competitive performance while maintaining high memory efficiency and fast training speed.

---

## 论文详细总结（自动生成）

# MoFo: 通过周期模式建模增强长期时间序列预测（NeurIPS 2025）——论文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究问题**：长期时间序列预测（LTSF）依赖数据中固有的稳定周期模式，但现有方法存在两大限制：
  - **连续但混乱的输入划分**：相邻时间步可能包含周期对齐和周期偏移的混合点，导致 patch 内部相关性混乱，难以学习周期结构。
  - **弱归纳偏置**：Transformer 的位置编码（如正弦编码或时间戳嵌入）无法有效体现周期性距离，导致模型对周期依赖的感知不足。
- **整体含义**：本文提出 MoFo（Modulator-Transformer），通过显式建模周期模式来提升长程预测精度和效率，为具有显著周期性的时间序列（如电力、交通、天气等）提供高效解决方案。

## 2. 方法论：核心思想、关键技术细节
### 2.1 核心思想
将周期模式分解为两个视角：
- **周期对齐时间步的相关性**：相同周期相位的时间步之间具有强相关。
- **周期偏移时间步的趋势**：同一周期内不同相位的时间步呈现连续变化趋势。

### 2.2 关键技术细节
#### a. 周期结构补丁（Period-structured Patch）
- **离散采样**：将输入序列 `X` 按周期长度 `P` 进行**离散采样**，构建 `P × ⌈T/P⌉` 的张量 `X_in`。
  - **每行**：包含所有周期中同一相位的时间步（周期对齐），用于建模周期性相关性。
  - **每列**：包含一个完整周期内所有相位的时间步（周期偏移），用于建模趋势。
- **填充策略**：当 `T` 不是 `P` 的整数倍时，从当前帧向前复制前一周期对应段，保证所有时间步都能参与计算，避免丢弃边界信息。

#### b. 周期感知调制器（Period-Aware Modulator）
- **相对周期距离矩阵**：定义时间步 `i` 与 `j` 的周期相对距离 `γ_ij = min((i-j) mod P, (j-i) mod P) ∈ [0, ⌊P/2⌋]`，确保周期临近的时间步距离小。
- **调制项**：使用**调节松弛函数（Regulated Relaxation Function, RRF）** 平滑近似阶跃函数：
  ```
  S(γ; α, β) = 1/(1+exp(α(γ-β))) + exp(-γ)/(1+exp(αβ))
  ```
  - **性质**：S(0)=1, S(∞)=0，连续可微，累积误差上界随 α → +∞ 趋近 0（见定理1证明）。
  - **参数 α, β 可学习**：α 控制衰减斜率，β 为距离惩罚阈值。
- **注意力机制**：将 `log S(Γ; α, β)` 加到注意力分数上，再经 Softmax：
  ```
  RRF(Q, K, V) = Softmax(QK^T/√d_h + log S(Γ; α, β)) V
  ```
  - 引入强归纳偏置：鼓励对齐周期趋势，同时解决自注意力的排列不变性问题。

#### c. 整体流程
1. 输入序列经周期结构补丁得到 `X_in ∈ R^{P × ⌈T/P⌉}`。
2. 通过线性层映射为 `Z ∈ R^{P × d}`。
3. 使用单层 Transformer（带 RRF 调制）处理 `Z`，输出 `Z̃`。
4. 展平并经输出线性层得到预测 `Ŷ ∈ R^L`。

- **独立通道学习**：多元时间序列中每个通道独立处理，并采用基于最大损失的自适应损失权重。

### 2.3 算法流程（文字描述）
1. 输入 `X ∈ R^T`，给定周期 `P`，计算填充后长度 `T' = P * ceil(T/P)`。
2. 按公式（1）填充得到 `X_pad`。
3. 通过周期对齐采样构造 `X_in ∈ R^{P × T'/P}`。
4. 线性嵌入 → Transformer（含 RRF 调制）→ 展平 → 线性输出 → 预测值。
5. 训练损失：L1 损失（FreDF 策略）+ 通道自适应权重。

## 3. 实验设计
### 3.1 数据集与场景
- **8 个真实世界数据集**：ETTh1, ETTh2, ETTm1, ETTm2（电力变压器温度）、Weather、Solar-Energy、Electricity、Traffic。
- **预测长度 L ∈ {96, 192, 336, 720}**，回视窗口 T ∈ {96, 336, 512}（取最优报告）。
- **额外测试**：非周期性数据集 ILI（流感样疾病）验证泛化能力。

### 3.2 基准方法
- 对比 **17 个基线**，包括：
  - 最新方法：DUET (2025), PDF (2024), iTransformer (2024), Pathformer (2024), CycleNet (2024), TimeMixer (2024)
  - 经典方法：PatchTST (2023), Crossformer (2023), DLinear (2023), FITS (2023), FiLM (2022), TimesNet (2023), FEDformer (2022), Informer (2021) 等。
- 评估指标：MSE 和 MAE。

### 3.3 实现平台
- 基于 **TFB 平台**（时间序列统一评估框架），确保公平比较。

## 4. 资源与算力
- **硬件**：NVIDIA A100 GPU（40GB 显存）。
- **未明确说明**：使用的 GPU 数量、总训练时长（仅给出了每个 epoch 的时间，如 Traffic L=720 时 MoFo 单 epoch 47 秒）。
- **参数规模**：MoFo 参数量仅 2.40M（Traffic 数据集），远低于多数 Transformer 基线。

## 5. 实验数量与充分性
### 5.1 实验组数
- **主实验**（Table 2）：覆盖 8 个数据集 × 4 个预测长度 = 32 个配置，与 10 个代表基线对比。
- **效率分析**（Table 3, 11）：对比 Transformer 基线的参数量、MACs、FLOPs、内存、训练时间。
- **超参数敏感性**：变换 Transformer 层数（1~6）和模型维度（8~304）。
- **消融实验**（Figure 4）：连续 patch、三种位置编码、移除 Modulator、损失函数等 5 种变体。
- **可扩展性**（Figure 5）：回视窗口从 96 扩展到 10000，监测内存、时间、FLOPs。
- **注意力可视化**（Figure 6）：4 个数据集上的注意力热图。
- **附录扩展实验**：
  - 与更多基线对比（10 个基线，Table 4）。
  - 非周期性数据集 ILI（Table 5）。
  - 填充策略消融（Table 6）。
  - 回视窗口敏感性（Table 7）。
  - 周期长度灵敏度（Table 8）、多周期混合实验（Table 9）、动态周期混合（Table 10）。
- **总计约 20+ 组实验**，覆盖性能、效率、鲁棒性、泛化性。

### 5.2 充分性与公平性
- **充分性**：实验设计全面，包含主结果、效率、消融、灵敏度、可扩展性、可视化等，论证充分。
- **公平性**：使用 TFB 平台统一设置，报告最优回视窗口下的结果，禁止“Drop Last”技巧。但未报告统计误差（如标准差或置信区间），存在一定偏差风险。

## 6. 主要结论与发现
1. **预测性能最优**：MoFo 在 8 个数据集、不同预测长度下，多数获得最佳或次优 MSE/MAE，尤其在长预测长度（720）上优势明显。
2. **效率极高**：复杂度仅与周期长度平方相关（P^2），与输入序列长度 T 无关。相比 PatchTST 等基线，参数量降低 90%+，训练加速 10~17 倍，内存节省 14 倍。
3. **消融验证关键设计**：移除 Modulator 或使用连续 patch 导致性能显著下降，证明周期结构补丁和周期感知调制器均不可或缺。
4. **可扩展性强**：回视窗口从 96 扩展到 10000 时，内存和训练时间增长极缓（<10%），适合超长序列。
5. **注意力对齐周期性**：可视化显示注意力权重随周期距离增大而递减，符合预期。

## 7. 优点
- **方法创新性**：提出周期结构补丁，将输入重塑为 2D 张量，分别建模周期对齐相关性和周期偏移趋势，思路新颖。
- **高效可学习调制器**：调节松弛函数（RRF）连续可微，参数 α、β 可自适应学习，避免了离散阶跃函数的不可导问题，且能逼近任意周期特性。
- **极低计算成本**：仅需单层 Transformer，复杂度不依赖序列长度，在大规模长序列场景下具有显著优势。
- **实验全面且多角度**：不仅提供主结果，还深入分析了效率、可扩展性、多周期、非周期情况，验证鲁棒性。
- **代码开源**：提供匿名代码仓库，便于复现。

## 8. 不足与局限
- **统计显著性缺失**：未报告误差条或置信区间，无法判断性能提升是否具有统计显著性。
- **周期已知假设**：需要预先指定或检测周期长度 P（通过 FFT 等），对无明显周期或多周期混合的数据集，依赖外部周期估计模块，可能引入误差。
- **注意力机制局限**：RRF 仅适用于标准二次复杂度自注意力，未扩展到线性注意力或稀疏注意力，限制了进一步加速的可能。
- **实验覆盖范围有限**：虽测试了非周期性数据（ILI），但缺乏对强噪声、缺失值、非平稳性等实际挑战的系统评估。
- **应用限制**：模型基于周期对齐假设，对于周期变化频繁或渐变的场景（如经济数据）可能不够鲁棒。
- **对比基线版本问题**：部分基线（如 CycleNet）在实验中的表现略差于 DLinear，可能与其实现或超参数选择有关，但论文未深入分析。

（完）
