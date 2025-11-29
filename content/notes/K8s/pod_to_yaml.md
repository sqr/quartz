---
title: Pod to yaml
tags:
    - kubernetes
    - pods
---
Since most pod properties are immutable, the fastest way to edit them when faced with broken pods in exams like Kubernetes Certified Administrator is to save the pod properties as yaml locally, editing as needed, deleting and recreating it.

To export a pod as yaml:

```bash
kubectl get pod <pod-name> -o yaml > pod.yml

