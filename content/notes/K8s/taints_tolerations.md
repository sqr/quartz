---
title: Taints, tolerations and NodeAffinity
tags:
    - kubernetes
---

Taints and tolerations have to be used together in order to schedule specific workloads on specific nodes.

- Taints work on the node side
- Tolerations work on the workload side

When adding a taint to a node or node group, no workloads will be scheduled on them. For a workload to be scheduled on a tainted node, the workload needs to have the corresponding toleration.

However, taints and tolerations are not enough if we want a specific workload to exclusively run in specific nodes. Taints would make nodes "clean", and tolerations would allow the workloads to run on them, but they do not exclude them from running on any other untainted nodes. 

To achieve more granularity, we can also add NodeAffinity into the mix, which acts as a sort of magnet that will make specific workloads only scheduled in specific nodes. With taints, we avoid undesired workloads on desired nodes, with tolerations we allow desired workloads on desired nodes, and with NodeAffinity we can guarantee that desired workloads are not running on undesired nodes.
