---
title: "Sundial: A Family of Highly Capable Time Series Foundation Models"
title_zh: Sundial：高性能时间序列基础模型家族
authors: "Yong Liu, Guo Qin, Zhiyuan Shi, Zhi Chen, Caiyin Yang, Xiangdong Huang, Jianmin Wang, Mingsheng Long"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=LO7ciRpjI5"
tags: ["query:qf"]
score: 6.0
evidence: 时间序列基础模型用于预测
tldr: 本文提出Sundial时间序列基础模型族，基于流匹配损失预训练于万亿时间点数据，可无需预先指定分布生成多种可能预测。模型采用最小化Transformer适应，在多个真实和合成数据集上展现强大性能，为金融时间序列预测提供了强大的基础模型。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-lo7cirpji5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 860, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lo7cirpji5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1770, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lo7cirpji5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 845, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lo7cirpji5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1766, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lo7cirpji5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lo7cirpji5/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 860, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lo7cirpji5/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 867, \"height\": 868, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lo7cirpji5/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 854, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lo7cirpji5/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1754, \"height\": 721, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lo7cirpji5/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1737, \"height\": 714, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lo7cirpji5/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1751, \"height\": 1908, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lo7cirpji5/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1767, \"height\": 1930, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lo7cirpji5/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1742, \"height\": 2229, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lo7cirpji5/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1765, \"height\": 1919, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lo7cirpji5/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1771, \"height\": 1883, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-lo7cirpji5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 483, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lo7cirpji5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1769, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lo7cirpji5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 860, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lo7cirpji5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1768, \"height\": 191, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lo7cirpji5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1761, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lo7cirpji5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1776, \"height\": 736, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lo7cirpji5/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1778, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lo7cirpji5/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1744, \"height\": 568, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lo7cirpji5/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1771, \"height\": 1374, \"label\": \"Table\"}]"
motivation: 现有时间序列预测模型依赖参数化密度或离散化，灵活性不足。
method: 采用流匹配损失直接建模连续值时间序列分布，构建大规模时间序列基础模型。
result: 在多种预测任务上取得领先性能，尤其在零样本场景下表现优异。
conclusion: 为通用时间序列预测提供了可扩展的基础模型，有望推动金融预测发展。
---

## Abstract
We introduce Sundial, a family of native, flexible, and scalable time series foundation models. To predict the next-patch's distribution, we propose a TimeFlow Loss based on flow-matching, which facilitates native pre-training of Transformers on continuous-valued time series without discrete tokenization. Conditioned on arbitrary-length time series, our models are pre-trained without specifying any prior distribution and can generate multiple probable predictions, achieving more flexibility in representation learning than using parametric densities. Towards time series foundation models, we leverage minimal but crucial adaptations of Transformers and curate TimeBench with one trillion time points, comprising mostly real-world datasets and synthetic data. By mitigating mode collapse via TimeFlow Loss, we pre-train a family of Sundial models on TimeBench, which achieve unprecedented model capacity and generalization performance. In addition to excellent scalability, Sundial achieves state-of-the-art results on both point and probabilistic forecasting benchmarks with a just-in-time inference speed, i.e., making zero-shot predictions within a few milliseconds. We believe that Sundial's pioneering generative forecasting capability can improve model reliability in real-world decision-making. Code is available at: https://github.com/thuml/Sundial.

---

## 论文详细总结（自动生成）

# Sundial: 高性能时间序列基础模型家族 - 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：时间序列预测本质上具有非确定性（non-deterministic），需要生成多种可能的预测结果以支持可靠决策。现有时间序列基础模型大多依赖**参数化密度函数**（如高斯分布、混合分布）或**离散化tokenization**（如将连续值量化成离散桶），这限制了模型对异质性（heterogeneous）时间序列分布的拟合能力，导致模式坍塌（mode collapse）或预测粒度粗糙。
- **研究背景**：尽管Transformer在语言、图像生成领域取得了巨大成功，但大多数时间序列基础模型并非真正的“生成式”概率预测器，无法提供置信度或多种可能。因此，需要一种**原生（native）、灵活、可扩展**的生成式时间序列基础模型，能够直接在连续值上学习任意复杂分布，同时支持零样本预测和快速推理。
- **整体含义**：本文提出Sundial家族，通过流匹配（flow-matching）框架实现连续值时间序列的**原生生成式预训练**，无需离散化或先验分布假设，在万亿时间点数据集上训练，首次将生成式模型引入时间序列基础模型领域，显著提升模型容量和泛化能力。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将流匹配（Flow-Matching）与自回归Transformer结合，通过**TimeFlow Loss**学习每个patch的预测分布，从而在连续域内直接生成多种可能的未来序列，同时避免模式坍塌。
- **关键技术细节**：
  - **时间序列tokenization**：
    - 采用**重归一化（Re-Normalization）**：对每个样本进行非参数实例归一化，缓解时序分布漂移和异常值，提升零样本泛化。
    - **Patch嵌入**：将连续时间序列分割成非重叠的patch（长度P），使用共享MLP将每个patch及其mask嵌入为向量，保留原始连续值，避免离散量化带来的信息损失。
  - **Transformer骨干**：
    - 采用**仅解码器（decoder-only）** 架构，使用**因果自注意力**、**RoPE（旋转位置编码）**、**Pre-LN（层前归一化）** 保证训练稳定性，并集成**FlashAttention**和**KV Cache**加速训练和推理。
    - 支持任意长度输入（最大上下文长度2880），采用**多patch预测**（预测长度F > 补丁长度P）减少自回归步数。
  - **TimeFlow Loss**：
    - 基于**条件流匹配（Conditional Flow-Matching）** 公式：
      \[
      L = \mathbb{E}_{t,\epsilon, y_i} \left[ \| u_\theta^t(y_i^{(t)} | h_i) - (y_i - y_i^{(0)}) \|^2 \right]
      \]
      其中 \(y_i^{(t)} = t y_i + (1-t) y_i^{(0)}\)，\(y_i^{(0)} \sim \mathcal{N}(0, I)\)，\(h_i\) 是来自Transformer的表示。
    - 训练一个小型MLP（FM-Net）作为速度场，条件表示通过AdaLN注入。
    - **推理**：从高斯噪声出发，通过K步ODE推进（算法1），重复采样生成多个预测，计算中位数、分位数等统计量用于点/概率预测。
- **预训练数据集 TimeBench**：收集并整理超过**1万亿时间点**的数据，其中约99.95%为真实数据（包括Chronos、ECG、金融、IoT、LOTSA、ERA5气象数据等），0.05%为合成数据（KernelSynth），覆盖多种频率和领域。

## 3. 实验设计：数据集、基准与对比方法

- **实验场景与基准**：
  1. **点预测（Point Forecasting）**：使用**Time-Series-Library (TSLib)** 基准，包含6个数据集（ETTm1/2、ETTh1/2、ECL、Weather），预测长度96/192/336/720，评价指标MSE和MAE。
  2. **概率预测（Probabilistic Forecasting）**：
     - **GIFT-Eval**：23个数据集，97种配置，评价MASE和CRPS。
     - **FEV Leaderboard**：27个数据集，评价MASE和WQL（加权分位数损失）。
- **对比方法**：
  - 时间序列基础模型：TimesFM、Timer、Time-MoE（Base/Large/Ultra）、Moirai（Base/Large）、Chronos（Base/Large）、Lag-Llama、MOMENT等。
  - 监督模型：DeepAR、TiDE、N-BEATS、PatchTST、iTransformer等。
  - 统计方法：Naïve、Seasonal ARIMA、Theta等。
- **实验设置**：所有评估数据集均排除在预训练之外，确保零样本；概率预测采样20-100个生成序列；推理步数K=50；Sundial模型分Small(32M)、Base(128M)、Large(444M)三个规模。

## 4. 资源与算力

- **硬件**：使用**32块NVIDIA A100 GPU**进行预训练。
- **训练优化器**：AdamW。
- **训练细节**：文中未明确给出总训练时长或迭代次数，但提到使用了全局shuffle、按比例采样数据域，并进行了多规模模型的预训练（Small/Base/Large）。在附录中给出了模型配置（层数、维度、注意力头数等）。
- **推理效率**：在CPU上生成20个预测（每个50步）约需1秒，远快于Chronos等模型（图5显示Sundial比Chronos快35倍）。

## 5. 实验数量与充分性

- **实验组数**：
  - **点预测**：6个数据集×4种预测长度 = 24组结果（表1、表9）。
  - **概率预测**：GIFT-Eval 97个配置（表2），FEV 27个数据集（图4）。
  - **规模实验**：不同模型尺寸对比（表1、图6）。
  - **损失函数对比**：TimeFlow vs Diffusion vs MSE（表3、表7）。
  - **消融实验**：RoPE、LayerNorm位置、FlashAttention、KV Cache（图9）。
  - **测试时校准**：采样数/步数影响（图7）。
  - **模型适应**：微调 vs 从零训练（图8）。
  - **不同回望长度**（图10）。
  - **训练数据规模影响**（表8）。
- **充分性评估**：实验覆盖了**点预测、概率预测、零样本、微调、消融、规模效应**等关键维度，对比方法全面（包括统计、监督、基础模型），且所有评估基于官方标准。但缺少**多变量协同训练**的对比，以及**非常高频数据**（如秒级）的专门测试。整体上实验设计客观、公平，结果具有说服力。

## 6. 论文的主要结论与发现

1. **Sundial在零样本点预测和概率预测上均达到SOTA**：
   - 在TSLib上平均MSE比前最佳Time-MoE降低7.57%，MAE降低4.71%。
   - 在GIFT-Eval上MASE排名第一（0.673），CRPS排名第二（0.472），仅略逊于有监督的PatchTST。
   - 在FEV上超过70%的有监督方法，且推理速度极快。
2. **TimeFlow Loss优于扩散损失和MSE损失**，能有效缓解模式坍塌，生成多样且连贯的预测。
3. **架构改进（RoPE、Pre-LN、FlashAttention、KV Cache）** 对零样本性能有显著提升，且降低资源消耗。
4. **模型容量随数据规模扩大而提升**，验证了时间序列基础模型的缩放律。
5. **生成式范式**为不确定性建模提供了新途径，支持测试时校准和指令微调。

## 7. 优点：方法或实验设计上的亮点

- **方法论亮点**：
  - **原生连续值建模**：无需离散化，避免信息损失和OOV问题，同时实现patch级预测，减少自回归步数。
  - **TimeFlow Loss**：首次将流匹配应用于自回归时间序列生成，兼具扩散模型的灵活性和ODE的高效性。
  - **最小化Transformer适配**：仅引入必要的工程改进（RoPE、Pre-LN、FlashAttention等），保持架构简洁，但效果显著。
- **实验设计亮点**：
  - **万亿级预训练数据集**：涵盖多种领域和频率，确保泛化能力。
  - **广泛的零样本评估**：覆盖三大权威基准，与多种类型基线公平对比。
  - **详尽的消融**：包含架构组件、损失函数、采样策略、数据规模等，结论可靠。
  - **开放代码与模型**：代码开源，模型上传HuggingFace，可复现。

## 8. 不足与局限

- **高频数据处理能力不足**：TimeBench主要包含中低频数据，对极高频率（如日以下）的性能未充分验证，可能导致幻觉。
- **单变量预训练**：采用S3格式进行单变量预训练，无法显式利用变量间的相关性和协变量信息，限制了在多变量场景下的潜力。
- **采样策略简单**：仅采用标准高斯噪声+均匀轨迹的朴素采样，尚未探索更先进的采样或后处理方法（如频率归一化）。
- **自回归误差累积**：多步自回归可能产生平滑甚至不可靠的长期预测，文中未深入分析。
- **计算资源需求高**：尽管推理快，但预训练需要32块A100，对一般研究者门槛较高。
- **未讨论域偏移的鲁棒性**：虽然进行了重归一化，但对极端分布变化（如突发趋势）的适应性未做分析。

（完）
