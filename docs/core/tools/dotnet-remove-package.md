---
title: Comando dotnet remove package
description: Il comando dotnet remove package offre un'opzione utile per rimuovere il riferimento del pacchetto NuGet a un progetto.
ms.date: 02/14/2020
ms.openlocfilehash: 8eaa311748c5627351ef149012dc4dddd2ab2793
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503640"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="81cb2-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="81cb2-103">dotnet remove package</span></span>

<span data-ttu-id="81cb2-104">**Questo articolo si applica a:** ✔️ .NET Core 2.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="81cb2-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="81cb2-105">Nome</span><span class="sxs-lookup"><span data-stu-id="81cb2-105">Name</span></span>

<span data-ttu-id="81cb2-106">`dotnet remove package`: rimuove il riferimento al pacchetto da un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="81cb2-106">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="81cb2-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="81cb2-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]
```

## <a name="description"></a><span data-ttu-id="81cb2-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81cb2-108">Description</span></span>

<span data-ttu-id="81cb2-109">Il comando `dotnet remove package` offre un'opzione utile per rimuovere un riferimento al pacchetto NuGet da un progetto.</span><span class="sxs-lookup"><span data-stu-id="81cb2-109">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="81cb2-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="81cb2-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="81cb2-111">Specifica il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="81cb2-111">Specifies the project file.</span></span> <span data-ttu-id="81cb2-112">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="81cb2-112">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="81cb2-113">Riferimento al pacchetto da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="81cb2-113">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="81cb2-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="81cb2-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="81cb2-115">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="81cb2-115">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="81cb2-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="81cb2-116">Examples</span></span>

- <span data-ttu-id="81cb2-117">Rimuovere `Newtonsoft.Json` il pacchetto NuGet da un progetto nella directory corrente:Remove NuGet package from a project in the current directory:</span><span class="sxs-lookup"><span data-stu-id="81cb2-117">Remove `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove package Newtonsoft.Json
  ```
