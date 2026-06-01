---
title: "CFPT: Empowering Time Series Forecasting through Cross-Frequency Interaction and Periodic-Aware Timestamp Modeling"
title_zh: CFPT：通过跨频交互和周期感知时间戳建模增强时间序列预测
authors: "Feifei Kou, Jiahao Wang, Lei Shi, Yuhan Yao, Yawen Li, Suguo Zhu, Zhongbao Zhang, Junping Du"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=hHYjiOJFum"
tags: ["query:qf"]
score: 6.0
evidence: 通过跨频交互的长期时间序列预测
tldr: 本文提出CFPT方法，通过频域特征融合机制学习不同频率分量间的交互，并利用周期性时间戳建模增强预测。该方法针对长期时间序列预测中频域交互和时间戳周期性利用不足的问题，在多个基准上取得了先进性能，可应用于金融时间序列的长期波动率预测。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-hhyjiojfum/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhyjiojfum/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 858, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhyjiojfum/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1767, \"height\": 959, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhyjiojfum/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 842, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhyjiojfum/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 851, \"height\": 732, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhyjiojfum/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1433, \"height\": 944, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-hhyjiojfum/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1775, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hhyjiojfum/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hhyjiojfum/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 871, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hhyjiojfum/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1755, \"height\": 681, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hhyjiojfum/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 954, \"height\": 535, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hhyjiojfum/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1774, \"height\": 1574, \"label\": \"Table\"}]"
motivation: 现有方法忽略了频率分量间的交互和时间戳的周期性信息。
method: 设计频域特征融合分支学习跨频交互，并构建周期感知时间戳建模模块。
result: 在长期预测任务上超越现有方法。
conclusion: 为长期时间序列预测提供了有效的新方法。
---

## Abstract
Long-term time series forecasting has been widely studied, yet two aspects remain insufficiently explored: the interaction learning between different frequency components  and the exploitation of periodic characteristics inherent in timestamps. To address the above issues, we propose **CFPT**, a novel method that empowering time series forecasting through **C**ross-**F**requency Interaction (CFI) and **P**eriodic-Aware **T**imestamp Modeling (PTM). To learn cross-frequency interactions, we design the CFI branch to process signals in frequency domain and captures their interactions through a feature fusion mechanism. Furthermore, to enhance prediction performance by leveraging timestamp periodicity, we develop the PTM branch which transforms timestamp sequences into 2D periodic tensors and utilizes 2D convolution to capture both intra-period dependencies and inter-period correlations of time series based on timestamp patterns. Extensive experiments on multiple real-world benchmarks demonstrate that CFPT achieves state-of-the-art performance in long-term forecasting tasks. The code is publicly available at this repository: https://github.com/BUPT-SN/CFPT.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：长期时间序列预测中，现有方法存在两个未被充分探索的方面：一是不同频率分量之间的交互学习（现有方法要么忽略频域，要么统一处理、只保留低频或简单加权求和，未建模跨频交互）；二是时间戳中固有的周期性特征利用不足（现有方法通过简单嵌入或注意力机制，未能显式建模周期内依赖和周期间相关性）。
- **整体含义**：论文提出 **CFPT** 框架，通过 **跨频交互**（CFI）和 **周期感知时间戳建模**（PTM）两个分支，分别捕捉频域交互和时间戳周期性模式，以提升长期预测精度。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程（用文字说明即可）

- **核心思想**：双分支协同。CFI 分支在频域内将信号分离为高频和低频，通过耦合网络实现跨频交互；PTM 分支将 1D 时间戳序列转换为 2D 周期张量，利用 2D 卷积同时捕获周期内依赖和周期间相关性。
- **关键技术细节**：
  - **CFI 分支**：
    - 对输入序列进行 DFT，得到频域表示 \( F \)。
    - 以中位频率为阈值，分为低频 \( F_L \) 和高频 \( F_H \)。
    - 分别提取实部/虚部后拼接，经过线性层得到特征 \( h_L, h_H \)。
    - 使用 L 层耦合网络进行交互（公式 14-15）：
      \[
      h_L^{k+1} = h_L^k \odot \exp(\rho(h_H^k)) + \eta(h_H^k)
      \]
      \[
      h_H^{k+1} = h_H^k \odot \exp(\nu(h_L^{k+1})) + \omega(h_L^{k+1})
      \]
    - 交互后经线性层、拆分、重组复数，再通过 IDFT 得到预测 \( \hat{X}_{CFI} \)。
  - **PTM 分支**：
    - 通过时间戳分层处理（THP）提取多粒度特征（如 HourOfDay、DayOfWeek 等），归一化至 [-0.5, 0.5]。
    - 经线性层对齐到变量维度 \( N \)。
    - 按周期长度 \( P \)（实验中固定为 24）将 1D 序列重塑为 2D 张量 \( \hat{Z}_A \in \mathbb{R}^{N \times P \times \lfloor \tau'/P \rfloor} \)。
    - 使用 \( k \times k \) 2D 卷积同时建模周期内和周期间模式，再经两个维度保持的线性映射，得到 \( \hat{X}_{PTM} \)。
  - **双分支融合**：通过加权求和 \( \hat{X} = \gamma \hat{X}_{CFI} + (1-\gamma) \hat{X}_{PTM} \)（\( \gamma \) 为常数）。
  - **优化目标**：L2 损失 \( \mathcal{L} = \|\hat{X}_{t+1:t+\tau'} - X_{t+1:t+\tau'}\|_2^2 \)。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法。

- **数据集**：7 个真实世界基准：ETT 系列（ETTh1, ETTh2, ETTm1, ETTm2）、ECL、Traffic、Weather。涵盖电力变压器温度、电力消耗、交通流量、气象观测。
- **场景**：长期预测，输入长度固定为 96，预测长度 {96, 192, 336, 720}。
- **对比方法**：TimeXer、FilterNet、iTransformer、PatchTST、FEDformer、TimesNet、DLinear、RLinear 等 8 种代表性或 SOTA 模型。
- **评价指标**：MSE 和 MAE。

### 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。若未明确说明，也请指出这一点。

- **明确说明**：论文指出实验在单张 **NVIDIA RTX 3090 GPU**（24 GB）上进行，使用 PyTorch 2.0.0。训练固定为 **10 个 epoch**，批量大小从 {4,8,16,128} 中选择。未提及总训练时间或具体 GPU 数量，但给出了每个迭代训练时间约 **0.8s**（表 5），且参数规模较小（如 ETTm1 上不同预测长度的参数量在 1.88M~48.97M 之间）。

### 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平。

- **实验组数**：
  - **主实验**：在 7 个数据集 × 4 个预测长度 = 28 个设定下对比 9 种方法，结果列于表 1（详细结果见表 6）。
  - **消融实验**：
    - 频域相关：w/o CFI-D（不分离频率）、w/o CFI-C（无耦合层）、w/o CFI（移除整个 CFI 分支）。
    - 时间戳相关：CFPT-HT（使用历史时间戳）、CFPT-1DT（使用 1D 卷积）、w/o PTM（移除 PTM 分支）。
    - 超参数敏感性：对 γ、k、L、D 进行网格搜索（图 6）。
    - 效率分析：在 ETTm1、ETTh2、Weather 上报告参数、GPU 内存、训练时间（表 5）。
    - 可视化：在 ECL 数据集上展示预测曲线（图 5）。
- **充分性与公平性**：实验覆盖了多领域数据集，对比方法均为近期代表性工作，消融设计合理，验证了各组件贡献。但论文未报告统计显著性检验（如 t 检验），且部分结果（如 Traffic 数据集）CFPT 未取得最佳（iTransformer 稍优），文中对此给出了解释。整体实验设计较为充分客观。

### 6. 论文的主要结论与发现。

- CFPT 在长期预测任务上实现了 **6 个数据集**（7 个中的 6 个）的最优平均 MSE/MAE，在 ECL 等具有丰富周期模式的数据集上优势明显。
- 消融实验表明：(1) 频率分解、跨频交互、CFI 分支均至关重要；(2) 使用未来时间戳比历史时间戳有效，尤其长 horizon 时；(3) 2D 周期感知建模优于 1D 建模；(4) PTM 分支的移除显著降低性能。
- 超参数敏感性分析显示模型对 γ 在 [0.1, 0.7] 区间稳健，优选 k=2，D=512。
- 计算效率较高，训练时间稳定。

### 7. 优点：方法或实验设计上有哪些亮点。

- **方法亮点**：
  - 首次显式建模 **跨频交互**，通过耦合网络实现低频与高频信息双向调制。
  - **周期感知时间戳建模** 创新地将 1D 时间戳转换为 2D 张量，利用 2D 卷积同时捕获周期内依赖和周期间相关性，优于传统嵌入或注意力机制。
  - 双分支设计互补，融合权重简单有效。
- **实验设计亮点**：
  - 全面的消融（对每个关键组件进行移除或替换），验证了设计必要性。
  - 对比了 8 种具有代表性的基线，涵盖纯时序、频域、线性等不同范式。
  - 提供了超参数敏感性分析和效率分析，增强实用参考价值。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等。

- **实验覆盖**：
  - 缺少在 **更复杂场景**（如多变量预测中变量间依赖建模）下的评估，所有方法均采用 channel-wise 处理。
  - 仅验证了预测长度 96~720，未覆盖超长预测（如 >1024）或短预测。
  - 未在 **金融、医疗** 等特殊领域数据集上测试。
- **偏差风险**：
  - 固定输入长度 96，可能不适用于所有数据集的最佳表现。
  - 周期长度 P 固定为 24，未自适应，可能不匹配某些数据集的真实周期。
  - 仅报告单次运行结果（seed=2025），未提供多次重复的方差。
- **应用限制**：
  - 需要未来时间戳（PTM 分支依赖），在缺少未来时间戳的场景（如纯预测）不可用。
  - 双分支增加模型复杂度（虽然论文证明效率尚可），但相比极简线性模型仍更复杂。
  - 依赖 DFT/IDFT，对非平稳信号的适应性可能有限。

（完）
