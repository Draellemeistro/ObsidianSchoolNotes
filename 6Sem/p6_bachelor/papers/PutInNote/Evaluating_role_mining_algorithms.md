---
id: Evaluating_role_mining_algorithms
aliases: []
tags:
  - SEARCH-role-mining
---


# [Evaluating role mining algorithms](https://dl.acm.org/doi/abs/10.1145/1542207.1542224?casa_token=EG6dKu95ejEAAAAA:qSXywC5mASXYREZkQ2pnLjPcqFtjGWZZwuLrUNKuA4reTfgcwZn8jo9zYm1UimJ2kC6xYS3frravnA)
While many role mining algorithms have been proposed in recent years, there lacks a comprehensive study to compare these algorithms. These role mining algorithms have been evaluated when they were proposed, buth the evaluations were using different datasets and evaluation criteria.

In this paper, we introduce a comprehensive framework for evaluating role mining algorithms. We categorize role mining algorithms into two classes based on their outputs;
1. Class 1 algorithms output a sequence of prioritized roles while
2. Class 2 algorithms output complete RBAC states. We then develop techniques that enable us to compare these algorithms directly. We also introduce a new role mining algorithm and two new ways for algorithmically generating datasets for evaluation. Using synthetic as well as real datasets, we compared nine role mining algorithms.

.........

# Conclusion
While many role mining algorithms have been proposed in recent years, there lacks a comprehensive study to compare these algs.
We presen an evaluation framework for comparing different role mining algs, including algs that output a sequence of prioritized roles (**class 1 algs**) and a;gs that output complete RBAC states (**Class 2 algs**).
WE also propose a neww role mining alg and two new ways for generating datasets for evaluating role mining algs. We evaluate nine role mining algs using real datasets as well as synthetic datasets and our result demonstrate the strengths and weaknesses of these algs. 

There are still a few interesting problems for future research:
- **Handling data with attribute information.** In addition to the user-permission data, attribute info may also be available. It is interesting to study how to measure the "_goodness_" of a role miing alg (e.g., _AttributeMiner_) that uses both user bpermission data and attribute info.
- Handling noisy data. In some scenarios, the input
user-permission data may contain noises. In this con-
text, the goal of the role mining algorithm is to output
an optimal RBAC state that is allowed to have a few
deviations from the original user-permission data. We
use DUPA assignments as an incomplete approxima-
tion of noise.

