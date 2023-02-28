# DB Project Template based on Domain-Driven Design

## Commands Used to Construct Project Template (Windows)

```txt
Create projects

   1        dotnet new console -n DbProject.Console
   2        dotnet new classlib -o DbProject.Infrastructure.Ado
   3        dotnet new classlib -o DbProject.Domain
   4        dotnet new mvc -n DbProject.Web
   5        dotnet new classlib -o DbProject.Infrastructure.EntityFramework


Add project dependencies

   6        dotnet add .\DbProject.Web\DbProject.Web.csproj reference .\DbProject.Domain\DbProject.Domain.csproj .\DbProject.Infrastructure.Ado\DbProject.Infrastructure.Ado.csproj .\DbProject.Infrastructure.EntityFramework\DbProject.Infrastructure.EntityFramework.csproj
   7        dotnet add .\DbProject.Web\DbProject.Console.csproj reference .\DbProject.Domain\DbProject.Domain.csproj .\DbProject.Infrastructure.Ado\DbProject.Infrastructure.Ado.csproj .\DbProject.Infrastructure.EntityFramework\DbProject.Infrastructure.EntityFramework.csproj 
   9        dotnet add .\DbProject.Infrastructure.Ado\DbProject.Infrastructure.Ado.csproj reference .\DbProject.Domain\DbProject.Domain.csproj   7        dotnet add .\DbProject.Infrastructure.EntityFramework\DbProject.Infrastructure.EntityFramework.csproj reference .\DbProject.Domain\DbProject.Domain.csproj   
 
Wrap up projects in a solution

  10        dotnet new sln -n DbProject
  11        dotnet sln .\DbProject.sln add (ls -r **/*.csproj)
  ```

## Added NuGet Package Dependencies
Be sure to *cd* into each project's directory before issuing the add package command.

### DbProject.Console

```txt
1. dotnet add package Microsoft.Extensions.Configuration
2. dotnet add package Microsoft.Extensions.Configuration.Json
3. dotnet add package Microsoft.Extensions.Configuration.FileExtensions
```

### DbProject.Infrastructure.Ado

```txt
1. dotnet add package System.Data.SqlClient
```

### DbProject.Infrastructure.EntityFramework

```txt
1. dotnet add package Microsoft.EntityFrameworkCore.SqlServer
2. dotnet add package Microsoft.EntityFrameworkCore.Design

You'll also want to install the .NET Core CLI Tools. Requires .NET Core SDK (you likely already have this if you've taken CS 366).

   dotnet tool install --global dotnet-ef
```
