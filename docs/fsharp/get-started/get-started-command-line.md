---
title: 'Introduzione a F # con gli strumenti da riga di comando'
description: "Informazioni su come compilare una soluzione multiprogetto semplice in F # utilizzando l'interfaccia CLI di .NET Core in qualsiasi sistema operativo (Windows, macOs o Linux)."
author: cartermp
ms.author: phcart
ms.date: 03/26/2018
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 767385be605d863644db563a2e86a41ca80527c4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="fd6f4-103">Introduzione a F # con l'interfaccia CLI di .NET Core</span><span class="sxs-lookup"><span data-stu-id="fd6f4-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="fd6f4-104">Questo articolo descrive il modo in cui è possibile iniziare a usare F # in qualsiasi sistema operativo (Windows, macOS o Linux) con l'interfaccia CLI dei componenti di base di .NET.</span><span class="sxs-lookup"><span data-stu-id="fd6f4-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="fd6f4-105">Passano attraverso la creazione di una soluzione multiprogetto con una libreria di classi che viene chiamata da un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="fd6f4-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fd6f4-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="fd6f4-106">Prerequisites</span></span>

<span data-ttu-id="fd6f4-107">Per iniziare, è necessario installare il [SDK 1.0 o versione successiva di .NET Core](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="fd6f4-107">To begin, you must install the [.NET Core SDK 1.0 or later](https://www.microsoft.com/net/download/).</span></span> <span data-ttu-id="fd6f4-108">Non è necessario disinstallare una versione precedente di .NET Core SDK, in quanto supporta installazioni side-by-side.</span><span class="sxs-lookup"><span data-stu-id="fd6f4-108">There is no need to uninstall a previous version of the .NET Core SDK, as it supports side-by-side installations.</span></span>

<span data-ttu-id="fd6f4-109">Questo articolo si presuppone che si conosce l'utilizzo di una riga di comando e un testo preferito editor.</span><span class="sxs-lookup"><span data-stu-id="fd6f4-109">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="fd6f4-110">Se non già utilizzarla, [codice di Visual Studio](https://code.visualstudio.com) è un'opzione utilissima come editor di testo per F #.</span><span class="sxs-lookup"><span data-stu-id="fd6f4-110">If you don't already use it, [Visual Studio Code](https://code.visualstudio.com) is a great option as a text editor for F#.</span></span> <span data-ttu-id="fd6f4-111">Per ottenere ancor più straordinaria funzionalità quali IntelliSense, una migliore evidenziazione della sintassi e altro ancora, è possibile scaricare il [Ionide estensione](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="fd6f4-111">To get awesome features like IntelliSense, better syntax highlighting, and more, you can download the [Ionide Extension](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="fd6f4-112">Compilare una soluzione multiprogetto semplice</span><span class="sxs-lookup"><span data-stu-id="fd6f4-112">Build a simple multi-project solution</span></span>

<span data-ttu-id="fd6f4-113">Aprire un prompt dei comandi/terminale e usare la [dotnet nuove](../../core/tools/dotnet-new.md) comando per creare nuovi file di soluzione denominato `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="fd6f4-113">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```
dotnet new sln -o FSNetCore
```

<span data-ttu-id="fd6f4-114">La seguente struttura di directory viene generata dopo l'esecuzione del comando precedente:</span><span class="sxs-lookup"><span data-stu-id="fd6f4-114">The following directory structure is produced after running the previous command:</span></span>

```
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="fd6f4-115">Scrivere una libreria di classi</span><span class="sxs-lookup"><span data-stu-id="fd6f4-115">Write a class library</span></span>

<span data-ttu-id="fd6f4-116">Passare alla directory *FSNetCore*.</span><span class="sxs-lookup"><span data-stu-id="fd6f4-116">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="fd6f4-117">Usare la `dotnet new` comando, creare un progetto libreria di classi nel **src** cartella libreria.</span><span class="sxs-lookup"><span data-stu-id="fd6f4-117">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```
dotnet new lib -lang F# -o src/Library
```

<span data-ttu-id="fd6f4-118">La seguente struttura di directory viene generata dopo l'esecuzione del comando precedente:</span><span class="sxs-lookup"><span data-stu-id="fd6f4-118">The following directory structure is produced after running the previous command:</span></span>

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="fd6f4-119">Sostituire il contenuto di `Library.fs` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fd6f4-119">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="fd6f4-120">Aggiungere il pacchetto NuGet newtonsoft. JSON per il progetto di libreria.</span><span class="sxs-lookup"><span data-stu-id="fd6f4-120">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="fd6f4-121">Aggiungere il `Library` del progetto per il `FSNetCore` soluzione usando la [sln dotnet aggiungere](../../core/tools/dotnet-sln.md) comando:</span><span class="sxs-lookup"><span data-stu-id="fd6f4-121">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="fd6f4-122">Ripristinare le dipendenze di NuGet usando il `dotnet restore` comando ([vedere la nota](#dotnet-restore-note)) ed eseguire `dotnet build` per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="fd6f4-122">Restore the NuGet dependencies using the `dotnet restore` command ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="fd6f4-123">Scrivere un'applicazione console che utilizza la libreria di classi</span><span class="sxs-lookup"><span data-stu-id="fd6f4-123">Write a console application that consumes the class library</span></span>

<span data-ttu-id="fd6f4-124">Usare la `dotnet new` comando, creare un'applicazione console nel **src** cartella denominato App.</span><span class="sxs-lookup"><span data-stu-id="fd6f4-124">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```
dotnet new console -lang F# -o src/App
```

<span data-ttu-id="fd6f4-125">La seguente struttura di directory viene generata dopo l'esecuzione del comando precedente:</span><span class="sxs-lookup"><span data-stu-id="fd6f4-125">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="fd6f4-126">Sostituire il contenuto del `Program.fs` file con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fd6f4-126">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="fd6f4-127">Aggiungere un riferimento per il `Library` progetto che utilizza [dotnet aggiungere riferimento](../../core/tools/dotnet-add-reference.md).</span><span class="sxs-lookup"><span data-stu-id="fd6f4-127">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="fd6f4-128">Aggiungere il `App` progetto per il `FSNetCore` soluzione usando il `dotnet sln add` comando:</span><span class="sxs-lookup"><span data-stu-id="fd6f4-128">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="fd6f4-129">Ripristinare le dipendenze di NuGet `dotnet restore` ([vedere la nota](#dotnet-restore-note)) ed eseguire `dotnet build` per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="fd6f4-129">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="fd6f4-130">Spostarsi nella directory per il `src/App` console progetto ed eseguire il progetto passando `Hello World` come argomenti:</span><span class="sxs-lookup"><span data-stu-id="fd6f4-130">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```
cd src/App
dotnet run Hello World
```

<span data-ttu-id="fd6f4-131">Verrà visualizzato i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd6f4-131">You should see the following results:</span></span>

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]