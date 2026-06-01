---
title: Selective Learning for Deep Time Series Forecasting
title_zh: 深度时间序列预测的选择性学习
authors: "Yisong Fu, Zezhi Shao, Chengqing Yu, Yujie Li, Zhulin An, Cheems Wang, Yongjun Xu, Fei Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=kgzRy6nD6D"
tags: ["query:qf"]
score: 6.0
evidence: 选择性学习用于深度时间序列预测以应对过拟合
tldr: 深度时间序列模型容易过拟合噪声和异常值。本文提出选择性学习策略，从所有时间步中筛选出可泛化的子集来计算训练损失，从而引导模型关注一般化模式而忽略非一般化噪声。该方法显著降低了过拟合，提升了预测性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-kgzry6nd6d/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kgzry6nd6d/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 752, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kgzry6nd6d/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1364, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kgzry6nd6d/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1436, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kgzry6nd6d/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 764, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kgzry6nd6d/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1466, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kgzry6nd6d/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1464, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kgzry6nd6d/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1459, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kgzry6nd6d/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1459, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kgzry6nd6d/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1460, \"height\": 327, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-kgzry6nd6d/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 770, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kgzry6nd6d/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kgzry6nd6d/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kgzry6nd6d/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kgzry6nd6d/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1457, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kgzry6nd6d/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1431, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kgzry6nd6d/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 393, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kgzry6nd6d/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 959, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kgzry6nd6d/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1369, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kgzry6nd6d/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1437, \"height\": 1813, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kgzry6nd6d/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1438, \"height\": 1814, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kgzry6nd6d/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1461, \"height\": 1076, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kgzry6nd6d/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1441, \"height\": 978, \"label\": \"Table\"}]"
motivation: 深度时间序列模型对所有时间步统一优化，导致过拟合噪声和异常值。
method: 提出选择性学习框架，动态筛选可泛化时间步的子集来计算损失。
result: 在多个基准数据集上，选择性学习提升了深度时间序列模型的泛化能力。
conclusion: 选择性采样训练时间步是缓解时间序列过拟合的有效手段。
---

## Abstract
Benefiting from high capacity for capturing complex temporal patterns, deep learning (DL) has significantly advanced time series forecasting (TSF). However, deep models tend to suffer from severe overfitting due to the inherent vulnerability of time series to noise and anomalies. The prevailing DL paradigm uniformly optimizes all timesteps through the MSE loss and learns those uncertain and anomalous timesteps without difference, ultimately resulting in overfitting. To address this, we propose a novel selective learning strategy for deep TSF. Specifically, selective learning screens a subset of the whole timesteps to calculate the MSE loss in optimization, guiding the model to focus on generalizable timesteps while disregarding non-generalizable ones. Our framework introduces a dual-mask mechanism to target timesteps: (1) an uncertainty mask leveraging residual entropy to filter uncertain timesteps, and (2) an anomaly mask employing residual lower bound estimation to exclude anomalous timesteps. Extensive experiments across eight real-world datasets demonstrate that selective learning can significantly improve the predictive performance for typical state-of-the-art deep models, including 37.4% MSE reduction for Informer, 8.4% for TimesNet, and 6.5% for iTransformer.

---

## 论文详细总结（自动生成）

# 论文中文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：深度时间序列预测（TSF）模型虽然能捕捉复杂时序模式，但由于真实时间序列数据中固有的噪声和异常值（如传感器干扰、政策干预导致的异常波动），模型在优化时对所有时间步（timestep）统一使用MSE损失进行训练，导致模型被迫学习那些不确定或异常、不可泛化的时间步，进而引发严重的过拟合。
- **整体含义**：现有深度学习范式将每个时间步等同对待，忽略了不同时间步的可泛化性差异。本文提出一种新的选择性学习策略，旨在动态筛选出可泛化的时间步子集用于损失计算，从而提升模型的泛化能力，缓解过拟合。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 选择性学习在每次优化迭代中，仅对部分时间步计算MSE损失，使模型专注于可泛化的模式，忽略非泛化（不确定或异常）的时间步。
- 通过一个**双重掩码机制（dual-mask mechanism）**动态确定哪些时间步应该被掩蔽。

### 关键技术细节
1. **不确定性掩码（Uncertainty Mask）**
   - 基于**残差熵（Residual Entropy）** ：假设每个时间步的预测残差服从高斯分布，利用滑动窗口采样得到多个预测残差，估计其方差，进而计算微分熵。高熵表示高不确定性，视为非泛化。
   - 对每个时间步计算熵，采用全局硬阈值，掩蔽熵最高的前 \( r_u\% \) 的时间步。
   - 阈值每个epoch更新一次，以降低计算开销。

2. **异常掩码（Anomaly Mask）**
   - 基于**残差下界估计**：训练一个轻量级辅助模型（如DLinear）来估计每个时间步的理想残差下界（理论上可达的最小残差）。当前残差与下界的距离较小，表明该时间步可能已经是异常（难以进一步改善）；距离较大则属于尚未学习好的可泛化样本。
   - 对每个样本的输出序列（per-sample），掩蔽距离最小的前 \( r_a\% \) 的时间步（即当前残差接近下界的异常点），从而避免模型拟合异常。
   - 这种动态掩码机制可以逐步调整被掩蔽的时间步，避免静态掩码对训练分布造成的偏差。

3. **损失函数**：
   \[
   L_{SL}(\theta) = \frac{1}{N \cdot |M^{(\tau)}|} \sum_{i=0}^{F-1} \| M^{(\tau)} (X_{t+i} - \hat{X}_{t+i}) \|^2
   \]
   其中 \( M^{(\tau)} = M_u^{(\tau)} \vee M_a^{(\tau)} \)，对每个变量独立计算掩码（channel-independent）。

### 算法流程（文字说明）
- 对于每次迭代：前向传播得到预测值，计算残差并更新历史残差记录。
- 每个epoch开始时，基于所有时间步的历史残差计算全局不确定性掩码的阈值。
- 每次迭代：基于当前残差和估计下界计算异常掩码的阈值（per-sample）。
- 合并两个掩码得到最终掩码，计算选择性学习损失，反向传播更新模型参数。

## 3. 实验设计

### 使用的数据集
- **8个真实数据集**：Electricity、Exchange、Weather、ILI，以及4个ETT子集（ETTh1、ETTh2、ETTm1、ETTm2）。
- 预测长度：对于ILI为 {24, 36, 48, 60}，其他数据集为 {96, 192, 336, 720}。
- 所有数据集按时间顺序划分训练/验证/测试（与TimesNet一致），比例为6:2:2或7:1:2等。

### Benchmark与对比方法
- **6个基线深度模型**：Informer、Crossformer、PatchTST、TimesNet、iTransformer、TimeMixer，涵盖Transformer、CNN、MLP架构。
- 使用MSE和MAE作为评价指标。
- 额外的对比实验：与其他非逐点训练目标（shape-based TILDE-Q、frequency-based FreDF、distribution-based PS loss）进行比较。
- 零样本预测实验：跨数据集泛化。
- 消融实验：去除各掩码、替换为随机掩码、静态掩码 vs 动态掩码、不同估计模型等。

## 4. 资源与算力
- 论文明确说明：所有实验在 **8块 NVIDIA GeForce RTX 4090 24GB GPU** 上完成。
- 训练时间方面：作者在附录中报告了运行成本（每个epoch的秒数），并指出选择性学习带来的额外时间开销在可接受范围内（例如，iTransformer在ETTh1上每个epoch增加约0.2-0.9秒）。具体数值因模型和序列长度而异。

## 5. 实验数量与充分性

- **实验数量充分**：
  - 8个数据集、每个数据集4个预测长度，共32个设置 × 6个基线模型 = 192组对比，几乎全部提升。
  - 消融实验覆盖4个数据集、4个预测长度。
  - 超参数分析（掩码比率、估计模型选择）提供多组结果。
  - 零样本实验涵盖6个迁移场景。
  - 与其他训练目标的对比实验（4个指标）也覆盖多个数据集。
- **公平性**：所有基线均使用其原论文最佳超参数，选择性学习只额外调整掩码比率，并以相同实验设置运行。代码已提供，可复现。

## 6. 主要结论与发现

1. **显著缓解过拟合**：选择性学习在所有192个测试案例中均一致提升模型性能，尤其对易过拟合的模型（如Informer、Crossformer）提升巨大。
   - Informer MSE平均下降37.4%（在ETTm2上达66.8%）。
   - iTransformer MSE下降6.5%，TimeMixer下降4.3%，表明在已有归一化技术（RevIN）基础上仍可额外提升。
2. **零样本泛化能力增强**：跨数据集测试时，选择性学习持续优于原始模型，部分场景甚至超过在目标数据集上从头训练的结果。
3. **优于其他非逐点训练目标**：与形状损失、频率损失、分布损失相比，选择性学习MSE更低。
4. **动态掩码优于静态掩码**：动态异常掩码可逐步学习极端事件，避免分布偏移。

## 7. 优点

- **创新性**：首次从时间步粒度解决TSF过拟合问题，提出不确定性+异常的双重掩码机制。
- **模型无关性**：可集成任意深度学习TSF骨干网络，通用性强。
- **理论支持**：提供方差估计误差的上界定理（Theorem 1），增强可靠性。
- **实验全面**：覆盖多种架构、数据集、消融、超参数分析、零样本等。
- **可解释性**：通过掩码可视化（案例）展示了选择性学习的效果。
- **兼容性**：可与现有归一化方法（如RevIN）和课程学习策略共存。

## 8. 不足与局限

- **任务局限**：目前仅用于时间序列预测，尚未扩展到分类、插补等其他分析任务。
- **极端事件预测能力可能受损**：异常掩码可能过滤掉稀有的极端事件，虽然动态机制部分缓解，但在极端事件重要性高的场景下需额外在线微调。
- **计算开销**：需要保存历史残差，大序列时内存需求增长（例如Electricity+F=336时约7GB RAM），且每epoch需更新熵阈值。
- **超参数敏感**：掩码比率 \( r_u, r_a \) 需要根据数据集调整，无通用最优值，依赖用户尝试。
- **预训练场景不直接适用**：对于大规模时间序列基础模型的预训练，无法逐时间步计算残差熵和下界，需重新设计（如概率预测器）。
- **估计模型依赖**：异常掩码需要训练一个估计模型，虽然作者证明简单模型可行，但增加了额外训练步骤。

（完）
