---
title: Comando di ripristino dello strumento dotnet
description: Il comando dotnet tool restore installa nel computer gli strumenti locali .NET Core che rientrano nell'ambito della directory corrente.
ms.date: 02/14/2020
ms.openlocfilehash: a518c2d45bbe9522bddfed4bbef61b30f1ad634b
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463338"
---
# <a name="dotnet-tool-restore"></a><span data-ttu-id="4014c-103">dotnet tool restore</span><span class="sxs-lookup"><span data-stu-id="4014c-103">dotnet tool restore</span></span>

<span data-ttu-id="4014c-104">**Questo articolo si applica a:** ✔️ .NET Core 3.0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="4014c-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="4014c-105">Nome</span><span class="sxs-lookup"><span data-stu-id="4014c-105">Name</span></span>

<span data-ttu-id="4014c-106">`dotnet tool restore`- Installa nel computer gli strumenti locali .NET Core che rientrano nell'ambito della directory corrente.- Installs on your machine the .NET Core local tools that are in scope for the current directory.</span><span class="sxs-lookup"><span data-stu-id="4014c-106">`dotnet tool restore` - Installs on your machine the .NET Core local tools that are in scope for the current directory.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4014c-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4014c-107">Synopsis</span></span>

```dotnetcli
dotnet tool restore <PACKAGE_NAME>
    [--configfile <FILE>] [--add-source <SOURCE>]
    [tool-manifest <PATH_TO_MANIFEST_FILE>] [--disable-parallel]
    [--ignore-failed-sources] [--no-cache] [--interactive]
    [-v|--verbosity <LEVEL>]

dotnet tool restore -h|--help
```

## <a name="description"></a><span data-ttu-id="4014c-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4014c-108">Description</span></span>

<span data-ttu-id="4014c-109">Il `dotnet tool restore` comando trova il file manifesto dello strumento che si trova nell'ambito della directory corrente e installa gli strumenti elencati in esso.</span><span class="sxs-lookup"><span data-stu-id="4014c-109">The `dotnet tool restore` command finds the tool manifest file that is in scope for the current directory and installs the tools that are listed in it.</span></span> <span data-ttu-id="4014c-110">Per informazioni sui file manifesto, consultate [Installare uno strumento locale](global-tools.md#install-a-local-tool) e [Richiamare uno strumento locale.](global-tools.md#invoke-a-local-tool)</span><span class="sxs-lookup"><span data-stu-id="4014c-110">For information about manifest files, see [Install a local tool](global-tools.md#install-a-local-tool) and [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="4014c-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4014c-111">Arguments</span></span>

- **`PACKAGE_NAME`**

<span data-ttu-id="4014c-112">Nome/ID del pacchetto NuGet che contiene lo strumento .NET Core da installare.</span><span class="sxs-lookup"><span data-stu-id="4014c-112">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="4014c-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4014c-113">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="4014c-114">File di configurazione NuGet (*nuget.config*) da usare.</span><span class="sxs-lookup"><span data-stu-id="4014c-114">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="4014c-115">Aggiunge un'altra origine pacchetto NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="4014c-115">Adds an additional NuGet package source to use during installation.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="4014c-116">Percorso del file manifesto.</span><span class="sxs-lookup"><span data-stu-id="4014c-116">Path to the manifest file.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="4014c-117">Impedire il ripristino di più progetti in parallelo.</span><span class="sxs-lookup"><span data-stu-id="4014c-117">Prevent restoring multiple projects in parallel.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="4014c-118">Considerare gli errori di origine del pacchetto come avvisi.</span><span class="sxs-lookup"><span data-stu-id="4014c-118">Treat package source failures as warnings.</span></span>

- **`--no-cache`**

  <span data-ttu-id="4014c-119">Non memorizzare nella cache i pacchetti e le richieste http.</span><span class="sxs-lookup"><span data-stu-id="4014c-119">Do not cache packages and http requests.</span></span>

- **`--interactive`**

  <span data-ttu-id="4014c-120">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione).</span><span class="sxs-lookup"><span data-stu-id="4014c-120">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`-h|--help`**

  <span data-ttu-id="4014c-121">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="4014c-121">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="4014c-122">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="4014c-122">Sets the verbosity level of the command.</span></span> <span data-ttu-id="4014c-123">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="4014c-123">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="example"></a><span data-ttu-id="4014c-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="4014c-124">Example</span></span>

- **`dotnet tool restore`**

  <span data-ttu-id="4014c-125">Ripristina gli strumenti locali per la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="4014c-125">Restores local tools for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="4014c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4014c-126">See also</span></span>

- [<span data-ttu-id="4014c-127">Strumenti .NET Core</span><span class="sxs-lookup"><span data-stu-id="4014c-127">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="4014c-128">Esercitazione: Installare e usare uno strumento locale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core local tool using the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="4014c-128">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
