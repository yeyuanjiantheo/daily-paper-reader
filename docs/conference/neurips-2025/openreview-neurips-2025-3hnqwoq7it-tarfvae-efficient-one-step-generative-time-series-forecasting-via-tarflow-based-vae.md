---
title: "TARFVAE: Efficient One-Step Generative Time Series Forecasting via TARFLOW based VAE"
title_zh: TARFVAE：基于TARFLOW的VAE高效一步生成式时间序列预测
authors: "Jiawen Wei, Lan Jiang, Pengbo Wei, Ziwen Ye, Teng Song, Chen Chen, Guangrui Ma"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=3hnqwOq7iT"
tags: ["query:qf"]
score: 5.0
evidence: 生成式时间序列预测，一步高效生成
tldr: 现有生成式时间序列预测方法多依赖循环生成或反复去噪，计算效率低，尤其长期预测受限。本文提出TARFVAE，基于TARFLOW和VAE创新实现一步生成式预测，大幅提升效率。在长期预测中与确定性方法对比显示其优势，为概率预测提供高效替代方案。可应用于金融时间序列波动率预测等场景。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-3hnqwoq7it/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1421, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3hnqwoq7it/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 746, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3hnqwoq7it/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1380, \"height\": 326, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-3hnqwoq7it/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 1135, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3hnqwoq7it/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3hnqwoq7it/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 731, \"height\": 772, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3hnqwoq7it/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1370, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3hnqwoq7it/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 730, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3hnqwoq7it/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1383, \"height\": 147, \"label\": \"Table\"}]"
motivation: 现有生成式时间序列预测方法计算繁琐，长期预测效率低且对比不充分。
method: 提出TARFVAE，结合TARFLOW与VAE实现一步生成式概率预测。
result: 在长期预测任务中效率显著提升，并与确定性方法进行了公平对比。
conclusion: 为时间序列预测提供高效生成式解决方案，可推广至金融等领域。
---

## Abstract
Time series data is ubiquitous, with forecasting applications spanning from finance to healthcare. Beyond popular deterministic methods, generative models are gaining attention due to advancements in areas like image synthesis and video generation, as well as their inherent ability to provide probabilistic predictions. However, existing generative approaches mostly involve recurrent generative operations or repeated denoising steps, making the prediction laborious, particularly for long-term forecasting. Most of them only conduct experiments for relatively short-term forecasting, with limited comparison to deterministic methods in long-term forecasting, leaving their practical advantages unclear. This paper presents TARFVAE, a novel generative framework that combines the Transformer-based autoregressive flow (TARFLOW) and variational autoencoder (VAE) for efficient one-step generative time series forecasting. Inspired by the rethinking that complex architectures for extracting time series representations might not be necessary, we add a flow module, TARFLOW, to VAE to promote spontaneous learning of latent variables that benefit predictions. TARFLOW enhances VAE's posterior estimation by breaking the Gaussian assumption, thereby enabling a more informative latent space. TARFVAE uses only the forward process of TARFLOW, avoiding autoregressive inverse operations and thus ensuring fast generation. During generation, it samples from the prior latent space and directly generates full-horizon forecasts via the VAE decoder. With simple MLP modules, TARFVAE achieves superior performance over state-of-the-art deterministic and generative models across different forecast horizons on benchmark datasets while maintaining efficient prediction speed, demonstrating its effectiveness as an efficient and powerful solution for generative time series forecasting. Our code is available at https://github.com/Gavine77/TARFVAE.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景**：时间序列预测广泛应用于金融、医疗、能源等领域。除传统确定性点预测外，生成式概率预测（如VAE、扩散模型）因能提供不确定性量化而逐渐受到关注。
- **核心问题**：现有生成式方法（尤其是扩散模型）依赖多步去噪或自回归循环生成，导致推理速度慢，尤其不适合长期预测（long-term forecasting）。同时，多数生成模型仅在短期场景下评估，与确定性方法的长期预测对比不足，其实际优势不明。
- **目标**：提出一种既保持一步生成高效性，又具备高精度概率预测能力的生成式框架，在长期预测中实现与顶级确定性方法可比甚至更优的性能。

## 2. 论文提出的方法论

### 核心思想
- 将**Transformer-based Autoregressive Flow (TARFLOW)** 引入VAE，打破VAE后验的高斯假设，从而学习更灵活、更信息丰富的隐空间。
- 仅使用TARFLOW的前向变换（避免耗时的自回归逆过程），实现一步生成。

### 关键技术细节
- **整体架构**（条件VAE）：
  - **实例归一化**：基于历史序列`x`的均值和方差对`x`和`y`归一化，保证训练与推理归一化一致。
  - **序列嵌入**：编码器、解码器、先验模块、TARFLOW各自使用独立嵌入层，避免干扰。
  - **先验与初始后验**：Prior网络基于`x`输出高斯先验`p(z|x)`；Encoder基于`[x,y]`输出初始后验`q(z0|x,y)`（高斯）。
  - **TARFLOW模块**：将初始后验分布变换为复杂后验`z`，变换过程受条件`[x,y]`控制（公式(26)），每个TARFLOW块采用仿射耦合层并由因果Transformer实现`s`和`t`函数，相邻块间进行维度反转。
  - **解码器**：使用全注意力机制从历史`x`中提取与`z`相关的信息，再通过MLP块将混合特征映射为预测`ˆy`。
- **训练损失**：基于ELBO推导得到式(28)，包含重构项、KL项和TARFLOW的对数行列式项。
- **推理过程**：直接采样`z ~ p(z|x)`，经解码器一步生成完整预测序列。

## 3. 实验设计

### 数据集
- **8个真实世界基准数据集**：ETTh1、ETTh2、ETTm1、ETTm2（电力变压器数据）、Electricity（电力）、Exchange（汇率）、Weather（天气）、Solar-Energy（太阳能）。

### Benchmark设置
- **与确定性方法对比**：lookback窗口`L=96`，预测长度`H∈{96,192,336,720}`，指标MSE、MAE。
- **与生成方法对比**：部分数据集设置不同`H`（如168、192、672等），`L`从96~1440中选择，额外计算CRPS。
- **推理效率对比**：在ETTh1单变量上测试不同`H`下的推理时间（ms）。

### 对比方法
- **确定性基线**：DUET、SOFTS、iTransformer、TSMixer、PatchTST、Crossformer、TiDE、DLinear、FEDformer。
- **生成式基线**：mr-Diff、TimeDiff、TimeGrad、CSDI、SSSD、D3VAE、CPF、PSA-GAN、N-Hits、FiLM、Depts、NBeats、SCINet、NLinear、DLinear、LSTMa。
- **CRPS对比**：另采用ProbTS协议与CSDI、iTransformer、PatchTST、GRU NVP、TimeGrad等对比。

## 4. 资源与算力

- 论文提到实验在**单张Nvidia-H20 GPU（141GB内存）**上运行，未明确给出训练时间。
- 推理效率比较在**Nvidia-A6000 GPU（48GB内存）**上进行，以对齐基线设置。
- 未说明总训练时长或具体超参数搜索耗时。

## 5. 实验数量与充分性

- **主要结果**：Table 1（与确定性方法对比，8数据集×4 horizon，共32组性能数据）；Table 3（与生成方法对比，5数据集×2指标×5方法）；Table 4（推理时间对比）；Table 5（CRPS对比）。
- **消融实验**：Table 6（去除TARFLOW、去除VAE&TARFLOW，在8数据集上平均MSE/MAE）。
- **超参分析**：Figure 3（不同lookback长度影响）、Table 2（不同推理样本数20/50/100/200对MSE/MAE/CRPS的影响）。
- **充分性评价**：
  - 覆盖了长期预测的多个典型horizon，数据集多样（通道数从7到321）。
  - 对比了近年主流确定性方法和生成方法，结果表明显著优势。
  - 消融实验证明了各模块的必要性；样本数实验验证了稳定性。
  - 实验设置公正：遵循已有论文配置，部分结果直接引用已发布成绩。

## 6. 论文的主要结论与发现

- **性能优势**：TARFVAE在8个数据集上获得最多“最优”结果（Table 1中33次MSE第1、27次MAE第1），尤其在ETTh2、Weather上平均MSE降低4.3%和4.8%。
- **效率优势**：与mr-Diff相比，推理时间减少85.6%（H=720时），且随样本数增加延迟增加极小（1~200样本仅增加0.3ms）。
- **概率预测可靠**：CRPS指标全面优于ProbTS中的对比方法（除Weather的H=192外均排第一或第二）。
- **模块有效性**：去掉TARFLOW导致MSE平均上升10.30%，去掉VAE&TARFLOW上升10.96%，证实二者协同作用。
- **样本稳健性**：随着样本数从20增至200，MSE、MAE、CRPS一致改善，且波动小。

## 7. 优点

- **方法创新**：巧妙将TARFLOW与VAE结合，既增强后验建模能力，又通过仅使用前向变换保留一步生成速度；采用简单MLP基础结构，避免复杂设计，验证了流模型的潜力。
- **实验全面**：同时评估点预测（MSE/MAE）和概率预测（CRPS），与大量基线公平对比，包含消融、超参数、推理速度等分析。
- **实用性强**：推理速度快（3ms级），便于实际部署；开源代码促进复现和拓展。
- **结果显著**：在长期预测任务上首次有生成模型达到与顶级确定性方法相当甚至更优的性能，并为生成式模型在长期场景下提供了有力证据。

## 8. 不足与局限

- **模型结构限制**：论文使用相同的MLP模块作为编码器、解码器和先验网络，可能未最大化各自潜力；MLP对复杂时序模式提取能力有限（论文附录B明确承认）。
- **泛化性验证不足**：仅在时间序列基准上测试，未涉及图像、视频等其他序列领域；未测试噪声或分布偏移下的鲁棒性。
- **实验细节缺失**：未给出训练时长、超参数搜索过程；推理时间对比中基线结果引用自原始论文，可能存在环境差异。
- **可解释性**：生成式模型内部隐空间可解释性未讨论。
- **实际应用风险**：论文在附录C讨论了隐私和过度依赖自动化预测的社会影响，但未提出具体缓解措施。

（完）
