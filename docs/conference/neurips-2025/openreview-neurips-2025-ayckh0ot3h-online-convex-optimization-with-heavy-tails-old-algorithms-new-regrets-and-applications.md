---
title: "Online Convex Optimization with Heavy Tails: Old Algorithms, New Regrets, and Applications"
title_zh: 重尾下的在线凸优化：旧算法、新遗憾和应用
authors: Zijian Liu
date: 2025-05-12
pdf: "https://openreview.net/pdf?id=AYcKh0oT3h"
tags: ["query:qf"]
score: 7.0
evidence: 重尾梯度下的在线凸优化，可用于尾部风险管理
tldr: 在线凸优化中，当梯度仅有有限p阶矩（重尾）时，经典算法的性能未知。本文证明在线梯度下降等算法在重尾设置下仍能达到最优遗憾界，无需修改算法。该结果为金融中重尾数据下的在线学习提供了理论保障，可用于尾部风险对冲等场景。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
motivation: 重尾梯度下经典在线凸优化算法的误差界未知。
method: 分析在线梯度下降等算法在重尾假设下的遗憾界，证明最优性。
result: 获得了参数最优的遗憾界，且无需修改算法。
conclusion: 为重尾数据下的在线学习提供了理论基础，可应用于金融风险管理。
---

## Abstract
In Online Convex Optimization (OCO), when the stochastic gradient has a finite variance, many algorithms provably work and guarantee a sublinear regret. However, limited results are known if the gradient estimate has a heavy tail, i.e., the stochastic gradient only admits a finite $\mathsf{p}$-th central moment for some $\mathsf{p}\in\left(1,2\right]$. Motivated by it, this work examines different old algorithms for OCO (e.g., Online Gradient Descent) in the more challenging heavy-tailed setting. Under the standard bounded domain assumption, we establish new regrets for these classical methods without any algorithmic modification. Remarkably, these regret bounds are fully optimal in all parameters (can be achieved even without knowing $\mathsf{p}$), suggesting that OCO with heavy tails can be solved effectively without any extra operation (e.g., gradient clipping). Our new results have several applications. A particularly interesting one is the first provable convergence result for nonsmooth nonconvex optimization under heavy-tailed noise without gradient clipping.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在线凸优化（OCO）中，当随机梯度仅服从重尾分布（即有限p阶矩，p∈(1,2]）时，传统算法（如在线梯度下降OGD、对偶平均DA、AdaGrad）的理论性能尚不明确。此前唯一相关工作[47]需要梯度裁剪等复杂修改，无法解释实践中未加修改的算法为何仍有效。
- **研究动机**：弥合理论分析与实际表现之间的鸿沟，验证“旧算法”在重尾噪声下能否无需任何修改即可达到最优遗憾界。
- **整体含义**：论文证明，在有界域的标准假设下，OGD、DA、AdaGrad 依旧能取得参数最优的期望遗憾界（GD√T + σDT^{1/p}），且AdaGrad无需知道任何问题参数。这一发现为重尾数据下的在线学习提供了扎实的理论基础，并首次为无梯度裁剪的非光滑非凸优化提供了收敛保证。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：利用可行域的有界性（直径D），通过更精细的分析技术（如Young不等式）将噪声项ϵ_t的p阶矩正确引入，避免因二阶矩发散导致证明失效。
- **关键技术与细节**：
  - **对OGD**：传统分析中使用不等式⟨g_t, x_t - x⟩ ≤ (‖x_t - x‖² - ‖x_{t+1} - x‖²)/(2η_t) + (η_t/2)‖g_t‖²，但在重尾下失效。作者引入“较少人知的分析”：⟨g_t, x_t - x⟩ ≤ (‖x_t - x‖² - ‖x_{t+1} - x‖²)/(2η_t) + ⟨g_t, x_t - x_{t+1}⟩ - ‖x_t - x_{t+1}‖²/(2η_t)。然后利用三角不等式和Young不等式处理⟨g_t, x_t - x_{t+1}⟩项，得到含‖ϵ_t‖^p的表达式，从而可以取期望。
  - **对DA**：类似思路，将DA的等效写法与上述技巧结合，得到相同形式的遗憾界。
  - **对AdaGrad**：利用其路径-wise遗憾上界∑⟨g_t, x_t - x⟩ ≤ (D²/(2η) + η)√(∑‖g_t‖²)，再通过范数不等式和Hölder不等式直接导出期望遗憾。
  - **步长设置**：OGD/DA采用η_t = D/(G√t) ∧ D/(σ t^{1/p})（需知参数）；AdaGrad采用η_t = η/√(∑_{s=1}^t ‖g_s‖²)，η = D/√2（无需参数）。
- **算法流程**（文字说明）：
  - OGD：x_{t+1} = Π_X(x_t - η_t g_t)
  - DA：x_{t+1} = Π_X(x_1 - η_t ∑_{s=1}^t g_s)
  - AdaGrad：x_{t+1} = Π_X(x_t - (η/√(V_t)) g_t)，其中V_t = ∑_{s=1}^t ‖g_s‖²
- **应用转化**：通过在线到批次转换（凸优化）和在线到非凸转换O2NC框架，得到相应的随机优化收敛速率。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **实验设计**：本文为纯理论工作，未进行任何实验验证。

### 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。若未明确说明，也请指出这一点。

- **未明确说明**：论文无实验部分，故未提及任何计算资源或算力需求。

### 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平。

- **无实验**：不适用。论文仅提供理论证明，实验结果未涉及。

### 6. 论文的主要结论与发现

- **主要结论**：
  1. 在有界域假设下，OGD、DA、AdaGrad 在重尾梯度下均可达到最优期望遗憾界 O(GD√T + σDT^{1/p})，且无需任何算法修改（如梯度裁剪）。
  2. 对于强凸情形，OGD 可获得 O(G² log T/μ + σ^p G^{2-p} T^{2-p}/μ) 的遗憾界。
  3. 应用于非光滑凸优化：首次给出无梯度裁剪的期望收敛速率（平均迭代和最后迭代均最优）。
  4. 应用于非光滑非凸优化：首次证明无需梯度裁剪时 O2NC 框架的收敛性，样本复杂度为 O(G²δ^{-1}ε^{-3} + σ^{p/(p-1)} δ^{-1}ε^{-(2p-1)/(p-1)})。
  5. AdaGrad 的性能无需知道 G、σ、p 等参数，具有良好的自适应性。

### 7. 优点：方法或实验设计上有哪些亮点

- **理论贡献显著**：填补了重尾OCO中经典算法理论分析的空白，证明了已有简单算法的最优性。
- **分析简洁精巧**：通过改进的基本不等式（如Young不等式替代AM-GM）巧妙处理重尾噪声项，无需复杂修改。
- **参数最优**：遗憾界在 T、G、σ、p 上均达到下界匹配，且在确定性情形自动退化为 O(√T)。
- **自适应能力**：AdaGrad 可在完全不知道问题参数的情况下达到最优界，极具实用价值。
- **应用广泛**：将OCO结果转化为随机优化（凸和非凸）的收敛性，首次去除了梯度裁剪的必要性。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **理论假设限制**：关键依赖“有界域”假设（直径D已知），若域无界或直径未知，结论不成立。这是论文明确指出的主要局限。
- **强凸情形可能非最优**：对于p∈(1,2)，强凸情形下的遗憾界 O(T^{2-p}) 可能未达到下界，作者猜测存在更好的结果。
- **仅考虑期望遗憾**：未分析高概率遗憾界（high-probability bound），而实际应用中高概率保证更为稳健。
- **缺乏实验验证**：纯理论推导，未提供任何数值实验或仿真来实证理论结果的有效性，与[47]的实验中观察到的现象呼应不足。
- **应用场景局限**：非光滑非凸优化部分，O2NC框架需要重置步长、且域半径δ/T的设置依赖于已知时间T，实际部署时需谨慎。

（完）
