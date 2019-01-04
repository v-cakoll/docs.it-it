---
title: Comando dotnet-add reference
description: Il comando dotnet add reference offre un'opzione utile per aggiungere riferimenti da progetto a progetto.
ms.date: 12/04/2018
ms.openlocfilehash: 8df9fa3c9469f74b27a9cb8120936f03532b016c
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169762"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="6e9ee-103">dotnet-add reference</span><span class="sxs-lookup"><span data-stu-id="6e9ee-103">dotnet-add reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="6e9ee-104">nome</span><span class="sxs-lookup"><span data-stu-id="6e9ee-104">Name</span></span>

<span data-ttu-id="6e9ee-105">`dotnet add reference`: aggiunge riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="6e9ee-105">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6e9ee-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="6e9ee-106">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="6e9ee-107">Description</span><span class="sxs-lookup"><span data-stu-id="6e9ee-107">Description</span></span>

<span data-ttu-id="6e9ee-108">Il comando `dotnet add reference` offre un'opzione utile per aggiungere i riferimenti al progetto in un progetto.</span><span class="sxs-lookup"><span data-stu-id="6e9ee-108">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="6e9ee-109">Dopo l'esecuzione del comando, al file di progetto vengono aggiunti gli elementi [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items).</span><span class="sxs-lookup"><span data-stu-id="6e9ee-109">After running the command, the [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="6e9ee-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6e9ee-110">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="6e9ee-111">Specifica il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="6e9ee-111">Specifies the project file.</span></span> <span data-ttu-id="6e9ee-112">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="6e9ee-112">If not specified, the command searches the current directory for one.</span></span>

* **`PROJECT_REFERENCES`**

  <span data-ttu-id="6e9ee-113">Riferimenti da progetto a progetto da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="6e9ee-113">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="6e9ee-114">Specificare uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="6e9ee-114">Specify one or more projects.</span></span> <span data-ttu-id="6e9ee-115">I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei sistemi basati su Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="6e9ee-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="6e9ee-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="6e9ee-116">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="6e9ee-117">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="6e9ee-117">Prints out a short help for the command.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="6e9ee-118">Aggiunge riferimenti al progetto solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="6e9ee-118">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="6e9ee-119">Esempi</span><span class="sxs-lookup"><span data-stu-id="6e9ee-119">Examples</span></span>

* <span data-ttu-id="6e9ee-120">Aggiungere un riferimento al progetto:</span><span class="sxs-lookup"><span data-stu-id="6e9ee-120">Add a project reference:</span></span>

  ```console
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

* <span data-ttu-id="6e9ee-121">Aggiungere più riferimenti al progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="6e9ee-121">Add multiple project references to the project in the current directory:</span></span>

  ```console
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

* <span data-ttu-id="6e9ee-122">Aggiungere più riferimenti al progetto usando un criterio GLOB in Linux/Unix:</span><span class="sxs-lookup"><span data-stu-id="6e9ee-122">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```console
  dotnet add app/app.csproj reference **/*.csproj
  ```