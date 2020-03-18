---
title: Risolvere i problemi di utilizzo degli strumenti .NET CoreTroubleshoot .NET Core tool usage issues
description: Scopri i problemi comuni durante l'esecuzione degli strumenti .NET Core e le possibili soluzioni.
author: kdollard
ms.date: 02/14/2020
ms.openlocfilehash: ed6243f802c4d3ce56a742916a1a28676e3cd876
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146450"
---
# <a name="troubleshoot-net-core-tool-usage-issues"></a><span data-ttu-id="e47c9-103">Risolvere i problemi di utilizzo degli strumenti .NET CoreTroubleshoot .NET Core tool usage issues</span><span class="sxs-lookup"><span data-stu-id="e47c9-103">Troubleshoot .NET Core tool usage issues</span></span>

<span data-ttu-id="e47c9-104">Si potrebbero incontrare problemi quando si tenta di installare o eseguire uno strumento .NET Core, che può essere uno strumento globale o uno strumento locale.</span><span class="sxs-lookup"><span data-stu-id="e47c9-104">You might come across issues when trying to install or run a .NET Core tool, which can be a global tool or a local tool.</span></span> <span data-ttu-id="e47c9-105">In questo articolo vengono descritte le cause principali comuni e alcune possibili soluzioni.</span><span class="sxs-lookup"><span data-stu-id="e47c9-105">This article describes the common root causes and some possible solutions.</span></span>

## <a name="installed-net-core-tool-fails-to-run"></a><span data-ttu-id="e47c9-106">Lo strumento .NET Core installato non viene eseguito</span><span class="sxs-lookup"><span data-stu-id="e47c9-106">Installed .NET Core tool fails to run</span></span>

<span data-ttu-id="e47c9-107">Quando uno strumento .NET Core non viene eseguito, molto probabilmente si è verificato uno dei seguenti problemi:</span><span class="sxs-lookup"><span data-stu-id="e47c9-107">When a .NET Core tool fails to run, most likely you ran into one of the following issues:</span></span>

* <span data-ttu-id="e47c9-108">Il file eseguibile per lo strumento non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="e47c9-108">The executable file for the tool wasn't found.</span></span>
* <span data-ttu-id="e47c9-109">La versione corretta del runtime di .NET Core non è stata trovata.</span><span class="sxs-lookup"><span data-stu-id="e47c9-109">The correct version of the .NET Core runtime wasn't found.</span></span>

### <a name="executable-file-not-found"></a><span data-ttu-id="e47c9-110">File eseguibile non trovato</span><span class="sxs-lookup"><span data-stu-id="e47c9-110">Executable file not found</span></span>

<span data-ttu-id="e47c9-111">Se il file eseguibile non viene trovato, verrà visualizzato un messaggio simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e47c9-111">If the executable file isn't found, you'll see a message similar to the following:</span></span>

```console
Could not execute because the specified command or file was not found.
Possible reasons for this include:
  * You misspelled a built-in dotnet command.
  * You intended to execute a .NET Core program, but dotnet-xyz does not exist.
  * You intended to run a global tool, but a dotnet-prefixed executable with this name could not be found on the PATH.
```

<span data-ttu-id="e47c9-112">Il nome dell'eseguibile determina la modalità di richiamo dello strumento.</span><span class="sxs-lookup"><span data-stu-id="e47c9-112">The name of the executable determines how you invoke the tool.</span></span> <span data-ttu-id="e47c9-113">Nella tabella seguente viene descritto il formato:</span><span class="sxs-lookup"><span data-stu-id="e47c9-113">The following table describes the format:</span></span>

| <span data-ttu-id="e47c9-114">Formato del nome eseguibile</span><span class="sxs-lookup"><span data-stu-id="e47c9-114">Executable name format</span></span>  | <span data-ttu-id="e47c9-115">Formato di chiamata</span><span class="sxs-lookup"><span data-stu-id="e47c9-115">Invocation format</span></span>   |
|-------------------------|---------------------|
| `dotnet-<toolName>.exe` | `dotnet <toolName>` |
| `<toolName>.exe`        | `<toolName>`        |

* <span data-ttu-id="e47c9-116">Strumenti globali</span><span class="sxs-lookup"><span data-stu-id="e47c9-116">Global tools</span></span>

  <span data-ttu-id="e47c9-117">Gli strumenti globali possono essere installati nella directory predefinita o in un percorso specifico.</span><span class="sxs-lookup"><span data-stu-id="e47c9-117">Global tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="e47c9-118">Le directory predefinite sono:</span><span class="sxs-lookup"><span data-stu-id="e47c9-118">The default directories are:</span></span>

  | <span data-ttu-id="e47c9-119">OS</span><span class="sxs-lookup"><span data-stu-id="e47c9-119">OS</span></span>          | <span data-ttu-id="e47c9-120">Path</span><span class="sxs-lookup"><span data-stu-id="e47c9-120">Path</span></span>                          |
  |-------------|-------------------------------|
  | <span data-ttu-id="e47c9-121">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="e47c9-121">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
  | <span data-ttu-id="e47c9-122">Windows</span><span class="sxs-lookup"><span data-stu-id="e47c9-122">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

  <span data-ttu-id="e47c9-123">Se si sta tentando di eseguire uno `PATH` strumento globale, verificare che la variabile di ambiente nel computer contenga il percorso in cui è stato installato lo strumento globale e che l'eseguibile si trovi in tale percorso.</span><span class="sxs-lookup"><span data-stu-id="e47c9-123">If you're trying to run a global tool, check that the `PATH` environment variable on your machine contains the path where you installed the global tool and that the executable is in that path.</span></span>

  <span data-ttu-id="e47c9-124">L'interfaccia della riga di comando di .NET Core tenta di aggiungere il percorso predefinito alla variabile di ambiente PATH al primo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="e47c9-124">The .NET Core CLI tries to add the default location to the PATH environment variable on its first usage.</span></span> <span data-ttu-id="e47c9-125">Tuttavia, esistono alcuni scenari in cui il percorso potrebbe non essere aggiunto automaticamente a PATH:However, there are some scenarios where the location might not be added to PATH automatically:</span><span class="sxs-lookup"><span data-stu-id="e47c9-125">However, there are some scenarios where the location might not be added to PATH automatically:</span></span>

  * <span data-ttu-id="e47c9-126">Se si utilizza Linux e è stato installato .NET Core SDK utilizzando i file *.tar.gz* e non apt-get o rpm.</span><span class="sxs-lookup"><span data-stu-id="e47c9-126">If you're using Linux and you've installed the .NET Core SDK using *.tar.gz* files and not apt-get or rpm.</span></span>
  * <span data-ttu-id="e47c9-127">Se utilizzi macOS 10.15 "Catalina" o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="e47c9-127">If you're using macOS 10.15 "Catalina" or later versions.</span></span>
  * <span data-ttu-id="e47c9-128">Se si utilizza macOS 10.14 "Mojave" o versioni precedenti e .NET Core SDK utilizzando i file *.tar.gz* e non *.pkg*.</span><span class="sxs-lookup"><span data-stu-id="e47c9-128">If you're using macOS 10.14 "Mojave" or earlier versions, and you've installed the .NET Core SDK using *.tar.gz* files and not *.pkg*.</span></span>
  * <span data-ttu-id="e47c9-129">Se è stato installato .NET Core 3.0 SDK `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` e la `false`variabile di ambiente è stata impostata su .</span><span class="sxs-lookup"><span data-stu-id="e47c9-129">If you've installed the .NET Core 3.0 SDK and you've set the `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` environment variable to `false`.</span></span>
  * <span data-ttu-id="e47c9-130">Se .NET Core 2.2 SDK o versioni precedenti è stato `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` installato `true`e la variabile di ambiente è stata impostata su .</span><span class="sxs-lookup"><span data-stu-id="e47c9-130">If you've installed .NET Core 2.2 SDK or earlier versions, and you've set the `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` environment variable to `true`.</span></span>

  <span data-ttu-id="e47c9-131">In questi scenari o `--tool-path` se è `PATH` stata specificata l'opzione , la variabile di ambiente nel computer non contiene automaticamente il percorso in cui è stato installato lo strumento globale.</span><span class="sxs-lookup"><span data-stu-id="e47c9-131">In these scenarios or if you specified the `--tool-path` option, the `PATH` environment variable on your machine doesn't automatically contain the path where you installed the global tool.</span></span> <span data-ttu-id="e47c9-132">In tal caso, aggiungere la posizione `$HOME/.dotnet/tools`dello `PATH` strumento (ad esempio, ) alla variabile di ambiente utilizzando il metodo fornito dalla shell per l'aggiornamento delle variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="e47c9-132">In that case, append the tool location (for example, `$HOME/.dotnet/tools`) to the `PATH` environment variable by using whatever method your shell provides for updating environment variables.</span></span> <span data-ttu-id="e47c9-133">Per ulteriori informazioni, vedere [Strumenti di .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e47c9-133">For more information, see [.NET Core tools](global-tools.md).</span></span>

* <span data-ttu-id="e47c9-134">Strumenti locali</span><span class="sxs-lookup"><span data-stu-id="e47c9-134">Local tools</span></span>

  <span data-ttu-id="e47c9-135">Se si sta tentando di eseguire uno strumento locale, verificare che sia presente un file manifesto denominato *dotnet-tools.json* nella directory corrente o in una delle relative directory padre.</span><span class="sxs-lookup"><span data-stu-id="e47c9-135">If you're trying to run a local tool, verify that there's a manifest file called *dotnet-tools.json* in the current directory or any of its parent directories.</span></span> <span data-ttu-id="e47c9-136">Questo file può anche trovarsi in una cartella denominata *.config* in qualsiasi punto della gerarchia di cartelle del progetto, anziché nella cartella radice.</span><span class="sxs-lookup"><span data-stu-id="e47c9-136">This file can also live under a folder named *.config* anywhere in the project folder hierarchy, instead of the root folder.</span></span> <span data-ttu-id="e47c9-137">Se *dotnet-tools.json* esiste, aprirlo e verificare la presenza dello strumento che si sta tentando di eseguire.</span><span class="sxs-lookup"><span data-stu-id="e47c9-137">If *dotnet-tools.json* exists, open it and check for the tool you're trying to run.</span></span> <span data-ttu-id="e47c9-138">Se il file non contiene `"isRoot": true`una voce per , controllare ulteriormente la gerarchia dei file per ulteriori file manifesto degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="e47c9-138">If the file doesn't contain an entry for `"isRoot": true`, then also check further up the file hierarchy for additional tool manifest files.</span></span>

  <span data-ttu-id="e47c9-139">Se si sta tentando di eseguire uno strumento .NET Core installato con un percorso specificato, è necessario includere tale percorso quando si utilizza lo strumento.</span><span class="sxs-lookup"><span data-stu-id="e47c9-139">If you're trying to run a .NET Core tool that was installed with a specified path, you need to include that path when using the tool.</span></span> <span data-ttu-id="e47c9-140">Un esempio di utilizzo di uno strumento di installazione del percorso utensile è:An example of using a tool-path installed tool is:</span><span class="sxs-lookup"><span data-stu-id="e47c9-140">An example of using a tool-path installed tool is:</span></span>

  ```console
  ..\<toolDirectory>\dotnet-<toolName>
  ```

### <a name="runtime-not-found"></a><span data-ttu-id="e47c9-141">Runtime non trovato</span><span class="sxs-lookup"><span data-stu-id="e47c9-141">Runtime not found</span></span>

<span data-ttu-id="e47c9-142">Gli strumenti .NET Core sono [applicazioni dipendenti dal framework,](../deploying/index.md#publish-runtime-dependent)il che significa che si basano su un runtime .NET Core installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="e47c9-142">.NET Core tools are [framework-dependent applications](../deploying/index.md#publish-runtime-dependent), which means they rely on a .NET Core runtime installed on your machine.</span></span> <span data-ttu-id="e47c9-143">Se il runtime previsto non viene trovato, seguono normali regole di rollforward del runtime .NET Core, ad esempio:If the expected runtime isn't found, they follow normal .NET Core runtime roll-forward rules such as:</span><span class="sxs-lookup"><span data-stu-id="e47c9-143">If the expected runtime isn't found, they follow normal .NET Core runtime roll-forward rules such as:</span></span>

* <span data-ttu-id="e47c9-144">Un'applicazione esegue il roll forward alla versione di patch più recente della versione principale e secondaria specificate.</span><span class="sxs-lookup"><span data-stu-id="e47c9-144">An application rolls forward to the highest patch release of the specified major and minor version.</span></span>
* <span data-ttu-id="e47c9-145">Se non è presente alcun runtime corrispondente con un numero di versione principale e secondario corrispondente, viene utilizzata la versione secondaria successiva superiore.</span><span class="sxs-lookup"><span data-stu-id="e47c9-145">If there's no matching runtime with a matching major and minor version number, the next higher minor version is used.</span></span>
* <span data-ttu-id="e47c9-146">Il roll forward non viene eseguito tra due versioni di anteprima del runtime o tra versioni di anteprima e versioni di rilascio.</span><span class="sxs-lookup"><span data-stu-id="e47c9-146">Roll forward doesn't occur between preview versions of the runtime or between preview versions and release versions.</span></span> <span data-ttu-id="e47c9-147">Pertanto, gli strumenti .NET Core creati utilizzando le versioni di anteprima devono essere ricompilati e ripubblicati dall'autore e reinstallati.</span><span class="sxs-lookup"><span data-stu-id="e47c9-147">So, .NET Core tools created using preview versions must be rebuilt and republished by the author and reinstalled.</span></span>

<span data-ttu-id="e47c9-148">Il rollforward non si verifica per impostazione predefinita in due scenari comuni:Roll-forward won't occur by default in two common scenarios:</span><span class="sxs-lookup"><span data-stu-id="e47c9-148">Roll-forward won't occur by default in two common scenarios:</span></span>

* <span data-ttu-id="e47c9-149">Sono disponibili solo versioni inferiori del runtime.</span><span class="sxs-lookup"><span data-stu-id="e47c9-149">Only lower versions of the runtime are available.</span></span> <span data-ttu-id="e47c9-150">Roll-forward seleziona solo le versioni successive del runtime.</span><span class="sxs-lookup"><span data-stu-id="e47c9-150">Roll-forward only selects later versions of the runtime.</span></span>
* <span data-ttu-id="e47c9-151">Sono disponibili solo le versioni principali superiori del runtime.</span><span class="sxs-lookup"><span data-stu-id="e47c9-151">Only higher major versions of the runtime are available.</span></span> <span data-ttu-id="e47c9-152">Il rollforward non supera i limiti della versione principale.</span><span class="sxs-lookup"><span data-stu-id="e47c9-152">Roll-forward doesn't cross major version boundaries.</span></span>

<span data-ttu-id="e47c9-153">Se un'applicazione non riesce a trovare un runtime appropriato, non viene eseguita e viene segnalato un errore.</span><span class="sxs-lookup"><span data-stu-id="e47c9-153">If an application can't find an appropriate runtime, it fails to run and reports an error.</span></span>

<span data-ttu-id="e47c9-154">È possibile scoprire quali runtime .NET Core sono installati nel computer utilizzando uno dei seguenti comandi:</span><span class="sxs-lookup"><span data-stu-id="e47c9-154">You can find out which .NET Core runtimes are installed on your machine using one of the following commands:</span></span>

```dotnetcli
dotnet --list-runtimes
dotnet --info
```

<span data-ttu-id="e47c9-155">Se si ritiene che lo strumento debba supportare la versione di runtime attualmente installata, è possibile contattare l'autore dello strumento e verificare se è possibile aggiornare il numero di versione o la versione multitarget.</span><span class="sxs-lookup"><span data-stu-id="e47c9-155">If you think the tool should support the runtime version you currently have installed, you can contact the tool author and see if they can update the version number or multi-target.</span></span> <span data-ttu-id="e47c9-156">Dopo aver ricompilato e ripubblicato il pacchetto di strumenti in NuGet con un numero di versione aggiornato, è possibile aggiornare la copia.</span><span class="sxs-lookup"><span data-stu-id="e47c9-156">Once they've recompiled and republished their tool package to NuGet with an updated version number, you can update your copy.</span></span> <span data-ttu-id="e47c9-157">Anche se ciò non accade, la soluzione più rapida per l'installazione di una versione del runtime che funzionerebbe con lo strumento che si sta tentando di eseguire.</span><span class="sxs-lookup"><span data-stu-id="e47c9-157">While that doesn't happen, the quickest solution for you is to install a version of the runtime that would work with the tool you're trying to run.</span></span> <span data-ttu-id="e47c9-158">Per scaricare una versione specifica di .NET Core Runtime, visitare la pagina di download di [.NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="e47c9-158">To download a specific .NET Core runtime version, visit the [.NET Core download page](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="e47c9-159">Se si installa .NET Core SDK in un percorso non predefinito, è necessario impostare la variabile `DOTNET_ROOT` di ambiente sulla directory che contiene l'eseguibile. `dotnet`</span><span class="sxs-lookup"><span data-stu-id="e47c9-159">If you install the .NET Core SDK to a non-default location, you need to set the environment variable `DOTNET_ROOT` to the directory that contains the `dotnet` executable.</span></span>

## <a name="net-core-tool-installation-fails"></a><span data-ttu-id="e47c9-160">Installazione dello strumento .NET Core non riuscita</span><span class="sxs-lookup"><span data-stu-id="e47c9-160">.NET Core tool installation fails</span></span>

<span data-ttu-id="e47c9-161">L'installazione di uno strumento globale o locale .NET Core potrebbe non riuscire per diversi motivi.</span><span class="sxs-lookup"><span data-stu-id="e47c9-161">There are a number of reasons the installation of a .NET Core global or local tool may fail.</span></span> <span data-ttu-id="e47c9-162">Quando l'installazione dello strumento non riesce, verrà visualizzato un messaggio simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e47c9-162">When the tool installation fails, you'll see a message similar to the following one:</span></span>

```console
Tool '{0}' failed to install. This failure may have been caused by:

* You are attempting to install a preview release and did not use the --version option to specify the version.
* A package by this name was found, but it was not a .NET Core tool.
* The required NuGet feed cannot be accessed, perhaps because of an Internet connection problem.
* You mistyped the name of the tool.

For more reasons, including package naming enforcement, visit https://aka.ms/failure-installing-tool
```

<span data-ttu-id="e47c9-163">Per diagnosticare questi errori, i messaggi NuGet vengono visualizzati direttamente all'utente, insieme al messaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="e47c9-163">To help diagnose these failures, NuGet messages are shown directly to the user, along with the previous message.</span></span> <span data-ttu-id="e47c9-164">Il messaggio NuGet può aiutare a identificare il problema.</span><span class="sxs-lookup"><span data-stu-id="e47c9-164">The NuGet message may help you identify the problem.</span></span>

### <a name="package-naming-enforcement"></a><span data-ttu-id="e47c9-165">Applicazione della denominazione dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="e47c9-165">Package naming enforcement</span></span>

<span data-ttu-id="e47c9-166">Microsoft ha modificato le linee guida sull'ID pacchetto per gli strumenti, con conseguente un numero di strumenti non vengono trovati con il nome previsto.</span><span class="sxs-lookup"><span data-stu-id="e47c9-166">Microsoft has changed its guidance on the Package ID for tools, resulting in a number of tools not being found with the predicted name.</span></span> <span data-ttu-id="e47c9-167">La nuova guida è che tutti gli strumenti Microsoft sono preceduti da "Microsoft".</span><span class="sxs-lookup"><span data-stu-id="e47c9-167">The new guidance is that all Microsoft tools be prefixed with "Microsoft."</span></span> <span data-ttu-id="e47c9-168">Questo prefisso è riservato e può essere utilizzato solo per i pacchetti firmati con un certificato autorizzato Microsoft.This prefix is reserved and can only be used for packages signed with a Microsoft authorized certificate.</span><span class="sxs-lookup"><span data-stu-id="e47c9-168">This prefix is reserved and can only be used for packages signed with a Microsoft authorized certificate.</span></span>

<span data-ttu-id="e47c9-169">Durante la transizione, alcuni strumenti Microsoft avranno la vecchia forma dell'ID del pacchetto, mentre altri avranno il nuovo formato:</span><span class="sxs-lookup"><span data-stu-id="e47c9-169">During the transition, some Microsoft tools will have the old form of the package ID, while others will have the new form:</span></span>

```dotnetcli
dotnet tool install -g Microsoft.<toolName>
dotnet tool install -g <toolName>
```

<span data-ttu-id="e47c9-170">Man mano che gli ID pacchetto vengono aggiornati, è necessario passare al nuovo ID pacchetto per ottenere gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="e47c9-170">As package IDs are updated, you'll need to change to the new package ID to get the latest updates.</span></span> <span data-ttu-id="e47c9-171">I pacchetti con il nome dello strumento semplificato saranno deprecati.</span><span class="sxs-lookup"><span data-stu-id="e47c9-171">Packages with the simplified tool name will be deprecated.</span></span>

### <a name="preview-releases"></a><span data-ttu-id="e47c9-172">Anteprima delle versioni</span><span class="sxs-lookup"><span data-stu-id="e47c9-172">Preview releases</span></span>

* <span data-ttu-id="e47c9-173">Si sta tentando di installare una versione di `--version` anteprima e non è stata utilizzata l'opzione per specificare la versione.</span><span class="sxs-lookup"><span data-stu-id="e47c9-173">You're attempting to install a preview release and didn't use the `--version` option to specify the version.</span></span>

<span data-ttu-id="e47c9-174">Gli strumenti .NET Core in anteprima devono essere specificati con una parte del nome per indicare che sono in anteprima.</span><span class="sxs-lookup"><span data-stu-id="e47c9-174">.NET Core tools that are in preview must be specified with a portion of the name to indicate that they are in preview.</span></span> <span data-ttu-id="e47c9-175">Non è necessario includere l'intera anteprima.</span><span class="sxs-lookup"><span data-stu-id="e47c9-175">You don't need to include the entire preview.</span></span> <span data-ttu-id="e47c9-176">Supponendo che i numeri di versione siano nel formato previsto, è possibile utilizzare qualcosa di simile all'esempio seguente:Assuming the version numbers are in the expected format, you can use something like the following example:</span><span class="sxs-lookup"><span data-stu-id="e47c9-176">Assuming the version numbers are in the expected format, you can use something like the following example:</span></span>

```dotnetcli
dotnet tool install -g --version 1.1.0-pre <toolName>
```

### <a name="package-isnt-a-net-core-tool"></a><span data-ttu-id="e47c9-177">Il pacchetto non è uno strumento .NET CorePackage isn't a .NET Core tool</span><span class="sxs-lookup"><span data-stu-id="e47c9-177">Package isn't a .NET Core tool</span></span>

* <span data-ttu-id="e47c9-178">È stato trovato un pacchetto NuGet con questo nome, ma non è stato uno strumento .NET Core.A NuGet package by this name was found, but it wasn't a .NET Core tool.</span><span class="sxs-lookup"><span data-stu-id="e47c9-178">A NuGet package by this name was found, but it wasn't a .NET Core tool.</span></span>

<span data-ttu-id="e47c9-179">Se si tenta di installare un pacchetto NuGet che è un normale pacchetto NuGet e non uno strumento .NET Core, verrà visualizzato un errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e47c9-179">If you try to install a NuGet package that is a regular NuGet package and not a .NET Core tool, you'll see an error similar to the following:</span></span>

> <span data-ttu-id="e47c9-180">NU1212: combinazione progetto-pacchetto `<ToolName>`non valida per .</span><span class="sxs-lookup"><span data-stu-id="e47c9-180">NU1212: Invalid project-package combination for `<ToolName>`.</span></span> <span data-ttu-id="e47c9-181">Lo stile di progetto DotnetToolReference può contenere solo riferimenti di tipo DotnetTool.</span><span class="sxs-lookup"><span data-stu-id="e47c9-181">DotnetToolReference project style can only contain references of the DotnetTool type.</span></span>

### <a name="nuget-feed-cant-be-accessed"></a><span data-ttu-id="e47c9-182">Impossibile accedere al feed NuGet</span><span class="sxs-lookup"><span data-stu-id="e47c9-182">NuGet feed can't be accessed</span></span>

* <span data-ttu-id="e47c9-183">Non è possibile accedere al feed NuGet richiesto, ad esempio a causa di un problema di connessione a Internet.</span><span class="sxs-lookup"><span data-stu-id="e47c9-183">The required NuGet feed can't be accessed, perhaps because of an Internet connection problem.</span></span>

<span data-ttu-id="e47c9-184">L'installazione dello strumento richiede l'accesso al feed NuGet che contiene il pacchetto dello strumento.</span><span class="sxs-lookup"><span data-stu-id="e47c9-184">Tool installation requires access to the NuGet feed that contains the tool package.</span></span> <span data-ttu-id="e47c9-185">Non riesce se il feed non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="e47c9-185">It fails if the feed isn't available.</span></span> <span data-ttu-id="e47c9-186">È possibile modificare `nuget.config`i feed `nuget.config` con , richiedere un file `--add-source` specifico o specificare feed aggiuntivi con il commutatore.</span><span class="sxs-lookup"><span data-stu-id="e47c9-186">You can alter feeds with `nuget.config`, request a specific `nuget.config` file, or specify additional feeds with the `--add-source` switch.</span></span> <span data-ttu-id="e47c9-187">Per impostazione predefinita, NuGet genera un errore per qualsiasi feed che non può connettersi.</span><span class="sxs-lookup"><span data-stu-id="e47c9-187">By default, NuGet throws an error for any feed that can't connect.</span></span> <span data-ttu-id="e47c9-188">Il `--ignore-failed-sources` flag può ignorare queste origini non raggiungibili.</span><span class="sxs-lookup"><span data-stu-id="e47c9-188">The flag `--ignore-failed-sources` can skip these non-reachable sources.</span></span>

### <a name="package-id-incorrect"></a><span data-ttu-id="e47c9-189">ID pacchetto non corretto</span><span class="sxs-lookup"><span data-stu-id="e47c9-189">Package ID incorrect</span></span>

* <span data-ttu-id="e47c9-190">Hai digitato male il nome dello strumento.</span><span class="sxs-lookup"><span data-stu-id="e47c9-190">You mistyped the name of the tool.</span></span>

<span data-ttu-id="e47c9-191">Un motivo di errore comune è che il nome dello strumento non è corretto.</span><span class="sxs-lookup"><span data-stu-id="e47c9-191">A common reason for failure is that the tool name isn't correct.</span></span> <span data-ttu-id="e47c9-192">Ciò può verificarsi a causa di errori di digitazione o perché lo strumento è stato spostato o è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="e47c9-192">This can happen because of mistyping, or because the tool has moved or been deprecated.</span></span> <span data-ttu-id="e47c9-193">Per gli strumenti su NuGet.org, un modo per assicurarsi di avere il nome corretto consiste nel cercare lo strumento al NuGet.org e copiare il comando di installazione.</span><span class="sxs-lookup"><span data-stu-id="e47c9-193">For tools on NuGet.org, one way to ensure you have the name correct is to search for the tool at NuGet.org and copy the installation command.</span></span>

## <a name="see-also"></a><span data-ttu-id="e47c9-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e47c9-194">See also</span></span>

* [<span data-ttu-id="e47c9-195">Strumenti .NET Core</span><span class="sxs-lookup"><span data-stu-id="e47c9-195">.NET Core tools</span></span>](global-tools.md)
