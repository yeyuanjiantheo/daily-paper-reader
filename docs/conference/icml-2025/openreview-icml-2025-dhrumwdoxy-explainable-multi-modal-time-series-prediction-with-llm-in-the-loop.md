---
title: Explainable Multi-modal Time Series Prediction with LLM-in-the-Loop
title_zh: 基于大模型回路的多模态时间序列可解释预测
authors: "Yushan Jiang, Wenchao Yu, Geon Lee, Dongjin Song, Kijung Shin, Wei Cheng, Yanchi Liu, Haifeng Chen"
date: 2025-01-24
pdf: "https://openreview.net/pdf?id=DHRUMwDOXy"
tags: ["query:qf"]
score: 7.0
evidence: 多模态时间序列预测框架，利用大模型处理金融时间序列
tldr: 现有时间序列方法常忽略辅助模态（如金融新闻）的上下文信息。TimeXL框架通过原型编码器与三个大语言模型协作，利用文本信息提升时间序列预测精度和可解释性，适用于金融等领域的多模态预测任务。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 675, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1569, \"height\": 751, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 774, \"height\": 837, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 717, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 373, \"height\": 856, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1687, \"height\": 1025, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1303, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1661, \"height\": 1066, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1768, \"height\": 981, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1602, \"height\": 1901, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1571, \"height\": 778, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1401, \"height\": 949, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1325, \"height\": 708, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1320, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1498, \"height\": 744, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1137, \"height\": 740, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1240, \"height\": 753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dhrumwdoxy/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1663, \"height\": 842, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-dhrumwdoxy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 735, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dhrumwdoxy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 844, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dhrumwdoxy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1787, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dhrumwdoxy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1580, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dhrumwdoxy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 896, \"height\": 228, \"label\": \"Table\"}]"
motivation: 多模态时间序列预测中，文本信息未被充分利用，影响预测效果。
method: 提出TimeXL，包含原型编码器处理时间序列和文本，再由预测大模型精化预测，并生成可解释依据。
result: 预测精度提高，同时提供基于案例的 rationale，增强模型可解释性。
conclusion: TimeXL有效融合文本和时间序列信息，为金融预测提供更准确和可解释的方案。
---

## Abstract
Time series analysis provides essential insights for real-world system dynamics and informs downstream decision-making, yet most existing methods often overlook the rich contextual signals present in auxiliary modalities (e.g., financial news or domain-specific documents). To bridge this gap, we introduce TimeXL, a multi-modal prediction framework that integrates a prototype-based time series encoder with three collaborating Large Language Models (LLMs) to deliver more accurate predictions and interpretable explanations. First, a multi-modal prototype-based encoder processes both time series and textual inputs to generate preliminary forecasts alongside case-based rationales. These outputs then feed into a prediction LLM, which refines the forecasts by reasoning over the encoder’s predictions and explanations. Next, a reflection LLM compares the predicted values against the ground truth, identifying textual inconsistencies or noise. Guided by this feedback, a refinement LLM iteratively enhances text quality and triggers encoder retraining. This closed-loop workflow—prediction, critique (reflect), and refinement—continuously boosts the framework’s performance and interpretability. Empirical evaluations on four real-world datasets demonstrate that TimeXL achieves up to 8.9 \% improvement in AUC and produces human-centric, multi-modal explanations, highlighting the power of LLM-driven reasoning for time series prediction.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有时间序列预测方法大多仅利用数值型时序数据，忽略了辅助模态（如金融新闻、医疗报告等文本）中丰富的上下文信号，且缺乏可解释性——无法说明“为什么”预测某个结果。
- **研究动机**：现实世界的时间序列（如天气、金融、医疗）常受外部信息影响，文本描述可提供关键线索；但传统多模态方法只关注预测精度，缺少系统性的推理与解释机制。同时，大语言模型（LLM）具备强大的文本推理能力，可作为可解释性的自然载体。
- **整体含义**：提出 **TimeXL** 框架，通过“预测-反思-精炼”的闭环流程，将**原型驱动的可解释编码器**与**三个协作的LLM代理**相结合，实现**更准确的预测**并生成**人类可读的多模态解释**。

## 2. 论文提出的方法论

### 核心思想
- 采用**原型学习**（prototype learning）在时间序列和文本模态中分别学习可解释的原型，每个原型对应一个真实训练样本的片段。
- 利用**三个LLM代理**（预测、反思、精炼）与编码器交互，形成闭环：预测→批评→精炼→再训练，持续提升性能和解释质量。

### 关键技术细节
1. **多模态原型编码器（Multi-modal Prototype-based Encoder）**
   - 时间序列编码器 \(E_\theta\) 和文本编码器 \(E_\phi\) 均为卷积网络，提取片段级表示 \(z_i\)。
   - 对每个类别 \(c\) 学习两组原型：时间序列原型 \(P_{time}^{(c)} \in \mathbb{R}^{k \times h}\) 和文本原型 \(P_{text}^{(c)} \in \mathbb{R}^{k' \times h'}\)。
   - 相似度计算：\( \text{Sim}_{i,j}^{(c)} = \exp(-\|p_i^{(c)} - z_j\|_2^2) \)，取每类的最大相似度聚合。
   - 通过非负全连接层融合两类相似度，输出分类概率 \(\hat{y}_{\text{enc}}\)。
   - 损失函数包括交叉熵 + 聚类正则化（\(L_c\)）+ 证据正则化（\(L_e\)）+ 多样性正则化（\(L_d\)）。
   - 训练后，每个原型被投影到与其最相似的训练片段上（prototype projection），赋予具体语义。

2. **预测LLM（Prediction LLM）**
   - 接收输入文本 \(s\) 和从原型编码器检索的 top-\(\omega\) 文本原型-片段对（作为解释）。
   - 输出预测 \(\hat{y}_{\text{LLM}}\)。
   - 最终预测为融合：\(\hat{y} = \alpha \hat{y}_{\text{enc}} + (1-\alpha) \hat{y}_{\text{LLM}}\)。

3. **反思LLM（Reflection LLM）**
   - 输入：当前文本 \(s_i\)、预测 \(\hat{y}_{\text{LLM}}\)、真实标签 \(y\)。
   - 输出：反思报告（Refl），分析文本中导致正确/错误预测的关键短语。

4. **精炼LLM（Refinement LLM）**
   - 根据反思报告，对原始文本进行筛选和重写，生成更高质量的文本 \(s_{i+1}\)。
   - 用精炼后的文本重新训练多模态编码器，形成迭代优化。

### 算法流程（文字说明）
- 初始化：原始文本 \(s_0 = s\)，迭代次数 \(i=0\)。
- 循环直到满足停止条件：
  1. 用当前文本训练编码器 \(M_{\text{enc}}\)。
  2. 推理得到预测 \(\hat{y}_{\text{enc}}\) 和解释 \(\text{expl}_{s_i}\)。
  3. 预测LLM结合文本和解释输出 \(\hat{y}_{\text{LLM}}\)。
  4. 融合预测 \(\hat{y}\)。
  5. 反思LLM生成反思报告。
  6. 精炼LLM生成新文本 \(s_{i+1}\)。
- 测试阶段：使用训练集上最佳迭代的反思报告精炼测试文本。

## 3. 实验设计

### 数据集
| 数据集 | 领域 | 任务 | 样本量 | 标签分布 |
|--------|------|------|--------|----------|
| Weather (纽约天气) | 天气 | 预测未来24小时是否下雨 | 5,216小时 | 雨(24.26%) / 非雨(75.74%) |
| Finance (原材料价格) | 金融 | 预测未来一日价格趋势（升/降/平） | 1,876天 | 升36.7% / 降34.1% / 平29.2% |
| Healthcare (Test-Positive) | 医疗 | 预测下周阳性率是否超过均值 | 4,447周 | 超过(34.23%) / 未超过(65.77%) |
| Healthcare (Mortality) | 医疗 | 预测下周死亡率是否超过均值 | 4,395周 | 超过(30.67%) / 未超过(69.33%) |

### 对比方法
- **纯时间序列方法**：DLinear, Autoformer, Crossformer, TimesNet, iTransformer, TSMixer, FreTS, PatchTST
- **LLM方法**：LLMTime (零样本), PromptCast (零样本), OFA, Time-LLM, TimeCMA
- **多模态方法**：MM-iTransformer, MM-PatchTST, TimeCAP
- **评估指标**：F1分数和AUC（因类别不平衡）

### 实验设置
- 训练/验证/测试：6/2/2划分
- 文本嵌入：Weather和Healthcare用BERT，Finance用Sentence-BERT
- LLM：GPT-4o (gpt-4o-2024-08-06)，温度0.7（生成）和0.3（预测）

## 4. 资源与算力

- 论文在 **Appendix A.4** 中明确说明：
  - **服务器**：TensorEX服务器
  - **CPU**：2个 Intel Xeon Gold 5218R（各20核）
  - **内存**：512GB
  - **GPU**：4块 NVIDIA RTX A6000（各48GB显存）
- **训练时长**：文中未提及具体训练时间（如小时数或迭代次数对应的实际耗时），因此无法从论文中获取。
- 注意：LLM推理通过 OpenAI API 调用，不占用本地GPU训练，但需要网络和API费用。

## 5. 实验数量与充分性

### 实验数量
- **主实验（表1）**：在4个数据集上，对比了15种方法，每个数据集报告F1和AUC。
- **消融实验（表2）**：5种变体（仅编码器、仅LLM文本、文本+原型、融合-选最优、完整TimeXL），在4个数据集上报告F1。
- **额外消融**：
  - 学习目标消融（图6）：6种变体（分别去除各类正则项），在4个数据集上报告F1和AUC。
  - 原型数量影响（图7）：分析top-ω对LLM预测的影响，2个数据集。
- **迭代分析（图5）**：展示了文本质量和整体性能随迭代的变化（默认最大迭代τ未明确，但从图看约3-5轮）。
- **案例研究**：对Weather和Finance各提供一个详细多模态解释案例。
- **回归演示（Appendix F）**：在Finance数据集上测试回归任务，报告F1、AUC、RMSE、MAE、MAPE。

### 充分性与公平性
- **充分性**：实验覆盖分类和回归任务、多样化的真实场景、详尽的消融和迭代分析，以及可视化解释，较为全面。
- **公平性**：
  - 对比的方法均为近年的SOTA，且作者声称使用各论文默认实现或官方代码。
  - 但未说明是否对所有基线进行了同样的超参数调优（如学习率搜索范围相同），可能存在调优差异。
  - 多模态方法中（MM-iTransformer等）由作者自行实现，可能引入偏差。
  - 未与最新视觉-语言模型（如GPT-4V）或多模态基础模型进行比较（尽管后者可能不直接适用于时间序列）。
- **偏差风险**：四个数据集样本量均较小（千级），且天气和医疗数据时间跨度有限，结果泛化性需更多验证。

## 6. 论文的主要结论与发现

1. **性能提升**：TimeXL在所有四个数据集上取得最高F1和AUC，相比最优基线TimeCAP，AUC提升最高达8.9%（Weather数据集）。在Healthcare (Test-Positive)上AUC达到0.996，接近完美。
2. **可解释性**：学习到的多模态原型与真实场景高度一致（如天气原型区分“雨”与“非雨”的模式），能够提供人类可理解的“案例推理”解释。
3. **闭环流程有效**：迭代式反思-精炼可显著提升文本质量（零样本预测准确率），进而提高编码器性能和最终预测。
4. **组件贡献**：消融实验表明，每个组件（编码器、文本+原型、融合）均对最终性能有正向贡献，原型信息尤为重要。

## 7. 优点

- **创新性**：首次将原型学习与三个LLM代理结合形成闭环，同时解决多模态融合、可解释性、文本噪声三大问题。
- **可解释性突出**：原型不仅用于预测，还可直接作为“相似案例”展示，比注意力热图等更直观。
- **实验设计扎实**：涵盖多种数据集、充分消融（学习目标、原型数量、组件）、迭代分析、案例可视化，且证明了方法在回归任务上的潜在适用性。
- **公平性考量**：对比方法包括时间序列专用模型、多模态变体及多种LLM方法，覆盖面广。

## 8. 不足与局限

### 实验覆盖
- **数据集规模和多样性有限**：四个数据集均为千级样本（时间点），且来自天气、金融、医疗三个领域，缺乏大规模、高维、多通道的复杂场景（如传感器网络、电力负荷）。
- **对比基线可能不全**：未与最新的多模态基础模型（如GPT-4V、Claude 3）或多模态时间序列大模型（如Chronos多模态版）比较，因为大部分未公开发布或不适配。
- **回归任务仅做初步演示**：只在Finance一个数据集上测试，且未与专门回归模型对比。
- **消融实验仅报告F1**：表2中AUC未全给出，虽然文本提到“full results in Table 4”，但表2本身有缺失。

### 方法局限
- **高成本**：依赖GPT-4o API，每次预测和迭代均需多次调用，且训练阶段需要多轮重新训练编码器，计算成本高。
- **可扩展性**：原型数量k和k′需要手动调整（如5~20），可能对超参数敏感。
- **文本质量依赖LLM**：反思和精炼LLM的输出质量直接影响后续训练，若LLM产生错误或偏见，可能放大偏差。
- **迭代终止条件凭经验**：算法中仅凭“improvement observed”和最大迭代次数决定，缺乏理论保证。

### 公平性风险
- **LLM偏见**：GPT-4o可能对某些文本模式有偏好（如对“下降”等词过度反应），导致反思和精炼引入系统性偏差。
- **数据分布假设**：所有数据假设时间平稳，但金融市场和医疗疫情数据可能存在时变模式，未验证方法的鲁棒性。

（完）
