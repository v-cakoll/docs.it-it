---
title: Comando dotnet remove package
description: Il comando dotnet remove package offre un'opzione utile per rimuovere il riferimento del pacchetto NuGet a un progetto.
ms.date: 02/14/2020
ms.openlocfilehash: fc74ac1364a0ed027b83dab270d382f238dc00e5
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463448"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="1498d-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="1498d-103">dotnet remove package</span></span>

<span data-ttu-id="1498d-104">**Questo articolo si applica a:** ✔️ .NET Core 2.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1498d-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="1498d-105">Nome</span><span class="sxs-lookup"><span data-stu-id="1498d-105">Name</span></span>

<span data-ttu-id="1498d-106">`dotnet remove package`: rimuove il riferimento al pacchetto da un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="1498d-106">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1498d-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="1498d-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] package <PACKAGE_NAME>

dotnet remove package -h|--help
```

## <a name="description"></a><span data-ttu-id="1498d-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1498d-108">Description</span></span>

<span data-ttu-id="1498d-109">Il comando `dotnet remove package` offre un'opzione utile per rimuovere un riferimento al pacchetto NuGet da un progetto.</span><span class="sxs-lookup"><span data-stu-id="1498d-109">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="1498d-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1498d-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="1498d-111">Specifica il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="1498d-111">Specifies the project file.</span></span> <span data-ttu-id="1498d-112">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="1498d-112">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="1498d-113">Riferimento al pacchetto da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="1498d-113">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="1498d-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1498d-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="1498d-115">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="1498d-115">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="1498d-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="1498d-116">Examples</span></span>

- <span data-ttu-id="1498d-117">Rimuovere `Newtonsoft.Json` il pacchetto NuGet da un progetto nella directory corrente:Remove NuGet package from a project in the current directory:</span><span class="sxs-lookup"><span data-stu-id="1498d-117">Remove `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove package Newtonsoft.Json
  ```
