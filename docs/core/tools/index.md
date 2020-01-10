---
title: Strumenti dell'interfaccia della riga di comando di .NET Core
description: Panoramica degli strumenti e delle funzionalità dell'interfaccia della riga di comando di .NET Core.
ms.date: 08/14/2017
ms.openlocfilehash: b3bffb47ff973bd0da90e3f943e817756e563138
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714143"
---
# <a name="net-core-command-line-interface-cli-tools"></a><span data-ttu-id="7c9e5-103">Strumenti dell'interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="7c9e5-103">.NET Core command-line interface (CLI) tools</span></span>

<span data-ttu-id="7c9e5-104">L'interfaccia della riga di comando di .NET Core è una nuova toolchain multipiattaforma per lo sviluppo di applicazioni .NET.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-104">The .NET Core command-line interface (CLI) is a new cross-platform toolchain for developing .NET applications.</span></span> <span data-ttu-id="7c9e5-105">È un elemento di base su cui possono essere costruiti altri strumenti di livello più elevato, come gli ambienti di sviluppo integrato (IDE, Integrated Development Environment), gli editor e gli agenti di orchestrazione della compilazione.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-105">The CLI is a foundation upon which higher-level tools, such as Integrated Development Environments (IDEs), editors, and build orchestrators, can rest.</span></span>

## <a name="installation"></a><span data-ttu-id="7c9e5-106">Installazione di</span><span class="sxs-lookup"><span data-stu-id="7c9e5-106">Installation</span></span>

<span data-ttu-id="7c9e5-107">È possibile usare programmi di installazione nativi o script della shell di installazione:</span><span class="sxs-lookup"><span data-stu-id="7c9e5-107">Either use the native installers or use the installation shell scripts:</span></span>

- <span data-ttu-id="7c9e5-108">I programmi di installazione nativi sono destinati essenzialmente ai computer degli sviluppatori e si avvalgono del meccanismo di installazione nativo di ogni piattaforma supportata, ad esempio i pacchetti DEB in Ubuntu o i bundle MSI in Windows.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-108">The native installers are primarily used on developer's machines and use each supported platform's native install mechanism, for instance, DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="7c9e5-109">Questi programmi installano e configurano l'ambiente in modo da poter essere immediatamente usato dallo sviluppatore ma richiedono privilegi amministrativi sul computer.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-109">These installers install and configure the environment for immediate use by the developer but require administrative privileges on the machine.</span></span> <span data-ttu-id="7c9e5-110">È possibile visualizzare le istruzioni di installazione nel sito Web [.NET Core installation guide](https://aka.ms/dotnetcoregs) (Guida all'installazione di .NET Core).</span><span class="sxs-lookup"><span data-stu-id="7c9e5-110">You can view the installation instructions in the [.NET Core installation guide](https://aka.ms/dotnetcoregs).</span></span>
- <span data-ttu-id="7c9e5-111">Gli script vengono usati principalmente per configurare i server di compilazione o quando si vuole installare gli strumenti senza privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-111">Shell scripts are primarily used for setting up build servers or when you wish to install the tools without administrative privileges.</span></span> <span data-ttu-id="7c9e5-112">Con l'installazione degli script non vengono installati nel computer anche i prerequisiti, che devono essere installati manualmente.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-112">Install scripts don't install prerequisites on the machine, which must be installed manually.</span></span> <span data-ttu-id="7c9e5-113">Per altre informazioni, vedere l'[argomento di riferimento sugli script di installazione](dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="7c9e5-113">For more information, see the [install script reference topic](dotnet-install-script.md).</span></span> <span data-ttu-id="7c9e5-114">Per informazioni su come configurare l'interfaccia della riga di comando nel server di compilazione di integrazione continua (CI, Continuous Integration), vedere [Uso di .NET Core SDK e dei relativi strumenti in integrazione continua](using-ci-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="7c9e5-114">For information on how to set up CLI on your continuous integration (CI) build server, see [Using .NET Core SDK and tools in Continuous Integration (CI)](using-ci-with-cli.md).</span></span>

<span data-ttu-id="7c9e5-115">Per impostazione predefinita, l'interfaccia della riga di comando viene installata in modalità side-by-side (SxS). Pertanto, in un unico computer possono coesistere più versioni degli strumenti dell'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-115">By default, the CLI installs in a side-by-side (SxS) manner, so multiple versions of the CLI tools can coexist on a single machine.</span></span> <span data-ttu-id="7c9e5-116">La procedura per determinare la versione usata in un computer in cui sono installate più versioni è illustrata nella sezione [Driver](#driver).</span><span class="sxs-lookup"><span data-stu-id="7c9e5-116">Determining which version is used on a machine where multiple versions are installed is explained in more detail in the [Driver](#driver) section.</span></span>

## <a name="cli-commands"></a><span data-ttu-id="7c9e5-117">Comandi dell'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="7c9e5-117">CLI commands</span></span>

<span data-ttu-id="7c9e5-118">Per impostazione predefinita vengono installati i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c9e5-118">The following commands are installed by default:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7c9e5-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7c9e5-119">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="7c9e5-120">**Comandi di base**</span><span class="sxs-lookup"><span data-stu-id="7c9e5-120">**Basic commands**</span></span>

- [<span data-ttu-id="7c9e5-121">new</span><span class="sxs-lookup"><span data-stu-id="7c9e5-121">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="7c9e5-122">restore</span><span class="sxs-lookup"><span data-stu-id="7c9e5-122">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="7c9e5-123">build</span><span class="sxs-lookup"><span data-stu-id="7c9e5-123">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="7c9e5-124">publish</span><span class="sxs-lookup"><span data-stu-id="7c9e5-124">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="7c9e5-125">run</span><span class="sxs-lookup"><span data-stu-id="7c9e5-125">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="7c9e5-126">test</span><span class="sxs-lookup"><span data-stu-id="7c9e5-126">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="7c9e5-127">vstest</span><span class="sxs-lookup"><span data-stu-id="7c9e5-127">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="7c9e5-128">pack</span><span class="sxs-lookup"><span data-stu-id="7c9e5-128">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="7c9e5-129">migrate</span><span class="sxs-lookup"><span data-stu-id="7c9e5-129">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="7c9e5-130">clean</span><span class="sxs-lookup"><span data-stu-id="7c9e5-130">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="7c9e5-131">sln</span><span class="sxs-lookup"><span data-stu-id="7c9e5-131">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="7c9e5-132">help</span><span class="sxs-lookup"><span data-stu-id="7c9e5-132">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="7c9e5-133">store</span><span class="sxs-lookup"><span data-stu-id="7c9e5-133">store</span></span>](dotnet-store.md)

<span data-ttu-id="7c9e5-134">**Comandi per la modifica dei progetti**</span><span class="sxs-lookup"><span data-stu-id="7c9e5-134">**Project modification commands**</span></span>

- [<span data-ttu-id="7c9e5-135">add package</span><span class="sxs-lookup"><span data-stu-id="7c9e5-135">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="7c9e5-136">add reference</span><span class="sxs-lookup"><span data-stu-id="7c9e5-136">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="7c9e5-137">remove package</span><span class="sxs-lookup"><span data-stu-id="7c9e5-137">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="7c9e5-138">remove reference</span><span class="sxs-lookup"><span data-stu-id="7c9e5-138">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="7c9e5-139">list reference</span><span class="sxs-lookup"><span data-stu-id="7c9e5-139">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="7c9e5-140">**Comandi avanzati**</span><span class="sxs-lookup"><span data-stu-id="7c9e5-140">**Advanced commands**</span></span>

- [<span data-ttu-id="7c9e5-141">nuget delete</span><span class="sxs-lookup"><span data-stu-id="7c9e5-141">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="7c9e5-142">nuget locals</span><span class="sxs-lookup"><span data-stu-id="7c9e5-142">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="7c9e5-143">nuget push</span><span class="sxs-lookup"><span data-stu-id="7c9e5-143">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="7c9e5-144">msbuild</span><span class="sxs-lookup"><span data-stu-id="7c9e5-144">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="7c9e5-145">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="7c9e5-145">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7c9e5-146">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7c9e5-146">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="7c9e5-147">**Comandi di base**</span><span class="sxs-lookup"><span data-stu-id="7c9e5-147">**Basic commands**</span></span>

- [<span data-ttu-id="7c9e5-148">new</span><span class="sxs-lookup"><span data-stu-id="7c9e5-148">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="7c9e5-149">restore</span><span class="sxs-lookup"><span data-stu-id="7c9e5-149">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="7c9e5-150">build</span><span class="sxs-lookup"><span data-stu-id="7c9e5-150">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="7c9e5-151">publish</span><span class="sxs-lookup"><span data-stu-id="7c9e5-151">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="7c9e5-152">run</span><span class="sxs-lookup"><span data-stu-id="7c9e5-152">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="7c9e5-153">test</span><span class="sxs-lookup"><span data-stu-id="7c9e5-153">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="7c9e5-154">vstest</span><span class="sxs-lookup"><span data-stu-id="7c9e5-154">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="7c9e5-155">pack</span><span class="sxs-lookup"><span data-stu-id="7c9e5-155">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="7c9e5-156">migrate</span><span class="sxs-lookup"><span data-stu-id="7c9e5-156">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="7c9e5-157">clean</span><span class="sxs-lookup"><span data-stu-id="7c9e5-157">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="7c9e5-158">sln</span><span class="sxs-lookup"><span data-stu-id="7c9e5-158">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="7c9e5-159">**Comandi per la modifica dei progetti**</span><span class="sxs-lookup"><span data-stu-id="7c9e5-159">**Project modification commands**</span></span>

- [<span data-ttu-id="7c9e5-160">add package</span><span class="sxs-lookup"><span data-stu-id="7c9e5-160">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="7c9e5-161">add reference</span><span class="sxs-lookup"><span data-stu-id="7c9e5-161">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="7c9e5-162">remove package</span><span class="sxs-lookup"><span data-stu-id="7c9e5-162">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="7c9e5-163">remove reference</span><span class="sxs-lookup"><span data-stu-id="7c9e5-163">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="7c9e5-164">list reference</span><span class="sxs-lookup"><span data-stu-id="7c9e5-164">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="7c9e5-165">**Comandi avanzati**</span><span class="sxs-lookup"><span data-stu-id="7c9e5-165">**Advanced commands**</span></span>

- [<span data-ttu-id="7c9e5-166">nuget delete</span><span class="sxs-lookup"><span data-stu-id="7c9e5-166">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="7c9e5-167">nuget locals</span><span class="sxs-lookup"><span data-stu-id="7c9e5-167">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="7c9e5-168">nuget push</span><span class="sxs-lookup"><span data-stu-id="7c9e5-168">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="7c9e5-169">msbuild</span><span class="sxs-lookup"><span data-stu-id="7c9e5-169">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="7c9e5-170">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="7c9e5-170">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="7c9e5-171">L'interfaccia della riga di comando adotta un modello di estendibilità che consente di specificare altri strumenti per i progetti.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-171">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="7c9e5-172">Per altre informazioni, vedere l'argomento [Modello di estendibilità dell'interfaccia della riga di comando di .NET Core](extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="7c9e5-172">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="7c9e5-173">Struttura dei comandi</span><span class="sxs-lookup"><span data-stu-id="7c9e5-173">Command structure</span></span>

<span data-ttu-id="7c9e5-174">La struttura dei comandi dell'interfaccia della riga di comando è composta dal [driver ("dotnet")](#driver), dal [comando](#command) e, in alcuni casi, dagli [argomenti](#arguments) e dalle [opzioni](#options).</span><span class="sxs-lookup"><span data-stu-id="7c9e5-174">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="7c9e5-175">Questo modello può essere osservato nella maggior parte delle operazioni eseguite dalla riga di comando, inclusa la creazione di una nuova app console e la relativa esecuzione dalla riga di comando, come illustrato dai comandi seguenti quando vengono eseguiti da una directory denominata *my_app*:</span><span class="sxs-lookup"><span data-stu-id="7c9e5-175">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7c9e5-176">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7c9e5-176">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7c9e5-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7c9e5-177">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="7c9e5-178">Driver</span><span class="sxs-lookup"><span data-stu-id="7c9e5-178">Driver</span></span>

<span data-ttu-id="7c9e5-179">Il driver, denominato [dotnet](dotnet.md), ha due compiti: eseguire un'[app dipendente dal framework](../deploying/index.md) ed eseguire un comando.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-179">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="7c9e5-180">Per eseguire un'applicazione dipendente dal framework, specificare l'app dopo il driver, ad esempio `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-180">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="7c9e5-181">Se si esegue il comando dalla cartella in cui si trova la DLL dell'app, è sufficiente eseguire `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-181">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="7c9e5-182">Se si vuole usare una versione specifica del runtime .NET Core, usare l'opzione `--fx-version <VERSION>` (vedere il riferimento per il [comando dotnet](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="7c9e5-182">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="7c9e5-183">Nel momento in cui si fornisce un comando al driver, `dotnet.exe` avvia il processo di esecuzione del comando dell'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-183">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="7c9e5-184">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7c9e5-184">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="7c9e5-185">Come prima operazione, il driver determina la versione dell'SDK da usare.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-185">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="7c9e5-186">Se non è presente nessuna voce ['global.json'](global-json.md) viene usata la versione più recente disponibile del SDK.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-186">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="7c9e5-187">Può essere una versione di anteprima o una versione stabile, a seconda di qual è la più recente disponibile nel computer.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-187">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="7c9e5-188">Dopo aver determinato la versione del SDK il driver esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-188">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="7c9e5-189">Comando</span><span class="sxs-lookup"><span data-stu-id="7c9e5-189">Command</span></span>

<span data-ttu-id="7c9e5-190">Il comando esegue un'azione.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-190">The command performs an action.</span></span> <span data-ttu-id="7c9e5-191">Ad esempio, `dotnet build` compila il codice.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-191">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="7c9e5-192">`dotnet publish` pubblica il codice.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-192">`dotnet publish` publishes code.</span></span> <span data-ttu-id="7c9e5-193">I comandi vengono implementati come un'applicazione console usando una convenzione `dotnet {command}`.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-193">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="7c9e5-194">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7c9e5-194">Arguments</span></span>

<span data-ttu-id="7c9e5-195">Gli argomenti passati alla riga di comando sono gli argomenti per il comando richiamato.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-195">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="7c9e5-196">Quando si esegue `dotnet publish my_app.csproj`, ad esempio, l'argomento `my_app.csproj` indica il progetto da pubblicare e viene passato al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-196">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="7c9e5-197">Options</span><span class="sxs-lookup"><span data-stu-id="7c9e5-197">Options</span></span>

<span data-ttu-id="7c9e5-198">Le opzioni passate alla riga di comando sono le opzioni per il comando richiamato.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-198">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="7c9e5-199">Quando si esegue `dotnet publish --output /build_output`, ad esempio, l'opzione `--output` e il relativo valore vengono passati al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-199">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="7c9e5-200">Migrazione da project.json</span><span class="sxs-lookup"><span data-stu-id="7c9e5-200">Migration from project.json</span></span>

<span data-ttu-id="7c9e5-201">Se si sono usati gli strumenti della Preview 2 per generare progetti basati su *project.json*, consultare l'argomento [dotnet migrate](dotnet-migrate.md) per informazioni sulla migrazione del progetto in MSBuild/ *.csproj* per l'uso con gli strumenti di rilascio.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-201">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="7c9e5-202">Per i progetti .NET Core creati prima del rilascio degli strumenti della Preview 2, aggiornare manualmente il progetto seguendo le istruzioni disponibili in [Migrazione da DNX all'interfaccia della riga di comando di .NET Core (project.json)](../migration/from-dnx.md) e usare `dotnet migrate` o aggiornare direttamente i progetti.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-202">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c9e5-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c9e5-203">See also</span></span>

- [<span data-ttu-id="7c9e5-204">Repository GitHub dotnet/CLI</span><span class="sxs-lookup"><span data-stu-id="7c9e5-204">dotnet/CLI GitHub Repository</span></span>](https://github.com/dotnet/cli/)
- <span data-ttu-id="7c9e5-205">[.NET Core installation guide](https://aka.ms/dotnetcoregs) (Guida all'installazione di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="7c9e5-205">[.NET Core installation guide](https://aka.ms/dotnetcoregs)</span></span>
