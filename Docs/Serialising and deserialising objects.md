# Serialising and deserialising objects

## Serialising

Code:

```csharp
using Avrora;
using System.IO;

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
