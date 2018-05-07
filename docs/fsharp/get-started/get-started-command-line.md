---
title: 'Introduzione a F # con gli strumenti da riga di comando'
description: "Informazioni su come compilare una soluzione multiprogetto semplice in F # utilizzando l'interfaccia CLI di .NET Core in qualsiasi sistema operativo (Windows, macOs o Linux)."
ms.date: 03/26/2018
ms.openlocfilehash: 35ec2313742a0b14c92f3de2662a16aff389b214
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Introduzione a F # con l'interfaccia CLI di .NET Core

Questo articolo descrive il modo in cui è possibile iniziare a usare F # in qualsiasi sistema operativo (Windows, macOS o Linux) con l'interfaccia CLI dei componenti di base di .NET. Passano attraverso la creazione di una soluzione multiprogetto con una libreria di classi che viene chiamata da un'applicazione console.

## <a name="prerequisites"></a>Prerequisiti

Per iniziare, è necessario installare il [SDK 1.0 o versione successiva di .NET Core](https://www.microsoft.com/net/download/). Non è necessario disinstallare una versione precedente di .NET Core SDK, in quanto supporta installazioni side-by-side.

Questo articolo si presuppone che si conosce l'utilizzo di una riga di comando e un testo preferito editor. Se non già utilizzarla, [codice di Visual Studio](https://code.visualstudio.com) è un'opzione utilissima come editor di testo per F #. Per ottenere ancor più straordinaria funzionalità quali IntelliSense, una migliore evidenziazione della sintassi e altro ancora, è possibile scaricare il [Ionide estensione](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).

## <a name="build-a-simple-multi-project-solution"></a>Compilare una soluzione multiprogetto semplice

Aprire un prompt dei comandi/terminale e usare la [dotnet nuove](../../core/tools/dotnet-new.md) comando per creare nuovi file di soluzione denominato `FSNetCore`:

```
dotnet new sln -o FSNetCore
```

La seguente struttura di directory viene generata dopo l'esecuzione del comando precedente:

```
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Scrivere una libreria di classi

Passare alla directory *FSNetCore*.

Usare la `dotnet new` comando, creare un progetto libreria di classi nel **src** cartella libreria.

```
dotnet new lib -lang F# -o src/Library
```

La seguente struttura di directory viene generata dopo l'esecuzione del comando precedente:

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Sostituire il contenuto di `Library.fs` con il codice seguente:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

Aggiungere il pacchetto NuGet newtonsoft. JSON per il progetto di libreria.

```
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Aggiungere il `Library` del progetto per il `FSNetCore` soluzione usando la [sln dotnet aggiungere](../../core/tools/dotnet-sln.md) comando:

```
dotnet sln add src/Library/Library.fsproj
```

Ripristinare le dipendenze di NuGet usando il `dotnet restore` comando ([vedere la nota](#dotnet-restore-note)) ed eseguire `dotnet build` per compilare il progetto.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Scrivere un'applicazione console che utilizza la libreria di classi

Usare la `dotnet new` comando, creare un'applicazione console nel **src** cartella denominato App.

```
dotnet new console -lang F# -o src/App
```

La seguente struttura di directory viene generata dopo l'esecuzione del comando precedente:

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        ├── App
        │   ├── App.fsproj
        │   ├── Program.fs
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Sostituire il contenuto del `Program.fs` file con il codice seguente:

```fsharp
open System
open Library

[<EntryPoint>]
let main argv =
    printfn "Nice command-line arguments! Here's what JSON.NET has to say about them:"

    argv
    |> Array.map getJsonNetJson
    |> Array.iter (printfn "%s")

    0 // return an integer exit code
```

Aggiungere un riferimento per il `Library` progetto che utilizza [dotnet aggiungere riferimento](../../core/tools/dotnet-add-reference.md).

```
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Aggiungere il `App` progetto per il `FSNetCore` soluzione usando il `dotnet sln add` comando:

```
dotnet sln add src/App/App.fsproj
```

Ripristinare le dipendenze di NuGet `dotnet restore` ([vedere la nota](#dotnet-restore-note)) ed eseguire `dotnet build` per compilare il progetto.

Spostarsi nella directory per il `src/App` console progetto ed eseguire il progetto passando `Hello World` come argomenti:

```
cd src/App
dotnet run Hello World
```

Verrà visualizzato i risultati seguenti:

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]