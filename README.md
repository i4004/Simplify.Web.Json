# This project is moved to https://github.com/SimplifyNet/Simplify.Web.Json

# Simplify.Web.Json

`Simplify.Web.Json` is a package which provides JSON serialization/deserialization for [Simplify.Web](https://github.com/i4004/Simplify.Web) web-framework controllers.

## Package status

| Latest version | [![Nuget version](http://img.shields.io/badge/nuget-v1.2.3-blue.png)](https://www.nuget.org/packages/Simplify.Web.Json/) |
| :------ | :------: |
| **Dependencies** | [![NuGet Status](http://nugetstatus.com/Simplify.Web.Json.png)](http://nugetstatus.com/packages/Simplify.Web.Json) |
| **Target Frameworks** | 4.6.2, Standard 2.0 |

## Build status

| Branch | Status |
| :------ | :------ |
| **master** | [![AppVeyor Build status](https://ci.appveyor.com/api/projects/status/dfi53jjk9klcc4bx/branch/master?svg=true)](https://ci.appveyor.com/project/i4004/simplify-web-json/branch/master) |

## Examples

### Sending JSON to client

If the controller returns `Json` response class object, then the Framework execution will be stopped, object will be parsed to JSON string and sent to client

```csharp
public class MyController : Controller
{
	public override ControllerResponse Invoke()
	{
		...
		return new Json(myObj);
	}
}
```

### Getting JSON from client

#### Registering binder

```csharp
public void Configuration(IAppBuilder app)
{
	...
	HttpModelHandler.RegisterModelBinder<JsonModelBinder>();

	app.UseSimplifyWeb();
}
```

#### Accessing model

JSON string will be deserialized to the controller model on first model access
```csharp
public class MyController : Controller<MyModel>
{
	public override ControllerResponse Invoke()
	{
		Model.
	}
}
```
