---
title: Risolvere i problemi di utilizzo degli strumenti .NET Core
description: Individuare i problemi comuni quando si eseguono gli strumenti di .NET Core e le possibili soluzioni.
author: kdollard
ms.date: 09/23/2019
ms.openlocfilehash: 45139c3441b84964b937d5d1cc63a018f8d1f0fb
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451077"
---
# <a name="troubleshoot-net-core-tool-usage-issues"></a><span data-ttu-id="c9b2c-103">Risolvere i problemi di utilizzo degli strumenti .NET Core</span><span class="sxs-lookup"><span data-stu-id="c9b2c-103">Troubleshoot .NET Core tool usage issues</span></span>

<span data-ttu-id="c9b2c-104">Si potrebbero riscontrare problemi durante il tentativo di installare o eseguire uno strumento .NET Core, che può essere uno strumento globale o uno strumento locale.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-104">You might come across issues when trying to install or run a .NET Core tool, which can be a global tool or a local tool.</span></span> <span data-ttu-id="c9b2c-105">Questo articolo descrive le cause principali comuni e alcune possibili soluzioni.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-105">This article describes the common root causes and some possible solutions.</span></span>

## <a name="installed-net-core-tool-fails-to-run"></a><span data-ttu-id="c9b2c-106">Non è possibile eseguire lo strumento .NET Core installato</span><span class="sxs-lookup"><span data-stu-id="c9b2c-106">Installed .NET Core tool fails to run</span></span>

<span data-ttu-id="c9b2c-107">Quando si verifica un errore di esecuzione di uno strumento .NET Core, è molto probabile che si verifichi uno dei problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9b2c-107">When a .NET Core tool fails to run, most likely you ran into one of the following issues:</span></span>

* <span data-ttu-id="c9b2c-108">Il file eseguibile per lo strumento non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-108">The executable file for the tool wasn't found.</span></span>
* <span data-ttu-id="c9b2c-109">La versione corretta del runtime di .NET Core non è stata trovata.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-109">The correct version of the .NET Core runtime wasn't found.</span></span>

### <a name="executable-file-not-found"></a><span data-ttu-id="c9b2c-110">File eseguibile non trovato</span><span class="sxs-lookup"><span data-stu-id="c9b2c-110">Executable file not found</span></span>

<span data-ttu-id="c9b2c-111">Se il file eseguibile non viene trovato, verrà visualizzato un messaggio simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c9b2c-111">If the executable file isn't found, you'll see a message similar to the following:</span></span>

```console
Could not execute because the specified command or file was not found.
Possible reasons for this include:
  * You misspelled a built-in dotnet command.
  * You intended to execute a .NET Core program, but dotnet-xyz does not exist.
  * You intended to run a global tool, but a dotnet-prefixed executable with this name could not be found on the PATH.
```

<span data-ttu-id="c9b2c-112">Il nome del file eseguibile determina il modo in cui si richiama lo strumento.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-112">The name of the executable determines how you invoke the tool.</span></span> <span data-ttu-id="c9b2c-113">La tabella seguente descrive il formato:</span><span class="sxs-lookup"><span data-stu-id="c9b2c-113">The following table describes the format:</span></span>

| <span data-ttu-id="c9b2c-114">Formato del nome eseguibile</span><span class="sxs-lookup"><span data-stu-id="c9b2c-114">Executable name format</span></span>  | <span data-ttu-id="c9b2c-115">Formato chiamata</span><span class="sxs-lookup"><span data-stu-id="c9b2c-115">Invocation format</span></span>   |
|-------------------------|---------------------|
| `dotnet-<toolName>.exe` | `dotnet <toolName>` |
| `<toolName>.exe`        | `<toolName>`        |

* <span data-ttu-id="c9b2c-116">Strumenti globali</span><span class="sxs-lookup"><span data-stu-id="c9b2c-116">Global tools</span></span>

    <span data-ttu-id="c9b2c-117">Gli strumenti globali possono essere installati nella directory predefinita o in una posizione specifica.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-117">Global tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="c9b2c-118">Le directory predefinite sono:</span><span class="sxs-lookup"><span data-stu-id="c9b2c-118">The default directories are:</span></span>

    | <span data-ttu-id="c9b2c-119">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="c9b2c-119">OS</span></span>          | <span data-ttu-id="c9b2c-120">Percorso</span><span class="sxs-lookup"><span data-stu-id="c9b2c-120">Path</span></span>                          |
    |-------------|-------------------------------|
    | <span data-ttu-id="c9b2c-121">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="c9b2c-121">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
    | <span data-ttu-id="c9b2c-122">WINDOWS</span><span class="sxs-lookup"><span data-stu-id="c9b2c-122">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

    <span data-ttu-id="c9b2c-123">Se si sta provando a eseguire uno strumento globale, verificare che la variabile di ambiente `PATH` nel computer contenga il percorso in cui è stato installato lo strumento globale e che il file eseguibile si trovi in tale percorso.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-123">If you're trying to run a global tool, check that the `PATH` environment variable on your machine contains the path where you installed the global tool and that the executable is in that path.</span></span>

    <span data-ttu-id="c9b2c-124">L'interfaccia della riga di comando di .NET Core tenta di aggiungere i percorsi predefiniti alla variabile di ambiente PATH al primo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-124">The .NET Core CLI tries to add the default locations to the PATH environment variable on its first usage.</span></span> <span data-ttu-id="c9b2c-125">Tuttavia, esistono un paio di scenari in cui il percorso potrebbe non essere aggiunto automaticamente al percorso, quindi è necessario modificare il percorso per configurarlo nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9b2c-125">However, there are a couple of scenarios where the location might not be added to PATH automatically, so you'll have to edit PATH to configure it for the following cases:</span></span>

  * <span data-ttu-id="c9b2c-126">Se si usa Linux e si è installato il .NET Core SDK usando file con *estensione tar. gz* e non apt-get o RPM.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-126">If you're using Linux and you've installed the .NET Core SDK using *.tar.gz* files and not apt-get or rpm.</span></span>
  * <span data-ttu-id="c9b2c-127">Se si usa macOS 10,15 "Catalina" o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-127">If you're using macOS 10.15 "Catalina" or later versions.</span></span>
  * <span data-ttu-id="c9b2c-128">Se si usa macOS 10,14 "Mojave" o versioni precedenti ed è stato installato il .NET Core SDK usando file con *estensione tar. gz* e non *. pkg*.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-128">If you're using macOS 10.14 "Mojave" or earlier versions, and you've installed the .NET Core SDK using *.tar.gz* files and not *.pkg*.</span></span>
  * <span data-ttu-id="c9b2c-129">Se è stato installato .NET Core 3,0 SDK e la variabile di ambiente `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` è stata impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-129">If you've installed the .NET Core 3.0 SDK and you've set the `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` environment variable to `false`.</span></span>
  * <span data-ttu-id="c9b2c-130">Se è stato installato .NET Core 2,2 SDK o versioni precedenti ed è stata impostata la variabile di ambiente `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` su `true`.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-130">If you've installed .NET Core 2.2 SDK or earlier versions, and you've set the `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` environment variable to `true`.</span></span>

  <span data-ttu-id="c9b2c-131">Per altre informazioni sugli strumenti globali, vedere [Cenni preliminari sugli strumenti globali di .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c9b2c-131">For more information about global tools, see [.NET Core Global Tools overview](global-tools.md).</span></span>

* <span data-ttu-id="c9b2c-132">Strumenti locali</span><span class="sxs-lookup"><span data-stu-id="c9b2c-132">Local tools</span></span>

  <span data-ttu-id="c9b2c-133">Se si sta provando a eseguire uno strumento locale, verificare che esista un file manifesto denominato *DotNet-Tools. JSON* nella directory corrente o in una delle relative directory padre.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-133">If you're trying to run a local tool, verify that there's a manifest file called *dotnet-tools.json* in the current directory or any of its parent directories.</span></span> <span data-ttu-id="c9b2c-134">Questo file può essere contenuto anche in una cartella denominata *. config* in un punto qualsiasi della gerarchia della cartella del progetto, anziché nella cartella radice.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-134">This file can also live under a folder named *.config* anywhere in the project folder hierarchy, instead of the root folder.</span></span> <span data-ttu-id="c9b2c-135">Se *DotNet-Tools. JSON* esiste, aprirlo e verificare lo strumento che si sta tentando di eseguire.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-135">If *dotnet-tools.json* exists, open it and check for the tool you're trying to run.</span></span> <span data-ttu-id="c9b2c-136">Se il file non contiene una voce per `"isRoot": true`, controllare anche ulteriormente la gerarchia dei file per ulteriori file manifesto dello strumento.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-136">If the file doesn't contain an entry for `"isRoot": true`, then also check further up the file hierarchy for additional tool manifest files.</span></span>

  <span data-ttu-id="c9b2c-137">Se si sta provando a eseguire uno strumento .NET Core installato con un percorso specificato, è necessario includere tale percorso quando si usa lo strumento.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-137">If you're trying to run a .NET Core tool that was installed with a specified path, you need to include that path when using the tool.</span></span> <span data-ttu-id="c9b2c-138">Di seguito è riportato un esempio di utilizzo di uno strumento-percorso installato:</span><span class="sxs-lookup"><span data-stu-id="c9b2c-138">An example of using a tool-path installed tool is:</span></span>

  ```console
  ..\<toolDirectory>\dotnet-<toolName>
  ```

### <a name="runtime-not-found"></a><span data-ttu-id="c9b2c-139">Runtime non trovato</span><span class="sxs-lookup"><span data-stu-id="c9b2c-139">Runtime not found</span></span>

<span data-ttu-id="c9b2c-140">Gli strumenti di .NET Core sono [applicazioni dipendenti dal Framework](../deploying/index.md#publish-runtime-dependent), ovvero si basano su un runtime di .NET Core installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-140">.NET Core tools are [framework-dependent applications](../deploying/index.md#publish-runtime-dependent), which means they rely on a .NET Core runtime installed on your machine.</span></span> <span data-ttu-id="c9b2c-141">Se il runtime previsto non viene trovato, seguono le normali regole di rollforward del runtime di .NET Core, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c9b2c-141">If the expected runtime isn't found, they follow normal .NET Core runtime roll-forward rules such as:</span></span>

* <span data-ttu-id="c9b2c-142">Un'applicazione esegue il roll forward alla versione di patch più recente della versione principale e secondaria specificate.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-142">An application rolls forward to the highest patch release of the specified major and minor version.</span></span>
* <span data-ttu-id="c9b2c-143">Se non esiste un runtime corrispondente con un numero di versione principale e secondario corrispondente, viene usata la versione secondaria successiva più elevata.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-143">If there's no matching runtime with a matching major and minor version number, the next higher minor version is used.</span></span>
* <span data-ttu-id="c9b2c-144">Il roll forward non viene eseguito tra due versioni di anteprima del runtime o tra versioni di anteprima e versioni di rilascio.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-144">Roll forward doesn't occur between preview versions of the runtime or between preview versions and release versions.</span></span> <span data-ttu-id="c9b2c-145">Quindi, gli strumenti di .NET Core creati usando le versioni di anteprima devono essere ricompilati e ripubblicati dall'autore e reinstallati.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-145">So, .NET Core tools created using preview versions must be rebuilt and republished by the author and reinstalled.</span></span>

<span data-ttu-id="c9b2c-146">Per impostazione predefinita, il rollforward non viene eseguito in due scenari comuni:</span><span class="sxs-lookup"><span data-stu-id="c9b2c-146">Roll-forward won't occur by default in two common scenarios:</span></span>

* <span data-ttu-id="c9b2c-147">Sono disponibili solo versioni inferiori del runtime.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-147">Only lower versions of the runtime are available.</span></span> <span data-ttu-id="c9b2c-148">Il rollforward consente solo di selezionare versioni successive del runtime.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-148">Roll-forward only selects later versions of the runtime.</span></span>
* <span data-ttu-id="c9b2c-149">Sono disponibili solo versioni principali più elevate del runtime.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-149">Only higher major versions of the runtime are available.</span></span> <span data-ttu-id="c9b2c-150">Il rollforward non supera i limiti della versione principale.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-150">Roll-forward doesn't cross major version boundaries.</span></span>

<span data-ttu-id="c9b2c-151">Se un'applicazione non riesce a trovare un runtime appropriato, l'esecuzione non riesce e viene segnalato un errore.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-151">If an application can't find an appropriate runtime, it fails to run and reports an error.</span></span>

<span data-ttu-id="c9b2c-152">È possibile scoprire quali runtime di .NET Core sono installati nel computer usando uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9b2c-152">You can find out which .NET Core runtimes are installed on your machine using one of the following commands:</span></span>

```dotnetcli
dotnet --list-runtimes
dotnet --info
```

<span data-ttu-id="c9b2c-153">Se si ritiene che lo strumento supporti la versione di Runtime attualmente installata, è possibile contattare l'autore dello strumento e verificare se è possibile aggiornare il numero di versione o il multitarget.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-153">If you think the tool should support the runtime version you currently have installed, you can contact the tool author and see if they can update the version number or multi-target.</span></span> <span data-ttu-id="c9b2c-154">Dopo aver ricompilato e ripubblicato il pacchetto di strumenti in NuGet con un numero di versione aggiornato, è possibile aggiornare la copia.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-154">Once they've recompiled and republished their tool package to NuGet with an updated version number, you can update your copy.</span></span> <span data-ttu-id="c9b2c-155">Sebbene ciò non accada, la soluzione più rapida per l'utente consiste nell'installare una versione del runtime che funzionerebbe con lo strumento che si sta tentando di eseguire.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-155">While that doesn't happen, the quickest solution for you is to install a version of the runtime that would work with the tool you're trying to run.</span></span> <span data-ttu-id="c9b2c-156">Per scaricare una versione specifica del runtime di .NET Core, visitare la [pagina di download di .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="c9b2c-156">To download a specific .NET Core runtime version, visit the [.NET Core download page](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="c9b2c-157">Se si installa il .NET Core SDK in un percorso non predefinito, è necessario impostare la variabile di ambiente `DOTNET_ROOT` alla directory che contiene il `dotnet` eseguibile.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-157">If you install the .NET Core SDK to a non-default location, you need to set the environment variable `DOTNET_ROOT` to the directory that contains the `dotnet` executable.</span></span>

## <a name="net-core-tool-installation-fails"></a><span data-ttu-id="c9b2c-158">L'installazione dello strumento .NET Core non riesce</span><span class="sxs-lookup"><span data-stu-id="c9b2c-158">.NET Core tool installation fails</span></span>

<span data-ttu-id="c9b2c-159">Esistono diversi motivi per cui l'installazione di uno strumento .NET Core globale o locale potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-159">There are a number of reasons the installation of a .NET Core global or local tool may fail.</span></span> <span data-ttu-id="c9b2c-160">Quando l'installazione dello strumento non riesce, verrà visualizzato un messaggio simile a quello riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c9b2c-160">When the tool installation fails, you'll see a message similar to following one:</span></span>

```console
Tool '{0}' failed to install. This failure may have been caused by:

* You are attempting to install a preview release and did not use the --version option to specify the version.
* A package by this name was found, but it was not a .NET Core tool.
* The required NuGet feed cannot be accessed, perhaps because of an Internet connection problem.
* You mistyped the name of the tool.

For more reasons, including package naming enforcement, visit https://aka.ms/failure-installing-tool
```

<span data-ttu-id="c9b2c-161">Per facilitare la diagnosi di questi errori, i messaggi NuGet vengono visualizzati direttamente all'utente, insieme al messaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-161">To help diagnose these failures, NuGet messages are shown directly to the user, along with the previous message.</span></span> <span data-ttu-id="c9b2c-162">Il messaggio NuGet può essere utile per identificare il problema.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-162">The NuGet message may help you identify the problem.</span></span>

### <a name="package-naming-enforcement"></a><span data-ttu-id="c9b2c-163">Imposizione dei nomi dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="c9b2c-163">Package naming enforcement</span></span>

<span data-ttu-id="c9b2c-164">Microsoft ha modificato le linee guida sull'ID del pacchetto per gli strumenti, causando la mancata presenza di alcuni strumenti con il nome stimato.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-164">Microsoft has changed its guidance on the Package ID for tools, resulting in a number of tools not being found with the predicted name.</span></span> <span data-ttu-id="c9b2c-165">Il nuovo materiale sussidiario prevede che tutti gli strumenti Microsoft siano preceduti da "Microsoft".</span><span class="sxs-lookup"><span data-stu-id="c9b2c-165">The new guidance is that all Microsoft tools be prefixed with "Microsoft."</span></span> <span data-ttu-id="c9b2c-166">Questo prefisso è riservato e può essere usato solo per i pacchetti firmati con un certificato autorizzato da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-166">This prefix is reserved and can only be used for packages signed with a Microsoft authorized certificate.</span></span>

<span data-ttu-id="c9b2c-167">Durante la transizione, alcuni strumenti Microsoft avranno il vecchio formato dell'ID del pacchetto, mentre altri avranno il nuovo formato:</span><span class="sxs-lookup"><span data-stu-id="c9b2c-167">During the transition, some Microsoft tools will have the old form of the package ID, while others will have the new form:</span></span>

```dotnetcli
dotnet tool install -g Microsoft.<toolName>
dotnet tool install -g <toolName>
```

<span data-ttu-id="c9b2c-168">Quando vengono aggiornati gli ID del pacchetto, è necessario passare al nuovo ID del pacchetto per ottenere gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-168">As package IDs are updated, you'll need to change to the new package ID to get the latest updates.</span></span> <span data-ttu-id="c9b2c-169">I pacchetti con il nome semplificato dello strumento saranno deprecati.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-169">Packages with the simplified tool name will be deprecated.</span></span>

### <a name="preview-releases"></a><span data-ttu-id="c9b2c-170">Versioni di anteprima</span><span class="sxs-lookup"><span data-stu-id="c9b2c-170">Preview releases</span></span>

* <span data-ttu-id="c9b2c-171">Si sta tentando di installare una versione di anteprima e non è stata usata l'opzione `--version` per specificare la versione.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-171">You're attempting to install a preview release and didn't use the `--version` option to specify the version.</span></span>

<span data-ttu-id="c9b2c-172">Gli strumenti di .NET Core in anteprima devono essere specificati con una parte del nome per indicare che sono in anteprima.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-172">.NET Core tools that are in preview must be specified with a portion of the name to indicate that they are in preview.</span></span> <span data-ttu-id="c9b2c-173">Non è necessario includere l'intera anteprima.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-173">You don't need to include the entire preview.</span></span> <span data-ttu-id="c9b2c-174">Supponendo che i numeri di versione siano nel formato previsto, è possibile usare qualcosa di simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c9b2c-174">Assuming the version numbers are in the expected format, you can use something like the following example:</span></span>

```dotnetcli
dotnet tool install -g --version 1.1.0-pre <toolName>
```

> [!NOTE]
> <span data-ttu-id="c9b2c-175">Il team interfaccia della riga di comando di .NET Core prevede di aggiungere un cambio di `--preview` in una versione futura per semplificare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-175">The .NET Core CLI team is planning to add a `--preview` switch in a future release to make this easier.</span></span>

### <a name="package-isnt-a-net-core-tool"></a><span data-ttu-id="c9b2c-176">Il pacchetto non è uno strumento .NET Core</span><span class="sxs-lookup"><span data-stu-id="c9b2c-176">Package isn't a .NET Core tool</span></span>

* <span data-ttu-id="c9b2c-177">Un pacchetto NuGet con questo nome è stato trovato, ma non era uno strumento .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-177">A NuGet package by this name was found, but it wasn't a .NET Core tool.</span></span>

<span data-ttu-id="c9b2c-178">Se si tenta di installare un pacchetto NuGet che è un pacchetto NuGet normale e non uno strumento .NET Core, verrà visualizzato un errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c9b2c-178">If you try to install a NuGet package that is a regular NuGet package and not a .NET Core tool, you'll see an error similar to the following:</span></span>

> <span data-ttu-id="c9b2c-179">NU1212: combinazione del pacchetto di progetto non valida per `<ToolName>`.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-179">NU1212: Invalid project-package combination for `<ToolName>`.</span></span> <span data-ttu-id="c9b2c-180">Lo stile del progetto DotnetToolReference può contenere solo riferimenti del tipo DotnetTool.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-180">DotnetToolReference project style can only contain references of the DotnetTool type.</span></span>

### <a name="nuget-feed-cant-be-accessed"></a><span data-ttu-id="c9b2c-181">Non è possibile accedere al feed NuGet</span><span class="sxs-lookup"><span data-stu-id="c9b2c-181">NuGet feed can't be accessed</span></span>

* <span data-ttu-id="c9b2c-182">Non è possibile accedere al feed NuGet necessario, probabilmente a causa di un problema di connessione a Internet.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-182">The required NuGet feed can't be accessed, perhaps because of an Internet connection problem.</span></span>

<span data-ttu-id="c9b2c-183">L'installazione dello strumento richiede l'accesso al feed NuGet che contiene il pacchetto di strumenti.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-183">Tool installation requires access to the NuGet feed that contains the tool package.</span></span> <span data-ttu-id="c9b2c-184">Se il feed non è disponibile, l'operazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-184">It fails if the feed isn't available.</span></span> <span data-ttu-id="c9b2c-185">È possibile modificare i feed con `nuget.config`, richiedere un file di `nuget.config` specifico o specificare feed aggiuntivi con il commutatore `--add-source`.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-185">You can alter feeds with `nuget.config`, request a specific `nuget.config` file, or specify additional feeds with the `--add-source` switch.</span></span> <span data-ttu-id="c9b2c-186">Per impostazione predefinita, NuGet genera un errore per tutti i feed che non possono connettersi.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-186">By default, NuGet throws an error for any feed that can't connect.</span></span> <span data-ttu-id="c9b2c-187">Il flag `--ignore-failed-sources` possibile ignorare queste origini non raggiungibili.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-187">The flag `--ignore-failed-sources` can skip these non-reachable sources.</span></span>

### <a name="package-id-incorrect"></a><span data-ttu-id="c9b2c-188">ID pacchetto errato</span><span class="sxs-lookup"><span data-stu-id="c9b2c-188">Package ID incorrect</span></span>

* <span data-ttu-id="c9b2c-189">Il nome dello strumento è stato digitato in forma non consentita.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-189">You mistyped the name of the tool.</span></span>

<span data-ttu-id="c9b2c-190">Una causa comune dell'errore è che il nome dello strumento non è corretto.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-190">A common reason for failure is that the tool name isn't correct.</span></span> <span data-ttu-id="c9b2c-191">Questo problema può verificarsi a causa di una digitazione errata o perché lo strumento è stato spostato o è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-191">This can happen because of mistyping, or because the tool has moved or been deprecated.</span></span> <span data-ttu-id="c9b2c-192">Per gli strumenti di NuGet.org, un modo per assicurarsi che il nome sia corretto è cercare lo strumento in NuGet.org e copiare il comando di installazione.</span><span class="sxs-lookup"><span data-stu-id="c9b2c-192">For tools on NuGet.org, one way to ensure you have the name correct is to search for the tool at NuGet.org and copy the installation command.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9b2c-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9b2c-193">See also</span></span>

* [<span data-ttu-id="c9b2c-194">Panoramica degli strumenti globali .NET Core</span><span class="sxs-lookup"><span data-stu-id="c9b2c-194">.NET Core Global Tools overview</span></span>](global-tools.md)
