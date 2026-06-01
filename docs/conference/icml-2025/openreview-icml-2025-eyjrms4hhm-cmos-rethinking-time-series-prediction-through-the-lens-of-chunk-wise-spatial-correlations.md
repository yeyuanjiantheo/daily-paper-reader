---
title: "CMoS: Rethinking Time Series Prediction Through the Lens of Chunk-wise Spatial Correlations"
title_zh: CMoS：通过块级空间相关性重新思考时间序列预测
authors: "Haotian Si, Changhua Pei, Jianhui li, Dan Pei, Gaogang Xie"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=eyjrms4HHm"
tags: ["query:qf"]
score: 6.0
evidence: 超轻量时间序列预测模型
tldr: "轻量时间序列预测模型通常假设任务简单，但现有方法仍需较多参数。本文提出CMoS，直接建模不同时间序列块之间的空间相关性，而非学习形状嵌入。引入相关混合技术以最少参数捕获多样空间模式，并可选的周期性注入加速收敛。CMoS仅用DLinear 1%的参数即超越现有最优模型，适用于金融高频数据的快速预测。"
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-eyjrms4hhm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 840, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eyjrms4hhm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 851, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eyjrms4hhm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1493, \"height\": 895, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eyjrms4hhm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 810, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eyjrms4hhm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 775, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eyjrms4hhm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 850, \"height\": 250, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eyjrms4hhm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 840, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eyjrms4hhm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 852, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eyjrms4hhm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1508, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eyjrms4hhm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1734, \"height\": 258, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eyjrms4hhm/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1687, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eyjrms4hhm/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1779, \"height\": 1006, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eyjrms4hhm/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1778, \"height\": 892, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-eyjrms4hhm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1781, \"height\": 607, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eyjrms4hhm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eyjrms4hhm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 859, \"height\": 153, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eyjrms4hhm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1182, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eyjrms4hhm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1298, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eyjrms4hhm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1759, \"height\": 2203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eyjrms4hhm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1769, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eyjrms4hhm/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1766, \"height\": 528, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eyjrms4hhm/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1283, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eyjrms4hhm/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 533, \"height\": 198, \"label\": \"Table\"}]"
motivation: 现有轻量时间序列预测模型仍有冗余参数，需要更高效的空间关系建模。
method: 提出CMoS，直接建模时间序列块间空间相关性，通过相关混合和周期性注入实现超轻量预测。
result: "仅用DLinear 1%的参数，在多个标准数据集上取得最优或可比较的预测性能。"
conclusion: 展示了时间序列预测中空间相关性建模的高效性，为资源受限的金融预测提供新思路。
---

## Abstract
Recent advances in lightweight time series forecasting models suggest the inherent simplicity of time series forecasting tasks. In this paper, we present CMoS, a super-lightweight time series forecasting model. Instead of learning the embedding of the shapes, CMoS directly models the spatial correlations between different time series chunks. Additionally, we introduce a Correlation Mixing technique that enables the model to capture diverse spatial correlations with minimal parameters, and an optional Periodicity Injection technique to ensure faster convergence. Despite utilizing as low as 1% of the lightweight model DLinear's parameters count, experimental results demonstrate that CMoS outperforms existing state-of-the-art models across multiple datasets. Furthermore, the learned weights of CMoS exhibit great interpretability, providing practitioners with valuable insights into temporal structures within specific application scenarios.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：现有轻量时间序列预测模型（如DLinear、FITS、SparseTSF等）尽管参数较少，但仍需学习形状嵌入或点对点依赖，忽略了时间序列中更稳定且高效的表示形式——**块级空间相关性**。作者观察到时间序列块之间的相对位置关系（即空间相关性）具有平移不变性和可分解性，这种性质可以用更少的参数捕获，且更具鲁棒性和可解释性。
- **整体含义**：提出了超轻量模型CMoS（Chunk-wise Mixture of Spatial correlations），仅用DLinear约1%的参数，即可在多个长时多变量预测任务上超越现有SOTA模型，同时提供对时间结构的高度可解释性。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：将预测任务重新定义为未来时间块与历史时间块之间的线性组合，直接学习**块与块之间的空间相关性矩阵**，而非学习形状嵌入。
- **关键技术细节**：
    1. **Chunk-wise Spatial Correlation Modeling**：将历史窗口和未来窗口分别分割为长度S的块（chunk），每个未来块表示为历史块的线性组合（公式(2)）。理论证明（Theorem 3.2）块级建模比点级建模对高斯噪声更鲁棒（噪声敏感度更低）。
    2. **Correlation Mixing**：借鉴MoE思想，学习K个共享的基础空间相关性矩阵，并为每个通道分配一组混合权重（由通道特有的信息聚合器提取的表示通过线性层映射得到），从而用极少的参数（K ≪ 通道数）适应不同通道的不同时间结构。
    3. **Periodicity Injection**：对于具有明显周期的时序（如人类活动相关数据集），通过直接编辑第一个相关性矩阵的初始权重（将周期性对应位置设为`p/L`，其余为0），强制模型关注周期依赖，加速收敛并提升性能。
    4. **Instance Normalization**：标准可逆实例归一化，消除分布偏移。
- **参数效率**：总参数量 = K×(L/S)×(H/S) + N×c + (2L-c)/c×K，其中K常数且远小于N，相比DLinear的2×L×H大幅降低（例如ETTh1上为L×H/96 + L，仅为DLinear的1%）。

### 3. 实验设计：数据集、场景、对比方法
- **数据集**：7个广泛使用的长时多变量预测数据集：Electricity（321通道）、Traffic（862通道）、Weather（21通道）、ETTh1/ETTh2（7通道）、ETTm1/ETTm2（7通道）。覆盖不同通道数、采样率（1小时/10分钟/15分钟）和周期性。
- **场景**：长期预测，预测长度H ∈ {96, 192, 336, 720}，回看窗口在{96,336,720}中网格搜索。
- **对比方法**：
    - **复杂模型**：Informer、FedFormer、TimesNet、PatchTST、TimeMixer、iTransformer。
    - **轻量模型**：DLinear、FITS、SparseTSF、CycleNet。
- **评价指标**：MSE和MAE，结果取5次随机初始化的平均值和标准差。

### 4. 资源与算力
- **硬件环境**：12核Intel Xeon Gold 5317 CPU @ 3.00GHz，4×NVIDIA RTX 3090 GPU（每实验使用单GPU）。
- **训练配置**：AdamW优化器，学习率在{2e-5, 5e-5, 8e-5, 8e-4}中搜索，StepLR调度器（step_size=20, gamma=0.75），训练200 epoch，批大小64。
- **算力统计**：未明确给出总训练时长，但提供了推理阶段的数据：在Electricity数据集上，CMoS的FLOPs仅2.96G，GPU内存252MB，推理时间1.58s（批大小64），远低于大多数基线。

### 5. 实验数量与充分性
- **实验数量**：
    - 主实验：7个数据集×4个预测长度，报告平均MSE/MAE（共28个结果）。
    - 消融实验：验证块建模、相关混合、周期性注射的影响（在H=96上对7数据集比较）。
    - 超参数分析：块大小（4~24）、基矩阵数量（1~12）在Electricity上的影响。
    - 通道策略对比：Private Line、One Bus、Data Mixing、Correlation Mixing（在3个多通道数据集上）。
    - 噪声鲁棒性：在合成正弦加突发噪声上与点级建模对比（附录G）。
    - 周期性注射对收敛速度的验证（训练损失曲线）。
- **充分性与公平性**：
    - 复现了最新轻量模型（CycleNet、SparseTSF）并参考TFB基准提供其他基线结果，保证公平。
    - 多次随机初始化取平均，报告标准差，体现稳定性。
    - 消融实验系统，每个组件均被验证。
    - 跨数据集（不同通道数、周期、噪声水平）验证，覆盖面较广。
    - **不足**：未包含Exchange-rate等争议数据集（作者明确说明剔除），但可能影响与部分论文的直接对比；合成噪声实验仅用于补充理论，缺乏真实噪声数据验证。

### 6. 论文的主要结论与发现
- CMoS仅用DLinear约1%的参数，在9/14个指标上取得第一，3/14第二，尤其在多通道数据集（Electricity、Traffic、Weather）上显著优于所有轻量模型，甚至超越复杂模型。
- 块级建模比点级建模更具鲁棒性和参数效率；相关混合机制允许用极少量基矩阵表达多种时间结构；周期性注射在具有稳定周期性的人类相关数据集上加速收敛并提升性能，但在自然现象数据集（Weather）上可能有害。
- 学习到的空间相关性矩阵具有高度可解释性，可以揭示系统的时间规律（如Mapping2对应前一日同块依赖，Mapping3对应极短时依赖，Mapping4对应长周期依赖，Mapping1捕获残差依赖）。

### 7. 优点
- **超轻量与高性能**：参数量仅为轻量模型DLinear的1%，却获得SOTA预测效果，特别适合资源受限的部署（边缘设备）。
- **强大的可解释性**：各基矩阵的权重直接反映历史块对未来块的贡献，结合通道混合权重可分析每个通道的时间结构。
- **方法简洁**：仅需线性组合，无需复杂注意力或RNN结构，训练和推理速度快。
- **鲁棒性设计**：块级建模含噪声抑制理论保证，相关混合对不同通道自适应，周期性注射可加速收敛但可选。
- **实验充分**：涵盖多数据集、多消融、超参数敏感性、通道策略对比、噪声鲁棒性，且报告多次运行标准差，结果可信。

### 8. 不足与局限
- **理论分析不足**：噪声鲁棒性证明仅针对高斯噪声，对突发噪声（burst noise）等非高斯噪声仅提供实验性验证，缺乏严格理论。
- **周期性注射的适用范围有限**：在无人工设定的自然数据（如Weather）上可能降低性能，需用户判断周期性是否显著，增加了使用门槛。
- **对不规则/非平稳时序可能无效**：作者承认对于随机游走等缺乏平稳性/周期性的序列，空间相关性建模的前提可能不成立，长时预测效果会受限。
- **实验覆盖仍有提升空间**：未包含金融、医疗等更多领域数据；未与其他极轻量模型（如TiDE）在相同资源下全面比较FLOPs实际耗时（仅提供了Electricity上的推理开销）。
- **可扩展性讨论不足**：当通道数极大（如>1000）时，相关混合中的信息聚合器（每个通道独立卷积）参数量N×c仍可能增长，论文未讨论大规模场景下的优化策略。
- **泛化性验证有限**：仅针对长时多变量预测，未在单变量或短时预测、分类、异常检测等任务上验证。

（完）
