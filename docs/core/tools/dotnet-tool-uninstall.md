---
title: Comando dotnet tool uninstall
description: Il comando DotNet Tool uninstall Disinstalla lo strumento .NET Core specificato dal computer.
ms.date: 02/14/2020
ms.openlocfilehash: 82dad0206d9c3e2ef0f41c353f4a608f10e4f127
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543443"
---
# <a name="dotnet-tool-uninstall"></a><span data-ttu-id="62ec7-103">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="62ec7-103">dotnet tool uninstall</span></span>

<span data-ttu-id="62ec7-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="62ec7-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="62ec7-105">Nome</span><span class="sxs-lookup"><span data-stu-id="62ec7-105">Name</span></span>

<span data-ttu-id="62ec7-106">`dotnet tool uninstall`: disinstalla lo [strumento .NET Core](global-tools.md) specificato dal computer.</span><span class="sxs-lookup"><span data-stu-id="62ec7-106">`dotnet tool uninstall` - Uninstalls the specified [.NET Core tool](global-tools.md) from your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="62ec7-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="62ec7-107">Synopsis</span></span>

```dotnetcli
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <PACKAGE_NAME>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a><span data-ttu-id="62ec7-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62ec7-108">Description</span></span>

<span data-ttu-id="62ec7-109">Il comando `dotnet tool uninstall` fornisce un modo per disinstallare gli strumenti di .NET Core dal computer.</span><span class="sxs-lookup"><span data-stu-id="62ec7-109">The `dotnet tool uninstall` command provides a way for you to uninstall .NET Core tools from your machine.</span></span> <span data-ttu-id="62ec7-110">Per utilizzare il comando, è necessario specificare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="62ec7-110">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="62ec7-111">Per disinstallare uno strumento globale che è stato installato nel percorso predefinito, usare l'opzione `--global`.</span><span class="sxs-lookup"><span data-stu-id="62ec7-111">To uninstall a global tool that was installed in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="62ec7-112">Per disinstallare uno strumento globale installato in un percorso personalizzato, utilizzare l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="62ec7-112">To uninstall a global tool that was installed in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="62ec7-113">Per disinstallare uno strumento locale, omettere le opzioni `--global` e `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="62ec7-113">To uninstall a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="62ec7-114">**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0.**</span><span class="sxs-lookup"><span data-stu-id="62ec7-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="62ec7-115">Argomenti</span><span class="sxs-lookup"><span data-stu-id="62ec7-115">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="62ec7-116">Nome/ID del pacchetto NuGet che contiene lo strumento .NET Core da disinstallare.</span><span class="sxs-lookup"><span data-stu-id="62ec7-116">Name/ID of the NuGet package that contains the .NET Core tool to uninstall.</span></span> <span data-ttu-id="62ec7-117">È possibile trovare il nome del pacchetto usando il comando [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="62ec7-117">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="62ec7-118">Opzioni</span><span class="sxs-lookup"><span data-stu-id="62ec7-118">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="62ec7-119">Specifica che lo strumento da rimuovere appartiene a un'installazione a livello utente.</span><span class="sxs-lookup"><span data-stu-id="62ec7-119">Specifies that the tool to be removed is from a user-wide installation.</span></span> <span data-ttu-id="62ec7-120">Non può essere usata con l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="62ec7-120">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="62ec7-121">Omettendo sia `--global` che `--tool-path` specifica che lo strumento da rimuovere è uno strumento locale.</span><span class="sxs-lookup"><span data-stu-id="62ec7-121">Omitting both `--global` and `--tool-path` specifies that the tool to be removed is a local tool.</span></span> 

- **`-h|--help`**

  <span data-ttu-id="62ec7-122">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="62ec7-122">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="62ec7-123">Specifica il percorso in cui disinstallare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="62ec7-123">Specifies the location where to uninstall the tool.</span></span> <span data-ttu-id="62ec7-124">Il valore di PATH può essere assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="62ec7-124">PATH can be absolute or relative.</span></span> <span data-ttu-id="62ec7-125">Non può essere usata con l'opzione `--global`.</span><span class="sxs-lookup"><span data-stu-id="62ec7-125">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="62ec7-126">Omettendo sia `--global` che `--tool-path` specifica che lo strumento da rimuovere è uno strumento locale.</span><span class="sxs-lookup"><span data-stu-id="62ec7-126">Omitting both `--global` and `--tool-path` specifies that the tool to be removed is a local tool.</span></span> 

## <a name="examples"></a><span data-ttu-id="62ec7-127">Esempi</span><span class="sxs-lookup"><span data-stu-id="62ec7-127">Examples</span></span>

- **`dotnet tool uninstall -g dotnetsay`**

  <span data-ttu-id="62ec7-128">Disinstalla lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) .</span><span class="sxs-lookup"><span data-stu-id="62ec7-128">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="62ec7-129">Disinstalla lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) da una directory di Windows specifica.</span><span class="sxs-lookup"><span data-stu-id="62ec7-129">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool from a specific Windows directory.</span></span>

- **`dotnet tool uninstall dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="62ec7-130">Disinstalla lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) da una directory Linux/MacOS specifica.</span><span class="sxs-lookup"><span data-stu-id="62ec7-130">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool from a specific Linux/macOS directory.</span></span>

- **`dotnet tool uninstall dotnetsay`**

  <span data-ttu-id="62ec7-131">Disinstalla lo strumento locale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) dalla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="62ec7-131">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool from the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="62ec7-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62ec7-132">See also</span></span>

- [<span data-ttu-id="62ec7-133">Strumenti di .NET Core</span><span class="sxs-lookup"><span data-stu-id="62ec7-133">.NET Core tools</span></span>](global-tools.md)
