---
title: 'Introduzione a F # con gli strumenti da riga di comando'
description: 'Informazioni su come creare una soluzione multiprogetto semplice in F # tramite la CLI di .NET Core in qualsiasi sistema operativo (Windows, macOs o Linux).'
ms.date: 03/26/2018
ms.openlocfilehash: 6cdb2b42781dba6ba00c03b20e6a76d033e03063
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2018
ms.locfileid: "37875014"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Introduzione a F # con la CLI di .NET Core

Questo articolo illustra come è possibile iniziare a usare F # in qualsiasi sistema operativo (Windows, macOS o Linux) con la CLI di .NET Core. La chiamata passa attraverso la creazione di una soluzione multiprogetto con una libreria di classi che viene chiamata da un'applicazione console.

## <a name="prerequisites"></a>Prerequisiti

Per iniziare, è necessario installare la versione più recente [.NET Core SDK](https://www.microsoft.com/net/download/).

Questo articolo si presuppone che si conosca come usare una riga di comando e hanno un testo preferito editor. Se non ne usi già, [Visual Studio Code](get-started-vscode.md) è un'ottima opzione come editor di testo per F #.

## <a name="build-a-simple-multi-project-solution"></a>Creare una soluzione multiprogetto semplice

Aprire un prompt dei comandi/terminale e usare la [dotnet nuove](../../core/tools/dotnet-new.md) comando per creare nuovi file di soluzione denominato `FSNetCore`:

```console
dotnet new sln -o FSNetCore
```

La seguente struttura di directory viene generata dopo l'esecuzione del comando precedente:

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Scrivere una libreria di classi

Passare alla directory *FSNetCore*.

Usare la `dotnet new` comando, creare un progetto libreria di classi nel **src** cartella denominata libreria.

```console
dotnet new lib -lang F# -o src/Library
```

La seguente struttura di directory viene generata dopo l'esecuzione del comando precedente:

```console
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

Aggiungere il pacchetto NuGet newtonsoft. JSON al progetto di libreria.

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Aggiungere il `Library` del progetto per il `FSNetCore` soluzione tramite il [dotnet sln aggiungere](../../core/tools/dotnet-sln.md) comando:

```console
dotnet sln add src/Library/Library.fsproj
```

Eseguire `dotnet build` per compilare il progetto. Verranno ripristinate le dipendenze non risolte durante la compilazione.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Scrivere un'applicazione console che usa la libreria di classi

Usare la `dotnet new` comando, creare un'applicazione console nel **src** cartella denominata App.

```console
dotnet new console -lang F# -o src/App
```

La seguente struttura di directory viene generata dopo l'esecuzione del comando precedente:

```console
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

Aggiungere un riferimento al `Library` progetto eseguendo [dotnet aggiungere riferimento](../../core/tools/dotnet-add-reference.md).

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Aggiungere il `App` del progetto per il `FSNetCore` soluzione usando il `dotnet sln add` comando:

```console
dotnet sln add src/App/App.fsproj
```

Ripristinare le dipendenze di NuGet `dotnet restore` ([vedere la nota](#dotnet-restore-note)) ed eseguire `dotnet build` per compilare il progetto.

Passare alla directory il `src/App` progetto console ed eseguire il progetto passando `Hello World` come argomenti:

```console
cd src/App
dotnet run Hello World
```

È consigliabile vedere i risultati seguenti:

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>Passaggi successivi

Successivamente, consultare il [Panoramica di F #](../tour.md) per altre informazioni sulle diverse funzionalità di F #.