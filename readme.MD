metrics service should be installed if not need to installed install it

kubectl get pods -n kube-system | grep metrics

To install metric server

kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

to check load and status

kubectl get pods -n kube-system | grep metrics

kubectl top pods

kubectl get hpa

To run the load 

kubectl run load-test --image=busybox -- /bin/sh

Inside the pod

while true; do wget -q -O- http://nginx-deploy; done

To watch scaling

kubectl get pods -w

scenario : we have deployement of nginx with two nginx replicas in it, on peek days load will increase so we need to increase replicase

using horizental pod autoscaler we are mapping resizing the replicas based on load, if average load reached to 50% pod will also be increased max to 5 replicas as we gave maxReplicas 5 and minReplicas 2 and scaleTargetRef gave deployemt of nginx
