---
title: Interfaccia della riga di comando di .NET Core
titleSuffix: ''
description: Panoramica dell'interfaccia della riga di comando di .NET Core e delle relative funzionalità.
ms.date: 02/13/2020
ms.openlocfilehash: ac5988bacbef41326f2501a2cff6c3f5aa0be798
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80110841"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="a2b73-103">Panoramica dell'interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="a2b73-103">.NET Core CLI overview</span></span>

<span data-ttu-id="a2b73-104">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="a2b73-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="a2b73-105">L'interfaccia della riga di comando (CLI) di .NET Core è una catena di strumenti multipiattaforma per lo sviluppo, la compilazione, l'esecuzione e la pubblicazione di applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a2b73-105">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="a2b73-106">L'interfaccia della riga di comando di .NET Core è inclusa in [.NET Core SDK.](../sdk.md)</span><span class="sxs-lookup"><span data-stu-id="a2b73-106">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="a2b73-107">Per informazioni su come installare .NET Core SDK, vedere [Installare .NET Core SDK](../install/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="a2b73-107">To learn how to install the .NET Core SDK, see [Install the .NET Core SDK](../install/sdk.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="a2b73-108">Comandi dell'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="a2b73-108">CLI commands</span></span>

<span data-ttu-id="a2b73-109">Per impostazione predefinita vengono installati i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2b73-109">The following commands are installed by default:</span></span>

### <a name="basic-commands"></a><span data-ttu-id="a2b73-110">Comandi di base</span><span class="sxs-lookup"><span data-stu-id="a2b73-110">Basic commands</span></span>

- [`new`](dotnet-new.md)
- [`restore`](dotnet-restore.md)
- [`build`](dotnet-build.md)
- [`publish`](dotnet-publish.md)
- [`run`](dotnet-run.md)
- [`test`](dotnet-test.md)
- [`vstest`](dotnet-vstest.md)
- [`pack`](dotnet-pack.md)
- [`migrate`](dotnet-migrate.md)
- [`clean`](dotnet-clean.md)
- [`sln`](dotnet-sln.md)
- [`help`](dotnet-help.md)
- [`store`](dotnet-store.md)

### <a name="project-modification-commands"></a><span data-ttu-id="a2b73-111">Comandi di modifica dei progetti</span><span class="sxs-lookup"><span data-stu-id="a2b73-111">Project modification commands</span></span>

- [`add package`](dotnet-add-package.md)
- [`add reference`](dotnet-add-reference.md)
- [`remove package`](dotnet-remove-package.md)
- [`remove reference`](dotnet-remove-reference.md)
- [`list reference`](dotnet-list-reference.md)

### <a name="advanced-commands"></a><span data-ttu-id="a2b73-112">Comandi avanzati</span><span class="sxs-lookup"><span data-stu-id="a2b73-112">Advanced commands</span></span>

- [`nuget delete`](dotnet-nuget-delete.md)
- [`nuget locals`](dotnet-nuget-locals.md)
- [`nuget push`](dotnet-nuget-push.md)
- [`msbuild`](dotnet-msbuild.md)
- [`dotnet install script`](dotnet-install-script.md)

### <a name="tool-management-commands"></a><span data-ttu-id="a2b73-113">Comandi di gestione degli strumenti</span><span class="sxs-lookup"><span data-stu-id="a2b73-113">Tool management commands</span></span>

- [`tool install`](dotnet-tool-install.md)
- [`tool list`](dotnet-tool-list.md)
- [`tool update`](dotnet-tool-update.md)
- <span data-ttu-id="a2b73-114">[`tool restore`](global-tools.md#install-a-local-tool)Disponibile da .NET Core SDK 3.0.</span><span class="sxs-lookup"><span data-stu-id="a2b73-114">[`tool restore`](global-tools.md#install-a-local-tool) Available since .NET Core SDK 3.0.</span></span>
- <span data-ttu-id="a2b73-115">[`tool run`](global-tools.md#invoke-a-local-tool)Disponibile da .NET Core SDK 3.0.</span><span class="sxs-lookup"><span data-stu-id="a2b73-115">[`tool run`](global-tools.md#invoke-a-local-tool) Available since .NET Core SDK 3.0.</span></span>
- [`tool uninstall`](dotnet-tool-uninstall.md)

<span data-ttu-id="a2b73-116">Gli strumenti sono applicazioni console installate da pacchetti NuGet e richiamate dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a2b73-116">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="a2b73-117">È possibile scrivere strumenti da soli o installare strumenti scritti da terze parti.</span><span class="sxs-lookup"><span data-stu-id="a2b73-117">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="a2b73-118">Gli strumenti sono noti anche come strumenti globali, strumenti per il percorso degli strumenti e strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="a2b73-118">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="a2b73-119">Per ulteriori informazioni, vedere [Panoramica degli strumenti .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a2b73-119">For more information, see [.NET Core tools overview](global-tools.md).</span></span>

## <a name="command-structure"></a><span data-ttu-id="a2b73-120">Struttura dei comandi</span><span class="sxs-lookup"><span data-stu-id="a2b73-120">Command structure</span></span>

<span data-ttu-id="a2b73-121">La struttura dei comandi dell'interfaccia della riga di comando è composta dal [driver ("dotnet")](#driver), dal [comando](#command) e, in alcuni casi, dagli [argomenti](#arguments) e dalle [opzioni](#options).</span><span class="sxs-lookup"><span data-stu-id="a2b73-121">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="a2b73-122">Questo modello può essere osservato nella maggior parte delle operazioni eseguite dalla riga di comando, inclusa la creazione di una nuova app console e la relativa esecuzione dalla riga di comando, come illustrato dai comandi seguenti quando vengono eseguiti da una directory denominata *my_app*:</span><span class="sxs-lookup"><span data-stu-id="a2b73-122">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a><span data-ttu-id="a2b73-123">Driver</span><span class="sxs-lookup"><span data-stu-id="a2b73-123">Driver</span></span>

<span data-ttu-id="a2b73-124">Il driver, denominato [dotnet](dotnet.md), ha due compiti: eseguire un'[app dipendente dal framework](../deploying/index.md) ed eseguire un comando.</span><span class="sxs-lookup"><span data-stu-id="a2b73-124">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span>

<span data-ttu-id="a2b73-125">Per eseguire un'applicazione dipendente dal framework, specificare l'app dopo il driver, ad esempio `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="a2b73-125">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="a2b73-126">Se si esegue il comando dalla cartella in cui si trova la DLL dell'app, è sufficiente eseguire `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="a2b73-126">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="a2b73-127">Se si vuole usare una versione specifica del runtime .NET Core, usare l'opzione `--fx-version <VERSION>` (vedere il riferimento per il [comando dotnet](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="a2b73-127">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="a2b73-128">Nel momento in cui si fornisce un comando al driver, `dotnet.exe` avvia il processo di esecuzione del comando dell'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="a2b73-128">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="a2b73-129">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a2b73-129">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="a2b73-130">Come prima operazione, il driver determina la versione dell'SDK da usare.</span><span class="sxs-lookup"><span data-stu-id="a2b73-130">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="a2b73-131">Se non è presente alcun file [global.json,](global-json.md) viene utilizzata la versione più recente dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="a2b73-131">If there is no [global.json](global-json.md) file, the latest version of the SDK available is used.</span></span> <span data-ttu-id="a2b73-132">Può essere una versione di anteprima o una versione stabile, a seconda di qual è la più recente disponibile nel computer.</span><span class="sxs-lookup"><span data-stu-id="a2b73-132">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="a2b73-133">Dopo aver determinato la versione del SDK il driver esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="a2b73-133">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="a2b73-134">Comando</span><span class="sxs-lookup"><span data-stu-id="a2b73-134">Command</span></span>

<span data-ttu-id="a2b73-135">Il comando esegue un'azione.</span><span class="sxs-lookup"><span data-stu-id="a2b73-135">The command performs an action.</span></span> <span data-ttu-id="a2b73-136">Ad esempio, `dotnet build` compila il codice.</span><span class="sxs-lookup"><span data-stu-id="a2b73-136">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="a2b73-137">`dotnet publish` pubblica il codice.</span><span class="sxs-lookup"><span data-stu-id="a2b73-137">`dotnet publish` publishes code.</span></span> <span data-ttu-id="a2b73-138">I comandi vengono implementati come un'applicazione console usando una convenzione `dotnet {command}`.</span><span class="sxs-lookup"><span data-stu-id="a2b73-138">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="a2b73-139">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a2b73-139">Arguments</span></span>

<span data-ttu-id="a2b73-140">Gli argomenti passati alla riga di comando sono gli argomenti per il comando richiamato.</span><span class="sxs-lookup"><span data-stu-id="a2b73-140">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="a2b73-141">Ad esempio, quando `dotnet publish my_app.csproj`si `my_app.csproj` esegue , l'argomento indica il `publish` progetto da pubblicare e viene passato al comando.</span><span class="sxs-lookup"><span data-stu-id="a2b73-141">For example, when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="a2b73-142">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a2b73-142">Options</span></span>

<span data-ttu-id="a2b73-143">Le opzioni passate alla riga di comando sono le opzioni per il comando richiamato.</span><span class="sxs-lookup"><span data-stu-id="a2b73-143">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="a2b73-144">Ad esempio, quando `dotnet publish --output /build_output`si `--output` esegue , l'opzione `publish` e il relativo valore vengono passati al comando.</span><span class="sxs-lookup"><span data-stu-id="a2b73-144">For example, when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2b73-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2b73-145">See also</span></span>

- [<span data-ttu-id="a2b73-146">repository GitHub dotnet/sdk</span><span class="sxs-lookup"><span data-stu-id="a2b73-146">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- <span data-ttu-id="a2b73-147">[.NET Core installation guide](../install/sdk.md) (Guida all'installazione di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="a2b73-147">[.NET Core installation guide](../install/sdk.md)</span></span>
