---
title: 'Esercitazione: creare uno strumento .NET Core'
description: Informazioni su come creare uno strumento .NET Core. Uno strumento è un'applicazione console che viene installata usando il interfaccia della riga di comando di .NET Core.
ms.date: 02/12/2020
ms.openlocfilehash: 88cc3be7b149834ace0c5f3ba8ac8c039199908f
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156725"
---
# <a name="tutorial-create-a-net-core-tool-using-the-net-core-cli"></a>Esercitazione: creare uno strumento .NET Core usando il interfaccia della riga di comando di .NET Core

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

Questa esercitazione illustra come creare e creare un pacchetto di uno strumento .NET Core. Il interfaccia della riga di comando di .NET Core consente di creare un'applicazione console come strumento, che altri utenti possono installare ed eseguire. Gli strumenti di .NET Core sono pacchetti NuGet installati dal interfaccia della riga di comando di .NET Core. Per altre informazioni sugli strumenti, vedere [Cenni preliminari sugli strumenti di .NET Core](global-tools.md).

Lo strumento che verrà creato è un'applicazione console che accetta un messaggio come input e visualizza il messaggio insieme alle righe di testo che creano l'immagine di un robot.

Questo è il primo di una serie di tre esercitazioni. In questa esercitazione viene creato e creato un pacchetto di uno strumento. Nelle due esercitazioni successive si [userà lo strumento come strumento globale](global-tools-how-to-use.md) e si [userà lo strumento come strumento locale](local-tools-how-to-use.md).

## <a name="prerequisites"></a>Prerequisites

- [.NET Core SDK 3,1](https://dotnet.microsoft.com/download) o versione successiva.

  Questa esercitazione e l' [esercitazione seguente per gli strumenti globali](global-tools-how-to-use.md) si applicano a .NET Core SDK 2,1 e versioni successive, perché gli strumenti globali sono disponibili a partire da tale versione. Tuttavia, in questa esercitazione si presuppone che sia installato 3,1 o versione successiva, in modo da avere la possibilità di continuare con l' [esercitazione sugli strumenti locali](local-tools-how-to-use.md). Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0. Le procedure per la creazione di uno strumento sono le stesse se lo si usa come strumento globale o come strumento locale.
  
- Un editor di testo o editor di codice di propria scelta.

## <a name="create-a-project"></a>Creare un progetto

1. Aprire un prompt dei comandi e creare una cartella denominata *repository*.

1. Passare alla cartella del *repository* e immettere il comando seguente:

   ```dotnetcli
   dotnet new console -n microsoft.botsay
   ```

   Il comando crea una nuova cartella denominata *Microsoft. botsay* nella cartella del *repository* .

1. Passare alla cartella *Microsoft. botsay* .

   ```console
   cd microsoft.botsay
   ```

## <a name="add-the-code"></a>Aggiungere il codice

1. Aprire il file `Program.cs` con l'editor di codice.

1. Aggiungere la direttiva di `using` seguente all'inizio del file:

   ```csharp
   using System.Reflection;
   ```

1. Sostituire il metodo `Main` con il codice seguente per elaborare gli argomenti della riga di comando per l'applicazione.

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

   Se non viene passato alcun argomento, viene visualizzato un breve messaggio di guida. In caso contrario, tutti gli argomenti vengono concatenati in una singola stringa e stampati chiamando il metodo `ShowBot` creato nel passaggio successivo.

1. Aggiungere un nuovo metodo denominato `ShowBot` che accetta un parametro di stringa. Il metodo stampa il messaggio e un'immagine di un robot usando righe di testo.

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

Eseguire il progetto e osservare l'output. Provare a eseguire queste variazioni dalla riga di comando per visualizzare risultati diversi:

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- Hello from the bot
```

Tutti gli argomenti dopo il delimitatore `--` vengono passati all'applicazione.

## <a name="package-the-tool"></a>Creare il pacchetto dello strumento

Prima di poter comprimere e distribuire l'applicazione come strumento, è necessario modificare il file di progetto.

1. Aprire il file *Microsoft. botsay. csproj* e aggiungere tre nuovi nodi XML alla fine del nodo `<PropertyGroup>`:

   ```xml
   <PackAsTool>true</PackAsTool>
   <ToolCommandName>botsay</ToolCommandName>
   <PackageOutputPath>./nupkg</PackageOutputPath>
   ```

   `<ToolCommandName>` è un elemento facoltativo che specifica il comando che verrà richiamato dallo strumento dopo l'installazione. Se questo elemento non viene specificato, il nome del comando per lo strumento è il nome del file di progetto senza estensione *csproj* .

   `<PackageOutputPath>` è un elemento facoltativo che determina la posizione in cui verrà generato il pacchetto NuGet. Il pacchetto NuGet è quello usato dal interfaccia della riga di comando di .NET Core per installare lo strumento.

   Il file di progetto ha ora un aspetto simile all'esempio seguente:

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

1. Creare un pacchetto NuGet eseguendo il comando [DotNet Pack](dotnet-pack.md) :

   ```dotnetcli
   dotnet pack
   ```

   Il file *Microsoft. botsay. 1.0.0. nupkg* viene creato nella cartella identificata dal valore `<PackageOutputPath>` dal file *Microsoft. botsay. csproj* , che in questo esempio è la cartella *./nupkg* .
  
   Quando si desidera rilasciare uno strumento pubblicamente, è possibile caricarlo in `https://www.nuget.org`. Quando lo strumento è disponibile in NuGet, gli sviluppatori possono installare lo strumento usando il comando [DotNet tool install](dotnet-tool-install.md) . Per questa esercitazione si installa il pacchetto direttamente dalla cartella *nupkg* locale, pertanto non è necessario caricare il pacchetto in NuGet.

## <a name="troubleshoot"></a>Risolvere problemi

Se viene visualizzato un messaggio di errore mentre si segue l'esercitazione, vedere [risolvere i problemi di utilizzo degli strumenti .NET Core](troubleshoot-usage-issues.md).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata creata un'applicazione console che è stata assemblata come strumento. Per informazioni su come usare lo strumento come strumento globale, passare all'esercitazione successiva.

> [!div class="nextstepaction"]
> [Installare e usare uno strumento globale](global-tools-how-to-use.md)

Se si preferisce, è possibile ignorare l'esercitazione sugli strumenti globali e passare direttamente all'esercitazione relativa agli strumenti locali.

> [!div class="nextstepaction"]
> [Installare e usare uno strumento locale](local-tools-how-to-use.md)
