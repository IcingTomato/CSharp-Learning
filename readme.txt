C# Learning
=================

So, I'm so excited to learn C# and I'm going to use this repository to store all my C# learning projects.

I'm going to use Visual Studio Code with .NET 7 to write my code on ChromeOS virtual machine (Debian 12).

Install .NET 7:

```bash
wget https://packages.microsoft.com/config/debian/12/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install -y dotnet-sdk-7.0
sudo apt-get install -y aspnetcore-runtime-7.0
sudo apt-get install -y dotnet-runtime-7.0
```

Create a new project:

```bash
#dotnet new console --framework net7.0 --output HelloWorld
dotnet new console --framework net7.0 
``` 
Source Code:

```csharp
// See https://aka.ms/new-console-template for more information
// Console.WriteLine("Hello, World!");

using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Text;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            // Console.WriteLine("Hello, World!");

            Console.WriteLine("What is your name? ");
            var name = Console.ReadLine();
            var currentDate = DateTime.Now;
            Console.WriteLine($"{Environment.NewLine}Hello, {name}, on {currentDate:d} at {currentDate:t}!");
            Console.Write($"{Environment.NewLine}Press any key to exit...");
            Console.ReadKey(true);
        }
    }
}
```

Change the `launch.json`:

```json
@@-"console": "internalConsole",
@@+"console": "integratedTerminal",
```

Run the project:

```bash
dotnet run
```
