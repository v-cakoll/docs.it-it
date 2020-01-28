---
title: comando DotNet Add Reference
description: Il comando dotnet add reference offre un'opzione utile per aggiungere riferimenti da progetto a progetto.
ms.date: 06/26/2019
ms.openlocfilehash: dc8bc01a2bff4f2cf3a8af9efb233448d7de337f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733280"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="3cc76-103">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="3cc76-103">dotnet add reference</span></span>

<span data-ttu-id="3cc76-104">**Questo articolo si applica a:** ✔️ .NET Core 1. x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="3cc76-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="3cc76-105">Name</span><span class="sxs-lookup"><span data-stu-id="3cc76-105">Name</span></span>

<span data-ttu-id="3cc76-106">`dotnet add reference`: aggiunge riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="3cc76-106">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3cc76-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3cc76-107">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help] [--interactive]`

## <a name="description"></a><span data-ttu-id="3cc76-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3cc76-108">Description</span></span>

<span data-ttu-id="3cc76-109">Il comando `dotnet add reference` offre un'opzione utile per aggiungere i riferimenti al progetto in un progetto.</span><span class="sxs-lookup"><span data-stu-id="3cc76-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="3cc76-110">Dopo l'esecuzione del comando, gli elementi `<ProjectReference>` vengono aggiunti al file di progetto.</span><span class="sxs-lookup"><span data-stu-id="3cc76-110">After running the command, the `<ProjectReference>` elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="3cc76-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3cc76-111">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="3cc76-112">Specifica il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="3cc76-112">Specifies the project file.</span></span> <span data-ttu-id="3cc76-113">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="3cc76-113">If not specified, the command searches the current directory for one.</span></span>

- **`PROJECT_REFERENCES`**

  <span data-ttu-id="3cc76-114">Riferimenti da progetto a progetto da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="3cc76-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="3cc76-115">Specificare uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="3cc76-115">Specify one or more projects.</span></span> <span data-ttu-id="3cc76-116">I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei sistemi basati su Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="3cc76-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="3cc76-117">Options</span><span class="sxs-lookup"><span data-stu-id="3cc76-117">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="3cc76-118">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="3cc76-118">Prints out a short help for the command.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3cc76-119">Aggiunge riferimenti al progetto solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="3cc76-119">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

- **`--interactive`**

  <span data-ttu-id="3cc76-120">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione).</span><span class="sxs-lookup"><span data-stu-id="3cc76-120">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="3cc76-121">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="3cc76-121">Available since .NET Core 3.0 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="3cc76-122">Esempi</span><span class="sxs-lookup"><span data-stu-id="3cc76-122">Examples</span></span>

- <span data-ttu-id="3cc76-123">Aggiungere un riferimento al progetto:</span><span class="sxs-lookup"><span data-stu-id="3cc76-123">Add a project reference:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="3cc76-124">Aggiungere più riferimenti al progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="3cc76-124">Add multiple project references to the project in the current directory:</span></span>

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="3cc76-125">Aggiungere più riferimenti al progetto usando un criterio GLOB in Linux/Unix:</span><span class="sxs-lookup"><span data-stu-id="3cc76-125">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
