# kind_example
Example code for getting started with local Kubernetes development using KinD

<br/>

## About

<br/>

## Steps to run


kind create cluster --config cluster_config.yaml

kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml

docker save demo:latest> demo.tar
kind load image-archive ./demo.tar

kubectl apply -f deployment.yaml

kubectl apply -f service.yaml

kubectl apply -f ingress.yaml

<br/>

## References
- https://kind.sigs.k8s.io/
- https://kubernetes.io/
- https://kubernetes.io/docs/reference/kubectl/
- https://kubernetes.io/docs/tasks/tools/
