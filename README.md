# kubernetes-snippets
Some useful snippets for Kubernetes

Every file can be applied with `kubectl -f <file-name>.yaml`

---

## [canary-deployment.yaml](https://github.com/BlessedRebuS/kubernetes-snippets/blob/master/canary-deployment.yaml)
This is a useful template for a scenario where a second deploy has to be tested. In this case the traffic is split between two deploys. 75% of requestes go to the canary1 deploy and the other 25% to the canary2 deploy. The Kubernetes service handles request with a selector.

## [multi-container-pod.yaml](https://github.com/BlessedRebuS/kubernetes-snippets/blob/master/multi-container-pod.yaml)
A simple template to deploy multiple containers in the same Pod.

## [network-policy.yaml](https://github.com/BlessedRebuS/kubernetes-snippets/blob/master/network-policy.yaml)
A Network Policy that allow access to the deploy labeled by **testdeploy** only to the pod with the label **access: granted**

## [nginx-with-init.yaml](https://github.com/BlessedRebuS/kubernetes-snippets/blob/master/nginx-with-init.yaml)
A Pod template with initContainers. The initContainers are containers that run before the others in order to initialize the enviroment. This is often done with busybox images.

## [statefulset-template.yaml](https://github.com/BlessedRebuS/kubernetes-snippets/blob/master/statefulset-template.yaml)
Template to test the StatefulSet functions of kubernetes.

## [security-context-pod](https://github.com/BlessedRebuS/kubernetes-snippets/blob/master/security-context-pod)
Template for the unprivileged Pod executions with some basic rules.
