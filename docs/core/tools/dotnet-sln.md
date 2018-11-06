---
title: Comando dotnet sln - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-sln rappresenta un'opzione comoda per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.
author: mairaw
ms.author: mairaw
ms.date: 06/13/2018
ms.openlocfilehash: 2651e8e14ad43f41354b8165179f95f65e732f4c
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "49121221"
---
# <a name="dotnet-sln"></a><span data-ttu-id="a4968-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="a4968-103">dotnet sln</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="a4968-104">nome</span><span class="sxs-lookup"><span data-stu-id="a4968-104">Name</span></span>

<span data-ttu-id="a4968-105">`dotnet sln`: consente di modificare un file di soluzione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a4968-105">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a4968-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a4968-106">Synopsis</span></span>

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="a4968-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a4968-107">Description</span></span>

<span data-ttu-id="a4968-108">Il comando `dotnet sln` offre un modo pratico per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="a4968-108">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

<span data-ttu-id="a4968-109">Per usare il comando `dotnet sln`, il file di soluzione deve essere già esistente.</span><span class="sxs-lookup"><span data-stu-id="a4968-109">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="a4968-110">Se è necessario crearne uno, usare il comando [dotnet new](dotnet-new.md), come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a4968-110">If you need to create one, use the [dotnet new](dotnet-new.md) command, like in the following example:</span></span>

```
dotnet new sln
```

## <a name="commands"></a><span data-ttu-id="a4968-111">Comandi:</span><span class="sxs-lookup"><span data-stu-id="a4968-111">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="a4968-112">Aggiunge uno o più progetti più al file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="a4968-112">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="a4968-113">I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei terminali basati su Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="a4968-113">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="a4968-114">Rimuove uno o più progetti dal file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="a4968-114">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="a4968-115">I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei terminali basati su Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="a4968-115">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="a4968-116">Elenca tutti i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="a4968-116">Lists all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="a4968-117">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a4968-117">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="a4968-118">File di soluzione da usare.</span><span class="sxs-lookup"><span data-stu-id="a4968-118">Solution file to use.</span></span> <span data-ttu-id="a4968-119">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a4968-119">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="a4968-120">Se sono presenti più file di soluzione nella directory, è necessario specificarne uno.</span><span class="sxs-lookup"><span data-stu-id="a4968-120">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="a4968-121">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a4968-121">Options</span></span>

`-h|--help`

<span data-ttu-id="a4968-122">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a4968-122">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="a4968-123">Esempi</span><span class="sxs-lookup"><span data-stu-id="a4968-123">Examples</span></span>

<span data-ttu-id="a4968-124">Aggiungere un progetto C# a una soluzione:</span><span class="sxs-lookup"><span data-stu-id="a4968-124">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="a4968-125">Rimuovere un progetto C# da una soluzione:</span><span class="sxs-lookup"><span data-stu-id="a4968-125">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="a4968-126">Aggiungere più progetti C# a una soluzione:</span><span class="sxs-lookup"><span data-stu-id="a4968-126">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="a4968-127">Rimuovere più progetti C# da una soluzione:</span><span class="sxs-lookup"><span data-stu-id="a4968-127">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="a4968-128">Aggiungere più progetti C# a una soluzione usando un criterio GLOB:</span><span class="sxs-lookup"><span data-stu-id="a4968-128">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="a4968-129">Rimuovere più progetti C# da una soluzione usando un criterio GLOB:</span><span class="sxs-lookup"><span data-stu-id="a4968-129">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`

> [!NOTE]
> <span data-ttu-id="a4968-130">L'utilizzo dei caratteri jolly non è una funzionalità dell'interfaccia della riga di comando, ma piuttosto una funzionalità della shell dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a4968-130">Globbing is not a CLI feature but rather a feature of the command shell.</span></span> <span data-ttu-id="a4968-131">Per espandere correttamente i file, è necessario usare una shell che supporta l'utilizzo dei caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="a4968-131">To successfully expand the files, you must use a shell that supports globbing.</span></span> <span data-ttu-id="a4968-132">Per altre informazioni sull'utilizzo dei caratteri jolly, vedere [Wikipedia](https://en.wikipedia.org/wiki/Glob_(programming)).</span><span class="sxs-lookup"><span data-stu-id="a4968-132">For more information about globbing, see [Wikipedia](https://en.wikipedia.org/wiki/Glob_(programming)).</span></span>
