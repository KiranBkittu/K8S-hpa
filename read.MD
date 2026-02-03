metrics service should be installed if not need to installed install it

kubectl get pods -n kube-system | grep metrics

To install metric server

kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

to check load and status

kubectl top pods

kubectl get hpa

To run the load 

kubectl run load-test --image=busybox -- /bin/sh

Inside the pod

while true; do wget -q -O- http://nginx-deploy; done

To watch scaling

kubectl get pods -w

