# helm-chart for webapp deployment

## To install helm chart onto your cluster:

- Download latest release of packaged chart
- Set kubectl context to your cluster 
- Run:
  ```
  helm install <Release_name> <Packaged_chart_parth>
  ```
  
## To configure values:

- Seeing configurable vlaues for the chart:
  ```
  helm show values <Packaged_chart_parth>
  ```
- Installing chart with configured values:
  ```
  helm install <Release_name> <Packaged_chart_parth> --set <key>=<Value>
  ```
  
## To unistall helm chart:
  
  - Run:
    ```
    helm unistall <Release_name>
    ```


helm install . -f values.yaml -n apps --generate-name
