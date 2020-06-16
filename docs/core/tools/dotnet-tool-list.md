---
title: Comando dotnet tool list
description: Il comando DotNet Tool List elenca gli strumenti di .NET Core installati nel computer.
ms.date: 02/14/2020
ms.openlocfilehash: 7ca894ab0f5daf0118ff92fb39e0118b952b3d83
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768274"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="9cc5b-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="9cc5b-103">dotnet tool list</span></span>

<span data-ttu-id="9cc5b-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="9cc5b-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="9cc5b-105">Nome</span><span class="sxs-lookup"><span data-stu-id="9cc5b-105">Name</span></span>

<span data-ttu-id="9cc5b-106">`dotnet tool list`: Elenca tutti gli [strumenti di .NET Core](global-tools.md) del tipo specificato attualmente installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-106">`dotnet tool list` - Lists all [.NET Core tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9cc5b-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="9cc5b-107">Synopsis</span></span>

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list --local

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a><span data-ttu-id="9cc5b-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9cc5b-108">Description</span></span>

<span data-ttu-id="9cc5b-109">Il `dotnet tool list` comando fornisce un modo per elencare tutti gli strumenti globali, di percorso degli strumenti e di .net core installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-109">The `dotnet tool list` command provides a way for you to list all .NET Core global, tool-path, or local tools installed on your machine.</span></span> <span data-ttu-id="9cc5b-110">Il comando elenca il nome del pacchetto, la versione installata e il comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="9cc5b-111">Per utilizzare il comando, è necessario specificare uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="9cc5b-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="9cc5b-112">Per elencare gli strumenti globali installati nel percorso predefinito, usare l' `--global` opzione</span><span class="sxs-lookup"><span data-stu-id="9cc5b-112">To list global tools installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="9cc5b-113">Per elencare gli strumenti globali installati in un percorso personalizzato, utilizzare l' `--tool-path` opzione.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-113">To list global tools installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="9cc5b-114">Per elencare gli strumenti locali, uno strumento locale.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-114">To list local tools, A local tool.</span></span> <span data-ttu-id="9cc5b-115">utilizzare l' `--local` opzione o omettere `--global` le `--tool-path` Opzioni, e `--local` .</span><span class="sxs-lookup"><span data-stu-id="9cc5b-115">use the `--local` option or omit the `--global`, `--tool-path`, and `--local` options.</span></span>

<span data-ttu-id="9cc5b-116">**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0.**</span><span class="sxs-lookup"><span data-stu-id="9cc5b-116">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="9cc5b-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9cc5b-117">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="9cc5b-118">Elenca gli strumenti globali a livello di utente.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-118">Lists user-wide global tools.</span></span> <span data-ttu-id="9cc5b-119">Non può essere usata con l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-119">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="9cc5b-120">Omettendo `--global` ed `--tool-path` elenca gli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-120">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="9cc5b-121">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-121">Prints out a short help for the command.</span></span>

- **`--local`**

  <span data-ttu-id="9cc5b-122">Elenca gli strumenti locali per la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-122">Lists local tools for the current directory.</span></span> <span data-ttu-id="9cc5b-123">Non può essere combinato con `--global` le `--tool-path` Opzioni o.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-123">Can't be combined with the `--global` or `--tool-path` options.</span></span> <span data-ttu-id="9cc5b-124">L'omissione `--global` di entrambi `--tool-path` gli strumenti e l'elenco degli strumenti locali anche se `--local` non è specificato.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-124">Omitting both `--global` and `--tool-path` lists local tools even if `--local` is not specified.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="9cc5b-125">Specifica una posizione personalizzata in cui trovare gli strumenti globali.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-125">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="9cc5b-126">Il valore di PATH può essere assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-126">PATH can be absolute or relative.</span></span> <span data-ttu-id="9cc5b-127">Non può essere usata con l'opzione `--global`.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-127">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="9cc5b-128">Omettendo `--global` ed `--tool-path` elenca gli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-128">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="9cc5b-129">Esempi</span><span class="sxs-lookup"><span data-stu-id="9cc5b-129">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="9cc5b-130">Elenca tutti gli strumenti globali installati a livello di utente nel computer (profilo utente corrente).</span><span class="sxs-lookup"><span data-stu-id="9cc5b-130">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="9cc5b-131">Elenca gli strumenti globali da una directory di Windows specifica.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-131">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="9cc5b-132">Elenca gli strumenti globali da una directory Linux/macOS specifica.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-132">Lists the global tools from a specific Linux/macOS directory.</span></span>

- <span data-ttu-id="9cc5b-133">**`dotnet tool list`** o**`dotnet tool list --local`**</span><span class="sxs-lookup"><span data-stu-id="9cc5b-133">**`dotnet tool list`** or **`dotnet tool list --local`**</span></span>

  <span data-ttu-id="9cc5b-134">Elenca tutti gli strumenti locali disponibili nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-134">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cc5b-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cc5b-135">See also</span></span>

- [<span data-ttu-id="9cc5b-136">Strumenti di .NET Core</span><span class="sxs-lookup"><span data-stu-id="9cc5b-136">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="9cc5b-137">Esercitazione: installare e usare uno strumento globale .NET Core usando il interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="9cc5b-137">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="9cc5b-138">Esercitazione: installare e usare uno strumento locale di .NET Core usando il interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="9cc5b-138">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
