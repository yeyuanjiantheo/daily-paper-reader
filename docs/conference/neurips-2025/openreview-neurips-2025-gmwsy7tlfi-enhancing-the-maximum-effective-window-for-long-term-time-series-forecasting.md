---
title: Enhancing the Maximum Effective Window for Long-Term Time Series Forecasting
title_zh: 增强长期时间序列预测的最大有效窗口
authors: "Jiahui Zhang, Zhengyang Zhou, Wenjie Du, Yang Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Gmwsy7TlFI"
tags: ["query:qf"]
score: 5.0
evidence: 长期时间序列预测指标与增强模块
tldr: 现有模型难以有效利用长历史窗口。本文提出最大有效窗口（MEW）指标衡量模型能力，并设计两个通用模块增强长程预测。为时间序列预测（包括金融领域）提供了实用的模型评估和改进工具。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gmwsy7tlfi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gmwsy7tlfi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1399, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gmwsy7tlfi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1398, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gmwsy7tlfi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gmwsy7tlfi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1449, \"height\": 1081, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmwsy7tlfi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1399, \"height\": 785, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmwsy7tlfi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmwsy7tlfi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1281, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmwsy7tlfi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmwsy7tlfi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1444, \"height\": 1036, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmwsy7tlfi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1464, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmwsy7tlfi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 903, \"height\": 637, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmwsy7tlfi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1083, \"height\": 315, \"label\": \"Table\"}]"
motivation: 长历史窗口带来噪声和注意力分散，导致模型性能下降。
method: 提出MEW指标和两个模块，分别优化输入表示和注意力机制。
result: 在多个时间序列数据上验证了指标的有效性，并提升了预测精度。
conclusion: 增强模型对长窗口的利用能力是提升长期预测的关键。
---

## Abstract
Long-term time series forecasting (LTSF) aims to predict future trends based on historical data. While longer lookback windows theoretically offer more comprehensive insights, Transformer-based models often struggle with them. On one hand, longer windows introduce more noise and redundancy, hindering the model's learning process. On the other hand, Transformers suffer from attention dispersion and are prone to overfitting to noise, especially when processing long sequences. In this paper, we introduce the Maximum Effective Window (MEW) metric to assess a model's ability to effectively utilize the lookback window. We also propose two model-agnostic modules to enhance MEW, enabling models to better leverage historical data for improved performance. Specifically, to reduce redundancy and noise, we introduce the Information Bottleneck Filter (IBF), which employs information bottleneck theory to extract the most essential subsequences from the input. Additionally, we propose the Hybrid-Transformer-Mamba (HTM), which incorporates the Mamba mechanism for selective forgetting of long sequences while harnessing the Transformer's strong modeling capabilities for shorter sequences. We integrate these two modules into various Transformer-based models, and experimental results show that they effectively enhance MEW, leading to improved overall performance. Our code is available at \url{https://github.com/forever-ly/PIH}.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：长期时间序列预测（LTSF）中，直觉上使用更长的历史窗口（lookback window）能提供更全面的信息，从而提高预测精度。但现有Transformer-based模型在处理长序列时面临两大挑战：一是长窗口引入更多噪声和冗余，干扰模型学习；二是Transformer自身存在注意力分散（attention dispersion）问题，容易对噪声过拟合，尤其在处理长序列时这些缺陷被放大。
- **核心问题**：如何量化模型有效利用长窗口的能力，并设计通用模块提升这种能力，使得模型能从更长的历史数据中获益。
- **整体含义**：提出**最大有效窗口（Maximum Effective Window, MEW）**指标，用于衡量模型能够从历史窗口中获取有效信息的最大长度。从信息论和架构两个角度分析MEW受限的原因，并设计两个模型无关的模块——信息瓶颈滤波器（IBF）和混合Transformer-Mamba（HTM），以增强模型对长窗口的利用，从而提升长期预测性能。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：
  1.  **MEW指标**：对于给定模型，固定其他设置，逐步增加历史窗口长度，存在一个点，超过此点后继续增加窗口不会提升性能，该点称为MEW。MEW反映了模型利用历史信息的能力上限。
  2.  **IBF (Information Bottleneck Filter)**：基于信息瓶颈（IB）理论，从输入序列中提取最关键的子序列，同时最小化冗余和噪声。核心是使用噪声注入策略：对重要子序列注入少量噪声（λ接近1），对不重要子序列注入大量噪声（λ接近0）。通过优化变分上界（预测损失 + 压缩损失）实现。
  3.  **HTM (Hybrid-Transformer-Mamba)**：结合Mamba的状态空间模型（SSM）的选择性记忆/遗忘能力（擅长处理长序列并过滤噪声）和Transformer的强建模能力（擅长处理短序列）。具体流程：Mamba先处理长序列（选择性过滤噪声） → IBF进一步去噪 → 将去噪后的长序列划分为多个短子序列（间隔分裂或块分裂）→ Transformer处理各子序列以捕获短期依赖。

- **关键技术细节**：
  - **IBF**：
    - 对每个patch嵌入 \(z_i\)，用MLP输出重要性 \(c_i = \text{sigmoid}(\text{MLP}(z_i))\)。
    - 使用Gumbel-Sigmoid采样伯努利变量 \(\lambda_i\)，得到噪声注入后的表示 \(z_{\text{noise}} = \lambda z + (1-\lambda)\epsilon\)，其中 \(\epsilon \sim \mathcal{N}(\mu_z, \sigma_z^2)\)。
    - 优化损失：\(\mathcal{L} = \mathcal{L}_{\text{pred}}(z_{\text{noise}}, Y) + \beta \mathcal{L}_{\text{comp}}(z_{\text{noise}}, z)\)，第一项为预测损失（MSE），第二项为压缩损失（变分上界）。
  - **HTM**：
    - 两种分裂方法：间隔分裂（interval split，将连续K个patch分散到不同块）和块分裂（block split，连续的一段patch形成一个块）。
    - Mamba模块（如Mamba-1）处理原始patches嵌入，Transformer模块处理分裂后的短子序列。
  - **整体模型PIH (Patch-IBF-HTM)**：基于PatchTST框架，先做Patching + Embedding，然后经过Mamba（Dropout后得到z），再经IBF得到z_noise，再分裂后由Transformer处理，最后通过Flatten + Linear Head输出预测。

- **公式/算法流程（文字说明）**：
  1. 输入x → Patching + Embedding → e
  2. e → Mamba + Dropout → z
  3. z → IBF：计算重要性c，采样λ，得到z_noise = λz + (1-λ)ϵ
  4. z_noise → Split（间隔或块分裂）→ 多个子序列
  5. 各子序列 → Transformer → 拼接 → Flatten → Linear Head → 预测Y
  6. 训练损失 = MSE(Y_pred, Y_truth) + β·压缩损失

### 3. 实验设计：数据集/场景、benchmark、对比方法

- **数据集**：
  - 主要使用7个公开数据集：Weather, Traffic, Electricity, ETTh1, ETTh2, ETTm1, ETTm2。
  - 额外验证集：Solar, PEMS（附录C.2）。
- **基准（Benchmark）**：采用标准LTSF设定，预测长度 \(T \in \{96, 192, 336, 720\}\)，历史窗口 \(L\) 最长设为1024，比以往工作更长。
- **对比方法**：
  - Mamba-based: Bi-Mamba, S-Mamba。
  - Transformer-based: PatchTST, FEDformer, Autoformer, Informer。
  - Linear-based: DLinear, NLinear。
  - 另在附录中与iTransformer对比。
- **评估指标**：MSE, MAE。

### 4. 资源与算力

- 论文未明确说明使用的GPU型号、数量及具体训练时长。仅在Fig.3(b)中给出了GPU内存（GB）和训练时间（min/epoch）的对比图，显示PIH相比纯PatchTST在内存和时间上略有增加，但比纯Mamba架构（PatchTSM）更高效。总体算力需求适中。
- 注：文中提到AI-driven实验依托于中国科学院机器人AI科学家平台，但无具体硬件细节。

### 5. 实验数量与充分性

- **实验数量充足**：涵盖了7个主要数据集 × 4个预测长度 = 28个实验场景，外加Solar/PEMS的额外验证（8个场景），以及多种基线对比（至少9种方法）。
- **消融实验**：：
  - 组件消融：对比PatchTST、+HTM、+HMM（纯Mamba）、+IB、PIH（完整），验证各模块贡献。
  - 分裂方法比较：间隔分裂 vs 块分裂。
  - 超参数分析：K（2,4,6,8）、β（0.0001~1）、τ（0.1~2）。
- **泛化性验证**：将IBF+HTM集成到Transformer、Informer、Autoformer、PatchTST四种模型，观察MEW提升效果（表2）。
- **统计显著性**：对PIH vs PatchTST在7个数据集上进行了5次重复实验并计算p-value（表6），多数场景p<0.05，表明改进显著。
- **公平性**：所有方法采用相同实验设定（学习率搜索范围一致），基线结果取自原论文或复现。但注意对Linear模型也设置了L=1024，避免了“故意选差设置”的质疑。

**评价**：实验覆盖广泛，消融充分，统计验证提供，整体客观公平。

### 6. 论文的主要结论与发现

1. **MEW指标有效反映模型能力**：较大MEW值对应更好性能；通过提升MEW可显著提升预测精度。
2. **IBF和HTM模块通用有效**：集成到多种Transformer模型后，均能提高MEW并降低MSE/MAE。
3. **PIH模型实现SOTA**：以PatchTST为骨干，结合IBF+HTM，在1024长窗口下超越所有非LLM-based模型，证明了增强长窗口利用的巨大潜力。
4. **混合架构优于纯架构**：HTM（Mamba+Transformer）在性能和计算开销上均优于纯Mamba或纯Transformer。
5. **长窗口有利但需处理方法限制**：简单增加窗口不一定好（如DLinear(1024)反而不如DLinear(336)），但通过IBF+HTM可有效利用更长窗口。

### 7. 优点：方法或实验设计上的亮点

- **方法创新**：
  - 首次提出MEW指标，为评估模型的长程利用能力提供量化工具。
  - IBF将IB理论引入时间序列子序列选择，结合噪声注入实现可微优化，既滤除噪声又保持关键信息。
  - HTM巧妙结合Mamba（选择性遗忘）和Transformer（强短程建模），并设计两种分裂方式适应不同时间结构。
- **实验亮点**：
  - 使用了远超常规的窗口长度1024，探索模型极限。
  - 泛化性实验覆盖点级和patch级Transformer，验证模块通用性。
  - 提供可视化（Fig.3c）展示IBF识别的重要子序列（峰值），增强可解释性。

### 8. 不足与局限

1. **实验覆盖**：主要关注单变量预测（channel-independent策略），未充分验证多变量联合建模场景（如iTransformer虽在附录中有一列，但未系统对比）。
2. **计算资源未明确**：未报告完整训练环境（GPU型号、数量、总耗时），无法复现计算成本。
3. **偏差风险**：
   - 超参数（β、τ）对性能影响显著，但仅基于少量验证集调参，可能过拟合特定数据集。
   - 分裂方法（间隔 vs 块）是启发式的，缺乏自适应机制，未来可探索端到端学习。
4. **应用限制**：
   - 长窗口假设在极短期预测（如T=96）中可能不必要（图3a中PIH在L=96时略逊于PatchTST）。
   - 模型复杂度随窗口线性增长（依赖Mamba），对极长序列（如>1024）可能仍有瓶颈。
   - 当前未与LLM-based大时间序列模型（如TimesFM）结合，虽声称正交，但缺乏实际集成验证。
5. **理论分析薄弱**：IBF的变分界推导基于高斯假设，不一定适用于所有时间序列分布。

---

（完）
