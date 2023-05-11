# Helm-chart for Webapp deployment

This helm-chart deploys a REST-api based app into a cluster. It uses a service to make the port of the app's pod available to the cluster. The deployment also has an HPA

## To install helm chart onto your cluster:

- Download latest release of packaged chart / clone the repo
- Set kubectl context to your cluster 
- Run:
  ```
  helm install <Release_name> <Packaged_chart_parth> -n <NameSpace> --generate-name
  ```
  ```
  helm install <Release_name> <Cloned_repo_path> -n <NameSpace> --generate-name
  ```
  
## To configure values:

- Seeing configurable vlaues for the chart:
  ```
  helm show values <Cloned_repo_path>
  ```
- Installing chart with configured values:
  ```
  helm install <Release_name> <Cloned_repo_path> --set <key>=<Value> -n <NameSpace> --generate-name
  ```
- Using a custom configuration file:
  ```
  helm install <Release_name> <Cloned_repo_path> -f values.yaml -n <NameSpace> --generate-name
  ```
  
## To unistall helm chart:
  
  - Run:
    ```
    helm unistall <Release_name>
    ```



