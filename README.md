# k8s-cheat-sheet
Kubernetes Cheat Sheet for Admins and CKA testers
<p>&nbsp;</p>

## Working with pods

| Command                                                               | Description                                                           |
| :-----------                                                          | :-----------                                                          |
| kubectl get pods                                                      | List all pods in the current namespace                                |
| kubectl get pods -o wide                                              | List all pods in the current namespace, with more details             |
| kubectl get pods --all-namespaces                                     | List all pods in all namespaces                                       |
| kubectl get pod my-pod -o yaml                                        | Get a pod's YAML                                                      |
| kubectl get pods --show-labels                                        | Show labels for all pods on the current namespace                     |
| kubectl get pods --selector env=prod,tier=frontend                    | List pods with the following labels env=prod,tier=frontend            |
| kubectl describe pod my-pod                                           | Describe pod with verbose output                                      |
| kubectl run nginx --image=nginx                                       | Create and run simple nginx pod                                       |
| kubectl run nginx --image=nginx  --dry-run=client -o yaml             | Generate POD Manifest YAML file                                       |

<p>&nbsp;</p>

---
<p>&nbsp;</p>

## Working with nodes

| Command                                                               | Description                                                           |
| :-----------                                                          | :-----------                                                          |
| kubectl get nodes                                                     | List all nodes in the current namespace                               |
| kubectl get nodes -o wide                                             | List all nodes in the current namespace, with more details            |
| kubectl cordon my-node                                                | Mark my-node as unschedulable                                         |
| kubectl drain my-node                                                 | Drain my-node in preparation for maintenance                          |
| kubectl uncordon my-node                                              | Mark my-node as schedulable                                           |
| kubectl top node my-node                                              | Show metrics for a given node                                         |

<p>&nbsp;</p>

---
<p>&nbsp;</p>

## Working with services