---
title: Comando dotnet tool update
description: Il comando DotNet Tool Update aggiorna lo strumento .NET Core specificato nel computer.
ms.date: 02/14/2020
ms.openlocfilehash: 50bb366fedfb0ea69b8b6007ff89e366b4f689de
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543417"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="840a9-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="840a9-103">dotnet tool update</span></span>

<span data-ttu-id="840a9-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="840a9-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="840a9-105">Nome</span><span class="sxs-lookup"><span data-stu-id="840a9-105">Name</span></span>

<span data-ttu-id="840a9-106">`dotnet tool update`: aggiorna lo [strumento .NET Core](global-tools.md) specificato nel computer.</span><span class="sxs-lookup"><span data-stu-id="840a9-106">`dotnet tool update` - Updates the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="840a9-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="840a9-107">Synopsis</span></span>

```dotnetcli
dotnet tool update <PACKAGE_NAME> <-g|--global> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <PACKAGE_NAME> <--tool-path> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <PACKAGE_NAME> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <-h|--help>
```

## <a name="description"></a><span data-ttu-id="840a9-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="840a9-108">Description</span></span>

<span data-ttu-id="840a9-109">Il `dotnet tool update` comando fornisce un modo per aggiornare gli strumenti di .NET Core nel computer alla versione stabile più recente del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="840a9-109">The `dotnet tool update` command provides a way for you to update .NET Core tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="840a9-110">Il comando disinstalla e reinstalla uno strumento aggiornandolo.</span><span class="sxs-lookup"><span data-stu-id="840a9-110">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="840a9-111">Per utilizzare il comando, è necessario specificare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="840a9-111">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="840a9-112">Per aggiornare uno strumento globale che è stato installato nel percorso predefinito, usare l'opzione `--global`</span><span class="sxs-lookup"><span data-stu-id="840a9-112">To update a global tool that was installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="840a9-113">Per aggiornare uno strumento globale installato in un percorso personalizzato, utilizzare l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="840a9-113">To update a global tool that was installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="840a9-114">Per aggiornare uno strumento locale, omettere le opzioni `--global` e `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="840a9-114">To update a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="840a9-115">**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0.**</span><span class="sxs-lookup"><span data-stu-id="840a9-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="840a9-116">Argomenti</span><span class="sxs-lookup"><span data-stu-id="840a9-116">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="840a9-117">Nome/ID del pacchetto NuGet che contiene lo strumento globale .NET Core da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="840a9-117">Name/ID of the NuGet package that contains the .NET Core global tool to update.</span></span> <span data-ttu-id="840a9-118">È possibile trovare il nome del pacchetto usando il comando [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="840a9-118">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="840a9-119">Opzioni</span><span class="sxs-lookup"><span data-stu-id="840a9-119">Options</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="840a9-120">Aggiunge un'altra origine pacchetto NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="840a9-120">Adds an additional NuGet package source to use during installation.</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="840a9-121">File di configurazione NuGet (*nuget.config*) da usare.</span><span class="sxs-lookup"><span data-stu-id="840a9-121">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="840a9-122">Specifica il [framework di destinazione](../../standard/frameworks.md) per cui aggiornare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="840a9-122">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

- **`-g|--global`**

  <span data-ttu-id="840a9-123">Specifica che l'aggiornamento è per uno strumento a livello utente.</span><span class="sxs-lookup"><span data-stu-id="840a9-123">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="840a9-124">Non può essere usata con l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="840a9-124">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="840a9-125">Omettendo sia `--global` che `--tool-path` specifica che lo strumento da aggiornare è uno strumento locale.</span><span class="sxs-lookup"><span data-stu-id="840a9-125">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span> 

- **`-h|--help`**

  <span data-ttu-id="840a9-126">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="840a9-126">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="840a9-127">Specifica il percorso in cui è installato lo strumento globale.</span><span class="sxs-lookup"><span data-stu-id="840a9-127">Specifies the location where the global tool is installed.</span></span> <span data-ttu-id="840a9-128">Il valore di PATH può essere assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="840a9-128">PATH can be absolute or relative.</span></span> <span data-ttu-id="840a9-129">Non può essere usata con l'opzione `--global`.</span><span class="sxs-lookup"><span data-stu-id="840a9-129">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="840a9-130">Omettendo sia `--global` che `--tool-path` specifica che lo strumento da aggiornare è uno strumento locale.</span><span class="sxs-lookup"><span data-stu-id="840a9-130">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span> 

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="840a9-131">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="840a9-131">Sets the verbosity level of the command.</span></span> <span data-ttu-id="840a9-132">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="840a9-132">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="840a9-133">Esempi</span><span class="sxs-lookup"><span data-stu-id="840a9-133">Examples</span></span>

- **`dotnet tool update -g dotnetsay`**

  <span data-ttu-id="840a9-134">Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) .</span><span class="sxs-lookup"><span data-stu-id="840a9-134">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="840a9-135">Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) che si trova in una directory di Windows specifica.</span><span class="sxs-lookup"><span data-stu-id="840a9-135">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Windows directory.</span></span>

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="840a9-136">Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) che si trova in una directory Linux/MacOS specifica.</span><span class="sxs-lookup"><span data-stu-id="840a9-136">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Linux/macOS directory.</span></span>

- **`dotnet tool update dotnetsay`**

  <span data-ttu-id="840a9-137">Aggiorna lo strumento locale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) installato per la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="840a9-137">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool installed for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="840a9-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="840a9-138">See also</span></span>

- [<span data-ttu-id="840a9-139">Strumenti di .NET Core</span><span class="sxs-lookup"><span data-stu-id="840a9-139">.NET Core tools</span></span>](global-tools.md)
