---
title: "DBLoss: Decomposition-based Loss Function for Time Series Forecasting"
title_zh: DBLoss：基于分解的时间序列预测损失函数
authors: "Xiangfei Qiu, Xingjian Wu, Hanyin Cheng, Xvyuan Liu, Chenjuan Guo, Jilin Hu, Bin Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=SbhBIkiRLT"
tags: ["query:qf"]
score: 7.0
evidence: 基于分解的时间序列预测损失函数
tldr: 现有MSE损失在预测期内难以捕捉季节性和趋势。本文提出DBLoss，利用指数移动平均将预测目标分解为季节和趋势成分，分别计算损失。实验显示该方法在多个领域（经济、交通、能源）提高了预测精度，且易于集成到现有模型。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbhbikirlt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbhbikirlt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbhbikirlt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 767, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbhbikirlt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 239, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbhbikirlt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 865, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbhbikirlt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1467, \"height\": 1180, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbhbikirlt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 1359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbhbikirlt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1457, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbhbikirlt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1451, \"height\": 559, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbhbikirlt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1452, \"height\": 444, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbhbikirlt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1448, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbhbikirlt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1027, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbhbikirlt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1025, \"height\": 463, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbhbikirlt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1025, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbhbikirlt/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1449, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbhbikirlt/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1450, \"height\": 1361, \"label\": \"Table\"}]"
motivation: MSE损失不能有效捕捉预测期内的季节性和趋势模式。
method: 使用指数移动平均分解预测目标为季节和趋势，计算分离损失。
result: 在多个数据集上提升预测精度，且模型无关。
conclusion: 提供了一种简单有效的损失函数改进，可广泛应用于时序预测。
---

## Abstract
Time series forecasting holds significant value in various domains such as economics, traffic, energy, and AIOps, as accurate predictions facilitate informed decision-making. However, the existing Mean Squared Error (MSE) loss function sometimes fails to accurately capture the seasonality or trend within the forecasting horizon, even when decomposition modules are used in the forward propagation to model the trend and seasonality separately. To address these challenges, we propose a simple yet effective Decomposition-Based Loss function called DBLoss. This method uses exponential moving averages to decompose the time series into seasonal and trend components within the forecasting horizon, and then calculates the loss for each of these components separately, followed by weighting them. As a general loss function, DBLoss can be combined with any deep learning forecasting model. Extensive experiments demonstrate that DBLoss significantly improves the performance of state-of-the-art models across diverse real-world datasets and provides a new perspective on the design of time series loss functions.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在时间序列预测中，广泛使用的均方误差（MSE）损失函数有时无法准确捕捉预测区间内的季节性和趋势模式，即便模型在前向传播中已经使用了分解模块来分别建模趋势和季节成分，预测结果仍然可能出现季节性或趋势拟合不佳的问题。
- **研究背景**：时间序列预测在经济学、交通、能源、AIOps等领域具有重要价值。近期众多深度模型（如DLinear、TimesNet、TimeMixer等）都致力于通过分解技术显式地提取时间序列中的季节性和趋势归纳偏置。然而，这些分解操作均在前向传播阶段进行，损失计算仍采用原始的距离损失（如MSE），并未在预测区间内直接对季节性和趋势进行针对性优化。
- **研究含义**：作者提出一种新的损失函数设计角度——在损失函数层面对预测结果进行分解，分别衡量季节和趋势成分的误差，从而更直接地驱动模型学习这两类模式，提升预测精度。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将预测值和真实值都通过指数移动平均（EMA）分解为季节分量和趋势分量，然后分别计算这两个分量的损失并进行加权组合，形成最终的总损失函数（称为DBLoss）。
- **关键技术细节**：
  - **EMA分解模块**：使用指数移动平均（Exponential Moving Average）来提取趋势成分。具体地，对时间序列施加指数衰减权重，计算加权累积和并归一化得到趋势项，残差即为季节项。平滑因子α（0<α<1）控制平滑程度，α越小趋势越平滑。
  - **季节性损失与趋势损失**：
    - 季节性损失（LS）：预测季节分量与真实季节分量的MSE。
    - 趋势损失（LT）：预测趋势分量与真实趋势分量的MAE。
  - **尺度对齐机制**：为了防止两个分量因尺度差异导致某一损失主导优化，引入自适应缩放：`LT_aligned = LT × stop_grad(LS / (LT + ε))`，其中梯度被阻断，使缩放比例不影响反向传播。
  - **总损失**：`L = β · LS + (1 - β) · LT_aligned`，β为超参数，用于平衡季节和趋势损失的贡献。
- **算法流程**（文字描述）：
  1. 使用任意骨干模型生成预测值Ŷ。
  2. 将预测值Ŷ和真实值Y输入EMA分解模块，分别得到它们的季节分量（Ŷ_S, Y_S）和趋势分量（Ŷ_T, Y_T）。
  3. 计算季节损失LS和趋势损失LT。
  4. 对趋势损失进行尺度对齐得到LT_aligned。
  5. 按权重β加权得到总损失L。
- **理论优势**：论文附录C从梯度分析角度证明，DBLoss去除了MSE中趋势误差与季节误差的交叉耦合项，使得两个分量可以独立优化，避免相互干扰。

## 3. 实验设计

- **数据集**：使用8个公开的长期多元时间序列预测基准数据集：
  - ETT系列：ETTh1、ETTh2、ETTm1、ETTm2（电力变压器温度数据，小时/15分钟粒度）
  - Solar（太阳能功率，10分钟粒度）
  - Weather（气象数据，10分钟粒度）
  - Electricity（电力消耗，小时粒度）
  - Traffic（交通占用率，小时粒度）
- **骨干模型（Baselines）**：选用8个当前最先进的模型，分为两类：
  - 时间序列专用模型：iTransformer、Amplifier、PatchTST、DLinear
  - 时间序列基础模型：CALF、UniTS、TTM、GPT4TS
- **对比方法**：
  - 主要对比基准：原始MSE损失。
  - 额外与其他损失函数对比：TILDE-Q（形状相似损失）、FreDF（频域损失）、PSLoss（补丁结构损失），以DLinear为骨干在ETTh2、ETTm1、Traffic三个数据集上进行比较。
- **评价指标**：MSE和MAE。
- **预测长度**：F ∈ {96, 192, 336, 720}。
- **实现细节**：使用统一的TFB基准框架，直接重用每个基线的最优超参数设置，仅将训练损失函数从MSE替换为DBLoss，不做其他修改。不使用“Drop Last”技巧。优化器为Adam，初始batch size为64（可减半至最小8）。所有代码和数据集已公开。

## 4. 资源与算力

- 论文在第4.1节提到：所有DBLoss实验基于Python 3.8和PyTorch，运行在**NVIDIA Tesla A800 GPU**上。
- 未明确给出具体GPU数量、训练总时长、每轮训练的详细时间。但在附录F中给出了使用PatchTST时DBLoss与MSE的每轮训练时间对比（秒），结果显示DBLoss增加的开销很小（例如ETTh1上从2.36秒增至3.11秒），随着数据集规模增大增量更不明显。
- 总体而言，算力资源描述较为简略，缺乏整体训练成本（如总GPU小时数）的量化。

## 5. 实验数量与充分性

- **主实验**：在8个数据集×4个预测长度×8个骨干模型（其中4个为专用模型，4个为基础模型）上进行了大量对比，共记录了大量MSE/MAE结果（表1和表4）。
- **与其它损失函数对比**：在3个数据集（ETTh2、ETTm1、Traffic）上以DLinear为骨干与TILDE-Q、FreDF、PSLoss进行了比较（表2），并报告了5次随机种子的标准差（附录E表6-8）。
- **零样本迁移实验**：在ETT系列内进行跨数据集零样本预测（表3），验证泛化能力。
- **基础模型实验**：在5%小样本微调设置下对4个基础模型进行了实验（表4和附录G表10）。
- **超参数敏感性分析**：对β和α进行了可视化分析（图4）。
- **泛化能力分析**：绘制了训练/测试MSE曲线（图3），展示了DBLoss能降低过拟合。
- **可视化**：提供了多个数据集上的预测可视化（图5、附录D图6）。
- **充分性评估**：
  - **优势**：实验覆盖8个多样化的真实数据集、多个骨干模型、多种预测长度，并横向对比了其他损失函数，交叉验证了有效性；零样本和小样本实验进一步验证了泛化性。
  - **不足**：所有实验仅在一个GPU型号（A800）上运行，未提供在同一硬件下的性能波动（如不同随机种子下的方差仅在部分附表中给出）；部分实验（如其他损失函数对比）仅基于单一骨干模型（DLinear），未在所有骨干上重复，可能不足以完全排除骨干依赖；超参数β和α的调优策略未自动化，实验依赖于手动设定。

## 6. 论文的主要结论与发现

- DBLoss在几乎所有设置中一致地优于原始MSE损失，且在多数情况下优于其他形状/频域/结构损失函数（TILDE-Q、FreDF、PSLoss）。
- 即使对于已经在前向传播中使用了分解的模型（如DLinear），DBLoss仍能带来额外提升，说明在损失层面进行分解具有互补作用。
- DBLoss能显著提升模型的泛化能力：在零样本迁移和小样本微调场景下均取得更好的性能。
- 使用DBLoss训练的模型虽然在训练阶段的误差略高，但在测试阶段的误差更低且更稳定，表明其具有更强的抗过拟合能力。
- 超参数β（季节性权重）和α（平滑因子）对性能有影响，最佳取值因数据集和模型而异。对于季节性强数据（如Traffic），较大的β和较小的α更好；对于季节性不强的数据（如ETTh2），需要平衡两个分量。

## 7. 优点

- **创新性**：首次在损失函数层面对预测区间进行季节-趋势分解，为时序预测损失函数设计提供了新视角。
- **简单有效**：方法实现简单（基于EMA分解），计算开销极小（仅增加不到30%的单轮训练时间），易于集成到任何深度学习模型中。
- **通用性强**：在多种基准测试中，DBLoss对专用模型和基础模型均能带来一致提升，且无需修改模型结构或训练策略。
- **实验充分**：在8个数据集、4种预测长度、8个骨干模型及多个损失函数对比下验证了有效性，并包含零样本和少样本实验。
- **理论支撑**：附录C提供了梯度分析的数学证明，解释为何DBLoss能独立优化季节和趋势分量。

## 8. 不足与局限

- **超参数选择缺乏自动化**：β和α需要手动调节，且最佳值因数据集和模型而异。论文未提供自动调优策略，在实践应用中可能增加额外调参成本。作者也承认这是未来研究方向。
- **计算资源报告不完整**：未明确给出总训练时间、GPU数量等算力消耗指标，仅附录F给出了单个模型（PatchTST）的每轮训练时间，可复制性细节不足。
- **实验覆盖面的局限**：
  - 与其他损失函数的对比仅基于一个骨干模型（DLinear），且仅在3个数据集上完成，可能不足以完全证明DBLoss在所有场景下优于这些方法。
  - 未包含超长预测跨度（如>720）或极短预测长度的实验。
  - 未讨论DBLoss在单变量预测场景下的表现（论文主要聚焦多元）。
- **理论基础假设的合理性**：理论分析假设趋势和季节分量高度独立，实际时间序列中二者可能相关（如趋势变化影响季节模式），该假设的普适性需进一步验证。
- **局限性声明**：论文在附录H明确提出了自动调参缺失这一局限性，体现了作者的诚实态度。

（完）
