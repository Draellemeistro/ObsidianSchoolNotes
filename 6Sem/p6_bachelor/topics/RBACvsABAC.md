---
id: RBACvsABAC
aliases: []
tags: []
---


# Links der nævner begge:
## ABAC vs RBAC
[Towards Attribute-Centric Access Control: an ABAC versus RBAC argument](https://www.proquest.com/docview/1832065500?accountid=8144&sourcetype=Scholarly%20Journals)
Recent developments in attribute-based access control have fueled the conventional debate regarding the pros and cons of Attributes-based access control (ABAC) versus Role-based access control (RBAC).
However, existing arguments have been primarily focused on the complexity analysis of the two models instead of their comprehensive need analysis.
On the contrary, the success and evolution of RBAC as a de-facto access control model is based on the thorough need analysis of using roles as a primary decision factor for controlling access.
Analogously, we need to consider the application areas for comparing the use of role-based and attribute-based approach.
In this regard, our work aims to bridge the gap between the RBAC and the ABAC proponents by convincing the RBAC supporters of the effectiveness of ABAC.
We identify various inherent traits of RBAC which have eventually become its limitations in addressing future access control needs for providing flexible, fine-grained, multifactor, and anonymous authorization in dynamically changing and context sensitive environments.
These limitations are usually addressed either through extended RBAC models or ABAC model.

We analyze the two approaches with respect to their effectiveness in overcoming the identified limitations and draw the conclusion that the attribute-centric approach is the ultimate future of access control.

@article{TwrdsAttributeAC2016
author={Fatima,Arjumand and Ghazi,Yumna and Shibli,Muhammad A. and Abassi,Abdul G.},
year={2016},
month={11},
title={Towards Attribute-Centric Access Control: an ABAC versus RBAC argument},
journal={Security and Communication Networks},
volume={9},
number={16},
pages={3152-3166},
note={Copyright - Copyright © 2016 John Wiley & Sons, Ltd; Last updated - 2016-10-26},
keywords={Communications},
isbn={19390114},
language={English},
url={https://www.proquest.com/scholarly-journals/towards-attribute-centric-access-control-abac/docview/1832065500/se-2},
}

## Mixing Role into ABAC
[Policy Based Role Centric Attribute Based Access Control Model Policy RC-ABAC](https://ieeexplore-ieee-org.zorac.aub.aau.dk/document/7411221)
As network speed and storage capacities are rising faster and higher, the remote storage and `cloud' concept is gaining momentum and is becoming increasingly popular with personal users as well as business users.
At the same time, privacy awareness and business confidentially are important factors in every cloud and data sharing decision.
For these and other reasons, the concept of access control models was developed in order to present complete solutions for privacy and confidentiality control in modern systems.
Various access controls methodologies have been suggested in the literature, each simplifying and providing flexibility to previous methods.
In this paper we will focus on two main methods which are Role Based Access Control (RBAC) and Attribute Based Access Control (ABAC).
We will discuss the benefits and drawbacks of each of them, and therefore the need for a novel approach that combines the benefits of these two techniques.

We are proposing a different hybrid model and justify how our suggested model and present why we think our suggested model (Policy RC-ABAC) will be more beneficiary in relation to a specific set of needs focusing on flexibility and auditability.

@INPROCEEDINGS{RCABAC2015,
  author={Varadharajan, Vijayaraghavan and Amid, Alon and Rai, Sudhanshu},
  booktitle={2015 International Conference on Computing and Network Communications (CoCoNet)}, 
  title={Policy based Role Centric Attribute Based Access Control model Policy RC-ABAC}, 
  year={2015},
  volume={},
  number={},
  pages={427-432},
  keywords={Access control;Logic gates;Measurement;Computational modeling;Business;Context;Standards;access control;authorization;ABAC;RBAC},
  doi={10.1109/CoCoNet.2015.7411221}}

## Towards user-oriented RBAC model
[Towards user-oriented RBAC model](https://content-iospress-com.zorac.aub.aau.dk/articles/journal-of-computer-security/jcs519)
Role mining is to define a role set to implement the role-based access control (RBAC) system and regarded as one of the most important and costliest implementation phases. 

While various role mining models have been proposed, we find that user experience/perception – one ultimate goal for any information system – is surprisingly ignored by the existing works.

One advantage of RBAC is to support multiple role assignments and allow a user to activate the necessary role to perform the tasks at each session.
However, frequent role activating and deactivating can be a tendinous thing from the user perspective.

A user-friendly RBAC system is expected to assign few roles to every user. So in this paper we propose to incorporate to the role mining process a user-role assignment constraint that mandates the maximum number of roles each user can have. Under this rationale, we formulate user-oriented role mining as the user role mining problem, where all users have the same maximal role assignments, the personalized role mining problem, where users can have different maximal role assignments, and the approximate versions of the two problems, which tolerate a certain amount of deviation from the complete reconstruction. The extra constraint on the maximal role assignments poses a great challenge to role mining, which in general is already a hard problem. We examine some typical existing role mining methods to see their applicability to our problems. In light of their insufficiency, we present a new algorithm, which is based on a novel dynamic candidate role generation strategy, tailored to our problems. Experiments on benchmark data sets demonstrate the effectiveness of our proposed algorithm.

@inproceedings{UserOrientedRBAC2013,
author = {Lu, Haibing and Hong, Yuan and Yang, Yanjiang and Duan, Lian and Badar, Nazia},
year = {2013},
month = {07},
pages = {81-96},
title = {Towards user-oriented RBAC model},
volume = {23},
isbn = {978-3-642-39255-9},
journal = {Journal of Computer Security},
doi = {10.1007/978-3-642-39256-6_6}
}

## A delegation model for extended RBAC
[A delegation model for extended RBAC](https://link-springer-com.zorac.aub.aau.dk/article/10.1007/s10207-010-0104-3)
In the field of access control, delegation is an important aspect that is considered part of the administration mechanism. Thus, a comprehensive access control model must provide a flexible administration model to manage delegation and revocation. Unfortunately, to our best knowledge, there is no complete model for describing all delegation requirements for role-based access control. Therefore, proposed models are often extended to support new delegation or revocation characteristics, which is a complex task to manage and requires the redefinition of these models. Moreover, since delegation is modelled separately from administration, this requires the specification of a separate security policy to deal with delegation. In this paper, we describe a new delegation approach for extended role-based access control models. We show that our approach is flexible and is sufficient to deal with administration and delegation requirements in a homogeneous unified framework. Moreover, it provides means to express various delegation and revocation dimensions in a simple manner.
