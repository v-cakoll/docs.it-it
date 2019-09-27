---
title: Strumenti globali .NET Core
description: Panoramica degli strumenti globali .NET Core e dei comandi dell'interfaccia della riga di comando di .NET Core disponibili.
author: KathleenDollard
ms.date: 05/29/2018
ms.custom: seodec18
ms.openlocfilehash: 40a0aabcf523e8dac9a3ad226064bbb3c1b3ce5b
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332012"
---
# <a name="net-core-global-tools-overview"></a><span data-ttu-id="7dc00-103">Panoramica degli strumenti globali .NET Core</span><span class="sxs-lookup"><span data-stu-id="7dc00-103">.NET Core Global Tools overview</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

<span data-ttu-id="7dc00-104">Uno strumento globale .NET Core è uno speciale pacchetto NuGet che contiene un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="7dc00-104">A .NET Core Global Tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="7dc00-105">È possibile installare uno strumento globale nel computer in un percorso predefinito incluso nella variabile di ambiente PATH o in un percorso personalizzato.</span><span class="sxs-lookup"><span data-stu-id="7dc00-105">A Global Tool can be installed on your machine on a default location that is included in the PATH environment variable or on a custom location.</span></span>

<span data-ttu-id="7dc00-106">Se si vuole usare uno strumento globale .NET Core:</span><span class="sxs-lookup"><span data-stu-id="7dc00-106">If you want to use a .NET Core Global Tool:</span></span>

* <span data-ttu-id="7dc00-107">Trovare le informazioni sullo strumento (in genere una pagina Web o una pagina di GitHub).</span><span class="sxs-lookup"><span data-stu-id="7dc00-107">Find information about the tool (usually a website or GitHub page).</span></span>
* <span data-ttu-id="7dc00-108">Verificare l'autore e le statistiche nella home page per il feed (in genere NuGet.org).</span><span class="sxs-lookup"><span data-stu-id="7dc00-108">Check the author and statistics in the home for the feed (usually NuGet.org).</span></span>
* <span data-ttu-id="7dc00-109">Installare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="7dc00-109">Install the tool.</span></span>
* <span data-ttu-id="7dc00-110">Chiamare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="7dc00-110">Call the tool.</span></span>
* <span data-ttu-id="7dc00-111">Aggiornare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="7dc00-111">Update the tool.</span></span>
* <span data-ttu-id="7dc00-112">Disinstallare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="7dc00-112">Uninstall the tool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7dc00-113">Gli strumenti globali .NET Core vengono visualizzati nel percorso ed eseguiti con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="7dc00-113">.NET Core Global Tools appear on your path and run in full trust.</span></span> <span data-ttu-id="7dc00-114">Non installare gli strumenti globali .NET Core se l'autore non è attendibile.</span><span class="sxs-lookup"><span data-stu-id="7dc00-114">Do not install .NET Core Global Tools unless you trust the author.</span></span>

## <a name="find-a-net-core-global-tool"></a><span data-ttu-id="7dc00-115">Trovare uno strumento globale .NET Core</span><span class="sxs-lookup"><span data-stu-id="7dc00-115">Find a .NET Core Global Tool</span></span>

<span data-ttu-id="7dc00-116">Attualmente non è disponibile una funzionalità di ricerca degli strumenti globali nell'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7dc00-116">Currently, there isn't a Global Tool search feature in the .NET Core Command-line Interface (CLI).</span></span>

<span data-ttu-id="7dc00-117">È possibile trovare gli strumenti globali .NET Core in [NuGet](https://www.nuget.org).</span><span class="sxs-lookup"><span data-stu-id="7dc00-117">You can find .NET Core Global Tools on [NuGet](https://www.nuget.org).</span></span> <span data-ttu-id="7dc00-118">NuGet tuttavia non consente ancora di cercare specificatamente gli strumenti globali .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7dc00-118">However, NuGet doesn't yet allow you to search specifically for .NET Core Global Tools.</span></span>

<span data-ttu-id="7dc00-119">Sono anche disponibili consigli sull'uso degli strumenti nei post di blog o nel repository GitHub [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools).</span><span class="sxs-lookup"><span data-stu-id="7dc00-119">You may also find tool recommendations in blog posts or in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>

<span data-ttu-id="7dc00-120">È anche possibile visualizzare il codice sorgente degli strumenti globali creati dal team di ASP.NET nel repository GitHub [aspnet/DotNetTools](https://github.com/aspnet/DotNetTools/).</span><span class="sxs-lookup"><span data-stu-id="7dc00-120">You can also see the source code for the Global Tools created by the ASP.NET team at the [aspnet/DotNetTools](https://github.com/aspnet/DotNetTools/) GitHub repository.</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="7dc00-121">Verificare l'autore e le statistiche</span><span class="sxs-lookup"><span data-stu-id="7dc00-121">Check the author and statistics</span></span>

<span data-ttu-id="7dc00-122">Poiché vengono eseguiti con attendibilità totale e vengono in genere installati nel percorso specificato, gli strumenti globali .NET Core possono essere molto potenti.</span><span class="sxs-lookup"><span data-stu-id="7dc00-122">Since .NET Core Global Tools run in full trust and are generally installed on your path, they can be very powerful.</span></span> <span data-ttu-id="7dc00-123">Non scaricare gli strumenti da utenti non attendibili.</span><span class="sxs-lookup"><span data-stu-id="7dc00-123">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="7dc00-124">Se lo strumento è ospitato su NuGet, è possibile verificare l'autore e le statistiche eseguendo una ricerca dello strumento.</span><span class="sxs-lookup"><span data-stu-id="7dc00-124">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="7dc00-125">Installare uno strumento globale</span><span class="sxs-lookup"><span data-stu-id="7dc00-125">Install a Global Tool</span></span>

<span data-ttu-id="7dc00-126">Per installare uno strumento globale, usare il comando [dotnet tool install](dotnet-tool-install.md) dell'interfaccia di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7dc00-126">To install a Global Tool, you use the [dotnet tool install](dotnet-tool-install.md) .NET Core CLI command.</span></span> <span data-ttu-id="7dc00-127">L'esempio seguente illustra come installare uno strumento globale nel percorso predefinito:</span><span class="sxs-lookup"><span data-stu-id="7dc00-127">The following example shows how to install a Global Tool in the default location:</span></span>

```dotnetcli
dotnet tool install -g dotnetsay
```

<span data-ttu-id="7dc00-128">Se lo strumento non può essere installato, vengono visualizzati messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="7dc00-128">If the tool can't be installed, error messages are displayed.</span></span> <span data-ttu-id="7dc00-129">Verificare che i feed previsti vengano controllati.</span><span class="sxs-lookup"><span data-stu-id="7dc00-129">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="7dc00-130">Se si sta tentando di installare una versione non definitiva o una versione specifica dello strumento, è possibile specificare il numero di versione usando il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="7dc00-130">If you're trying to install a pre-release version or a specific version of the tool, you can specify the version number using the following format:</span></span>

```dotnetcli
dotnet tool install -g <package-name> --version <version-number>
```

<span data-ttu-id="7dc00-131">Se l'installazione ha esito positivo, viene visualizzato un messaggio che mostra il comando usato per chiamare lo strumento e la versione installata, simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="7dc00-131">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.0.0') was successfully installed.
```

<span data-ttu-id="7dc00-132">Gli strumenti globali possono essere installati nella directory predefinita o in un percorso specifico.</span><span class="sxs-lookup"><span data-stu-id="7dc00-132">Global Tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="7dc00-133">Le directory predefinite sono:</span><span class="sxs-lookup"><span data-stu-id="7dc00-133">The default directories are:</span></span>

| <span data-ttu-id="7dc00-134">OS</span><span class="sxs-lookup"><span data-stu-id="7dc00-134">OS</span></span>          | <span data-ttu-id="7dc00-135">`Path`</span><span class="sxs-lookup"><span data-stu-id="7dc00-135">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="7dc00-136">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="7dc00-136">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="7dc00-137">Windows</span><span class="sxs-lookup"><span data-stu-id="7dc00-137">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="7dc00-138">Questi percorsi vengono aggiunti al percorso dell'utente alla prima esecuzione dell'SDK in modo che gli strumenti globali installati possano essere chiamati direttamente.</span><span class="sxs-lookup"><span data-stu-id="7dc00-138">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="7dc00-139">Si noti che gli strumenti globali sono specifici dell'utente e non globali del computer.</span><span class="sxs-lookup"><span data-stu-id="7dc00-139">Note that the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="7dc00-140">Per questa ragione non è possibile installare uno strumento globale disponibile per tutti gli utenti del computer.</span><span class="sxs-lookup"><span data-stu-id="7dc00-140">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="7dc00-141">Lo strumento è disponibile solo per i singoli profili utente in cui è stato installato.</span><span class="sxs-lookup"><span data-stu-id="7dc00-141">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="7dc00-142">Gli strumenti globali possono anche essere installati in una directory specifica.</span><span class="sxs-lookup"><span data-stu-id="7dc00-142">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="7dc00-143">Quando vengono installati in una directory specifica, l'utente deve verificare che il comando sia disponibile includendo la directory nel percorso, chiamando il comando con la directory specificata chiamando lo strumento dall'interno della directory specificata.</span><span class="sxs-lookup"><span data-stu-id="7dc00-143">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="7dc00-144">In questo caso l'interfaccia della riga di comando di .NET Core non aggiunge automaticamente il percorso alla variabile di ambiente PATH.</span><span class="sxs-lookup"><span data-stu-id="7dc00-144">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="use-the-tool"></a><span data-ttu-id="7dc00-145">Usare lo strumento</span><span class="sxs-lookup"><span data-stu-id="7dc00-145">Use the tool</span></span>

<span data-ttu-id="7dc00-146">Dopo aver installato lo strumento, è possibile chiamarlo usando il relativo comando.</span><span class="sxs-lookup"><span data-stu-id="7dc00-146">Once the tool is installed, you can call it by using its command.</span></span> <span data-ttu-id="7dc00-147">Si noti che il comando potrebbe non corrispondere al nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7dc00-147">Note that the command may not be the same as the package name.</span></span>

<span data-ttu-id="7dc00-148">Se il comando è `dotnetsay`, è possibile chiamarlo con:</span><span class="sxs-lookup"><span data-stu-id="7dc00-148">If the command is `dotnetsay`, you call it with:</span></span>

```console
dotnetsay
```

<span data-ttu-id="7dc00-149">Se l'autore dello strumento voleva che lo strumento fosse visualizzato nel contesto del prompt di `dotnet`, è possibile che lo strumento sia stato progettato in modo da essere chiamato come `dotnet <command>`, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7dc00-149">If the tool author wanted the tool to appear in the context of the `dotnet` prompt, they may have written it in a way that you call it as `dotnet <command>`, such as:</span></span>

```dotnetcli
dotnet doc
```

<span data-ttu-id="7dc00-150">Per scoprire quali strumenti sono inclusi in un pacchetto di strumenti globali installato è possibile visualizzare l'elenco dei pacchetti installati tramite il comando [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="7dc00-150">You can find which tools are included in an installed Global Tool package by listing the installed packages using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

<span data-ttu-id="7dc00-151">È anche possibile cercare le istruzioni d'uso nel sito Web dello strumento o digitando uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7dc00-151">You can also look for usage instructions at the tool's website or by typing one of the following commands:</span></span>

```console
<command> --help
dotnet <command> --help
```

## <a name="other-cli-commands"></a><span data-ttu-id="7dc00-152">Altri comandi dell'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="7dc00-152">Other CLI commands</span></span>

<span data-ttu-id="7dc00-153">.NET Core SDK contiene altri comandi che supportano gli strumenti globali .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7dc00-153">The .NET Core SDK contains other commands that support .NET Core Global Tools.</span></span> <span data-ttu-id="7dc00-154">Usare uno dei comandi `dotnet tool` con una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7dc00-154">Use any of the `dotnet tool` commands with one of the following options:</span></span>

* <span data-ttu-id="7dc00-155">`--global` o `-g` specifica che il comando è applicabile agli strumenti globali a livello utente.</span><span class="sxs-lookup"><span data-stu-id="7dc00-155">`--global` or `-g` specifies that the command is applicable to user-wide Global Tools.</span></span>
* <span data-ttu-id="7dc00-156">`--tool-path` specifica un percorso personalizzato per gli strumenti globali.</span><span class="sxs-lookup"><span data-stu-id="7dc00-156">`--tool-path` specifies a custom location for Global Tools.</span></span>

<span data-ttu-id="7dc00-157">Per individuare i comandi disponibili per gli strumenti globali:</span><span class="sxs-lookup"><span data-stu-id="7dc00-157">To find out which commands are available for Global Tools:</span></span>

```dotnetcli
dotnet tool --help
```

<span data-ttu-id="7dc00-158">L'aggiornamento di uno strumento globale prevede la disinstallazione e la reinstallazione con l'ultima versione stabile.</span><span class="sxs-lookup"><span data-stu-id="7dc00-158">Updating a Global Tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="7dc00-159">Per aggiornare uno strumento globale, usare il comando [dotnet tool update](dotnet-tool-update.md):</span><span class="sxs-lookup"><span data-stu-id="7dc00-159">To update a Global Tool, use the [dotnet tool update](dotnet-tool-update.md) command:</span></span>

```dotnetcli
dotnet tool update -g <packagename>
```

<span data-ttu-id="7dc00-160">Rimuovere un strumento globale usando [dotnet tool uninstall](dotnet-tool-uninstall.md):</span><span class="sxs-lookup"><span data-stu-id="7dc00-160">Remove a Global Tool using the [dotnet tool uninstall](dotnet-tool-uninstall.md):</span></span>

```dotnetcli
dotnet tool uninstall -g <packagename>
```

<span data-ttu-id="7dc00-161">Per visualizzare tutti gli strumenti globali attualmente installati nel computer, con la versione e comandi, usare il comando [dotnet tool list](dotnet-tool-list.md):</span><span class="sxs-lookup"><span data-stu-id="7dc00-161">To display all of the Global Tools currently installed on the machine, along with their version and commands, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```dotnetcli
dotnet tool list -g
```

## <a name="see-also"></a><span data-ttu-id="7dc00-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7dc00-162">See also</span></span>

* [<span data-ttu-id="7dc00-163">Risolvere i problemi di utilizzo degli strumenti .NET Core</span><span class="sxs-lookup"><span data-stu-id="7dc00-163">Troubleshoot .NET Core tool usage issues</span></span>](troubleshoot-usage-issues.md)
