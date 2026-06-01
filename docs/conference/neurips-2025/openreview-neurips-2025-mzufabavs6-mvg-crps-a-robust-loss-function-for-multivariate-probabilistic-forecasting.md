---
title: "MVG-CRPS: A Robust Loss Function for Multivariate Probabilistic Forecasting"
title_zh: MVG-CRPS：用于多元概率预测的鲁棒损失函数
authors: "Vincent Zhihao Zheng, Lijun Sun"
date: 2025-05-02
pdf: "https://openreview.net/pdf?id=mZuFaBAVs6"
tags: ["query:qf"]
score: 7.0
evidence: 用于多元概率预测的鲁棒损失函数，基于高斯分布
tldr: 多元概率预测中，标准负对数似然对异常值敏感，而能量分数计算昂贵。本文提出MVG-CRPS，一种针对多元高斯分布的封闭形式严格合理评分规则，兼具鲁棒性和计算效率。该方法在神经网络训练中可扩展，显著提升了异常值存在下的预测准确性。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzufabavs6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 513, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzufabavs6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 573, \"height\": 206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzufabavs6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 572, \"height\": 206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzufabavs6/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1017, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzufabavs6/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 877, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzufabavs6/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 950, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzufabavs6/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1311, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzufabavs6/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1169, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzufabavs6/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 948, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzufabavs6/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 877, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzufabavs6/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1089, \"height\": 632, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzufabavs6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 572, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzufabavs6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 567, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzufabavs6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 738, \"height\": 514, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzufabavs6/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1317, \"height\": 816, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzufabavs6/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 775, \"height\": 390, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzufabavs6/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1456, \"height\": 569, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzufabavs6/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1490, \"height\": 589, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzufabavs6/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 737, \"height\": 537, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzufabavs6/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 737, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzufabavs6/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 800, \"height\": 552, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzufabavs6/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1456, \"height\": 569, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzufabavs6/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1478, \"height\": 593, \"label\": \"Table\"}]"
motivation: 现有多元概率预测损失函数在鲁棒性和计算效率之间存在权衡。
method: 提出了MVG-CRPS，一种基于多元高斯分布的封闭形式鲁棒评分规则，兼具能量分数的鲁棒性和负对数似然的计算效率。
result: 在多元时间序列预测任务中，MVG-CRPS提升了异常值下的预测精度并降低了计算开销。
conclusion: MVG-CRPS是多元概率预测中有效的鲁棒损失函数替代方案。
---

## Abstract
Multivariate probabilistic forecasting typically leverages neural network-based distributional regression, often employing Gaussian assumptions to simplify computation. While the standard negative log-likelihood provides analytical convenience, its sensitivity to outliers can severely degrade forecasting accuracy. Conversely, robust alternatives like the Energy Score, although less sensitive to extreme values, rely heavily on computationally expensive sampling approximations, limiting scalability in neural network training. To bridge this gap, we introduce the MVG-CRPS, a novel, strictly proper scoring rule for multivariate Gaussian distributions that maintains robustness to outliers while providing a closed-form expression, enabling efficient training and evaluation. Our approach leverages a whitening transformation, decorrelating multivariate outputs and reducing the multivariate scoring task to tractable univariate CRPS computations. Experiments on real-world datasets for both multivariate autoregressive and univariate sequence-to-sequence (Seq2Seq) forecasting tasks demonstrate that MVG-CRPS enhances robustness and predictive performance.

---

## 论文详细总结（自动生成）

# MVG-CRPS 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：在多元概率预测中，现有损失函数在鲁棒性和计算效率之间存在固有矛盾。
- **具体背景**：
    - **负对数似然（log-score）**：在多元高斯假设下，计算方便，但指数型尾部惩罚导致其对异常值和极端事件极度敏感，易产生过于保守或不准确的预测分布。
    - **能量分数（Energy Score, ES）**：作为鲁棒替代方案，对异常值不敏感，但其没有封闭形式，需要蒙特卡洛采样来近似，计算成本高，限制了在神经网络训练中的可扩展性。
- **整体含义**：需要一种同时具备鲁棒性（类似ES）和计算效率（类似log-score）的评分规则，以提升多元概率预测模型在真实世界数据（常含异常值）上的性能和训练速度。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：提出MVG-CRPS，一种针对多元高斯分布的、严格合理的、具有封闭形式的评分规则。它通过**白化变换**将多元问题分解为一组易于处理的单变量问题，从而兼具鲁棒性和计算效率。
- **关键技术细节与算法流程**：
    1.  **假设**：预测分布为多元高斯分布 \(z_t \sim N(\mu_t, \Sigma_t)\)。
    2.  **白化变换**：
        - 对协方差矩阵 \(\Sigma_t\) 进行奇异值分解（SVD）：\(\Sigma_t = U_t S_t U_t^\top\)。
        - 定义白化后的残差向量：\(w_t = S_t^{-1/2} U_t^\top (z_t - \mu_t)\)。
        - 该变换使得 \(w_t\) 的每个分量 \(w_{i,t}\) 服从独立的标准正态分布 \(N(0, 1)\)，且分量之间不相关。
    3.  **多元评分简化为单变量CRPS**：
        - 利用单变量CRPS对标准正态分布的封闭形式表达式（\(CRPS(\Phi, z)\)）。
        - MVG-CRPS 的计算公式变为对每个白化分量的CRPS加权求和：\(MCRPS = \Sigma_i \sqrt{\lambda_{i,t}} CRPS(\Phi, w_{i,t})\)，其中 \(\lambda_{i,t}\) 是特征值。
        - 这相当于将多元高斯分布的CRPS转化为 \(N\) 个相互独立的标准正态分布CRPS的计算，每个计算都有解析解。
    4.  **整体损失函数**：在整个观测周期 \(T\) 上求和：\(L = \Sigma_t MCRPS\)。
- **优点**：
    - **封闭形式**：所有梯度都有解析表达式，可以直接与深度学习框架的反向传播集成，无需采样。
    - **严格合理**：在多元高斯分布族下被证明是严格合理的评分规则。
    - **高敏感性**：对预测分布的均值和协方差矩阵同样敏感，弥补了能量分数对协方差结构不敏感的缺点。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法
- **任务场景**：
    1.  **多元自回归预测**：使用RNN（GPVar）和解码器Transformer。
    2.  **单变量序列到序列预测**：使用MLP（N-HiTS）。
- **数据集**：来自GluonTS的13个真实世界时间序列数据集，包括`elec_au`, `cif_2016`, `electricity`, `elec_weekly`, `exchange_rate`, `kdd_cup`, `m1_yearly`, `m3_yearly`, `nn5_daily`, `saugeenday`, `sunspot`, `tourism`, `traffic`等，覆盖多种粒度和领域。在单变量Seq2Seq任务中额外增加了`covid`, `m4_hourly`, `pedestrian`等8个数据集。
- **基准模型（Baseline）**：
    - 强基准：向量自回归模型（VAR）作为朴素基线。
    - 核心对比：基于log-score和ES训练的同一模型（GPVar和Transformer）。
- **对比方法**：MVG-CRPS与**对数分数(log-score)**、**能量分数(ES)** 进行对比。

## 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。若未明确说明，也请指出这一点。
- **明确说明**：论文在附录C.4节中提到，所有模型在一个环境中训练，该环境包含：
    - CPU: AMD Ryzen Threadripper PRO 5955WX
    - GPU: 4块 NVIDIA RTX A5000（每块24GB显存）
- **训练时长**：论文并未提供每项实验的具体总时长，但在表2中给出了每个epoch的训练时间（分钟）和总训练时间（分钟）。例如，在`elec_au`数据集上使用GPVar，log-score总训练时间33.53分钟，ES为717分钟，MVG-CRPS为29.14分钟，直观展示了MVG-CRPS比ES快一个数量级。

## 5. 实验数量与充分性：大概做了多少组实验，这些实验是否充分、是否客观、公平
- **实验数量与覆盖度**：
    - **主实验**：在13个数据集、2种模型架构（GPVar和Transformer）上系统比较了三种评分规则（log-score, ES, MVG-CRPS），包括CRPS sum, CRPS mean, ES三种评估指标，构成了相当全面的实验阵。
    - **消融与鲁棒性实验**：
        - 玩具示例：研究评分规则对均值、标准差、相关系数偏离的敏感性。
        - 合成数据实验：在有数据污染的合成数据上评估参数估计的鲁棒性。
        - 超参数敏感性分析：对不同损失函数分别调优学习率和秩。
        - 受控异常值实验：在训练数据中注入合成异常值，观察模型性能退化情况。
    - **可视化**：比较了不同损失函数下模型输出的协方差矩阵和概率预测图，提供了定性证据。
- **实验充分性与公平性评估**：
    - **客观性**：多次重复实验（如10次）并报告均值和标准差，体现了良好的统计严谨性。
    - **公平性**：主实验中保持超参数对所有损失函数一致，以确保改进归因于损失函数本身。虽然这可能导致MVG-CRPS未达最优，但后续超参数调优实验证实了MVG-CRPS的优异性能。
    - **不足**：论文指出由于ES训练时间过长，未对其进行超参数调优，这在一定程度上影响了对比的完全公平性。

## 6. 论文的主要结论与发现
- **主要结论**：提出的MVG-CRPS是一种有效、鲁棒且高效的损失函数，适用于多元高斯概率预测。
- **具体发现**：
    - **鲁棒性优于log-score**：在含有异常值的数据上，MVG-CRPS相比log-score能生成更准确、更稳定、校准更好的预测，协方差矩阵估计也更稳健。
    - **效率远超ES**：MVG-CRPS无需采样，具有封闭形式梯度，训练速度比ES快一个数量级以上。
    - **性能持平或优于ES**：在大多数数据集上，MVG-CRPS的预测精度（CRPS, ES）与ES相当或更优。
    - **综合性能**：MVG-CRPS在准确性、鲁棒性和计算效率之间取得了更好的平衡。

## 7. 优点：方法或实验设计上有哪些亮点
- **方法论亮点**：
    - **创新性**：巧妙利用PCA白化变换，将复杂的多元CRPS问题简化为多个有封闭解的单变量CRPS问题。
    - **设计精妙**：严格证明了MVG-CRPS在多元高斯族中的严格合理性，理论基础扎实。
    - **实用性**：直接、易于集成到现代深度学习框架中，且能保持对协方差结构的高度敏感性。
- **实验设计亮点**：
    - **多维度验证**：综合运用合成数据、真实数据、玩具示例和视觉化分析，全面评估方法的鲁棒性、准确性和效率。
    - **公平性考量**：在主要实验中采用统一超参数，排除了超参数选择对结果的干扰。
    - **鲁棒性测试**：专门设计合成异常值和噪声注入实验，直接验证了提出的鲁棒性优势。

## 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等
- **实验覆盖**：
    - **场景覆盖**：方法假设多元高斯分布，未探讨其在非高斯分布（如厚尾、多模态）上的表现。论文在“未来方向”中提及可通过Copula扩展，但未实验验证。
    - **模型与合成数据限制**：核心实验围绕GPVar和N-HiTS完成，但缺少与其他常用概率预测模型（如DeepAR, TACTiS）的对比。
- **偏差风险**：
    - **超参数偏差**：实验设计优先保证公平，但未对ES进行超参数调优，可能略微低估了ES的潜在能力。
    - **ERM框架限制**：方法仅适用于基于期望风险最小化的训练。
- **应用限制**：
    - **计算瓶颈**：MVG-CRPS涉及协方差矩阵的特征分解（SVD），其计算复杂度为 \(O(B^3)\)，其中 \(B\) 是批/批次维度的时间序列数量。虽然批大小较小，但在大规模高维数据上仍可能成为瓶颈。论文提到可通过采用各向同性噪声参数化来缓解，但未充分验证。
    - **高斯假设局限性**：对非高斯数据分布的直接适配能力有限。
    - **可解释性**：相比于统计模型，预测不确定性的解释提出更高挑战。

（完）
