# k8s-cheat-sheet
Kubernetes Cheat Sheet for Admins and CKA testers <br>
<p>&nbsp;</p>

## Working with pods

| Command                                                               | Description                                                           |
| :-----------                                                          | :-----------                                                          |
| kubectl explain pod                                                   | Documentation for pods                                                |
| kubectl get pods                                                      | List all pods in the current namespace                                |
| kubectl get pods -o wide                                              | List all pods in the current namespace, with more details             |
| kubectl get pods --all-namespaces                                     | List all pods in all namespaces                                       |
| kubectl get pods -n myspace                                           | List all pods in in myspace namespace                                 |
| kubectl get pod my-pod -o yaml                                        | Get a pod's YAML                                                      |
| kubectl get pods --show-labels                                        | Show labels for all pods on the current namespace                     |
| kubectl get pods --selector env=prod,tier=frontend                    | List pods with the following labels env=prod,tier=frontend            |
| kubectl describe pod my-pod                                           | Describe pod with verbose output                                      |
| kubectl run nginx --image=nginx                                       | Create and run simple nginx pod                                       |
| kubectl run nginx --image=nginx  --dry-run=client -o yaml             | Generate POD Manifest YAML file                                       |
| kubectl edit pod nginx                                                | Directly edit pod resource in current namespace                       |
| kubectl delete pod nginx                                              | Delete pod in current namespace                                       |
| kubectl logs pod/nginx                                                | Detailed insights into what's happening inside nginx pod              |
| kubectl exec -it nginx -n default -- bash                             | Access shell in nginx pod in default namespace                        |

<p>&nbsp;</p>

---
<p>&nbsp;</p>

## Working with nodes

| Command                                                               | Description                                                           |
| :-----------                                                          | :-----------                                                          |
| kubectl explain node                                                  | Documentation for nodes                                               |
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