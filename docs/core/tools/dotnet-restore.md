---
title: Comando dotnet restore - Interfaccia della riga di comando di .NET Core
description: Informazioni sul ripristino delle dipendenze e degli strumenti specifici per il progetto tramite il comando dotnet-restore.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 504a0621beb8aea961133d2cc6d287ce17051c1c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127329"
---
# <a name="dotnet-restore"></a><span data-ttu-id="021a9-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="021a9-103">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="021a9-104">nome</span><span class="sxs-lookup"><span data-stu-id="021a9-104">Name</span></span>

<span data-ttu-id="021a9-105">`dotnet restore`: ripristina le dipendenze e gli strumenti di un progetto.</span><span class="sxs-lookup"><span data-stu-id="021a9-105">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="021a9-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="021a9-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="021a9-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="021a9-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity] [--interactive]
dotnet restore [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="021a9-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="021a9-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="021a9-109">Description</span><span class="sxs-lookup"><span data-stu-id="021a9-109">Description</span></span>

<span data-ttu-id="021a9-110">Il comando `dotnet restore` usa NuGet per ripristinare le dipendenze e gli strumenti specifici del progetto definiti nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="021a9-110">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="021a9-111">Per impostazione predefinita, il ripristino delle dipendenze e degli strumenti viene eseguito in parallelo.</span><span class="sxs-lookup"><span data-stu-id="021a9-111">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="021a9-112">Per ripristinare le dipendenze, NuGet necessita dei feed in cui si trovano i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="021a9-112">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="021a9-113">I feed vengono forniti in genere tramite il file di configurazione *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="021a9-113">Feeds are usually provided via the *NuGet.config* configuration file.</span></span> <span data-ttu-id="021a9-114">Durante l'installazione degli strumenti dell'interfaccia della riga di comando, viene fornito un file di configurazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="021a9-114">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="021a9-115">È possibile specificare più feed creando un file *NuGet.config* nella directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="021a9-115">You specify additional feeds by creating your own *NuGet.config* file in the project directory.</span></span> <span data-ttu-id="021a9-116">È inoltre possibile specificare feed aggiuntivi per ogni chiamata a un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="021a9-116">You also specify additional feeds per invocation at a command prompt.</span></span>

<span data-ttu-id="021a9-117">Per le dipendenze è possibile specificare dove vengono inseriti i pacchetti ripristinati durante l'operazione di ripristino usando l'argomento `--packages`.</span><span class="sxs-lookup"><span data-stu-id="021a9-117">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="021a9-118">Se questa destinazione non viene specificata, viene usata la cache predefinita dei pacchetti NuGet che si trova nella directory `.nuget/packages` della directory home dell'utente in tutti i sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="021a9-118">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="021a9-119">Ad esempio, */home/user1* in Linux o *C:\Utenti\user1* in Windows.</span><span class="sxs-lookup"><span data-stu-id="021a9-119">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="021a9-120">Per gli strumenti specifici del progetto, `dotnet restore` ripristina innanzitutto il pacchetto in cui viene compresso lo strumento e quindi ripristina le dipendenze dello strumento come specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="021a9-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

<span data-ttu-id="021a9-121">Il funzionamento del comando `dotnet restore` può essere modificato da alcune impostazioni del file *NuGet.Config*, se è presente.</span><span class="sxs-lookup"><span data-stu-id="021a9-121">The behavior of the `dotnet restore` command is affected by some of the settings in the *Nuget.Config* file, if present.</span></span> <span data-ttu-id="021a9-122">Se ad esempio si imposta `globalPackagesFolder` in *NuGet.Config* i pacchetti NuGet ripristinati vengono posizionati nella cartella specificata.</span><span class="sxs-lookup"><span data-stu-id="021a9-122">For example, setting the `globalPackagesFolder` in *NuGet.Config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="021a9-123">Questo approccio rappresenta un'alternativa all'impostazione dell'opzione `--packages` per il comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="021a9-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="021a9-124">Per altre informazioni, vedere [NuGet.Config reference](/nuget/schema/nuget-config-file) (Informazioni di riferimento su NuGet.Config).</span><span class="sxs-lookup"><span data-stu-id="021a9-124">For more information, see the [NuGet.Config reference](/nuget/schema/nuget-config-file).</span></span>

## <a name="implicit-dotnet-restore"></a><span data-ttu-id="021a9-125">`dotnet restore` implicito</span><span class="sxs-lookup"><span data-stu-id="021a9-125">Implicit `dotnet restore`</span></span>

<span data-ttu-id="021a9-126">A partire da .NET Core 2.0, `dotnet restore` viene eseguito in modo implicito se necessario quando si usano i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="021a9-126">Starting with .NET Core 2.0, `dotnet restore` is run implicitly if necessary when you issue the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="021a9-127">Nella maggior parte dei casi non è più necessario usare il comando `dotnet restore` in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="021a9-127">In most cases, you no longer need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="021a9-128">In alcuni casi, potrebbe non essere appropriato eseguire `dotnet restore` in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="021a9-128">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="021a9-129">È ad esempio necessario che alcuni sistemi automatizzati, come i sistemi di compilazione, chiamino `dotnet restore` in modo esplicito per controllare quando si verifica il ripristino in modo che possano controllare l'utilizzo della rete.</span><span class="sxs-lookup"><span data-stu-id="021a9-129">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="021a9-130">Per impedire l'esecuzione implicita di `dotnet restore`, è possibile usare il flag `--no-restore` con uno di questi comandi per disabilitare il ripristino implicito.</span><span class="sxs-lookup"><span data-stu-id="021a9-130">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="021a9-131">Argomenti</span><span class="sxs-lookup"><span data-stu-id="021a9-131">Arguments</span></span>

`ROOT`

<span data-ttu-id="021a9-132">Percorso facoltativo del file di progetto da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="021a9-132">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="021a9-133">Opzioni</span><span class="sxs-lookup"><span data-stu-id="021a9-133">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="021a9-134">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="021a9-134">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="021a9-135">File di configurazione NuGet (*NuGet.config*) da usare per l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="021a9-135">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="021a9-136">Disabilita il ripristino di più progetti in parallelo.</span><span class="sxs-lookup"><span data-stu-id="021a9-136">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="021a9-137">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="021a9-137">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="021a9-138">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="021a9-138">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="021a9-139">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="021a9-139">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="021a9-140">Segnala le origini con esito negativo solo se sono presenti pacchetti che soddisfano il requisito di versione.</span><span class="sxs-lookup"><span data-stu-id="021a9-140">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="021a9-141">Specifica di non memorizzare nella cache pacchetti e richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="021a9-141">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="021a9-142">Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="021a9-142">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="021a9-143">Specifica la directory per i pacchetti ripristinati.</span><span class="sxs-lookup"><span data-stu-id="021a9-143">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="021a9-144">Specifica un runtime per il ripristino dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="021a9-144">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="021a9-145">Questo runtime viene usato per ripristinare i pacchetti di runtime non esplicitamente elencati nel tag `<RuntimeIdentifiers>` del file *csproj*.</span><span class="sxs-lookup"><span data-stu-id="021a9-145">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="021a9-146">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="021a9-146">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="021a9-147">Specificare più origini selezionando questa opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="021a9-147">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="021a9-148">Specifica un'origine dei pacchetti NuGet da usare durante l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="021a9-148">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="021a9-149">Questa impostazione esegue l'override di tutte le origini specificate nei file *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="021a9-149">This setting overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="021a9-150">È possibile specificare più origini, selezionando questa opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="021a9-150">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="021a9-151">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="021a9-151">Sets the verbosity level of the command.</span></span> <span data-ttu-id="021a9-152">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="021a9-152">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--interactive`

<span data-ttu-id="021a9-153">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione).</span><span class="sxs-lookup"><span data-stu-id="021a9-153">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="021a9-154">A partire da .NET Core 2.1.400</span><span class="sxs-lookup"><span data-stu-id="021a9-154">Since .NET Core 2.1.400.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="021a9-155">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="021a9-155">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="021a9-156">File di configurazione NuGet (*NuGet.config*) da usare per l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="021a9-156">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="021a9-157">Disabilita il ripristino di più progetti in parallelo.</span><span class="sxs-lookup"><span data-stu-id="021a9-157">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="021a9-158">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="021a9-158">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="021a9-159">Segnala le origini con esito negativo solo se sono presenti pacchetti che soddisfano il requisito di versione.</span><span class="sxs-lookup"><span data-stu-id="021a9-159">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="021a9-160">Specifica di non memorizzare nella cache pacchetti e richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="021a9-160">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="021a9-161">Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="021a9-161">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="021a9-162">Specifica la directory per i pacchetti ripristinati.</span><span class="sxs-lookup"><span data-stu-id="021a9-162">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="021a9-163">Specifica un runtime per il ripristino dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="021a9-163">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="021a9-164">Questo runtime viene usato per ripristinare i pacchetti di runtime non esplicitamente elencati nel tag `<RuntimeIdentifiers>` del file *csproj*.</span><span class="sxs-lookup"><span data-stu-id="021a9-164">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="021a9-165">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="021a9-165">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="021a9-166">Specificare più origini selezionando questa opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="021a9-166">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="021a9-167">Specifica un'origine dei pacchetti NuGet da usare durante l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="021a9-167">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="021a9-168">Questa impostazione esegue l'override di tutte le origini specificate nei file *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="021a9-168">This overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="021a9-169">È possibile specificare più origini, selezionando questa opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="021a9-169">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="021a9-170">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="021a9-170">Sets the verbosity level of the command.</span></span> <span data-ttu-id="021a9-171">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="021a9-171">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="021a9-172">Esempi</span><span class="sxs-lookup"><span data-stu-id="021a9-172">Examples</span></span>

<span data-ttu-id="021a9-173">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="021a9-173">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="021a9-174">Ripristinare le dipendenze e gli strumenti per il progetto `app1` che si trova nel percorso specificato:</span><span class="sxs-lookup"><span data-stu-id="021a9-174">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="021a9-175">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente usando il percorso di file specificato come origine:</span><span class="sxs-lookup"><span data-stu-id="021a9-175">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="021a9-176">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente usando i due percorsi di file specificati come origini:</span><span class="sxs-lookup"><span data-stu-id="021a9-176">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="021a9-177">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente e mostrare solo un output minimo:</span><span class="sxs-lookup"><span data-stu-id="021a9-177">Restore dependencies and tools for the project in the current directory and shows only minimal output:</span></span>

`dotnet restore --verbosity minimal`
