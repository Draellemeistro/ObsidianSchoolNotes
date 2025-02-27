---
id: probabilistic_approach_to_hybrid_role_mining
aliases: []
tags:
  - SEARCH-role-mining
---

# [A probabilistic approach to hybrid role mining](https://dl.acm.org/doi/abs/10.1145/1653662.1653675?casa_token=2bFs-UTWk2UAAAAA:gxe61h0UJc9UhLDjEVOjMCokRNGMwP7YCl-sFCIuV1NFwTYzFknkZHl0joWajMyTYCy1QFHTnUu1hQ)

Role mining algorithms address an important access control problem: configuring a role-based access control system. Given a direct assignment of users to permissions, role mining discovers a set of roles together with an assignment of users to roles. The results should closely agree with the direct assignment. Moreover, the roles should be understandable from the business perspective in that they reflect functional roles within the enterprise. This requires hybrid role mining methods that work with both direct assignments and business information from the enterprise.

In this paper, we provide statistical measures to analyze the relevance of different kinds of business information for defining roles. We then present an approach that incorporates relevant business information into a probabilistic model with an associated algorithm for hybrid role mining. Experiments on actual enterprise data show that our algorithm yields roles that both explain the given user-permission assignments and are meaningful from the business perspective.
