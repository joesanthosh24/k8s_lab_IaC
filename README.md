# Kubernetes Deployment Lab.

- Docker container url: https://hub.docker.com/repository/docker/joesanthosh/cst8918-a01-weather-app/general
- Requirements
    * enable Kubernetes in Docker Desktop
    * install kubectl (kubernetes CLI)
- Steps For testing:
    ```
     kubectl config use-context docker-desktop
     kubectl apply -f ./k8s/a01_namespace.yaml (Create a namespace)
     kubectl create secret generic weather --from-literal='api-key=<your-secret-api-key>' -n cst8918 (Create a Secret)
     kubectl apply -f ./k8s/a01_deployment.yaml -n cst8918 (Run the deployment yaml file)
     kubectl apply -f ./k8s/a01_service.yaml -n cst8918 (Run the service yaml file)
    ```

- Delete Resources:
   ```
    kubectl delete deployment weather-app-deployment -n cst8918
    kubectl delete service weather-app-service -n cst8918
    kubectl delete secret weather -n cst8918
    kubectl delete namespace cst8918
   ```
