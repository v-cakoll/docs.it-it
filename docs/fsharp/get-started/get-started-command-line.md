---
title: Introduzione agli strumenti F# da riga di comando
description: Informazioni su come creare una semplice soluzione multiprogetto sull' F# uso del interfaccia della riga di comando di .NET Core in qualsiasi sistema operativo (Windows, MacOS o Linux).
ms.date: 03/26/2018
ms.openlocfilehash: 1376b6b5384f380c06a96cdc568ad108de8a6e5f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855832"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Introduzione a F# con l'interfaccia della riga di comando di .NET Core

Questo articolo illustra come iniziare a usare F# qualsiasi sistema operativo (Windows, MacOS o Linux) con la interfaccia della riga di comando di .NET Core. Viene illustrata la creazione di una soluzione multiprogetto con una libreria di classi chiamata da un'applicazione console.

## <a name="prerequisites"></a>Prerequisiti

Per iniziare, è necessario installare la [.NET Core SDK](https://dotnet.microsoft.com/download)più recente.

Questo articolo presuppone che l'utente sappia come usare una riga di comando e avere un editor di testo preferito. Se non è già usato, [Visual Studio Code](get-started-vscode.md) rappresenta un'ottima opzione come editor di testo per F#.

## <a name="build-a-simple-multi-project-solution"></a>Creazione di una soluzione multiprogetto semplice

Aprire un prompt dei comandi o un terminale e usare il comando [DotNet New](../../core/tools/dotnet-new.md) per creare un nuovo `FSNetCore`file di soluzione denominato:

```console
dotnet new sln -o FSNetCore
```

La struttura di directory seguente viene generata dopo l'esecuzione del comando precedente:

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Scrivere una libreria di classi

Modificare le directory in *FSNetCore*.

Usare il `dotnet new` comando, creare un progetto libreria di classi nella cartella **src** denominata Library.

```console
dotnet new classlib -lang F# -o src/Library
```

La struttura di directory seguente viene generata dopo l'esecuzione del comando precedente:

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

Aggiungere il pacchetto NuGet Newtonsoft. JSON al progetto di libreria.

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Aggiungere il `Library` progetto `FSNetCore` alla soluzione usando il comando [DotNet sln Add](../../core/tools/dotnet-sln.md) :

```console
dotnet sln add src/Library/Library.fsproj
```

Eseguire `dotnet build` per compilare il progetto. Le dipendenze non risolte verranno ripristinate durante la compilazione.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Scrivere un'applicazione console che utilizza la libreria di classi

Usare il `dotnet new` comando per creare un'applicazione console nella cartella **src** denominata app.

```console
dotnet new console -lang F# -o src/App
```

La struttura di directory seguente viene generata dopo l'esecuzione del comando precedente:

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

Aggiungere un riferimento al `Library` progetto usando [DotNet Add Reference](../../core/tools/dotnet-add-reference.md).

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Aggiungere il `App` progetto `FSNetCore` alla soluzione usando il `dotnet sln add` comando:

```console
dotnet sln add src/App/App.fsproj
```

Ripristinare le dipendenze `dotnet restore` NuGet ed eseguire `dotnet build` per compilare il progetto.

Passare alla directory del `src/App` progetto console ed eseguire il progetto passando `Hello World` come argomenti:

```console
cd src/App
dotnet run Hello World
```

Dovrebbero essere visualizzati i risultati seguenti:

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>Passaggi successivi

Successivamente, consultare la [presentazione di F# ](../tour.md) per altre informazioni sulle diverse F# funzionalità.
