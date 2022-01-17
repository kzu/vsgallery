# vsgallery

A Visual Studio custom gallery feed based on Azure functions and blob storage

Usage:

1. Create an Azure storage account and a corresponding container.
2. Create an Azure Functions (v4+) app
3. Add a `AZURE_STORAGE` setting to the functions app in 2) with the connection string to the storage account in 1).
4. Fork this repo
5. Add a repo secret named `AZURE_CONTAINER` with the container name used in 1). You can skip 
   this if the container name is `vsgallery`.
6. Add a repo secret named `AZURE_APPNAME` containing the functions app name from 2).
7. Add a repo secret named `AZURE_CREDENTIALS` after following the [steps in this blog](https://www.cazzulino.com/net6functions.html#github-actions-builddeploy)
8. In the Deployment Center section of the function app, connect to the repo, and select the existing `deploy.yml` workflow, using 
   the App Service deployment provider. 

Now whenever you upload a new VSIX to the container in 1), an `atom.xml` file 
will be automatically created/updated as needed.