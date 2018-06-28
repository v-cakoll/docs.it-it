---
title: Strumenti globali .NET Core
description: Panoramica degli strumenti globali .NET Core e dei comandi dell'interfaccia della riga di comando di .NET Core disponibili.
author: KathleenDollard
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 077ffd53f1ba2988c80a637aaa109a66139736b0
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34697092"
---
# <a name="net-core-global-tools-overview"></a><span data-ttu-id="5e91b-103">Panoramica degli strumenti globali .NET Core</span><span class="sxs-lookup"><span data-stu-id="5e91b-103">.NET Core Global Tools overview</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

<span data-ttu-id="5e91b-104">Uno strumento globale .NET Core è uno speciale pacchetto NuGet che contiene un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="5e91b-104">A .NET Core Global Tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="5e91b-105">È possibile installare uno strumento globale nel computer in un percorso predefinito incluso nella variabile di ambiente PATH o in un percorso personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5e91b-105">A Global Tool can be installed on your machine on a default location that is included in the PATH environment variable or on a custom location.</span></span>

<span data-ttu-id="5e91b-106">Se si vuole usare uno strumento globale .NET Core:</span><span class="sxs-lookup"><span data-stu-id="5e91b-106">If you want to use a .NET Core Global Tool:</span></span>

* <span data-ttu-id="5e91b-107">Trovare le informazioni sullo strumento (in genere una pagina Web o una pagina di GitHub).</span><span class="sxs-lookup"><span data-stu-id="5e91b-107">Find information about the tool (usually a website or GitHub page).</span></span>
* <span data-ttu-id="5e91b-108">Verificare l'autore e le statistiche nella home page per il feed (in genere NuGet.org).</span><span class="sxs-lookup"><span data-stu-id="5e91b-108">Check the author and statistics in the home for the feed (usually NuGet.org).</span></span>
* <span data-ttu-id="5e91b-109">Installare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="5e91b-109">Install the tool.</span></span>
* <span data-ttu-id="5e91b-110">Chiamare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="5e91b-110">Call the tool.</span></span>
* <span data-ttu-id="5e91b-111">Aggiornare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="5e91b-111">Update the tool.</span></span>
* <span data-ttu-id="5e91b-112">Disinstallare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="5e91b-112">Uninstall the tool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e91b-113">Gli strumenti globali .NET Core vengono visualizzati nel percorso ed eseguiti con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="5e91b-113">.NET Core Global Tools appear on your path and run in full trust.</span></span> <span data-ttu-id="5e91b-114">Non installare gli strumenti globali .NET Core se l'autore non è attendibile.</span><span class="sxs-lookup"><span data-stu-id="5e91b-114">Do not install .NET Core Global Tools unless you trust the author.</span></span>

## <a name="find-a-net-core-global-tool"></a><span data-ttu-id="5e91b-115">Trovare uno strumento globale .NET Core</span><span class="sxs-lookup"><span data-stu-id="5e91b-115">Find a .NET Core Global Tool</span></span>

<span data-ttu-id="5e91b-116">Attualmente non è disponibile una funzionalità di ricerca degli strumenti globali nell'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5e91b-116">Currently, there isn't a Global Tool search feature in the .NET Core Command-line Interface (CLI).</span></span>

<span data-ttu-id="5e91b-117">È possibile trovare gli strumenti globali .NET Core in [NuGet](https://www.nuget.org).</span><span class="sxs-lookup"><span data-stu-id="5e91b-117">You can find .NET Core Global Tools on [NuGet](https://www.nuget.org).</span></span> <span data-ttu-id="5e91b-118">NuGet tuttavia non consente ancora di cercare specificatamente gli strumenti globali .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5e91b-118">However, NuGet doesn't yet allow you to search specifically for .NET Core Global Tools.</span></span>

<span data-ttu-id="5e91b-119">Sono anche disponibili consigli sull'uso degli strumenti nei post di blog o nel repository GitHub [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools).</span><span class="sxs-lookup"><span data-stu-id="5e91b-119">You may also find tool recommendations in blog posts or in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>

<span data-ttu-id="5e91b-120">È anche possibile visualizzare il codice sorgente degli strumenti globali creati dal team di ASP.NET nel repository GitHub [aspnet/DotNetTools](https://github.com/aspnet/DotNetTools/).</span><span class="sxs-lookup"><span data-stu-id="5e91b-120">You can also see the source code for the Global Tools created by the ASP.NET team at the [aspnet/DotNetTools](https://github.com/aspnet/DotNetTools/) GitHub repository.</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="5e91b-121">Verificare l'autore e le statistiche</span><span class="sxs-lookup"><span data-stu-id="5e91b-121">Check the author and statistics</span></span>

<span data-ttu-id="5e91b-122">Poiché vengono eseguiti con attendibilità totale e vengono in genere installati nel percorso specificato, gli strumenti globali .NET Core possono essere molto potenti.</span><span class="sxs-lookup"><span data-stu-id="5e91b-122">Since .NET Core Global Tools run in full trust and are generally installed on your path, they can be very powerful.</span></span> <span data-ttu-id="5e91b-123">Non scaricare gli strumenti da utenti non attendibili.</span><span class="sxs-lookup"><span data-stu-id="5e91b-123">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="5e91b-124">Se lo strumento è ospitato su NuGet, è possibile verificare l'autore e le statistiche eseguendo una ricerca dello strumento.</span><span class="sxs-lookup"><span data-stu-id="5e91b-124">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="5e91b-125">Installare uno strumento globale</span><span class="sxs-lookup"><span data-stu-id="5e91b-125">Install a Global Tool</span></span>

<span data-ttu-id="5e91b-126">Per installare uno strumento globale, usare il comando [dotnet tool install](dotnet-tool-install.md) dell'interfaccia di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5e91b-126">To install a Global Tool, you use the [dotnet tool install](dotnet-tool-install.md) .NET Core CLI command.</span></span> <span data-ttu-id="5e91b-127">L'esempio seguente illustra come installare uno strumento globale nel percorso predefinito:</span><span class="sxs-lookup"><span data-stu-id="5e91b-127">The following example shows how to install a Global Tool in the default location:</span></span>

```console
dotnet tool install -g dotnetsay
```

<span data-ttu-id="5e91b-128">Se lo strumento non può essere installato, vengono visualizzati messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="5e91b-128">If the tool can't be installed, error messages are displayed.</span></span> <span data-ttu-id="5e91b-129">Verificare che i feed previsti vengano controllati.</span><span class="sxs-lookup"><span data-stu-id="5e91b-129">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="5e91b-130">Se si sta tentando di installare una versione non definitiva o una versione specifica dello strumento, è possibile specificare il numero di versione usando il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="5e91b-130">If you're trying to install a pre-release version or a specific version of the tool, you can specify the version number using the following format:</span></span>

```console
dotnet tool install -g <package-name> --version <version-number>
```

<span data-ttu-id="5e91b-131">Se l'installazione ha esito positivo, viene visualizzato un messaggio che mostra il comando usato per chiamare lo strumento e la versione installata, simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5e91b-131">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.0.0') was successfully installed.
```

<span data-ttu-id="5e91b-132">Gli strumenti globali possono essere installati nella directory predefinita o in un percorso specifico.</span><span class="sxs-lookup"><span data-stu-id="5e91b-132">Global Tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="5e91b-133">Le directory predefinite sono:</span><span class="sxs-lookup"><span data-stu-id="5e91b-133">The default directories are:</span></span>

| <span data-ttu-id="5e91b-134">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="5e91b-134">OS</span></span>          | <span data-ttu-id="5e91b-135">Path</span><span class="sxs-lookup"><span data-stu-id="5e91b-135">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="5e91b-136">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="5e91b-136">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="5e91b-137">WINDOWS</span><span class="sxs-lookup"><span data-stu-id="5e91b-137">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="5e91b-138">Questi percorsi vengono aggiunti al percorso dell'utente alla prima esecuzione dell'SDK in modo che gli strumenti globali installati possano essere chiamati direttamente.</span><span class="sxs-lookup"><span data-stu-id="5e91b-138">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="5e91b-139">Si noti che gli strumenti globali sono specifici dell'utente e non globali del computer.</span><span class="sxs-lookup"><span data-stu-id="5e91b-139">Note that the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="5e91b-140">Per questa ragione non è possibile installare uno strumento globale disponibile per tutti gli utenti del computer.</span><span class="sxs-lookup"><span data-stu-id="5e91b-140">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="5e91b-141">Lo strumento è disponibile solo per i singoli profili utente in cui è stato installato.</span><span class="sxs-lookup"><span data-stu-id="5e91b-141">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="5e91b-142">Gli strumenti globali possono anche essere installati in una directory specifica.</span><span class="sxs-lookup"><span data-stu-id="5e91b-142">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="5e91b-143">Quando vengono installati in una directory specifica, l'utente deve verificare che il comando sia disponibile includendo la directory nel percorso, chiamando il comando con la directory specificata chiamando lo strumento dall'interno della directory specificata.</span><span class="sxs-lookup"><span data-stu-id="5e91b-143">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="5e91b-144">In questo caso l'interfaccia della riga di comando di .NET Core non aggiunge automaticamente il percorso alla variabile di ambiente PATH.</span><span class="sxs-lookup"><span data-stu-id="5e91b-144">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="use-the-tool"></a><span data-ttu-id="5e91b-145">Usare lo strumento</span><span class="sxs-lookup"><span data-stu-id="5e91b-145">Use the tool</span></span>

<span data-ttu-id="5e91b-146">Dopo aver installato lo strumento, è possibile chiamarlo usando il relativo comando.</span><span class="sxs-lookup"><span data-stu-id="5e91b-146">Once the tool is installed, you can call it by using its command.</span></span> <span data-ttu-id="5e91b-147">Si noti che il comando potrebbe non corrispondere al nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5e91b-147">Note that the command may not be the same as the package name.</span></span>

<span data-ttu-id="5e91b-148">Se il comando è `dotnetsay`, è possibile chiamarlo con:</span><span class="sxs-lookup"><span data-stu-id="5e91b-148">If the command is `dotnetsay`, you call it with:</span></span>

```console
dotnetsay
```

<span data-ttu-id="5e91b-149">Se l'autore dello strumento voleva che lo strumento fosse visualizzato nel contesto del prompt di `dotnet`, è possibile che lo strumento sia stato progettato in modo da essere chiamato come `dotnet <command>`, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5e91b-149">If the tool author wanted the tool to appear in the context of the `dotnet` prompt, they may have written it in a way that you call it as `dotnet <command>`, such as:</span></span>

```console
dotnet doc
```

<span data-ttu-id="5e91b-150">Per scoprire quali strumenti sono inclusi in un pacchetto di strumenti globali installato è possibile visualizzare l'elenco dei pacchetti installati tramite il comando [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="5e91b-150">You can find which tools are included in an installed Global Tool package by listing the installed packages using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

<span data-ttu-id="5e91b-151">È anche possibile cercare le istruzioni d'uso nel sito Web dello strumento o digitando uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e91b-151">You can also look for usage instructions at the tool's website or by typing one of the following commands:</span></span>

```console
<command> --help
dotnet <command> --help
```

### <a name="what-could-go-wrong"></a><span data-ttu-id="5e91b-152">Problemi possibili</span><span class="sxs-lookup"><span data-stu-id="5e91b-152">What could go wrong</span></span>

<span data-ttu-id="5e91b-153">Gli strumenti globali sono [applicazioni dipendenti dal framework](../deploying/index.md#framework-dependent-deployments-fdd), ovvero sono basati su un runtime di .NET Core installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="5e91b-153">Global Tools are [framework-dependent applications](../deploying/index.md#framework-dependent-deployments-fdd), which means they rely on a .NET Core runtime installed on your machine.</span></span> <span data-ttu-id="5e91b-154">Se il runtime previsto non viene trovato, agli strumenti si applicano le normali regole di rollforward di runtime di .NET Core, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5e91b-154">If the expected runtime is not found, they follow normal .NET Core runtime roll-forward rules such as:</span></span>

* <span data-ttu-id="5e91b-155">Un'applicazione esegue il roll forward alla versione di patch più recente della versione principale e secondaria specificate.</span><span class="sxs-lookup"><span data-stu-id="5e91b-155">An application rolls forward to the highest patch release of the specified major and minor version.</span></span>
* <span data-ttu-id="5e91b-156">Se non è presente alcun runtime corrispondente con un numero di versione principale o secondaria, viene usata la successiva versione più elevata.</span><span class="sxs-lookup"><span data-stu-id="5e91b-156">If there is no matching runtime with a matching major and minor version number, the next higher minor version is used.</span></span>
* <span data-ttu-id="5e91b-157">Il roll forward non viene eseguito tra due versioni di anteprima del runtime o tra versioni di anteprima e versioni di rilascio.</span><span class="sxs-lookup"><span data-stu-id="5e91b-157">Roll forward doesn't occur between preview versions of the runtime or between preview versions and release versions.</span></span> <span data-ttu-id="5e91b-158">Di conseguenza, gli strumenti globali creati usando le versioni di anteprima devono essere ricompilati e ripubblicati dall'autore e reinstallati.</span><span class="sxs-lookup"><span data-stu-id="5e91b-158">Thus, Global Tools created using preview versions must be rebuilt and republished by the author and reinstalled.</span></span>
* <span data-ttu-id="5e91b-159">È possibile che si verifichino ulteriori problemi con gli strumenti globali creati in .NET Core 2.1 Preview 1.</span><span class="sxs-lookup"><span data-stu-id="5e91b-159">Additional issues can occur with Global Tools created in .NET Core 2.1 Preview 1.</span></span> <span data-ttu-id="5e91b-160">Per altre informazioni, vedere [.NET Core 2.1 Preview 2 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/2.1/Preview/2.1.0-preview2-known-issues.md) (Problemi noti di NET Core 2.1 Preview 2).</span><span class="sxs-lookup"><span data-stu-id="5e91b-160">For more information, see [.NET Core 2.1 Preview 2 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/2.1/Preview/2.1.0-preview2-known-issues.md).</span></span>

<span data-ttu-id="5e91b-161">Se un'applicazione non trova un runtime appropriato, non viene eseguita e viene segnalato un errore.</span><span class="sxs-lookup"><span data-stu-id="5e91b-161">If an application cannot find an appropriate runtime, it fails to run and reports an error.</span></span>

<span data-ttu-id="5e91b-162">Un altro problema potrebbe essere costituito da uno strumento globale creato con un'anteprima precedente che non viene eseguito con i runtime .NET Core correntemente installati.</span><span class="sxs-lookup"><span data-stu-id="5e91b-162">Another issue that might happen is that a Global Tool that was created during an earlier preview may not run with your currently installed .NET Core runtimes.</span></span> <span data-ttu-id="5e91b-163">È possibile visualizzare i runtime installati nel computer usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5e91b-163">You can see which runtimes are installed on your machine using the following command:</span></span>

```console
dotnet --list-runtimes
```

<span data-ttu-id="5e91b-164">Contattare l'autore dello strumento globale e verificare se è possibile ricompilare e ripubblicare il pacchetto di strumenti in NuGet con un numero di versione aggiornata.</span><span class="sxs-lookup"><span data-stu-id="5e91b-164">Contact the author of the Global Tool and see if they can recompile and republish their tool package to NuGet with an updated version number.</span></span> <span data-ttu-id="5e91b-165">Dopo aver aggiornato il pacchetto su NuGet, è possibile aggiornare la copia.</span><span class="sxs-lookup"><span data-stu-id="5e91b-165">Once they have updated the package on NuGet, you can update your copy.</span></span>

<span data-ttu-id="5e91b-166">L'interfaccia della riga di comando di .NET Core tenta di aggiungere i percorsi predefiniti alla variabile di ambiente PATH al primo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="5e91b-166">The .NET Core CLI tries to add the default locations to the PATH environment variable on its first usage.</span></span> <span data-ttu-id="5e91b-167">Esistono tuttavia un paio di scenari in cui è possibile che il percorso non venga aggiunto automaticamente alla variabile di ambiente PATH, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5e91b-167">However, there are a couple of scenarios where the location might not be added to PATH automatically, such as:</span></span>

* <span data-ttu-id="5e91b-168">Se è stata impostata la variabile di ambiente `DOTNET_SKIP_FIRST_TIME_EXPERIENCE`.</span><span class="sxs-lookup"><span data-stu-id="5e91b-168">If you've set the `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` environment variable.</span></span>
* <span data-ttu-id="5e91b-169">In macOS se è stato installato .NET Core SDK usando file *.tar.gz* e non *.pkg*.</span><span class="sxs-lookup"><span data-stu-id="5e91b-169">On macOS, if you've installed the .NET Core SDK using *.tar.gz* files and not *.pkg*.</span></span>
* <span data-ttu-id="5e91b-170">In Linux è necessario modificare il file di ambiente della shell per configurare la variabile PATH.</span><span class="sxs-lookup"><span data-stu-id="5e91b-170">On Linux, you need to edit the shell environment file to configure the PATH.</span></span>

## <a name="other-cli-commands"></a><span data-ttu-id="5e91b-171">Altri comandi dell'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="5e91b-171">Other CLI commands</span></span>

<span data-ttu-id="5e91b-172">.NET Core SDK contiene altri comandi che supportano gli strumenti globali .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5e91b-172">The .NET Core SDK contains other commands that support .NET Core Global Tools.</span></span> <span data-ttu-id="5e91b-173">Usare uno dei comandi `dotnet tool` con una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e91b-173">Use any of the `dotnet tool` commands with one of the following options:</span></span>

* <span data-ttu-id="5e91b-174">`--global` o `-g` specifica che il comando è applicabile agli strumenti globali a livello utente.</span><span class="sxs-lookup"><span data-stu-id="5e91b-174">`--global` or `-g` specifies that the command is applicable to user-wide Global Tools.</span></span>
* <span data-ttu-id="5e91b-175">`--tool-path` specifica un percorso personalizzato per gli strumenti globali.</span><span class="sxs-lookup"><span data-stu-id="5e91b-175">`--tool-path` specifies a custom location for Global Tools.</span></span>

<span data-ttu-id="5e91b-176">Per individuare i comandi disponibili per gli strumenti globali:</span><span class="sxs-lookup"><span data-stu-id="5e91b-176">To find out which commands are available for Global Tools:</span></span>

```console
dotnet tool --help
```

<span data-ttu-id="5e91b-177">L'aggiornamento di uno strumento globale prevede la disinstallazione e la reinstallazione con l'ultima versione stabile.</span><span class="sxs-lookup"><span data-stu-id="5e91b-177">Updating a Global Tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="5e91b-178">Per aggiornare uno strumento globale, usare il comando [dotnet tool update](dotnet-tool-update.md):</span><span class="sxs-lookup"><span data-stu-id="5e91b-178">To update a Global Tool, use the [dotnet tool update](dotnet-tool-update.md) command:</span></span>

```console
dotnet tool update -g <packagename>
```

<span data-ttu-id="5e91b-179">Rimuovere un strumento globale usando [dotnet tool uninstall](dotnet-tool-uninstall.md):</span><span class="sxs-lookup"><span data-stu-id="5e91b-179">Remove a Global Tool using the [dotnet tool uninstall](dotnet-tool-uninstall.md):</span></span>

```console
dotnet tool uninstall -g <packagename>
```

<span data-ttu-id="5e91b-180">Per visualizzare tutti gli strumenti globali attualmente installati nel computer, con la versione e comandi, usare il comando [dotnet tool list](dotnet-tool-list.md):</span><span class="sxs-lookup"><span data-stu-id="5e91b-180">To display all of the Global Tools currently installed on the machine, along with their version and commands, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```console
dotnet tool list -g
```