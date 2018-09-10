---
title: Comando dotnet tool update - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet tool update aggiorna lo strumento globale .NET Core specificato nel computer.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 90b0dc91f74d890420dc7185642aa89100cadba8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44069393"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="6a1c8-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="6a1c8-103">dotnet tool update</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="6a1c8-104">nome</span><span class="sxs-lookup"><span data-stu-id="6a1c8-104">Name</span></span>

<span data-ttu-id="6a1c8-105">`dotnet tool update` - Aggiorna lo [strumento globale .NET Core](global-tools.md) specificato nel computer.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-105">`dotnet tool update` - Updates the specified [.NET Core Global Tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6a1c8-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="6a1c8-106">Synopsis</span></span>

```console
dotnet tool update <PACKAGE_NAME> <-g|--global> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <PACKAGE_NAME> <--tool-path> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <-h|--help>
```

## <a name="description"></a><span data-ttu-id="6a1c8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a1c8-107">Description</span></span>

<span data-ttu-id="6a1c8-108">Il comando `dotnet tool update` consente di aggiornare gli strumenti globali .NET Core nel computer all'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-108">The `dotnet tool update` command provides a way for you to update .NET Core Global Tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="6a1c8-109">Il comando disinstalla e reinstalla uno strumento aggiornandolo.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-109">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="6a1c8-110">Per usare il comando, è necessario specificare che si vuole aggiornare uno strumento da un'installazione a livello utente con l'opzione `--global` oppure specificare un percorso in cui è installato lo strumento con l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-110">To use the command, you either have to specify that you want to update a tool from a user-wide installation using the `--global` option or specify a path to where the tool is installed using the `--tool-path` option.</span></span>

## <a name="arguments"></a><span data-ttu-id="6a1c8-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6a1c8-111">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="6a1c8-112">Nome/ID del pacchetto NuGet che contiene lo strumento globale .NET Core da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-112">Name/ID of the NuGet package that contains the .NET Core Global Tool to update.</span></span> <span data-ttu-id="6a1c8-113">È possibile trovare il nome del pacchetto usando il comando [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="6a1c8-113">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="6a1c8-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="6a1c8-114">Options</span></span>

`--add-source <SOURCE>`

<span data-ttu-id="6a1c8-115">Aggiunge un'altra origine pacchetto NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-115">Adds an additional NuGet package source to use during installation.</span></span>

`--configfile <FILE>`

<span data-ttu-id="6a1c8-116">File di configurazione NuGet (*nuget.config*) da usare.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-116">The NuGet configuration (*nuget.config*) file to use.</span></span>

`--framework <FRAMEWORK>`

<span data-ttu-id="6a1c8-117">Specifica il [framework di destinazione](../../standard/frameworks.md) per cui aggiornare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-117">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

`-g|--global`

<span data-ttu-id="6a1c8-118">Specifica che l'aggiornamento è per uno strumento a livello utente.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-118">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="6a1c8-119">Non può essere usata con l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-119">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="6a1c8-120">Se non si specifica questa opzione, è necessario specificare l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-120">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="6a1c8-121">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-121">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="6a1c8-122">Specifica il percorso in cui è installato lo strumento globale.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-122">Specifies the location where the Global Tool is installed.</span></span> <span data-ttu-id="6a1c8-123">Il valore di PATH può essere assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-123">PATH can be absolute or relative.</span></span> <span data-ttu-id="6a1c8-124">Non può essere usata con l'opzione `--global`.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-124">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="6a1c8-125">Se non si specifica questa opzione, è necessario specificare l'opzione `--global`.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-125">If you don't specify this option, you must specify the `--global` option.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="6a1c8-126">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-126">Sets the verbosity level of the command.</span></span> <span data-ttu-id="6a1c8-127">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6a1c8-127">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="6a1c8-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="6a1c8-128">Examples</span></span>

<span data-ttu-id="6a1c8-129">Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/):</span><span class="sxs-lookup"><span data-stu-id="6a1c8-129">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool:</span></span>

`dotnet tool update -g dotnetsay`

<span data-ttu-id="6a1c8-130">Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) in una cartella di Windows specifica:</span><span class="sxs-lookup"><span data-stu-id="6a1c8-130">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool located on a specific Windows folder:</span></span>

`dotnet tool update dotnetsay --tool-path c:\global-tools`

<span data-ttu-id="6a1c8-131">Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) in una cartella di Linux/macOS specifica:</span><span class="sxs-lookup"><span data-stu-id="6a1c8-131">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool located on a specific Linux/macOS folder:</span></span>

`dotnet tool update dotnetsay --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="6a1c8-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a1c8-132">See also</span></span>

* [<span data-ttu-id="6a1c8-133">Strumenti globali .NET Core</span><span class="sxs-lookup"><span data-stu-id="6a1c8-133">.NET Core Global Tools</span></span>](global-tools.md)