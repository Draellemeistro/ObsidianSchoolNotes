---
id: paper-survey_of_role_mining
aliases: []
tags:
  - SEARCH-role-mining
---

# [A Survey of Role Mining](https://dl.acm.org/doi/abs/10.1145/2871148?casa_token=Rk1MW4xl7w8AAAAA:pazBszKxIk9Qh9oBvMQx2c9jLT8oC40Ai_T5yhx08I5TQ3LoxxHXUYTKZPDz4lRAwaNu1x3R_xip2Q)

[[Role-Based_Access_Control_(RBAC)]]

RBAC critically depends on defining roles, which are a functional intermediate between users and permissions. Thus, for RBAC to be effective, an appropriate set of roles needs to be identified. Since many organizations already have user-permission assignments defined in some form, it makes sense to identify roles from this existing information. This process, known as role mining, is one of the critical steps for succesful RBAC adoption in any enterprise.

In recent years, numerous rolemining techniques have been developed, which take into account the characteristics of the core RBAC model, as well as its various extended features. In this article, we comprehensively study and classify the basic problem of role mining along with its several variants and the corresponding solution strategies. Categorization is done on the basis of the nature of the target RBAC system, the objective of role mining, and the type of solution. We then discuss the limitations of existing work and identify new areas of research that can lead to further enrichment of this field.

## Intro

**RBAC** (Sandhu et al. 1996; Ferraiolo et al. 2001) Permissions are grouped as roles, which are then assigned to users. Benefits only realized if the role set is appropriate for the organizational needs.

Apart from other considerations, the cost of admin is significantly reduced since the role set encapsulates functional requirements of the organization and does not change even if the personnel carrying out the tasks change. Thus, in order to successfully implement RBAC, a complete and correct set of roles is required.

The process of determining the required set of roles by combining several permissions is known as -- **Role Engineering** -- (Coyne 1995, Shin et al. 2003, Colantonio et al. 2008, Baumgrass et al. 2011)

Role engineering has been determined to be the most expensive aspect of deploying RBAC (O'Connor and Loomis 2010)
Traditionally carried out in a top-down fashion (Roeckle et al. 2000, Neumann and Strembeck 2002), wherein org business processes are analyzed and decomposed into smaller units.
This approach suffers from scalability issues and is time-consuming and typically necessitates some amount of human intervention.

More recently, a bottom-up approach has been put forward. This is -- **Role Mining** -- (Fuchs and pernul 2008, Frank et al. 2009, Molloy et al. 2010)

## Basic Formulation of Role Mining

### Deterministic Problem Modeling

#### Basic-RMP

- Variants of Basic-RMP
  - δ-approx RMP
  - MinNoise RMP
  - Usage RMP
  - Edge-RMP
  - User-Oriented Exact RMP
  - Edge + Basic-RMP
  - WSC Optimization
  - Cost-Based Metric

#### Role Hierarchy

### Heuristic Solutions for Deterministic Modeling

The different variants above are all NP-hard problems. Hence, several heuristic algorithms have been proposed for these problem variants. On to some different attempts at tackling just that....

#### Permission Grouping

Many algorithms are based on grouping of similar permission assignments of users to create roles. (Vaidya et al. 2010b) propose two algs of this type:

- CompleteMiner
- FastMiner
(Zhang et al 2013a) came forward with
- Data-Driven Role Evolution (DDRE)
(Blundo and Cimato 2010) propose
- Simple Role Mining Algorithm (SMA)

#### Problem-Mapping-Based Solutions

#### Matrix Decomposition

#### Graph-Based Strategies

#### Formal Concept-Analysis-Based Strategies

#### Data-Mining- and Optimization-Based Strategies

#### Mining Semantically Meaningful Roles

### Probabilistic Problem Modeling and Solutions

## Role Mining for RBAC Extensions

### Minimal Pertubation Role Mining

#### Mining Role Hierarchy

### Constraints in Role Mining

### Visual Role Mining

### Hybrid Role Mining

## Advanced Modeling of Role Mining

### Extended Boolean Matrix Decomposition

### Temporal Role Mining

## Tools and Evaluation

### Tools

- **ORCA:** (Schlegelmilch and Steffens 2005) Performs role mining by clustering similar permissions assignments and creates a hierarchy of permission clusters.
    It scans the user permission assignments, identifies the permission clusters etc..........
- **RMiner:** (Li et al 2013) Implements CompleteMiner, FastMiner, HierarchicalMiner, ORCA, StateMiner, GraphOptimization, Anti-apriori and WeightedRoleMining. Based on...
  - AN OPEN-SOURCE DATA MINING TOOL CALLED **WEKA** (Hall et al 2009)
- **VAT:** (Wang et al 2008) _Visual Assessment of cluster Tendency_ for analyzing cluster tendency...
  - **RoleVAT:** (Zhang et al 2009) Basically VAT for the purpose of role engineering.
- **ContROLE:** is a role development tool that provides a full support for HyDRo.
- (Ahmed and Osborn 2014) propose a Java-based tool that incorporates risk awareness
in the process of role mining

e provide a comparison of the different tools discussed so far in Table XI. The tool
proposed in **Ahmed and Osborn 2014** is referred to as the Risk Aware Tool (RAT). An
entry containing “-” indicates that the corresponding information is not available.

+-------------------------------------------------------------------+
|  Tool  |  TechDetails  |  RolMinSup  |  Functionality  | AlgType  |
+--------+---------------+-------------+-----------------+----------+
|  ORCA  |      Java     |     Post    |  ClusterAnalys  |    Own   |
+--------+---------------+-------------+-----------------+----------+
| RMiner |   Java, WEKA  |     Both    |RoleMine Updating| Existing |
+--------+---------------+-------------+-----------------+----------+
| RoleVAT|   Java, WEKA  |     Pre     | Anlyz need RBAC |   Own    |
+--------+---------------+-------------+-----------------+----------+
|ContRole|      ---      |     Pre     | HybridRoleMining|Own,Existi|
+--------+---------------+-------------+-----------------+----------+
|  RAT   |  Java, MYSQL  |     Both    |  Risk Detection | Existing |
+--------+---------------+-------------+-----------------+----------+

![Image](./../../../../../../Downloads/Screenshot%202025-02-14%20at%2000-50-24%20A%20Survey%20of%20Role%20Mining.png)
