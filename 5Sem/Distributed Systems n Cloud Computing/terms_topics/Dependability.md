> [!NOTE] Parent term [[Fault Tolerance]] from [[Cloud 10 Fault Tolerance|lecture 10]]

#### Basics

A **Component** provides **services** to **clients**. To provide services, the component may require services from other components $\to$ a component may **DEPEND** on some other component.

##### Specifically

A component $C$ depends on $C*$ if the **correctness** of $\text{C's}$  behavior depends on the correctness of $C*\text{'s}$ behavior. (Components are [[Process|processes]] or channels)

### Requirements related to dependability

| Requirement         | Description                              | Example                                                                                                                                   |
| ------------------- | ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| **Availability**    | Readiness for usage                      | System should be available for us at any time (99.999% availability, i.e., five 9s => very small down times)                              |
| **Reliability**     | Continuity of service delivery           | System should run continuously without failure. E.g., if we decide to stop the system for 2 hours it is not available, but it is reliable |
| **Safety**          | Very low probability of catastrophes     | Computing systems controlling an airplane, nuclear reactor                                                                                |
| **Maintainability** | How easy can a failed system be repaired |                                                                                                                                           |

#### Reliability vs Availability

![[image_Dependability.png]]
