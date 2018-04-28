---
title: Comando dotnet sln - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-sln rappresenta un'opzione comoda per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 837d47c38119f9a7aa75c74576ed75b8ef3813dd
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-sln"></a><span data-ttu-id="d8b5f-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="d8b5f-103">dotnet sln</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d8b5f-104">nome</span><span class="sxs-lookup"><span data-stu-id="d8b5f-104">Name</span></span>

<span data-ttu-id="d8b5f-105">`dotnet sln`: consente di modificare un file di soluzione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d8b5f-105">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d8b5f-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="d8b5f-106">Synopsis</span></span>

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="d8b5f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8b5f-107">Description</span></span>

<span data-ttu-id="d8b5f-108">Il comando `dotnet sln` offre un modo pratico per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="d8b5f-108">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

## <a name="commands"></a><span data-ttu-id="d8b5f-109">Comandi:</span><span class="sxs-lookup"><span data-stu-id="d8b5f-109">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="d8b5f-110">Aggiunge uno o più progetti più al file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="d8b5f-110">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="d8b5f-111">I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei terminali basati su Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="d8b5f-111">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="d8b5f-112">Rimuove uno o più progetti dal file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="d8b5f-112">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="d8b5f-113">I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei terminali basati su Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="d8b5f-113">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="d8b5f-114">Elenca tutti i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="d8b5f-114">Lists all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="d8b5f-115">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d8b5f-115">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="d8b5f-116">File di soluzione da usare.</span><span class="sxs-lookup"><span data-stu-id="d8b5f-116">Solution file to use.</span></span> <span data-ttu-id="d8b5f-117">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="d8b5f-117">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="d8b5f-118">Se sono presenti più file di soluzione nella directory, è necessario specificarne uno.</span><span class="sxs-lookup"><span data-stu-id="d8b5f-118">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="d8b5f-119">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d8b5f-119">Options</span></span>

`-h|--help`

<span data-ttu-id="d8b5f-120">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="d8b5f-120">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="d8b5f-121">Esempi</span><span class="sxs-lookup"><span data-stu-id="d8b5f-121">Examples</span></span>

<span data-ttu-id="d8b5f-122">Aggiungere un progetto C# a una soluzione:</span><span class="sxs-lookup"><span data-stu-id="d8b5f-122">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="d8b5f-123">Rimuovere un progetto C# da una soluzione:</span><span class="sxs-lookup"><span data-stu-id="d8b5f-123">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="d8b5f-124">Aggiungere più progetti C# a una soluzione:</span><span class="sxs-lookup"><span data-stu-id="d8b5f-124">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="d8b5f-125">Rimuovere più progetti C# da una soluzione:</span><span class="sxs-lookup"><span data-stu-id="d8b5f-125">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="d8b5f-126">Aggiungere più progetti C# a una soluzione usando un criterio GLOB:</span><span class="sxs-lookup"><span data-stu-id="d8b5f-126">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="d8b5f-127">Rimuovere più progetti C# da una soluzione usando un criterio GLOB:</span><span class="sxs-lookup"><span data-stu-id="d8b5f-127">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`
