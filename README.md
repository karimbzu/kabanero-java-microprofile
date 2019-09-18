# Kabanero collections and pipelines demo

## Appsody Collections Demo commands

- Install appsody : 
	```
  brew install appsody/appsody/appsody
  ```
- List appsody repo : 
  ```
  appsody repo list
  ```
- Add Kabanero collections repo in appsody:
  ```
  appsody repo add <name> <url>
  appsody repo add kabcollections https://github.com/kabanero-io/collections/releases/download/v0.1.2/kabanero-index.yaml
  ```
- List all kabanero collections:
  ```
  appsody list | grep kabcollections
  ```
- Initialize kabanero java-microprofile collection:
  ```
  appsody init kabcollections/java-microprofile
  ```
- Generate app-deploy for deploying app on Kubernetes :
  ```
  appsody deploy --generate-only
  ```

## Kabanero Pipelines Demo commands


- Login to your cluster:
  ```
  oc login
  ```
- List all pods with all namespaces : 
  ```
  oc get pods --all-namespaces
  ```
- List all the kabanero tasks:
  ```
  oc get tasks
  ```
- List all kabanero pipelines:
  ```
  oc get pipelines
  ```
- Git clone Kabanero-pipleines in openshift cluster:
  ```
  git clone https://github.com/kabanero-io/kabanero-pipelines.git
  ```
- Apply pv.yaml file to the cluster:
  ```
  oc apply -f pv.yaml
  ```
- Create Docket secret:
  ```
  oc apply -f my-docker-secret.yaml 
  oc apply -f my-docker-secret.yaml 
  ```
- Update docker secret in service account:
  ```
  oc edit serviceaccounts kabanero-operator
  ```
- Apply the resources file:
  ```
  oc apply -f <pipeline-resource-file>.yaml 
  oc apply -f java-microprofile-pipeline-resources.yaml
  ```
- Apply the pipelinerun file:
  ```
  oc apply -f <pipeline-run-file>.yaml
  oc apply -f java-microprofile-pipeline-run.yaml
  ```
- Check logs of the pods:
  ```
  oc logs -f <pod-name> --all-containers
  ```
- Check the routes of the deployed application:
  ```
  oc get routes:
  ```
- Check the status of a pipelinerun and error if any failed status:
  ```
  oc get pipelineruns
  oc get pipelineruns/<pipelinerun-name> -o yaml
  ```
- Clean all the pipelineruns and application run pods
  ```
  oc delete pipelineruns --all
  oc delete appsodyapplications --all
  ```
