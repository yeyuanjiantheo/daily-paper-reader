---
title: "Uncertainty-aware breeding decisions: MCMC-based optimum contribution selection increases breeding decision robustness"
title_zh: 考虑不确定性的育种决策：基于 MCMC 的最优贡献选择提高育种决策的稳健性
authors: "Ahlinder, J., Waldmann, P."
date: 2026-06-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.15.711440v2.full.pdf"
tags: ["query:qf"]
score: 8.0
evidence: 运用金融组合理论中的条件风险价值(CVaR)管理育种决策中的尾部风险
tldr: "传统最优贡献选择依赖育种值点估计，忽略不确定性，导致遗传增益高估和选择不稳定。本研究提出CVaR-OCS方法，将育种值后验分布通过条件风险价值纳入优化，同时最大化期望增益并防范尾部风险。在模拟数据和挪威云杉育种中，CVaR-OCS消除了16.7%的增益高估，提高尾部安全性6.60%并扩大选择基础，仅牺牲微小增益。该方法为育种提供原则性不确定性感知决策工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有OCS依赖点估计忽略EBV不确定性，导致遗传增益高估和选择个体不稳定，亟需不确定性感知方法。
method: 提出CVaR-OCS，通过条件风险价值将EBV后验分布直接纳入OCS优化，实现期望增益与尾部风险的同时优化。
result: "模拟数据消除16.7%增益高估并降低方差，挪威云杉提高尾部安全6.60%、扩大选择基础个体数从145到159，仅牺牲0.70%增益。"
conclusion: CVaR-OCS为育种提供原则性、高效的不确定性感知选择工具，多世代遗传影响需进一步研究。
---

## 摘要
最优贡献选择（OCS）通过优化亲本对下一代的贡献来平衡遗传增益与近交，但目前的方法依赖于育种值的点估计，丢弃了遗传评估中固有的不确定性。我们引入了 CVaR-OCS，这是一种新颖的公式，通过条件风险价值（CVaR）（一种来自金融投资组合理论的一致性风险度量）将估计育种值（EBV）的完整后验分布直接纳入 OCS 目标，允许单次优化同时最大化预期遗传增益并防范由 EBV 不确定性导致的最坏情况结果。我们在一个具有已知真实育种值的模拟多世代基因组选择数据集（QTL-MAS 2010；n = 900 个候选个体）上，以及在挪威云杉（Picea abies，n = 5525）的林木育种子代试验中评估了 CVaR-OCS。在模拟数据集上，MAP-OCS 由于 EBV 不确定性高估了其预期遗传增益 16.7%，这种偏差通过构建 CVaR-OCS 得以消除，同时 CVaR-OCS 还额外恢复了一个神谕最优个体，并将增益分布方差降低了 4.8%。在挪威云杉中，推荐的 CVaR-OCS 操作点将尾部增益安全性提高了 6.60%，并将选择基础从 145 个个体扩大到 159 个，而遗传增益成本仅为 0.70%。基于 MCMC 的互补稳健性得分显示，挪威云杉中有 25 个 MAP-OCS 选择在后验分布中不稳定；事后排除这些个体未能改善尾部增益安全性，从而推动了有原则的 CVaR-OCS 方法。CVaR-OCS 为育种者提供了一种有原则且计算高效的工具，用于考虑不确定性的选择决策，并且需要多世代模拟研究来充分表征其对遗传增益轨迹和近交积累的长期影响。

## Abstract
Optimum contribution selection (OCS) balances genetic gain and inbreeding by optimizing parental contributions to the next generation, but current implementations rely on point estimates of breeding values that discard the uncertainty inherent in genetic evaluations. We introduce CVaR-OCS, a novel formulation that incorporates the full posterior distribution of estimated breeding values (EBVs) directly into the OCS objective via Conditional Value at Risk (CVaR) (a coherent risk measure from financial portfolio theory) allowing a single optimization to simultaneously maximize expected genetic gain and protect against worst-case outcomes driven by EBV uncertainty. We evaluate CVaR-OCS on a simulated multi-generation genomic selection dataset with known true breeding values (QTL-MAS 2010; n = 900 candidates), enabling direct comparison to an oracle solution, and on Norway spruce (Picea abies} n = 5525) forest tree breeding progeny trials. On the simulated dataset, MAP-OCS overestimated its own expected genetic gain by 16.7% due to EBV uncertainty, a bias eliminated by CVaR-OCS by construction, while CVaR-OCS also recovered one additional oracle-optimal individual and reduced gain distribution variance by 4.8%. In Norway spruce, the recommended CVaR-OCS operating point improved tail-gain security by 6.60% and broadened the selection base from 145 to 159 individuals at a genetic gain cost of only 0.70%. Complementary MCMC-based robustness scores revealed that 25 MAP-OCS selections in Norway spruce were unstable across the posterior distribution; post-hoc exclusion of these individuals failed to improve tail-gain security, motivating the principled CVaR-OCS approach. CVaR-OCS provides breeders with a principled, computationally efficient tool for uncertainty-aware selection decisions, and multi-generation simulation studies are needed to fully characterize its long-term effects on genetic gain trajectories and inbreeding accumulation.