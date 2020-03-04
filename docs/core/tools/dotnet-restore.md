---
title: Comando dotnet restore
description: Informazioni sul ripristino delle dipendenze e degli strumenti specifici per il progetto tramite il comando dotnet-restore.
ms.date: 02/27/2020
ms.openlocfilehash: e74027ba70ddf6905a12f9691caeb0a406428ad6
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157024"
---
# <a name="dotnet-restore"></a><span data-ttu-id="c2472-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c2472-103">dotnet restore</span></span>

<span data-ttu-id="c2472-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="c2472-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c2472-105">Nome</span><span class="sxs-lookup"><span data-stu-id="c2472-105">Name</span></span>

<span data-ttu-id="c2472-106">`dotnet restore`: ripristina le dipendenze e gli strumenti di un progetto.</span><span class="sxs-lookup"><span data-stu-id="c2472-106">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c2472-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="c2472-107">Synopsis</span></span>

```dotnetcli
dotnet restore [<ROOT>] [--configfile] [--disable-parallel]
    [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime]
    [-s|--source] [-v|--verbosity] [--interactive]

dotnet restore [-h|--help]
```

## <a name="description"></a><span data-ttu-id="c2472-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c2472-108">Description</span></span>

<span data-ttu-id="c2472-109">Il comando `dotnet restore` usa NuGet per ripristinare le dipendenze e gli strumenti specifici del progetto definiti nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="c2472-109">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="c2472-110">Per impostazione predefinita, il ripristino delle dipendenze e degli strumenti viene eseguito in parallelo.</span><span class="sxs-lookup"><span data-stu-id="c2472-110">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

<span data-ttu-id="c2472-111">Per ripristinare le dipendenze, NuGet necessita dei feed in cui si trovano i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="c2472-111">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="c2472-112">I feed vengono forniti in genere tramite il file di configurazione *nuget.config*.</span><span class="sxs-lookup"><span data-stu-id="c2472-112">Feeds are usually provided via the *nuget.config* configuration file.</span></span> <span data-ttu-id="c2472-113">Quando viene installato il .NET Core SDK, viene fornito un file di configurazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="c2472-113">A default configuration file is provided when the .NET Core SDK is installed.</span></span> <span data-ttu-id="c2472-114">È possibile specificare più feed creando un file *nuget.config* nella directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="c2472-114">You specify additional feeds by creating your own *nuget.config* file in the project directory.</span></span> <span data-ttu-id="c2472-115">È possibile eseguire l'override dei feed *NuGet. config* con l'opzione-`-s`.</span><span class="sxs-lookup"><span data-stu-id="c2472-115">You can override the *nuget.config* feeds with the - `-s` option.</span></span>

<span data-ttu-id="c2472-116">Per le dipendenze è possibile specificare dove vengono inseriti i pacchetti ripristinati durante l'operazione di ripristino usando l'argomento `--packages`.</span><span class="sxs-lookup"><span data-stu-id="c2472-116">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="c2472-117">Se questa destinazione non viene specificata, viene usata la cache predefinita dei pacchetti NuGet che si trova nella directory `.nuget/packages` della directory home dell'utente in tutti i sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="c2472-117">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="c2472-118">Ad esempio, */home/user1* in Linux o *C:\Utenti\user1* in Windows.</span><span class="sxs-lookup"><span data-stu-id="c2472-118">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="c2472-119">Per gli strumenti specifici del progetto, `dotnet restore` ripristina innanzitutto il pacchetto in cui viene compresso lo strumento e quindi ripristina le dipendenze dello strumento come specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="c2472-119">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

### <a name="nugetconfig-differences"></a><span data-ttu-id="c2472-120">Differenze di nuget.config</span><span class="sxs-lookup"><span data-stu-id="c2472-120">nuget.config differences</span></span>

<span data-ttu-id="c2472-121">Il funzionamento del comando `dotnet restore` può essere modificato dalle impostazioni del file *nuget.config*, se è presente.</span><span class="sxs-lookup"><span data-stu-id="c2472-121">The behavior of the `dotnet restore` command is affected by the settings in the *nuget.config* file, if present.</span></span> <span data-ttu-id="c2472-122">Se ad esempio si imposta `globalPackagesFolder` in *nuget.config*, i pacchetti NuGet ripristinati vengono posizionati nella cartella specificata.</span><span class="sxs-lookup"><span data-stu-id="c2472-122">For example, setting the `globalPackagesFolder` in *nuget.config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="c2472-123">Questo approccio rappresenta un'alternativa all'impostazione dell'opzione `--packages` per il comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="c2472-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="c2472-124">Per altre informazioni, vedere [Informazioni di riferimento su nuget.config](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="c2472-124">For more information, see the [nuget.config reference](/nuget/schema/nuget-config-file).</span></span>

<span data-ttu-id="c2472-125">Esistono tre impostazioni specifiche che `dotnet restore` ignora:</span><span class="sxs-lookup"><span data-stu-id="c2472-125">There are three specific settings that `dotnet restore` ignores:</span></span>

- [<span data-ttu-id="c2472-126">bindingRedirects</span><span class="sxs-lookup"><span data-stu-id="c2472-126">bindingRedirects</span></span>](/nuget/schema/nuget-config-file#bindingredirects-section)

  <span data-ttu-id="c2472-127">I reindirizzamenti di binding non funzionano con elementi `<PackageReference>` e .NET Core supporta solo elementi `<PackageReference>` per i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="c2472-127">Binding redirects don't work with `<PackageReference>` elements and .NET Core only supports `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="c2472-128">solution</span><span class="sxs-lookup"><span data-stu-id="c2472-128">solution</span></span>](/nuget/schema/nuget-config-file#solution-section)

  <span data-ttu-id="c2472-129">Questa impostazione è specifica di Visual Studio e non può essere applicata a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c2472-129">This setting is Visual Studio specific and doesn't apply to .NET Core.</span></span> <span data-ttu-id="c2472-130">.NET Core non usa un file `packages.config` ma usa invece elementi `<PackageReference>` per i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="c2472-130">.NET Core doesn't use a `packages.config` file and instead uses `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="c2472-131">trustedSigners</span><span class="sxs-lookup"><span data-stu-id="c2472-131">trustedSigners</span></span>](/nuget/schema/nuget-config-file#trustedsigners-section)

  <span data-ttu-id="c2472-132">Questa impostazione non può essere applicata perché [NuGet non supporta ancora la verifica multipiattaforma](https://github.com/NuGet/Home/issues/7939) di pacchetti attendibili.</span><span class="sxs-lookup"><span data-stu-id="c2472-132">This setting isn't applicable as [NuGet doesn't yet support cross-platform verification](https://github.com/NuGet/Home/issues/7939) of trusted packages.</span></span>

## <a name="implicit-restore"></a><span data-ttu-id="c2472-133">Ripristino implicito</span><span class="sxs-lookup"><span data-stu-id="c2472-133">Implicit restore</span></span>

<span data-ttu-id="c2472-134">Il comando `dotnet restore` viene eseguito in modo implicito se necessario quando si eseguono i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2472-134">The `dotnet restore` command is run implicitly if necessary when you run the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="c2472-135">Nella maggior parte dei casi non è necessario usare in modo esplicito il comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="c2472-135">In most cases, you don't need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="c2472-136">In alcuni casi, potrebbe non essere appropriato eseguire `dotnet restore` in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="c2472-136">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="c2472-137">È ad esempio necessario che alcuni sistemi automatizzati, come i sistemi di compilazione, chiamino `dotnet restore` in modo esplicito per controllare quando si verifica il ripristino in modo che possano controllare l'utilizzo della rete.</span><span class="sxs-lookup"><span data-stu-id="c2472-137">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="c2472-138">Per impedire l'esecuzione implicita di `dotnet restore`, è possibile usare il flag `--no-restore` con uno di questi comandi per disabilitare il ripristino implicito.</span><span class="sxs-lookup"><span data-stu-id="c2472-138">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="c2472-139">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c2472-139">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="c2472-140">Percorso facoltativo del file di progetto da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="c2472-140">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="c2472-141">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c2472-141">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="c2472-142">File di configurazione NuGet (*nuget.config*) da usare per l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="c2472-142">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="c2472-143">Disabilita il ripristino di più progetti in parallelo.</span><span class="sxs-lookup"><span data-stu-id="c2472-143">Disables restoring multiple projects in parallel.</span></span>

- **`--force`**

  <span data-ttu-id="c2472-144">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c2472-144">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="c2472-145">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="c2472-145">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c2472-146">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="c2472-146">Prints out a short help for the command.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="c2472-147">Segnala le origini con esito negativo solo se sono presenti pacchetti che soddisfano il requisito di versione.</span><span class="sxs-lookup"><span data-stu-id="c2472-147">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

- **`--no-cache`**

  <span data-ttu-id="c2472-148">Specifica di non memorizzare nella cache pacchetti e richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="c2472-148">Specifies to not cache packages and HTTP requests.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="c2472-149">Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="c2472-149">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

- **`--packages <PACKAGES_DIRECTORY>`**

  <span data-ttu-id="c2472-150">Specifica la directory per i pacchetti ripristinati.</span><span class="sxs-lookup"><span data-stu-id="c2472-150">Specifies the directory for restored packages.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="c2472-151">Specifica un runtime per il ripristino dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="c2472-151">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="c2472-152">Questo runtime viene usato per ripristinare i pacchetti di runtime non esplicitamente elencati nel tag `<RuntimeIdentifiers>` del file *csproj*.</span><span class="sxs-lookup"><span data-stu-id="c2472-152">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="c2472-153">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="c2472-153">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="c2472-154">Specificare più origini selezionando questa opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="c2472-154">Provide multiple RIDs by specifying this option multiple times.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="c2472-155">Specifica un'origine dei pacchetti NuGet da usare durante l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="c2472-155">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="c2472-156">Questa impostazione esegue l'override di tutte le origini specificate nei file *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="c2472-156">This setting overrides all of the sources specified in the *nuget.config* files.</span></span> <span data-ttu-id="c2472-157">È possibile specificare più origini, selezionando questa opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="c2472-157">Multiple sources can be provided by specifying this option multiple times.</span></span>

- **`--verbosity <LEVEL>`**

  <span data-ttu-id="c2472-158">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="c2472-158">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c2472-159">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c2472-159">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c2472-160">Il valore predefinito è `minimal`.</span><span class="sxs-lookup"><span data-stu-id="c2472-160">Default value is `minimal`.</span></span>

- **`--interactive`**

  <span data-ttu-id="c2472-161">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione).</span><span class="sxs-lookup"><span data-stu-id="c2472-161">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="c2472-162">A partire da .NET Core 2.1.400</span><span class="sxs-lookup"><span data-stu-id="c2472-162">Since .NET Core 2.1.400.</span></span>

## <a name="examples"></a><span data-ttu-id="c2472-163">Esempi</span><span class="sxs-lookup"><span data-stu-id="c2472-163">Examples</span></span>

- <span data-ttu-id="c2472-164">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="c2472-164">Restore dependencies and tools for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet restore
  ```

- <span data-ttu-id="c2472-165">Ripristinare le dipendenze e gli strumenti per il progetto `app1` trovato nel percorso specificato:</span><span class="sxs-lookup"><span data-stu-id="c2472-165">Restore dependencies and tools for the `app1` project found in the   given path:</span></span>

  ```dotnetcli
  dotnet restore ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="c2472-166">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente usando il percorso del file fornito come origine:</span><span class="sxs-lookup"><span data-stu-id="c2472-166">Restore the dependencies and tools for the project in the current   directory using the file path provided as the source:</span></span>

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages
  ```

- <span data-ttu-id="c2472-167">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente usando i due percorsi di file forniti come origini:</span><span class="sxs-lookup"><span data-stu-id="c2472-167">Restore the dependencies and tools for the project in the current   directory using the two file paths provided as sources:</span></span>

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages
  ```

- <span data-ttu-id="c2472-168">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente che mostra l'output dettagliato:</span><span class="sxs-lookup"><span data-stu-id="c2472-168">Restore dependencies and tools for the project in the current directory   showing detailed output:</span></span>

  ```dotnetcli
  dotnet restore --verbosity detailed
  ```
