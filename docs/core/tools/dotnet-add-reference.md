---
title: comando DotNet Add Reference
description: Il comando dotnet add reference offre un'opzione utile per aggiungere riferimenti da progetto a progetto.
ms.date: 02/14/2020
ms.openlocfilehash: b261e24ed6a9d5bd489d317d2663b1420b5c34ff
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158320"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="9b56f-103">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="9b56f-103">dotnet add reference</span></span>

<span data-ttu-id="9b56f-104">**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="9b56f-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="9b56f-105">Nome</span><span class="sxs-lookup"><span data-stu-id="9b56f-105">Name</span></span>

<span data-ttu-id="9b56f-106">`dotnet add reference`: aggiunge riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="9b56f-106">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9b56f-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="9b56f-107">Synopsis</span></span>

```dotnetcli
dotnet add [<PROJECT>] reference [-f|--framework <FRAMEWORK>]
     [--interactive] <PROJECT_REFERENCES>

dotnet add reference -h|--help
```

## <a name="description"></a><span data-ttu-id="9b56f-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b56f-108">Description</span></span>

<span data-ttu-id="9b56f-109">Il comando `dotnet add reference` offre un'opzione utile per aggiungere i riferimenti al progetto in un progetto.</span><span class="sxs-lookup"><span data-stu-id="9b56f-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="9b56f-110">Dopo l'esecuzione del comando, al file di progetto vengono aggiunti gli elementi `<ProjectReference>`.</span><span class="sxs-lookup"><span data-stu-id="9b56f-110">After running the command, the `<ProjectReference>` elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="9b56f-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="9b56f-111">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="9b56f-112">Specifica il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="9b56f-112">Specifies the project file.</span></span> <span data-ttu-id="9b56f-113">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="9b56f-113">If not specified, the command searches the current directory for one.</span></span>

- **`PROJECT_REFERENCES`**

  <span data-ttu-id="9b56f-114">Riferimenti da progetto a progetto da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="9b56f-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="9b56f-115">Specificare uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="9b56f-115">Specify one or more projects.</span></span> <span data-ttu-id="9b56f-116">I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei sistemi basati su Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="9b56f-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="9b56f-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9b56f-117">Options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="9b56f-118">Aggiunge riferimenti al progetto solo quando la destinazione è un [Framework](../../standard/frameworks.md) specifico usando il formato TFM.</span><span class="sxs-lookup"><span data-stu-id="9b56f-118">Adds project references only when targeting a specific [framework](../../standard/frameworks.md) using the TFM format.</span></span>

- **`-h|--help`**

  <span data-ttu-id="9b56f-119">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="9b56f-119">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="9b56f-120">Consente al comando di arrestare e attendere l'input o l'azione dell'utente (in genere usato per completare l'autenticazione).</span><span class="sxs-lookup"><span data-stu-id="9b56f-120">Allows the command to stop and wait for user input or action (typically used to complete authentication).</span></span> <span data-ttu-id="9b56f-121">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="9b56f-121">Available since .NET Core 3.0 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="9b56f-122">Esempi</span><span class="sxs-lookup"><span data-stu-id="9b56f-122">Examples</span></span>

- <span data-ttu-id="9b56f-123">Aggiungere un riferimento al progetto:</span><span class="sxs-lookup"><span data-stu-id="9b56f-123">Add a project reference:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="9b56f-124">Aggiungere più riferimenti al progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="9b56f-124">Add multiple project references to the project in the current directory:</span></span>

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="9b56f-125">Aggiungere più riferimenti al progetto usando un criterio GLOB in Linux/Unix:</span><span class="sxs-lookup"><span data-stu-id="9b56f-125">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
