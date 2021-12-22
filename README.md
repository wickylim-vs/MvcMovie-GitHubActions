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


making changes on both master and dev-branch

