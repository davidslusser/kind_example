# kind_example
example code for getting started with local Kubernetes development using Kind


kind create cluster --config cluster_config.yaml
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml

docker save demo:latest> demo.tar
kind load image-archive ./demo.tar

kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl apply -f ingress.yaml
