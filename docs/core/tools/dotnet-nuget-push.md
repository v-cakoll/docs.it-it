---
title: Comando dotnet-nuget-push - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-nuget-push effettua il push di un pacchetto nel server e lo pubblica.
keywords: dotnet-nuget-push, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: karann-msft
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f54d9adf-94f8-41cc-bb52-42f7ca3be6ff
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 83da967d9d7432fcb422b88344ff597d45fc9e85
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-nuget-push"></a><span data-ttu-id="18c0c-104">dotnet-nuget push</span><span class="sxs-lookup"><span data-stu-id="18c0c-104">dotnet-nuget push</span></span>

## <a name="name"></a><span data-ttu-id="18c0c-105">Nome</span><span class="sxs-lookup"><span data-stu-id="18c0c-105">Name</span></span>

<span data-ttu-id="18c0c-106">`dotnet-nuget push`: effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="18c0c-106">`dotnet-nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="18c0c-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="18c0c-107">Synopsis</span></span>

`dotnet nuget push [<ROOT>] [-s|--source] [-ss|--symbol-source] [-t|--timeout] [-k|--api-key] [-sk|--symbol-api-key] [-d|--disable-buffering] [-n|--no-symbols] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="18c0c-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18c0c-108">Description</span></span>

<span data-ttu-id="18c0c-109">Il comando `dotnet nuget push` effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="18c0c-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="18c0c-110">Il comando di push usa dettagli del server e delle credenziali presenti nel file di configurazione NuGet o nella catena di file di configurazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="18c0c-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="18c0c-111">Per altre informazioni sui file di configurazione, vedere [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configurazione del comportamento di NuGet).</span><span class="sxs-lookup"><span data-stu-id="18c0c-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="18c0c-112">La configurazione predefinita di NuGet si ottiene caricando *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS) e quindi caricando qualsiasi file *nuget.config* o *.nuget\nuget.config* dalla directory radice dell'unità nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="18c0c-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="18c0c-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="18c0c-113">Arguments</span></span>

`ROOT`

<span data-ttu-id="18c0c-114">Specificare il percorso del pacchetto e la chiave API per effettuare il push del pacchetto al server.</span><span class="sxs-lookup"><span data-stu-id="18c0c-114">Specify the path to the package and your API key to push the package to the server.</span></span>

## <a name="options"></a><span data-ttu-id="18c0c-115">Opzioni</span><span class="sxs-lookup"><span data-stu-id="18c0c-115">Options</span></span>

`-h|--help`

<span data-ttu-id="18c0c-116">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="18c0c-116">Prints out a short help for the command.</span></span>  

`-s|--source <SOURCE>`

<span data-ttu-id="18c0c-117">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="18c0c-117">Specifies the server URL.</span></span> <span data-ttu-id="18c0c-118">Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="18c0c-118">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`--symbols-source <SOURCE>`

<span data-ttu-id="18c0c-119">Specifica l'URL del server di simboli.</span><span class="sxs-lookup"><span data-stu-id="18c0c-119">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="18c0c-120">Specifica il timeout (in secondi) per il push a un server.</span><span class="sxs-lookup"><span data-stu-id="18c0c-120">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="18c0c-121">Il valore predefinito è 300 secondi (5 minuti).</span><span class="sxs-lookup"><span data-stu-id="18c0c-121">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="18c0c-122">Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="18c0c-122">Specifying 0 (zero seconds) applies the default value.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="18c0c-123">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="18c0c-123">The API key for the server.</span></span>

`--symbol-api-key <API_KEY>`

<span data-ttu-id="18c0c-124">Chiave API per il server di simboli.</span><span class="sxs-lookup"><span data-stu-id="18c0c-124">The API key for the symbol server.</span></span>

`-d|--disable-buffering`

<span data-ttu-id="18c0c-125">Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="18c0c-125">Disables buffering when pushing to an HTTP(S) server to decrease memory usage.</span></span>

`-n|--no-symbols`

<span data-ttu-id="18c0c-126">Non effettua il push dei simboli (anche se presenti).</span><span class="sxs-lookup"><span data-stu-id="18c0c-126">Doesn't push symbols (even if present).</span></span>

`--force-english-output`

<span data-ttu-id="18c0c-127">Forza la visualizzazione di tutto l'output registrato in inglese.</span><span class="sxs-lookup"><span data-stu-id="18c0c-127">Forces all logged output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="18c0c-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="18c0c-128">Examples</span></span>

<span data-ttu-id="18c0c-129">Effettua il push di *foo.nupkg* all'origine push predefinita, specificando la chiave API:</span><span class="sxs-lookup"><span data-stu-id="18c0c-129">Pushes *foo.nupkg* to the default push source, providing an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

<span data-ttu-id="18c0c-130">Effettua il push di *foo.nupkg* all'origine push personalizzata `http://customsource`, specificando la chiave API:</span><span class="sxs-lookup"><span data-stu-id="18c0c-130">Push *foo.nupkg* to the custom push source `http://customsource`, providing an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/` 

<span data-ttu-id="18c0c-131">Effettua il push di *foo.nupkg* all'origine push predefinita:</span><span class="sxs-lookup"><span data-stu-id="18c0c-131">Pushes *foo.nupkg* to the default push source:</span></span>

`dotnet nuget push foo.nupkg` 

<span data-ttu-id="18c0c-132">Effettua il push di *foo.symbols.nupkg* all'origine simboli predefinita:</span><span class="sxs-lookup"><span data-stu-id="18c0c-132">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

`dotnet nuget push foo.symbols.nupkg`

<span data-ttu-id="18c0c-133">Effettua il push di *foo.nupkg* all'origine push predefinita, specificando un timeout di 360 secondi:</span><span class="sxs-lookup"><span data-stu-id="18c0c-133">Pushes *foo.nupkg* to the default push source, specifying a 360 second timeout:</span></span>

`dotnet nuget push foo.nupkg --timeout 360`

<span data-ttu-id="18c0c-134">Effettua il push di tutti i file con estensione *nupkg* presenti nella directory corrente all'origine push predefinita:</span><span class="sxs-lookup"><span data-stu-id="18c0c-134">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

`dotnet nuget push *.nupkg`

<span data-ttu-id="18c0c-135">Effettua il push di tutti i file con estensione *nupkg* presenti nella directory corrente all'origine push predefinita, specificando un file di configurazione personalizzato *./config/My.Config*:</span><span class="sxs-lookup"><span data-stu-id="18c0c-135">Pushes all *.nupkg* files in the current directory to the default push source, specifying a custom config file *./config/My.Config*:</span></span>

`dotnet nuget push *.nupkg --config-file ./config/My.Config`

<span data-ttu-id="18c0c-136">Effettua il push di tutti i file con estensione *nupkg* presenti nella directory corrente all'origine push predefinita con il massimo livello di dettaglio:</span><span class="sxs-lookup"><span data-stu-id="18c0c-136">Push all *.nupkg* files in the current directory to the default push source with maximum verbosity:</span></span>

`dotnet nuget push *.nupkg --verbosity detailed`

