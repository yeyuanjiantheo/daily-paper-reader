---
title: Minimax Adaptive Online Nonparametric Regression over Besov spaces
title_zh: 贝索夫空间上的极小极大自适应在线非参数回归
authors: "Paul Liautaud, Pierre Gaillard, Olivier Wintenberger"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=nKuFQhKZtt"
tags: ["query:qf"]
score: 4.0
evidence: 自适应在线非参数回归用于时间序列
tldr: 本文提出一种自适应小波算法用于贝索夫空间上的在线非参数回归，实现了对函数光滑性参数和空间局部变化的自适应，并达到极小极大最优遗憾界。该算法能够在对抗性环境下进行序贯预测，适用于金融时间序列中非平稳和结构突变的情况。主要贡献在理论层面，提供了面向复杂函数类的在线学习框架。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nkufqhkztt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 506, \"height\": 610, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nkufqhkztt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 600, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nkufqhkztt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 660, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nkufqhkztt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 906, \"height\": 393, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-nkufqhkztt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1311, \"height\": 481, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nkufqhkztt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1399, \"height\": 653, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nkufqhkztt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1270, \"height\": 744, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nkufqhkztt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 613, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nkufqhkztt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1119, \"height\": 475, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nkufqhkztt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 837, \"height\": 377, \"label\": \"Table\"}]"
motivation: 现有在线回归算法无法自适应未知的函数光滑性参数。
method: 基于小波分解的自适应预测算法，无需要求先验知识即能逼近任意Besov函数。
result: 在理论上建立了极小极大最优遗憾界，并设计了局部自适应扩展。
conclusion: 为在线非参数回归提供了通用自适应框架，可应用于金融时间序列的实时预测。
---

## Abstract
We study online adversarial regression with convex losses against a rich class of continuous yet highly irregular competitor functions,% prediction rules, 
modeled by Besov spaces $B_{pq}^s$ with general parameters $1 \leq p,q \leq \infty$ and smoothness $s > \tfrac{d}{p}$. 
We introduce an adaptive
wavelet-based algorithm that performs sequential prediction without prior knowledge of $(s,p,q)$, and establish minimax-optimal regret bounds against any comparator in $B_{pq}^s$.
We further design a locally adaptive extension capable of sequentially adapting to spatially inhomogeneous smoothness. This adaptive mechanism adjusts the resolution of the predictions over both time and space, yielding refined regret bounds in terms of local regularity. Consequently, in heterogeneous environments, our adaptive guarantees can significantly surpass those obtained by standard global methods.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：在线回归（online regression）环境下，目标函数可能高度不规则（如属于贝索夫空间 \(B_{pq}^s\)），传统的平滑类假设（如Lipschitz、RKHS）不再适用。现有算法大多需要预先知道函数的平滑性参数 \((s,p,q)\)，且无法自适应空间不均匀的平滑度。
- **核心问题**：如何设计一种**无需先验知识**的在线预测算法，能够与任意贝索夫空间中的复杂函数进行竞争，并达到极小极大最优的遗憾界（regret bound）；同时，如何进一步实现**局部自适应**，在空间异质性环境下显著优于全局方法。
- **整体意义**：本文在理论上建立了面向广义非参数函数类的在线学习框架，为金融时间序列、信号处理等实际场景中的实时预测提供了理论基础。

### 2. 论文提出的方法论（核心思想、关键技术细节）

- **核心思想**：利用小波多尺度表示，将函数展开为尺度系数和小波系数，通过在线梯度更新逐层学习系数；同时，通过专家聚合机制实现局部自适应。
- **关键技术细节**：
  - **算法1：在线小波分解**（Online Wavelet Decomposition）
    - 基于S-正则小波基（如Daubechies小波），从初始尺度 \(j_0\) 到最大尺度 \(J=\lceil \frac{Sd}{\varepsilon}\log_2 T\rceil\) 进行截断。
    - 每一时间步 \(t\)，只更新与当前输入 \(x_t\) 相关的活跃系数（active coefficient set）。
    - 梯度计算：\(g_{j,k,t} = \ell'_t(\hat f_t(x_t)) \cdot \varphi_{j,k}(x_t)\)，其中 \(\varphi_{j,k}\) 为小波或尺度函数。
    - 更新规则采用“无参数”（parameter-free）的一阶算法（如coin-betting），满足假设1：\(\sum_t g_t(c_t-c) \le |c-c_1|\left(C_1\sqrt{\sum_t g_t^2}+C_2\hat G\right)\)。
  - **算法2：自适应在线小波回归**（Adaptive Online Wavelet Regression）
    - 构建多尺度二进划分树，每个节点对应一个局部区域 \(X_n\) 和初始尺度 \(j_0 = l(n)\)。
    - 每个节点上运行一个全局小波预测器 \(\hat f_{j_0}\) 的局部版本 \(\hat f_{n,a_n}\)，其中 \(a_n\) 取自精度为 \(T^{-1/2}\) 的网格。
    - 在线聚合：使用“睡眠专家”（sleeping experts）框架，通过满足假设2的聚合算法（如第二界算法）加权组合各专家预测。
    - 预测值被裁剪到 \([-B,B]\)（\(B\ge\|f\|_\infty\)），确保梯度的有界性。
- **流程图/文字描述**：
  - 算法1：输入当前系数 → 预测 → 接收梯度 → 仅更新活跃系数（按假设1的更新规则）→ 输出下一时刻系数。
  - 算法2：初始化专家集及权重 → 每轮根据输入确定活跃专家 → 聚合预测 → 接收梯度 → 更新聚合权重（假设2）→ 并行更新各专家的局部小波系数（算法1）。

### 3. 实验设计

- **该论文是纯理论工作**，未进行任何数值实验或仿真。
- **Benchmark与对比方法**：文中以表格形式（表1、表2）对比了已有在线回归方法（Vovk 2006/2007、Gaillard & Gerchinovitz 2015、Zadorozhnyi et al. 2021、Liautaud et al. 2025等）在贝索夫空间上所能达到的遗憾率及所需输入参数。对比表明本文算法在更广的参数范围（\(p,q\ge1\)，\(s>d/p\)）下实现了极小极大最优率，且算法是构造性的（polynomial-time），而此前方法多不可实现或非最优。
- **场景**：理论上分析了两种损失函数情形——一般凸损失和指数凹（exp-concave）损失，以及全局均匀光滑和局部非均匀光滑的竞争者。

### 4. 资源与算力

- 文中**没有提及**任何计算资源、GPU型号、训练时长等信息，因为论文本身不包含实验。
- 只在附录F中分析了算法的时间复杂度：
  - 算法1：\(O(T \cdot J \cdot S^d) = O\left(T \cdot \frac{Sd}{\varepsilon}\log_2 T \cdot S^d\right)\)
  - 算法2：\(O\left(T \cdot |\mathcal{A}|^\lambda \cdot J_0 \cdot J \cdot S^d\right) = O\left(T^{1+\lambda/2} \cdot \frac{S^2 d^2}{\varepsilon^2}\log_2^2 T \cdot S^d\right)\)
  - 其中 \(S\) 是小波正则度，\(d\) 是输入维度，\(\lambda\) 是空间重叠常数。

### 5. 实验数量与充分性

- **无实验**。论文完全基于理论分析和证明，包括定理1、推论1、定理2（局部自适应）等。证明过程在附录中详细展开（附录A-C）。
- **充分性评价**：作为理论文章，其结论的充分性体现在覆盖了多种损失函数、多种平滑性参数、全局与局部自适应场景，且与极小极大下界匹配。无需通过实验验证理论结果。

### 6. 论文的主要结论与发现

- **定理1**（全局算法）：对任意 \(f\in B_{pq}^s\)（\(s>d/p\)），算法1的遗憾界为：
  - 当 \(s\ge d/2\) 或 \(p<2\) 时：\(R_T(f) \le C G \|f\|_{B_{pq}^s} \sqrt{T}\);
  - 当 \(p\ge2\) 且 \(s<d/2\) 时：\(R_T(f) \le C G \|f\|_{B_{pq}^s} T^{1-s/d}\)。
  该界极小极大最优，且算法自动适应未知参数 \((s,p,q)\)。
- **推论1**（Hölder空间）：对 \(f\in C^s(X)\)，得到显式形式，包含 \(|f|_s\) 和 \(\|f\|_\infty\)。
- **定理2**（局部自适应算法2）：遗憾界表示为各局部区域 \(X_n\) 上局部平滑度 \(s_n\) 的函数，在损失为凸时可达 \(O\left(B\sqrt{|T_n|} + 2^{-l(n)s_n}\|f\|_{s_n} |T_n|^{r_n}\right)\)；损失为指数凹时可达 \(O\left(B + 2^{-l(n)s_n}\|f\|_{s_n} |T_n|^{r_n}\right)\)，其中 \(r_n = 1/2\) 或 \(1-s_n/d\)。该界在空间异质性环境下明显优于全局方法。
- **主要发现**：首次将小波理论与在线非参数回归结合，构造出计算可行且极小极大最优的算法，并可进一步局部自适应。

### 7. 优点

- **理论创新**：首次在贝索夫空间上实现了构造性的极小极大最优在线回归，覆盖了此前方法无法处理的参数范围（\(p<2\)、低光滑度）。
- **自适应性强**：算法无需知道函数的光滑性参数，自动在高低光滑度间权衡；局部扩展版本能动态适应空间不均匀的平滑度，理论上可大幅降低遗憾。
- **计算可行性**：算法具有多项式时间复杂度（线性或拟线性于 \(T\) 和维度 \(d\)），与现有不可实现的方法形成鲜明对比。
- **证明严谨**：所有定理证明详细，包含非线性逼近、最优停止尺度选择、专家聚合等关键步骤。

### 8. 不足与局限

- **缺乏实验验证**：纯理论论文，没有数值实验或实际数据集测试，其实际应用效果未知。
- **假设较强**：要求 \(s>d/p\) 以保证函数连续有界；对于 \(s\le d/p\)（无界函数）仅进行了讨论，未给出完整算法与保证（附录D指出此情形下可能需要额外条件或下界未闭合）。
- **维度诅咒**：时间复杂度中正则度 \(S\) 以指数 \(d\) 增长（\(S^d\)），高维时计算复杂，实际中需采用低正则度小波（如Haar）可能牺牲近似精度。
- **局部自适应部分假设全局参数 \(p,q\) 不变**，仅允许平滑度 \(s\) 局部变化，更通用的“完全局部贝索夫空间”（允许 \(p,q\) 也变化）留作未来工作。
- **聚合算法要求梯度的有界性**，依赖于截断操作，可能引入轻微偏差。

（完）
