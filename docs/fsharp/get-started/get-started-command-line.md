---
title: Introduzione a F# con gli strumenti da riga di comando
description: Informazioni su come creare una soluzione multiprogetto semplice in F# tramite la CLI di .NET Core in qualsiasi sistema operativo (Windows, macOs o Linux).
ms.date: 03/26/2018
ms.openlocfilehash: 8a82970f33c8bbe1b8cdd8fb6499b59b16d3cbf3
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "45673909"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="1548a-103">Introduzione a F# con la CLI di .NET Core</span><span class="sxs-lookup"><span data-stu-id="1548a-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="1548a-104">Questo articolo illustra come è possibile iniziare a usare F# in qualsiasi sistema operativo (Windows, macOS o Linux) con la CLI di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1548a-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="1548a-105">La chiamata passa attraverso la creazione di una soluzione multiprogetto con una libreria di classi che viene chiamata da un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="1548a-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1548a-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1548a-106">Prerequisites</span></span>

<span data-ttu-id="1548a-107">Per iniziare, è necessario installare la versione più recente [.NET Core SDK](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="1548a-107">To begin, you must install the latest [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

<span data-ttu-id="1548a-108">Questo articolo si presuppone che si conosca come usare una riga di comando e hanno un testo preferito editor.</span><span class="sxs-lookup"><span data-stu-id="1548a-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="1548a-109">Se non ne usi già, [Visual Studio Code](get-started-vscode.md) è un'ottima opzione come editor di testo per F#.</span><span class="sxs-lookup"><span data-stu-id="1548a-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="1548a-110">Creare una soluzione multiprogetto semplice</span><span class="sxs-lookup"><span data-stu-id="1548a-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="1548a-111">Aprire un prompt dei comandi/terminale e usare la [dotnet nuove](../../core/tools/dotnet-new.md) comando per creare nuovi file di soluzione denominato `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="1548a-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```console
dotnet new sln -o FSNetCore
```

<span data-ttu-id="1548a-112">La seguente struttura di directory viene generata dopo l'esecuzione del comando precedente:</span><span class="sxs-lookup"><span data-stu-id="1548a-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="1548a-113">Scrivere una libreria di classi</span><span class="sxs-lookup"><span data-stu-id="1548a-113">Write a class library</span></span>

<span data-ttu-id="1548a-114">Passare alla directory *FSNetCore*.</span><span class="sxs-lookup"><span data-stu-id="1548a-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="1548a-115">Usare la `dotnet new` comando, creare un progetto libreria di classi nel **src** cartella denominata libreria.</span><span class="sxs-lookup"><span data-stu-id="1548a-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```console
dotnet new classlib -lang F# -o src/Library
```

<span data-ttu-id="1548a-116">La seguente struttura di directory viene generata dopo l'esecuzione del comando precedente:</span><span class="sxs-lookup"><span data-stu-id="1548a-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="1548a-117">Sostituire il contenuto di `Library.fs` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1548a-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="1548a-118">Aggiungere il pacchetto NuGet newtonsoft. JSON al progetto di libreria.</span><span class="sxs-lookup"><span data-stu-id="1548a-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="1548a-119">Aggiungere il `Library` del progetto per il `FSNetCore` soluzione tramite il [dotnet sln aggiungere](../../core/tools/dotnet-sln.md) comando:</span><span class="sxs-lookup"><span data-stu-id="1548a-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```console
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="1548a-120">Eseguire `dotnet build` per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="1548a-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="1548a-121">Verranno ripristinate le dipendenze non risolte durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="1548a-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="1548a-122">Scrivere un'applicazione console che usa la libreria di classi</span><span class="sxs-lookup"><span data-stu-id="1548a-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="1548a-123">Usare la `dotnet new` comando, creare un'applicazione console nel **src** cartella denominata App.</span><span class="sxs-lookup"><span data-stu-id="1548a-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```console
dotnet new console -lang F# -o src/App
```

<span data-ttu-id="1548a-124">La seguente struttura di directory viene generata dopo l'esecuzione del comando precedente:</span><span class="sxs-lookup"><span data-stu-id="1548a-124">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="1548a-125">Sostituire il contenuto del `Program.fs` file con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1548a-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="1548a-126">Aggiungere un riferimento al `Library` progetto eseguendo [dotnet aggiungere riferimento](../../core/tools/dotnet-add-reference.md).</span><span class="sxs-lookup"><span data-stu-id="1548a-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="1548a-127">Aggiungere il `App` del progetto per il `FSNetCore` soluzione usando il `dotnet sln add` comando:</span><span class="sxs-lookup"><span data-stu-id="1548a-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```console
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="1548a-128">Ripristinare le dipendenze di NuGet `dotnet restore` ([vedere la nota](#dotnet-restore-note)) ed eseguire `dotnet build` per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="1548a-128">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="1548a-129">Passare alla directory il `src/App` progetto console ed eseguire il progetto passando `Hello World` come argomenti:</span><span class="sxs-lookup"><span data-stu-id="1548a-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```console
cd src/App
dotnet run Hello World
```

<span data-ttu-id="1548a-130">È consigliabile vedere i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="1548a-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="1548a-131">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="1548a-131">Next steps</span></span>

<span data-ttu-id="1548a-132">Successivamente, consultare il [Panoramica di F#](../tour.md) per altre informazioni sulle diverse funzionalità di F#.</span><span class="sxs-lookup"><span data-stu-id="1548a-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
