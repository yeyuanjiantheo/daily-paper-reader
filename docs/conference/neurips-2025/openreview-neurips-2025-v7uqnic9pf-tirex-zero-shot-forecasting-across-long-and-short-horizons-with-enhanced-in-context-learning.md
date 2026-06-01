---
title: "TiRex: Zero-Shot Forecasting Across Long and Short Horizons with Enhanced In-Context Learning"
title_zh: TiRex：通过增强上下文学习实现长短时间跨度的零样本预测
authors: "Andreas Auer, Patrick Podest, Daniel Klotz, Sebastian Böck, Günter Klambauer, Sepp Hochreiter"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=v7UqniC9pF"
tags: ["query:qf"]
score: 6.0
evidence: 基于LSTM的零样本时间序列预测
tldr: 本文提出TiRex，一种基于LSTM的零样本时间序列预测方法，通过增强上下文学习实现长短时间跨度的外推预测。与现有基于Transformer的方法相比，LSTM架构在时间序列上下文中更具优势，在多个真实世界数据集上取得了最优结果，尤其在长期预测和少量样本场景下表现突出。该方法可应用于金融数据匮乏情况下的波动率或收益率预测，但需进一步针对金融序列特性调整。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1453, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1454, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1455, \"height\": 860, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 725, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 691, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1275, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1449, \"height\": 853, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1456, \"height\": 872, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1454, \"height\": 861, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1451, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1453, \"height\": 910, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1463, \"height\": 999, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1455, \"height\": 844, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1442, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1436, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1449, \"height\": 1460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1456, \"height\": 696, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1462, \"height\": 1098, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1466, \"height\": 2118, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7uqnic9pf/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1464, \"height\": 2099, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1464, \"height\": 845, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 834, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1127, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 582, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 807, \"height\": 1111, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 787, \"height\": 1574, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1180, \"height\": 2271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 660, \"height\": 1077, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1583, \"height\": 1655, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1512, \"height\": 1628, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1580, \"height\": 1653, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1511, \"height\": 1628, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1394, \"height\": 1632, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1307, \"height\": 1604, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1375, \"height\": 1633, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1303, \"height\": 1604, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1452, \"height\": 1020, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7uqnic9pf/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1452, \"height\": 1020, \"label\": \"Table\"}]"
motivation: 现有零样本时间序列预测方法多基于Transformer，但LSTM在时间序列上表现更佳。
method: 设计基于LSTM的上下文学习架构，利用历史序列作为上下文直接预测未来值。
result: 在多个基准数据集上超越现有零样本方法，尤其在长序列预测上优势明显。
conclusion: 为时间序列的零样本预测提供了新基线，但金融特定任务需要进一步验证。
---

## Abstract
In-context learning, the ability of large language models to perform tasks using only examples provided in the prompt, has recently been adapted for time series forecasting. 
This paradigm enables zero-shot prediction, where past values serve as context for forecasting future values, 
making powerful forecasting tools accessible to non-experts and increasing the performance when training data are scarce.
Most existing zero-shot forecasting approaches rely on transformer architectures, which, despite their success in language, often fall short of expectations in time series forecasting, where recurrent models like LSTMs frequently have the edge. Conversely, while LSTMs are well-suited for time series modeling due to their state-tracking capabilities, they lack strong in-context learning abilities.
We introduce *TiRex* that closes this gap by leveraging xLSTM, an enhanced LSTM with competitive in-context learning skills. Unlike transformers, state-space models, or parallelizable RNNs such as RWKV, TiRex retains state tracking, a critical property for long-horizon forecasting. To further facilitate its state-tracking ability, we propose a training-time masking strategy called CPM.
TiRex sets a new state of the art in zero-shot time series forecasting on the Hugging Face benchmarks *GiftEval* and *Chronos-ZS*, outperforming significantly larger models including *TabPFN-TS* (Prior Labs), *Chronos Bolt* (Amazon), *TimesFM* (Google), and *Moirai* (Salesforce) across both short- and long-term forecasts.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将根据您提供的论文内容，生成一份结构化、深入且客观的中文总结。

***

### **论文：TiRex: Zero-Shot Forecasting Across Long and Short Horizons with Enhanced In-Context Learning**

#### **1. 论文的核心问题与整体含义（研究动机和背景）**

*   **核心问题**：当前，基于大规模预训练的零样本（Zero-Shot）时间序列预测模型主要依赖Transformer架构。然而，尽管Transformer在自然语言处理中取得巨大成功，但在时间序列预测任务上，其性能往往不如循环神经网络（RNN），特别是长短期记忆网络（LSTM）。LSTM因其天然的**状态跟踪（State-Tracking）** 能力，在捕捉长期依赖和周期模式方面表现优异，但这恰恰是Transformer等并行架构的弱点。
*   **研究动机**：LSTM虽然擅长时间序列建模，但缺乏强大的**上下文学习（In-Context Learning, ICL）** 能力——即仅凭提示中提供的少量示例就能执行任务的能力，而这正是实现零样本预测的关键。因此，如何同时拥有LSTM的时序建模优势和Transformer的ICL能力，是该领域的主要挑战。
*   **整体含义**：本论文提出TiRex模型，旨在弥合这一差距。它通过采用增强版的LSTM——**xLSTM**，作为核心架构，同时具备强大的状态跟踪和上下文学习能力，从而在零样本时间序列预测任务上，特别是长时域预测上，实现超越现有Transformer系列模型的表现。

#### **2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程**

*   **核心思想**：利用xLSTM（特别是其sLSTM变体）替换Transformer作为零样本预测模型的主干网络，以同时获得LSTM的状态跟踪能力和接近Transformer的上下文学习能力。并为此设计了专门的训练策略和数据增强方法来充分发挥其潜力。

*   **关键技术细节**：
    1.  **架构（TiRex）**：
        *   采用**解码器（Decoder-only）** 架构，堆叠多个**xLSTM块**（具体使用sLSTM模块）。
        *   **输入层**：对输入时间序列进行**Z-score归一化（实例归一化）** 增强鲁棒性；将序列分割成**非重叠**的窗口（patch），并通过一个**残差块**映射到特征空间。缺失值通过一个二进制掩码（mask）进行标记。
        *   **输出层**：将xLSTM的输出token映射回原始时间尺度，输出**9个等距分位数**（0.1到0.9），实现**概率预测**。
        *   **损失函数**：使用**分位数损失（Quantile Loss）** 来优化模型参数。

    2.  **多分块预测（Multi-Patch Horizon Forecasts）**：
        *   当预测长度超过一个输出窗口时，将未来的输入视为**缺失值**。
        *   模型利用其内部记忆状态在预测块之间传播**预测信息和不确定性**，从而避免误差积累，保持概率预测的连贯性。

    3.  **连续分块掩码（Contiguous Patch Masking, CPM）**：
        *   **核心作用**：增强xLSTM的**稳定多分块预测能力**，特别针对长时域预测。
        *   **算法流程**：在训练时，对于每个样本，随机采样一个掩码长度（`cmask`）和一个掩码概率（`pmask`），然后生成连续的掩码。这些掩码块在输入中被标记为“缺失值”，模拟了多步预测时的输入结构，迫使模型学会基于不完整的上下文进行长期推理。

    4.  **数据增强 (Data Augmentation)**：
        *   受计算机视觉领域预训练中数据增强成功应用的启发，提出了三种专门用于时间序列的增强方法：
            *   **振幅调制（Amplitude Modulation）**：引入趋势和变化点，改变序列的尺度。
            *   **审查增强（Censor Augmentation）**：以随机阈值对序列进行截断（censoring），模拟数据缺失或异常值。
            *   **尖峰注入（Spike Injection）**：增加周期性的、短时、尖锐的脉冲信号，提升模型对罕见突发事件的敏感度。

#### **3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法**

*   **使用的Benchmarks（基准）**：两个来自HuggingFace的公共标准基准。
    1.  **Chronos-ZS**：包含27个数据集，主要用于**短时域**预测。
    2.  **GiftEval**：包含24个数据集，覆盖**短、中、长**三种时域和多种频率（共97个评估设置）。为避免数据泄露，去除了与训练集重叠的16个设置，得到**GiftEval-ZS**。最终，TiRex在这两个基准（以及完整的GiftEval基准）上都进行了评估。
*   **评价指标**：使用**MASE**（平均绝对尺度误差）评估点预测性能，使用**CRPS**（连续分级概率评分，近似为加权分位数损失WQL）评估概率预测性能。最终通过几何平均和平均排名进行汇总。
*   **对比方法**：对比了全面的最新模型，分为几类：
    *   **零样本预训练模型**：Chronos, Chronos-Bolt, TimesFM (v1.0, v2.0), Moirai, TabPFN-TS, TTM等。
    *   **任务特定模型**（在每个数据集上单独训练）：PatchTST, TFT, DLinear, DeepAR, N-BEATS等（这些提供不对称比较，用于上下文参考）。
    *   **统计模型**：Auto-ARIMA, Seasonal Naive等。

#### **4. 资源与算力**

*   论文附录C.4中提及，所有实验在**Nvidia A40和H100 GPU**上进行，A40足以完成所有训练。CPU要求为64核。
*   **训练过程**：预训练共**500,000步**，使用**256**的批量大小。未明确指出使用了多少块GPU进行单次训练，也未提供总的GPU小时数。
*   作者承认，由于计算资源的限制，**未进行大规模的超参数调优**，仅对关键参数进行了敏感性分析。

#### **5. 实验数量与充分性**

*   **实验数量**：非常丰富。
    *   **主实验**：在两个大型基准（Chronos-ZS和GiftEval-ZS）的多个子任务上进行评估，涵盖了短、中、长期预测以及多变量数据。
    *   **消融实验（Ablation Study）**：系统地验证了模型三个核心组件：**CPM策略**、**数据增强**和**主干网络**（对比sLSTM、mLSTM、Transformer、不同xLSTM组合以及Chronos-Bolt架构）。
    *   **敏感性分析**：对CPM的超参数（`pmax_mask`, `cmax_mask`）和数据增强的应用概率进行了分析。
    *   **推理效率实验**：比较了不同模型的GPU内存占用和推理时间。
    *   **微调实验**：在预训练基础上进行了微调并对比。
*   **充分性与客观性**：
    *   **充分性**：实验设计相当全面，覆盖了模型性能的各个方面。统计显著性方面，TiRex报告了**6个随机种子的均值和标准差**，并在消融实验中将性能退化超过三倍标准差的视为显著。
    *   **公平性**：作者考虑了**数据泄漏（Zero-Shot Leak）** 问题，将GiftEval中与训练集重叠的部分排除，得到GiftEval-ZS，并明确指出Moirai、TimesFM等模型在Chronos-ZS上存在较高重叠（如Moirai达82%），这确保了对比的相对公平。但需要注意的是，公开数据显示的基准结果来自模型作者，TiRex作者并未复现所有对比模型的运行结果，这存在因实现差异导致结果不一致的潜在风险。

#### **6. 论文的主要结论与发现**

1.  **性能SOTA**：TiRex在**GiftEval-ZS**和**Chronos-ZS**两个标准零样本预测基准上取得了**新的最佳成绩**，在概率预测（CRPS）和点预测（MASE）指标上均大幅超越现有方法。
2.  **长短兼顾**：TiRex是唯一一个**同时擅长短时域和长时域预测**的模型，其他模型往往只在一个方面表现突出。尤其在长时域预测上，它首次有零样本模型超越了领域特定的PatchTST和TFT模型。
3.  **效率优势**：尽管性能优异，TiRex模型参数量仅为**3500万**，远小于Chronos-Bolt-Base (2亿) 和 TimesFM-2.0 (5亿)。这使得其在GPU内存和推理速度上具备显著优势（比TimesFM-2.0快11倍以上）。
4.  **组件有效性**：消融实验证实了**xLSTM（sLSTM）架构**、**CPM训练策略**和**数据增强**分别对模型性能有显著贡献，缺一不可。
5.  **多步预测能力**：CPM训练策略使模型能利用内部记忆进行鲁棒的多步预测，有效传播不确定性，避免了自回归误差积累和分位数坍塌的问题。

#### **7. 优点：方法或实验设计上有哪些亮点**

*   **方法论创新**：
    *   **架构选择**：大胆选用了xLSTM作为零样本预测的主干架构，巧妙地将LSTM的**状态跟踪**优势和xLSTM的**上下文学习**能力结合起来，解决了当前领域的一个核心矛盾。
    *   **CPM策略**：提出的**连续分块掩码**策略是训练多步预测模型的一个精巧设计，它并非直接模拟未来输入，而是通过随机遮蔽连续块来激发模型对长期依赖和不确定性的建模能力。
    *   **数据增强**：针对时间序列设计的三种增强方法（特别是尖峰注入）非常具有针对性，提升了模型对未见过的动态模式的鲁棒性。
*   **实验严谨性**：
    *   **基准选择**：使用了两个具有公开排行榜的标准基准，结果可复现、可比较。
    *   **数据泄露处理**：明确区分了**零样本泄漏**模型，并专门建立了**GiftEval-ZS**子集，确保了评估的公平性。
    *   **统计分析**：报告了多次运行的均值和标准差，并为关键消融实验提供了统计显著性阈值，增强了结果的可信度。
    *   **全面性**：实验覆盖了性能对比、推理效率、消融、敏感性分析等多个维度。

#### **8. 不足与局限：包括实验覆盖、偏差风险、应用限制等**

*   **超参数调优不足**：作者承认因计算资源限制，未对超参数进行大规模搜索，这可能意味着最佳性能尚未完全挖掘。
*   **多变量处理**：当前仅专注于**单变量**时间序列模型，虽然通过独立处理每个变量在部分多变量任务上表现良好，但这并非最优解法。未来应考虑设计原生支持多变量的输入结构。
*   **计算成本**：尽管模型参数少，但xLSTM（特别是sLSTM）的前向传播本身可能涉及复杂的循环计算，论文未详细比较与Transformer的**实际训练成本**。
*   **数据泄露风险**：尽管作者尽力排除，但论文提到的高频数据（如‘solar’）可能存在的“难以验证”的重叠，依然存在潜在的数据污染风险，影响“零样本”评价的绝对纯净性。
*   **应用限制**：论文主要关注于通用时间序列的预测，没有深入探讨其在高频金融或其他特殊领域的具体表现和适用性。其有效性未能在更多元化的（如非平稳性极强的、存在时间戳变化的）真实世界场景中得到充分验证。
*   **定性分析局限**：文中的定性分析（Figure 1）仅展示了个例，缺乏对大量失败案例的系统性分析，未能解释模型在哪些数据模式上表现最差。

（完）
