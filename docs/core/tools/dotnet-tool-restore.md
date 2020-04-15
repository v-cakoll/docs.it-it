---
title: Comando di ripristino dello strumento dotnet
description: Il comando dotnet tool restore installa nel computer gli strumenti locali .NET Core che rientrano nell'ambito della directory corrente.
ms.date: 02/14/2020
ms.openlocfilehash: 0d1e67ec809ddd725721698cc741f9acc99e1ce7
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389610"
---
# <a name="dotnet-tool-restore"></a><span data-ttu-id="02a18-103">dotnet tool restore</span><span class="sxs-lookup"><span data-stu-id="02a18-103">dotnet tool restore</span></span>

<span data-ttu-id="02a18-104">**Questo articolo si applica a:** ✔️ .NET Core 3.0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="02a18-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="02a18-105">Nome</span><span class="sxs-lookup"><span data-stu-id="02a18-105">Name</span></span>

<span data-ttu-id="02a18-106">`dotnet tool restore`- Installa nel computer gli strumenti locali .NET Core che rientrano nell'ambito della directory corrente.- Installs on your machine the .NET Core local tools that are in scope for the current directory.</span><span class="sxs-lookup"><span data-stu-id="02a18-106">`dotnet tool restore` - Installs on your machine the .NET Core local tools that are in scope for the current directory.</span></span>

## <a name="synopsis"></a><span data-ttu-id="02a18-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="02a18-107">Synopsis</span></span>

```dotnetcli
dotnet tool restore <PACKAGE_NAME>
    [--configfile] [--add-source] [tool-manifest]
    [--disable-parallel] [--ignore-failed-sources]
    [--no-cache] [--interactive] [-v|--verbosity]

dotnet tool restore <-h|--help>
```

## <a name="description"></a><span data-ttu-id="02a18-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02a18-108">Description</span></span>

<span data-ttu-id="02a18-109">Il `dotnet tool restore` comando trova il file manifesto dello strumento che si trova nell'ambito della directory corrente e installa gli strumenti elencati in esso.</span><span class="sxs-lookup"><span data-stu-id="02a18-109">The `dotnet tool restore` command finds the tool manifest file that is in scope for the current directory and installs the tools that are listed in it.</span></span> <span data-ttu-id="02a18-110">Per informazioni sui file manifesto, consultate [Installare uno strumento locale](global-tools.md#install-a-local-tool) e [Richiamare uno strumento locale.](global-tools.md#invoke-a-local-tool)</span><span class="sxs-lookup"><span data-stu-id="02a18-110">For information about manifest files, see [Install a local tool](global-tools.md#install-a-local-tool) and [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="02a18-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="02a18-111">Arguments</span></span>

- **`PACKAGE_NAME`**

<span data-ttu-id="02a18-112">Nome/ID del pacchetto NuGet che contiene lo strumento .NET Core da installare.</span><span class="sxs-lookup"><span data-stu-id="02a18-112">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="02a18-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="02a18-113">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="02a18-114">File di configurazione NuGet (*nuget.config*) da usare.</span><span class="sxs-lookup"><span data-stu-id="02a18-114">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="02a18-115">Aggiunge un'altra origine pacchetto NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="02a18-115">Adds an additional NuGet package source to use during installation.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="02a18-116">Percorso del file manifesto.</span><span class="sxs-lookup"><span data-stu-id="02a18-116">Path to the manifest file.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="02a18-117">Impedire il ripristino di più progetti in parallelo.</span><span class="sxs-lookup"><span data-stu-id="02a18-117">Prevent restoring multiple projects in parallel.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="02a18-118">Considerare gli errori di origine del pacchetto come avvisi.</span><span class="sxs-lookup"><span data-stu-id="02a18-118">Treat package source failures as warnings.</span></span>

- **`--no-cache`**

  <span data-ttu-id="02a18-119">Non memorizzare nella cache i pacchetti e le richieste http.</span><span class="sxs-lookup"><span data-stu-id="02a18-119">Do not cache packages and http requests.</span></span>

- **`--interactive`**

  <span data-ttu-id="02a18-120">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione).</span><span class="sxs-lookup"><span data-stu-id="02a18-120">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`-h|--help`**

  <span data-ttu-id="02a18-121">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="02a18-121">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="02a18-122">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="02a18-122">Sets the verbosity level of the command.</span></span> <span data-ttu-id="02a18-123">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="02a18-123">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="example"></a><span data-ttu-id="02a18-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="02a18-124">Example</span></span>

- **`dotnet tool restore`**

  <span data-ttu-id="02a18-125">Ripristina gli strumenti locali per la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="02a18-125">Restores local tools for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="02a18-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02a18-126">See also</span></span>

- [<span data-ttu-id="02a18-127">Strumenti .NET Core</span><span class="sxs-lookup"><span data-stu-id="02a18-127">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="02a18-128">Esercitazione: Installare e usare uno strumento locale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core local tool using the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="02a18-128">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
