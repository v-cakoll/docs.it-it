---
title: Comando dotnet restore - Interfaccia della riga di comando di .NET Core
description: Informazioni sul ripristino delle dipendenze e degli strumenti specifici per il progetto tramite il comando dotnet-restore.
keywords: dotnet-restore, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 82a78dcb0cc85e2ba087b6df5ee029cbfb687358
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-restore"></a><span data-ttu-id="ad5d7-104">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="ad5d7-104">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ad5d7-105">Nome</span><span class="sxs-lookup"><span data-stu-id="ad5d7-105">Name</span></span>

<span data-ttu-id="ad5d7-106">`dotnet restore`: ripristina le dipendenze e gli strumenti di un progetto.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-106">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ad5d7-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="ad5d7-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="ad5d7-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="ad5d7-108">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ad5d7-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ad5d7-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="ad5d7-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad5d7-110">Description</span></span>

<span data-ttu-id="ad5d7-111">Il comando `dotnet restore` usa NuGet per ripristinare le dipendenze e gli strumenti specifici del progetto definiti nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-111">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="ad5d7-112">Per impostazione predefinita, il ripristino delle dipendenze e degli strumenti viene eseguito in parallelo.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-112">By default, the restoration of dependencies and tools are performed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="ad5d7-113">Per ripristinare le dipendenze, NuGet necessita dei feed in cui si trovano i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-113">In order to restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="ad5d7-114">I feed vengono forniti in genere tramite il file di configurazione *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-114">Feeds are usually provided via the *NuGet.config* configuration file.</span></span> <span data-ttu-id="ad5d7-115">Durante l'installazione degli strumenti dell'interfaccia della riga di comando, viene fornito un file di configurazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-115">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="ad5d7-116">È possibile specificare più feed creando un file *NuGet.config* nella directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-116">You specify additional feeds by creating your own *NuGet.config* file in the project directory.</span></span> <span data-ttu-id="ad5d7-117">È inoltre possibile specificare feed aggiuntivi per ogni chiamata a un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-117">You also specify additional feeds per invocation at a command prompt.</span></span>

<span data-ttu-id="ad5d7-118">Per le dipendenze è possibile specificare dove vengono inseriti i pacchetti ripristinati durante l'operazione di ripristino usando l'argomento `--packages`.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-118">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="ad5d7-119">Se questa destinazione non viene specificata, viene usata la cache predefinita dei pacchetti NuGet che si trova nella directory `.nuget/packages` della directory home dell'utente in tutti i sistemi operativi (ad esempio, */home/user1* in Linux or *C:\Users\user1* in Windows).</span><span class="sxs-lookup"><span data-stu-id="ad5d7-119">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems (for example, */home/user1* on Linux or *C:\Users\user1* on Windows).</span></span>

<span data-ttu-id="ad5d7-120">Per gli strumenti specifici del progetto, `dotnet restore` ripristina innanzitutto il pacchetto in cui viene compresso lo strumento e quindi ripristina le dipendenze dello strumento come specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

<span data-ttu-id="ad5d7-121">Il funzionamento del comando `dotnet restore` può essere modificato da alcune impostazioni del file *NuGet.Config*, se è presente.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-121">The behavior of the `dotnet restore` command is affected by some of the settings in the *Nuget.Config* file, if present.</span></span> <span data-ttu-id="ad5d7-122">Se ad esempio si imposta `globalPackagesFolder` in *NuGet.Config* i pacchetti NuGet ripristinati vengono posizionati nella cartella specificata.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-122">For example, setting the `globalPackagesFolder` in *NuGet.Config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="ad5d7-123">Questo approccio rappresenta un'alternativa all'impostazione dell'opzione `--packages` per il comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="ad5d7-124">Per altre informazioni, vedere [NuGet.Config reference](/nuget/schema/nuget-config-file) (Informazioni di riferimento su NuGet.Config).</span><span class="sxs-lookup"><span data-stu-id="ad5d7-124">For more information, see the [NuGet.Config reference](/nuget/schema/nuget-config-file).</span></span>

## <a name="arguments"></a><span data-ttu-id="ad5d7-125">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ad5d7-125">Arguments</span></span>

`ROOT`

<span data-ttu-id="ad5d7-126">Percorso facoltativo del file di progetto da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-126">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="ad5d7-127">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ad5d7-127">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="ad5d7-128">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="ad5d7-128">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="ad5d7-129">File di configurazione NuGet (*NuGet.config*) da usare per l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-129">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="ad5d7-130">Disabilita il ripristino di più progetti in parallelo.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-130">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="ad5d7-131">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-131">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="ad5d7-132">Ciò equivale a eliminare il file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-132">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="ad5d7-133">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-133">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="ad5d7-134">Segnala le origini con esito negativo solo se sono presenti pacchetti che soddisfano il requisito di versione.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-134">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="ad5d7-135">Specifica di non memorizzare nella cache pacchetti e richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-135">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="ad5d7-136">Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-136">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="ad5d7-137">Specifica la directory per i pacchetti ripristinati.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-137">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="ad5d7-138">Specifica un runtime per il ripristino dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-138">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="ad5d7-139">Questo runtime viene usato per ripristinare i pacchetti di runtime non esplicitamente elencati nel tag `<RuntimeIdentifiers>` del file *csproj*.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-139">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="ad5d7-140">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="ad5d7-140">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="ad5d7-141">Specificare più origini selezionando questa opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-141">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="ad5d7-142">Specifica un'origine dei pacchetti NuGet da usare durante l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-142">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="ad5d7-143">Questa impostazione esegue l'override di tutte le origini specificate nel file *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-143">This overrides all of the sources specified in the *NuGet.config* file(s).</span></span> <span data-ttu-id="ad5d7-144">È possibile specificare più origini, selezionando questa opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-144">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="ad5d7-145">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ad5d7-146">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ad5d7-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ad5d7-147">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="ad5d7-148">File di configurazione NuGet (*NuGet.config*) da usare per l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-148">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="ad5d7-149">Disabilita il ripristino di più progetti in parallelo.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-149">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="ad5d7-150">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-150">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="ad5d7-151">Segnala le origini con esito negativo solo se sono presenti pacchetti che soddisfano il requisito di versione.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-151">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="ad5d7-152">Specifica di non memorizzare nella cache pacchetti e richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-152">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="ad5d7-153">Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-153">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="ad5d7-154">Specifica la directory per i pacchetti ripristinati.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-154">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="ad5d7-155">Specifica un runtime per il ripristino dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-155">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="ad5d7-156">Questo runtime viene usato per ripristinare i pacchetti di runtime non esplicitamente elencati nel tag `<RuntimeIdentifiers>` del file *csproj*.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-156">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="ad5d7-157">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="ad5d7-157">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="ad5d7-158">Specificare più origini selezionando questa opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-158">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="ad5d7-159">Specifica un'origine dei pacchetti NuGet da usare durante l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-159">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="ad5d7-160">Questa impostazione esegue l'override di tutte le origini specificate nel file *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-160">This overrides all of the sources specified in the *NuGet.config* file(s).</span></span> <span data-ttu-id="ad5d7-161">È possibile specificare più origini, selezionando questa opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-161">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="ad5d7-162">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-162">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ad5d7-163">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ad5d7-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="ad5d7-164">Esempi</span><span class="sxs-lookup"><span data-stu-id="ad5d7-164">Examples</span></span>

<span data-ttu-id="ad5d7-165">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="ad5d7-165">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="ad5d7-166">Ripristinare le dipendenze e gli strumenti per il progetto `app1` che si trova nel percorso specificato:</span><span class="sxs-lookup"><span data-stu-id="ad5d7-166">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="ad5d7-167">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente usando il percorso di file specificato come origine:</span><span class="sxs-lookup"><span data-stu-id="ad5d7-167">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="ad5d7-168">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente usando i due percorsi di file specificati come origini:</span><span class="sxs-lookup"><span data-stu-id="ad5d7-168">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="ad5d7-169">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente e mostrare solo un output minimo:</span><span class="sxs-lookup"><span data-stu-id="ad5d7-169">Restore dependencies and tools for the project in the current directory and shows only minimal output:</span></span>

`dotnet restore --verbosity minimal`
