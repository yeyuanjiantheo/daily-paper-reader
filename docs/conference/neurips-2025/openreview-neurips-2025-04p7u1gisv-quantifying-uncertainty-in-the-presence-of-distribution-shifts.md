---
title: Quantifying Uncertainty in the Presence of Distribution Shifts
title_zh: 分布漂移存在下的不确定性量化
authors: "Yuli Slavutsky, David Blei"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=04p7u1gIsv"
tags: ["query:qf"]
score: 4.0
evidence: 分布漂移下用自适应先验量化不确定性，可用于样本外评估
tldr: 神经网络在测试协变量分布漂移时给出的不确定性估计不可靠。本文提出一种贝叶斯框架，通过自适应先验（同时基于训练和新协变量）自然增大远离训练分布区域的不确定性，并采用摊销变分推断高效近似后验。该方法可应用于金融时间序列预测中的样本外不确定性评估，帮助识别预测可靠性下降的区域，从而为经济解释提供置信度指标。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-04p7u1gisv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1480, \"height\": 174, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-04p7u1gisv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 507, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-04p7u1gisv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1311, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-04p7u1gisv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1464, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-04p7u1gisv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1222, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-04p7u1gisv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1436, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-04p7u1gisv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1244, \"height\": 300, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-04p7u1gisv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-04p7u1gisv/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1432, \"height\": 728, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-04p7u1gisv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1388, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-04p7u1gisv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1545, \"height\": 638, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-04p7u1gisv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 941, \"height\": 579, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-04p7u1gisv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1591, \"height\": 638, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-04p7u1gisv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1597, \"height\": 382, \"label\": \"Table\"}]"
motivation: 现有关键不确定性估计方法在协变量分布漂移时失效。
method: 构建自适应先验的贝叶斯框架，利用摊销变分推断近似后验。
result: 在合成和真实数据上，该方法在分布漂移下提供了校准的不确定性估计。
conclusion: 为深度学习在非平稳环境中的可信赖性提供了可行方案。
---

## Abstract
Neural networks make accurate predictions but often fail to provide reliable uncertainty estimates, especially when test-time covariates differ from those seen during training, as occurs with selection bias or shifts over time. To address this, we propose a Bayesian framework for uncertainty estimation that explicitly accounts for covariate shifts. Unlike conventional approaches that rely on fixed priors, a key idea of our method is an adaptive prior, conditioned on both training and new covariates. This prior naturally increases uncertainty for inputs that lie far from the training distribution in regions where predictive performance is likely to degrade. To efficiently approximate the resulting posterior predictive distribution, we employ amortized variational inference. Finally, we construct synthetic environments by drawing small bootstrap samples from the training data, simulating a range of plausible covariate shifts using only the original dataset. We evaluate our method on both synthetic and real-world data, demonstrating that it yields substantially improved uncertainty estimates under distribution shift compared to existing approaches.

---

## 论文详细总结（自动生成）

# 论文《Quantifying Uncertainty in the Presence of Distribution Shifts》详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：神经网络在预测中表现准确，但常无法提供可靠的不确定性估计，尤其当测试时协变量分布与训练分布存在漂移（covariate shift）时，现有方法的不确定性估计会严重失效。这在医疗、人脸识别等高风险应用中可能导致有害后果。
- **研究动机**：经典贝叶斯神经网络中，预测不确定性完全来自参数θ的后验不确定性，而新输入x∗的分布信息并未被利用。直觉上，若x∗远离训练协变量，预测应更不确定。现有距离感知方法（如SNGP、DUE、DUL）使用固定度量检测漂移，但并非所有漂移都同等影响预测性能，这些方法无法学习漂移与性能退化之间的关系。
- **整体含义**：本文旨在提出一种显式建模协变量漂移对预测不确定性影响的贝叶斯框架，使不确定性估计能根据测试输入与训练分布的偏离程度自适应调整。

## 2. 论文提出的方法论

### 核心思想
- **自适应先验**：将先验分布p(θ)替换为同时依赖于训练协变量x₁:N和测试协变量x∗的条件先验p(θ|x₁:N, x∗)。该先验通过能量函数定义，使其在x∗远离训练数据时，将先验质量分散到参数空间中那些可能导致不同预测的区域，从而自然增大预测不确定性。
- **摊销变分推断**：使用神经网络hγ将测试协变量x∗映射为变分后验qϕ(θ; x∗)的参数（均值和对角协方差），高效近似后验p(θ|x₁:N, y₁:N, x∗)，从而避免对每个测试点单独计算。
- **合成环境生成**：由于测试时漂移分布未知，通过从训练数据中抽取bootstrap小样本构造多个“合成环境”，每个环境模拟一种可能的协变量漂移。理论证明（命题3.1）表明，只要抽取足够多的合成环境，至少有一个会接近真实测试分布。

### 关键技术细节
- **自适应先验定义**：p(θ|x₁:N, x∗) ∝ exp( E(θ; x₁:N, x∗) )，其中能量函数E = ∫ [∑_i log p(y|xi,θ) + log p(y|x∗,θ)] dy。对于离散Y，积分退化为求和；对于连续Y，使用蒙特卡洛积分。
- **变分目标**：最大化每个测试点的证据下界（ELBO）：L(ϕ; x∗, D) = E_q[log p(y₁:N|x₁:N,θ)] - KL(qϕ(θ; x∗) || p(θ|x₁:N, x∗))。通过重参数化技巧进行随机梯度优化。
- **推理网络结构**：先预训练嵌入网络gξ（最大化似然），然后对训练集嵌入取均值作为聚合表示，与测试嵌入拼接后输入hγ，输出变分参数。
- **跨环境目标**：使用L个合成环境，每个环境有训练子集D_tr^(ℓ)和测试子集D_te^(ℓ)。整体目标为L = Σ_ℓ L^(ℓ) + τ·Var(L^(1),...,L^(L))，其中方差项惩罚环境间性能差异，提升鲁棒性（类似OOD泛化中的REx方法）。

### 算法流程（文字描述）
1. 预训练嵌入网络gξ和预测器fθ。
2. 对每个训练步：
   - 抽取L个合成环境（每个环境含n个训练样本、m个测试样本）。
   - 对每个环境中的每个测试点，计算其与训练聚合嵌入的拼接，通过hγ得到变分参数ϕ。
   - 利用重参数化采样θ，计算ELBO。
   - 更新hγ参数以最大化跨环境目标（含方差惩罚）。
3. 最终预测时，对新的测试点x∗，使用学习好的hγ得到后验近似，从中采样多个θ，计算预测均值与方差。

## 3. 实验设计

- **数据集/场景**：
  - **合成数据**：异方差线性回归（x~U[0,a], x*~U[0,b], a<b）和缺失数据的逻辑回归（训练数据剔除中间区间(t,1-t)）。
  - **真实分类**：Corrupted CIFAR-10（三种腐蚀：defocus blur, glass blur, contrast），Celeb-A（三个shift-target对：Pale Skin→Blond Hair, Heavy Makeup→Male, Gray Hair→Blond Hair）。
  - **真实回归**：三个UCI数据集（Boston, Concrete, Wine），通过K-means聚类（K=2）构造集群分布不均衡的train/test split。
- **Benchmark与对比方法**：对比了三种距离感知方法：SNGP（Liu et al., 2020）、DUE（Van Amersfoort et al., 2021）、DUL（Park and Blei, 2024）。所有方法使用相同的网络骨干（分类使用两层卷积+全连接，回归使用单层或小型全连接）。
- **评估指标**：分类：准确率、平均校准误差（ACE）；回归：RMSE；同时可视化不确定性（标准差带）。

## 4. 资源与算力

- 论文在附录E中明确说明了：
  - 合成数据与UCI实验：2个CPU，每次重复少于7分钟。
  - CIFAR-10与Celeb-A实验：单块A100 GPU，每次重复少于18分钟。
- 未报告GPU数量和总计算时长，但提供了不同方法的运行时间对比表（Table 5），其中VIDS在CIFAR-C上平均2.5分钟/次，在Celeb-A上平均2.4分钟/次，均快于DUE（7.4/4.4分钟）和DUL（4.0/3.3分钟）。

## 5. 实验数量与充分性

- **实验数量**：
  - 合成数据：2个场景（线性和逻辑），每个场景使用N=M=500，10次重复。
  - 真实分类：CIFAR-10-C上3种腐蚀，Celeb-A上3个shift-target对，共6个实验，每个10次重复。
  - 真实回归：3个UCI数据集，每个10次重复。
- **消融/分析**：未做专门的消融实验，但包含了对比方法的完整超参数网格搜索，并报告了均值与标准差。
- **充分性与公平性**：
  - 所有方法使用相同的骨干网络，超参数通过单独的验证轮次（grid search）选择，并丢弃。
  - 实验覆盖了不同数据类型（合成、图像、表格）、不同漂移类型（腐蚀、属性偏置、聚类偏置），较全面。
  - 但未进行大规模或真实世界应用场景（如医学影像）的验证，也缺乏对更大模型的测试（如ResNet-50等）。
- **结论**：实验比较充分、客观，但多样性仍有限（分类仅用CIFAR和Celeb-A两个数据集，回归仅三个UCI小数据集）。

## 6. 论文的主要结论与发现

- VIDS在大多数任务上取得了最高的分类准确率（6个分类实验全部最优）和最低/相当的回归RMSE（3个回归实验全部最优或并列）。
- VIDS的不确定性估计更符合预期：在远离训练数据的区域（如异方差回归的高x处、分类的缺失中间区域）表现出更高的方差，而对比方法（尤其SNGP、DUE）常出现低估或高估。
- 自适应先验比固定距离度量更有效：VIDS能够从数据中学习哪些漂移会影响性能，而不仅依赖输入空间的距离。
- 合成环境策略（bootstrap抽样+跨环境方差惩罚）使模型在未见漂移下仍能保持良好校准。

## 7. 优点

- **方法创新**：将自适应先验与摊销变分推断结合，首次显式地将协变量漂移信息融入贝叶斯神经网络的先验，而不是仅仅依赖参数后验。
- **理论支撑**：提供了合成环境逼近测试分布的理论保证（命题3.1及附录B的形式化证明）。
- **计算高效**：推理网络仅在最后一层（预测层）进行变分推断，并预训练特征提取器，因此在大模型场景下比全文贝叶斯方法或集成方法更高效。
- **无需真实测试数据**：仅利用训练数据生成合成环境即可训练，适用于只有单一训练集的实际场景。
- **结果一致优**：在所有6个分类和3个回归实验中准确率或RMSE领先，且不确定性校准更好（可视化及ACE指标）。

## 8. 不足与局限

- **实验规模有限**：图像分类仅使用了小型CNN，未在大型模型（如ResNet、ViT）或更大数据集（如ImageNet）上验证。回归数据集均为UCI小数据，结果可能不能推广到复杂高维问题。
- **缺乏消融研究**：未单独分析自适应先验、合成环境数目、方差惩罚系数等各组件的贡献。
- **假设限制**：自适应先验的能量函数需要在整个Y空间上积分，对于高维连续输出（如图像生成）计算代价高；当前仅对离散或低维连续可行；对于高维输出，文中使用均匀网格蒙特卡洛，精度和效率未讨论。
- **合成环境的理论假设**：命题3.1要求支撑包含关系supp(p*)⊆supp(p)，当测试集出现训练集未见过的新类别/新区域时，理论保证会减弱（附录中提及可通过丢弃未覆盖bin和重归一化缓解，但实际效果未验证）。
- **基线对比不足**：未与经典的深度集成（Deep Ensemble）或MC Dropout等非距离感知的贝叶斯方法对比，也未与最新的OOD检测方法（如ODIN、Mahalanobis等）比较。
- **评估指标单一**：主要报告准确率、RMSE和可视化不确定性，缺乏可靠性图、期望校准误差（ECE）、负对数似然（NLL）等标准不确定性评估指标。
- **可重复性细节**：超参数通过一次单独实验确定并丢弃，但未说明该次实验是否随机或多次平均，存在一定过拟合风险。

（完）
