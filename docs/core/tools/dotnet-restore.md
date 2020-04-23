---
title: Comando dotnet restore
description: Informazioni sul ripristino delle dipendenze e degli strumenti specifici per il progetto tramite il comando dotnet-restore.
ms.date: 02/27/2020
ms.openlocfilehash: 3deef68a9bcee389a52291c72e7e1a1019a739fd
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102788"
---
# <a name="dotnet-restore"></a><span data-ttu-id="3fb6c-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="3fb6c-103">dotnet restore</span></span>

<span data-ttu-id="3fb6c-104">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="3fb6c-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="3fb6c-105">Nome</span><span class="sxs-lookup"><span data-stu-id="3fb6c-105">Name</span></span>

<span data-ttu-id="3fb6c-106">`dotnet restore`: ripristina le dipendenze e gli strumenti di un progetto.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-106">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3fb6c-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3fb6c-107">Synopsis</span></span>

```dotnetcli
dotnet restore [<ROOT>] [--configfile <FILE>] [--disable-parallel]
    [-f|--force] [--force-evaluate] [--ignore-failed-sources]
    [--interactive] [--lock-file-path <LOCK_FILE_PATH>] [--locked-mode]
    [--no-cache] [--no-dependencies] [--packages <PACKAGES_DIRECTORY>]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [-s|--source <SOURCE>]
    [--use-lockfile] [-v|--verbosity <LEVEL>]

dotnet restore -h|--help
```

## <a name="description"></a><span data-ttu-id="3fb6c-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3fb6c-108">Description</span></span>

<span data-ttu-id="3fb6c-109">Il comando `dotnet restore` usa NuGet per ripristinare le dipendenze e gli strumenti specifici del progetto definiti nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-109">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="3fb6c-110">Per impostazione predefinita, il ripristino delle dipendenze e degli strumenti viene eseguito in parallelo.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-110">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

### <a name="specify-feeds"></a><span data-ttu-id="3fb6c-111">Specificare i feed</span><span class="sxs-lookup"><span data-stu-id="3fb6c-111">Specify feeds</span></span>

<span data-ttu-id="3fb6c-112">Per ripristinare le dipendenze, NuGet necessita dei feed in cui si trovano i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-112">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="3fb6c-113">I feed vengono forniti in genere tramite il file di configurazione *nuget.config*.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-113">Feeds are usually provided via the *nuget.config* configuration file.</span></span> <span data-ttu-id="3fb6c-114">Quando è installato .NET Core SDK, viene fornito un file di configurazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-114">A default configuration file is provided when the .NET Core SDK is installed.</span></span> <span data-ttu-id="3fb6c-115">Per specificare feed aggiuntivi, effettuate una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="3fb6c-115">To specify additional feeds, do one of the following:</span></span>

- <span data-ttu-id="3fb6c-116">Creare il proprio file *nuget.config* nella directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-116">Create your own *nuget.config* file in the project directory.</span></span> <span data-ttu-id="3fb6c-117">Per altre informazioni, vedere [Configurazioni comuni](/nuget/consume-packages/configuring-nuget-behavior) di NuGet e [differenze di nuget.config](#nugetconfig-differences) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-117">For more information, see [Common NuGet configurations](/nuget/consume-packages/configuring-nuget-behavior) and [nuget.config differences](#nugetconfig-differences) later in this article.</span></span>
- <span data-ttu-id="3fb6c-118">Utilizzare `dotnet nuget` comandi [`dotnet nuget add source`](dotnet-nuget-add-source.md)come .</span><span class="sxs-lookup"><span data-stu-id="3fb6c-118">Use `dotnet nuget` commands such as [`dotnet nuget add source`](dotnet-nuget-add-source.md).</span></span>

<span data-ttu-id="3fb6c-119">È possibile eseguire l'override dei `-s` feed *nuget.config* con l'opzione.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-119">You can override the *nuget.config* feeds with the `-s` option.</span></span>

<span data-ttu-id="3fb6c-120">Per informazioni su come utilizzare i feed autenticati, vedere [Utilizzo di pacchetti da feed autenticati](/nuget/consume-packages/consuming-packages-authenticated-feeds).</span><span class="sxs-lookup"><span data-stu-id="3fb6c-120">For information about how to use authenticated feeds, see [Consuming packages from authenticated feeds](/nuget/consume-packages/consuming-packages-authenticated-feeds).</span></span>

### <a name="package-cache"></a><span data-ttu-id="3fb6c-121">Cache dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="3fb6c-121">Package cache</span></span>

<span data-ttu-id="3fb6c-122">Per le dipendenze è possibile specificare dove vengono inseriti i pacchetti ripristinati durante l'operazione di ripristino usando l'argomento `--packages`.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-122">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="3fb6c-123">Se questa destinazione non viene specificata, viene usata la cache predefinita dei pacchetti NuGet che si trova nella directory `.nuget/packages` della directory home dell'utente in tutti i sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-123">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="3fb6c-124">Ad esempio, */home/user1* in Linux o *C:\Utenti\user1* in Windows.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-124">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

### <a name="project-specific-tooling"></a><span data-ttu-id="3fb6c-125">Strumenti specifici del progetto</span><span class="sxs-lookup"><span data-stu-id="3fb6c-125">Project-specific tooling</span></span>

<span data-ttu-id="3fb6c-126">Per gli strumenti specifici del progetto, `dotnet restore` ripristina innanzitutto il pacchetto in cui viene compresso lo strumento e quindi ripristina le dipendenze dello strumento come specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-126">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

### <a name="nugetconfig-differences"></a><span data-ttu-id="3fb6c-127">Differenze di nuget.config</span><span class="sxs-lookup"><span data-stu-id="3fb6c-127">nuget.config differences</span></span>

<span data-ttu-id="3fb6c-128">Il funzionamento del comando `dotnet restore` può essere modificato dalle impostazioni del file *nuget.config*, se è presente.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-128">The behavior of the `dotnet restore` command is affected by the settings in the *nuget.config* file, if present.</span></span> <span data-ttu-id="3fb6c-129">Se ad esempio si imposta `globalPackagesFolder` in *nuget.config*, i pacchetti NuGet ripristinati vengono posizionati nella cartella specificata.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-129">For example, setting the `globalPackagesFolder` in *nuget.config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="3fb6c-130">Questo approccio rappresenta un'alternativa all'impostazione dell'opzione `--packages` per il comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-130">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="3fb6c-131">Per altre informazioni, vedere [Informazioni di riferimento su nuget.config](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="3fb6c-131">For more information, see the [nuget.config reference](/nuget/schema/nuget-config-file).</span></span>

<span data-ttu-id="3fb6c-132">Esistono tre impostazioni specifiche che `dotnet restore` ignora:</span><span class="sxs-lookup"><span data-stu-id="3fb6c-132">There are three specific settings that `dotnet restore` ignores:</span></span>

- [<span data-ttu-id="3fb6c-133">bindingRedirects</span><span class="sxs-lookup"><span data-stu-id="3fb6c-133">bindingRedirects</span></span>](/nuget/schema/nuget-config-file#bindingredirects-section)

  <span data-ttu-id="3fb6c-134">I reindirizzamenti di binding non funzionano con elementi `<PackageReference>` e .NET Core supporta solo elementi `<PackageReference>` per i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-134">Binding redirects don't work with `<PackageReference>` elements and .NET Core only supports `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="3fb6c-135">Soluzione</span><span class="sxs-lookup"><span data-stu-id="3fb6c-135">solution</span></span>](/nuget/schema/nuget-config-file#solution-section)

  <span data-ttu-id="3fb6c-136">Questa impostazione è specifica di Visual Studio e non può essere applicata a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-136">This setting is Visual Studio specific and doesn't apply to .NET Core.</span></span> <span data-ttu-id="3fb6c-137">.NET Core non usa un file `packages.config` ma usa invece elementi `<PackageReference>` per i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-137">.NET Core doesn't use a `packages.config` file and instead uses `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="3fb6c-138">trustedSigners</span><span class="sxs-lookup"><span data-stu-id="3fb6c-138">trustedSigners</span></span>](/nuget/schema/nuget-config-file#trustedsigners-section)

  <span data-ttu-id="3fb6c-139">Questa impostazione non può essere applicata perché [NuGet non supporta ancora la verifica multipiattaforma](https://github.com/NuGet/Home/issues/7939) di pacchetti attendibili.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-139">This setting isn't applicable as [NuGet doesn't yet support cross-platform verification](https://github.com/NuGet/Home/issues/7939) of trusted packages.</span></span>

## <a name="implicit-restore"></a><span data-ttu-id="3fb6c-140">Ripristino implicito</span><span class="sxs-lookup"><span data-stu-id="3fb6c-140">Implicit restore</span></span>

<span data-ttu-id="3fb6c-141">Il `dotnet restore` comando viene eseguito in modo implicito se necessario quando si eseguono i seguenti comandi:</span><span class="sxs-lookup"><span data-stu-id="3fb6c-141">The `dotnet restore` command is run implicitly if necessary when you run the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="3fb6c-142">Nella maggior parte dei casi, non `dotnet restore` è necessario utilizzare in modo esplicito il comando.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-142">In most cases, you don't need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="3fb6c-143">In alcuni casi, potrebbe non essere appropriato eseguire `dotnet restore` in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-143">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="3fb6c-144">È ad esempio necessario che alcuni sistemi automatizzati, come i sistemi di compilazione, chiamino `dotnet restore` in modo esplicito per controllare quando si verifica il ripristino in modo che possano controllare l'utilizzo della rete.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-144">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="3fb6c-145">Per impedire l'esecuzione implicita di `dotnet restore`, è possibile usare il flag `--no-restore` con uno di questi comandi per disabilitare il ripristino implicito.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-145">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="3fb6c-146">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3fb6c-146">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="3fb6c-147">Percorso facoltativo del file di progetto da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-147">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="3fb6c-148">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3fb6c-148">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="3fb6c-149">File di configurazione NuGet (*nuget.config*) da usare per l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-149">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="3fb6c-150">Disabilita il ripristino di più progetti in parallelo.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-150">Disables restoring multiple projects in parallel.</span></span>

- **`--force`**

  <span data-ttu-id="3fb6c-151">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-151">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="3fb6c-152">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-152">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`--force-evaluate`**

  <span data-ttu-id="3fb6c-153">Forza il ripristino per rivalutare tutte le dipendenze anche se esiste già un file di blocco.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-153">Forces restore to reevaluate all dependencies even if a lock file already exists.</span></span>

- **`-h|--help`**

  <span data-ttu-id="3fb6c-154">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-154">Prints out a short help for the command.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="3fb6c-155">Segnala le origini con esito negativo solo se sono presenti pacchetti che soddisfano il requisito di versione.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-155">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

- **`--interactive`**

  <span data-ttu-id="3fb6c-156">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione).</span><span class="sxs-lookup"><span data-stu-id="3fb6c-156">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="3fb6c-157">A partire da .NET Core 2.1.400</span><span class="sxs-lookup"><span data-stu-id="3fb6c-157">Since .NET Core 2.1.400.</span></span>

- **`--lock-file-path <LOCK_FILE_PATH>`**

  <span data-ttu-id="3fb6c-158">Percorso di output in cui viene scritto il file di blocco del progetto.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-158">Output location where project lock file is written.</span></span> <span data-ttu-id="3fb6c-159">Per impostazione predefinita, si tratta di *PROJECT_ROOT,packages.lock.json*.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-159">By default, this is *PROJECT_ROOT\packages.lock.json*.</span></span>

- **`--locked-mode`**

  <span data-ttu-id="3fb6c-160">Non consentire l'aggiornamento del file di blocco del progetto.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-160">Don't allow updating project lock file.</span></span>

- **`--no-cache`**

  <span data-ttu-id="3fb6c-161">Specifica di non memorizzare nella cache le richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-161">Specifies to not cache HTTP requests.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="3fb6c-162">Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-162">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

- **`--packages <PACKAGES_DIRECTORY>`**

  <span data-ttu-id="3fb6c-163">Specifica la directory per i pacchetti ripristinati.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-163">Specifies the directory for restored packages.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="3fb6c-164">Specifica un runtime per il ripristino dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-164">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="3fb6c-165">Questo runtime viene usato per ripristinare i pacchetti di runtime non esplicitamente elencati nel tag `<RuntimeIdentifiers>` del file *csproj*.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-165">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="3fb6c-166">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="3fb6c-166">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="3fb6c-167">Specificare più origini selezionando questa opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-167">Provide multiple RIDs by specifying this option multiple times.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="3fb6c-168">Specifica un'origine dei pacchetti NuGet da usare durante l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-168">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="3fb6c-169">Questa impostazione esegue l'override di tutte le origini specificate nei file *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-169">This setting overrides all of the sources specified in the *nuget.config* files.</span></span> <span data-ttu-id="3fb6c-170">È possibile specificare più origini, selezionando questa opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-170">Multiple sources can be provided by specifying this option multiple times.</span></span>

- **`--use-lockfile`**

  <span data-ttu-id="3fb6c-171">Consente di generare e utilizzare il file di blocco del progetto con il ripristino.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-171">Enables project lock file to be generated and used with restore.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="3fb6c-172">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-172">Sets the verbosity level of the command.</span></span> <span data-ttu-id="3fb6c-173">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-173">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="3fb6c-174">Il valore predefinito è `minimal`.</span><span class="sxs-lookup"><span data-stu-id="3fb6c-174">Default value is `minimal`.</span></span>

## <a name="examples"></a><span data-ttu-id="3fb6c-175">Esempi</span><span class="sxs-lookup"><span data-stu-id="3fb6c-175">Examples</span></span>

- <span data-ttu-id="3fb6c-176">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="3fb6c-176">Restore dependencies and tools for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet restore
  ```

- <span data-ttu-id="3fb6c-177">Ripristinare le dipendenze `app1` e gli strumenti per il progetto disponibili nel percorso specificato:Restore dependencies and tools for the project found in the given path:</span><span class="sxs-lookup"><span data-stu-id="3fb6c-177">Restore dependencies and tools for the `app1` project found in the   given path:</span></span>

  ```dotnetcli
  dotnet restore ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="3fb6c-178">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente utilizzando il percorso del file fornito come origine:</span><span class="sxs-lookup"><span data-stu-id="3fb6c-178">Restore the dependencies and tools for the project in the current   directory using the file path provided as the source:</span></span>

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages
  ```

- <span data-ttu-id="3fb6c-179">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente utilizzando i due percorsi di file forniti come origini:</span><span class="sxs-lookup"><span data-stu-id="3fb6c-179">Restore the dependencies and tools for the project in the current   directory using the two file paths provided as sources:</span></span>

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages
  ```

- <span data-ttu-id="3fb6c-180">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente che mostra l'output dettagliato:Restore dependencies and tools for the project in the current directory showing detailed output:</span><span class="sxs-lookup"><span data-stu-id="3fb6c-180">Restore dependencies and tools for the project in the current directory   showing detailed output:</span></span>

  ```dotnetcli
  dotnet restore --verbosity detailed
  ```
