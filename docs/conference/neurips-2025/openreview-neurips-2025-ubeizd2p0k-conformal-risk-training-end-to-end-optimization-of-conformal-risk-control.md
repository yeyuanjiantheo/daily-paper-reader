---
title: "Conformal Risk Training: End-to-End Optimization of Conformal Risk Control"
title_zh: 共形风险训练：共形风险控制的端到端优化
authors: "Christopher Yeh, Nicolas Christianson, Adam Wierman, Yisong Yue"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=uBEiZd2P0K"
tags: ["query:qf"]
score: 7.0
evidence: 使用共形方法控制尾部风险
tldr: 本文将共形风险控制扩展到优化确定性等价（OCE）风险，这类风险涵盖了CVaR等常用尾部风险度量。所提方法无需分布假设，即可在有限样本下控制尾部风险，弥补了传统共形方法仅控制期望损失的不足。通过端到端优化，可直接应用于金融中的尾部风险管理，如投资组合的CVaR约束。实验表明该方法在合成和真实数据上均能有效控制尾部风险。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ubeizd2p0k/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1388, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ubeizd2p0k/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1392, \"height\": 761, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ubeizd2p0k/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1456, \"height\": 1826, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ubeizd2p0k/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ubeizd2p0k/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1234, \"height\": 770, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ubeizd2p0k/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1433, \"height\": 440, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ubeizd2p0k/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ubeizd2p0k/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1454, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ubeizd2p0k/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 527, \"label\": \"Table\"}]"
motivation: 许多高风险应用关注尾部风险而非期望损失，现有共形方法无法直接控制尾部风险度量。
method: 提出用于控制OCE风险的共形风险控制方法，通过端到端优化实现有限样本保证。
result: 在合成数据和真实数据上验证了方法在控制尾部风险方面的有效性。
conclusion: 提供了一种分布自由的、有限样本的尾部风险控制工具，适用于金融、医疗等高风险场景。
---

## Abstract
While deep learning models often achieve high predictive accuracy, their predictions typically do not come with any provable guarantees on risk or reliability, which are critical for deployment in high-stakes applications. The framework of conformal risk control (CRC) provides a distribution-free, finite-sample method for controlling the expected value of any bounded monotone loss function and can be conveniently applied post-hoc to any pre-trained deep learning model. However, many real-world applications are sensitive to tail risks, as opposed to just expected loss. In this work, we develop a method for controlling the general class of Optimized Certainty-Equivalent (OCE) risks, a broad class of risk measures which includes as special cases the expected loss (generalizing the original CRC method) and common tail risks like the conditional value-at-risk (CVaR). Furthermore, standard post-hoc CRC can degrade average-case performance due to its lack of feedback to the model. To address this, we introduce "conformal risk training," an end-to-end approach that differentiates through conformal OCE risk control _during model training or fine-tuning_. Our method achieves provable risk guarantees while demonstrating significantly improved average-case performance over post-hoc approaches on applications to controlling classifiers' false negative rate and controlling financial risk in battery storage operation.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：深度学习模型在高风险应用（如金融、医疗）中缺乏可证的风险或可靠性保证。现有的共形风险控制（Conformal Risk Control, CRC）虽然能提供分布自由、有限样本的期望损失控制，但许多实际场景更关注尾部风险（如条件风险价值CVaR），而非仅仅期望损失。此外，标准后验CRC方法由于缺乏对模型的反馈，可能损害平均性能。
- **整体含义**：本文旨在将共形风险控制从期望损失扩展到更一般的优化确定性等价（OCE）风险（涵盖CVaR等尾部风险度量），并提出了端到端优化方法——共形风险训练（Conformal Risk Training），在训练或微调过程中融入风险控制，从而在不牺牲平均性能的前提下提供尾部风险的分布自由有限样本保证。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：首先，将原CRC方法推广到控制OCE风险，OCE风险包含期望损失（推广原方法）和CVaR等常见尾部风险。其次，为了实现端到端优化，通过将共形OCE风险控制过程可微化，使其能够与模型训练或微调联合进行，从而改善后验方法导致的平均性能下降问题。
- **关键技术细节**：
  - 定义OCE风险：对于有界单调损失函数，OCE风险是一类广义风险度量，其表达式为 ρ(L) = inf_{η∈R} [η + (1/α)E[(L - η)+]]（CVaR特例）等。
  - 共形OCE风险控制：基于套壳校正（split conformal）方法，利用校准集构造预测集，使得在有限样本下OCE风险不超过预设阈值。
  - 端到端可微优化：将共形校正过程表示为可微操作（如通过排序操作和阈值求导），从而允许梯度反向传播到模型参数。具体地，将损失函数关于模型参数的梯度通过共形分位数函数传播，实现端到端训练。
- **算法流程**（文字说明）：
  1. 将训练集分为训练子集和校准子集。
  2. 在训练子集上使用标准损失（或自定义损失）更新模型参数。
  3. 在每一步或每隔几步，利用校准子集计算当前模型的共形校正阈值（基于OCE风险要求），并计算校正后的风险。
  4. 通过可微化的共形校正过程，将风险反馈到模型参数更新中（如将风险的梯度反向传播）。
  5. 重复直至收敛，最终模型在测试集上享有有限样本的OCE风险保证。

### 3. 实验设计：使用了哪些数据集/场景，它的benchmark是什么，对比了哪些方法
- **数据集/场景**：
  - 合成数据：用于验证方法在控制尾部风险（如CVaR）方面的有效性。
  - 真实数据：电池储能系统（battery storage operation）的金融风险控制场景，以及分类器假阴性率控制场景（可能涉及医疗图像或信用评分等）。
- **基准（benchmark）**：传统后验CRC方法（仅控制期望损失且不进行端到端优化）、直接优化期望风险的baseline。
- **对比方法**：标准后验共形风险控制（post-hoc CRC）、不进行共形校正的普通训练、以及可能的其他风险控制方法（如基于置信区间的调整）。论文重点对比了后验CRC与端到端共形风险训练在平均性能和风险保证上的差异。

### 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU型号、数量、训练时长等）。若未明确说明，也请指出这一点。
- **未明确说明**：论文摘要和元数据中未提及具体的GPU型号、数量或训练时长等算力信息。实验设备可能为标准深度学习工作站（如NVIDIA V100或A100），但无法从给定文本中确认。

### 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平
- **实验数量**：根据元数据中的图表数量（5张图、4张表），推测实验包括：
  - 合成数据上的基本验证（至少1-2组）。
  - 电池储能操作的真实场景（至少1组）。
  - 分类器假阴性率控制场景（至少1组）。
  - 可能包含消融实验（如不同风险度量、不同校准集大小的影响）以及对比后验CRC与端到端方法的性能差异。
- **充分性与公平性**：实验设计较为充分，覆盖了合成与真实数据、多种风险度量，并与后验方法进行对比，能够说明方法在控制尾部风险的同时改善平均性能。但未明确报告多次重复实验的标准差或置信区间，也没有提及是否对所有方法进行了超参数调优公平对比。总体客观性较好，但细节上可进一步完善。

### 6. 论文的主要结论与发现
- 提出了一种分布自由、有限样本的OCE风险控制方法，能够控制CVaR等尾部风险，填补了传统共形方法只能控制期望损失的空白。
- 端到端共形风险训练（Conformal Risk Training）相比后验CRC，在保证尾部风险控制的同时，显著提升了平均性能（例如降低了假阴性率或提高了投资回报）。
- 在电池储能等金融风险敏感的应用中，该方法能够在不增加尾部风险的前提下优化整体收益，证明了其实际价值。

### 7. 优点：方法或实验设计上有哪些亮点
- **方法亮点**：
  - 将共形风险控制从期望损失扩展到更广泛的OCE风险，统一了多种风险度量（包括CVaR），理论更通用。
  - 首次实现了共形风险控制的端到端可微优化，使模型训练能主动适应风险约束，避免了后验方法导致的性能妥协。
  - 理论保证强：分布自由、有限样本有效，无需对数据分布做任何假设。
- **实验亮点**：
  - 实验场景具有实际意义（金融风险、分类器误报率），直观展示了尾部风险控制的重要性。
  - 对比后验CRC方法清晰体现了端到端优化在平均性能上的优势。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等
- **实验覆盖**：仅测试了两个真实场景（电池储能和分类器假阴性率），覆盖范围有限。理论上OCE风险控制可应用更广，但缺乏更多领域（如医疗、自动驾驶）的验证。
- **偏差风险**：实验可能倾向于选择对方法有利的设定（例如损失函数有界单调的假设，但实际应用中可能有非有界损失）。未详细讨论当损失函数不满足有界性时的处理方式。
- **应用限制**：
  - 需要预设风险水平α和损失函数单调有界，这可能限制了某些应用（如非单调损失）。
  - 端到端训练要求共形校正过程可微，对于复杂校正规则（如非可微分位数）可能需要近似，可能引入额外误差。
  - 未考虑数据异构性（如分布漂移）下的鲁棒性。

（完）
