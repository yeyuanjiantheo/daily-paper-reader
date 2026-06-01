---
title: Towards Accurate Time Series Forecasting via Implicit Decoding
title_zh: 通过隐式解码实现准确时间序列预测
authors: "Xinyu Li, Yuchen Luo, Hao Wang, Haoxuan Li, Liuhua Peng, Feng Liu, Yandong Guo, Kun Zhang, Mingming Gong"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=gqoeQPhQcE"
tags: ["query:qf"]
score: 5.0
evidence: 通用时间序列预测方法，可应用于金融序列
tldr: 现有时间序列预测方法多侧重历史建模，忽略预测阶段。本文提出隐式预测器（IF），通过分解预测思想增强全局建模能力，避免逐点预测导致的模式缺失。实验表明IF有效提升了长期预测准确度，为金融等领域的时间序列预测提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gqoeqphqce/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1383, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gqoeqphqce/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1294, \"height\": 635, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gqoeqphqce/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gqoeqphqce/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1178, \"height\": 485, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gqoeqphqce/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 1893, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gqoeqphqce/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1419, \"height\": 1872, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gqoeqphqce/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1453, \"height\": 772, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gqoeqphqce/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1448, \"height\": 778, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-gqoeqphqce/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 473, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gqoeqphqce/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 691, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gqoeqphqce/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 629, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gqoeqphqce/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 771, \"height\": 352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gqoeqphqce/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1083, \"height\": 557, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gqoeqphqce/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 906, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gqoeqphqce/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1302, \"height\": 759, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gqoeqphqce/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1296, \"height\": 577, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gqoeqphqce/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 1817, \"label\": \"Table\"}]"
motivation: 现有预测方法忽略预测阶段的全局建模，导致长期预测效果不佳。
method: 提出隐式预测器，利用分解预测思想对预测阶段进行额外解码，增强全局视角。
result: 在多个时间序列基准上取得最先进或竞争性结果，验证了方法的有效性。
conclusion: 关注预测阶段的设计是提升时间序列预测性能的重要方向。
---

## Abstract
Recent booming time series models have demonstrated remarkable forecasting performance. However, these methods often place greater focus on more effectively modelling the historical series, largely neglecting the forecasting phase, which generates long-term forecasts by separately predicting multiple time points. Given that real-world time series typically consist of various long short-term dynamics, independent predictions over individual time points may fail to express complex underlying patterns and can lead to a lack of global views. To address these issues, this work explores new perspectives from the forecasting phase and proposes a novel Implicit Forecaster (IF) as an additional decoding module. Inspired by decomposition forecasting, IF adopts a more nuanced approach by implicitly predicting constituent waves represented by their frequency, amplitude, and phase, thereby accurately forming the time series. Extensive experimental results from multiple real-world datasets show that IF can consistently boost mainstream time series models, achieving state-of-the-art forecasting performance. Code is available at this repository: [https://github.com/rakuyorain/Implicit-Forecaster](https://github.com/rakuyorain/Implicit-Forecaster).

---

## 论文详细总结（自动生成）

# 中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

现有时间序列预测方法大多专注于改进历史序列的建模（编码阶段），而忽略了预测阶段（解码阶段）的设计。传统方法通常使用简单的MLP对每个未来时间点进行独立预测，这种逐点预测方式缺乏对时间序列整体波动的全局视角，难以捕捉复杂的长短期动态模式，导致长期预测效果不佳。论文指出，时间序列可分解为不同频率的组成波动（如长期趋势和季节性），因此提出从频率角度隐式地预测这些构成波动，从而更准确地形成未来序列。

## 2. 论文提出的方法论

### 核心思想
提出**隐式预测器（Implicit Forecaster, IF）**，作为一种额外的解码模块，替换现有TSF模型的输出层。IF不直接预测每个时间点的值，而是预测一组周期性波动的频率、幅度和相位，然后通过逆离散傅里叶变换（iDFT）组合这些波动以重构未来序列。

### 关键技术细节
- **输入**：接收两个输入：1) 编码器提取的隐藏表示 \( X_{enc} \in \mathbb{R}^{N \times D} \)；2) 原始输入时间序列 \( X \in \mathbb{R}^{T \times N} \)（通过跳跃连接提供）。
- **频率池**：预定义包含 \( P \) 个不同频率的频谱（\( P \geq L \)，L为预测长度），以捕获超低频成分。
- **幅度头（AHead）**：MLP预测每个频率的幅度 \( \hat{A} \in \mathbb{R}^{N \times P}_{\geq 0} \)，输入包含编码器表示和原始输入序列的幅度谱。
- **相位头（PHead）**：为避免相位数值不连续性，预测相位的正弦和余弦分量（\( \hat{\alpha}, \hat{\beta} \)），再通过`atan2`得到相位 \( \hat{\phi} \in [-\pi, \pi]^{N \times P} \)。
- **合成**：通过逆DFT将预测的幅度和相位合成时间序列，并裁剪至预测长度L。
- **对称性利用**：只预测前一半频谱（共轭对称性），降低计算量。
- **复杂度**：\( O(P \log P) \)，通过FFT实现iDFT。

### 公式流程（文字说明）
1. 对输入序列X进行DFT，提取幅度和相位。
2. 将编码器表示与幅度/相位拼接到一起，分别输入AHead和PHead。
3. AHead输出预测幅度，PHead输出预测相位（通过正弦/余弦）。
4. 将幅度和相位组合为复数列，进行iDFT得到重构序列。
5. 截取预测长度部分作为最终输出。

## 3. 实验设计

### 数据集
14个真实基准数据集，涵盖能源、交通、天气、经济、疾病等领域：
- ETT（4个子集：ETTh1, ETTh2, ETTm1, ETTm2）
- ECL（电力消耗）、Traffic、Weather、Exchange Rate、ILI
- PeMS（4个子集：PEMS03, PEMS04, PEMS07, PEMS08）
- Solar Energy

### 比较方法
7种主流TSF模型：SOFTS（MLP）、TimeXer、iTransformer、PatchTST、Crossformer（Transformer类）、SegRNN（RNN）、TimesNet（CNN）。每个模型与其搭配IF后的版本进行对比。

### 评估指标
MSE和MAE，预测长度L根据数据集不同（ILI:24,36,48,60；PEMS:12,24,48,96；其余:96,192,336,720）。回溯窗口T=36（ILI）、T=96（其他）。

## 4. 资源与算力

论文明确说明：
- 硬件：16核AMD EPYC 9654 CPU + 单张NVIDIA RTX 4090 GPU。
- 框架：PyTorch 2.0，使用Adam优化器、L2损失。
- 训练设置：学习率指数衰减，早停（验证集3次不改进则停止）。
- **未提供具体训练时长**，但给出了计算效率对比表（ms/iter和内存占用）。

## 5. 实验数量与充分性

### 实验数量
- **主实验结果**（表1）：7个baseline × 14个数据集 × 平均预测长度 = 98个对比项，全面展示IF的提升。
- **消融实验**（表2-3）：替换IF为线性/MLP/Transformer解码器；去除或只保留跳跃连接。
- **计算效率对比**（表4）：4个数据集上比较速度与内存。
- **变长回溯窗口实验**（图3）：T = 96, 72, 48, 24，比较IF与线性解码器。
- **可视化分析**：权重与预测能量分布（图4）。
- **统计显著性检验**（附录表6-7）：5次随机运行的标准差和配对t检验（14个数据集中13个显著，p<0.05）。

### 充分性与公平性
- 所有基线使用官方代码和相同超参数，保证公平。
- 数据按时间划分（70%训练、15%验证、15%测试），避免泄露。
- 消融实验验证了IF各组件贡献，排除了跳跃连接或非线性变换带来的干扰。
- 统计检验证实改进的显著性。

## 6. 论文的主要结论与发现

1. **IF显著提升性能**：在所有baseline上，IF带来一致且大幅的MSE/MAE降低，尤其在PeMS数据集上平均MSE降低30.4%、MAE降低18.2%。
2. **全局视角优势**：频率成分预测提供了对输出序列的整体把握，MSE改善大于MAE，表明预测更精确。
3. **编码器能力被释放**：IF的改进说明现有编码器已能提取足够信息，而原有逐点解码限制了其表达。
4. **短回溯下的鲁棒性**：IF在输入长度缩短时性能下降更平缓，优于线性解码器，说明其从有限信息中提取模式的能力更强。
5. **可解释性**：IF的幅度头学习到的权重大小与预测的能量分布一致，指示其能自动识别主导周期。

## 7. 优点

- **创新视角**：首次系统性地关注预测阶段（解码），提出基于频率分解的隐式解码范式。
- **即插即用**：IF可作为通用模块替换现有模型的输出层，无需修改编码器结构，兼容多种架构。
- **性能优异**：在14个数据集上取得SOTA，平均提升显著，且具有统计显著性。
- **设计优雅**：通过预测幅度/相位规避逐点预测的局部性问题，利用DFT/iDFT天然支持全局重构。
- **鲁棒性强**：在短输入、不同预测长度下表现稳定，消融实验设计完整。

## 8. 不足与局限

1. **计算效率**：IF相比线性或MLP解码器增加了计算开销（iDFT的O(P log P)），在大规模数据上可能成为瓶颈。
2. **固定频率池**：手动定义的频率池（大小P）可能不是最优，对于某些数据集可能引入冗余或缺失关键频率。
3. **仅考虑全局波动**：DFT基函数为全局正弦波，对局部突变或非平稳模式（如突变、趋势变化）捕捉能力有限，论文提及未来可结合小波变换。
4. **实验覆盖**：虽然数据集多样，但未在极高维度（如数百个变量）或极端长序列（如超过1000步）上测试，且未讨论金融数据中的特定挑战（如噪声、异方差）。
5. **缺乏理论分析**：未提供关于收敛性、泛化边界等理论保证，主要依赖实验验证。
6. **仅适用于点预测**：未扩展到概率预测或区间预测场景。

（完）
