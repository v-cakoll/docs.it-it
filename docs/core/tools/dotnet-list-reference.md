---
title: Comando dotnet list reference
description: Il comando dotnet list reference offre un'opzione utile per visualizzare un elenco dei riferimenti da progetto a progetto.
ms.date: 02/14/2020
ms.openlocfilehash: b9b34c17102c6218f3d99f6e2620e99f70140284
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802756"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="cb5be-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="cb5be-103">dotnet list reference</span></span>

<span data-ttu-id="cb5be-104">**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="cb5be-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="cb5be-105">Nome</span><span class="sxs-lookup"><span data-stu-id="cb5be-105">Name</span></span>

<span data-ttu-id="cb5be-106">`dotnet list reference`: visualizza un elenco dei riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="cb5be-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cb5be-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="cb5be-107">Synopsis</span></span>

```dotnetcli
dotnet list [<PROJECT>] reference

dotnet list -h|--help
```

## <a name="description"></a><span data-ttu-id="cb5be-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb5be-108">Description</span></span>

<span data-ttu-id="cb5be-109">Il comando `dotnet list reference` offre un'opzione utile per visualizzare un elenco dei riferimenti al progetto per un progetto specificato.</span><span class="sxs-lookup"><span data-stu-id="cb5be-109">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="cb5be-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="cb5be-110">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="cb5be-111">File di progetto da usare.</span><span class="sxs-lookup"><span data-stu-id="cb5be-111">The project file to operate on.</span></span> <span data-ttu-id="cb5be-112">Se non viene specificato alcun file, il comando cercherà una directory corrente.</span><span class="sxs-lookup"><span data-stu-id="cb5be-112">If a file is not specified, the command will search the current directory for one.</span></span>

## <a name="options"></a><span data-ttu-id="cb5be-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cb5be-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="cb5be-114">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="cb5be-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="cb5be-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="cb5be-115">Examples</span></span>

* <span data-ttu-id="cb5be-116">Visualizzare l'elenco dei riferimenti al progetto per il progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="cb5be-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="cb5be-117">Visualizzare l'elenco dei riferimenti al progetto per il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="cb5be-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
