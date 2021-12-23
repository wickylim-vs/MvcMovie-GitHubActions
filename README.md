# DotNet Core MVC Movie

### dotnet CLI Build Steps

Run debug on local
```
dotnet run
```
Restore packages
```
dotnet restore
```
Create release .dll
```
dotnet publish -c Release -o out
```
Run release .dll
```
cd out/
dotnet MvcMovie.dll
```


### Environment Variable

Use environment variable (on controller)
```
Environment.GetEnvironmentVariable("APP_MESSAGE");
```

Pass variables from controller to view. On Controller,
```
ViewBag.Message = Environment.GetEnvironmentVariable("APP_MESSAGE");
```
on view,
```
<h1 class="display-4">Welcome to MVCMovie @ViewBag.Message</h1>
```

### Docker run
Run app
```
docker run -p 80:80 -d --rm --name mvcmovie wickylim18/dotnet-mvcmovie:0.1
```
Pass environment variable on "docker run"
```
docker run -p 80:80 -d --rm --name mvcmovie -e APP_MESSAGE='on Docker' wickylim18/dotnet-mvcmovie:0.1
```


### Merge conflicts

making changes on both master and dev-branch

1. git rebase
2. (edit files with conficts)
3. git commit


### Unit Test

1. Add unit test dependencies on .csproj
```
  <ItemGroup>
    ...
    
    <PackageReference Include="Microsoft.NET.Test.Sdk" Version="16.11.0" />
    <PackageReference Include="NUnit" Version="3.13.2" />
    <PackageReference Include="NUnit3TestAdapter" Version="4.0.0" />
    <PackageReference Include="coverlet.collector" Version="3.1.0" />
  </ItemGroup>
```

2. Create unit test .cs files
3. dotnet test

Unit test reference: https://docs.microsoft.com/en-us/dotnet/core/tutorials/testing-with-cli#organizing-and-testing-using-the-newtypes-pets-sample
Reference (exclude unit test on Release build): https://stackoverflow.com/a/56646051/2963461