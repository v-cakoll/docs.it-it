---
title: Comando dotnet list reference
description: Il comando dotnet list reference offre un'opzione utile per visualizzare un elenco dei riferimenti da progetto a progetto.
ms.date: 02/14/2020
ms.openlocfilehash: c0ea46298123e69ae527870e50d204d8fcf5cc85
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463652"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="91404-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="91404-103">dotnet list reference</span></span>

<span data-ttu-id="91404-104">**Questo articolo si applica a:** ✔️ .NET Core 2.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="91404-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="91404-105">Nome</span><span class="sxs-lookup"><span data-stu-id="91404-105">Name</span></span>

<span data-ttu-id="91404-106">`dotnet list reference`: visualizza un elenco dei riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="91404-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="91404-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="91404-107">Synopsis</span></span>

```dotnetcli
dotnet list [<PROJECT>|<SOLUTION>] reference

dotnet list -h|--help
```

## <a name="description"></a><span data-ttu-id="91404-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91404-108">Description</span></span>

<span data-ttu-id="91404-109">Il comando `dotnet list reference` offre un'opzione utile per visualizzare un elenco dei riferimenti al progetto per un progetto o una soluzione specificata.</span><span class="sxs-lookup"><span data-stu-id="91404-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="91404-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="91404-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="91404-111">Specifica il file di progetto o di soluzione da usare per l'elenco dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="91404-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="91404-112">Se non specificato, il comando cerca un file di progetto nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="91404-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="91404-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="91404-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="91404-114">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="91404-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="91404-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="91404-115">Examples</span></span>

* <span data-ttu-id="91404-116">Visualizzare l'elenco dei riferimenti al progetto per il progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="91404-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="91404-117">Visualizzare l'elenco dei riferimenti al progetto per il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="91404-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
