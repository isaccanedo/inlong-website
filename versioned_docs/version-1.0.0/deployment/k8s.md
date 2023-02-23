---
title: Kubernetes
sidebar_position: 3
---

## Prerequisites

- Kubernetes 1.10+
- Helm 3.0+
- [InLong Helm Chart](https://github.com/apache/incubator-inlong/tree/master/docker/kubernetes)
- A dynamic provisioner for the PersistentVolumes(`production environment`)

## Install

```shell
kubectl create namespace inlong
helm upgrade inlong --install -n inlong ./
```

## Configuration



## Uninstall

```shell
helm uninstall inlong -n inlong
```

You can delete all `PVC ` if any persistent volume claims used, it will lose all data.

```shell
kubectl delete pvc -n inlong --all
```

