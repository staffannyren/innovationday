# innovationday

Test project to use Azure functions and entity framework.

Read https://dev.to/azure/using-entity-framework-with-azure-functions-50aa

In powershell goto Auth-folder.

$env:IdentityDbConnectionString="Server=(localdb)\MSSQLLocalDB;Database=IdentityDb;Trusted_Connection=True;MultipleActiveResultSets=true"
then
dotnet-ef migrations add nameOfMigration (Initial migration already exists) 
or
dotnet-ef database update

ApplicationDbContextFactory is needed to use with dotnet-ef

Setup variables in local.settings.json
```
{
  "IsEncrypted": false,
  "Values": {
    "AzureWebJobsStorage": "UseDevelopmentStorage=true",
    "FUNCTIONS_WORKER_RUNTIME": "dotnet",
    "UseInMemoryDatabase": true,
    "IdentityDbConnectionString": "Server=(localdb)\\MSSQLLocalDB;Database=IdentityDb;Trusted_Connection=True;MultipleActiveResultSets=true"
  }
}
```