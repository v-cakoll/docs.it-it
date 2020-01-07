---
title: Come creare uno strumento globale .NET Core
description: Descrive come creare uno strumento globale. Lo strumento globale è un'applicazione console installata tramite l'interfaccia della riga di comando di .NET Core.
author: Thraka
ms.author: adegeo
ms.date: 08/22/2018
ms.openlocfilehash: 1daecf7234f02a5fe0dcf25cf7edbb0af327b8c1
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75343515"
---
# <a name="create-a-net-core-global-tool-using-the-net-core-cli"></a>Creare uno strumento globale Core .NET tramite l'interfaccia della riga di comando di .NET Core

Questo articolo illustra come creare uno strumento globale .NET Core e inserirlo in un pacchetto. L'interfaccia della riga di comando di .NET Core consente di creare un'applicazione console come uno strumento globale, che altri utenti possono facilmente installare ed eseguire. Gli strumenti globali .NET Core sono pacchetti NuGet installati dall'interfaccia della riga di comando di .NET Core. Per altre informazioni sugli strumenti globali, vedere [Panoramica degli strumenti globali .NET Core](global-tools.md).

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="create-a-project"></a>Creare un progetto

In questo articolo viene usata l'interfaccia della riga di comando di .NET Core per creare e gestire un progetto.

Lo strumento di esempio sarà un'applicazione console che genera un bot ASCII e stampa un messaggio. Creare innanzitutto una nuova applicazione console .NET Core.

```dotnetcli
dotnet new console -o botsay
```

Passare alla directory `botsay` creata dal comando precedente.

## <a name="add-the-code"></a>Aggiunta del codice

Aprire il file `Program.cs` con un editor di testo, ad esempio `vim` oppure [Visual Studio Code](https://code.visualstudio.com/).

Aggiungere la direttiva `using` seguente all'inizio del file, in modo da abbreviare il codice per visualizzare le informazioni sulla versione dell'applicazione.

```csharp
using System.Reflection;
```

Spostarsi quindi verso il basso fino al metodo `Main`. Sostituire il metodo con il codice seguente per elaborare gli argomenti della riga di comando per l'applicazione. Se non si passa alcun argomento, viene visualizzato un breve messaggio della Guida. In caso contrario, tutti gli argomenti vengono trasformati in una stringa e stampati con il bot.

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

### <a name="create-the-bot"></a>Creare il bot

Aggiungere quindi un nuovo metodo denominato `ShowBot` che accetta un parametro di stringa. Questo metodo stampa il messaggio e il bot ASCII. Il codice del bot ASCII è stato ricavato dall'esempio [dotnetbot](https://github.com/dotnet/core/blob/master/samples/dotnetsay/Program.cs).

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

### <a name="test-the-tool"></a>Testare lo strumento

Eseguire il progetto e osservare l'output. Provare a eseguire queste variazioni dalla riga di comando per visualizzare risultati diversi:

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- hello from the bot
```

Tutti gli argomenti dopo il delimitatore `--` vengono passati all'applicazione.

## <a name="set-up-the-global-tool"></a>Configurare lo strumento globale

Prima di inserire in un pacchetto e distribuire l'applicazione come uno strumento globale, è necessario modificare il file di progetto. Aprire il file `botsay.csproj` e aggiungere tre nuovi nodi XML al nodo `<Project><PropertyGroup>`:

- `<PackAsTool>`\
[OBBLIGATORIO] Indica che verrà creato un pacchetto dell'applicazione per l'installazione come strumento globale.

- `<ToolCommandName>`\
[FACOLTATIVO] Nome alternativo per lo strumento. Se non viene specificato, il nome del comando per lo strumento verrà assegnato in base al file di progetto. È possibile includere più strumenti in un pacchetto, scegliendo un nome descrittivo e univoco che consenta di differenziarli dagli altri strumenti contenuti nello stesso pacchetto.

- `<PackageOutputPath>`\
[FACOLTATIVO] Percorso in cui verrà creato il pacchetto NuGet. Il pacchetto NuGet viene usato dagli strumenti globali dell'interfaccia della riga di comando di .NET Core per installare lo strumento.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>

    <PackAsTool>true</PackAsTool>
    <ToolCommandName>botsay</ToolCommandName>
    <PackageOutputPath>./nupkg</PackageOutputPath>

  </PropertyGroup>

</Project>
```

Anche se `<PackageOutputPath>` è facoltativo, verrà usato in questo esempio. Assicurarsi di impostarlo: `<PackageOutputPath>./nupkg</PackageOutputPath>`.

Creare quindi un pacchetto NuGet per l'applicazione.

```dotnetcli
dotnet pack
```

Il file `botsay.1.0.0.nupkg` viene creato nella cartella identificata dal valore XML `<PackageOutputPath>` dal file `botsay.csproj`, ovvero in questo esempio la cartella `./nupkg`. Questo ne rende più semplice l'installazione e il test. Per rilasciare pubblicamente uno strumento, caricarlo in <https://www.nuget.org>. Quando lo strumento è disponibile in NuGet, gli sviluppatori possono eseguire un'installazione dello strumento a livello di utente usando l'opzione `--global` del comando [DotNet tool install](dotnet-tool-install.md) .

Dopo aver creato un pacchetto, installare lo strumento da tale pacchetto:

```dotnetcli
dotnet tool install --global --add-source ./nupkg botsay
```

Il parametro `--add-source` indica all'interfaccia della riga di comando di .NET Core di usare temporaneamente la cartella `./nupkg` (ovvero, la cartella `<PackageOutputPath>` che è stata specificata) come feed di origine aggiuntivo per i pacchetti NuGet. Per altre informazioni sull'installazione degli strumenti globali, vedere [Panoramica degli strumenti globali .NET Core](global-tools.md).

Se l'installazione ha esito positivo, viene visualizzato un messaggio che mostra il comando usato per chiamare lo strumento e la versione installata, simile all'esempio seguente:

```output
You can invoke the tool using the following command: botsay
Tool 'botsay' (version '1.0.0') was successfully installed.
```

A questo punto, dovrebbe essere possibile digitare `botsay` e ottenere una risposta dallo strumento.

> [!NOTE]
> Se l'installazione ha avuto esito positivo, ma non è possibile usare il comando `botsay`, potrebbe essere necessario aprire un nuovo terminale per aggiornare il percorso.

## <a name="remove-the-tool"></a>Rimuovere lo strumento

Dopo aver completato la sperimentazione con lo strumento, è possibile rimuoverlo con il comando seguente:

```dotnetcli
dotnet tool uninstall -g botsay
```
