# Avrora

Avrora is a comprehensive package for .NET that provides a library for Avro
serialisation, along with tools for inspecting and modifying Avro encoded
binary files. This toolkit is to help teams easily integrate Avro
serialisation into their projects and manage Avro files efficiently.

## Licensing

This library is closed-source and requires an annual subscription for access
and support. A 30-day demo license is available upon request.

## Features

- **Serialization Library**: High-performance .NET Standard 2.0 library
  for encoding and decoding messages in Avro format.
- **Command Line Tool**: CLI for encoding and decoding Avro files, perfect
  for automation and scripting.

## Compatibility

The library is supporting the [Avro 1.11.1][C1] specification.

The library is compatible with .NET Standard 2.0 and can be used in .NET and
.NET Core 2.0 and later, as well as .NET Framework. See
the [compatibility table][C2] for more information.

[C1]: https://avro.apache.org/docs/1.11.1/
[C2]: https://docs.microsoft.com/en-us/dotnet/standard/net-standard

## Getting Started

## Installation

### Via NuGet Package Manager

1. Open your project in Visual Studio.
2. Go to `Tools` > `NuGet Package Manager` > `Manage NuGet Packages for Solution`.
3. Search for `Avrora`.
4. Select the package and click `Install`.

### Via .NET CLI

Run the following command in your project directory:

```sh
dotnet add package Avrora
```

## Usage

## Serialising

```csharp
using Avrora;

public class Player
{
    public string Name { get; set; }
    public int Level { get; set; }
    public int Experience { get; set; }
}

var player = new Player
{
    Name = "John",
    Level = 10,
    Experience = 100
};

byte[] data = AvroSerialiser.Serialise(player);
```

## Deserialising

```csharp
var player = AvroSerialiser.Deserialise<Player>(data);
```

## Command Line Tool

The command line tool is distributed with the NuGet package.

## Encoding

Encodes a JSON file into an Avro file:

```sh
avrora encode data.json data.avro
```

## Decoding

Decodes an Avro file into a JSON file:

```sh
avrora decode data.avro data.json
```
