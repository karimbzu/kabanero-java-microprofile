# kabanero collections and pipelines demo

## Appsody Collections Demo

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
