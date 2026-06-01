---
title: "TimeEmb: A Lightweight Static-Dynamic Disentanglement Framework for Time Series Forecasting"
title_zh: TimeEmb：用于时间序列预测的轻量级静态-动态解耦框架
authors: "Mingyuan Xia, Chunxu Zhang, Zijian Zhang, Hao Miao, Qidong Liu, Yuanshao Zhu, Bo Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=sLfMvrkn6T"
tags: ["query:qf"]
score: 7.0
evidence: 时序预测的静态-动态解耦
tldr: 时间序列的非平稳性导致分布偏移下预测困难。现有方法常混淆长期静态和短期动态模式。本文提出TimeEmb，一个轻量级静态-动态解耦框架，将时间序列分为时不变和时变因子分别建模，从而提升分布偏移下的预测鲁棒性。实验表明该方法在多个基准上表现优异，且计算开销小。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-slfmvrkn6t/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 714, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-slfmvrkn6t/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 797, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-slfmvrkn6t/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1400, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-slfmvrkn6t/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-slfmvrkn6t/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 570, \"height\": 929, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-slfmvrkn6t/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1324, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-slfmvrkn6t/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1346, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-slfmvrkn6t/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1398, \"height\": 406, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-slfmvrkn6t/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 853, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-slfmvrkn6t/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-slfmvrkn6t/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-slfmvrkn6t/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1463, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-slfmvrkn6t/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1253, \"height\": 1334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-slfmvrkn6t/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1254, \"height\": 1335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-slfmvrkn6t/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 896, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-slfmvrkn6t/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 833, \"height\": 676, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-slfmvrkn6t/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1206, \"height\": 761, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-slfmvrkn6t/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1205, \"height\": 764, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-slfmvrkn6t/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1031, \"height\": 1245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-slfmvrkn6t/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1115, \"height\": 825, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-slfmvrkn6t/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1203, \"height\": 755, \"label\": \"Table\"}]"
motivation: 时间序列非平稳性导致分布偏移，现有方法难以区分静态和动态成分。
method: 将时间序列解耦为时不变和时变因子，分别建模后融合。
result: 在多个非平稳时间序列数据集上预测精度提升，且模型轻量。
conclusion: 为时间序列预测中的分布偏移问题提供了有效的解耦方案。
---

## Abstract
Temporal non-stationarity, the phenomenon that time series distributions change over time, poses fundamental challenges to reliable time series forecasting. Intuitively, the complex time series can be decomposed into two factors, i.e., time-invariant and time-varying components, which indicate static and dynamic patterns, respectively. Nonetheless, existing methods often conflate the time-varying and time-invariant components, and jointly learn the combined long-term patterns and short-term fluctuations, leading to suboptimal performance facing distribution shifts. To address this issue, we initiatively propose a lightweight static-dynamic decomposition framework, TimeEmb, for time series forecasting. TimeEmb innovatively separates time series into two complementary components: (1) time-invariant component, captured by a novel global embedding module that learns persistent representations across time series, and (2) time-varying component, processed by an efficient frequency-domain filtering mechanism inspired by full-spectrum analysis in signal processing. Experiments on real-world datasets demonstrate that TimeEmb outperforms state-of-the-art baselines and requires fewer computational resources. We conduct comprehensive quantitative and qualitative analyses to verify the efficacy of static-dynamic disentanglement. This lightweight framework can also improve existing time-series forecasting methods with simple integration. To ease reproducibility, our code is available at https://github.com/showmeon/TimeEmb.

---

## 论文详细总结（自动生成）

### 论文中文总结

#### 1. 核心问题与整体含义  
- **背景**：时间序列预测面临非平稳性挑战，即数据分布在时间上不断变化，违背了大多数预测方法的独立同分布（IID）假设。  
- **问题**：现有方法通常将长期静态模式（时不变）与短期动态波动（时变）混杂在一起共同学习，导致在分布偏移下表现不佳。  
- **目标**：提出一种轻量级的解耦框架，显式分离时不变和时变分量，分别建模以提高预测鲁棒性和效率。

#### 2. 方法论  
- **核心思想**：在频域中对时间序列进行静态‑动态解耦。  
- **关键技术**：  
  - **时不变分量（Xs）**：通过一个可学习的嵌入库（embedding bank） E ∈ ℝ^{M×F×D} 获取。根据输入序列最后一个时间戳检索对应嵌入，捕捉跨日、跨周的稳定周期性模式（如交通流量早晚高峰）。  
  - **时变分量（Xd）**：将原始序列的频域表示减去 Xs 得到 Xd，再通过可学习的频域滤波器 Hω（复数调制向量）进行元素级乘法，强调有用频率、抑制噪声。  
  - **融合与预测**：将滤波后的动态分量与静态分量相加，经 IFFT 变换回时域，再通过两层 MLP 进行预测。  
- **优化目标**：结合时域 MSE 和频域 MAE 损失：  
  L = α·MAE(FFT(Ŷ), FFT(Y)) + (1-α)·MSE(Ŷ, Y)。  
- **计算效率**：嵌入查找 O(M)，频域滤波 O(F×D)，主要开销来自 FFT（O(D×L log L)），整体线性复杂度。

#### 3. 实验设计  
- **数据集**：7 个真实世界基准：ETTh1, ETTh2, ETTm1, ETTm2（电力变压器温度）、Weather、Electricity (ECL)、Traffic。  
- **预测设置**：回溯窗口长度 L ∈ {96, 336, 720}，预测长度 H ∈ {96, 192, 336, 720}。  
- **对比方法**：三类：  
  - 频率基：FilterNet, FITS, FreTS  
  - MLP基：DLinear, CycleNet  
  - Transformer基：iTransformer, PatchTST, Fredformer  
- **实现细节**：PyTorch 2.1，单张 NVIDIA RTX 4090 24GB GPU，训练 30 epochs，早停 patience=5。批量大小：ETT 和 Weather 为 256，其余为 64。学习率从 {0.0005, 0.001, 0.002, 0.005} 中选择。隐藏层维度固定为 512。

#### 4. 资源与算力  
- **GPU**：单张 NVIDIA RTX 4090（24GB 显存）。  
- **训练时长**：在 Electricity 数据集上，TimeEmb 每 epoch 约 19.8 秒（参见 Figure 1），但未给出完整实验的总训练耗时。  
- **参数规模**：TimeEmb 仅 0.91M 参数（以 Electricity 为例），远低于 Transformer 类模型（如 iTransformer 5.15M）。  
- **文中未明确说明**：总 GPU 小时数、是否使用多卡、以及推理时间等信息。

#### 5. 实验数量与充分性  
- **主要实验**：Table 1 展示了 L=96 下 4 个预测长度的 MSE/MAE，覆盖全部 7 个数据集。Table 2 补充了 L=336 和 L=720 的结果（部分数据集）。  
- **消融实验**：  
  - 频域分析：保留 top-k 振幅频率或低通滤波比例对性能的影响（Figure 5a,b）。  
  - 组件消融：替换嵌入库为随机/零/均值、移除 Xs 或滤波器 Hω（Figure 5c,d 和 Appendix Table 11）。  
- **兼容性实验**：将 TimeEmb 作为插件集成到 Linear、MLP、DLinear、iTransformer 中，均带来稳定提升（Table 3）。  
- **可视化**：T-SNE 分布对比、频域谱图、预测样例等（Figure 3,4,7,8）。  
- **充分性评价**：实验覆盖多种回溯/预测长度、多类型基线，并进行了统计显著性报告（±标准差），消融设计全面。但部分结果（如 L=336/720 的完整表）放于附录，主文只列了平均性能。

#### 6. 主要结论与发现  
- TimeEmb 在几乎所有设置下优于 SOTA，平均 MSE 相对降低 3.0%–8.7%。  
- 解耦后的时变分量在 T-SNE 上呈现更清晰的聚类，验证了分离有效性。  
- 轻量架构在性能与效率间取得最佳平衡：比 iTransformer 参数少 5 倍以上，训练更快且精度更高。  
- 可作为即插即用模块增强现有方法，仅增加少量计算成本。

#### 7. 优点  
- **创新性**：首次将可学习嵌入库与频域解耦结合，显式分离全局静态模式与局部动态波动。  
- **轻量高效**：计算复杂度近线性，参数极少，适合资源受限场景（如边缘设备）。  
- **可解释性**：通过频域分析观察不同频率分量的贡献，嵌入库可视化揭示了周期性模式。  
- **通用性**：作为插件可提升多种主流模型，仅增加微小开销。  
- **实验严谨**：报告多次运行标准差，消融充分，可视化丰富。

#### 8. 不足与局限  
- **固定分辨率**：嵌入库采用固定时间步粒度（如每小时），无法自适应多尺度周期。  
- **离散结构**：嵌入是离散的，难以建模连续演变的周期性（如季节长度逐渐变化）。  
- **实验覆盖**：部分长回溯窗口（L=720）的结果只在附录中完整展示，且未测试超长序列（如 L>720）。  
- **假设依赖**：依赖离散步长划分（如 24 小时），对无明确周期或周期不稳定的数据集可能效果有限。  
- **理论分析有限**：附录虽提供了频域滤波的卷积定理证明，但未深入分析解耦可识别性。

（完）
