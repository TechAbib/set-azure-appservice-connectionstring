# set-azure-appservice-connectionstring

This action sets a connection string value in an Azure App Service settings. This action works for both windows and ubuntu vms.

## Usage

```yml
name: Test Set Connection String Action

on: [push]

jobs:
  # test set connectionstring
  setConnectionString:
    runs-on: windows-latest
    
    steps:
    - name: Set connection string
      uses: abelsquidhead/set-azure-appservice-connectionstring@v1
      with:
        servicePrincipal: 'http://AbelDeployPrincipal'
        servicePrincipalTenant: '72f988bf-86f1-41af-91ab-2d7cd011db47'
        servicePrincipalSecret: ${{ secrets.SERVICE_PRINCIPAL_SECRET }}
        azureSubscriptionName: 'ca-abewan-demo-test'
        resourceGroup: 'testconnstringaction-rg'
        appService: 'abel'
        connectionStringType: 'SQLAzure'
        connectionString: ${{ secrets.ABEL_CONNECTION_STRING }}
        connectionStringName: 'DefaultConnection'
```
## License
The scripts and documentation in this project are released under the [MIT License](LICENSE)
