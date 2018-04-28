---
title: Comando dotnet-add reference - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet add reference offre un'opzione utile per aggiungere riferimenti da progetto a progetto.
author: mairaw
ms.author: mairaw
ms.date: 09/19/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: c82696eee2fbe4bbad86e59cf5de1c2e74d048f6
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="99b4d-103">dotnet-add reference</span><span class="sxs-lookup"><span data-stu-id="99b4d-103">dotnet-add reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="99b4d-104">nome</span><span class="sxs-lookup"><span data-stu-id="99b4d-104">Name</span></span>

<span data-ttu-id="99b4d-105">`dotnet add reference`: aggiunge riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="99b4d-105">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="99b4d-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="99b4d-106">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="99b4d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99b4d-107">Description</span></span>

<span data-ttu-id="99b4d-108">Il comando `dotnet add reference` offre un'opzione utile per aggiungere i riferimenti al progetto in un progetto.</span><span class="sxs-lookup"><span data-stu-id="99b4d-108">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="99b4d-109">Dopo l'esecuzione del comando, al file di progetto vengono aggiunti gli elementi [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items).</span><span class="sxs-lookup"><span data-stu-id="99b4d-109">After running the command, the [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="99b4d-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="99b4d-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="99b4d-111">Specifica il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="99b4d-111">Specifies the project file.</span></span> <span data-ttu-id="99b4d-112">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="99b4d-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="99b4d-113">Riferimenti da progetto a progetto da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="99b4d-113">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="99b4d-114">Specificare uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="99b4d-114">Specify one or more projects.</span></span> <span data-ttu-id="99b4d-115">I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei sistemi basati su Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="99b4d-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="99b4d-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="99b4d-116">Options</span></span>

`-h|--help`

<span data-ttu-id="99b4d-117">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="99b4d-117">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="99b4d-118">Aggiunge riferimenti al progetto solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="99b4d-118">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="99b4d-119">Esempi</span><span class="sxs-lookup"><span data-stu-id="99b4d-119">Examples</span></span>

<span data-ttu-id="99b4d-120">Aggiungere un riferimento al progetto:</span><span class="sxs-lookup"><span data-stu-id="99b4d-120">Add a project reference:</span></span>

`dotnet add app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="99b4d-121">Aggiungere più riferimenti al progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="99b4d-121">Add multiple project references to the project in the current directory:</span></span>

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="99b4d-122">Aggiungere più riferimenti al progetto usando un criterio GLOB in Linux/Unix:</span><span class="sxs-lookup"><span data-stu-id="99b4d-122">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

`dotnet add app/app.csproj reference **/*.csproj`
