---
title: 'Esercitazione: Creare uno strumento .NET CoreTutorial: Create a .NET Core tool'
description: Informazioni su come creare uno strumento .NET Core.Learn how to create a .NET Core tool. A tool is a console application that is installed by using the .NET Core CLI.
ms.date: 02/12/2020
ms.openlocfilehash: 88cc3be7b149834ace0c5f3ba8ac8c039199908f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156725"
---
# <a name="tutorial-create-a-net-core-tool-using-the-net-core-cli"></a>Esercitazione: Creare uno strumento .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Create a .NET Core tool using the .NET Core CLI

**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive

Questa esercitazione illustra come creare e creare un pacchetto di uno strumento .NET Core.This tutorial teaches you how to create and package a .NET Core tool. L'interfaccia della riga di comando di .NET Core consente di creare un'applicazione console come strumento, che altri utenti possono installare ed eseguire. Gli strumenti .NET Core sono pacchetti NuGet installati dall'interfaccia della riga di comando di .NET Core.NET Core tools are NuGet packages that are installed from the .NET Core CLI. Per ulteriori informazioni sugli strumenti, vedere [Panoramica degli strumenti .NET Core](global-tools.md).

Lo strumento che verrà creato è un'applicazione console che accetta un messaggio come input e visualizza il messaggio insieme a righe di testo che creano l'immagine di un robot.

Questo è il primo di una serie di tre tutorial. In questa esercitazione viene creato e creato un pacchetto di uno strumento. Nelle due esercitazioni successive si [utilizza lo strumento come strumento globale](global-tools-how-to-use.md) e lo strumento come strumento [locale.](local-tools-how-to-use.md)

## <a name="prerequisites"></a>Prerequisites

- [.NET Core SDK 3.1](https://dotnet.microsoft.com/download) o versione successiva.

  Questa esercitazione e [l'esercitazione](global-tools-how-to-use.md) seguente per gli strumenti globali si applicano a .NET Core SDK 2.1 e versioni successive perché gli strumenti globali sono disponibili a partire da tale versione. Ma questo tutorial presuppone che hai installato 3.1 o versione successiva in modo che si ha la possibilità di continuare al [tutorial strumenti locali](local-tools-how-to-use.md). Gli strumenti locali sono disponibili a partire da .NET Core SDK 3.0. Le procedure per la creazione di uno strumento sono le stesse sia che lo si utilizzi come strumento globale o come strumento locale.
  
- Un editor di testo o editor di codice di propria scelta.

## <a name="create-a-project"></a>Creare un progetto

1. Aprire un prompt dei comandi e creare una cartella denominata *repository*.

1. Passare alla cartella del *repository* e immettere il comando seguente:

   ```dotnetcli
   dotnet new console -n microsoft.botsay
   ```

   Il comando crea una nuova cartella denominata *microsoft.botsay* nella cartella del *repository.*

1. Passare alla cartella *microsoft.botsay.*

   ```console
   cd microsoft.botsay
   ```

## <a name="add-the-code"></a>Aggiungere il codice

1. Aprire `Program.cs` il file con l'editor di codice.

1. Aggiungere la `using` seguente direttiva all'inizio del file:

   ```csharp
   using System.Reflection;
   ```

1. Sostituire `Main` il metodo con il codice seguente per elaborare gli argomenti della riga di comando per l'applicazione.

   ```csharp
   static void Main(string[] args)
   {
       if (args.Length == 0)
       {
           var versionString = Assembly.GetEntryAssembly()
                                   .GetCustomAttribute<AssemblyInformationalVersionAttribute>()
                                   .InformationalVersion
                                   .ToString();

           Console.WriteLine($"botsay v{versionString}");
           Console.WriteLine("-------------");
           Console.WriteLine("\nUsage:");
           Console.WriteLine("  botsay <message>");
           return;
       }

       ShowBot(string.Join(' ', args));
   }
   ```

   Se non viene passato alcun argomento, viene visualizzato un breve messaggio della Guida. In caso contrario, tutti gli argomenti vengono concatenati `ShowBot` in un'unica stringa e stampati chiamando il metodo creato nel passaggio successivo.

1. Aggiungere un nuovo `ShowBot` metodo denominato che accetta un parametro di stringa. Il metodo stampa il messaggio e l'immagine di un robot utilizzando righe di testo.

   ```csharp
   static void ShowBot(string message)
   {
       string bot = $"\n        {message}";
       bot += @"
       __________________
                         \
                          \
                             ....
                             ....'
                              ....
                           ..........
                       .............'..'..
                    ................'..'.....
                  .......'..........'..'..'....
                 ........'..........'..'..'.....
                .'....'..'..........'..'.......'.
                .'..................'...   ......
                .  ......'.........         .....
                .    _            __        ......
               ..    #            ##        ......
              ....       .                 .......
              ......  .......          ............
               ................  ......................
               ........................'................
              ......................'..'......    .......
           .........................'..'.....       .......
        ........    ..'.............'..'....      ..........
      ..'..'...      ...............'.......      ..........
     ...'......     ...... ..........  ......         .......
    ...........   .......              ........        ......
   .......        '...'.'.              '.'.'.'         ....
   .......       .....'..               ..'.....
      ..       ..........               ..'........
             ............               ..............
            .............               '..............
           ...........'..              .'.'............
          ...............              .'.'.............
         .............'..               ..'..'...........
         ...............                 .'..............
          .........                        ..............
           .....
   ";
       Console.WriteLine(bot);
   }
   ```

1. Salvare le modifiche.

## <a name="test-the-application"></a>Test dell'applicazione

Eseguire il progetto e osservare l'output. Provare queste variazioni nella riga di comando per visualizzare risultati diversi:

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- Hello from the bot
```

Tutti gli argomenti dopo il delimitatore `--` vengono passati all'applicazione.

## <a name="package-the-tool"></a>Confezionare lo strumento

Prima di poter comprimere e distribuire l'applicazione come strumento, è necessario modificare il file di progetto.

1. Aprire il file *microsoft.botsay.csproj* e aggiungere tre nuovi `<PropertyGroup>` nodi XML alla fine del nodo:

   ```xml
   <PackAsTool>true</PackAsTool>
   <ToolCommandName>botsay</ToolCommandName>
   <PackageOutputPath>./nupkg</PackageOutputPath>
   ```

   `<ToolCommandName>`è un elemento facoltativo che specifica il comando che richiamerà lo strumento dopo l'installazione. Se questo elemento non viene fornito, il nome del comando per lo strumento è il nome del file di progetto senza l'estensione *csproj.*

   `<PackageOutputPath>`è un elemento facoltativo che determina dove verrà prodotto il pacchetto NuGet. Il pacchetto NuGet è ciò che l'interfaccia della riga di comando di .NET Core utilizza per installare lo strumento.

   Il file di progetto è ora simile all'esempio seguente:The project file now looks like the following example:

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">
  
     <PropertyGroup>

       <OutputType>Exe</OutputType>
       <TargetFramework>netcoreapp3.1</TargetFramework>
  
       <PackAsTool>true</PackAsTool>
       <ToolCommandName>botsay</ToolCommandName>
       <PackageOutputPath>./nupkg</PackageOutputPath>
  
     </PropertyGroup>

   </Project>
   ```

1. Creare un pacchetto NuGet eseguendo il comando [dotnet pack:](dotnet-pack.md)

   ```dotnetcli
   dotnet pack
   ```

   Il file *microsoft.botsay.1.0.0.nupkg* viene creato nella `<PackageOutputPath>` cartella identificata dal valore del file *microsoft.botsay.csproj,* che in questo esempio è la cartella *./nupkg.*
  
   Quando si desidera rilasciare uno strumento pubblicamente, è possibile caricarlo in `https://www.nuget.org`. Una volta che lo strumento è disponibile su NuGet, gli sviluppatori possono installare lo strumento utilizzando il comando [dotnet tool install.](dotnet-tool-install.md) Per questa esercitazione si installa il pacchetto direttamente dalla cartella nupkg locale, pertanto non è necessario caricare il pacchetto in NuGet.For this tutorial you install the package directly from the local *nupkg* folder, so there's no need to upload the package to NuGet.

## <a name="troubleshoot"></a>Risolvere problemi

Se viene visualizzato un messaggio di errore durante l'esercitazione, vedere Risolvere i problemi di [utilizzo degli strumenti .NET Core](troubleshoot-usage-issues.md).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata creata un'applicazione console e inserita nel pacchetto come strumento. Per informazioni su come usare lo strumento come strumento globale, passare all'esercitazione successiva.

> [!div class="nextstepaction"]
> [Installare e usare uno strumento globale](global-tools-how-to-use.md)

Se si preferisce, è possibile saltare il tutorial strumenti globali e andare direttamente al tutorial strumenti locali.

> [!div class="nextstepaction"]
> [Installare e usare uno strumento locale](local-tools-how-to-use.md)
