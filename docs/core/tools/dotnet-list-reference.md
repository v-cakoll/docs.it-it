---
title: Comando dotnet list reference
description: Il comando dotnet list reference offre un'opzione utile per visualizzare un elenco dei riferimenti da progetto a progetto.
ms.date: 06/26/2019
ms.openlocfilehash: b4b82ca1e7aeb2b73d9f99aff1c97452b2166770
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117672"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="6025e-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="6025e-103">dotnet list reference</span></span>

<span data-ttu-id="6025e-104">**Questo argomento si applica a: ✓** .NET Core 2.1.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="6025e-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="6025e-105">nome</span><span class="sxs-lookup"><span data-stu-id="6025e-105">Name</span></span>

<span data-ttu-id="6025e-106">`dotnet list reference`: visualizza un elenco dei riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="6025e-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6025e-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="6025e-107">Synopsis</span></span>

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="6025e-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6025e-108">Description</span></span>

<span data-ttu-id="6025e-109">Il comando `dotnet list reference` offre un'opzione utile per visualizzare un elenco dei riferimenti al progetto per un progetto o una soluzione specificata.</span><span class="sxs-lookup"><span data-stu-id="6025e-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="6025e-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6025e-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="6025e-111">Specifica il file di progetto o di soluzione da usare per l'elenco dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="6025e-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="6025e-112">Se non specificato, il comando cerca un file di progetto nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="6025e-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="6025e-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="6025e-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="6025e-114">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="6025e-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="6025e-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="6025e-115">Examples</span></span>

* <span data-ttu-id="6025e-116">Visualizzare l'elenco dei riferimenti al progetto per il progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="6025e-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="6025e-117">Visualizzare l'elenco dei riferimenti al progetto per il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="6025e-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
