---
title: Online Time Series Forecasting with Theoretical Guarantees
title_zh: 具有理论保证的在线时间序列预测
authors: "Zijian Li, Changze Zhou, Minghao Fu, Sanjay Manjunath, Fan Feng, Guangyi Chen, Yingyao Hu, Ruichu Cai, Kun Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=0XCZWAo7wN"
tags: ["query:qf"]
score: 6.0
evidence: 具有理论保证的在线时间序列预测，应对分布漂移
tldr: 在线时间序列预测面临分布漂移挑战。本文提出带有理论保证的在线时间序列预测框架TOT，证明引入潜在变量可降低贝叶斯风险，并设计基于邻近观测的潜在变量识别方法。该方法在合成和真实数据上验证了其有效性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-0xczwao7wn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 434, \"height\": 228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0xczwao7wn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 853, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0xczwao7wn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 638, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0xczwao7wn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1404, \"height\": 331, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1412, \"height\": 133, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1457, \"height\": 658, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1437, \"height\": 1398, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 856, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1118, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1262, \"height\": 1667, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1386, \"height\": 1592, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1386, \"height\": 1633, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1595, \"height\": 1671, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1269, \"height\": 1509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1454, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1028, \"height\": 762, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1454, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1454, \"height\": 413, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1454, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0xczwao7wn/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1454, \"height\": 412, \"label\": \"Table\"}]"
motivation: 在线时间序列预测中分布漂移导致预测不准确，且缺乏理论保证。
method: 提出TOT框架，通过引入潜在变量并证明其能降低贝叶斯风险，同时设计最小邻近观测的潜在变量识别方法。
result: 在合成和真实时间序列数据上，TOT优于现有在线预测方法。
conclusion: 潜在变量有助于提升在线时间序列预测的理论保证和经验表现。
---

## Abstract
This paper is concerned with online time series forecasting, where unknown distribution shifts occur over time, i.e., latent variables influence the mapping from historical to future observations. To develop an automated way of online time series forecasting, we propose a Theoretical framework for Online Time-series forecasting (TOT in short) with theoretical guarantees. Specifically, we prove that supplying a forecaster with latent variables tightens the Bayes risk—the benefit endures under estimation uncertainty of latent variables and grows as the latent variables achieve a more precise identifiability. To better introduce latent variables into online forecasting algorithms, we further propose to identify latent variables with minimal adjacent observations. Based on these results, we devise a model-agnostic blueprint by employing a temporal decoder to match the distribution of observed variables and two independent noise estimators to model the causal inference of latent variables and mixing procedures of observed variables, respectively. Experiment results on synthetic data support our theoretical claims. Moreover, plug-in implementations built on several baselines yield general improvement across multiple benchmarks, highlighting the effectiveness in real-world applications.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

在线时间序列预测面临一个关键挑战：由于未知的潜在变量（latent variables）随时间变化，导致历史观测到未来观测的映射关系发生分布漂移（distribution shift），使得传统预测模型性能下降。现有方法（如Pham et al., Zhang et al., Zhao & Shen等）虽能通过模型架构或概念漂移估计来缓解这一问题，但缺乏系统的理论保证——它们未能解释为何引入分布漂移估计能系统性降低预测误差，也忽视了分布漂移估计本身的不确定性对泛化风险的影响。因此，本文旨在建立一个通用的、具有理论保证的在线时间序列预测框架，并为其提供实用的模型架构。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将时间序列数据生成过程建模为受潜在变量 \( z_t \) 驱动的非平稳过程（如图1所示）。证明利用潜在变量可收紧贝叶斯风险（Bayes risk），且该收益随潜在变量可识别性（identifiability）的提高而增大；进一步证明仅需四个连续观测即可唯一识别潜在变量及其因果动态。基于此，设计一个模型无关（model-agnostic）的即插即用架构。

- **关键技术细节**：
  - **数据生成过程**：观测变量 \( x_t = g(z_t, x_{t-1}, \epsilon^o_t) \)（非线性混合）；潜在变量 \( z_{t,i} = f_i(\text{Pa}^d(z_{t,i}), \text{Pa}^e(z_{t,i}), \epsilon^z_{t,i}) \)（潜在因果影响）。噪声独立。
  - **理论贡献**：
    - **定理1（预测风险降低）**：条件预测模型使用 \( \{x_{t-\tau:t}, z_t\} \) 的贝叶斯风险 \( R_z \) 低于仅使用 \( \{x_{t-\tau:t}\} \) 的 \( R_o \)；使用估计潜在变量 \( \hat{z}_t \) 的风险 \( R_{\hat{z}} \) 介于两者之间，且当 \( z_t \) 可完全识别时 \( R_{\hat{z}} = R_z \)。
    - **定理2（块识别）**：在边界连续密度、线性算子单射性及谱分解唯一性假设下，通过匹配四个相邻观测 \( \{x_{t-2}, x_{t-1}, x_t, x_{t+1}\} \) 的联合分布，可得到 \( (x_t, z_t) \) 的块级可识别性（block-wise identifiable）。
    - **定理3（分量识别）**：在稀疏混合过程（sparse mixing procedure）假设下，进一步证明潜在变量 \( z_t \) 的各分量可一一对应识别（component-wise identifiable）。
  - **模型架构**（图3）：
    - 编码器 \( \phi \) 从历史观测 \( x_{1:t} \) 估计潜在变量 \( \hat{z}_{1:T} \)；解码器 \( \psi \) 从 \( \hat{z}_{1:t} \) 重建 \( \hat{x}_{1:t} \)。
    - **潜在转移估计器**：利用逆变换 \( r^z_i \) 从 \( z_t, z_{t-1} \) 估计噪声 \( \hat{\epsilon}^z_{t,i} \)，通过变量变换公式计算对数概率，并施加独立性约束（KL散度）。
    - **观测转移估计器**：类似地，利用 \( r^o_i \) 从 \( z_t, x_{t-1}, x_t \) 估计噪声 \( \hat{\epsilon}^o_{t,i} \)，建模观测动态。
    - **残差预测器**：结合历史观测 \( x_{1:t} \)（经降维）和估计潜在变量 \( \hat{z}_{t+1:T} \) 进行预测 \( \hat{x}_{t+1:T} = \varphi(\hat{z}_{t+1:T}, \eta(x_{1:t})) \)。
    - **稀疏约束**：对 \( \partial \hat{x}_t / \partial \hat{z}_t \) 施加L1惩罚，增强混合过程的稀疏性。
  - **损失函数**：\( L_{\text{total}} = L_y + \alpha L_r - \beta (L^z_{KL} + L^o_{KL}) + \gamma L_s \)。

## 3. 实验设计

- **数据集**：
  - **合成数据**：提出4种不同设置的合成数据集（A: 严格按图1生成，观测间有因果边；B: 无观测因果边；C: 时间滞后为2；D: 10维潜在变量）。报告了A和B的结果。
  - **真实数据**：6个基准数据集：ETTh2、ETTm1（电力变压器温度）、Exchange（汇率）、Weather（气象）、ECL（电力消耗）、Traffic（交通流量）。
- **基准方法**：
  - 合成数据：对比IDOL、TDRL、CariNG（用于可识别性评估）；对比仅用 \( x_t \)、用 \( x_t+z_t \) 和用 \( x_t+\hat{z}_t \) 的预测上限/下限。
  - 真实数据：基于5种骨干网络：LSTD、Proceed-T、OneNet（两种变体）、Online-T、MIR、TFCL。每种骨干分别加入TOT模块对比。
- **评价指标**：MCC（识别性能）、MSE和MAE（预测性能）。重复3次不同随机种子报告均值和标准差。

## 4. 资源与算力

论文未明确说明使用的GPU型号、数量和训练时长。附录提供了各骨干网络的详细架构配置，但未给出具体算力消耗信息。因此，无法量化资源使用情况。

## 5. 实验数量与充分性

- **实验数量**：丰富且系统。
  - 合成数据：4种数据集 × 2种任务（识别+预测） × 多个基线，共约10+组对比。
  - 真实数据：6个数据集 × 多个预测长度（1, 24, 48） × 7种骨干网络（含变体） × 3次重复，生成大量表格（表2-3、A12-A17）。另外有消融实验（图4）对比移除稀疏项、KL项、重建项的效果。
  - 额外实验：控制参数量（表A13）证明改进非来自参数增加；附录还报告了标准差。
- **充分性与客观性**：实验覆盖多种数据生成设置和真实场景，对比方法较全面（包括在线学习和持续学习基线），消融实验验证各组件必要性。结果均报告均值和标准差，确保统计意义。结论客观指出在某些任务（如ECL上LSTD骨干）改进较小但匹配或超过。整体充分且公平。

## 6. 论文的主要结论与发现

- 引入潜在变量进行条件预测可理论保证地降低贝叶斯风险，且风险减少程度随潜在变量可识别性提高而增强。
- 仅需四个连续观测即可唯一识别潜在变量及其因果动态，无需严格的单调性或归一化假设。
- 提出的TOT框架（模型无关即插即用架构）在合成数据上验证了理论结果，在多个真实世界基准上一致提升了现有在线预测方法的性能（MSE和MAE指标普遍下降）。
- 消融实验表明，稀疏约束、KL散度项和重建损失均不可或缺。

## 7. 优点

- **理论扎实**：首次为在线时间序列预测中引入潜在变量提供了完整的贝叶斯风险下界和非参数可识别性证明（块级和分量级），填补了现有方法缺乏理论保证的空白。
- **模型无关性**：提出的架构可轻松插入多种骨干网络（LSTD、OneNet、TCN等），无需改变训练策略，实用性强。
- **实验充分**：涵盖合成和6个真实数据集、多种预测长度、多个骨干，并报告均值与标准差，验证了可迁移性和鲁棒性。
- **技术新颖性**：利用四个相邻观测进行块识别比以往需要三个观测的方法更通用；稀疏混合过程假设比稀疏因果过程假设更容易满足；允许观测噪声使模型更贴近实际。
- **消融验证**：明确各损失项的必要性，增加可解释性。

## 8. 不足与局限

- **理论假设限制**：要求数据完全观测且离散均匀采样，未覆盖连续时间、不规则采样或多速率采样场景。论文也承认这是未来方向。
- **实验覆盖**：虽然数据集多样，但仍以电力、天气、交通等典型领域为主，缺乏金融高频、生物医学等更复杂动态场景的验证。部分任务（如ECL上LSTD骨干）改进幅度较小，暗示在特定数据上优势不显著。
- **算力开销未报告**：未提供GPU型号、训练时间等细节，难以评估方法在实际部署中的计算成本。
- **潜在变量维度设定**：当前假设观测和潜在变量维度 \( n \) 相同（均为n维），实际中维度可能不匹配，需要进一步扩展。
- **可识别结果的实践性**：定理2和3中的假设（如线性算子单射、谱分解唯一性）在严格意义上难以完全满足，但论文通过实例说明合理。然而在真实数据中验证可识别性（MCC）仅通过合成数据，未在真实数据上直接验证潜在变量恢复质量。
- **持续学习对比**：虽然对比了TFCL、MIR等持续学习方法，但重点仍为在线时间序列预测的领域，缺乏与在线凸优化等经典理论方法的直接对比。

（完）
