---
title: Comando dotnet tool list
description: Il comando dotnet tool list elenca gli strumenti .NET Core installati nel computer.
ms.date: 02/14/2020
ms.openlocfilehash: 28f9155407d1238f8b0960b69b34ea329ca0e8e6
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463353"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="55116-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="55116-103">dotnet tool list</span></span>

<span data-ttu-id="55116-104">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="55116-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="55116-105">Nome</span><span class="sxs-lookup"><span data-stu-id="55116-105">Name</span></span>

<span data-ttu-id="55116-106">`dotnet tool list`- Elenca tutti [gli strumenti .NET Core](global-tools.md) del tipo specificato attualmente installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="55116-106">`dotnet tool list` - Lists all [.NET Core tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="55116-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="55116-107">Synopsis</span></span>

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a><span data-ttu-id="55116-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55116-108">Description</span></span>

<span data-ttu-id="55116-109">Il `dotnet tool list` comando consente di elencare tutti gli strumenti globali, di percorso degli strumenti o locali di .NET Core installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="55116-109">The `dotnet tool list` command provides a way for you to list all .NET Core global, tool-path, or local Tools installed on your machine.</span></span> <span data-ttu-id="55116-110">Il comando elenca il nome del pacchetto, la versione installata e il comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="55116-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="55116-111">Per utilizzare il comando, specificare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="55116-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="55116-112">Uno strumento globale installato nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="55116-112">A global tool installed in the default location.</span></span> <span data-ttu-id="55116-113">Utilizzare `--global` l'opzione</span><span class="sxs-lookup"><span data-stu-id="55116-113">Use the `--global` option</span></span>
* <span data-ttu-id="55116-114">Strumento globale installato in una posizione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="55116-114">A global tool installed in a custom location.</span></span> <span data-ttu-id="55116-115">Usare l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="55116-115">Use the `--tool-path` option.</span></span>
* <span data-ttu-id="55116-116">Uno strumento locale.</span><span class="sxs-lookup"><span data-stu-id="55116-116">A local tool.</span></span> <span data-ttu-id="55116-117">Omettere le `--global` `--tool-path` opzioni e .</span><span class="sxs-lookup"><span data-stu-id="55116-117">Omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="55116-118">**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3.0.**</span><span class="sxs-lookup"><span data-stu-id="55116-118">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="55116-119">Opzioni</span><span class="sxs-lookup"><span data-stu-id="55116-119">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="55116-120">Elenca gli strumenti globali a livello di utente.</span><span class="sxs-lookup"><span data-stu-id="55116-120">Lists user-wide global tools.</span></span> <span data-ttu-id="55116-121">Non può essere usata con l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="55116-121">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="55116-122">Omettendo `--global` sia `--tool-path` ed elenca gli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="55116-122">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="55116-123">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="55116-123">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="55116-124">Specifica una posizione personalizzata in cui trovare gli strumenti globali.</span><span class="sxs-lookup"><span data-stu-id="55116-124">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="55116-125">Il valore di PATH può essere assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="55116-125">PATH can be absolute or relative.</span></span> <span data-ttu-id="55116-126">Non può essere usata con l'opzione `--global`.</span><span class="sxs-lookup"><span data-stu-id="55116-126">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="55116-127">Omettendo `--global` sia `--tool-path` ed elenca gli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="55116-127">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="55116-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="55116-128">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="55116-129">Elenca tutti gli strumenti globali installati a livello di utente nel computer (profilo utente corrente).</span><span class="sxs-lookup"><span data-stu-id="55116-129">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="55116-130">Elenca gli strumenti globali da una directory di Windows specifica.</span><span class="sxs-lookup"><span data-stu-id="55116-130">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="55116-131">Elenca gli strumenti globali da una directory Linux/macOS specifica.</span><span class="sxs-lookup"><span data-stu-id="55116-131">Lists the global tools from a specific Linux/macOS directory.</span></span>

- **`dotnet tool list`**

  <span data-ttu-id="55116-132">Elenca tutti gli strumenti locali disponibili nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="55116-132">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="55116-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55116-133">See also</span></span>

- [<span data-ttu-id="55116-134">Strumenti .NET Core</span><span class="sxs-lookup"><span data-stu-id="55116-134">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="55116-135">Esercitazione: Installare e usare uno strumento globale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core global tool using the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="55116-135">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="55116-136">Esercitazione: Installare e usare uno strumento locale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core local tool using the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="55116-136">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
