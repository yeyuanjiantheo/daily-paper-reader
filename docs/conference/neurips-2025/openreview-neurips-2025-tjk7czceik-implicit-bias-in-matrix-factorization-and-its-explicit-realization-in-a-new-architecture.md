---
title: Implicit Bias in Matrix Factorization and its Explicit Realization in a New Architecture
title_zh: 矩阵分解的隐式偏差及其在新架构中的显式实现
authors: "Yikun Hou, Suvrit Sra, Alp Yurtsever"
date: 2025-05-11
pdf: "https://openreview.net/pdf?id=tJk7czcEIK"
tags: ["query:qf"]
score: 4.0
evidence: 矩阵分解的隐式低秩偏差与因子模型相关
tldr: 该论文分析矩阵分解中梯度下降的隐式低秩偏差，并提出新架构显式利用该偏差。低秩逼近与因子模型的稀疏结构相似，但论文未涉及金融因子模型的具体应用。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjk7czceik/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1279, \"height\": 962, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjk7czceik/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1126, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjk7czceik/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1214, \"height\": 818, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjk7czceik/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1407, \"height\": 464, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-tjk7czceik/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1309, \"height\": 390, \"label\": \"Table\"}]"
motivation: 矩阵分解隐式偏差的理论理解不足。
method: 提出约束U和V范数球、D对角化的分解模型，稳定隐式偏差。
result: 实验表明新模型始终产生低秩解。
conclusion: 隐式偏差可通过显式架构可靠实现。
---

## Abstract
Gradient descent for matrix factorization is known to exhibit an implicit bias toward approximately low-rank solutions. While existing theories often assume the boundedness of iterates, empirically the bias persists even with unbounded sequences. We thus hypothesize that implicit bias is driven by divergent dynamics markedly different from the convergent dynamics for data fitting. Using this perspective, we introduce a new factorization model: $X\approx UDV^\top$, where $U$ and $V$ are constrained within norm balls, while $D$ is a diagonal factor allowing the model to span the entire search space. Our experiments reveal that this model exhibits a strong implicit bias regardless of initialization and step size, yielding truly (rather than approximately) low-rank solutions. Furthermore, drawing parallels between matrix factorization and neural networks, we propose a novel neural network model featuring constrained layers and diagonal components. This model achieves strong performance across various regression and classification tasks while finding low-rank solutions, resulting in efficient and lightweight networks.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究动机**：梯度下降应用于矩阵分解（Burer-Monteiro 分解）时，会表现出隐式低秩偏差，即解倾向于近似低秩。然而现有理论通常假设迭代有界，而实际中即使序列无界，该偏差仍然存在。论文提出一个关键假设：隐式偏差由**发散动力学**驱动，而非数据拟合的收敛动力学。基于此，作者试图**显式地捕获并增强这种隐式偏差**，从而可靠地获得真正低秩的解，并将其推广到神经网络架构中。
- **整体含义**：通过设计显式约束和可学习对角因子的分解模型，可以稳定并放大隐式低秩偏差，不仅在矩阵补全/感知任务中有效，还能衍生出高效、轻量的前馈神经网络，为网络剪枝和压缩提供新思路。

### 2. 论文提出的方法论
- **核心思想**：将矩阵分解从 $X = UV^\top$ 改为 $X = UDV^\top$，其中 $U$ 和 $V$ 被约束在 Frobenius 范数球内（通过投影保证），$D$ 是非负对角矩阵，使得模型在不限制搜索空间的前提下实现类似幂法的缩放行为。
- **关键技术细节**：
  - **矩阵分解模型**（式 4）：$\min_{U,D} \frac12\|A(UDU^\top)-b\|_2^2$，满足 $\|U\|_F\le\alpha$，$D\succeq0$ 且为对角。通过**投影梯度法**更新 $U$ 和 $D$（式 5）。
  - **神经网络架构（UDV）**（式 7）：三层结构 $f(x)=\sum_{j=1}^m v_j w_j u_j^\top x$，约束 $\sum\|u_j\|_2^2\le1$，$\sum\|v_j\|_2^2\le1$，$w_j\ge0$。即第一、三层为约束的全连接层，中间为对角层（可视为参数化的线性激活）。
  - **固定点分析**（第 2.3 节）：证明该模型的固定点不会处于投影激活区域（即 $\|U\|_F$ 不会超越边界），且当 $U$ 趋向于增长时，算法暂时偏向于对齐 $-\nabla f$ 的负特征向量，从而逐步揭示低秩结构。
- **算法流程**：初始化 $U_0$ 随机缩放，$D_0=I$；迭代进行：计算梯度 $\nabla_U f$ 和 $\nabla_D f$，然后对 $U$ 按范数球投影，对 $D$ 进行非负投影；最终 $U$ 中只有少数非零列，$D$ 对应非零元素，自然实现低秩分解。

### 3. 实验设计
- **矩阵分解实验**：
  - **数据集/场景**：合成矩阵补全问题，$X^*=U^*U^{*\top}$，$d=100$，真实秩 $r^*=3$，采样 900 个元素（noiseless）；另含噪声版（附录 A.1）和相位恢复图像恢复（附录 A.2）。
  - **基准**：经典 Burer-Monteiro 分解（BM，即 $X=UU^\top$）。
  - **对比方法**：不同步长（$\eta=10^{-3},10^{-2},10^{-1}$）、不同初始化距离（$\xi=10^{-2},10^{-4},10^{-6}$）下的 BM vs. UDU。
- **神经网络实验**：
  - **数据集**：回归：HPART（79-26-1 结构）、NYCTTD（12-10-1）；分类：MNIST（Transfer Learning 使用 MaxViT-T, EfficientNet-B0, RegNetX-32GF）。
  - **基准**：标准两层全连接网络（UV，线性激活）和 UV-ReLU，与 UDV 比较。
  - **对比方法**：四种优化器（Adam、NAdam、MBGD、MBGDM），多种学习率（回归：$10^{-4}\sim3$；分类：$10^{-6}\sim5$），每种配置调优。
- **额外实验**（附录）：
  - 四种 UDV 变体比较（附录 B.1）。
  - 仅用 MBGDM 的结果（附录 B.2）。
  - SVD 剪枝实验（左图：剪枝后验证损失变化；右图：直接训练紧凑模型）。
  - 权重衰减对比（附录 B.6）。
  - 深度对比：三层全连接 vs. UDV（附录 B.5）。
  - LoRA 微调 LLaMA-2 的 toy example（附录 B.7）。

### 4. 资源与算力
- 文中明确提及：
  - **分类任务**：NVIDIA A100 GPU（4 核 AMD Epyc 7742 处理器）。
  - **回归任务**：单核 Intel Xeon Gold 6132。
  - **时长估计**：CPU 任务总墙钟时间约 7 天，GPU 任务约 3 天。
  - 具体每个实验的 GPU 数量、内存等未进一步说明，但代码和指令已提供。

### 5. 实验数量与充分性
- **矩阵分解实验**：改变步长和初始化共 6 组基本对比，附加噪声和图像恢复实验，覆盖典型条件。
- **神经网络实验**：3 个数据集 × 3 种架构（UDV, UV, UV-ReLU）× 4 种优化器 × 若干学习率，结果平均若干随机种子（HPART: 1000 种子，NYCTTD: 100，MNIST: 1）。此外包含剪枝、深度、权重衰减等消融实验。
- **评价**：实验设计较为全面，覆盖多种优化器和学习率，且与标准基线公平对比（相同初始化、相同迭代次数）。对剪枝的评估使用了性能退化曲线和直接训练对比。但 MNIST 分类仅 1 次运行（未报告误差棒），且缺少大规模分类数据集（如 CIFAR-100 或 ImageNet 微调）的验证，泛化性有待更多证据。

### 6. 论文的主要结论与发现
- **UDU 矩阵分解**：无论步长和初始化如何，始终收敛到**真正低秩**解（奇异值几乎为 0 的列全为 0），而经典 BM 分解仅得到近似低秩（奇异值缓慢衰减）。
- **UDV 神经网络**：在回归和分类任务上达到与标准全连接网络持平甚至更优的性能，同时展现出**极强的低秩偏差**（奇异值快速衰减）。
- **剪枝应用**：利用 SVD 截断隐藏层神经元后，压缩后的模型性能损失很小，甚至在某些情况下优于直接训练紧凑模型，说明 UDV 的隐式低秩结构有助于自然剪枝。
- **理论洞察**：固定点分析表明，UDU 的更新规则会迫使 $U$ 的列对齐 $\nabla f$ 的负特征向量，从而逐步揭示低秩方向，且不会停留在投影激活区域。

### 7. 优点
- **方法创新**：巧妙地将隐式偏差归因于发散动力学，并通过对 $U,V$ 施加范数约束 + 对角因子显式模仿幂法行为，设计出简单但有效的三因子分解。
- **实验可靠性**：对步长、初始化、优化器等关键超参数进行了系统的鲁棒性分析，验证了 UDV 的低秩偏差**不受这些因素影响**，显著优于经典 BM。
- **实用价值**：UDV 网络可自然产生低秩解，结合 SVD 剪枝可实现高效压缩，且方法简单、易实现，可与现有优化器兼容。
- **理论链接**：提供了初步的固定点分析，揭示了算法内在的低秩搜索机制，为理解隐式偏差提供新视角。

### 8. 不足与局限
- **实验覆盖不够广**：神经网络实验仅包含中/小规模数据集（HPART, NYCTTD, MNIST），未在 ImageNet 级别或更大规模任务上验证；MNIST 分类仅单次运行，缺乏统计显著性。
- **收敛速度**：论文自身提到 UDV 表现出“增秩”行为（逐渐增加有效秩），这会降低收敛速度，尤其是较慢的学习率下需要大量迭代（如矩阵实验中 10^6 次迭代）。
- **理论不完整**：固定点分析仅提供启发式理解，缺乏收敛性保证或泛化界的严格证明；对神经网络中随机梯度和动量如何影响隐式偏差的讨论不足。
- **约束选择**：当前版本采用 Frobenius 范数球约束，但其他范数（如 L1/L2 混合）可能带来不同行为，尚未比较。
- **剪枝策略的泛化性**：SVD 剪枝仅在 UDV 结构上展示，未与标准网络剪枝方法（如 magnitude pruning、structured pruning）做充分对比。
- **缺少大规模场景**：LoRA 微调仅为 toy example，且未与其他低秩适配方法（如标准 LoRA）定量比较。

（完）
