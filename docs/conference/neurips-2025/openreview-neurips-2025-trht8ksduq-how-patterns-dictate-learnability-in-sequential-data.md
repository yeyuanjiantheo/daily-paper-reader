---
title: How Patterns Dictate Learnability in Sequential Data
title_zh: 模式如何决定序列数据的可学习性
authors: "Mario Morawski, Anaïs Després, Remi Rehm"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=TRHT8ksdUQ"
tags: ["query:qf"]
score: 4.0
evidence: 序列数据模式分析框架，提及金融时间序列
tldr: 序列数据的可学习性依赖于潜在模式。本文提出基于预测信息的通用框架，量化过去与未来之间的互信息，指导回归阶数和特征选择。以金融时间序列为例，该工作为时间序列建模中的数据模式识别提供了理论基础，有助于改进金融预测模型。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-trht8ksduq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 638, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-trht8ksduq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1150, \"height\": 754, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-trht8ksduq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 641, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-trht8ksduq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1450, \"height\": 639, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-trht8ksduq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1402, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-trht8ksduq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 479, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-trht8ksduq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1005, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-trht8ksduq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 930, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-trht8ksduq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1447, \"height\": 642, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-trht8ksduq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 635, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-trht8ksduq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 634, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-trht8ksduq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 634, \"label\": \"Table\"}]"
motivation: 序列数据中的模式难以识别，导致模型设定错误和泛化误差增加。
method: 基于预测信息（过去与未来的互信息）构建框架，用于模式分析和特征选择。
result: 在合成和真实序列数据上展示框架的有效性，能提升预测性能。
conclusion: 量化数据模式的可学习性是提高序列预测模型鲁棒性的关键。
---

## Abstract
Sequential data—ranging from financial time series to natural language—has driven the growing adoption of autoregressive models. However, these algorithms rely on the presence of underlying patterns in the data, and their identification often depends heavily on human expertise. Misinterpreting these patterns can lead to model misspecification, resulting in increased generalization error and degraded performance. The recently proposed $\texttt{evolving pattern (EvoRate)}$ metric addresses this by using the mutual information between the next data point and its past to guide regression order estimation and feature selection. Building on this idea, we introduce a general framework based on predictive information—the mutual information between the past and the future, $\mathbf{I}(X_{\text{past}}; X_{\text{future}})$. This quantity naturally defines an information-theoretic learning curve, which quantifies the amount of predictive information available as the observation window grows. Using this formalism, we show that the presence or absence of temporal patterns fundamentally constrains the learnability of sequential models: even an optimal predictor cannot outperform the intrinsic information limit imposed by the data. We validate our framework through experiments on synthetic data, demonstrating its ability to assess model adequacy, quantify the inherent complexity of a dataset, and reveal interpretable structure in sequential data.

---

## 论文详细总结（自动生成）

# 论文《How Patterns Dictate Learnability in Sequential Data》中文总结

## 1. 核心问题与研究动机
- **研究背景**：序列数据（金融时间序列、自然语言等）中广泛采用自回归模型，但这些模型的性能高度依赖数据中是否存在可识别的模式。然而，模式识别通常依赖人工专家经验，错误识别会导致模型设定偏误（model misspecification），增加泛化误差。
- **核心问题**：
  - (i) 对于序列数据，预测模型能达到的最小风险（minimal achievable risk）是什么？
  - (ii) 当模型表现不佳时，如何判断是因为模型能力不足，还是数据本身固有不可预测性？
- **整体含义**：模式的存在与否从根本上决定了序列模型的可学习性：即使是最优预测器也无法超越数据内在的信息限制。本文通过信息论框架量化这一限制，为模型诊断和选择提供理论基础。

## 2. 方法论
### 核心思想
- 基于 **预测信息（Predictive Information）**：过去与未来之间的互信息 \(I(X_{\text{past}}; X_{\text{future}})\)，将其作为刻画时间序列模式强度的核心量。
- 定义 **通用学习曲线** \(\Lambda(k) = \ell(k) - \ell_0\)，其中 \(\ell(k)\) 是阶数为 \(k\) 的条件熵率，\(\ell_0\) 是极限熵率。\(\Lambda(k)\) 衡量增加额外观测长度带来的不确定性降低，量化了数据中可被提取的预测信息。

### 关键技术细节
- **预测信息定义**：\[I_{\text{pred}}(k, k') = I(X_{t-k+1}^t; X_{t+1}^{t+k'})\]
- **与学习曲线的联系**：\(\Lambda(k) = \lim_{k'\to\infty} [I_{\text{pred}}(k+1, k') - I_{\text{pred}}(k, k')]\)（Proposition 4.1）。
- **最小风险上界**：对任意阶数 \(k\) 和模型 \(Q \in \mathcal{H}_k\)，有  
  \[R_\infty(Q^*) \le \hat{R}^k(Q) - \Lambda(k) + 2\hat{\mathfrak{R}}_n(\mathcal{F}_k) + 3\sqrt{\frac{\ln(1/\delta)}{n}}\]  
  其中 \(R_\infty(Q^*)\) 是最优预测风险，\(\hat{R}^k(Q)\) 是经验风险，\(\hat{\mathfrak{R}}_n\) 是经验 Rademacher 复杂度。
- **参数模型渐近行为**：对于参数维度为 \(p\) 的过程，\(I_{\text{pred}} \sim \frac{p}{2}\ln k + \text{常数}\)，从而 \(\Lambda(k) \sim \frac{p}{2k}\)。
- **马尔可夫过程**：若过程为 \(m\) 阶马尔可夫，则当 \(k \ge m\) 时 \(\Lambda(k)=0\)，学习曲线可识别真正马尔可夫阶数。
- **实用估计器**：通过从训练好的模型集合（如不同回归阶数的 LSTM/MLP）中计算 \(\min_k\{\hat{R}^k(Q_k) - \Lambda(k)\}\) 来估计最小可达风险。

## 3. 实验设计
### 数据集与场景
1. **高斯过程（合成）**：使用多种核函数（AR, Matern 3/2, Matern 5/2, Squared Exponential, Periodic, Rational Quadratic, Locally Periodic），生成不同维度的序列，用于验证预测信息估计的准确性。
2. **自回归过程（AR(p)）**：模拟三维向量自回归过程，阶数 \(p=5\) 和 \(p=10\)，用于验证学习曲线 \(\Lambda(k)\) 能否正确识别真实阶数。
3. **伊辛自旋序列（Ising Spin Sequences）**：生成块状随机马尔可夫链（二进制变量），块大小 \(M\) 分别取 10,000、100,000、1,000,000、10,000,000，训练 MLP 和 LSTM 预测下一步，用于评估最小可达风险估计和模型诊断。

### Benchmark 与对比方法
- 对比了多种互信息估计器：SMILE, NWJ, InfoNCE, DV, TUBA（基于神经网络的 variational estimators）。
- 与 **EvoRate** 指标进行比较（表1–2），EvoRate 是已有基于互信息的模式量化方法。
- 模型对比：LSTM 和 MLP 两种神经网络架构。

## 4. 资源与算力
- **计算平台**：14 核 CPU、20 核集成 GPU、24 GB 统一内存、1 TB SSD（附录 D）。
- **算法复杂度**：估计 \(I_{\text{pred}}\) 的每次迭代计算成本为 \(O(B^2 d)\)，其中 \(B\) 为批大小，\(d\) 为表示维度。估计学习曲线 \(\hat{\Lambda}(k)\) 的总复杂度为 \(O(n B^2 d)\)（\(n\) 为最大阶数）。训练模型 \(\mathcal{Q}\) 的成本未具体量化，但包含在内。
- **未明确说明 GPU 型号**（可能使用 Apple Silicon 集成 GPU），未给出精确训练时长。

## 5. 实验数量与充分性
- **实验组数**：三个主要实验场景，每个场景包含多种参数变化（如不同核函数、维度、阶数、块大小），共生成若干张图表（图1–4，表1–8）。
- **充分性评价**：
  - **充分**：覆盖了理论验证（AR 阶数识别、参数模型渐近行为）和应用诊断（Ising 序列中模型 vs 数据限制）。
  - **客观性**：合成数据使用已知分布，能计算真实值（如 \(I_{\text{pred}}\) 解析解、\(\Lambda(k)\) 理论值），对比了多种估计器，并报告了误差棒。
  - **公平性**：在 Ising 实验中，两种模型（LSTM/MLP）使用相同训练配置，对比了 EvoRate 和本文估计量。
  - **局限性**：缺乏真实世界大规模序列数据集（如 NLP、金融）的验证，作者在附录 F 中承认这一不足。

## 6. 主要结论与发现
- 预测信息 \(I_{\text{pred}}\) 和通用学习曲线 \(\Lambda(k)\) 能有效刻画时间序列中的模式强度，并给出最小可实现风险的上界。
- \(\Lambda(k)\) 在马尔可夫阶数处显著下降（几乎为零），可准确识别模型所需的最小观察长度。
- 在参数模型下，\(\Lambda(k) \sim p/(2k)\)，可估计参数空间维度 \(p\)，且与理论一致（如 Ising 实验中估计维度接近真实值 1）。
- 最小风险估计 \(\hat{R}_\infty(Q^*)\) 与模型实际损失比较，能诊断模型是否已充分捕获数据中的预测信息：当两者接近时，提升模型能力无益；差距大时表明模型欠拟合。
- EvoRate 仅指示模式存在，而本文框架提供定量的风险目标，更具操作性。

## 7. 优点
- **理论创新**：建立了序列数据模式（通过预测信息）与可学习性（最小可达风险）之间的严格信息论联系。
- **实用价值**：提出了无需知道真实分布即可估算最小风险的实用方法，可在线评估模型充分性。
- **模型无关性**：学习曲线 \(\Lambda(k)\) 本身不依赖特定模型类，仅反映数据固有结构；而最小风险估计虽依赖模型类，但实验显示对不同架构（LSTM/MLP）结果一致。
- **解释性**：通过 \(\Lambda(k)\) 的消失可识别马尔可夫阶数，通过渐近行为可推断参数维度。
- **实验设计严谨**：使用已知解析解的合成数据进行验证，误差棒报告完整。

## 8. 不足与局限
- **预测信息估计困难**：在实践中有偏且不稳定，尤其在高维或弱依赖场景（如附录 C.1 中当 \(k\) 远大于真实阶数时 \(\Lambda(k)\) 出现负值），可能导致下游风险估计失真。
- **模型依赖性**：最小风险估计 \(\hat{R}_\infty(Q^*)\) 依赖于具体模型类 \(\mathcal{H}_k\)，可能无法公平比较不同容量或结构的模型。作者认为其目的正是诊断特定模型，但依然存在局限。
- **实验覆盖不完整**：仅在合成数据上验证，缺乏真实大规模时间序列（如 Exchange 数据集）的评估，实际应用效果未知。
- **未与经典方法（如 AIC/BIC）系统对比**：在阶数选择方面，未与 AIC、BIC 等标准准则对比，仅与 EvoRate 对比。
- **代码未完全公开**：虽提供 GitHub 链接，但分析中未详细说明可复现性细节（如随机种子、超参数搜索等）。
- **计算成本未量化**：虽然给出了复杂度，但未记录实际训练时间或 GPU 小时数，不利于复现。

（完）
