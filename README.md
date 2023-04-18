This demo pulls a model registry from the Azure ML workspace, builds the a docker with model in it, then publishes the docker image into docker hub.

Github Actions is used to orchestrates the build steps.

### Notes
* Implements mlops ch4
* Use ml extension for az cli v2. Not to confuse ml v1 obsolete extensions.

* The auto install of az extension seems does not work
   * Not this: https://learn.microsoft.com/en-us/cli/azure/ml(v1)?view=azure-cli-latest
  * But this: https://learn.microsoft.com/en-us/azure/machine-learning/quickstart-create-resources?view=azureml-api-2

* Generate Azure Service Principal (using Azure CloudShell)
    ``` 
        az ad sp create-for-rbac --name "ml-auth2" 
        --sdk-auth --role contributor --scopes /subscriptions/{subs-id}/resourceGroups/{resource-group-id}
    ```