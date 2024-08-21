# kind_example
Example code for getting started with local Kubernetes development using Kind and simple web applications built with Python and Go.

<br/>

## Steps to run

1. set the kubeconfig environment variable:

    ```shell
    export KUBECONFIG=~/.kube/config.kind
    ```

2. create the cluster using a cluster configuration

    ```shell
    kind create cluster --config cluster_config.yaml
    ```

3. view the nodes

    ```shell
    kubectl get nodes
    ```

4. add an ingress controller
    ```shell
    kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
    ```

5. create the deployment(s)

    ```shell
    kubectl apply -f go_web_deployment.yaml
    kubectl apply -f py_web_deployment.yaml
    ```

6. create the service(s)

    ```shell
    kubectl apply -f go_web_service.yaml
    kubectl apply -f py_web_service.yaml
    ```

6. create the ingress

    ```shell
    kubectl apply -f ingress.yaml
    ```

7. open a browser to http://127.0.0.1
    - refresh the page a few times to see the pod name, node name, and ip address change
    - nagivate to http://127.0.0.1/py 
    - navigate to http://127.0.0.1/go

<br/>

## Application code and Docker images:
#### Go web app

* **github:** https://github.com/davidslusser/pod_info_go
* **docker image:** https://github.com/davidslusser/pod_info_go/pkgs/container/pod_info_go 
* **docker pull:** 
    ```shell 
    docker pull ghcr.io/davidslusser/pod_info_go:latest 
    ```

#### Python web app

* **github:** https://github.com/davidslusser/pod_info_py
* **docker image:** https://github.com/davidslusser/pod_info_py/pkgs/container/pod_info_py 
* **docker pull:** 
    ```shell 
    docker pull ghcr.io/davidslusser/pod_info_py:latest 
    ```

<br/>

## References
- https://kind.sigs.k8s.io/
- https://kubernetes.io/
- https://kubernetes.io/docs/reference/kubectl/
- https://kubernetes.io/docs/tasks/tools/
