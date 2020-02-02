---
title: Interfaccia della riga di comando di .NET Core
titleSuffix: ''
description: Panoramica del interfaccia della riga di comando di .NET Core e delle relative funzionalità.
ms.date: 08/14/2017
ms.openlocfilehash: b0a8e0dd8cf77bb6f7567c27e9972f62515ec0f2
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920488"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="3b188-103">Panoramica di interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="3b188-103">.NET Core CLI overview</span></span>

<span data-ttu-id="3b188-104">L'interfaccia della riga di comando di .NET Core è una serie di procedure multipiattaforma per lo sviluppo, la compilazione, l'esecuzione e la pubblicazione di applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3b188-104">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="3b188-105">Il interfaccia della riga di comando di .NET Core è incluso nel [.NET Core SDK](../sdk.md).</span><span class="sxs-lookup"><span data-stu-id="3b188-105">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="3b188-106">Per informazioni su come installare il .NET Core SDK, vedere [Install the .NET Core SDK](../install/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="3b188-106">To learn how to install the .NET Core SDK, see [Install the .NET Core SDK](../install/sdk.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="3b188-107">Comandi dell'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="3b188-107">CLI commands</span></span>

<span data-ttu-id="3b188-108">Per impostazione predefinita vengono installati i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b188-108">The following commands are installed by default:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="3b188-109">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="3b188-109">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="3b188-110">**Comandi di base**</span><span class="sxs-lookup"><span data-stu-id="3b188-110">**Basic commands**</span></span>

- [<span data-ttu-id="3b188-111">new</span><span class="sxs-lookup"><span data-stu-id="3b188-111">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="3b188-112">restore</span><span class="sxs-lookup"><span data-stu-id="3b188-112">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="3b188-113">build</span><span class="sxs-lookup"><span data-stu-id="3b188-113">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="3b188-114">publish</span><span class="sxs-lookup"><span data-stu-id="3b188-114">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="3b188-115">run</span><span class="sxs-lookup"><span data-stu-id="3b188-115">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="3b188-116">test</span><span class="sxs-lookup"><span data-stu-id="3b188-116">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="3b188-117">vstest</span><span class="sxs-lookup"><span data-stu-id="3b188-117">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="3b188-118">pack</span><span class="sxs-lookup"><span data-stu-id="3b188-118">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="3b188-119">migrate</span><span class="sxs-lookup"><span data-stu-id="3b188-119">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="3b188-120">clean</span><span class="sxs-lookup"><span data-stu-id="3b188-120">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="3b188-121">sln</span><span class="sxs-lookup"><span data-stu-id="3b188-121">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="3b188-122">help</span><span class="sxs-lookup"><span data-stu-id="3b188-122">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="3b188-123">store</span><span class="sxs-lookup"><span data-stu-id="3b188-123">store</span></span>](dotnet-store.md)

<span data-ttu-id="3b188-124">**Comandi per la modifica dei progetti**</span><span class="sxs-lookup"><span data-stu-id="3b188-124">**Project modification commands**</span></span>

- [<span data-ttu-id="3b188-125">add package</span><span class="sxs-lookup"><span data-stu-id="3b188-125">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="3b188-126">add reference</span><span class="sxs-lookup"><span data-stu-id="3b188-126">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="3b188-127">remove package</span><span class="sxs-lookup"><span data-stu-id="3b188-127">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="3b188-128">remove reference</span><span class="sxs-lookup"><span data-stu-id="3b188-128">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="3b188-129">list reference</span><span class="sxs-lookup"><span data-stu-id="3b188-129">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="3b188-130">**Comandi avanzati**</span><span class="sxs-lookup"><span data-stu-id="3b188-130">**Advanced commands**</span></span>

- [<span data-ttu-id="3b188-131">nuget delete</span><span class="sxs-lookup"><span data-stu-id="3b188-131">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="3b188-132">nuget locals</span><span class="sxs-lookup"><span data-stu-id="3b188-132">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="3b188-133">nuget push</span><span class="sxs-lookup"><span data-stu-id="3b188-133">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="3b188-134">msbuild</span><span class="sxs-lookup"><span data-stu-id="3b188-134">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="3b188-135">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="3b188-135">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3b188-136">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3b188-136">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="3b188-137">**Comandi di base**</span><span class="sxs-lookup"><span data-stu-id="3b188-137">**Basic commands**</span></span>

- [<span data-ttu-id="3b188-138">new</span><span class="sxs-lookup"><span data-stu-id="3b188-138">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="3b188-139">restore</span><span class="sxs-lookup"><span data-stu-id="3b188-139">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="3b188-140">build</span><span class="sxs-lookup"><span data-stu-id="3b188-140">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="3b188-141">publish</span><span class="sxs-lookup"><span data-stu-id="3b188-141">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="3b188-142">run</span><span class="sxs-lookup"><span data-stu-id="3b188-142">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="3b188-143">test</span><span class="sxs-lookup"><span data-stu-id="3b188-143">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="3b188-144">vstest</span><span class="sxs-lookup"><span data-stu-id="3b188-144">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="3b188-145">pack</span><span class="sxs-lookup"><span data-stu-id="3b188-145">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="3b188-146">migrate</span><span class="sxs-lookup"><span data-stu-id="3b188-146">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="3b188-147">clean</span><span class="sxs-lookup"><span data-stu-id="3b188-147">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="3b188-148">sln</span><span class="sxs-lookup"><span data-stu-id="3b188-148">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="3b188-149">**Comandi per la modifica dei progetti**</span><span class="sxs-lookup"><span data-stu-id="3b188-149">**Project modification commands**</span></span>

- [<span data-ttu-id="3b188-150">add package</span><span class="sxs-lookup"><span data-stu-id="3b188-150">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="3b188-151">add reference</span><span class="sxs-lookup"><span data-stu-id="3b188-151">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="3b188-152">remove package</span><span class="sxs-lookup"><span data-stu-id="3b188-152">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="3b188-153">remove reference</span><span class="sxs-lookup"><span data-stu-id="3b188-153">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="3b188-154">list reference</span><span class="sxs-lookup"><span data-stu-id="3b188-154">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="3b188-155">**Comandi avanzati**</span><span class="sxs-lookup"><span data-stu-id="3b188-155">**Advanced commands**</span></span>

- [<span data-ttu-id="3b188-156">nuget delete</span><span class="sxs-lookup"><span data-stu-id="3b188-156">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="3b188-157">nuget locals</span><span class="sxs-lookup"><span data-stu-id="3b188-157">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="3b188-158">nuget push</span><span class="sxs-lookup"><span data-stu-id="3b188-158">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="3b188-159">msbuild</span><span class="sxs-lookup"><span data-stu-id="3b188-159">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="3b188-160">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="3b188-160">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="3b188-161">L'interfaccia della riga di comando adotta un modello di estendibilità che consente di specificare altri strumenti per i progetti.</span><span class="sxs-lookup"><span data-stu-id="3b188-161">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="3b188-162">Per altre informazioni, vedere l'argomento [Modello di estendibilità dell'interfaccia della riga di comando di .NET Core](extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="3b188-162">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="3b188-163">Struttura dei comandi</span><span class="sxs-lookup"><span data-stu-id="3b188-163">Command structure</span></span>

<span data-ttu-id="3b188-164">La struttura dei comandi dell'interfaccia della riga di comando è composta dal [driver ("dotnet")](#driver), dal [comando](#command) e, in alcuni casi, dagli [argomenti](#arguments) e dalle [opzioni](#options).</span><span class="sxs-lookup"><span data-stu-id="3b188-164">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="3b188-165">Questo modello può essere osservato nella maggior parte delle operazioni eseguite dalla riga di comando, inclusa la creazione di una nuova app console e la relativa esecuzione dalla riga di comando, come illustrato dai comandi seguenti quando vengono eseguiti da una directory denominata *my_app*:</span><span class="sxs-lookup"><span data-stu-id="3b188-165">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="3b188-166">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="3b188-166">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3b188-167">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3b188-167">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="3b188-168">Driver</span><span class="sxs-lookup"><span data-stu-id="3b188-168">Driver</span></span>

<span data-ttu-id="3b188-169">Il driver, denominato [dotnet](dotnet.md), ha due compiti: eseguire un'[app dipendente dal framework](../deploying/index.md) ed eseguire un comando.</span><span class="sxs-lookup"><span data-stu-id="3b188-169">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="3b188-170">Per eseguire un'applicazione dipendente dal framework, specificare l'app dopo il driver, ad esempio `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="3b188-170">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="3b188-171">Se si esegue il comando dalla cartella in cui si trova la DLL dell'app, è sufficiente eseguire `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="3b188-171">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="3b188-172">Se si vuole usare una versione specifica del runtime .NET Core, usare l'opzione `--fx-version <VERSION>` (vedere il riferimento per il [comando dotnet](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="3b188-172">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="3b188-173">Nel momento in cui si fornisce un comando al driver, `dotnet.exe` avvia il processo di esecuzione del comando dell'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="3b188-173">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="3b188-174">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3b188-174">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="3b188-175">Come prima operazione, il driver determina la versione dell'SDK da usare.</span><span class="sxs-lookup"><span data-stu-id="3b188-175">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="3b188-176">Se non è presente nessuna voce ['global.json'](global-json.md) viene usata la versione più recente disponibile del SDK.</span><span class="sxs-lookup"><span data-stu-id="3b188-176">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="3b188-177">Può essere una versione di anteprima o una versione stabile, a seconda di qual è la più recente disponibile nel computer.</span><span class="sxs-lookup"><span data-stu-id="3b188-177">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="3b188-178">Dopo aver determinato la versione del SDK il driver esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="3b188-178">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="3b188-179">Comando</span><span class="sxs-lookup"><span data-stu-id="3b188-179">Command</span></span>

<span data-ttu-id="3b188-180">Il comando esegue un'azione.</span><span class="sxs-lookup"><span data-stu-id="3b188-180">The command performs an action.</span></span> <span data-ttu-id="3b188-181">Ad esempio, `dotnet build` compila il codice.</span><span class="sxs-lookup"><span data-stu-id="3b188-181">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="3b188-182">`dotnet publish` pubblica il codice.</span><span class="sxs-lookup"><span data-stu-id="3b188-182">`dotnet publish` publishes code.</span></span> <span data-ttu-id="3b188-183">I comandi vengono implementati come un'applicazione console usando una convenzione `dotnet {command}`.</span><span class="sxs-lookup"><span data-stu-id="3b188-183">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="3b188-184">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3b188-184">Arguments</span></span>

<span data-ttu-id="3b188-185">Gli argomenti passati alla riga di comando sono gli argomenti per il comando richiamato.</span><span class="sxs-lookup"><span data-stu-id="3b188-185">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="3b188-186">Quando si esegue `dotnet publish my_app.csproj`, ad esempio, l'argomento `my_app.csproj` indica il progetto da pubblicare e viene passato al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="3b188-186">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="3b188-187">Options</span><span class="sxs-lookup"><span data-stu-id="3b188-187">Options</span></span>

<span data-ttu-id="3b188-188">Le opzioni passate alla riga di comando sono le opzioni per il comando richiamato.</span><span class="sxs-lookup"><span data-stu-id="3b188-188">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="3b188-189">Quando si esegue `dotnet publish --output /build_output`, ad esempio, l'opzione `--output` e il relativo valore vengono passati al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="3b188-189">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="3b188-190">Migrazione da project.json</span><span class="sxs-lookup"><span data-stu-id="3b188-190">Migration from project.json</span></span>

<span data-ttu-id="3b188-191">Se si sono usati gli strumenti della Preview 2 per generare progetti basati su *project.json*, consultare l'argomento [dotnet migrate](dotnet-migrate.md) per informazioni sulla migrazione del progetto in MSBuild/ *.csproj* per l'uso con gli strumenti di rilascio.</span><span class="sxs-lookup"><span data-stu-id="3b188-191">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="3b188-192">Per i progetti .NET Core creati prima del rilascio degli strumenti della Preview 2, aggiornare manualmente il progetto seguendo le istruzioni disponibili in [Migrazione da DNX all'interfaccia della riga di comando di .NET Core (project.json)](../migration/from-dnx.md) e usare `dotnet migrate` o aggiornare direttamente i progetti.</span><span class="sxs-lookup"><span data-stu-id="3b188-192">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b188-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b188-193">See also</span></span>

- [<span data-ttu-id="3b188-194">repository GitHub DotNet/SDK</span><span class="sxs-lookup"><span data-stu-id="3b188-194">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- <span data-ttu-id="3b188-195">[.NET Core installation guide](https://aka.ms/dotnetcoregs) (Guida all'installazione di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="3b188-195">[.NET Core installation guide](https://aka.ms/dotnetcoregs)</span></span>
