---
title: "TimePro: Efficient Multivariate Long-term Time Series Forecasting with Variable- and Time-Aware Hyper-state"
title_zh: TimePro：基于变量和时间感知超状态的高效多变量长期时间序列预测
authors: "Xiaowen Ma, Zhen-Liang Ni, Shuai Xiao, Xinghao Chen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=s69Ei2VrIW"
tags: ["query:qf"]
score: 5.0
evidence: 多变量时间序列预测，具有变量和时间感知，可应用于金融波动率建模
tldr: 长期时间序列预测中不同变量对目标的影响时间滞后不同（多延迟问题）。本文提出TimePro，基于Mamba模型构建变量和时间感知的超状态，保留每个变量令牌的细粒度时序特征，并自适应选择关注时间点。实验表明TimePro在长期预测任务上优于先前方法。该框架可迁移至金融多变量波动率预测场景。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-s69ei2vriw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 573, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s69ei2vriw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 931, \"height\": 567, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s69ei2vriw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1668, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s69ei2vriw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1693, \"height\": 785, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s69ei2vriw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1423, \"height\": 998, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s69ei2vriw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1734, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s69ei2vriw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1744, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s69ei2vriw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1708, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s69ei2vriw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1713, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s69ei2vriw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1421, \"height\": 1173, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s69ei2vriw/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1596, \"height\": 614, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-s69ei2vriw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 99, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s69ei2vriw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1758, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s69ei2vriw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 611, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s69ei2vriw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 773, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s69ei2vriw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1773, \"height\": 439, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s69ei2vriw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1767, \"height\": 1054, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s69ei2vriw/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1247, \"height\": 341, \"label\": \"Table\"}]"
motivation: 多变量长期预测中不同变量对目标的影响存在不同时间延迟，现有统一处理方法效果有限。
method: 基于Mamba设计变量和时间感知的超状态，保留变量级细粒度时间特征并自适应选择关注点。
result: 在多个长期预测数据集上，TimePro的预测误差低于现有基线。
conclusion: TimePro有效解决了多延迟问题，为多变量时间序列预测提供了新思路。
---

## Abstract
In long-term time series forecasting, different variables often influence the target variable over distinct time intervals, a challenge known as the multi-delay issue. Traditional models typically process all variables or time points uniformly, which limits their ability to capture complex variable relationships and obtain non-trivial time representations. To address this issue, we propose TimePro, an innovative Mamba-based model that constructs variate- and time-aware hyper-states. Unlike conventional approaches that merely transfer plain states across variable or time dimensions, TimePro preserves the fine-grained temporal features of each variate token and adaptively selects the focused time points to tune the plain state. The reconstructed hyper-state can perceive both variable relationships and salient temporal information, which helps the model make accurate forecasting. In experiments, TimePro performs competitively on eight real-world long-term forecasting benchmarks with satisfactory linear complexity. Code is available at https://github.com/xwmaxwma/TimePro.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
多变量长期时间序列预测中存在“多延迟问题”（multi-delay issue）：不同变量对目标变量的影响具有不同的时间滞后，传统方法（如 Transformer、Mamba）对所有变量或时间点进行统一处理，难以捕捉复杂的变量间关系和非平凡的时间表示。为此，本文提出 TimePro——一种基于 Mamba 的创新模型，通过构建“变量-时间感知的超状态”（variate- and time-aware hyper-state）来同时捕捉变量依赖和关键时间信息，从而解决多延迟问题。

## 2. 方法论
### 核心思想
保持每个变量令牌（variate token）的细粒度时间特征，自适应地选择关键时间点来调整普通隐藏状态，重构得到超状态，该超状态既感知变量关系又感知显著时间信息。

### 关键技术细节
- **嵌入层**：对每个变量独立进行 Patch 嵌入（可重叠），保留变量维度，得到 \(E_0 \in \mathbb{R}^{N \times P \times D}\)（N 变量数，P 补丁数，D 特征维）。
- **ProBlock 模块**：多个级联的 ProBlock，每个包含 HyperMamba 和 TimeFFN。
  - **HyperMamba**：核心创新。先沿变量维度进行双向扫描（通道分裂后反向扫描）得到普通隐藏状态 \(h\)。然后通过“时间调谐”（time tune）策略：对状态重塑恢复细粒度时间维，用卷积学习偏移量 \(\delta h\)，通过线性插值从参考点采样 \(M\) 个关键时间点，再线性融合得到超状态 \(h_o\)。最后用门控机制（SiLU）输出。
  - **硬件感知实现**：在 GPU SRAM 中执行扫描，减少 HBM 读写。
  - **简化结构**：与原 Mamba 相比，去掉了深度卷积和扫描后的线性投影（消融验证无效），并加入了双向扫描。
- **复杂度**：时间复杂度 \(O(NL)\)（N 变量数，L 序列长度），对比 iTransformer \(O(N^2+NL)\)、PatchTST \(O(NL^2)\)。

### 算法流程（文字说明）
1. 输入 \(X \in \mathbb{R}^{N \times L}\)，使用 RevIN 进行归一化。
2. 对每个变量进行 Patch 嵌入，得到 \(E_0\)。
3. 对 \(E_0\) 通过 \(\gamma\) 层 ProBlock，每层内先 HyperMamba 进行变量交互和时间调谐，再 TimeFFN 进行时间特征变换。
4. 最后一层输出经展平后通过线性投影得到预测 \(Y \in \mathbb{R}^{N \times H}\)，再 RevIN 反归一化。

## 3. 实验设计
- **数据集**：8 个真实世界长期预测基准：ETTh1、ETTh2、ETTm1、ETTm2（电力变压器温度）、Exchange（汇率）、Electricity（电力消耗）、Weather（天气）、Solar-Energy（太阳能）。
- **设置**：回溯窗口 \(L=96\)，预测长度 \(H \in \{96,192,336,720\}\)。指标为 MSE 和 MAE。
- **对比方法**：10 种 SOTA 方法：S-Mamba、SOFTS、iTransformer、PatchTST、Crossformer、TiDE、TimesNet、DLinear、SCINet、Stationary（基于非平稳 Transformer）。
- **额外分析**：不同回溯窗口（48/96/192/336）实验、不同变量通道数下的效率分析。

## 4. 资源与算力
- **GPU 数量与型号**：4 块 NVIDIA Tesla V100，每块 32 GB VRAM。
- **优化器**：ADAM，初始学习率 5e-4，余弦退火。
- **训练时长**：论文未明确给出总训练时间或每轮时间。

## 5. 实验数量与充分性
- **主实验**：8 个数据集 × 4 个预测长度 = 32 组结果（Table 2 展示平均，Table 6 展示全量）。TimePro 在 16 个平均指标中取得 12 个第一、2 个第二。
- **消融实验**：共 6 组：
  - 特征维度 D（32/48/64/96）
  - 编码器层数（1~4）
  - Patch 长度（8/16/32）
  - 时间调谐设计（自适应 vs 非自适应线性）
  - HyperMamba 结构（移除 DWConv、线性层）
  - Hyper-Scan 设计（仅变量维、仅时间维、变量+时间、自适应）
- **可视化分析**：多变量相关性分析（Pearson）、预测曲线对比（ETTh2、ECL）、不同扫描设计的预测对比。
- **效率对比**：参数、FLOPs、内存、训练/推理时间（V100 上）。
- **充分性**：实验覆盖多个数据集、多种设置、模型变体，对比方法全面，消融设计合理，结论可靠。

## 6. 主要结论与发现
- TimePro 在大部分数据集上超越现有 SOTA，尤其在 ECL、Exchange、Weather、ETTm1/2 上表现突出。
- 自适应时间调谐策略能有效缓解多延迟问题，使学习到的变量相关性更接近真实标签。
- HyperMamba 相比原始 Mamba 去除冗余组件后性能更好，效率更高。
- 模型复杂度为线性 \(O(NL)\)，在实际部署中参数少、FLOPs 低、训练/推理速度快。

## 7. 优点
- **方法创新**：首次将时间调谐（可变形时间采样）引入状态空间模型，实现了变量和时间信息的联合感知。
- **高效性**：保持 Mamba 的线性复杂度，同时通过结构精简进一步降低开销，适用于资源受限场景。
- **实验扎实**：在 8 个多样化数据集上系统评估，包含充分消融、可视化和效率对比，验证了各模块的有效性。
- **代码开源**：提供 GitHub 仓库，便于复现和扩展。

## 8. 不足与局限
- **数据集覆盖有限**：未在金融、交通、工业等典型领域数据集（如 Traffic、ILI）上验证。
- **Solar-Energy 上未达最佳**：SOFTS 在该数据集上的 MSE/MAE 略低于 TimePro（0.229 vs 0.232），表明模型对某些数据模式可能不是最优。
- **超参数敏感性**：Patch 长度、特征维度等对性能影响因数据集而异，缺乏自动调参或通用方案。
- **仅面向长期预测**：未评估短期预测（H<96）或滚动预测场景，通用性有待扩展。
- **未讨论分布偏移**：虽然使用了 RevIN，但未深入分析非平稳性或多延迟对训练稳定性的影响。
- **理论分析薄弱**：对多延迟问题的形式化定义和求解保证缺乏严格推导。

（完）
