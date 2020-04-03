# AnyConfig
A .net configuration library to make configuration of multi-target applications easier.

## Description

AnyConfig makes configuration on solutions which mix .Net Core and .Net Framework projects easier. It abstracts away ConfigurationManager and IConfiguration loading with no dependencies on Microsoft implementation. You can instead use ConfigurationManager to load either json or xml configuration files, as well as the IConfiguration interface. This allows you to upgrade to json configuration files even for older projects without changing any code!

## Installation
```Powershell
PM> Install-Package AnyConfig
```

## Features

* Backwards compatible interface for ConfigurationManager for xml and json
* Supports IConfiguration interface for xml and json
* Supports generics for simple configuration value lookups
* Automatic discovery of configuration files for .Net Core or .Net Framework projects

## Usage

Simplest usage is using the dedicated generics interface:
```csharp
var isEnabled = Config.Get<bool>("IsEnabled");
```

You can also create a configuration class:
```csharp
var configuration = Config.Get<MyTestConfiguration>();
```

If you need, use the legacy ConfigurationManager too:
```csharp
var isEnabled = ConfigurationManager.AppSettings["IsEnabled"];
```

The built-in ConfigurationManager even supports generics:
```csharp
var isEnabled = ConfigurationManager.AppSettings<bool>["IsEnabled"];
```

## Advanced Usage

See the [wiki](https://github.com/replaysMike/AnyConfig/wiki)


