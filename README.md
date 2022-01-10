# vsgallery

A Visual Studio custom gallery feed based on Azure functions and blob storage

Usage:

1. Clone this repo
2. Deploy to an Azure Functions (v4+) app
3. Add a `VSGALLERY_STORAGE` setting with the connection string to your storage account.

Assumes:
1. The storage account has a container named `feed`.
2. VSIXes will be uploaded to that container, which will cause an `atom.xml` file in the 
   container to be automatically created/updated as needed.