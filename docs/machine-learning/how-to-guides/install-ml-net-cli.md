---
title: Come installare lo strumento dell'interfaccia della riga di comando (CLI) di ML.NET
description: Panoramica e installazione dello strumento dell'interfaccia della riga di comando (CLI) di ML.NET.
ms.date: 04/16/2019
ms.custom: ''
ms.openlocfilehash: baced9bbcc72153458d42d4b6d8206921bf187b8
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117997"
---
# <a name="how-to-install-the-mlnet-command-line-interface-cli-tool"></a><span data-ttu-id="d6462-103">Come installare lo strumento dell'interfaccia della riga di comando (CLI) di ML.NET</span><span class="sxs-lookup"><span data-stu-id="d6462-103">How to install the ML.NET Command-Line Interface (CLI) tool</span></span>

<span data-ttu-id="d6462-104">L'interfaccia della riga di comando di ML.NET è uno strumento che può essere eseguito in qualsiasi prompt dei comandi (Windows, Mac o Linux) per generare modelli ML.NET e codice sorgente di buona qualità in base ai training set specificati.</span><span class="sxs-lookup"><span data-stu-id="d6462-104">The ML.NET CLI (command-line interface) is a tool you can run on any command-prompt (Windows, Mac, or Linux) for generating good quality ML.NET models and source code based on training datasets you provide.</span></span>

> [!NOTE]
> <span data-ttu-id="d6462-105">Questo argomento fa riferimento all'interfaccia della riga di comando di ML.NET e al Machine Learning automatico, attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="d6462-105">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="d6462-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d6462-106">Pre-requisites</span></span>

- [<span data-ttu-id="d6462-107">.NET Core 2.2 SDK</span><span class="sxs-lookup"><span data-stu-id="d6462-107">.NET Core 2.2 SDK</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)

- <span data-ttu-id="d6462-108">(Facoltativo) [Visual Studio 2017 o 2019](https://visualstudio.microsoft.com/vs/)</span><span class="sxs-lookup"><span data-stu-id="d6462-108">(Optional) [Visual Studio 2017 or 2019](https://visualstudio.microsoft.com/vs/)</span></span>

<span data-ttu-id="d6462-109">È possibile eseguire i progetti in codice C# generati con F5 in Visual Studio o con `dotnet run` (interfaccia della riga di comando di .NET Core).</span><span class="sxs-lookup"><span data-stu-id="d6462-109">You can either run the generated C# code projects with Visual Studio F5 or with `dotnet run` (.NET Core CLI).</span></span>

<span data-ttu-id="d6462-110">Nota: Se dopo l'installazione di [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) il comando `dotnet tool` non funziona, disconnettersi da Windows ed eseguire di nuovo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d6462-110">Note: If after installing [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) the `dotnet tool` command is not working, sign out from Windows and sign in again.</span></span>

## <a name="install"></a><span data-ttu-id="d6462-111">Installazione di</span><span class="sxs-lookup"><span data-stu-id="d6462-111">Install</span></span>

<span data-ttu-id="d6462-112">L'interfaccia della riga di comando di ML.NET viene installata come gli altri strumenti globali dotnet.</span><span class="sxs-lookup"><span data-stu-id="d6462-112">The ML.NET CLI is installed like any other dotnet Global Tool.</span></span> <span data-ttu-id="d6462-113">Usare il comando dell'interfaccia della riga di comando di .NET Core `dotnet tool install`.</span><span class="sxs-lookup"><span data-stu-id="d6462-113">You use the `dotnet tool install` .NET Core CLI command.</span></span> 

<span data-ttu-id="d6462-114">L'esempio seguente illustra come installare l'interfaccia della riga di comando di ML.NET nel percorso del feed NuGet predefinito:</span><span class="sxs-lookup"><span data-stu-id="d6462-114">The following example shows how to install the ML.NET CLI in the default NuGet feed location:</span></span>

```dotnetcli
dotnet tool install -g mlnet
```

<span data-ttu-id="d6462-115">Se lo strumento non può essere installato (ovvero, se non è disponibile nel feed NuGet predefinito), vengono visualizzati i messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="d6462-115">If the tool can't be installed (that is, if it is not available at the default NuGet feed), error messages are displayed.</span></span> <span data-ttu-id="d6462-116">Verificare che i feed previsti vengano controllati.</span><span class="sxs-lookup"><span data-stu-id="d6462-116">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="d6462-117">Se l'installazione ha esito positivo, viene visualizzato un messaggio che mostra il comando usato per chiamare lo strumento e la versione installata, simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d6462-117">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```console
You can invoke the tool using the following command: mlnet
Tool 'mlnet' (version 'X.X.X') was successfully installed.
```

<span data-ttu-id="d6462-118">È possibile verificare che l'installazione sia avvenuta correttamente digitando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d6462-118">You can confirm the installation was successful by typing the following command:</span></span>

```console
mlnet
```

<span data-ttu-id="d6462-119">Verranno visualizzate le informazioni della Guida per i comandi disponibili per lo strumento mlnet, ad esempio per il comando 'auto-train'.</span><span class="sxs-lookup"><span data-stu-id="d6462-119">You should see the help for available commands for the mlnet tool such as the 'auto-train' command.</span></span>

## <a name="install-a-specific-release-version"></a><span data-ttu-id="d6462-120">Installare una versione specifica</span><span class="sxs-lookup"><span data-stu-id="d6462-120">Install a specific release version</span></span>

<span data-ttu-id="d6462-121">Se si sta tentando di installare una versione non definitiva o una versione specifica dello strumento, è possibile specificare il [framework](../../standard/frameworks.md) usando il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="d6462-121">If you're trying to install a pre-release version or a specific version of the tool, you can specify the [framework](../../standard/frameworks.md) using the following format:</span></span>

```dotnetcli
dotnet tool install -g mlnet --framework <FRAMEWORK>
```

<span data-ttu-id="d6462-122">È anche possibile verificare se il pacchetto è installato correttamente digitando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d6462-122">You can also check if the package is properly installed by typing the following command:</span></span>

```dotnetcli
dotnet tool list -g
```

## <a name="uninstall-the-cli-package"></a><span data-ttu-id="d6462-123">Disinstallare il pacchetto dell'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="d6462-123">Uninstall the CLI package</span></span>

<span data-ttu-id="d6462-124">Digitare il comando seguente per disinstallare il pacchetto dal computer locale:</span><span class="sxs-lookup"><span data-stu-id="d6462-124">Type the following command to uninstall the package from your local machine:</span></span>

```dotnetcli
dotnet tool uninstall mlnet -g
```

## <a name="update-the-cli-package"></a><span data-ttu-id="d6462-125">Aggiornare il pacchetto dell'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="d6462-125">Update the CLI package</span></span>

<span data-ttu-id="d6462-126">Digitare il comando seguente per aggiornare il pacchetto del computer locale:</span><span class="sxs-lookup"><span data-stu-id="d6462-126">Type the following command to update the package from your local machine:</span></span>

```dotnetcli
dotnet tool update -g mlnet
```

## <a name="set-up-cli-suggestions-tab-based-auto-completion"></a><span data-ttu-id="d6462-127">Configurare i suggerimenti dell'interfaccia della riga di comando (completamento automatico con il tasto TAB)</span><span class="sxs-lookup"><span data-stu-id="d6462-127">Set up CLI suggestions (tab-based auto-completion)</span></span>

<span data-ttu-id="d6462-128">Poiché è basata su `System.CommandLine`, l'interfaccia della riga di comando di ML.NET include un supporto predefinito per il completamento con il tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="d6462-128">Since the ML.NET CLI is based on `System.CommandLine`, it has built-in support for tab completion.</span></span>

<span data-ttu-id="d6462-129">L'animazione seguente mostra un esempio del funzionamento del completamento automatico con il tasto TAB:</span><span class="sxs-lookup"><span data-stu-id="d6462-129">An example of how tab auto completion works is shown in the following animation:</span></span>

![immagine](./media/cli-tab-completion.gif)

<span data-ttu-id="d6462-131">Il completamento automatico con il tasto TAB (suggerimenti di parametri) può essere usato in *Windows PowerShell* e *bash macOS/Linux* ma non in *Windows CMD*.</span><span class="sxs-lookup"><span data-stu-id="d6462-131">'Tab-based auto-completion' (parameter suggestions) works on *Windows PowerShell* and *macOS/Linux bash* but it won't work on *Windows CMD*.</span></span>

<span data-ttu-id="d6462-132">Per abilitarlo nella versione di anteprima corrente è necessario che l'utente finale esegua le operazioni descritte di seguito per ogni shell.</span><span class="sxs-lookup"><span data-stu-id="d6462-132">To enable it, in the current preview version, the end user has to take a few steps once per shell, outlined below.</span></span> <span data-ttu-id="d6462-133">Al termine, il completamento potrà essere usato per tutte le app scritte con `System.CommandLine`, ad esempio l'interfaccia della riga di comando di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="d6462-133">Once this is done, completions will work for all apps written using `System.CommandLine` such as the ML.NET CLI.</span></span>

<span data-ttu-id="d6462-134">Nel computer in cui si vuole abilitare il completamento, è necessario eseguire due operazioni.</span><span class="sxs-lookup"><span data-stu-id="d6462-134">On the machine where you'd like to enable completion, you'll need to do two things.</span></span>

1. <span data-ttu-id="d6462-135">Installare lo strumento globale `dotnet-suggest` eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d6462-135">Install the `dotnet-suggest` global tool by running the following command:</span></span>

    ```dotnetcli
    dotnet tool install dotnet-suggest -g
    ```

2. <span data-ttu-id="d6462-136">Aggiungere lo script shim appropriato al profilo della shell.</span><span class="sxs-lookup"><span data-stu-id="d6462-136">Add the appropriate shim script to your shell profile.</span></span> <span data-ttu-id="d6462-137">Potrebbe essere necessario creare un file del profilo della shell.</span><span class="sxs-lookup"><span data-stu-id="d6462-137">You may have to create a shell profile file.</span></span> <span data-ttu-id="d6462-138">Lo script shim inoltra le richieste di completamento della shell allo strumento `dotnet-suggest` che delega all'app basata su `System.CommandLine` appropriata.</span><span class="sxs-lookup"><span data-stu-id="d6462-138">The shim script will forward completion requests from your shell to the `dotnet-suggest` tool, which delegates to the appropriate `System.CommandLine`-based app.</span></span>

    - <span data-ttu-id="d6462-139">Per bash, aggiungere il contenuto di [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) a `~/.bash_profile`.</span><span class="sxs-lookup"><span data-stu-id="d6462-139">For bash, add the contents of [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) to `~/.bash_profile`.</span></span>

    - <span data-ttu-id="d6462-140">Per PowerShell, aggiungere il contenuto di [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) al profilo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6462-140">For PowerShell, add the contents of [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) to your PowerShell profile.</span></span> <span data-ttu-id="d6462-141">È possibile individuare il percorso previsto per il profilo PowerShell eseguendo il comando seguente nella console:</span><span class="sxs-lookup"><span data-stu-id="d6462-141">You can find the expected path to your PowerShell profile by running the following command in your console:</span></span>

    ```console
    echo $profile
    ``` 

<span data-ttu-id="d6462-142">(Per le altre shell, [ricercare](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) o aprire un [problema](https://github.com/dotnet/System.CommandLine/issues)).</span><span class="sxs-lookup"><span data-stu-id="d6462-142">(For other shells, [look for](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) or open an [issue](https://github.com/dotnet/System.CommandLine/issues).)</span></span>

## <a name="installation-directory"></a><span data-ttu-id="d6462-143">Directory di installazione</span><span class="sxs-lookup"><span data-stu-id="d6462-143">Installation directory</span></span>

<span data-ttu-id="d6462-144">L'interfaccia della riga di comando di ML.NET può essere installata nella directory predefinita o in un percorso specifico.</span><span class="sxs-lookup"><span data-stu-id="d6462-144">The ML.NET CLI can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="d6462-145">Le directory predefinite sono:</span><span class="sxs-lookup"><span data-stu-id="d6462-145">The default directories are:</span></span>

| <span data-ttu-id="d6462-146">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="d6462-146">OS</span></span>          | <span data-ttu-id="d6462-147">Path</span><span class="sxs-lookup"><span data-stu-id="d6462-147">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="d6462-148">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="d6462-148">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="d6462-149">WINDOWS</span><span class="sxs-lookup"><span data-stu-id="d6462-149">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="d6462-150">Questi percorsi vengono aggiunti al percorso dell'utente alla prima esecuzione dell'SDK in modo che gli strumenti globali installati possano essere chiamati direttamente.</span><span class="sxs-lookup"><span data-stu-id="d6462-150">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="d6462-151">Nota: gli strumenti globali sono specifici dell'utente e non globali del computer.</span><span class="sxs-lookup"><span data-stu-id="d6462-151">Note: the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="d6462-152">Per questa ragione non è possibile installare uno strumento globale disponibile per tutti gli utenti del computer.</span><span class="sxs-lookup"><span data-stu-id="d6462-152">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="d6462-153">Lo strumento è disponibile solo per i singoli profili utente in cui è stato installato.</span><span class="sxs-lookup"><span data-stu-id="d6462-153">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="d6462-154">Gli strumenti globali possono anche essere installati in una directory specifica.</span><span class="sxs-lookup"><span data-stu-id="d6462-154">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="d6462-155">Quando vengono installati in una directory specifica, l'utente deve verificare che il comando sia disponibile includendo la directory nel percorso, chiamando il comando con la directory specificata chiamando lo strumento dall'interno della directory specificata.</span><span class="sxs-lookup"><span data-stu-id="d6462-155">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="d6462-156">In questo caso l'interfaccia della riga di comando di .NET Core non aggiunge automaticamente il percorso alla variabile di ambiente PATH.</span><span class="sxs-lookup"><span data-stu-id="d6462-156">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6462-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6462-157">See also</span></span>

- [<span data-ttu-id="d6462-158">Esercitazione dell'introduzione allo strumento dell'interfaccia della riga di comando di ML.NET CLI</span><span class="sxs-lookup"><span data-stu-id="d6462-158">Tutorial on 'Getting Started with ML.NET CLI tool'</span></span>](../tutorials/mlnet-cli.md)
- [<span data-ttu-id="d6462-159">Come eseguire automaticamente il training dei modelli con lo strumento dell'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="d6462-159">How to automatically train models with the ML.NET CLI tool</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="d6462-160">Guida di riferimento per i comandi di training automatico dell'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="d6462-160">ML.NET CLI auto-train command reference guide</span></span>](../reference/ml-net-cli-reference.md) 
- [<span data-ttu-id="d6462-161">Telemetria nell'interfaccia della riga di comando di ML.NET</span><span class="sxs-lookup"><span data-stu-id="d6462-161">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
