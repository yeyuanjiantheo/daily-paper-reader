---
title: Non-Asymptotic and Non-Lipschitzian Bounds on Optimal Values in Stochastic Optimization Under Heavy Tails
title_zh: 重尾下随机优化最优值的非渐近与非Lipschitz界
authors: "Jindong Tong, Hongcheng Liu, Johannes O. Royset"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=XAFfOEFJG1"
tags: ["query:qf"]
score: 6.0
evidence: 重尾随机优化的置信界，与尾部风险管理相关
tldr: 现有随机优化置信界常依赖全局Lipschitz常数和轻尾假设，实际应用中重尾分布常见。本文推导出非渐近、非Lipschitz的置信界，适用于凸随机优化问题中重尾分布下的最优值置信区间。通过样本平均逼近和直径风险最小化两种框架实现，为尾部风险管理的理论分析提供新工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-xaffoefjg1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 847, \"height\": 561, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-xaffoefjg1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xaffoefjg1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 825, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xaffoefjg1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 815, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xaffoefjg1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1621, \"height\": 990, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xaffoefjg1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 716, \"height\": 654, \"label\": \"Table\"}]"
motivation: 现有随机优化置信界依赖Lipschitz常数和轻尾假设，在重尾金融数据中适用性受限。
method: 基于样本平均逼近和直径风险最小化，推导非渐近、非Lipschitz的置信界，无需全局光滑性和轻尾条件。
result: 理论证明所提置信界在重尾分布下有效，计算上可行，数值实验验证其鲁棒性。
conclusion: 为重尾风险建模提供了更宽松的置信界工具，可用于VaR、ES等尾部风险的统计推断。
---

## Abstract
This paper focuses on non-asymptotic confidence bounds (CB) for the optimal values of stochastic optimization (SO) problems. Existing approaches often rely on two conditions that may be restrictive: The need for a global Lipschitz constant and the assumption of light-tailed distributions. Beyond either of the conditions, it remains largely unknown whether computable CBs can be constructed. In view of this literature gap, we provide three key findings below: (i) Based on the conventional formulation of sample average approximation (SAA), we derive non-Lipschitzian CBs for convex SP problems under heavy tails. (ii) We explore diametrical risk minimization (DRM)---a recently introduced modification to SAA---and attain non-Lipschitzian CBs for nonconvex SP problems in light-tailed settings. (iii) We extend our analysis of DRM to handle heavy-tailed randomness by utilizing properties in formulations for training over-parameterized classification models.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：现有非渐近置信界（NCB）的构造通常依赖两个严格假设：全局Lipschitz常数已知，以及随机变量的分布具有轻尾（即所有阶矩存在）。然而在实际应用中，许多随机优化（SO）问题面临重尾分布（如金融数据、网络流量）且难以获得准确的Lipschitz常数。作者旨在填补空白：在**不依赖全局Lipschitz常数且允许重尾**的条件下，构造可计算的、非渐近的置信界。
- **核心问题**：如何通过样本平均近似（SAA）或其变体——直径风险最小化（DRM），在凸/非凸、轻尾/重尾场景下给出最优值 \(F^*\) 的置信区间。
- **意义**：为尾部风险管理、统计决策、多臂老虎机等问题提供了更宽松的理论工具，尤其适合高维和重尾数据。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：利用局部矩条件（仅在最优解处或全体解上限制p阶矩）代替全局Lipschitz常数和轻尾假设；通过SAA和DRM两种框架分别处理凸和非凸问题；对非凸重尾场景，借助过参数化模型（零损失）构造有界辅助问题。
- **关键技术细节**：
  - **凸SO重尾场景**（定理4.1）：假设存在p≥2使得在最优解处随机梯度与目标值的p阶矩有界（\(\sigma_g, \sigma_f\)）。通过Marcinkiewicz不等式和凸性导出：
    \[
    \begin{aligned}
    L_{N,\alpha} &= F_N^* - \frac{2.74}{\alpha^{1/p}} \cdot 6^{1/p} \cdot \sigma_f \sqrt{\frac{p}{N}} - \delta \\
    U_{N,\alpha} &= F_N^* + \frac{2.74}{\alpha^{1/p}} \cdot 6^{1/p} \cdot (\sigma_g D_q + \sigma_f) \sqrt{\frac{p}{N}}
    \end{aligned}
    \]
    其中 \(D_q\) 为可行域q-范数直径。界与Lipschitz常数无关。
  - **非凸SO轻尾场景**（定理4.7+引理4.6）：假设f(x,ξ)具有子指数范数\(\sigma_\psi\)。下界由SAA给出（Bernstein不等式），上界通过DRM（4）及\(\epsilon\)-网技术（Sudakov下界）导出：
    \[
    U_{N,\alpha} = F_\gamma^* + 4\sigma_\psi\sqrt{\frac{1}{2N}}\sqrt{\frac{\Delta_{p,q} d^{2/q}}{\gamma^2} + \ln\frac{4}{\alpha}} + \frac{4\sigma_\psi}{N}\left(\frac{\Delta_{p,q} d^{2/q}}{\gamma^2} + \ln\frac{4}{\alpha}\right)
    \]
    其中 \(\Delta_{p,q}\) 与p-范数直径和维度相关（近似线性增长于q），从而依赖维度为\(\ln d\)。
  - **非凸SO重尾场景（过参数化模型）**（定理4.13+假设4.11）：假设非负损失且DRM最优值为0（如二分类正间隔），将原始问题通过截断构造有界辅助问题，利用马尔可夫不等式和Markov链导出：
    \[
    U_{N,\alpha} = \left[F_\gamma^* + 8\ln2\cdot\left(\frac{\Delta_{p,q} d^{2/q}}{\gamma^2} + \ln\frac{4}{\alpha}\right)\left(1+\frac{\sigma'_f}{p-1}\right)N^{-\frac{p-2}{2p}}\right]\cdot \left[1 - 7\ln2\cdot\left(\frac{\Delta_{p,q} d^{2/q}}{\gamma^2} + \ln\frac{4}{\alpha}\right)N^{-1/2}\right]^{-1}
    \]
- **算法流程**：SAA和DRM的求解可使用随机梯度下降（SGD）或次梯度方法；DRM需额外计算邻域内最大经验风险（类似SAM算法）。论文给出伪代码（Algorithm 1）用于计算 \(F_N^*\) 和 \(F_\gamma^*\)。

### 3. 实验设计：使用了哪些数据集/场景，benchmark，对比了哪些方法
- **实验一**：**凸SO**——随机线性规划问题，其中随机变量服从帕累托分布（重尾，p=2.01有效），可行域为单纯形。对比方法：基于Oliveira & Thompson (2023)的基准NCB（B-NCB）。提出的NCB分为两个版本：P-NCB*（使用真实问题量）和P-NCB^E（估计问题量，模拟实际应用）。
- **实验二**：**非凸SO**——训练一个过参数化的两层神经网络，数据生成过程为 \(Y = h(X) + \epsilon\)，其中\(\epsilon\)服从学生t分布（重尾）。DRM参数γ=0.01。对比基准：Oliveira & Thompson (2023)的非凸NCB（B-NCB-NC^E）。提出的方法记为P-NCB-NC^E。
- **评价指标**：经验覆盖概率（ECP）和置信区间长度之比\(r_1\)（凸）、\(r_2\)（非凸）。

### 4. 资源与算力
- **文中未提及GPU型号、数量、训练时长等具体算力信息**。论文仅描述了算法流程（SGD, DRM迭代次数等），但未报告硬件环境。推测实验在CPU工作站或单GPU上完成，算力需求不高；计算量主要体现在多次独立重复（凸实验10,000次重复，非凸实验10次重复）上。

### 5. 实验数量与充分性
- **凸实验**：在不同维度（d=100,500,1000,2000,4000）和样本量（N=5,10,50,100,500,1000）下进行组合，共约30组，并报告了ECP（基于10,000次重复）和长度比。充分。
- **非凸实验**：在维度-样本量组合（d=41,N=300,340,380,420；d=961,N=500,600,700,800；d=1681,N=500,600,700,800）共12组，每组重复10次计算平均长度比。ECP报告显示均达1.0。实验数量适中，但重复次数较少。
- **消融实验**：未提供（如改变p值、α值等）。总体而言，实验覆盖了问题规模和样本量变化，客观性较好，但非凸部分重复次数偏少，且未展示更多随机种子差异。

### 6. 论文的主要结论与发现
- 首次在无Lipschitz常数和允许重尾条件下，给出了凸SO问题的非渐近置信界，且收敛速度仍为\(O(N^{-1/2})\)。
- 首次在非凸SO轻尾情况下给出了非Lipschitzian的置信界，维度依赖可降低至\(\ln d\)。
- 对过参数化模型（零损失假设），进一步扩展到重尾非凸情况，得到可计算的上下界。
- 数值实验表明，所提NCB（尤其是P-NCB*）的置信区间长度显著短于基于Lipschitz和轻尾的基准方法（长度比<0.6甚至<0.1），且覆盖概率仍可靠（接近1）。
- 结论：所提方法在更高维问题中优势更明显，具有良好的可扩展性。

### 7. 优点：方法或实验设计上的亮点
- **理论创新**：显著放宽了现有NCB的假设（无需全局Lipschitz、允许重尾），且首次覆盖凸、非凸、轻尾、重尾的组合。
- **非保守性**：在保持覆盖概率的同时，置信区间更窄，尤其在高维下表现优异。
- **实用性**：给出显式公式，依赖的量（如\(\sigma_f,\sigma_g\)）可在实践中估计。
- **DRM框架的利用**：通过直径风险最小化自然避免Lipschitz常数，且与SAM算法联系紧密，有实用价值。
- **实验设计**：考虑了估计量与真实量的对比（P-NCB^E vs P-NCB*），模拟了实际应用场景。

### 8. 不足与局限
- **理论假设仍有约束**：对于非凸重尾情况，引入了“过参数化模型”和“零损失”假设（假设4.11），限制了应用范围（仅适用于可分数据/正间隔分类问题）。
- **保守性**：所有ECP均接近1.0，高于名义置信水平0.99或0.9，表明置信界可能仍偏保守。
- **非凸实验的重复次数少**：仅重复10次，且ECP均为1.0，缺乏对置信区间波动的统计描述。
- **计算量**：DRM求解需要比SAA多3-5倍时间，论文未讨论大模型下的可扩展性。
- **缺少消融实验**：未分析不同p值、γ半径等超参数对置信界长度和覆盖的影响。

（完）
