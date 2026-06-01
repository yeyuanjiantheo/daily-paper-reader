---
title: "TimeStacker: A Novel Framework with Multilevel Observation for Capturing Nonstationary Patterns in Time Series Forecasting"
title_zh: TimeStacker：多级观测捕获非平稳模式的时间序列预测新框架
authors: "Qinglong Liu, Cong Xu, Wenhao Jiang, Kaixuan Wang, Lin Ma, Haifeng Li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=5RYSqSKz9b"
tags: ["query:qf"]
score: 6.0
evidence: 提出基于堆叠和频率注意力的非平稳时间序列预测框架
tldr: 现实时间序列常具有非平稳性，现有模型难以捕捉。TimeStacker通过独特的堆叠机制捕获全局和局部特征，并集成频率自注意力增强建模能力。实验在多个真实数据集上取得领先性能，适用于金融时间序列预测。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-5rysqskz9b/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5rysqskz9b/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1765, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5rysqskz9b/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 839, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5rysqskz9b/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1775, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5rysqskz9b/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 857, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5rysqskz9b/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1567, \"height\": 1334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5rysqskz9b/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1589, \"height\": 827, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-5rysqskz9b/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1766, \"height\": 647, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5rysqskz9b/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1503, \"height\": 676, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5rysqskz9b/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 805, \"height\": 574, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5rysqskz9b/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1769, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5rysqskz9b/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1777, \"height\": 123, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5rysqskz9b/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1765, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5rysqskz9b/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1766, \"height\": 161, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5rysqskz9b/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1508, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5rysqskz9b/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1163, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5rysqskz9b/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1557, \"height\": 547, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5rysqskz9b/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1773, \"height\": 1043, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5rysqskz9b/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1762, \"height\": 1952, \"label\": \"Table\"}]"
motivation: 现有模型难以同时捕获非平稳时间序列的全局和局部特征。
method: 提出堆叠机制与频率自注意力模块相结合。
result: 在多个真实数据集上优于现有方法。
conclusion: 多级观测和频率注意力有效处理非平稳性。
---

## Abstract
Real-world time series inherently exhibit significant non-stationarity, posing substantial challenges for forecasting. To address this issue, this paper proposes a novel prediction framework, TimeStacker, designed to overcome the limitations of existing models in capturing the characteristics of non-stationary signals. By employing a unique stacking mechanism, TimeStacker effectively captures global signal features while thoroughly exploring local details. Furthermore, the framework integrates a frequency-based self-attention module, significantly enhancing its feature modeling capabilities. Experimental results demonstrate that TimeStacker achieves outstanding performance across multiple real-world datasets, including those from the energy, finance, and weather domains. It not only delivers superior predictive accuracy but also exhibits remarkable advantages with fewer parameters and higher computational efficiency.

---

## 论文详细总结（自动生成）

# 论文总结：TimeStacker：多级观测捕获非平稳模式的时间序列预测新框架

## 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：现实世界的时间序列普遍具有**非平稳性**（统计特性随时间变化），传统模型难以同时捕获全局趋势与局部细节。
- **背景**：现有深度学习模型（如Transformer、MLP）多聚焦时域相关性，忽视了**频域特征**的时变规律。短时傅里叶变换（STFT）的窗长选择存在“时间-频率分辨率权衡”：大窗长捕获全局但丢失局部，小窗长反之。
- **目标**：提出一种不依赖单一时窗、而是通过**多级堆叠**聚合不同尺度频域模式的方法，提升非平稳信号的预测精度与效率。

## 2. 方法论：核心思想、关键技术细节
### 核心思想
- **多尺度堆叠（Stacking）**：将时间序列按**从大到小**的补丁（patch）序列逐层分割、聚合：大补丁优先捕获全局频率特征，小补丁逐步细化局部细节。
- **频域增强自注意力（FreqAttention）**：在频域计算补丁间相似度（利用可学习的频域滤波器），在时域完成聚合，避免傅里叶误差与频谱泄漏影响。

### 关键技术细节
- **整体架构**：
  - 输入序列先做**RevIn归一化**（减均值除方差）。
  - 依次通过 **L个StackerBlock**，每个Block对应一个补丁大小 $p_1>p_2>...>p_L$（需整除序列长度T）。
  - 每个StackerBlock内部包含：
    1. **Smooth Layer**：用卷积平滑（核大小=$p_l$）抑制异常值。
    2. **FreqAttention**：先对补丁序列做FFT得到频域表示 $\tilde{X}^{(l)}$；用可学习滤波向量 $W_q,W_k$ 做哈达玛积得到 Query和Key；在频域计算相似度矩阵 $CorMat=Softmax( (W_q\odot\tilde{X})\cdot(W_k\odot\tilde{X})^T/\sqrt{d_k} )$；最后在时域用该矩阵聚合Value $V=X^{(l)}W_v$。
  - 残差连接：`StackerBlock(X) = FreqAttention(SmoothLayer(X) + X) + X`。
- **预测头**：最后一层输出经线性层映射到预测长度，再反归一化（加回均值方差）。
- **理论依据**：非平稳信号的傅里叶系数 $a_n(t),b_n(t)$ 随时间变化，通过多级补丁堆叠可逐步降低频率分辨率、提升时间分辨率，符合时频不确定性原理。

## 3. 实验设计
### 数据集与场景
- **8个真实数据集**：ETTh1、ETTh2、ETTm1、ETTm2（电力）、Traffic（交通）、Electricity（电力）、Weather（天气）、Exchange（汇率）。覆盖能源、交通、天气、金融领域。
- **任务**：长序列预测（输入长度96，预测长度{96,192,336,720}）。部分实验也测试了不同回溯长度（96/192/336/720）。
- **数据划分**：训练/验证/测试=6:2:2（时序划分，防止数据泄露）。

### 对比方法
- **Transformer系**：Crossformer、PatchTST、SAMformer、iTransformer。
- **MLP/线性系**：DLinear、RLinear、SparseTSF、SOFTS、TimeMixer。
- 额外在附录中对比了**多分辨率方法**N-HiTS、频域方法FEDformer、FiLM。

### 评估指标
- **MSE**（侧重全局误差、对异常敏感）和**MAE**（衡量平均绝对偏差）。所有结果取4种预测长度的平均值。

## 4. 资源与算力
- 文中明确提到实验使用 **NVIDIA RTX 4080 GPU（16GB）**，框架为PyTorch 2.0。
- **未明确给出总体训练时长**，仅在复杂度分析时报告了“训练时间（ms/iter）”：TimeStacker在输入长度96下约115 ms/iter（batch size=128），GPU内存约24.9 MB。对比模型如DLinear约59 ms/iter、SparseTSF约108 ms/iter。
- **未说明训练轮数、总迭代次数**，仅给出学习率1e-3、Adam优化器等基础配置。

## 5. 实验数量与充分性
- **主要结果（表1）**：在8个数据集×4种预测长度共32个设置下，与9个基线进行MSE/MAE对比。TimeStacker在**15/26**次排名第一，显著领先。
- **消融实验（表2）**：在ETTh1/ETTh2/Exchange三个数据集上，对FreqAttention进行替换/移除、对哈达玛积进行替换/移除，验证各模块有效性。
- **回溯长度影响（表3、图4）**：在ETTh1、ETTh2、Exchange上测试4种回溯长度，并与其他模型对比。
- **补丁列表组合影响（附录表7）**：在ETTm1上测试不同补丁大小序列组合的敏感性。
- **复杂性分析（表8）**：对比输入长度192~3072下的GPU内存与训练时间。
- **单变量实验（附录表10）**：在Traffic和Electricity上测试单变量预测（原多变量下降），发现其优势减弱。
- **合成信号可视化（图7）**：展示非线性频率变化信号下的预测效果。
- **充分性评价**：实验覆盖了多种领域、多种预测长度、不同回溯长度、消融与替换、计算效率对比，较为充分。但**未在更多数据集（如ILI疾病）或更高维度（>862变量）上验证**；多变量场景存在性能瓶颈，实验仅补充了单变量对比，未深入分析原因。

## 6. 主要结论与发现
- **TimeStacker 在多数真实数据集上达到最佳或次佳预测精度**，尤其在能源、天气、汇率数据上显著优于iTransformer、PatchTST等强基模型。
- **频域自注意力显著优于传统时域自注意力**：消融实验表明，移除FreqAttention或替换为传统注意力均导致性能下降。
- **堆叠机制有效利用长回溯窗口信息**：随着回溯长度增加，TimeStacker在ETTh1/ETTh2上精度持续提升，而部分对比模型（如SAMformer）效果不稳定。
- **计算效率高**：参数量少、内存占用低（仅24.9 MB/115ms每步），远低于Crossformer等模型，适合资源受限场景。
- **局限**：在多变量密集场景（Traffic、Electricity）中性能不如SOFTS等专门处理多通道的方法，表明频率相似度计算可能被多通道噪声干扰。

## 7. 优点
- **方法创新性**：首次将“多级堆叠”与“频域注意力”结合，优雅解决了时频分辨率权衡问题，且无需手工选择单一时窗。
- **理论支撑**：从时频不确定性原理出发，为堆叠机制提供数学解释。
- **实验全面性**：涵盖多种领域、多种预测长度、消融、复杂度、回溯长度、合成数据验证，对比方法最新。
- **效率优势**：计算复杂度 $O(L\log_2 p)$ 远低于传统自注意力 $O(Lp)$，内存占用小，适合部署。
- **伪代码与超参数公开**：附录给出算法流程及数据集特定配置，可复现性强。

## 8. 不足与局限
- **多变量性能瓶颈**：作者自己指出在Traffic、Electricity等变量较多（862、321维）的数据集上表现不如SOFTS，且实验仅补充了单变量对比，**未深入分析堆叠机制在多维度下的失效原因**。
- **数据集覆盖有限**：未在医疗、文本、传感器等其他常见序列模态上测试，泛化性存疑。
- **超参数敏感**：补丁列表大小需按数据集手动配置（如ETTh用6个补丁，Exchange用3个），未给出自动选择或鲁棒性分析。
- **缺乏显著性检验**：表6虽给出多次运行的标准差，但未报告统计显著性（如p值），结论的稳健性有待更严格验证。
- **对长预测步长表现不稳定**：在720步预测中，部分数据集（如ETTh1）MSE相对960/192步下降明显，说明长期预测能力仍受挑战。
- **算力信息不完整**：未给出总训练时间、模型参数量确切数值、推理速度等关键指标，难以完整评估工程可用性。

（完）
