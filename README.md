# k8s-cheat-sheet
Kubernetes Cheat Sheet for Admins and CKA testers <br>
<p>&nbsp;</p>

## Working with pods

| Command                                                                   | Description                                                           |
| :-----------                                                              | :-----------                                                          |
| kubectl explain pod                                                       | Documentation for pods                                                |
| kubectl get pods                                                          | List all pods in the current namespace                                |
| kubectl get pods -o wide                                                  | List all pods in the current namespace, with more details             |
| kubectl get pods --all-namespaces                                         | List all pods in all namespaces                                       |
| kubectl get pods -n myspace                                               | List all pods in in myspace namespace                                 |
| kubectl get pod my-pod -o yaml                                            | Get a pod's YAML                                                      |
| kubectl get pods --show-labels                                            | Show labels for all pods on the current namespace                     |
| kubectl get pods --selector env=prod,tier=frontend                        | List pods with the following labels env=prod,tier=frontend            |
| kubectl describe pod my-pod                                               | Describe pod with verbose output                                      |
| kubectl run nginx --image=nginx                                           | Create and run simple nginx pod                                       |
| kubectl run nginx --image=nginx  --dry-run=client -o yaml                 | Generate POD Manifest YAML file                                       |
| kubectl edit pod nginx                                                    | Directly edit pod resource in current namespace                       |
| kubectl delete pod nginx                                                  | Delete pod in current namespace                                       |
| kubectl logs nginx                                                        | Detailed insights into what's happening inside nginx pod              |
| kubectl logs --since=1h nginx                                             | Print the logs for the last hour for the nginx pod                    |
| kubectl logs --tail=20 nginx                                              | Print the most recent 20 lines of logs                                |
| kubectl exec -it nginx -n default -- bash                                 | Access shell in nginx pod in default namespace                        |
| kubectl get pods --sort-by='.status.containerStatuses[0].restartCount'    | List pods Sorted by Restart Count                                     |
| kubectl get pods -o wide &#124; grep mynode                               | Pods running on a node                                                |

<p>&nbsp;</p>

---
<p>&nbsp;</p>

## Working with nodes

| Command                                                                   | Description                                                           |
| :-----------                                                              | :-----------                                                          |
| kubectl explain node                                                      | Documentation for nodes                                               |
| kubectl get nodes                                                         | List all nodes in the current namespace                               |
| kubectl get nodes -o wide                                                 | List all nodes in the current namespace, with more details            |
| kubectl cordon my-node                                                    | Mark my-node as unschedulable                                         |
| kubectl drain my-node                                                     | Drain my-node in preparation for maintenance                          |
| kubectl uncordon my-node                                                  | Mark my-node as schedulable                                           |
| kubectl top node my-node                                                  | Show metrics for a given node                                         |
| kubectl describe nodes &#124; grep Allocated -A 5                         | Resource allocation per node                                          |
| kubectl describe nodes &#124; grep Taint                                  | Check for taints on all nodes                                         |
| kubectl taint nodes my-node key=value:NoSchedule                          | Create taint on my-node with NoSchedule affect                        |

<p>&nbsp;</p>

---
<p>&nbsp;</p>

## Working with services

| Command                                                                            | Description                             |
| :-----------                                                                       | :-----------                            |
| kubectl get services                                                               | List all services                       |
| kubectl get endpoints                                                              | List service endpoints                  |
| kubectl get service nginx-service -o yaml                                          | Get service detail                      |
| kubectl get service nginx-service -o go-template='{{.spec.clusterIP}}'             | Get service cluster ip                  |
| kubectl get service nginx-service -o go-template='{{(index .spec.ports 0).port}}'  | Get service cluster port                |
| kubectl expose deployment/my-app --type=LoadBalancer --name=my-service             | Expose deployment as lb service         |
| kubectl expose service/wordpress-1-svc --type=LoadBalancer --name=ns1              | Expose service as lb service            | 
