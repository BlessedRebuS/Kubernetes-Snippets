# kubernetes-snippets
Some useful snippets for Kubernetes. Here are listed the most useful ones.

Many examples starts from templates that can also be found here **https://github.com/dgkanatsios/CKAD-exercises**.

Every file can be applied with `kubectl -f <file-name>.yaml`.

---

## [canary-deployment.yaml](https://github.com/BlessedRebuS/kubernetes-snippets/blob/master/canary-deployment.yaml)
This is a useful template for a scenario where a second deploy has to be tested. In this case the traffic is split between two deploys. 75% of requestes go to the canary1 deploy and the other 25% to the canary2 deploy. The Kubernetes service handles request with a selector.

## [pod-with-volumes.yaml](https://github.com/BlessedRebuS/kubernetes-snippets/blob/master/pod-with-volumes.yaml)
This is a very common scenario where two containers mount the same directory at **/etc/foo**. This is often used for logging or serving custom webpages in nginx microservices.

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

## [liveness-probe.yaml](https://github.com/BlessedRebuS/kubernetes-snippets/blob/master/liveness-probe.yaml)
An example of a Liveness Probe. A Liveness Probe tells to the Kubernetes Node if the Pod has to be restarted or not.

## [pod-limitrange.yaml](https://github.com/BlessedRebuS/kubernetes-snippets/blob/master/pod-limitrange.yaml)
A limit range configuration that avoids the deploy of resources with more than 700Mi of memory. Increasing the Pod request will cause the apply to fail.

## [taint-pod.yaml](https://github.com/BlessedRebuS/kubernetes-snippets/blob/master/taint-pod.yaml)
Example of taint in Kubernetes. Each Pod with **tier=frontend** label will not be scheduled.

