---
title: Interfaccia della riga di comando di .NET Core
titleSuffix: ''
description: Panoramica del interfaccia della riga di comando di .NET Core e delle relative funzionalità.
ms.date: 02/13/2020
ms.openlocfilehash: f92151c85b4816fef1859e84ad94945445db1854
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "86415970"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="7dee8-103">Panoramica dell'interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="7dee8-103">.NET Core CLI overview</span></span>

<span data-ttu-id="7dee8-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="7dee8-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="7dee8-105">L'interfaccia della riga di comando di .NET Core è una serie di procedure multipiattaforma per lo sviluppo, la compilazione, l'esecuzione e la pubblicazione di applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7dee8-105">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="7dee8-106">Il interfaccia della riga di comando di .NET Core è incluso nel [.NET Core SDK](../sdk.md).</span><span class="sxs-lookup"><span data-stu-id="7dee8-106">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="7dee8-107">Per informazioni su come installare il .NET Core SDK, vedere [installare .NET Core](../install/windows.md).</span><span class="sxs-lookup"><span data-stu-id="7dee8-107">To learn how to install the .NET Core SDK, see [Install .NET Core](../install/windows.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="7dee8-108">Comandi dell'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="7dee8-108">CLI commands</span></span>

<span data-ttu-id="7dee8-109">Per impostazione predefinita vengono installati i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7dee8-109">The following commands are installed by default:</span></span>

### <a name="basic-commands"></a><span data-ttu-id="7dee8-110">Comandi di base</span><span class="sxs-lookup"><span data-stu-id="7dee8-110">Basic commands</span></span>

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

### <a name="project-modification-commands"></a><span data-ttu-id="7dee8-111">Comandi di modifica dei progetti</span><span class="sxs-lookup"><span data-stu-id="7dee8-111">Project modification commands</span></span>

- [`add package`](dotnet-add-package.md)
- [`add reference`](dotnet-add-reference.md)
- [`remove package`](dotnet-remove-package.md)
- [`remove reference`](dotnet-remove-reference.md)
- [`list reference`](dotnet-list-reference.md)

### <a name="advanced-commands"></a><span data-ttu-id="7dee8-112">Comandi avanzati</span><span class="sxs-lookup"><span data-stu-id="7dee8-112">Advanced commands</span></span>

- [`nuget delete`](dotnet-nuget-delete.md)
- [`nuget locals`](dotnet-nuget-locals.md)
- [`nuget push`](dotnet-nuget-push.md)
- [`msbuild`](dotnet-msbuild.md)
- [`dotnet install script`](dotnet-install-script.md)

### <a name="tool-management-commands"></a><span data-ttu-id="7dee8-113">Comandi di gestione degli strumenti</span><span class="sxs-lookup"><span data-stu-id="7dee8-113">Tool management commands</span></span>

- [`tool install`](dotnet-tool-install.md)
- [`tool list`](dotnet-tool-list.md)
- [`tool update`](dotnet-tool-update.md)
- <span data-ttu-id="7dee8-114">[`tool restore`](global-tools.md#install-a-local-tool)Disponibile a partire da .NET Core SDK 3,0.</span><span class="sxs-lookup"><span data-stu-id="7dee8-114">[`tool restore`](global-tools.md#install-a-local-tool) Available since .NET Core SDK 3.0.</span></span>
- <span data-ttu-id="7dee8-115">[`tool run`](global-tools.md#invoke-a-local-tool)Disponibile a partire da .NET Core SDK 3,0.</span><span class="sxs-lookup"><span data-stu-id="7dee8-115">[`tool run`](global-tools.md#invoke-a-local-tool) Available since .NET Core SDK 3.0.</span></span>
- [`tool uninstall`](dotnet-tool-uninstall.md)

<span data-ttu-id="7dee8-116">Gli strumenti sono applicazioni console installate da pacchetti NuGet e vengono richiamate dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="7dee8-116">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="7dee8-117">È possibile scrivere strumenti manualmente oppure installare gli strumenti scritti da terze parti.</span><span class="sxs-lookup"><span data-stu-id="7dee8-117">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="7dee8-118">Gli strumenti sono noti anche come strumenti globali, strumenti per percorsi di strumenti e strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="7dee8-118">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="7dee8-119">Per altre informazioni, vedere [Cenni preliminari sugli strumenti di .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7dee8-119">For more information, see [.NET Core tools overview](global-tools.md).</span></span>

## <a name="command-structure"></a><span data-ttu-id="7dee8-120">Struttura dei comandi</span><span class="sxs-lookup"><span data-stu-id="7dee8-120">Command structure</span></span>

<span data-ttu-id="7dee8-121">La struttura dei comandi dell'interfaccia della riga di comando è composta dal [driver ("dotnet")](#driver), dal [comando](#command) e, in alcuni casi, dagli [argomenti](#arguments) e dalle [opzioni](#options).</span><span class="sxs-lookup"><span data-stu-id="7dee8-121">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="7dee8-122">Questo modello può essere osservato nella maggior parte delle operazioni eseguite dalla riga di comando, inclusa la creazione di una nuova app console e la relativa esecuzione dalla riga di comando, come illustrato dai comandi seguenti quando vengono eseguiti da una directory denominata *my_app*:</span><span class="sxs-lookup"><span data-stu-id="7dee8-122">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a><span data-ttu-id="7dee8-123">Driver</span><span class="sxs-lookup"><span data-stu-id="7dee8-123">Driver</span></span>

<span data-ttu-id="7dee8-124">Il driver, denominato [dotnet](dotnet.md), ha due compiti: eseguire un'[app dipendente dal framework](../deploying/index.md) ed eseguire un comando.</span><span class="sxs-lookup"><span data-stu-id="7dee8-124">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span>

<span data-ttu-id="7dee8-125">Per eseguire un'applicazione dipendente dal framework, specificare l'app dopo il driver, ad esempio `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="7dee8-125">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="7dee8-126">Se si esegue il comando dalla cartella in cui si trova la DLL dell'app, è sufficiente eseguire `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="7dee8-126">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="7dee8-127">Se si vuole usare una versione specifica del runtime .NET Core, usare l'opzione `--fx-version <VERSION>` (vedere il riferimento per il [comando dotnet](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="7dee8-127">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="7dee8-128">Nel momento in cui si fornisce un comando al driver, `dotnet.exe` avvia il processo di esecuzione del comando dell'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="7dee8-128">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="7dee8-129">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7dee8-129">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="7dee8-130">Come prima operazione, il driver determina la versione dell'SDK da usare.</span><span class="sxs-lookup"><span data-stu-id="7dee8-130">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="7dee8-131">Se non è presente alcun [global.jsnel](global-json.md) file, viene usata la versione più recente dell'SDK disponibile.</span><span class="sxs-lookup"><span data-stu-id="7dee8-131">If there is no [global.json](global-json.md) file, the latest version of the SDK available is used.</span></span> <span data-ttu-id="7dee8-132">Può essere una versione di anteprima o una versione stabile, a seconda di qual è la più recente disponibile nel computer.</span><span class="sxs-lookup"><span data-stu-id="7dee8-132">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="7dee8-133">Dopo aver determinato la versione del SDK il driver esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="7dee8-133">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="7dee8-134">Comando</span><span class="sxs-lookup"><span data-stu-id="7dee8-134">Command</span></span>

<span data-ttu-id="7dee8-135">Il comando esegue un'azione.</span><span class="sxs-lookup"><span data-stu-id="7dee8-135">The command performs an action.</span></span> <span data-ttu-id="7dee8-136">Ad esempio, `dotnet build` compila il codice.</span><span class="sxs-lookup"><span data-stu-id="7dee8-136">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="7dee8-137">`dotnet publish` pubblica il codice.</span><span class="sxs-lookup"><span data-stu-id="7dee8-137">`dotnet publish` publishes code.</span></span> <span data-ttu-id="7dee8-138">I comandi vengono implementati come un'applicazione console usando una convenzione `dotnet {command}`.</span><span class="sxs-lookup"><span data-stu-id="7dee8-138">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="7dee8-139">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7dee8-139">Arguments</span></span>

<span data-ttu-id="7dee8-140">Gli argomenti passati alla riga di comando sono gli argomenti per il comando richiamato.</span><span class="sxs-lookup"><span data-stu-id="7dee8-140">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="7dee8-141">Ad esempio, quando si esegue `dotnet publish my_app.csproj` , l' `my_app.csproj` argomento indica il progetto da pubblicare e viene passato al `publish` comando.</span><span class="sxs-lookup"><span data-stu-id="7dee8-141">For example, when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="7dee8-142">Opzioni</span><span class="sxs-lookup"><span data-stu-id="7dee8-142">Options</span></span>

<span data-ttu-id="7dee8-143">Le opzioni passate alla riga di comando sono le opzioni per il comando richiamato.</span><span class="sxs-lookup"><span data-stu-id="7dee8-143">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="7dee8-144">Ad esempio, quando si esegue `dotnet publish --output /build_output` , l' `--output` opzione e il relativo valore vengono passati al `publish` comando.</span><span class="sxs-lookup"><span data-stu-id="7dee8-144">For example, when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="see-also"></a><span data-ttu-id="7dee8-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7dee8-145">See also</span></span>

- [<span data-ttu-id="7dee8-146">repository GitHub DotNet/SDK</span><span class="sxs-lookup"><span data-stu-id="7dee8-146">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- <span data-ttu-id="7dee8-147">[.NET Core installation guide](../install/windows.md) (Guida all'installazione di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="7dee8-147">[.NET Core installation guide](../install/windows.md)</span></span>
