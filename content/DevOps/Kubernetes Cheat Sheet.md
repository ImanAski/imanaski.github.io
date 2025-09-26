---
tags:
  - DevOps
  - Kubernetes
  - Cheatsheet
title: Kubernetes Cheat Sheet
draft:
---

## Basic Commands
- `kubectl version`: Check Kubernetes version
- `kubectl cluster-info`: Display cluster info
- `kubectl get <resource>`: List resources (pods, services, etc.)
- `kubectl describe <resource> <name>`: Show detailed resource info
- `kubectl apply -f <file>`: Apply configuration file
- `kubectl delete -f <file>`: Delete resources from file

## Pod Management
- `kubectl get pods`: List all pods
- `kubectl get pods -o wide`: List pods with detailed info
- `kubectl create -f <pod.yaml>`: Create pod from YAML
- `kubectl delete pod <name>`: Delete a pod
- `kubectl exec -it <pod> -- <cmd>`: Execute command in pod
- `kubectl logs <pod>`: View pod logs

## Deployment Management
- `kubectl create deployment <name> --image=<image>`: Create deployment
- `kubectl scale deployment <name> --replicas=<n>`: Scale deployment
- `kubectl rollout status deployment/<name>`: Check rollout status
- `kubectl rollout undo deployment/<name>`: Rollback deployment
- `kubectl edit deployment <name>`: Edit deployment config

## Service Management
- `kubectl get services`: List services
- `kubectl expose deployment <name> --port=<port> --type=<type>`: Create service
- `kubectl delete service <name>`: Delete service

## ConfigMap and Secrets
- `kubectl create configmap <name> --from-file=<file>`: Create ConfigMap
- `kubectl create secret generic <name> --from-literal=<key>=<value>`: Create Secret
- `kubectl get configmaps`: List ConfigMaps
- `kubectl get secrets`: List Secrets

## Namespace Management
- `kubectl get namespaces`: List namespaces
- `kubectl create namespace <name>`: Create namespace
- `kubectl delete namespace <name>`: Delete namespace
- `kubectl get pods -n <namespace>`: List pods in namespace

## Resource Monitoring
- `kubectl top pod`: Show pod resource usage
- `kubectl top node`: Show node resource usage
- `kubectl get events`: View cluster events

## Common YAML Structure
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: <name>
  namespace: <namespace>
  labels:
    <key>: <value>
spec:
  containers:
  - name: <container-name>
    image: <image>
    ports:
    - containerPort: <port>
```