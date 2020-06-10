---
title: Come installare lo strumento dell'interfaccia della riga di comando (CLI) di ML.NET
description: Informazioni su come installare, aggiornare, eseguire il downgrade e disinstallare lo strumento dell'interfaccia della riga di comando ML.NET.
ms.date: 06/08/2020
ms.custom: mlnet-tooling
ms.openlocfilehash: 13203246411deadf3ab13a5eba0d2c8e6e9027c5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602271"
---
# <a name="how-to-install-the-mlnet-command-line-interface-cli-tool"></a><span data-ttu-id="161ab-103">Come installare lo strumento dell'interfaccia della riga di comando (CLI) di ML.NET</span><span class="sxs-lookup"><span data-stu-id="161ab-103">How to install the ML.NET Command-Line Interface (CLI) tool</span></span>

<span data-ttu-id="161ab-104">Informazioni su come installare l'interfaccia della riga di comando di ML.NET in Windows, Mac o Linux.</span><span class="sxs-lookup"><span data-stu-id="161ab-104">Learn how to install the ML.NET CLI (command-line interface) on Windows, Mac, or Linux.</span></span>

<span data-ttu-id="161ab-105">L'interfaccia della riga di comando di ML.NET genera modelli ML.NET e codice sorgente di qualità elevata usando l'apprendimento automatico automatico (AutoML) e un set di dati di training.</span><span class="sxs-lookup"><span data-stu-id="161ab-105">The ML.NET CLI generates good quality ML.NET models and source code using automated machine learning (AutoML) and a training dataset.</span></span>

> [!NOTE]
> <span data-ttu-id="161ab-106">Questo argomento fa riferimento all'interfaccia della riga di comando di ML.NET e al Machine Learning automatico, attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="161ab-106">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="161ab-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="161ab-107">Pre-requisites</span></span>

- [<span data-ttu-id="161ab-108">SDK di .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="161ab-108">.NET Core 3.1 SDK</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

- <span data-ttu-id="161ab-109">Opzionale [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)</span><span class="sxs-lookup"><span data-stu-id="161ab-109">(Optional) [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)</span></span>

<span data-ttu-id="161ab-110">È possibile eseguire i progetti di codice C# generati con Visual Studio premendo il `F5` tasto o con `dotnet run` (interfaccia della riga di comando di .NET Core).</span><span class="sxs-lookup"><span data-stu-id="161ab-110">You can run the generated C# code projects with Visual Studio by pressing the `F5` key or with `dotnet run` (.NET Core CLI).</span></span>

<span data-ttu-id="161ab-111">Nota: se dopo l'installazione .NET Core SDK il `dotnet tool` comando non funziona, disconnettersi da Windows ed eseguire di nuovo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="161ab-111">Note: If after installing .NET Core SDK the `dotnet tool` command is not working, sign out from Windows and sign in again.</span></span>

## <a name="install"></a><span data-ttu-id="161ab-112">Installazione</span><span class="sxs-lookup"><span data-stu-id="161ab-112">Install</span></span>

<span data-ttu-id="161ab-113">L'interfaccia della riga di comando di ML.NET viene installata come gli altri strumenti globali dotnet.</span><span class="sxs-lookup"><span data-stu-id="161ab-113">The ML.NET CLI is installed like any other dotnet Global Tool.</span></span> <span data-ttu-id="161ab-114">Usare il comando dell'interfaccia della riga di comando di .NET Core `dotnet tool install`.</span><span class="sxs-lookup"><span data-stu-id="161ab-114">You use the `dotnet tool install` .NET Core CLI command.</span></span>

<span data-ttu-id="161ab-115">L'esempio seguente illustra come installare l'interfaccia della riga di comando di ML.NET nel percorso del feed NuGet predefinito:</span><span class="sxs-lookup"><span data-stu-id="161ab-115">The following example shows how to install the ML.NET CLI in the default NuGet feed location:</span></span>

```dotnetcli
dotnet tool install -g mlnet
```

<span data-ttu-id="161ab-116">Se lo strumento non può essere installato (ovvero, se non è disponibile nel feed NuGet predefinito), vengono visualizzati i messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="161ab-116">If the tool can't be installed (that is, if it is not available at the default NuGet feed), error messages are displayed.</span></span> <span data-ttu-id="161ab-117">Verificare che i feed previsti vengano controllati.</span><span class="sxs-lookup"><span data-stu-id="161ab-117">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="161ab-118">Se l'installazione ha esito positivo, viene visualizzato un messaggio che mostra il comando usato per chiamare lo strumento e la versione installata, simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="161ab-118">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```console
You can invoke the tool using the following command: mlnet
Tool 'mlnet' (version 'X.X.X') was successfully installed.
```

<span data-ttu-id="161ab-119">È possibile verificare che l'installazione sia avvenuta correttamente digitando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="161ab-119">You can confirm the installation was successful by typing the following command:</span></span>

```console
mlnet
```

<span data-ttu-id="161ab-120">Dovrebbe essere visualizzata la guida per i comandi disponibili per lo strumento mlnet, ad esempio il comando "classificazione".</span><span class="sxs-lookup"><span data-stu-id="161ab-120">You should see the help for available commands for the mlnet tool such as the 'classification' command.</span></span>

## <a name="install-a-specific-release-version"></a><span data-ttu-id="161ab-121">Installare una versione specifica</span><span class="sxs-lookup"><span data-stu-id="161ab-121">Install a specific release version</span></span>

<span data-ttu-id="161ab-122">Se si sta tentando di installare una versione non definitiva o una versione specifica dello strumento, è possibile specificare il [framework](../../standard/frameworks.md) usando il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="161ab-122">If you're trying to install a pre-release version or a specific version of the tool, you can specify the [framework](../../standard/frameworks.md) using the following format:</span></span>

```dotnetcli
dotnet tool install -g mlnet --framework <FRAMEWORK>
```

<span data-ttu-id="161ab-123">È anche possibile verificare se il pacchetto è installato correttamente digitando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="161ab-123">You can also check if the package is properly installed by typing the following command:</span></span>

```dotnetcli
dotnet tool list -g
```

## <a name="uninstall-the-cli-package"></a><span data-ttu-id="161ab-124">Disinstallare il pacchetto dell'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="161ab-124">Uninstall the CLI package</span></span>

<span data-ttu-id="161ab-125">Digitare il comando seguente per disinstallare il pacchetto dal computer locale:</span><span class="sxs-lookup"><span data-stu-id="161ab-125">Type the following command to uninstall the package from your local machine:</span></span>

```dotnetcli
dotnet tool uninstall mlnet -g
```

## <a name="update-the-cli-package"></a><span data-ttu-id="161ab-126">Aggiornare il pacchetto dell'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="161ab-126">Update the CLI package</span></span>

<span data-ttu-id="161ab-127">Digitare il comando seguente per aggiornare il pacchetto del computer locale:</span><span class="sxs-lookup"><span data-stu-id="161ab-127">Type the following command to update the package from your local machine:</span></span>

```dotnetcli
dotnet tool update -g mlnet
```

## <a name="set-up-cli-suggestions-tab-based-auto-completion"></a><span data-ttu-id="161ab-128">Configurare i suggerimenti dell'interfaccia della riga di comando (completamento automatico con il tasto TAB)</span><span class="sxs-lookup"><span data-stu-id="161ab-128">Set up CLI suggestions (tab-based auto-completion)</span></span>

<span data-ttu-id="161ab-129">Poiché è basata su `System.CommandLine`, l'interfaccia della riga di comando di ML.NET include un supporto predefinito per il completamento con il tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="161ab-129">Since the ML.NET CLI is based on `System.CommandLine`, it has built-in support for tab completion.</span></span>

<span data-ttu-id="161ab-130">L'animazione seguente mostra un esempio del funzionamento del completamento automatico con il tasto TAB:</span><span class="sxs-lookup"><span data-stu-id="161ab-130">An example of how tab auto completion works is shown in the following animation:</span></span>

![image](./media/cli-tab-completion.gif)

<span data-ttu-id="161ab-132">Il completamento automatico con il tasto TAB (suggerimenti di parametri) può essere usato in *Windows PowerShell* e *bash macOS/Linux* ma non in *Windows CMD*.</span><span class="sxs-lookup"><span data-stu-id="161ab-132">'Tab-based auto-completion' (parameter suggestions) works on *Windows PowerShell* and *macOS/Linux bash* but it won't work on *Windows CMD*.</span></span>

<span data-ttu-id="161ab-133">Per abilitarlo nella versione di anteprima corrente è necessario che l'utente finale esegua le operazioni descritte di seguito per ogni shell.</span><span class="sxs-lookup"><span data-stu-id="161ab-133">To enable it, in the current preview version, the end user has to take a few steps once per shell, outlined below.</span></span> <span data-ttu-id="161ab-134">Al termine, il completamento potrà essere usato per tutte le app scritte con `System.CommandLine`, ad esempio l'interfaccia della riga di comando di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="161ab-134">Once this is done, completions will work for all apps written using `System.CommandLine` such as the ML.NET CLI.</span></span>

<span data-ttu-id="161ab-135">Nel computer in cui si vuole abilitare il completamento, è necessario eseguire due operazioni.</span><span class="sxs-lookup"><span data-stu-id="161ab-135">On the machine where you'd like to enable completion, you'll need to do two things.</span></span>

1. <span data-ttu-id="161ab-136">Installare lo strumento globale `dotnet-suggest` eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="161ab-136">Install the `dotnet-suggest` global tool by running the following command:</span></span>

    ```dotnetcli
    dotnet tool install dotnet-suggest -g
    ```

2. <span data-ttu-id="161ab-137">Aggiungere lo script shim appropriato al profilo della shell.</span><span class="sxs-lookup"><span data-stu-id="161ab-137">Add the appropriate shim script to your shell profile.</span></span> <span data-ttu-id="161ab-138">Potrebbe essere necessario creare un file del profilo della shell.</span><span class="sxs-lookup"><span data-stu-id="161ab-138">You may have to create a shell profile file.</span></span> <span data-ttu-id="161ab-139">Lo script shim inoltra le richieste di completamento della shell allo strumento `dotnet-suggest` che delega all'app basata su `System.CommandLine` appropriata.</span><span class="sxs-lookup"><span data-stu-id="161ab-139">The shim script will forward completion requests from your shell to the `dotnet-suggest` tool, which delegates to the appropriate `System.CommandLine`-based app.</span></span>

    - <span data-ttu-id="161ab-140">Per bash, aggiungere il contenuto di [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) a `~/.bash_profile`.</span><span class="sxs-lookup"><span data-stu-id="161ab-140">For bash, add the contents of [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) to `~/.bash_profile`.</span></span>

    - <span data-ttu-id="161ab-141">Per PowerShell, aggiungere il contenuto di [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) al profilo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="161ab-141">For PowerShell, add the contents of [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) to your PowerShell profile.</span></span> <span data-ttu-id="161ab-142">È possibile individuare il percorso previsto per il profilo PowerShell eseguendo il comando seguente nella console:</span><span class="sxs-lookup"><span data-stu-id="161ab-142">You can find the expected path to your PowerShell profile by running the following command in your console:</span></span>

    ```console
    echo $profile
    ```

<span data-ttu-id="161ab-143">(Per le altre shell, [ricercare](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) o aprire un [problema](https://github.com/dotnet/System.CommandLine/issues)).</span><span class="sxs-lookup"><span data-stu-id="161ab-143">(For other shells, [look for](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) or open an [issue](https://github.com/dotnet/System.CommandLine/issues).)</span></span>

## <a name="installation-directory"></a><span data-ttu-id="161ab-144">Directory di installazione</span><span class="sxs-lookup"><span data-stu-id="161ab-144">Installation directory</span></span>

<span data-ttu-id="161ab-145">L'interfaccia della riga di comando di ML.NET può essere installata nella directory predefinita o in un percorso specifico.</span><span class="sxs-lookup"><span data-stu-id="161ab-145">The ML.NET CLI can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="161ab-146">Le directory predefinite sono:</span><span class="sxs-lookup"><span data-stu-id="161ab-146">The default directories are:</span></span>

| <span data-ttu-id="161ab-147">OS</span><span class="sxs-lookup"><span data-stu-id="161ab-147">OS</span></span>          | <span data-ttu-id="161ab-148">Path</span><span class="sxs-lookup"><span data-stu-id="161ab-148">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="161ab-149">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="161ab-149">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="161ab-150">Windows</span><span class="sxs-lookup"><span data-stu-id="161ab-150">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="161ab-151">Questi percorsi vengono aggiunti al percorso dell'utente alla prima esecuzione dell'SDK in modo che gli strumenti globali installati possano essere chiamati direttamente.</span><span class="sxs-lookup"><span data-stu-id="161ab-151">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="161ab-152">Nota: gli strumenti globali sono specifici dell'utente e non globali del computer.</span><span class="sxs-lookup"><span data-stu-id="161ab-152">Note: the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="161ab-153">Per questa ragione non è possibile installare uno strumento globale disponibile per tutti gli utenti del computer.</span><span class="sxs-lookup"><span data-stu-id="161ab-153">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="161ab-154">Lo strumento è disponibile solo per i singoli profili utente in cui è stato installato.</span><span class="sxs-lookup"><span data-stu-id="161ab-154">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="161ab-155">Gli strumenti globali possono anche essere installati in una directory specifica.</span><span class="sxs-lookup"><span data-stu-id="161ab-155">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="161ab-156">Quando vengono installati in una directory specifica, l'utente deve verificare che il comando sia disponibile includendo la directory nel percorso, chiamando il comando con la directory specificata chiamando lo strumento dall'interno della directory specificata.</span><span class="sxs-lookup"><span data-stu-id="161ab-156">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="161ab-157">In questo caso l'interfaccia della riga di comando di .NET Core non aggiunge automaticamente il percorso alla variabile di ambiente PATH.</span><span class="sxs-lookup"><span data-stu-id="161ab-157">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="161ab-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="161ab-158">See also</span></span>

- [<span data-ttu-id="161ab-159">Panoramica dell'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="161ab-159">ML.NET CLI overview</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="161ab-160">Esercitazione: analizzare i sentimenti con l'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="161ab-160">Tutorial: Analyze sentiment with the ML.NET CLI</span></span>](../tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="161ab-161">Guida di riferimento per i comandi di training automatico dell'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="161ab-161">ML.NET CLI auto-train command reference guide</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="161ab-162">Telemetria nell'interfaccia della riga di comando ML.NET</span><span class="sxs-lookup"><span data-stu-id="161ab-162">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
