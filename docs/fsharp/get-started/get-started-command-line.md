---
title: Introduzione agli strumenti F# da riga di comando
description: Informazioni su come creare una semplice soluzione multiprogetto sull' F# uso del interfaccia della riga di comando di .NET Core in qualsiasi sistema operativo (Windows, MacOS o Linux).
ms.date: 03/26/2018
ms.openlocfilehash: aa3ed84660a951eeafc11a00ea3831f587b6d876
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559487"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="46086-103">Introduzione a F# con l'interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="46086-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="46086-104">Questo articolo illustra come iniziare a usare F# qualsiasi sistema operativo (Windows, MacOS o Linux) con la interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="46086-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="46086-105">Viene illustrata la creazione di una soluzione multiprogetto con una libreria di classi chiamata da un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="46086-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="46086-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="46086-106">Prerequisites</span></span>

<span data-ttu-id="46086-107">Per iniziare, è necessario installare la [.NET Core SDK](https://dotnet.microsoft.com/download)più recente.</span><span class="sxs-lookup"><span data-stu-id="46086-107">To begin, you must install the latest [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="46086-108">Questo articolo presuppone che l'utente sappia come usare una riga di comando e avere un editor di testo preferito.</span><span class="sxs-lookup"><span data-stu-id="46086-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="46086-109">Se non è già usato, [Visual Studio Code](get-started-vscode.md) rappresenta un'ottima opzione come editor di testo per F#.</span><span class="sxs-lookup"><span data-stu-id="46086-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="46086-110">Creazione di una soluzione multiprogetto semplice</span><span class="sxs-lookup"><span data-stu-id="46086-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="46086-111">Aprire un prompt dei comandi o un terminale e usare il comando [DotNet New](../../core/tools/dotnet-new.md) per creare un nuovo file di soluzione denominato `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="46086-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```dotnetcli
dotnet new sln -o FSNetCore
```

<span data-ttu-id="46086-112">La struttura di directory seguente viene generata dopo l'esecuzione del comando precedente:</span><span class="sxs-lookup"><span data-stu-id="46086-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="46086-113">Scrivere una libreria di classi</span><span class="sxs-lookup"><span data-stu-id="46086-113">Write a class library</span></span>

<span data-ttu-id="46086-114">Modificare le directory in *FSNetCore*.</span><span class="sxs-lookup"><span data-stu-id="46086-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="46086-115">Usare il comando `dotnet new`, creare un progetto libreria di classi nella cartella **src** denominata Library.</span><span class="sxs-lookup"><span data-stu-id="46086-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```dotnetcli
dotnet new classlib -lang "F#" -o src/Library
```

<span data-ttu-id="46086-116">La struttura di directory seguente viene generata dopo l'esecuzione del comando precedente:</span><span class="sxs-lookup"><span data-stu-id="46086-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="46086-117">Sostituire il contenuto di `Library.fs` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="46086-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="46086-118">Aggiungere il pacchetto NuGet Newtonsoft. JSON al progetto di libreria.</span><span class="sxs-lookup"><span data-stu-id="46086-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="46086-119">Aggiungere il progetto `Library` alla soluzione `FSNetCore` usando il comando [DotNet sln Add](../../core/tools/dotnet-sln.md) :</span><span class="sxs-lookup"><span data-stu-id="46086-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="46086-120">Eseguire `dotnet build` per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="46086-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="46086-121">Le dipendenze non risolte verranno ripristinate durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="46086-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="46086-122">Scrivere un'applicazione console che utilizza la libreria di classi</span><span class="sxs-lookup"><span data-stu-id="46086-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="46086-123">Usare il comando `dotnet new` per creare un'applicazione console nella cartella **src** denominata app.</span><span class="sxs-lookup"><span data-stu-id="46086-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```dotnetcli
dotnet new console -lang "F#" -o src/App
```

<span data-ttu-id="46086-124">La struttura di directory seguente viene generata dopo l'esecuzione del comando precedente:</span><span class="sxs-lookup"><span data-stu-id="46086-124">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="46086-125">Sostituire il contenuto del file `Program.fs` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="46086-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="46086-126">Aggiungere un riferimento al progetto `Library` usando [DotNet Add Reference](../../core/tools/dotnet-add-reference.md).</span><span class="sxs-lookup"><span data-stu-id="46086-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="46086-127">Aggiungere il progetto `App` alla soluzione `FSNetCore` usando il comando `dotnet sln add`:</span><span class="sxs-lookup"><span data-stu-id="46086-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```dotnetcli
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="46086-128">Ripristinare le dipendenze NuGet, `dotnet restore` ed eseguire `dotnet build` per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="46086-128">Restore the NuGet dependencies, `dotnet restore` and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="46086-129">Passare alla directory del progetto console `src/App` ed eseguire il progetto passando `Hello World` come argomenti:</span><span class="sxs-lookup"><span data-stu-id="46086-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```console
cd src/App
dotnet run Hello World
```

<span data-ttu-id="46086-130">I risultati visualizzati sono simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="46086-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="46086-131">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="46086-131">Next steps</span></span>

<span data-ttu-id="46086-132">Successivamente, consultare la [presentazione di F# ](../tour.md) per altre informazioni sulle diverse F# funzionalità.</span><span class="sxs-lookup"><span data-stu-id="46086-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
