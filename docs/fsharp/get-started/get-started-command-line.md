---
title: 'Introduzione a F # con gli strumenti da riga di comando'
description: "Informazioni su come utilizzare F # su qualsiasi sistema operativo (MacOS Windows, Linux) con l'interfaccia CLI di più piattaforme .NET Core."
keywords: visual f#, f#, programmazione funzionale, .NET, .NET Core
author: cartermp
ms.author: phcart
ms.date: 06/14/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 615db1ec-6ef3-4de2-bae6-4586affa9771
ms.openlocfilehash: 4820a8a306bd478429b497a8b7c70ff170c1c655
ms.sourcegitcommit: d095094e942eedf09530ea5636fbaf9029853027
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2017
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="7c79d-104">Introduzione a F # con l'interfaccia CLI di .NET Core</span><span class="sxs-lookup"><span data-stu-id="7c79d-104">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="7c79d-105">Questo articolo descrive come è possibile iniziare in qualsiasi sistema operativo (Windows, Mac OS o Linux) con F # con .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="7c79d-105">This article covers how you can get started on any OS (Windows, macOS, or Linux) by using F# with the .NET Core CLI.</span></span> <span data-ttu-id="7c79d-106">Analizzerà la creazione di una soluzione multiprogetto con una libreria di classi che viene chiamato da un'applicazione Console.</span><span class="sxs-lookup"><span data-stu-id="7c79d-106">It will go through building a multi-project solution with a Class Library that is called by a Console Application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7c79d-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7c79d-107">Prerequisites</span></span>

<span data-ttu-id="7c79d-108">Per iniziare, è necessario installare il [SDK 1.0 o versione successiva di .NET Core](https://dot.net/core).</span><span class="sxs-lookup"><span data-stu-id="7c79d-108">To begin, you must install the [.NET Core SDK 1.0 or later](https://dot.net/core).</span></span> <span data-ttu-id="7c79d-109">Non è necessario disinstallare una versione precedente di .NET Core SDK, in quanto supporta installazioni side-by-side.</span><span class="sxs-lookup"><span data-stu-id="7c79d-109">There is no need to uninstall a previous version of the .NET Core SDK, as it supports side-by-side installations.</span></span>

<span data-ttu-id="7c79d-110">Questo articolo si presuppone che si conosce l'utilizzo di una riga di comando e un testo preferito editor.</span><span class="sxs-lookup"><span data-stu-id="7c79d-110">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="7c79d-111">Se non già utilizzarla, [codice di Visual Studio](https://code.visualstudio.com) è un'opzione utilissima come editor di testo per F #.</span><span class="sxs-lookup"><span data-stu-id="7c79d-111">If you don't already use it, [Visual Studio Code](https://code.visualstudio.com) is a great option as a text editor for F#.</span></span> <span data-ttu-id="7c79d-112">Per ottenere ancor più straordinaria funzionalità quali IntelliSense, una migliore evidenziazione della sintassi e altro ancora, è possibile scaricare il [Ionide estensione](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="7c79d-112">To get awesome features like IntelliSense, better syntax highlighting, and more, you can download the [Ionide Extension](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span>

## <a name="building-a-simple-multi-project-solution"></a><span data-ttu-id="7c79d-113">Creazione di una soluzione multiprogetto semplice</span><span class="sxs-lookup"><span data-stu-id="7c79d-113">Building a Simple Multi-project Solution</span></span>

<span data-ttu-id="7c79d-114">Aprire un prompt dei comandi/terminal e utilizzare il `dotnet new` comando per creare nuovi file di soluzione denominato `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="7c79d-114">Open a command prompt/terminal and use the `dotnet new` command to create new solution file called `FSNetCore`:</span></span>

```
dotnet new sln -o FSNetCore
```

<span data-ttu-id="7c79d-115">La struttura di directory riportata di seguito viene generata come risultato il completamento del comando:</span><span class="sxs-lookup"><span data-stu-id="7c79d-115">The folowing directory structure is produced as a result of the command completing:</span></span>

```
FSNetCore
    ├── FSNetCore.sln
```

<span data-ttu-id="7c79d-116">Passare alla directory *FSNetCore* e iniziare ad aggiungere progetti nella cartella della soluzione.</span><span class="sxs-lookup"><span data-stu-id="7c79d-116">Change directories to *FSNetCore* and start adding projects to the solution folder.</span></span>
 
### <a name="writing-a-class-library"></a><span data-ttu-id="7c79d-117">Scrittura di una libreria di classi</span><span class="sxs-lookup"><span data-stu-id="7c79d-117">Writing a Class library</span></span>

<span data-ttu-id="7c79d-118">Utilizzare il `dotnet new` comando, creare un progetto libreria di classi nel **src** cartella libreria.</span><span class="sxs-lookup"><span data-stu-id="7c79d-118">Use the `dotnet new` command, create a Class Library project in the **src** folder named Library.</span></span> 

```bash
dotnet new lib -lang F# -o src/Library 
```

<span data-ttu-id="7c79d-119">La seguente struttura di directory è stata generata come risultato il completamento del comando:</span><span class="sxs-lookup"><span data-stu-id="7c79d-119">The following directory structure is produced as a result of the command completing:</span></span>

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="7c79d-120">Sostituire il contenuto di `Library.fs` con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7c79d-120">Replace the contents of `Library.fs` with the following:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value = 
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value  (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="7c79d-121">Aggiungere il pacchetto NuGet newtonsoft. JSON per il progetto di libreria.</span><span class="sxs-lookup"><span data-stu-id="7c79d-121">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```bash
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="7c79d-122">Aggiungere il `Library` progetto per il `FSNetCore` soluzione usando il `dotnet sln add` comando:</span><span class="sxs-lookup"><span data-stu-id="7c79d-122">Add the `Library` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```bash
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="7c79d-123">Ripristinare le dipendenze di NuGet `dotnet restore` ([vedere la nota](#dotnet-restore-note)) ed eseguire `dotnet build` per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="7c79d-123">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

### <a name="writing-a-console-application-which-consumes-the-class-library"></a><span data-ttu-id="7c79d-124">Scrittura di un'applicazione Console che utilizza la libreria di classi</span><span class="sxs-lookup"><span data-stu-id="7c79d-124">Writing a Console Application which Consumes the Class Library</span></span>

<span data-ttu-id="7c79d-125">Utilizzare il `dotnet new` comando, creare un'applicazione Console nel **src** cartella denominato App.</span><span class="sxs-lookup"><span data-stu-id="7c79d-125">Use the `dotnet new` command, create a Console app in the **src** folder named App.</span></span> 

```bash
dotnet new console -lang F# -o src/App 
```

<span data-ttu-id="7c79d-126">La seguente struttura di directory è stata generata come risultato il completamento del comando:</span><span class="sxs-lookup"><span data-stu-id="7c79d-126">The following directory structure is produced as a result of the command completing:</span></span>

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

<span data-ttu-id="7c79d-127">Modifica `Program.fs` per:</span><span class="sxs-lookup"><span data-stu-id="7c79d-127">Change `Program.fs` to:</span></span>

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

<span data-ttu-id="7c79d-128">Aggiungere un riferimento di `Library` progetto utilizzando `dotnet add reference`.</span><span class="sxs-lookup"><span data-stu-id="7c79d-128">Add a reference to the `Library` project using `dotnet add reference`.</span></span>

```bash
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="7c79d-129">Aggiungere il `App` progetto per il `FSNetCore` soluzione usando il `dotnet sln add` comando:</span><span class="sxs-lookup"><span data-stu-id="7c79d-129">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```bash
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="7c79d-130">Ripristinare le dipendenze di NuGet `dotnet restore` ([vedere la nota](#dotnet-restore-note)) ed eseguire `dotnet build` per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="7c79d-130">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="7c79d-131">Passare alla directory di `src/App` progetto console ed eseguire il progetto passando `Hello World` come argomenti.</span><span class="sxs-lookup"><span data-stu-id="7c79d-131">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments.</span></span>

```bash
cd src/App
dotnet run Hello World
``` 

<span data-ttu-id="7c79d-132">Verrà visualizzato i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c79d-132">You should see the following results:</span></span>

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```
<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
