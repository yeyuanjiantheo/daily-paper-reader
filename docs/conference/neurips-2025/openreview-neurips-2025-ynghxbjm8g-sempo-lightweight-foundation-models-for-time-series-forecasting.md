---
title: "SEMPO: Lightweight Foundation Models for Time Series Forecasting"
title_zh: SEMPO：轻量级时间序列预测基础模型
authors: "Hui He, Kun Yi, Yuanchi Ma, Qi Zhang, Zhendong Niu, Guansong Pang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=YngHXbJM8g"
tags: ["query:qf"]
score: 7.0
evidence: 轻量级时间序列预测基础模型
tldr: 现有的时间序列基础模型参数量大且依赖大规模预训练数据，部署成本高。本文提出SEMPO，一种轻量级基础模型，通过能量感知谱分解模块实现小样本预训练，同时保持强大的通用预测能力。实验表明SEMPO在多个下游任务中性能与大规模模型持平，而参数量大幅减少，为资源受限环境下的时间序列预测提供了可行方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ynghxbjm8g/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ynghxbjm8g/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 821, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ynghxbjm8g/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 666, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ynghxbjm8g/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1479, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ynghxbjm8g/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 625, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ynghxbjm8g/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 694, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ynghxbjm8g/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1459, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ynghxbjm8g/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1479, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ynghxbjm8g/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1381, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ynghxbjm8g/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 692, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ynghxbjm8g/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1451, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ynghxbjm8g/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1410, \"height\": 1501, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ynghxbjm8g/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1482, \"height\": 481, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ynghxbjm8g/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1486, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ynghxbjm8g/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1458, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ynghxbjm8g/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 516, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ynghxbjm8g/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1296, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ynghxbjm8g/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1435, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ynghxbjm8g/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 674, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ynghxbjm8g/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1493, \"height\": 1287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ynghxbjm8g/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1270, \"height\": 872, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ynghxbjm8g/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1455, \"height\": 554, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ynghxbjm8g/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1439, \"height\": 1076, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ynghxbjm8g/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1342, \"height\": 853, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ynghxbjm8g/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1441, \"height\": 872, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ynghxbjm8g/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1531, \"height\": 1254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ynghxbjm8g/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1531, \"height\": 1260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ynghxbjm8g/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1406, \"height\": 1167, \"label\": \"Table\"}]"
motivation: 现有时间序列基础模型参数量大、预训练成本高，难以在资源受限场景部署。
method: 提出能量感知谱分解模块，结合轻量级架构实现小数据预训练。
result: 在多个数据集上性能与大规模模型相当，但参数量显著降低。
conclusion: SEMPO为资源受限环境下的时间序列预测提供了高效的基础模型方案。
---

## Abstract
The recent boom of large pre-trained models witnesses remarkable success in developing foundation models (FMs) for time series forecasting. Despite impressive performance across diverse downstream forecasting tasks, existing time series FMs possess massive network architectures and require substantial pre-training on large-scale datasets, which significantly hinders their deployment in resource-constrained environments. In response to this growing tension between versatility and affordability, we propose **SEMPO**, a novel lightweight foundation model that requires pretraining on relatively small-scale data, yet exhibits strong general time series forecasting. Concretely, SEMPO comprises two key modules: 1) _energy-aware **S**p**E**ctral decomposition module_, that substantially improves the utilization of pre-training data by modeling not only the high-energy frequency signals but also the low-energy yet informative frequency signals that are ignored in current methods; and 2) _**M**ixture-of-**P**r**O**mpts enabled Transformer_, that learns heterogeneous temporal patterns through small dataset-specific prompts and adaptively routes time series tokens to prompt-based experts for parameter-efficient model adaptation across different datasets and domains. Equipped with these modules, SEMPO significantly reduces both pre-training data scale and model size, while achieving strong generalization. Extensive experiments on two large-scale benchmarks covering 16 datasets demonstrate the superior performance of SEMPO in both zero-shot and few-shot forecasting scenarios compared with state-of-the-art methods. Code and data are available at https://github.com/mala-lab/SEMPO.

---

## 论文详细总结（自动生成）

好的，以下是对论文《SEMPO: Lightweight Foundation Models for Time Series Forecasting》的详细中文总结。

---

### 1. 核心问题与整体含义（研究动机和背景）

*   **核心问题**：现有的大规模时间序列基础模型（Foundation Models, FMs）虽然在通用预测任务上表现优异，但普遍存在**参数量巨大**和**依赖大规模数据预训练**的问题，这导致其难以在**资源受限环境**中部署。
*   **研究动机**：文章旨在探索能否在**显著降低模型参数量**和**预训练数据规模**的同时，依然保持模型强大的零样本（zero-shot）和少样本（few-shot）泛化能力。
*   **整体含义**：文章提出了一种名为 **SEMPO** 的新型轻量级基础模型，为在计算资源有限的场景下实现高效的通用时间序列预测提供了可行的解决方案，挑战了“越大越好”的传统思路。

### 2. 方法论

SEMPO 采用编码器-解码器架构，其核心创新在于两个关键模块：

**核心思想**：通过**能量感知谱分解模块**（EASD）提升预训练数据的利用率；通过**混合提示Transformer模块**（MoPFormer）实现轻量级、参数高效的跨领域模型自适应。

**关键技术细节**：

1.  **能量感知谱分解模块**：旨在解决现有模型在预训练时偏向学习高能量频谱信号而忽略低能量（但信息丰富）信号的问题。
    *   **能量级频谱划分（Energy-wise Spectral Partitioning）**：首先将输入时间序列经过FFT变换到频域。然后，通过一个**可学习的能量阈值**，将频谱划分为高频能量成分和低频能量成分两个分支，确保低能量成分不会被高能量成分淹没。
    *   **频率级频谱掩码（Frequency-wise Spectral Masking）**：在两个能量分支中，分别使用**独立参数化的多频带掩码**来选择性地抑制高/低频带。这种解耦设计增强了频谱多样性，并促使模型学习更全面的时序模式。最终，将掩码后的两个分支的结果相加，并通过iFFT变换回时域。

2.  **混合提示Transformer模块**：旨在以参数量小的提示（Prompts）替代大规模的专家混合（MoE）结构，来学习异构的时序模式。
    *   **混合提示（Mixture of Prompts, MoP）**：初始化一个**提示专家池**。
    *   **自适应路由器（Adaptive Router）**：为每个输入的时序令牌（token）动态计算权重，从专家池中选择并柔性地合并多个提示向量，形成一个 **“结构化提示键值对”** 。
    *   **与自注意力机制融合**：将生成的提示键值对**拼接**到Transformer自注意力层（Self-Attention）的Key和Value矩阵上，从而影响注意力输出。这相当于在不增加主模型参数量的情况下，注入了适应特定数据集的知识。

**训练流程（两阶段）**：

*   **第一阶段：能量感知预训练**。联合训练EASD、编码器和解码器，通过**自监督重建损失**学习跨领域的通用特征。这一阶段不使用MoP模块。
*   **第二阶段：提示微调**（MoP Tuning）。冻结第一阶段训练好的所有参数（包括Transformer骨干），**只训练**MoP模块和预测头。通过联合优化**监督预测损失**和重建损失来适应下游任务。

### 3. 实验设计

*   **数据集与场景**：
    *   **预训练数据**：从 UTSD 数据集中精选了约 **8300万个时间点**。
    *   **零样本/少样本评估**：
        *   **TSLib Benchmark**：包含7个数据集（ETTh1、ETTh2、ETTm1、ETTm2、Weather、Electricity、Traffic），评估零样本和少样本（使用5%和10%训练数据）预测性能。
        *   **GIFT-Eval Benchmark**：选取了其中9个数据集，用于评估零样本预测能力。
*   **对比方法**：文章与**17种**最新方法进行了对比，分为三类：
    1.  **预训练时间序列基础模型**：TTM、Time-MoE、Timer、Moirai、Chronos、TimesFM、Moment。
    2.  **基于LLM的时间序列模型**：Time-LLM、GPT4TS、S²IP-LLM。
    3.  **特定任务模型**：iTransformer、DLinear、PatchTST、TimesNet等。
*   **评估指标**：在TSLib上使用**均方误差（MSE）**和**平均绝对误差（MAE）**；在GIFT-Eval上使用**对称平均绝对百分比误差（SMAPE）**和**归一化均方根误差（NRMSE）**。

### 4. 资源与算力

*   论文明确说明，整个两阶段预训练过程在 **4张NVIDIA A6000-48G GPU** 上，使用 BF32 精度，batch size为2048，共耗时约 **10小时**。
*   模型参数量的“小”是核心贡献之一，仅 **6.5M**。
*   具体的推理时间和参数对比在效率分析章节（Figure 1, Figure 6）有详细展示。

### 5. 实验数量与充分性

*   **实验数量**：实验量非常充分。在三个主要评估场景（零样本、少样本5%、少样本10%）下，每个场景均覆盖7个数据集，并报告了预测长度从96到720的不同结果，总计上百个实验点。此外，还包括大量消融实验、灵敏度分析、可视化分析和效率分析。
*   **充分性与公平性**：
    *   对比方法覆盖全面，包括主流的轻量级和大规模模型，以及LLM驱动的方法，对比基准全面。
    *   消融实验验证了EASD和MoPTwo个核心模块的有效性，并分析了不同变体（如替代掩码策略、稀疏MoE）的影响。
    *   提供了不同超参数（如掩码数量、提示数量、潜在维度）的灵敏度分析。
    *   实验设置方法（如lookback window length、训练数据比例）遵循学术界标准协议，保证了结果的客观性。

### 6. 主要结论与发现

*   **SEMPO 性能优越**：在参数量仅**6.5M**、预训练数据量仅**83M**时间点的条件下，SEMPO 在零样本和少样本预测任务上，全面超越参数量数百倍（如Chronos L, 710M）、训练数据量数十倍（如Time-MoE, 309B）的SOTA模型。
*   **显著降低误差**：与现有方法相比，SEMPO 在零样本和少样本场景下，平均预测误差（MSE）分别降低了**12%**和**22%**。
*   **高效的泛化能力**：验证了通过学习低能量频谱信号和使用轻量级MoP，可以实现高效率的跨领域知识迁移。
*   **数据效率是关键**：证明了在基础模型开发中，“小而精”（小模型 + 小数据 + 强利用）的范式可以替代“大而全”（大模型 + 大数据 + 高成本）的传统范式。

### 7. 优点

*   **极高的数据效率**：仅用8,300万数据点进行预训练，大幅降低了数据成本和训练门槛，这是该论文最突出的亮点。
*   **轻量级设计**：6.5M的参数量使其在资源受限设备（如嵌入式系统、移动端）上部署成为可能。
*   **方法创新性**：
    *   **EASD模块**：明确指出了现有模型对低能量频率成分的忽视问题，并提出有效解决方案，见解独到。
    *   **MoP模块**：用轻量级的软寻址机制（自适应路由 + 提示合并）替代了计算密集型的大规模稀疏MoE，在不牺牲性能的前提下实现了参数效率。
*   **实验全面**：在两个主流基准（TSLib, GIFT-Eval）上进行了全面的零样本和少样本实验，并提供了丰富的消融、灵敏度和可视化分析，实验的说服力强。

### 8. 不足与局限

*   **架构复杂性**：论文在缩放分析（Scaling Analysis）中暗示，当模型参数规模增大时，性能可能出现瓶颈或下降（Figure 10），这表明其方法对进一步提升模型容量可能不够友好。模型的“轻量级”定位可能限制其在处理极端复杂的时序数据时的上限。
*   **核心假设风险**：EASD模块的有效性高度依赖于**可学习的能量阈值**。虽然实验表明算法能自适应调整，但在跨领域时，该阈值的鲁棒性可能存在风险，尤其当不同领域数据能量分布差异过大时。
*   **MoP的“专家”效率**：MoP虽然轻量，但“提示专家”本身是参数化的向量。在一定规模下（Figure 9b），过多的提示可能会导致冗余或注意力分散。论文未详尽探讨在专家数量极端庞大时的性能表现。
*   **实验范围**：虽然覆盖了经典基准，但实验主要集中在单变量（通道独立）的预测上。对多变量强相关场景的建模能力，论文是基于“通道独立性”处理，这是一种简化策略，可能忽略了变量间复杂的耦合关系。对未来的“考虑多元交互”的展望也间接承认了此局限。
*   **输出分布**：模型目前仅输出确定性点预测（MSE/MAE）。缺乏概率预测能力（如预测区间），限制了其在风险敏感场景（如金融、能源）的应用。作者在贡献部分也提到，输出灵活性是未来方向。

（完）
