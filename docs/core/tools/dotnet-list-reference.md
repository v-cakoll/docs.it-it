---
title: Comando dotnet list reference - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet list reference offre un'opzione utile per visualizzare un elenco dei riferimenti da progetto a progetto.
ms.date: 12/03/2018
ms.openlocfilehash: 58b4e07abfe95d1febdd54d117825ecedf502e61
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152603"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="a056b-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="a056b-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="a056b-104">nome</span><span class="sxs-lookup"><span data-stu-id="a056b-104">Name</span></span>

<span data-ttu-id="a056b-105">`dotnet list reference`: visualizza un elenco dei riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="a056b-105">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a056b-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a056b-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="a056b-107">Description</span><span class="sxs-lookup"><span data-stu-id="a056b-107">Description</span></span>

<span data-ttu-id="a056b-108">Il comando `dotnet list reference` offre un'opzione utile per visualizzare un elenco dei riferimenti al progetto per un progetto o una soluzione specificata.</span><span class="sxs-lookup"><span data-stu-id="a056b-108">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="a056b-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a056b-109">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="a056b-110">Specifica il file di progetto da usare per l'elenco dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="a056b-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="a056b-111">Se non specificato, il comando cerca un file di progetto nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a056b-111">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="a056b-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a056b-112">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="a056b-113">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a056b-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="a056b-114">Esempi</span><span class="sxs-lookup"><span data-stu-id="a056b-114">Examples</span></span>

* <span data-ttu-id="a056b-115">Visualizzare l'elenco dei riferimenti al progetto per il progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="a056b-115">List the project references for the specified project:</span></span>

  ```console
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="a056b-116">Visualizzare l'elenco dei riferimenti al progetto per il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="a056b-116">List the project references for the project in the current directory:</span></span>

  ```console
  dotnet list reference
  ```