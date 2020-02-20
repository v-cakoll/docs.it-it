---
title: comando DotNet Add Reference
description: Il comando dotnet add reference offre un'opzione utile per aggiungere riferimenti da progetto a progetto.
ms.date: 02/14/2020
ms.openlocfilehash: 84ea25e94efc8d84aebfeccf62c30a64551c5019
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503796"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="1db4d-103">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="1db4d-103">dotnet add reference</span></span>

<span data-ttu-id="1db4d-104">**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1db4d-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="1db4d-105">Nome</span><span class="sxs-lookup"><span data-stu-id="1db4d-105">Name</span></span>

<span data-ttu-id="1db4d-106">`dotnet add reference`: aggiunge riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="1db4d-106">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1db4d-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="1db4d-107">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help] [--interactive]`

## <a name="description"></a><span data-ttu-id="1db4d-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1db4d-108">Description</span></span>

<span data-ttu-id="1db4d-109">Il comando `dotnet add reference` offre un'opzione utile per aggiungere i riferimenti al progetto in un progetto.</span><span class="sxs-lookup"><span data-stu-id="1db4d-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="1db4d-110">Dopo l'esecuzione del comando, gli elementi `<ProjectReference>` vengono aggiunti al file di progetto.</span><span class="sxs-lookup"><span data-stu-id="1db4d-110">After running the command, the `<ProjectReference>` elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="1db4d-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1db4d-111">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="1db4d-112">Specifica il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="1db4d-112">Specifies the project file.</span></span> <span data-ttu-id="1db4d-113">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="1db4d-113">If not specified, the command searches the current directory for one.</span></span>

- **`PROJECT_REFERENCES`**

  <span data-ttu-id="1db4d-114">Riferimenti da progetto a progetto da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="1db4d-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="1db4d-115">Specificare uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="1db4d-115">Specify one or more projects.</span></span> <span data-ttu-id="1db4d-116">I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei sistemi basati su Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="1db4d-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="1db4d-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1db4d-117">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="1db4d-118">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="1db4d-118">Prints out a short help for the command.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1db4d-119">Aggiunge riferimenti al progetto solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="1db4d-119">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

- **`--interactive`**

  <span data-ttu-id="1db4d-120">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione).</span><span class="sxs-lookup"><span data-stu-id="1db4d-120">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="1db4d-121">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1db4d-121">Available since .NET Core 3.0 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="1db4d-122">Esempi</span><span class="sxs-lookup"><span data-stu-id="1db4d-122">Examples</span></span>

- <span data-ttu-id="1db4d-123">Aggiungere un riferimento al progetto:</span><span class="sxs-lookup"><span data-stu-id="1db4d-123">Add a project reference:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="1db4d-124">Aggiungere più riferimenti al progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="1db4d-124">Add multiple project references to the project in the current directory:</span></span>

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="1db4d-125">Aggiungere più riferimenti al progetto usando un criterio GLOB in Linux/Unix:</span><span class="sxs-lookup"><span data-stu-id="1db4d-125">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
