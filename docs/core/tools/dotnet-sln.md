---
title: Comando dotnet-sln - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-sln rappresenta un'opzione comoda per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.
keywords: dotnet-sln, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 04/11/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: e5a72d3e-c14b-4b0a-a978-c5e54a0988c6
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 606929fbcafddf47abf5da6d3c8ce97d5af06909
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-sln"></a><span data-ttu-id="93ef6-104">dotnet-sln</span><span class="sxs-lookup"><span data-stu-id="93ef6-104">dotnet-sln</span></span>

## <a name="name"></a><span data-ttu-id="93ef6-105">Nome</span><span class="sxs-lookup"><span data-stu-id="93ef6-105">Name</span></span>

<span data-ttu-id="93ef6-106">`dotnet-sln`: consente di modificare un file di soluzione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="93ef6-106">`dotnet-sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="93ef6-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="93ef6-107">Synopsis</span></span>

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="93ef6-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93ef6-108">Description</span></span>

<span data-ttu-id="93ef6-109">Il comando `dotnet sln` offre un modo pratico per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="93ef6-109">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

## <a name="commands"></a><span data-ttu-id="93ef6-110">Comandi:</span><span class="sxs-lookup"><span data-stu-id="93ef6-110">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="93ef6-111">Aggiunge uno o più progetti più al file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="93ef6-111">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="93ef6-112">I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei terminali basati su Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="93ef6-112">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="93ef6-113">Rimuove uno o più progetti dal file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="93ef6-113">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="93ef6-114">I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei terminali basati su Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="93ef6-114">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="93ef6-115">Elenca tutti i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="93ef6-115">List all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="93ef6-116">Argomenti</span><span class="sxs-lookup"><span data-stu-id="93ef6-116">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="93ef6-117">File di soluzione da usare.</span><span class="sxs-lookup"><span data-stu-id="93ef6-117">Solution file to use.</span></span> <span data-ttu-id="93ef6-118">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="93ef6-118">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="93ef6-119">Se sono presenti più file di soluzione nella directory, è necessario specificarne uno.</span><span class="sxs-lookup"><span data-stu-id="93ef6-119">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="93ef6-120">Opzioni</span><span class="sxs-lookup"><span data-stu-id="93ef6-120">Options</span></span>

`-h|--help`

<span data-ttu-id="93ef6-121">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="93ef6-121">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="93ef6-122">Esempi</span><span class="sxs-lookup"><span data-stu-id="93ef6-122">Examples</span></span>

<span data-ttu-id="93ef6-123">Aggiungere un progetto C# a una soluzione:</span><span class="sxs-lookup"><span data-stu-id="93ef6-123">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="93ef6-124">Rimuovere un progetto C# da una soluzione:</span><span class="sxs-lookup"><span data-stu-id="93ef6-124">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="93ef6-125">Aggiungere più progetti C# a una soluzione:</span><span class="sxs-lookup"><span data-stu-id="93ef6-125">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="93ef6-126">Rimuovere più progetti C# da una soluzione:</span><span class="sxs-lookup"><span data-stu-id="93ef6-126">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="93ef6-127">Aggiungere più progetti C# a una soluzione usando un criterio GLOB:</span><span class="sxs-lookup"><span data-stu-id="93ef6-127">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="93ef6-128">Rimuovere più progetti C# da una soluzione usando un criterio GLOB:</span><span class="sxs-lookup"><span data-stu-id="93ef6-128">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`

