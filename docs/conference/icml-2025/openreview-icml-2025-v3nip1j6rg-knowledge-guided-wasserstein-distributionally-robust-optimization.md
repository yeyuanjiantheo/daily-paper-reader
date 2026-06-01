---
title: Knowledge-Guided Wasserstein Distributionally Robust Optimization
title_zh: 知识引导的Wasserstein分布鲁棒优化
authors: "Zitao Wang, Ziyuan Wang, Molei Liu, Nian Si"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=v3niP1j6Rg"
tags: ["query:qf"]
score: 6.0
evidence: 提出知识引导的Wasserstein分布鲁棒优化用于迁移学习，与鲁棒组合优化相关
tldr: 标准Wasserstein分布鲁棒优化在小样本下过于保守。本文提出知识引导的WDRO，利用外部知识缩小不确定集，在迁移学习中提升精度。该方法可应用于金融中带辅助信息的鲁棒投资组合优化。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-v3nip1j6rg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1768, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3nip1j6rg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1592, \"height\": 921, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-v3nip1j6rg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1744, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3nip1j6rg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 848, \"height\": 424, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3nip1j6rg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1475, \"height\": 619, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3nip1j6rg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1602, \"height\": 834, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3nip1j6rg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1626, \"height\": 618, \"label\": \"Table\"}]"
motivation: 标准WDRO在小样本下过于保守，希望利用外部知识减少保守性。
method: 构建知识导向的Wasserstein模糊集，控制沿信息方向的运输成本。
result: 理论和实验表明，KG-WDRO比标准WDRO具有更好的泛化性能。
conclusion: 外部知识可有效改进分布鲁棒优化。
---

## Abstract
Wasserstein Distributionally Robust Optimization (WDRO) is a principled framework for robust estimation under distributional uncertainty. However, its standard formulation can be overly conservative, particularly in small-sample regimes. We propose a novel knowledge-guided WDRO (KG-WDRO) framework for transfer learning, which adaptively incorporates multiple sources of external knowledge to improve generalization accuracy. Our method constructs smaller Wasserstein ambiguity sets by controlling the transportation along directions informed by the source knowledge. This strategy can alleviate perturbations on the predictive projection of the covariates and protect against information loss. Theoretically, we establish the equivalence between our WDRO formulation and the knowledge-guided shrinkage estimation based on collinear similarity, ensuring tractability and geometrizing the feasible set. This also reveals a novel and general interpretation for recent shrinkage-based transfer learning approaches from the perspective of distributional robustness. In addition, our framework can adjust for scaling differences in the regression models between the source and target and accommodates general types of regularization such as lasso and ridge. Extensive simulations demonstrate the superior performance and adaptivity of KG-WDRO in enhancing small-sample transfer learning.

---

## 论文详细总结（自动生成）

# 知识引导的Wasserstein分布鲁棒优化（KG-WDRO）—— 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：Wasserstein分布鲁棒优化（WDRO）是处理分布不确定性的重要框架，但其标准形式在小样本场景下往往过于保守，导致泛化性能不佳。真实应用中常存在外部知识（如源域训练的模型参数）可供迁移学习，但如何将其有效融入WDRO以降低保守性并提升精度，仍是一个开放问题。
- **整体含义**：本文提出知识引导的WDRO（KG-WDRO），通过构造受外部知识约束的Wasserstein模糊集，使模型在保持鲁棒性的同时减少过度保守，尤其适用于小样本迁移学习。该框架统一了多种收缩型迁移学习方法，为它们提供了分布鲁棒性解释。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：在标准WDRO中，用一个Wasserstein球（以经验分布为中心）定义模糊集。KG-WDRO在此基础上，通过修改运输代价函数，施加沿外部知识向量θ方向的惩罚（强传递为无穷大惩罚，弱传递为有限惩罚），从而缩小模糊集并引导解朝向知识方向。
- **关键技术细节**：
  - **知识引导运输代价**：  
    - 强传递：`c_{2,∞} = ∥x - u∥_q^2 + ∞·|y - v| + ∞·|θ^T(x - u)|`（对分类用`c_{1,∞}`）。  
    - 弱传递（仅线性回归p=2）：`c_{2,λ} = ∥x - u∥_2^2 + λ·(θ^T(x - u))^2 + ∞·|y - v|`。  
  - **等价正则化形式**（定理3.3、3.5、3.6）：  
    - 线性回归强传递：`inf_{β, ϑ∈Θ} (√MSE_N(β) + √δ ∥β - ϑ∥_p)^2`。  
    - 线性回归弱传递（p=2）：`inf_β (√MSE_N(β) + √δ ∥β∥_{Ψ_λ})^2`，其中`Ψ_λ = I - (1/(∥θ∥_2^2+λ)) θθ^T`。  
    - 二分类（逻辑损失/合页损失）强传递：`inf_{β, ϑ∈Θ} (1/N∑ℓ(y_i, β^T x_i) + δ∥β - ϑ∥_p)`。  
  - **多源知识**：扩展到多个先验向量张成的线性空间Θ，强传递时要求秩<d，否则退化。  
  - **子系数向量传递**：通过Mahalanobis距离（Λ矩阵）实现部分特征的知识迁移。  

## 3. 实验设计：数据集、场景、benchmark与对比方法
- **合成数据实验**（三个模拟）：  
  - **Simulation 1**：高维稀疏逻辑回归，二分类。目标-源系数对按多元正态生成（相关性ρ可变），样本量N=20/50/80，维度150（50非零+100零）。对比方法：标准WDRO、Trans-GLM (Tian & Feng, 2023)。评估指标：分类准确率。  
  - **Simulation 2**：高维线性回归，协变量相关（相关性0.3）。N=50/70/90，维度100。对比方法：标准WDRO、Trans-Ridge（Li et al., 2021）。评估指标：out-of-sample R²。  
  - **Simulation 3**：多源迁移线性回归。三个源系数θ₁,θ₂,θ₃及其线性组合θ_S，目标β与θ_S相关。N=50/60/70。对比方法：标准WDRO、oracle Trans-Lasso（Li et al., 2021）。评估指标：out-of-sample R²。  
  - 每个配置重复100次，取平均。超参数通过验证集（与训练集等大）选择。
- **真实数据实验**：2020年美国大选县级选举结果预测（二分类任务）。8个目标州，其余州作为源知识。特征为761个标准化预测变量，样本约3100个县。对比方法：标准WDRO和Trans-GLM。评估指标：log-loss。
- **benchmark**：上述对比方法（标准WDRO、Trans-GLM、Trans-Ridge、Trans-Lasso）均为相关领域代表性方法。

## 4. 资源与算力
- **文中未明确提及**：未报告GPU型号、数量、训练时长或总计算资源消耗。仅说明实验重复100次，但未提供硬件配置。这可能因为实验主要基于CPU即可完成（合成数据规模不大）。

## 5. 实验数量与充分性
- **实验数量**：共3组合成实验 + 1组真实数据实验。合成实验覆盖了不同样本量（3~4种）、不同相关性ρ（6个水平）、不同信号强度s（2种）、不同多源组合（2种）等多种组合，总计约72个设置（每个重复100次）。真实数据在8个州评估。  
- **充分性**：合成实验系统性强，控制了关键变量（相关性、样本量、稀疏性、多源结构），对比了多种基线，实验结果以表格和曲线呈现。真实数据实验规模较小（仅一个数据集），但展示了实际可行性。  
- **客观公平**：对比方法使用同一超参数选择流程（网格搜索+验证集），性能评估基于独立测试集。合成实验重复100次降低随机性。未提及统计显著性检验（如t检验），但差异主要靠数值大小判断，结合多次重复，结果较为可信。

## 6. 论文的主要结论与发现
- KG-WDRO在合成和真实数据上均优于标准WDRO（尤其在低样本、低相关性时），有效缓解了WDRO的保守性。  
- 在Simulation 1中，KG-WDRO在小样本（N=20）时分类准确率比Trans-GLM高约2%；在大样本时二者接近。  
- 在Simulation 2中，KG-WDRO（强传递和弱传递）在中低相关性下显著优于Trans-Ridge；在高相关性下三种方法性能相近。  
- 在多源场景（Simulation 3）中，KG-WDRO在学习系数组合不均等时明显优于Trans-Lasso；在等权重组合时仍保持竞争力。  
- 真实数据中，KG-WDRO在5/8个州优于Trans-GLM，总体log-loss降低7.6%。  
- 理论贡献：证明了KG-WDRO等价于基于共线相似性的收缩估计，为多种迁移学习方法提供了分布鲁棒性新视角。

## 7. 优点
- **方法论创新**：首次将外部知识系统性地融入WDRO，通过修改代价函数实现知识引导，兼具可解性和理论保证。  
- **灵活性**：支持连续/二分类、强/弱传递、多源、lasso/ridge型正则化、尺度调整、子系数选择性迁移（Mahalanobis范数）。  
- **实验验证全面**：覆盖多种典型迁移学习难题（高维稀疏、相关协变量、多源），对比了代表性基准方法。  
- **理论深入**：不仅有等价形式证明，还通过Toland对偶性简化了内层最大化问题的求解。

## 8. 不足与局限
- **统计保证缺失**：论文未提供KG-WDRO估计量的收敛速率、置信区域或泛化误差界（仅在结论中提及作为未来工作）。  
- **超参数选择**：δ和λ通过网格搜索+验证集选择，未提出自适应或理论驱动的选择准则，实际应用可能依赖大量调参。  
- **真实数据评估有限**：仅使用一个选举数据集，且特征维度高达761，但目标州样本很少，结果可能受特定数据特性影响，需更多领域验证。  
- **弱传递仅讨论了p=2情况**：对于p≠2的弱传递分析未给出（强传递覆盖了任意p）。  
- **算力报告缺乏**：未说明实验计算资源，不利于复现和性能评估。  
- **未与更现代的迁移学习方法比较**：如基于深度神经网络或Transformer的迁移方法（虽本文聚焦线性模型，但可提及局限性）。  
- **负迁移预防**：框架通过自动符号适应可部分避免负迁移，但文中未深入分析在低相关性时的退化行为（例如当θ与β几乎无关时，模糊集约束可能无效或有害）。

（完）
