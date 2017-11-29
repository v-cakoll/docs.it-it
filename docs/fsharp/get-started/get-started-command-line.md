---
title: 'Introduzione a F # con gli strumenti da riga di comando'
description: "Informazioni sull'utilizzo di F # con più piattaforme .NET Core CLI."
keywords: visual f#, f#, programmazione funzionale, .NET, .NET Core
author: cartermp
ms.author: phcart
ms.date: 06/14/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 615db1ec-6ef3-4de2-bae6-4586affa9771
ms.openlocfilehash: a23d4861ce599f20f37ecd0564a0187e7b9b739f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Introduzione a F # con l'interfaccia CLI di .NET Core

Questo articolo descrive come è possibile iniziare con l'utilizzo di F # su .NET Core. Analizzerà la creazione di una soluzione multiprogetto con una libreria di classi che viene chiamato da un'applicazione Console.

## <a name="prerequisites"></a>Prerequisiti

Per iniziare, è necessario installare il [SDK 1.0 o versione successiva di .NET Core](https://dot.net/core). Non è necessario disinstallare una versione precedente di .NET Core SDK, in quanto supporta installazioni side-by-side.

Questo articolo si presuppone che si conosce l'utilizzo di una riga di comando e un testo preferito editor. Se non già utilizzarla, [codice di Visual Studio](https://code.visualstudio.com) è un'opzione utilissima come editor di testo per F #. Per ottenere ancor più straordinaria funzionalità quali IntelliSense, una migliore evidenziazione della sintassi e altro ancora, è possibile scaricare il [Ionide estensione](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).

## <a name="building-a-simple-multi-project-solution"></a>Creazione di una soluzione multiprogetto semplice

Aprire un prompt dei comandi/terminal e utilizzare il `dotnet new` comando per creare nuovi file di soluzione denominato `FSNetCore`:

```
dotnet new sln -o FSNetCore
```

La struttura di directory riportata di seguito viene generata come risultato il completamento del comando:

```
FSNetCore
    ├── FSNetCore.sln
```

Passare alla directory *FSNetCore* e iniziare ad aggiungere progetti nella cartella della soluzione.
 
### <a name="writing-a-class-library"></a>Scrittura di una libreria di classi

Utilizzare il `dotnet new` comando, creare un progetto libreria di classi nel **src** cartella libreria. 

```bash
dotnet new lib -lang F# -o src/Library 
```

La seguente struttura di directory è stata generata come risultato il completamento del comando:

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Sostituire il contenuto di `Library.fs` con quanto segue:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value = 
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value  (JsonConvert.SerializeObject(value))
```

Aggiungere il pacchetto NuGet newtonsoft. JSON per il progetto di libreria.

```bash
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Aggiungere il `Library` progetto per il `FSNetCore` soluzione usando il `dotnet sln add` comando:

```bash
dotnet sln add src/Library/Library.fsproj
```

Ripristinare le dipendenze di NuGet `dotnet restore` ([vedere la nota](#dotnet-restore-note)) ed eseguire `dotnet build` per compilare il progetto.

### <a name="writing-a-console-application-which-consumes-the-class-library"></a>Scrittura di un'applicazione Console che utilizza la libreria di classi

Utilizzare il `dotnet new` comando, creare un'applicazione Console nel **src** cartella denominato App. 

```bash
dotnet new console -lang F# -o src/App 
```

La seguente struttura di directory è stata generata come risultato il completamento del comando:

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

Modifica `Program.fs` per:

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

Aggiungere un riferimento di `Library` progetto utilizzando `dotnet add reference`.

```bash
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Aggiungere il `App` progetto per il `FSNetCore` soluzione usando il `dotnet sln add` comando:

```bash
dotnet sln add src/App/App.fsproj
```

Ripristinare le dipendenze di NuGet `dotnet restore` ([vedere la nota](#dotnet-restore-note)) ed eseguire `dotnet build` per compilare il progetto.

Passare alla directory di `src/App` progetto console ed eseguire il progetto passando `Hello World` come argomenti.

```bash
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