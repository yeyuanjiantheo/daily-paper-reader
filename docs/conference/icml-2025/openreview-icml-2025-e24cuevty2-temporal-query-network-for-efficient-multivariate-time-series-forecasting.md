---
title: Temporal Query Network for Efficient Multivariate Time Series Forecasting
title_zh: 时序查询网络用于高效多变量时间序列预测
authors: "Shengsheng Lin, Haojun Chen, Haijie Wu, Chunyun Qiu, Weiwei Lin"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=e24CueVty2"
tags: ["query:qf"]
score: 7.0
evidence: 高效多变量时间序列预测方法
tldr: 针对多变量时间序列预测中变量间相关建模困难的问题，提出时序查询（TQ）技术，使用周期移位可学习向量作为注意力查询，从原始输入中提取键值，以单层注意力高效捕获全局跨变量模式，构建TQNet模型，在多个数据集上取得高效准确结果。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-e24cuevty2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 847, \"height\": 781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-e24cuevty2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1487, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-e24cuevty2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 784, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-e24cuevty2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1688, \"height\": 546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-e24cuevty2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1751, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-e24cuevty2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 852, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-e24cuevty2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1685, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-e24cuevty2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1495, \"height\": 434, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-e24cuevty2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 870, \"height\": 465, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-e24cuevty2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1782, \"height\": 533, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-e24cuevty2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 834, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-e24cuevty2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1775, \"height\": 638, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-e24cuevty2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1778, \"height\": 2173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-e24cuevty2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1779, \"height\": 633, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-e24cuevty2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 623, \"height\": 626, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-e24cuevty2/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 621, \"height\": 625, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-e24cuevty2/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1778, \"height\": 1670, \"label\": \"Table\"}]"
motivation: 现有模型难以有效捕获多变量间的全局相关模式。
method: 设计周期移位的可学习向量作为查询，结合单层注意力机制建模变量间相关。
result: 在多个基准上实现了高效且准确的预测性能。
conclusion: 提出的TQ技术可有效提升多变量时间序列预测的效率与准确性。
---

## Abstract
Sufficiently modeling the correlations among variables (aka channels) is crucial for achieving accurate multivariate time series forecasting (MTSF). In this paper, we propose a novel technique called Temporal Query (TQ) to more effectively capture multivariate correlations, thereby improving model performance in MTSF tasks. Technically, the TQ technique employs periodically shifted learnable vectors as queries in the attention mechanism to capture global inter-variable patterns, while the keys and values are derived from the raw input data to encode local, sample-level correlations. Building upon the TQ technique, we develop a simple yet efficient model named Temporal Query Network (TQNet), which employs only a single-layer attention mechanism and a lightweight multi-layer perceptron (MLP). Extensive experiments demonstrate that TQNet learns more robust multivariate correlations, achieving state-of-the-art forecasting accuracy across 12 challenging real-world datasets. Furthermore, TQNet achieves high efficiency comparable to linear-based methods even on high-dimensional datasets, balancing performance and computational cost. The code is available at: https://github.com/ACAT-SCUT/TQNet.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：多变量时间序列预测（MTSF）中，准确建模变量（通道）间的相关性至关重要，但现实数据常受非平稳扰动（如极端值、缺失值、噪声）影响，导致单个样本中观测到的局部相关性与全局（数据集级）相关性存在显著偏差，难以稳定捕获鲁棒的跨变量模式。
- **动机**：现有方法（如 iTransformer 采用完全自注意力）依赖样本自身的输入生成查询和键值，易受干扰；而通道独立（CI）方法则完全忽略变量间关系，成为性能瓶颈。需一种机制有效融合全局先验与局部信息，提升相关建模的鲁棒性。
- **含义**：提出 Temporal Query (TQ) 技术，通过周期移位的可学习向量作为注意力查询，以全局稳定的先验指导注意力，集成全局与局部相关，从而在轻量级架构下实现高效且精准的预测。

## 2. 方法论

### 核心思想
- 利用周期移位的可学习参数向量作为注意力机制的查询（Query），从原始输入序列中提取键（Key）和值（Value），使得注意力分数既能体现全局稳定模式（来自 TQ），又能保留样本特定的局部信息（来自原始数据）。

### 关键技术细节
1. **Temporal Query (TQ) 技术**
   - 初始化可学习参数矩阵 θ_TQ ∈ ℝ^{C×W}，W 为数据集稳定周期长度（例如周、日）。
   - 对于时间步 t，动态提取 θ_TQ 中的一个长度为 L 的段 θ_t, L_TQ，起始索引为 `t mod W`，实现周期性复用。
   - 公式：θ_t, L_TQ = θ_(t+i·W), L_TQ（同一周期内样本共享查询）。

2. **TQ-Enhanced Multi-Head Attention (TQ-MHA)**
   - 对于每个注意力头 h：
     - Q_h = θ_t, L_TQ × W_Q_h
     - K_h = X_t × W_K_h
     - V_h = X_t × W_V_h
     - 注意力计算：Head_h = Softmax( (Q_h K_h^T) / √L ) × V_h
   - 多头输出拼接后经输出投影矩阵 W_O 得到最终注意力结果。

3. **整体模型结构 TQNet**
   - 输入：X_t ∈ ℝ^{C×L}
   - 步骤：
     - 可选实例归一化（IN）去除分布漂移。
     - **单层 TQ-MHA** + 残差连接 → h_attn。
     - **轻量 MLP**（两层全连接 + GeLU 激活）+ 残差连接 → h_mlp。
     - **输出投影**：线性层 + Dropout → 预测 Ŷ_t ∈ ℝ^{C×H}。
     - 若使用 IN，则反归一化恢复尺度。
   - 注：仅单层注意力 + 单层 MLP，结构极为简洁。

4. **超参数 W 确定**
   - 通过先验知识（如数据周期）或自相关函数（ACF）计算。建议选择最长稳定周期（如周长度），以隐式包含子周期。

## 3. 实验设计

### 数据集
- 共 **12 个真实世界数据集**：
  - **ETT 系列**（ETTh1, ETTh2, ETTm1, ETTm2）：7 通道，电力温度数据。
  - **Electricity**（321 通道）、**Solar**（137 通道）、**Traffic**（862 通道）、**Weather**（21 通道）。
  - **PEMS 系列**（PEMS03, PEMS04, PEMS07, PEMS08）：交通流量数据，通道数 170～883。
- 涵盖不同尺度、维度、频率和领域。

### 基准方法
- 对比方法包括：TimeXer, CycleNet, iTransformer, MSGNet, TimesNet, PatchTST, Crossformer, DLinear, SCINet。
- 主要采用 **MSE** 和 **MAE** 作为评估指标。

### 训练/验证/测试划分
- 遵循 iTransformer 和 TimesNet 的设定：ETT 和 PEMS 采用 6:2:2 划分，其余采用 7:1:2 划分。

## 4. 资源与算力

- 文中明确提及：
  - 使用 **单张 NVIDIA GeForce RTX 4090 GPU（24 GB 显存）** 进行所有实验。
  - 模型训练使用 Adam 优化器，L2 损失，30 个 epoch，早停 patience=5。
  - 学习率：大尺度数据集 3×10⁻³，小尺度（ETT 系列）1×10⁻³。
  - 批大小根据数据集规模调整（如 Traffic 为 16，Weather 为 64）。
- 未给出具体训练时间数值（除效率分析中约 20~50 秒/epoch 外），但强调 TQNet 在 1000 通道以下可接近线性模型的效率。

## 5. 实验数量与充分性

- **主实验**：12 个数据集 × 4 个预测长度（96,192,336,720）→ 48 组对比，报告 MSE/MAE，TQNet 在 22/24 指标中进入 Top-2。
- **消融实验**：
  - TQ-MHA 中 Q/K 来源的三种配置对比。
  - TQNet 组件移除（TQ、MHA、两者同去）。
- **集成实验**：将 TQ 技术插入 iTransformer、PatchTST、DLinear 中测试性能提升。
- **表示学习分析**：t-SNE 可视化 TQ 表征与通道模式对应关系。
- **依赖研究**：多变量到单变量预测中逐步增加协变量数量的效果。
- **超参数 W 影响**：在 Electricity 数据集上测试不同 W 值。
- **效率分析**：参数规模、训练时间随通道数变化的基准。
- **额外附录实验**：多组随机种子/学习率的稳定性、不同回看长度的影响、多层堆叠对比、与 ETS 比较、多变量到单变量预测对比等。
- **总体评价**：实验设计全面，包含主要性能对比、消融、可迁移性、鲁棒性、效率等多个维度，对比方法均为近年代表性工作，设置公平（固定回看长度 96，统一基准）。实验充分且客观。

## 6. 主要结论与发现

- **TQ 技术有效捕获全局相关模式**，其 t-SNE 可视化显示接近的通道具有相似的序列模式，且能够对周期样本平均化噪声，增强鲁棒性。
- **TQNet 在 12 个数据集上整体达到 SOTA**，尤其在通道数高（如 Traffic 862 通道）的数据集上优势明显，22/24 指标 Top-2。
- **单层注意力+单层 MLP 的轻量架构已足够**，堆叠更多层未带来显著增益（PEMS 上有微小改善）。
- **TQ 技术具有良好的可迁移性**：集成到 iTransformer、PatchTST、DLinear 中均能提升原模型性能。
- **超参数 W 需匹配数据最大周期性**（如周长度），倍频设定仍有效；非周期对齐的 W 会下降，但最差情况（如 W=1）仍优于不加 TQ，体现鲁棒性。
- **计算效率接近线性方法**（DLinear），参数规模和训练时间远低于其他 Transformer/CD 方法，在 1000 通道以下保持实用。

## 7. 优点

- **方法创新强**：将可学习周期移位向量作为注意力查询，巧妙融合全局先验与局部信息，简洁而有效。
- **架构极简**：单层注意力 + 单层 MLP，性能却超越多层复杂模型，证明了高效设计潜力。
- **可迁移性**：TQ 技术可作为即插即用模块提升多种现有模型，通用性强。
- **实验扎实**：覆盖多领域、多维度、多预测长度的广泛基准，并提供丰富的消融、鲁棒性、效率分析，结果可靠。
- **可解释性**：t-SNE 可视化显示 TQ 学到的表征与原始通道模式关联，有助于理解模型行为。
- **效率突出**：在保持 SOTA 精度的同时，训练开销极低，适合实际部署。

## 8. 不足与局限

- **依赖周期先验**：W 需根据数据周期预设，若数据缺乏清晰周期性（如不规则振荡），可能导致性能下降或需额外调参。
- **单周期假设**：当存在多个不重叠的周期（如周和月重叠但周期长度非整数倍）时，单一 W 难以同时覆盖，文中仅提出简单折衷或集成方案，未深入解决。
- **弱相关场景**：若变量间关联本身微弱，强制建模可能引入噪声、降低性能。
- **长回看窗口的边际效益下降**：如图 8 所示，当回看长度足够长时，所有方法差距缩小，说明长时序可部分替代多变量信息，但长窗口也带来过拟合风险。
- **注意力复杂度**：虽然因轻量设计在 C<1000 时接近线性，但理论上仍为二次复杂度，在超大规模通道（如万级）时可能成为瓶颈。
- **实验缺失国际标准数据集**：如 M4、M5 等常规竞争，但文中选用 12 个真实基准已具代表性。

（完）
