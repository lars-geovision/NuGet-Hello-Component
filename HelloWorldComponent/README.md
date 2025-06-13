#### Notes:
```
cd D:\Projekte\NuGet-Hello-Component\HelloWorldComponent; dotnet pack -c Debug -o "$env:USERPROFILE\.nuget\packages\helloworldcomponent\"; cd D:\Projekte\HelloWorldBlazorApp; dotnet clean; dotnet nuget locals all --clear; dotnet add package HelloWorldComponent --source "$env:USERPROFILE\.nuget\packages\helloworldcomponent\";





dotnet add package HelloWorldComponent
dotnet nuget locals all --clear;
dotnet add package HelloWorldComponent
Remove-Item -Recurse -Force "$env:USERPROFILE\.nuget\packages\helloworldcomponent";
cd D:\Projekte\NuGet-Hello-Component\HelloWorldComponent; dotnet pack -c Debug -o  D:\Projekte\NuGet-Hello-Component\HelloWorldComponent\local-packages; cd D:\Projekte\HelloWorldBlazorApp; dotnet clean; dotnet nuget locals all --clear; dotnet clean; dotnet add package HelloWorldComponent --source D:\Projekte\NuGet-Hello-Component\HelloWorldComponent\local-packages\;


```

# This one works:
but creates additional folder
1. do changes in HelloWorldComponent project
2. run the following command in PowerShell:

```
cd D:\Projekte\NuGet-Hello-Component\HelloWorldComponent; dotnet pack -c Debug -o  D:\Projekte\NuGet-Hello-Component\HelloWorldComponent\local-packages; cd D:\Projekte\HelloWorldBlazorApp; dotnet clean; dotnet nuget locals all --clear; dotnet clean; dotnet add package HelloWorldComponent --source D:\Projekte\NuGet-Hello-Component\HelloWorldComponent\local-packages\

```
3. Press Restart or Run Button in Visual Studio


Hints: Ignore the following error message in Visual Studio:
```
error: NU1101: Unable to find package Microsoft.AspNetCore.Components.Web. No packages exist with this id in source(s): D:\Projekte\NuGet-Hello-Component\HelloWorldComponent\local-packages\
error: Package 'HelloWorldComponent' is incompatible with 'all' frameworks in project 'D:\Projekte\HelloWorldBlazorApp\HelloWorldBlazorApp.csproj'.
```