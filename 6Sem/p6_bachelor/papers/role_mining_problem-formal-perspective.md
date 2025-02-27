---
id: role_mining_problem-formal-perspective
aliases: []
tags:
  - SEARCH-role-mining
---

# [The role mining problem: A formal perspective](https://dl.acm.org/doi/abs/10.1145/1805974.1805983)

Devising a complete and correct set of roles has been recognized as one of the most important and challenging tasks in implementing role-based access control. A key problem related to this is the notion of goodness/interestingness—when is a role good/interesting? In this article, we define the Role Mining Problem (RMP) as the problem of discovering an optimal set of roles from existing user permissions. The main contribution of this article is to formally define RMP and analyze its theoretical bounds. In addition to the above basic RMP, we introduce two different variations of the RMP, called the δ-Approx RMP and the minimal-noise RMP that have pragmatic implications. We reduce the known “Set Basis Problem” to RMP to show that RMP is an NP-complete problem. An important contribution of this article is also to show the relation of the RMP to several problems already identified in the data mining and data analysis literature. By showing that the RMP is in essence reducible to these known problems, we can directly borrow the existing implementation solutions and guide further research in this direction. We also develop a heuristic solution based on the previously proposed FastMiner algorithm, which is very accurate and efficient.
