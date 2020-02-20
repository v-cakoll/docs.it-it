---
title: Comando dotnet list reference
description: Il comando dotnet list reference offre un'opzione utile per visualizzare un elenco dei riferimenti da progetto a progetto.
ms.date: 02/14/2020
ms.openlocfilehash: 43c4dbc94b33e717c6ba0a1c1c5317ac006f5bba
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503708"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="a140c-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="a140c-103">dotnet list reference</span></span>

<span data-ttu-id="a140c-104">**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="a140c-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="a140c-105">Nome</span><span class="sxs-lookup"><span data-stu-id="a140c-105">Name</span></span>

<span data-ttu-id="a140c-106">`dotnet list reference`: visualizza un elenco dei riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="a140c-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a140c-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a140c-107">Synopsis</span></span>

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="a140c-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a140c-108">Description</span></span>

<span data-ttu-id="a140c-109">Il comando `dotnet list reference` offre un'opzione utile per visualizzare un elenco dei riferimenti al progetto per un progetto o una soluzione specificata.</span><span class="sxs-lookup"><span data-stu-id="a140c-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="a140c-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a140c-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="a140c-111">Specifica il file di progetto o di soluzione da usare per l'elenco dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="a140c-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="a140c-112">Se non specificato, il comando cerca un file di progetto nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a140c-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="a140c-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a140c-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="a140c-114">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a140c-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="a140c-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="a140c-115">Examples</span></span>

* <span data-ttu-id="a140c-116">Visualizzare l'elenco dei riferimenti al progetto per il progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="a140c-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="a140c-117">Visualizzare l'elenco dei riferimenti al progetto per il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="a140c-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
