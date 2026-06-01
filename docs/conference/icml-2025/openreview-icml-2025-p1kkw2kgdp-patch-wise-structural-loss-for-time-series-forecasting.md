---
title: Patch-wise Structural Loss for Time Series Forecasting
title_zh: 时间序列预测的斑块结构损失
authors: "Dilfira Kudrat, Zongxia Xie, Yanru Sun, Tianyu Jia, Qinghua Hu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=p1KkW2kgDp"
tags: ["query:qf"]
score: 6.0
evidence: 用于时间序列预测的结构性损失函数
tldr: 本文提出基于斑块的结构性损失（PS loss），通过比较时间序列局部斑块的统计特性（如相关性、方差、均值）来捕捉结构偏差。该损失函数可替代传统逐点损失，增强模型对时间序列中复杂时间模式的建模能力。在多个时间序列预测基准上，使用PS损失的模型取得了更好的预测精度，有望提升金融波动率预测的准确性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-p1kkw2kgdp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 848, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p1kkw2kgdp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1779, \"height\": 489, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p1kkw2kgdp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1484, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p1kkw2kgdp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 868, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p1kkw2kgdp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1779, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p1kkw2kgdp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1790, \"height\": 781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p1kkw2kgdp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1780, \"height\": 1195, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-p1kkw2kgdp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1783, \"height\": 1246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p1kkw2kgdp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1778, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p1kkw2kgdp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1487, \"height\": 458, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p1kkw2kgdp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1486, \"height\": 438, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p1kkw2kgdp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1484, \"height\": 642, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p1kkw2kgdp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1365, \"height\": 401, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p1kkw2kgdp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1778, \"height\": 352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p1kkw2kgdp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1169, \"height\": 1251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p1kkw2kgdp/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1607, \"height\": 1032, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p1kkw2kgdp/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1607, \"height\": 1029, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p1kkw2kgdp/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1611, \"height\": 692, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p1kkw2kgdp/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1610, \"height\": 698, \"label\": \"Table\"}]"
motivation: 逐点损失函数忽略了时间序列的结构依赖关系。
method: 设计斑块级别的结构性损失，利用局部统计特性进行对齐。
result: 在多个数据集上，PS损失改进了预测性能。
conclusion: 为时间序列预测提供了一种通用的损失函数改进方案。
---

## Abstract
Time-series forecasting has gained significant attention in machine learning due to its crucial role in various domains. However, most existing forecasting models rely heavily on point-wise loss functions like Mean Squared Error, which treat each time step independently and neglect the structural dependencies inherent in time series data, making it challenging to capture complex temporal patterns accurately. To address these challenges, we propose a novel **P**atch-wise **S**tructural (**PS**) loss, designed to enhance structural alignment by comparing time series at the patch level. Through leveraging local statistical properties, such as correlation, variance, and mean, PS loss captures nuanced structural discrepancies overlooked by traditional point-wise losses. Furthermore, it integrates seamlessly with point-wise loss, simultaneously addressing local structural inconsistencies and individual time-step errors. PS loss establishes a novel benchmark for accurately modeling complex time series data and provides a new perspective on time series loss function design. Extensive experiments demonstrate that PS loss significantly improves the performance of state-of-the-art models across diverse real-world datasets. The data and code are publicly available at: \url{https://github.com/Dilfiraa/PS_Loss}.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有时间序列预测模型普遍使用逐点损失函数（如MSE），将每个时间步独立对待，忽略了时间序列固有的结构依赖关系（如趋势、波动、周期等），导致难以准确捕捉复杂的时间模式。
- **研究背景**：虽然深度学习模型在时序预测上取得了显著进展，但损失函数的设计仍以MSE为主。MSE在评估预测时只考虑点值差异，无法区分图1所示三种具有相同MSE但结构质量完全不同的情况（相关性差、方差失配、均值偏移）。这促使作者设计一种能捕获局部结构相似性的损失函数。
- **整体含义**：论文首次从**斑块（Patch）级别**引入结构相似性度量，通过比较真实序列与预测序列局部统计特性（相关系数、方差、均值），并结合梯度动态加权策略，实现更精准的结构对齐，从而提升预测精度和泛化能力。

## 2. 论文提出的方法论

### 核心思想
将预测序列和真实序列在时间维度上分成若干“斑块”（Patch），对每个斑块计算三个统计量损失（相关性损失、方差损失、均值损失），并自适应加权组合，最终与MSE联合优化。

### 关键技术细节（文字描述流程）

1. **傅里叶自适应分块（Fourier-based Adaptive Patching, FAP）**
   - 对真实序列Y做快速傅里叶变换，提取主频f，计算周期p = ⌊T/f⌋。
   - 斑块长度P = min(⌊p/2⌋, δ)，其中δ是预设最大斑块长度阈值，防止斑块过大。
   - 步长S = ⌊P/2⌋，将序列分割成N个重叠斑块。

2. **斑块结构损失（Patch-wise Structural Loss, PS Loss）**
   - **相关性损失** LCorr：基于Pearson相关系数，衡量每个斑块内预测与真实的线性方向和趋势一致性。公式为：LCorr = 1/N Σ (1 - ρ(Y_p^(i), Ŷ_p^(i)))。
   - **方差损失** LVar：先计算斑块内每个时间点偏离均值的差值，用softmax转化为概率分布，再用KL散度衡量真实序列与预测序列的相对离散程度。由于softmax平移不变性，可直接对原始值做softmax。公式：LVar = 1/N Σ KL(ϕ(Y_p^(i)) || ϕ(Ŷ_p^(i)))。
   - **均值损失** LMean：计算每个斑块均值的MAE，用于纠正预测偏移。公式：LMean = 1/N Σ |μ^(i) - μ̂^(i)|。
   - 总PS损失：LPS = α LCorr + β LVar + γ LMean。

3. **梯度动态加权（Gradient-based Dynamic Weighting, GDW）**
   - 在每轮训练中，计算三个损失项对模型输出层权重的梯度L2范数：G_Corr, G_Var, G_Mean。
   - 取三者均值Ḡ，然后设定权重：α = Ḡ / G_Corr，β = Ḡ / G_Var，γ = c·v· Ḡ / G_Mean。
     - 其中c和v是基于整体的协方差与标准差比值的调节因子，当预测与真实的相关性和方差匹配较好时，增大均值损失的权重，进一步精细调整。
   - 总损失：L = LMSE + λ LPS，λ为超参数控制PS损失贡献。

### 公式与算法流程（文字说明）
- 输入：历史序列X → 预测模型 → 预测序列Ŷ
- 步骤1：对Y和Ŷ分别进行FAP分块，得到N个斑块。
- 步骤2：计算每个斑块的LCorr, LVar, LMean。
- 步骤3：计算当前梯度G_Corr, G_Var, G_Mean，得到动态权重α, β, γ。
- 步骤4：计算LPS并加权到总损失中，与MSE一起反向传播更新模型参数。

## 3. 实验设计

- **数据集**：7个真实世界多变量时间序列
  - ETT系列（ETTh1, ETTh2, ETTm1, ETTm2）——电力变压器温度
  - Weather —— 气象因子
  - ECL —— 电力消耗负载
  - Exchange —— 外汇汇率
  - 数据划分：ETT按12/4/4月分割；其余按7:1:2分割。

- **基准模型（Backbones）**：5个SOTA架构
  - Transformer-based：iTransformer, PatchTST
  - MLP-based：DLinear, TimeMixer
  - CNN-based：TimesNet
  - 另外扩展到LLM-based：OFA（基于GPT-2）, AutoTimes（基于LLaMA）

- **对比方法**：
  - 主要对比标准MSE。
  - 与其他先进损失函数比较：TILDE-Q（形状不变损失）、FreDF（频域损失）。

- **实验场景**：
  - 长期多变量预测（预测长度96/192/336/720）。
  - 零样本预测（跨数据集迁移，使用一个数据训练，直接在其他数据测试）。
  - 消融研究（去掉每个损失分量、去掉分块、去掉动态加权）。
  - 超参数敏感性（λ和δ）。
  - 可视化对比。
  - 额外指标（DTW, TDI, PCC）评估。

## 4. 资源与算力

- **硬件**：论文指出实验使用PyTorch，在单张NVIDIA RTX 3090 24GB GPU上运行。
- **训练时长**：未给出总训练时长，但在附录D表中提供了每个epoch的训练时间对比（以iTransformer为例，PS loss相比MSE每epoch增加0.7~5.2秒不等）。
- **说明**：论文明确说明使用了单张RTX 3090，但未提及GPU数量、总训练轮数或总训练天数，因此算力细节不完整。

## 5. 实验数量与充分性

- **实验数量**：
  - 主实验表1：5个backbone × 7数据集 × 4预测长度 = 140种配置，PS在其中134个优于MSE。
  - LLM模型表2：2模型 × 4数据集 × 4长度 = 32种。
  - 与先进损失函数对比表3：1模型 × 3数据集 × 4长度 = 12种。
  - 消融表4：DLinear在2数据集上，去除各组件共6种情况 × 4长度 = 48项对比。
  - 零样本表5：3 backbone × 12源-目标对 = 36个。（还有不同长度及LLM零样本表11/12，总计超50项）。
  - 超参数敏感性（图4, 图5）、可视化、额外指标等。
- **充分性与客观性**：
  - 覆盖多种模型架构（Transformer、MLP、CNN、LLM）和多个领域数据集。
  - 严格遵循各backbone官方实现和默认超参数，仅调节λ和δ，控制变量公平。
  - 消融实验验证了每个组件的必要性，并对比了不使用分块或固定权重的情况。
  - 实验量充足，统计结果可信。唯一不足是消融仅在两个backbone（DLinear和iTransformer）部分数据集上进行，未在所有模型上验证。

## 6. 论文的主要结论与发现

- PS loss显著提升所有测试SOTA模型的预测精度，平均MSE和MAE均下降，例如DLinear上MSE平均降低5.22%，MAE降低4.39%。
- 在零样本场景下，PS loss在34/36个设置中优于MSE，表明其能提升模型对未见数据的泛化能力。
- 三个损失分量（相关性、方差、均值）缺一不可；自适应分块和梯度动态加权均起到重要作用。
- 与TILDE-Q、FreDF相比，PS loss在多数情况下取得最佳MSE/MAE。
- 可视化显示，PS loss使预测更贴近真实序列的趋势、波动幅度和整体水平。

## 7. 优点（方法与实验设计亮点）

- **方法创新性**：首次在损失函数层面引入patch级局部统计结构对齐，组合相关性、方差和均值三个互补维度。
- **自适应分块**：通过FFT确定主周期动态确定斑块长度，避免固定长度导致的信息丢失。
- **动态加权**：基于梯度幅度自动平衡多损失项，避免手动调参，且引入全局统计量c和v微调均值损失系数，增强训练的鲁棒性。
- **即插即用**：可与任何骨干模型结合，仅需添加少量计算开销（附录时间增加约0.7~5.2秒/epoch），适用范围广。
- **实验全面**：覆盖多种架构、多种数据集、多种预测长度，且包含零样本、消融、超参数敏感性、可视化等多维度验证。
- **代码开源**：便于复现和推广。

## 8. 不足与局限

- **计算开销**：虽然增加不大，但在极大规模数据集或实时部署场景下可能成为瓶颈。
- **超参数依赖**：需要调节λ和δ，尽管敏感性分析显示较鲁棒，但最优值仍需搜索。
- **实验覆盖有限**：
  - 消融实验仅在DLinear和iTransformer部分数据集上进行，未在所有骨干上验证每个组件，可能影响结论的普适性。
  - 与Soft-DTW、DILATE等形状损失函数未做直接对比（仅因计算复杂度高而未列入，但作为相关工作提及）。
  - 主要聚焦长期预测（96~720步），短期预测或单变量预测未专门实验。
- **对非平稳/无周期序列的适用性**：FAP依赖FFT提取主频，若序列周期性弱或剧烈非平稳，分块效果可能下降，论文未深入分析。
- **仅考虑局部结构**：作者在结论中承认当前方法只关注局部patch内结构，忽略了跨patch或全局结构动态，未来需扩展。
- **均值损失权重调节**：c和v因子依赖全局协方差和标准差，可能在极端噪声下不稳定。

（完）
