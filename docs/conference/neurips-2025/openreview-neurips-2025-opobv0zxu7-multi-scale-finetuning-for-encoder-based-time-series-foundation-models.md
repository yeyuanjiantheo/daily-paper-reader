---
title: Multi-Scale Finetuning for Encoder-based Time Series Foundation Models
title_zh: 基于编码器的时间序列基础模型的多尺度微调
authors: "Zhongzheng Qiao, Chenghao Liu, Yiming Zhang, Ming Jin, Quang Pham, Qingsong Wen, Ponnuthurai Nagaratnam Suganthan, Xudong Jiang, Savitha Ramasamy"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=OPOBV0zXu7"
tags: ["query:qf"]
score: 6.0
evidence: 时间序列基础模型的多尺度微调方法可应用于金融预测
tldr: 针对编码器基础模型的时间序列预测，该论文提出多尺度微调方法，通过显式建模不同采样尺度的时序模式来避免过拟合。实验表明该方法比朴素微调效果更佳，为金融时间序列波动率预测等下游任务提供了有效策略。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-opobv0zxu7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1313, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-opobv0zxu7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1433, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-opobv0zxu7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1386, \"height\": 622, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-opobv0zxu7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 704, \"height\": 236, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-opobv0zxu7/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 689, \"height\": 233, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-opobv0zxu7/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 694, \"height\": 247, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-opobv0zxu7/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1451, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-opobv0zxu7/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1432, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-opobv0zxu7/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1431, \"height\": 491, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-opobv0zxu7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1273, \"height\": 1022, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-opobv0zxu7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1273, \"height\": 672, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-opobv0zxu7/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1415, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-opobv0zxu7/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1123, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-opobv0zxu7/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1201, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-opobv0zxu7/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1447, \"height\": 453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-opobv0zxu7/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 698, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-opobv0zxu7/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-opobv0zxu7/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1440, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-opobv0zxu7/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1437, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-opobv0zxu7/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1437, \"height\": 527, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-opobv0zxu7/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 821, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-opobv0zxu7/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1449, \"height\": 651, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-opobv0zxu7/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1448, \"height\": 650, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-opobv0zxu7/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1449, \"height\": 402, \"label\": \"Table\"}]"
motivation: 现有微调方法未能充分利用时间序列基础模型的多尺度预测能力。
method: 从因果角度分析微调过程，提出显式建模多尺度时间模式的微调方法。
result: 在多个预测任务上超越朴素微调基线。
conclusion: 多尺度微调是提升时间序列基础模型下游性能的关键。
---

## Abstract
Time series foundation models (TSFMs) demonstrate impressive zero-shot performance for time series forecasting. However, an important yet underexplored challenge is how to effectively finetune TSFMs on specific downstream tasks. While naive finetuning can yield performance gains, we argue that it falls short of fully leveraging TSFMs' capabilities, often resulting in overfitting and suboptimal performance. Given the diverse temporal patterns across sampling scales and the inherent multi-scale forecasting capabilities of TSFMs, we adopt a causal perspective to analyze finetuning process, through which we highlight the critical importance of explicitly modeling multiple scales and reveal the shortcomings of naive approaches. Focusing on encoder-based TSFMs, we propose Multiscale finetuning (MSFT), a simple yet general framework that explicitly integrates multi-scale modeling into the finetuning process. Experimental results on three different backbones (Moirai, Moment and Units) demonstrate that TSFMs finetuned with MSFT not only outperform naive and typical parameter efficient finetuning methods but also surpass state-of-the-art deep learning methods. Codes are available at https://github.com/zqiao11/MSFT.

---

## 论文详细总结（自动生成）

# 论文《Multi-Scale Finetuning for Encoder-based Time Series Foundation Models》详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究背景**：时间序列基础模型（TSFMs）在零样本预测中表现出色，但如何针对特定下游任务有效微调仍未被充分探索。现有工作多聚焦于预训练和零样本评估，对微调关注有限。
- **核心问题**：简单的朴素微调（如全参微调、线性探测等）未能充分利用TSFMs的多尺度预测能力，容易过拟合，且忽略了时间序列固有的多尺度特性（不同采样尺度下呈现不同时序模式）。
- **因果视角**：作者构建了结构因果模型（SCM），指出采样尺度 **S** 是一个混杂因子，同时影响输入上下文 **X** 和模型激活的知识 **M**，导致朴素微调学到的 **P(Y|X)** 含有虚假关联。因此需要因果干预，通过后门调整得到 **P(Y|do(X))**，即显式建模多尺度以消除混杂。
- **挑战**：多尺度补丁（patch）的粒度不同，直接跨尺度自注意力会因时间索引错位而引入虚假依赖，且需要有效聚合多尺度预测。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
基于后门调整公式：
**P(Y|do(X)) = Σ_s P(Y|X, S=s, M=g(X,s)) P(s)**
其中 **g** 为激活尺度特定知识的函数。通过将原始序列下采样为多个尺度（S₀, S₁, …, Sₖ），并设计模块化组件来实现该干预。

### 关键技术细节（MSFT框架）

| 组件 | 功能 | 实现方式 |
|------|------|----------|
| **尺度特定知识激活** | 激活预训练模型内对应尺度的知识 | 冻结预训练输入投影，为每个尺度添加独立的线性适配器（Linear_i）；在注意力层为每个尺度添加独立的LoRA模块（W_Q, W_K, W_V各一个） |
| **解耦的令牌依赖建模** | 避免跨尺度时间索引错位带来的虚假依赖 | (1) **In-scale Attention**：使用注意力掩码 **M_in**，仅允许同尺度内的令牌相互注意力；(2) **Cross-scale Aggregator**：通过粗到细（C2F，重复粗令牌对齐细尺度）和细到粗（F2C，平均池化细令牌对齐粗尺度）两个方向迭代融合相邻尺度信息 |
| **多尺度混合** | 聚合各尺度预测结果 | 每个尺度独立生成预测 **Ŷᵢ**，使用可学习权重 **wᵢ**（对应P(s)）加权求和；训练时损失为 **L_total = Σ wᵢ L_predᵢ**；推理时对各尺度预测上采样后加权求和 |

### 算法流程（文字说明）
1. 对输入（X, Y）进行平均池化下采样，得到K+1个尺度（包括原尺度）。
2. 对每个尺度进行补丁分割，通过预训练的InProject和尺度特定线性适配器得到嵌入。
3. 将所有尺度的嵌入拼接，并附上尺度索引。
4. 通过L个MSFT注意力块：每个块内先做尺度特定LoRA的QKV投影，再做In-scale掩码注意力，然后通过C2F和F2C两个方向进行跨尺度聚合，最后合并。
5. 从最后一层嵌入中分离各尺度，各尺度独立通过输出投影得到预测，计算加权损失。
6. 推理时，对各尺度预测上采样后加权求和得到最终预测。

（不需要公式，以上文字说明已覆盖）

## 3. 实验设计

### 数据集与场景
- **长序列预测（LSF）**：ETTm1, ETTm2, ETTh1, ETTh2, Electricity, Weather（6个数据集，每个含4种预测长度96/192/336/720）。
- **概率预测（PF）**：Electricity, Solar, Weather, Istanbul Traffic, Turkey Power（5个数据集，使用滚动评估窗口）。
- 所有测试集均不包含在TSFMs的预训练数据中，确保公平。

### Benchmark与对比方法
- **TSFMs基座**：MOIRAI Small/Base, MOMENT, UNITS。
- **微调方法对比**：零样本（Zero-shot）、全微调、线性探测、提示微调、LoRA、AdaLoRA、MSFT（本文）。
- **传统深度学习方法**：DLinear, PatchTST, iTransformer, TimeMixer, SimpleTM等。

### 评估指标
- LSF：MSE, MAE。
- PF：CRPS, MSIS, sMAPE, MASE, ND, NRMSE等。

## 4. 资源与算力

文中附录B.6说明：
- **服务器配置**：AMD EPYC 7763 CPU（64核128线程），4块NVIDIA A40 GPU（每块40GB显存）。
- **未明确**：总训练时长或每轮迭代时间，仅给出训练速度比较（Table 8），例如MSFT-S在ETTm1上为103.53 ms/iter。

## 5. 实验数量与充分性

实验非常充分且客观：
- **主要实验**：LSF共6个数据集×4种预测长度=24个结果，PF共5个数据集，均报告多个指标。
- **消融实验**：Table 3列出10种变体（冻结/共享/替换各组件），每个变体在3个数据集上重复3次，报告均值和标准差（Table 11），验证了各模块有效性。
- **额外分析**：
  - 不同下采样方法比较（平均池化、最大池化、首步采样）。
  - 尺度数量K的影响（图4）。
  - 注意力机制对比（直接自注意力、对齐索引注意力、本文解耦注意力）。
  - 计算效率对比（训练/测试速度、GPU显存）。
  - 跨数据集迁移实验（Table 12），验证知识遗忘情况。
- **公平性**：所有微调方法均使用相同的数据划分、优化器、早停等设置，避免数据泄露。

结论：实验设计全面，消融充分，统计鲁棒性较好（标准差小），对比公平。

## 6. 主要结论与发现

- **MSFT显著优于所有对比微调方法**：在全部LSF和PF数据集上取得最佳结果，且超越从头训练的SOTA方法。
- **在分钟级数据上改进更突出**：例如ETTm1（15分钟）上MSFT比全微调MSE降低6.8%，而小时级数据改进较小。
- **因果视角有效**：通过显式建模多尺度消除了尺度混杂，避免了朴素微调中的虚假关联。
- **通用性强**：在MOIRAI, MOMENT, UNITS三种不同结构上均有效。
- **轻量级**：仅增加少量可学习参数（如表9显示4.4M vs 全微调13.8M），训练速度可接受。

## 7. 优点

1. **理论创新**：首次将因果视角引入TSFM微调，清晰解释了朴素微调失效的原因，并给出基于后门调整的解决方案。
2. **方法通用**：不依赖特定模型结构，可即插即用于多种编码器TSFM。
3. **模块化设计**：冻结主参数，仅添加适配器、LoRA、注意力掩码等，易于实现和扩展。
4. **性能显著**：在多个标准和现实数据集上稳定提升，尤其适用于高分辨率数据。
5. **实验严谨**：消融深入，统计报告标准差，计算效率对比完整。

## 8. 不足与局限

1. **仅适用于编码器模型**：对解码器（如TimesFM, Lag-Llama）需额外适配（附录E给出了初步思路但未验证），限制推广范围。
2. **计算开销增加**：多尺度输入使令牌数增加，注意力和GPU显存消耗上升（Table 9显示MSFT训练速度约4.6 it/s vs LoRA的11.1 it/s），存在性能-效率权衡。
3. **对部分模型改进有限**：在MOMENT上改进较小，作者归因于其固定上下文长度的预训练方式限制。
4. **跨数据集迁移风险**：跨数据集迁移实验（Table 12）显示MSFT在某些设定下性能下降，说明多尺度知识不一定泛化到异构数据集。
5. **未讨论**：未涉及多变量场景下的通道交互（仅使用单变量模式），也未测试极长上下文或极端稀疏数据。
6. **未公开**：总训练时间、单次微调所需GPU小时数等细节，复现成本不够透明。

（完）
