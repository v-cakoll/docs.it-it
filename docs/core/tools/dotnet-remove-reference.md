---
title: Comando dotnet remove reference
description: Il comando dotnet remove reference offre un'opzione utile per rimuovere riferimenti da progetto a progetto.
ms.date: 02/14/2020
ms.openlocfilehash: 92d36bbbde64d806abc8f223c5f08e3f3d79ce9d
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463437"
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="5c97e-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="5c97e-103">dotnet remove reference</span></span>

<span data-ttu-id="5c97e-104">**Questo articolo si applica a:** ✔️ .NET Core 2.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="5c97e-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="5c97e-105">Nome</span><span class="sxs-lookup"><span data-stu-id="5c97e-105">Name</span></span>

<span data-ttu-id="5c97e-106">`dotnet remove reference`: rimuove i riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="5c97e-106">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5c97e-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="5c97e-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] reference [-f|--framework <FRAMEWORK>] <PROJECT_REFERENCES>

dotnet remove reference -h|--help
```

## <a name="description"></a><span data-ttu-id="5c97e-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c97e-108">Description</span></span>

<span data-ttu-id="5c97e-109">Il comando `dotnet remove reference` offre un'opzione utile per rimuovere i riferimenti al progetto da un progetto.</span><span class="sxs-lookup"><span data-stu-id="5c97e-109">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="5c97e-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5c97e-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="5c97e-111">File di progetto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5c97e-111">Target project file.</span></span> <span data-ttu-id="5c97e-112">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="5c97e-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="5c97e-113">Riferimenti da progetto a progetto da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="5c97e-113">Project-to-project (P2P) references to remove.</span></span> <span data-ttu-id="5c97e-114">È possibile specificare uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="5c97e-114">You can specify one or multiple projects.</span></span> <span data-ttu-id="5c97e-115">I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei terminali basati su Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="5c97e-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="5c97e-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5c97e-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="5c97e-117">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="5c97e-117">Prints out a short help for the command.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5c97e-118">Rimuove il riferimento solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="5c97e-118">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="5c97e-119">Esempi</span><span class="sxs-lookup"><span data-stu-id="5c97e-119">Examples</span></span>

- <span data-ttu-id="5c97e-120">Rimuovere un riferimento al progetto dal progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="5c97e-120">Remove a project reference from the specified project:</span></span>

  ```dotnetcli
  dotnet remove app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="5c97e-121">Rimuovere più riferimenti al progetto dal progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="5c97e-121">Remove multiple project references from the project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="5c97e-122">Rimuovere più riferimenti al progetto usando un criterio GLOB in Unix/Linux:</span><span class="sxs-lookup"><span data-stu-id="5c97e-122">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

  ```dotnetcli
  dotnet remove app/app.csproj reference **/*.csproj`
  ```
