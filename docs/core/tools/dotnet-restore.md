---
title: Comando dotnet restore
description: Informazioni sul ripristino delle dipendenze e degli strumenti specifici per il progetto tramite il comando dotnet-restore.
ms.date: 05/29/2018
ms.openlocfilehash: 82dd85e340a4cb520f781d977b0798b0f532a088
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75340444"
---
# <a name="dotnet-restore"></a><span data-ttu-id="33f33-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="33f33-103">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="33f33-104">Name</span><span class="sxs-lookup"><span data-stu-id="33f33-104">Name</span></span>

<span data-ttu-id="33f33-105">`dotnet restore`: ripristina le dipendenze e gli strumenti di un progetto.</span><span class="sxs-lookup"><span data-stu-id="33f33-105">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="33f33-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="33f33-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="33f33-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="33f33-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity] [--interactive]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="33f33-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="33f33-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="33f33-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33f33-109">Description</span></span>

<span data-ttu-id="33f33-110">Il comando `dotnet restore` usa NuGet per ripristinare le dipendenze e gli strumenti specifici del progetto definiti nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="33f33-110">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="33f33-111">Per impostazione predefinita, il ripristino delle dipendenze e degli strumenti viene eseguito in parallelo.</span><span class="sxs-lookup"><span data-stu-id="33f33-111">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="33f33-112">Per ripristinare le dipendenze, NuGet necessita dei feed in cui si trovano i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="33f33-112">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="33f33-113">I feed vengono forniti in genere tramite il file di configurazione *nuget.config*.</span><span class="sxs-lookup"><span data-stu-id="33f33-113">Feeds are usually provided via the *nuget.config* configuration file.</span></span> <span data-ttu-id="33f33-114">Durante l'installazione degli strumenti dell'interfaccia della riga di comando, viene fornito un file di configurazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="33f33-114">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="33f33-115">È possibile specificare più feed creando un file *nuget.config* nella directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="33f33-115">You specify additional feeds by creating your own *nuget.config* file in the project directory.</span></span> <span data-ttu-id="33f33-116">È possibile eseguire l'override dei feed *NuGet. config* con l'opzione `-s`.</span><span class="sxs-lookup"><span data-stu-id="33f33-116">You can override the *nuget.config* feeds with the `-s` option.</span></span>

<span data-ttu-id="33f33-117">Per le dipendenze è possibile specificare dove vengono inseriti i pacchetti ripristinati durante l'operazione di ripristino usando l'argomento `--packages`.</span><span class="sxs-lookup"><span data-stu-id="33f33-117">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="33f33-118">Se questa destinazione non viene specificata, viene usata la cache predefinita dei pacchetti NuGet che si trova nella directory `.nuget/packages` della directory home dell'utente in tutti i sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="33f33-118">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="33f33-119">Ad esempio, */home/user1* in Linux o *C:\Utenti\user1* in Windows.</span><span class="sxs-lookup"><span data-stu-id="33f33-119">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="33f33-120">Per gli strumenti specifici del progetto, `dotnet restore` ripristina innanzitutto il pacchetto in cui viene compresso lo strumento e quindi ripristina le dipendenze dello strumento come specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="33f33-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

### <a name="nugetconfig-differences"></a><span data-ttu-id="33f33-121">Differenze di nuget.config</span><span class="sxs-lookup"><span data-stu-id="33f33-121">nuget.config differences</span></span>

<span data-ttu-id="33f33-122">Il funzionamento del comando `dotnet restore` può essere modificato dalle impostazioni del file *nuget.config*, se è presente.</span><span class="sxs-lookup"><span data-stu-id="33f33-122">The behavior of the `dotnet restore` command is affected by the settings in the *nuget.config* file, if present.</span></span> <span data-ttu-id="33f33-123">Se ad esempio si imposta `globalPackagesFolder` in *nuget.config*, i pacchetti NuGet ripristinati vengono posizionati nella cartella specificata.</span><span class="sxs-lookup"><span data-stu-id="33f33-123">For example, setting the `globalPackagesFolder` in *nuget.config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="33f33-124">Questo approccio rappresenta un'alternativa all'impostazione dell'opzione `--packages` per il comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="33f33-124">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="33f33-125">Per altre informazioni, vedere [Informazioni di riferimento su nuget.config](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="33f33-125">For more information, see the [nuget.config reference](/nuget/schema/nuget-config-file).</span></span>

<span data-ttu-id="33f33-126">Esistono tre impostazioni specifiche che `dotnet restore` ignora:</span><span class="sxs-lookup"><span data-stu-id="33f33-126">There are three specific settings that `dotnet restore` ignores:</span></span>

- [<span data-ttu-id="33f33-127">bindingRedirects</span><span class="sxs-lookup"><span data-stu-id="33f33-127">bindingRedirects</span></span>](/nuget/schema/nuget-config-file#bindingredirects-section)

  <span data-ttu-id="33f33-128">I reindirizzamenti di binding non funzionano con elementi `<PackageReference>` e .NET Core supporta solo elementi `<PackageReference>` per i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="33f33-128">Binding redirects don't work with `<PackageReference>` elements and .NET Core only supports `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="33f33-129">solution</span><span class="sxs-lookup"><span data-stu-id="33f33-129">solution</span></span>](/nuget/schema/nuget-config-file#solution-section)

  <span data-ttu-id="33f33-130">Questa impostazione è specifica di Visual Studio e non può essere applicata a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="33f33-130">This setting is Visual Studio specific and doesn't apply to .NET Core.</span></span> <span data-ttu-id="33f33-131">.NET Core non usa un file `packages.config` ma usa invece elementi `<PackageReference>` per i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="33f33-131">.NET Core doesn't use a `packages.config` file and instead uses `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="33f33-132">trustedSigners</span><span class="sxs-lookup"><span data-stu-id="33f33-132">trustedSigners</span></span>](/nuget/schema/nuget-config-file#trustedsigners-section)

  <span data-ttu-id="33f33-133">Questa impostazione non può essere applicata perché [NuGet non supporta ancora la verifica multipiattaforma](https://github.com/NuGet/Home/issues/7939) di pacchetti attendibili.</span><span class="sxs-lookup"><span data-stu-id="33f33-133">This setting isn't applicable as [NuGet doesn't yet support cross-platform verification](https://github.com/NuGet/Home/issues/7939) of trusted packages.</span></span>

## <a name="implicit-dotnet-restore"></a><span data-ttu-id="33f33-134">`dotnet restore` implicito</span><span class="sxs-lookup"><span data-stu-id="33f33-134">Implicit `dotnet restore`</span></span>

<span data-ttu-id="33f33-135">A partire da .NET Core 2.0, `dotnet restore` viene eseguito in modo implicito se necessario quando si usano i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="33f33-135">Starting with .NET Core 2.0, `dotnet restore` is run implicitly if necessary when you issue the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="33f33-136">Nella maggior parte dei casi non è più necessario usare il comando `dotnet restore` in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="33f33-136">In most cases, you no longer need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="33f33-137">In alcuni casi, potrebbe non essere appropriato eseguire `dotnet restore` in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="33f33-137">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="33f33-138">È ad esempio necessario che alcuni sistemi automatizzati, come i sistemi di compilazione, chiamino `dotnet restore` in modo esplicito per controllare quando si verifica il ripristino in modo che possano controllare l'utilizzo della rete.</span><span class="sxs-lookup"><span data-stu-id="33f33-138">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="33f33-139">Per impedire l'esecuzione implicita di `dotnet restore`, è possibile usare il flag `--no-restore` con uno di questi comandi per disabilitare il ripristino implicito.</span><span class="sxs-lookup"><span data-stu-id="33f33-139">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="33f33-140">Argomenti</span><span class="sxs-lookup"><span data-stu-id="33f33-140">Arguments</span></span>

`ROOT`

<span data-ttu-id="33f33-141">Percorso facoltativo del file di progetto da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="33f33-141">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="33f33-142">Options</span><span class="sxs-lookup"><span data-stu-id="33f33-142">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="33f33-143">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="33f33-143">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="33f33-144">File di configurazione NuGet (*nuget.config*) da usare per l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="33f33-144">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="33f33-145">Disabilita il ripristino di più progetti in parallelo.</span><span class="sxs-lookup"><span data-stu-id="33f33-145">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="33f33-146">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="33f33-146">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="33f33-147">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="33f33-147">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="33f33-148">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="33f33-148">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="33f33-149">Segnala le origini con esito negativo solo se sono presenti pacchetti che soddisfano il requisito di versione.</span><span class="sxs-lookup"><span data-stu-id="33f33-149">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="33f33-150">Specifica di non memorizzare nella cache pacchetti e richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="33f33-150">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="33f33-151">Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="33f33-151">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="33f33-152">Specifica la directory per i pacchetti ripristinati.</span><span class="sxs-lookup"><span data-stu-id="33f33-152">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="33f33-153">Specifica un runtime per il ripristino dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="33f33-153">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="33f33-154">Questo runtime viene usato per ripristinare i pacchetti di runtime non esplicitamente elencati nel tag `<RuntimeIdentifiers>` del file *csproj*.</span><span class="sxs-lookup"><span data-stu-id="33f33-154">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="33f33-155">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="33f33-155">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="33f33-156">Specificare più origini selezionando questa opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="33f33-156">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="33f33-157">Specifica un'origine dei pacchetti NuGet da usare durante l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="33f33-157">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="33f33-158">Questa impostazione esegue l'override di tutte le origini specificate nei file *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="33f33-158">This setting overrides all of the sources specified in the *nuget.config* files.</span></span> <span data-ttu-id="33f33-159">È possibile specificare più origini, selezionando questa opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="33f33-159">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="33f33-160">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="33f33-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="33f33-161">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="33f33-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="33f33-162">Il valore predefinito è `minimal`.</span><span class="sxs-lookup"><span data-stu-id="33f33-162">Default value is `minimal`.</span></span>

`--interactive`

<span data-ttu-id="33f33-163">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione).</span><span class="sxs-lookup"><span data-stu-id="33f33-163">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="33f33-164">A partire da .NET Core 2.1.400</span><span class="sxs-lookup"><span data-stu-id="33f33-164">Since .NET Core 2.1.400.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="33f33-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="33f33-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="33f33-166">File di configurazione NuGet (*nuget.config*) da usare per l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="33f33-166">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="33f33-167">Disabilita il ripristino di più progetti in parallelo.</span><span class="sxs-lookup"><span data-stu-id="33f33-167">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="33f33-168">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="33f33-168">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="33f33-169">Segnala le origini con esito negativo solo se sono presenti pacchetti che soddisfano il requisito di versione.</span><span class="sxs-lookup"><span data-stu-id="33f33-169">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="33f33-170">Specifica di non memorizzare nella cache pacchetti e richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="33f33-170">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="33f33-171">Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="33f33-171">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="33f33-172">Specifica la directory per i pacchetti ripristinati.</span><span class="sxs-lookup"><span data-stu-id="33f33-172">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="33f33-173">Specifica un runtime per il ripristino dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="33f33-173">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="33f33-174">Questo runtime viene usato per ripristinare i pacchetti di runtime non esplicitamente elencati nel tag `<RuntimeIdentifiers>` del file *csproj*.</span><span class="sxs-lookup"><span data-stu-id="33f33-174">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="33f33-175">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="33f33-175">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="33f33-176">Specificare più origini selezionando questa opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="33f33-176">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="33f33-177">Specifica un'origine dei pacchetti NuGet da usare durante l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="33f33-177">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="33f33-178">Esegue l'override di tutte le origini specificate nei file *NuGet. config* , leggendo effettivamente il file *NuGet. config* come se l'elemento `<packageSource>` non fosse presente.</span><span class="sxs-lookup"><span data-stu-id="33f33-178">This overrides all of the sources specified in the *nuget.config* files, effectively reading the *nuget.config* file as if the `<packageSource>` element was not there.</span></span> <span data-ttu-id="33f33-179">È possibile specificare più origini, selezionando questa opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="33f33-179">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="33f33-180">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="33f33-180">Sets the verbosity level of the command.</span></span> <span data-ttu-id="33f33-181">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="33f33-181">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="33f33-182">Il valore predefinito è `minimal`.</span><span class="sxs-lookup"><span data-stu-id="33f33-182">The default is `minimal`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="33f33-183">Esempi</span><span class="sxs-lookup"><span data-stu-id="33f33-183">Examples</span></span>

<span data-ttu-id="33f33-184">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="33f33-184">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="33f33-185">Ripristinare le dipendenze e gli strumenti per il progetto `app1` che si trova nel percorso specificato:</span><span class="sxs-lookup"><span data-stu-id="33f33-185">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="33f33-186">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente usando il percorso di file specificato come origine:</span><span class="sxs-lookup"><span data-stu-id="33f33-186">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="33f33-187">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente usando i due percorsi di file specificati come origini:</span><span class="sxs-lookup"><span data-stu-id="33f33-187">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="33f33-188">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente che mostra l'output dettagliato:</span><span class="sxs-lookup"><span data-stu-id="33f33-188">Restore dependencies and tools for the project in the current directory showing detailed output:</span></span>

`dotnet restore --verbosity detailed`
