# innovationday

Test project to use Azure functions and entity framework.

Read https://dev.to/azure/using-entity-framework-with-azure-functions-50aa

In powershell goto Auth-folder.

$env:IdentityDbConnectionString="Server=(localdb)\MSSQLLocalDB;Database=IdentityDb;Trusted_Connection=True;MultipleActiveResultSets=true"<br/>
then<br/>
dotnet-ef migrations add nameOfMigration (Initial migration already exists)<br/>
or<br/>
dotnet-ef database update<br/>

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

Requires dotnet ef tools:<br/>
install with: dotnet tool install --global dotnet-ef