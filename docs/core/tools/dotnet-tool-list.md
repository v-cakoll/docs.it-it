---
title: Comando dotnet tool list
description: Il comando DotNet Tool List elenca gli strumenti di .NET Core installati nel computer.
ms.date: 02/14/2020
ms.openlocfilehash: bb74cfeaf441cf8a1a030d97d16655f85d8267d1
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543456"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="e4fd2-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="e4fd2-103">dotnet tool list</span></span>

<span data-ttu-id="e4fd2-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="e4fd2-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="e4fd2-105">Nome</span><span class="sxs-lookup"><span data-stu-id="e4fd2-105">Name</span></span>

<span data-ttu-id="e4fd2-106">`dotnet tool list`: elenca tutti gli [strumenti di .NET Core](global-tools.md) del tipo specificato attualmente installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-106">`dotnet tool list` - Lists all [.NET Core tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e4fd2-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="e4fd2-107">Synopsis</span></span>

```dotnetcli
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list
dotnet tool list <-h|--help>
```

## <a name="description"></a><span data-ttu-id="e4fd2-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4fd2-108">Description</span></span>

<span data-ttu-id="e4fd2-109">Il `dotnet tool list` comando fornisce un modo per elencare tutti gli strumenti globali, di percorso degli strumenti e di .NET Core installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-109">The `dotnet tool list` command provides a way for you to list all .NET Core global, tool-path, or local Tools installed on your machine.</span></span> <span data-ttu-id="e4fd2-110">Il comando elenca il nome del pacchetto, la versione installata e il comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="e4fd2-111">Per utilizzare il comando, è necessario specificare uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="e4fd2-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="e4fd2-112">Uno strumento globale installato nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-112">A global tool installed in the default location.</span></span> <span data-ttu-id="e4fd2-113">Usare l'opzione `--global`</span><span class="sxs-lookup"><span data-stu-id="e4fd2-113">Use the `--global` option</span></span>
* <span data-ttu-id="e4fd2-114">Uno strumento globale installato in un percorso personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-114">A global tool installed in a custom location.</span></span> <span data-ttu-id="e4fd2-115">Usare l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-115">Use the `--tool-path` option.</span></span>
* <span data-ttu-id="e4fd2-116">Uno strumento locale.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-116">A local tool.</span></span> <span data-ttu-id="e4fd2-117">Omettere le opzioni `--global` e `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-117">Omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="e4fd2-118">**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0.**</span><span class="sxs-lookup"><span data-stu-id="e4fd2-118">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="e4fd2-119">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e4fd2-119">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="e4fd2-120">Elenca gli strumenti globali a livello di utente.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-120">Lists user-wide global tools.</span></span> <span data-ttu-id="e4fd2-121">Non può essere usata con l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-121">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="e4fd2-122">Omettere sia `--global` che `--tool-path` elenca gli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-122">Omitting both `--global` and `--tool-path` lists local tools.</span></span> 

- **`-h|--help`**

  <span data-ttu-id="e4fd2-123">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-123">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="e4fd2-124">Specifica una posizione personalizzata in cui trovare gli strumenti globali.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-124">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="e4fd2-125">Il valore di PATH può essere assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-125">PATH can be absolute or relative.</span></span> <span data-ttu-id="e4fd2-126">Non può essere usata con l'opzione `--global`.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-126">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="e4fd2-127">Omettere sia `--global` che `--tool-path` elenca gli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-127">Omitting both `--global` and `--tool-path` lists local tools.</span></span> 

## <a name="examples"></a><span data-ttu-id="e4fd2-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="e4fd2-128">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="e4fd2-129">Elenca tutti gli strumenti globali installati a livello di utente nel computer (profilo utente corrente).</span><span class="sxs-lookup"><span data-stu-id="e4fd2-129">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="e4fd2-130">Elenca gli strumenti globali da una directory di Windows specifica.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-130">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="e4fd2-131">Elenca gli strumenti globali da una directory Linux/macOS specifica.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-131">Lists the global tools from a specific Linux/macOS directory.</span></span>

- **`dotnet tool list`**

  <span data-ttu-id="e4fd2-132">Elenca tutti gli strumenti locali disponibili nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="e4fd2-132">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4fd2-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4fd2-133">See also</span></span>

- [<span data-ttu-id="e4fd2-134">Strumenti di .NET Core</span><span class="sxs-lookup"><span data-stu-id="e4fd2-134">.NET Core tools</span></span>](global-tools.md)
