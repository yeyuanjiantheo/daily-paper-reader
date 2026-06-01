---
title: Covariate-moderated Empirical Bayes Matrix Factorization
title_zh: 协变量调节的经验贝叶斯矩阵分解
authors: "William R.P. Denault, Karl Tayeb, Peter Carbonetto, Jason Willwerscheid, Matthew Stephens"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=OrmLtoFF60"
tags: ["query:qf"]
score: 4.0
evidence: 协变量调节的经验贝叶斯矩阵分解用于因子模型
tldr: 矩阵分解中利用侧信息提升潜在结构估计是一个挑战。本文提出协变量调节的经验贝叶斯矩阵分解（cEBMF），一个模块化框架，可接受任意类型的侧信息（图像、文本、图等），并通过概率模型或神经网络处理。该方法在多种数据上展示了优越的因子恢复能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ormltoff60/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 801, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ormltoff60/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 947, \"height\": 1011, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ormltoff60/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1302, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ormltoff60/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1331, \"height\": 1289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ormltoff60/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 968, \"height\": 835, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ormltoff60/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 966, \"height\": 839, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ormltoff60/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 992, \"height\": 859, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ormltoff60/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 964, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ormltoff60/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1445, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ormltoff60/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1449, \"height\": 1643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ormltoff60/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1447, \"height\": 1658, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ormltoff60/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1124, \"height\": 320, \"label\": \"Table\"}]"
motivation: 现有矩阵分解方法难以灵活利用多种类型的侧信息来改进估计。
method: 提出cEBMF框架，将侧信息通过概率模型或神经网络融入经验贝叶斯矩阵分解。
result: 在多个基准数据集上，cEBMF在因子恢复和预测任务中优于现有方法。
conclusion: 协变量调节能有效提升矩阵分解中潜在结构的推断质量。
---

## Abstract
Matrix factorization is a fundamental method in statistics and machine learning for inferring and summarizing structure in multivariate data. Modern data sets often come with "side information" of various forms (images, text, graphs) that can be leveraged to improve estimation of the underlying structure. However, existing methods that leverage side information are limited in the types of data they can incorporate, and they assume specific parametric models. Here, we introduce a novel method for this problem, *covariate-moderated empirical Bayes matrix factorization* (cEBMF). cEBMF is a modular framework that accepts any type of side information that is processable by a probabilistic model or a neural network. The cEBMF framework can accommodate different assumptions and constraints on the factors through the use of different priors, and it adapts these priors to the data. We demonstrate the benefits of cEBMF in simulations and in analyses of spatial transcriptomics and collaborative filtering data. A PyTorch-based implementation of cEBMF with flexible priors is available at https://github.com/william-denault/cebmf_torch.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：矩阵分解（如 PCA、NMF）是分析多变量数据中潜在结构的经典方法，但现实数据常伴随多种形式的**侧信息**（如图像、文本、图结构、空间坐标等）。现有利用侧信息的方法大多局限于特定数据类型和参数化模型（例如高斯过程、线性回归），缺乏通用性和灵活性，且通常需要手动调整超参数。
- **研究动机**：希望开发一个**通用、灵活**的矩阵分解框架，能够**自动学习**如何利用任意类型的侧信息来改进潜在因子的估计，同时保持对因子形式（稀疏、非负等）的适应能力。
- **整体含义**：提出**协变量调节的经验贝叶斯矩阵分解（cEBMF）**，将侧信息通过概率模型或神经网络融入经验贝叶斯框架，既能利用侧信息提升准确性，又无需对数据生成过程做过多假设，从而广泛适用于空间转录组学、协同过滤等多种场景。

## 2. 论文提出的方法论

### 核心思想
- 基于**经验贝叶斯矩阵分解（EBMF）** 框架，将其扩展为**协变量调节的版本**：允许因子的先验分布依赖于侧信息（行/列协变量）。
- 先验分布不再是全局固定的，而是由协变量通过参数化模型（例如逻辑回归、多层感知机）动态生成，且通过经验贝叶斯自动学习参数。

### 关键技术细节
- **模型设定**：数据矩阵 \( Z \approx LF^T \)，假设 \( Z_{ij} \sim N( (LF^T)_{ij}, \tau_{ij}^{-1} ) \)。对每个因子 \( k \)，行因子 \( \ell_{ik} \) 的先验为 \( g_k^{(\ell)}(x_i) \in \mathcal{G}_{\ell,k} \)，列因子 \( f_{jk} \) 的先验为 \( g_k^{(f)}(y_j) \in \mathcal{G}_{f,k} \)，其中 \( x_i, y_j \) 是侧信息。
- **参数化先验家族**：文中主要使用**参数化 spike-and-slab 先验**（如公式 (5)(6)），即混合点质量在0和连续分布（如正态或指数），其混合权重由侧信息通过神经网络或逻辑回归建模。这允许先验只影响稀疏模式（零的位置），而非幅度，从而保持分解的尺度不变性。
- **学习算法**：采用**坐标上升法优化证据下界（ELBO）**。每次迭代中，对每个因子依次执行：
  1. 从当前残差中剥离该因子，计算更新该因子的伪观测值和标准差。
  2. 求解**协变量调节的经验贝叶斯正态均值（cEBNM）** 问题：利用伪观测值和协变量，以最大化边际似然的方式学习先验参数 \( \theta \)。
  3. 根据更新后的先验计算后验均值和二阶矩。
  4. 更新残差矩阵。
- **cEBNM 求解**：cEBNM 是对传统 EBNM 的扩展，允许先验依赖于协变量 \( d_i \)。其关键在于计算形如 (11) 的边际似然并优化参数 \( \theta \)，以及计算后验矩。对于 spike-and-slab 家族可解析计算，否则可用高斯-厄米特求积等数值方法。这使得框架模块化：不同先验家族只需提供对应的 cEBNM 求解器即可。

### 算法流程（文字说明）
- 初始化因子矩估计和残差。
- 重复直至收敛：
  - 更新残差方差（假设同质、列异质或行异质）。
  - 对每个因子 \( k \)：
    - 从总残差中去除该因子的贡献。
    - 对行因子：计算伪观测值和标准差，调用 cEBNM 求解得到先验和后验矩，更新行因子矩。
    - 对列因子同理。
    - 将该因子贡献重新加入残差。
- 返回最终的因子矩和先验。

## 3. 实验设计

### 使用的数据集/场景
1. **模拟数据**：四种场景，各生成100个数据集。
   - **稀疏驱动协变量**：行/列协变量仅影响因子稀疏模式（90%零）。
   - **无信息协变量**：协变量仅为噪声，无真实作用。
   - **平铺聚类**：因子 \( L \) 依赖于2D空间位置（每个点属于三个聚类之一，平铺状），\( F \) 随机生成。
   - **偏移平铺聚类**：与平铺聚类类似，但 \( L \) 的取值模式被故意旋转，使得 cEBMF 的先验家族无法完美恢复（模型误设）。
2. **协同过滤**：MovieLens 100K 数据集（1682部电影 × 943个用户，93%缺失评分）。侧信息为电影类型（19维二进制向量）。
3. **空间转录组学**：人类背外侧前额叶皮层（DLPFC）12个切片数据，每切片约4000个像素（点）×5000个基因。侧信息为2D空间坐标。
4. **可扩展性基准**：模拟平铺聚类数据，变化行数 \( n \) 从 \( 10^3 \) 到 \( 10^6 \)，比较运行时间。

### Benchmark 和对比方法
- **不使用侧信息的方法**：EBMF（R包flashier）、PMD（PMA R包）、SSVD、SVD、VAE（PyTorch实现）。
- **使用侧信息的方法**：MFAI（R包mfair）、Spatial PCA（R包SpatialPCA）、cVAE、NCF（PyTorch实现）、CMF（集体矩阵分解）。
- 注意：在协同过滤实验中，cEBMF和EBMF被配置为产生非负分解（EBNMF、cEBNMF），使用混合指数先验。MFAI无法产生非负分解。

### 评价指标
- 模拟：恢复真实 \( LF^T \) 的**RMSE**。
- 协同过滤：测试集上的预测RMSE（随机保留部分评分）。
- 空间转录组：定性比较因子（或聚类）与专家标注的匹配度（通过可视化饼图/聚类图）。
- 可扩展性：平均运行时间（秒）。

## 4. 资源与算力

- 文中仅在**可扩展性基准**部分提供了算力详情：使用计算机配置为 **32 GB 内存、NVIDIA GeForce RTX 4070 GPU、AMD Ryzen 9 7940HS CPU（8核16线程）**。
- 其他实验（模拟、MovieLens、DLPFC）未明确说明使用的具体GPU/CPU型号、训练时长或节点数。但提到部分计算在**芝加哥大学研究计算中心**的高性能计算集群上完成。
- **注意**：论文主要聚焦算法和实验，算力信息不够完整，例如未给出所有实验的总GPU小时数或训练轮数。

## 5. 实验数量与充分性

- **模拟**：每个场景100个数据集 × 4种噪声水平 → 总计 **400×4=1600** 次模拟（但图2只展示了部分噪声水平的结果）。每个模拟重复多次，结果用箱线图展示，统计充分。
- **协同过滤**：3种训练比例（50%、70%、90%），每个比例10次随机训练-测试划分 → 共30次实验。
- **空间转录组**：12个切片，但对每个切片cEBMF与其他方法均仅展示一个运行结果（未做多次重复）。对比方法包括NMF、EBNMF、MFAI、Spatial PCA、VAE、cVAE、NCF等。
- **可扩展性基准**：每个 \( n \) 值10次模拟求平均运行时间。
- **充分性**：模拟场景覆盖了协变量信息性、模型正确/误设等情况，实验客观公平。但空间转录组部分缺乏多次重复和定量指标（只有定性比较），略显不足。总体上实验数量合理，结论支持充分。

## 6. 论文的主要结论与发现

- cEBMF 在**信息性协变量**情景下（如平铺聚类）显著优于不使用侧信息的方法（EBMF、PMD等），并且优于其他利用侧信息的方法（MFAI、Spatial PCA、cVAE、NCF）。
- 在**无信息协变量**或**模型误设**情景下，cEBMF 与 EBMF 表现相当，不会因加入无用信息而变差，鲁棒性好。
- 在**协同过滤**任务中，cEBNMF 比 EBNMF、MFAI、VAE、cVAE、NCF 均取得更低的预测 RMSE，尤其在低训练比例时优势明显。
- 在**空间转录组学**中，cEBNMF 产生的因子能更好地匹配专家标注的组织区域，且每个因子具有清晰的空间连续性，优于 NMF、EBNMF 以及 Spatial PCA 等。
- **可扩展性**：cEBMF 可处理百万行数据，运行时间远低于 MFAI 和 Spatial PCA。
- 总体结论：cEBMF 是一个通用、灵活、鲁棒的矩阵分解框架，能有效利用侧信息提升结构推断质量。

## 7. 优点

- **通用性**：可接受任意类型的侧信息（图像、文本、图等），只需将其编码为神经网络或概率模型的输入。
- **灵活性**：通过选择不同的先验家族（如 spike-and-slab、非负约束等），cEBMF 可涵盖许多现有方法（PCA、NMF、稀疏因子分析等）作为特例。
- **自动调参**：经验贝叶斯框架自动学习先验中的超参数，无需交叉验证。
- **模块化**：算法将复杂问题分解为顺序的 cEBNM 子问题，每个子问题可独立实现（解析或数值求解），便于扩展。
- **鲁棒性**：在无信息协变量或模型误设时不会显著退化。
- **可扩展性**：能够在百万规模数据上运行，且时间成本远低于同类方法（MFAI、Spatial PCA）。

## 8. 不足与局限

- **实验覆盖**：
  - 空间转录组学的评估主要依赖**定性比较**，缺乏定量指标（如聚类 ARI、因子相关性等），说服力稍弱。
  - 未在更大规模的真实数据集（如百万用户级推荐系统）上测试，仅模拟了可扩展性。
  - 未系统研究不同神经网络架构（MLP、GNN、CNN）对侧信息编码的影响，仅使用了多层感知机。
- **模型假设**：虽然框架灵活，但仍假设噪声为高斯分布，且需通过 ELBO 优化（变分推断），对于非线性、非高斯的复杂数据可能不够充分。
- **计算复杂度**：虽然可扩展，但相较于简单 EBMF，cEBMF 的计算量更大（因为每个因子更新需运行神经网络优化），在非常大规模数据上可能仍需 GPU 加速和大内存。
- **初始化敏感性**：算法使用坐标上升，可能收敛到局部最优，但论文未讨论初始化策略的影响。
- **理论保证**：缺乏对收敛性、统计一致性等方面的理论分析。

（完）
