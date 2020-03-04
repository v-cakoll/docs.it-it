---
title: Interfaccia della riga di comando di .NET Core
titleSuffix: ''
description: Panoramica del interfaccia della riga di comando di .NET Core e delle relative funzionalità.
ms.date: 02/13/2020
ms.openlocfilehash: d84f96889cabc3fb4521e39db25050aacdd11546
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156712"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="90e69-103">Panoramica di interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="90e69-103">.NET Core CLI overview</span></span>

<span data-ttu-id="90e69-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="90e69-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="90e69-105">L'interfaccia della riga di comando di .NET Core è una serie di procedure multipiattaforma per lo sviluppo, la compilazione, l'esecuzione e la pubblicazione di applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="90e69-105">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="90e69-106">Il interfaccia della riga di comando di .NET Core è incluso nel [.NET Core SDK](../sdk.md).</span><span class="sxs-lookup"><span data-stu-id="90e69-106">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="90e69-107">Per informazioni su come installare il .NET Core SDK, vedere [Install the .NET Core SDK](../install/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="90e69-107">To learn how to install the .NET Core SDK, see [Install the .NET Core SDK](../install/sdk.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="90e69-108">Comandi dell'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="90e69-108">CLI commands</span></span>

<span data-ttu-id="90e69-109">Per impostazione predefinita vengono installati i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="90e69-109">The following commands are installed by default:</span></span>

### <a name="basic-commands"></a><span data-ttu-id="90e69-110">Comandi di base</span><span class="sxs-lookup"><span data-stu-id="90e69-110">Basic commands</span></span>

- [<span data-ttu-id="90e69-111">Nuovo</span><span class="sxs-lookup"><span data-stu-id="90e69-111">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="90e69-112">restore</span><span class="sxs-lookup"><span data-stu-id="90e69-112">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="90e69-113">build</span><span class="sxs-lookup"><span data-stu-id="90e69-113">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="90e69-114">pubblica</span><span class="sxs-lookup"><span data-stu-id="90e69-114">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="90e69-115">run</span><span class="sxs-lookup"><span data-stu-id="90e69-115">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="90e69-116">test</span><span class="sxs-lookup"><span data-stu-id="90e69-116">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="90e69-117">vstest</span><span class="sxs-lookup"><span data-stu-id="90e69-117">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="90e69-118">pack</span><span class="sxs-lookup"><span data-stu-id="90e69-118">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="90e69-119">migrazione</span><span class="sxs-lookup"><span data-stu-id="90e69-119">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="90e69-120">clean</span><span class="sxs-lookup"><span data-stu-id="90e69-120">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="90e69-121">sln</span><span class="sxs-lookup"><span data-stu-id="90e69-121">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="90e69-122">help</span><span class="sxs-lookup"><span data-stu-id="90e69-122">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="90e69-123">store</span><span class="sxs-lookup"><span data-stu-id="90e69-123">store</span></span>](dotnet-store.md)

### <a name="project-modification-commands"></a><span data-ttu-id="90e69-124">Comandi di modifica dei progetti</span><span class="sxs-lookup"><span data-stu-id="90e69-124">Project modification commands</span></span>

- [<span data-ttu-id="90e69-125">add package</span><span class="sxs-lookup"><span data-stu-id="90e69-125">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="90e69-126">add reference</span><span class="sxs-lookup"><span data-stu-id="90e69-126">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="90e69-127">remove package</span><span class="sxs-lookup"><span data-stu-id="90e69-127">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="90e69-128">remove reference</span><span class="sxs-lookup"><span data-stu-id="90e69-128">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="90e69-129">list reference</span><span class="sxs-lookup"><span data-stu-id="90e69-129">list reference</span></span>](dotnet-list-reference.md)

### <a name="advanced-commands"></a><span data-ttu-id="90e69-130">Comandi avanzati</span><span class="sxs-lookup"><span data-stu-id="90e69-130">Advanced commands</span></span>

- [<span data-ttu-id="90e69-131">nuget delete</span><span class="sxs-lookup"><span data-stu-id="90e69-131">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="90e69-132">nuget locals</span><span class="sxs-lookup"><span data-stu-id="90e69-132">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="90e69-133">nuget push</span><span class="sxs-lookup"><span data-stu-id="90e69-133">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="90e69-134">msbuild</span><span class="sxs-lookup"><span data-stu-id="90e69-134">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="90e69-135">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="90e69-135">dotnet install script</span></span>](dotnet-install-script.md)

### <a name="tool-management-commands"></a><span data-ttu-id="90e69-136">Comandi di gestione degli strumenti</span><span class="sxs-lookup"><span data-stu-id="90e69-136">Tool management commands</span></span>

- [<span data-ttu-id="90e69-137">installazione dello strumento</span><span class="sxs-lookup"><span data-stu-id="90e69-137">tool install</span></span>](dotnet-tool-install.md)
- [<span data-ttu-id="90e69-138">Elenco strumenti</span><span class="sxs-lookup"><span data-stu-id="90e69-138">tool list</span></span>](dotnet-tool-list.md)
- [<span data-ttu-id="90e69-139">aggiornamento dello strumento</span><span class="sxs-lookup"><span data-stu-id="90e69-139">tool update</span></span>](dotnet-tool-update.md)
- <span data-ttu-id="90e69-140">[ripristino dello strumento](global-tools.md#install-a-local-tool) **disponibile a partire da .NET Core SDK 3,0**</span><span class="sxs-lookup"><span data-stu-id="90e69-140">[tool restore](global-tools.md#install-a-local-tool) **Available starting with .NET Core SDK 3.0**</span></span>
- <span data-ttu-id="90e69-141">[esecuzione dello strumento](global-tools.md#invoke-a-local-tool) **disponibile a partire da .NET Core SDK 3,0**</span><span class="sxs-lookup"><span data-stu-id="90e69-141">[tool run](global-tools.md#invoke-a-local-tool) **Available starting with .NET Core SDK 3.0**</span></span>
- [<span data-ttu-id="90e69-142">Disinstallazione dello strumento</span><span class="sxs-lookup"><span data-stu-id="90e69-142">tool uninstall</span></span>](dotnet-tool-uninstall.md)

<span data-ttu-id="90e69-143">Gli strumenti sono applicazioni console installate da pacchetti NuGet e vengono richiamate dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="90e69-143">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="90e69-144">È possibile scrivere strumenti manualmente oppure installare gli strumenti scritti da terze parti.</span><span class="sxs-lookup"><span data-stu-id="90e69-144">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="90e69-145">Gli strumenti sono noti anche come strumenti globali, strumenti per percorsi di strumenti e strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="90e69-145">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="90e69-146">Per altre informazioni, vedere [Cenni preliminari sugli strumenti di .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="90e69-146">For more information, see [.NET Core tools overview](global-tools.md).</span></span>

## <a name="command-structure"></a><span data-ttu-id="90e69-147">Struttura dei comandi</span><span class="sxs-lookup"><span data-stu-id="90e69-147">Command structure</span></span>

<span data-ttu-id="90e69-148">La struttura dei comandi dell'interfaccia della riga di comando è composta dal [driver ("dotnet")](#driver), dal [comando](#command) e, in alcuni casi, dagli [argomenti](#arguments) e dalle [opzioni](#options).</span><span class="sxs-lookup"><span data-stu-id="90e69-148">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="90e69-149">Questo modello può essere osservato nella maggior parte delle operazioni eseguite dalla riga di comando, inclusa la creazione di una nuova app console e la relativa esecuzione dalla riga di comando, come illustrato dai comandi seguenti quando vengono eseguiti da una directory denominata *my_app*:</span><span class="sxs-lookup"><span data-stu-id="90e69-149">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a><span data-ttu-id="90e69-150">Driver</span><span class="sxs-lookup"><span data-stu-id="90e69-150">Driver</span></span>

<span data-ttu-id="90e69-151">Il driver, denominato [dotnet](dotnet.md), ha due compiti: eseguire un'[app dipendente dal framework](../deploying/index.md) ed eseguire un comando.</span><span class="sxs-lookup"><span data-stu-id="90e69-151">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span>

<span data-ttu-id="90e69-152">Per eseguire un'applicazione dipendente dal framework, specificare l'app dopo il driver, ad esempio `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="90e69-152">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="90e69-153">Se si esegue il comando dalla cartella in cui si trova la DLL dell'app, è sufficiente eseguire `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="90e69-153">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="90e69-154">Se si vuole usare una versione specifica del runtime .NET Core, usare l'opzione `--fx-version <VERSION>` (vedere il riferimento per il [comando dotnet](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="90e69-154">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="90e69-155">Nel momento in cui si fornisce un comando al driver, `dotnet.exe` avvia il processo di esecuzione del comando dell'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="90e69-155">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="90e69-156">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="90e69-156">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="90e69-157">Come prima operazione, il driver determina la versione dell'SDK da usare.</span><span class="sxs-lookup"><span data-stu-id="90e69-157">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="90e69-158">Se non è presente alcun file [Global. JSON](global-json.md) , viene usata la versione più recente dell'SDK disponibile.</span><span class="sxs-lookup"><span data-stu-id="90e69-158">If there is no [global.json](global-json.md) file, the latest version of the SDK available is used.</span></span> <span data-ttu-id="90e69-159">Può essere una versione di anteprima o una versione stabile, a seconda di qual è la più recente disponibile nel computer.</span><span class="sxs-lookup"><span data-stu-id="90e69-159">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="90e69-160">Dopo aver determinato la versione del SDK il driver esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="90e69-160">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="90e69-161">Comando</span><span class="sxs-lookup"><span data-stu-id="90e69-161">Command</span></span>

<span data-ttu-id="90e69-162">Il comando esegue un'azione.</span><span class="sxs-lookup"><span data-stu-id="90e69-162">The command performs an action.</span></span> <span data-ttu-id="90e69-163">Ad esempio, `dotnet build` compila il codice.</span><span class="sxs-lookup"><span data-stu-id="90e69-163">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="90e69-164">`dotnet publish` pubblica il codice.</span><span class="sxs-lookup"><span data-stu-id="90e69-164">`dotnet publish` publishes code.</span></span> <span data-ttu-id="90e69-165">I comandi vengono implementati come un'applicazione console usando una convenzione `dotnet {command}`.</span><span class="sxs-lookup"><span data-stu-id="90e69-165">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="90e69-166">Argomenti</span><span class="sxs-lookup"><span data-stu-id="90e69-166">Arguments</span></span>

<span data-ttu-id="90e69-167">Gli argomenti passati alla riga di comando sono gli argomenti per il comando richiamato.</span><span class="sxs-lookup"><span data-stu-id="90e69-167">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="90e69-168">Quando si esegue `dotnet publish my_app.csproj`, ad esempio, l'argomento `my_app.csproj` indica il progetto da pubblicare e viene passato al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="90e69-168">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="90e69-169">Opzioni</span><span class="sxs-lookup"><span data-stu-id="90e69-169">Options</span></span>

<span data-ttu-id="90e69-170">Le opzioni passate alla riga di comando sono le opzioni per il comando richiamato.</span><span class="sxs-lookup"><span data-stu-id="90e69-170">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="90e69-171">Quando si esegue `dotnet publish --output /build_output`, ad esempio, l'opzione `--output` e il relativo valore vengono passati al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="90e69-171">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="see-also"></a><span data-ttu-id="90e69-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90e69-172">See also</span></span>

- [<span data-ttu-id="90e69-173">repository GitHub DotNet/SDK</span><span class="sxs-lookup"><span data-stu-id="90e69-173">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- <span data-ttu-id="90e69-174">[.NET Core installation guide](../install/sdk.md) (Guida all'installazione di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="90e69-174">[.NET Core installation guide](../install/sdk.md)</span></span>
