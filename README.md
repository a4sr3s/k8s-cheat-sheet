# k8s-cheat-sheet
Kubernetes Cheat Sheet for Admins and CKA testers

## Working with pods

| Command                                                               | Description                                                           |
| :-----------                                                          | :-----------                                                          |
| kubectl get pods                                                      | List all pods in the current namespace                                |
| kubectl get pods -o wide                                              | List all pods in the current namespace, with more details             |
| kubectl get pods --all-namespaces                                     | List all pods in all namespaces                                       |
| kubectl get pod my-pod -o yaml                                        | Get a pod's YAML                                                      |
| kubectl get pods --selector env=prod,tier=frontend                    | List pods with the following labels env=prod,tier=frontend            |
| kubectl describe pod my-pod                                           | Describe pod with verbose output                                      |