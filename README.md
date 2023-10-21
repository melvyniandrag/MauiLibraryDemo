# MauiLibraryDemo
Cant figure out how to get partial methods to work 

## /Demo/A.cs
```
namespace Demo
{
    public partial class A
    {
        public partial void DoNothing();
    }
}
```

## /Demo/Platforms/Windows/A.cs
```
using System.Diagnostics;

namespace Demo;

public partial class A
{
    public partial void DoNothing()
    {
        Debug.WriteLine("library does nothing");
    }
}
```

## Will not build. 
Error message:
```
Error	CS8795	Partial method 'A.DoNothing()' must have an implementation part because it has accessibility modifiers.	Demo (net7.0), Demo (net7.0-android), Demo (net7.0-ios), Demo (net7.0-maccatalyst)	C:\Users\melvy\Documents\Demo\Demo\A.cs	5	Active
```

## What the heck
This pattern does work for MAUI apps. This little minimal example was based on [ the official Microsoft demo ](https://github.com/dotnet/maui-samples/tree/main/7.0/PlatformIntegration/InvokePlatformCodeDemos)

Could it be that this partial method technique doesnt work with libraries?
