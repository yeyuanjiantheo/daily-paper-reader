---
title: How Different from the Past? Spatio-Temporal Time Series Forecasting with Self-Supervised Deviation Learning
title_zh: 与过去有何不同？基于自监督偏差学习的时空时间序列预测
authors: "Haotian Gao, Zheng Dong, Jiawei Yong, Shintaro Fukushima, Kenjiro Taura, Renhe Jiang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=TgGH1bY6kl"
tags: ["query:qf"]
score: 4.0
evidence: 自监督偏差学习方法用于时间序列预测
tldr: 现有时空预测方法常忽略当前输入与历史模式之间的动态偏差，而这些偏差包含重要信号。本文提出ST-SSDL框架，通过自监督学习将每个输入锚定到历史平均值，并对偏差部分进行离散化建模。在交通和城市数据上验证了有效性。该方法的偏差学习机制可直接迁移至金融时间序列波动率预测，以捕捉市场状态突变。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-tggh1by6kl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 687, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tggh1by6kl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tggh1by6kl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1289, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tggh1by6kl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 790, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tggh1by6kl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 662, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tggh1by6kl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 890, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tggh1by6kl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1442, \"height\": 717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tggh1by6kl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 721, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tggh1by6kl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1443, \"height\": 716, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tggh1by6kl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1444, \"height\": 721, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-tggh1by6kl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 941, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tggh1by6kl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1453, \"height\": 1017, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tggh1by6kl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1455, \"height\": 358, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tggh1by6kl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1414, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tggh1by6kl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1263, \"height\": 1076, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tggh1by6kl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1351, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tggh1by6kl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1461, \"height\": 1144, \"label\": \"Table\"}]"
motivation: 时空预测中动态偏差包含关键信号，但现有方法未充分利用。
method: 提出ST-SSDL框架，通过自监督偏差学习将输入与历史平均的差异离散化并建模。
result: 在多个时空数据集上预测精度优于基线。
conclusion: 为时间序列预测引入了一种新颖的偏差感知范式。
---

## Abstract
Spatio-temporal forecasting is essential for real-world applications such as traffic management and urban computing. Although recent methods have shown improved accuracy, they often fail to account for dynamic deviations between current inputs and historical patterns. These deviations contain critical signals that can significantly affect model performance. To fill this gap, we propose $\textbf{ST-SSDL}$, a $\underline{S}$patio-$\underline{T}$emporal time series forecasting framework that incorporates a $\underline{S}$elf-$\underline{S}$upervised $\underline{D}$eviation $\underline{L}$earning scheme to capture and utilize such deviations. ST-SSDL anchors each input to its historical average and discretizes the latent space using learnable prototypes that represent typical spatio-temporal patterns. Two auxiliary objectives are proposed to refine this structure: a contrastive loss that enhances inter-prototype discriminability and a deviation loss that regularizes the distance consistency between input representations and corresponding prototypes to quantify deviation. Optimized jointly with the forecasting objective, these components guide the model to organize its hidden space and improve generalization across diverse input conditions. Experiments on six benchmark datasets show that ST-SSDL consistently outperforms state-of-the-art baselines across multiple metrics. Visualizations further demonstrate its ability to adaptively respond to varying levels of deviation in complex spatio-temporal scenarios. Our code and datasets are available at https://github.com/Jimmy-7664/ST-SSDL.

---

## 论文详细总结（自动生成）

## 论文中文总结

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：现有时空预测方法（如交通流量预测）通常只建模当前输入到未来的映射，忽略了当前观测与历史模式之间的**动态偏差**。这种偏差（如事故、特殊事件导致的模式突变）包含对预测至关重要的信号，但传统方法仅使用固定时间偏移（如同一天同一时刻）无法动态捕捉。
- **整体含义**：本文提出一种自监督偏差学习框架 ST-SSDL，首次将当前输入与历史平均值的差异作为显式特征进行建模，从而提升模型对不同时空背景下偏差的适应性和预测精度。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：引入 **相对距离一致性** 原则——物理空间中相近的当前-历史输入对，在潜在空间中也应相近；物理空间中较远的对，在潜在空间中也应较远。通过可学习原型离散化潜在空间，并利用两个自监督损失实现偏差的量化与利用。
- **关键技术细节**：
  - **历史作为自监督锚点**：将训练序列按周分割，计算每周对应的历史平均作为锚点 `Xa`，与当前输入 `Xc` 一起通过共享编码器（GCRU）得到隐表示 `Hc, Ha`。
  - **空间离散化**：使用 `M` 个可学习原型 `P` 代表典型时空模式。通过查询-原型注意力（公式3）得到每个输入对应原型的权重，并选取最相关（正样本）和第二相关（负样本）原型。
  - **对比损失** `LCon`（公式4）：基于三元组损失，拉近当前查询与正原型，推远与负原型，增强原型间可分性。
  - **偏差损失** `LDev`（公式5）：最小化物理空间距离（`|Qc - Qa|`）与潜在空间距离（通过原型距离 `|Pc - Pa|` 近似）之间的差异，强制相对距离一致性。
  - **预测目标**：使用 GCRU 编码器-解码器架构，将 `Hc, Ha` 及其增强表示（通过注意力加权原型）拼接后生成自适应邻接矩阵，用于解码预测未来序列。
  - **总损失**：`L = L_MAE + λ_Con·L_Con + λ_Dev·L_Dev`，联合优化。
- **公式/算法流程**：使用停止梯度操作 `sg()` 防止模型崩塌，确保原型学习到有意义的分布。

### 3. 实验设计
- **数据集**：6个标准时空预测基准：
  - 交通速度：METRLA（207传感器）、PEMSBAY（325）、PEMSD7(M)（228）
  - 交通流量：PEMS04（307）、PEMS07（883）、PEMS08（170）
  - 时间分辨率均为5分钟，输入/预测窗均为12步（1小时）。
- **基准与对比方法**：包括 HI（统计）、GRU（时序）、以及11种时空模型（STGCN, DCRNN, Graph WaveNet, MTGNN, AGCRN, GTS, STNorm, STID, ST-WA, MegaCRN, STDN）。
- **评估指标**：MAE、RMSE、MAPE。

### 4. 资源与算力
- **GPU 型号**：NVIDIA RTX 5000 Ada Generation（文中提及）。
- **GPU 数量**：未明确说明，但推测为单卡或少量卡（基于实验在“常规计算服务器”上进行）。
- **训练时长**：效率表给出了每个 epoch 的训练时间（如 METRLA 上 71.84s），但未报告总 epoch 数或总训练时间。推理时间也给出（如 PEMS07 上 217.80s），但未明确说明总算力开销。
- **备注**：论文未提供完整的算力统计（如总 GPU 小时数），仅给出相对效率对比。

### 5. 实验数量与充分性
- **实验数量充足**：
  - 主性能对比表（表2）：覆盖6个数据集，每个数据集报告3个时间步或平均结果，共16个对比方法。
  - 消融实验（表3）：5个变体（去除 LCon、LDev、两者、整个SSDL、朴素版本），在6个数据集上验证。
  - 效率对比（表4）：与5个典型模型对比参数量、训练/推理时间。
  - 超参数研究（图3）：在不同原型数量 M 和维度 d 下观察 RMSE 稳定性。
  - 案例研究：包括偏差等级分类（低/中/高）、潜在空间可视化、物理空间原型恢复。
- **充分性评估**：实验设计系统，覆盖性能、泛化性、效率、稳定性和可解释性；所用数据集均为公开基准，对比方法包括最先进基线，结论可靠。但未报告多次运行的方差/置信区间，可能影响统计显著性。

### 6. 论文的主要结论与发现
- ST-SSDL 在所有6个数据集上的所有指标均**一致超过**所有基线，证明了偏差建模的有效性。
- 消融实验表明：单独去掉对比损失或偏差损失均导致性能下降，同时去掉或整个SSDL导致更差，验证每个组件必要性。
- 视觉分析显示：模型能根据偏差程度（低、中、高）自适应地调整原型分配和预测输出，低偏差时映射到同一原型，高偏差时映射到分离原型。
- 原型在物理空间的恢复揭示了交通模式（如快速下降对应高峰期、平坦对应稳定状态等），表明模型学到了可解释的时空模式。

### 7. 优点：方法或实验设计上的亮点
- **方法创新**：首次使用自监督方式显式建模时空动态偏差，无需外部标签，具有普遍适用性。
- **技术精巧**：通过原型离散化+对比损失+偏差损失实现了潜在空间的结构化组织，避免了传统阈值方法的二元化局限。
- **轻量高效**：参数量远小于大多数 Transformer 类模型（如 METRLA 上 498K 参数，而 STDN 达 5971K），且在中小规模数据集上保持低参数量。
- **实验全面**：涵盖多类型数据集（速度/流量）、多对比方法、详细消融和可视化，结论扎实。

### 8. 不足与局限
- **计算效率**：虽然参数量少，但 GCRU 循环结构导致推理时间较长（如 PEMS07 上 inference 217.80s），明显慢于多数轻量模型（如 STID 0.64s），在实时高要求场景下可能受限。
- **周期性依赖**：锚点计算依赖周平均值，假设数据具有显著周期性；对于无周期或周期不固定的数据（如突发事件主导的场景），有效性需验证。
- **超参数敏感性**：原型数量 M 和维度 d 对性能有一定影响，尽管文中声称稳定，但极端值仍会导致欠拟合或过拟合。
- **缺失方差报告**：主结果仅给出单次运行数值，未报告多次试验的均值和标准差，统计可靠性不够透明。
- **偏差风险**：传感器部署不均可能导致模型在某些区域（如乡村道路）拟合不足，存在公平性问题（文中在“更广泛影响”中提及但未量化）。
- **应用限制**：当前仅在交通数据上验证，未扩展至其他时空领域（如环境、能源、气候），通用性待进一步证明。

（完）
