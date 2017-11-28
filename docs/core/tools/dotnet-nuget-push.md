---
title: Comando dotnet nuget push - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet nuget push effettua il push di un pacchetto nel server e lo pubblica.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 6721615e4df820ab50ea4f79fbba30daeffe8165
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="c0266-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="c0266-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c0266-104">Nome</span><span class="sxs-lookup"><span data-stu-id="c0266-104">Name</span></span>

<span data-ttu-id="c0266-105">`dotnet nuget push`: effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="c0266-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c0266-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="c0266-106">Synopsis</span></span>

`dotnet nuget push [<ROOT>] [-s|--source] [-ss|--symbol-source] [-t|--timeout] [-k|--api-key] [-sk|--symbol-api-key] [-d|--disable-buffering] [-n|--no-symbols] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="c0266-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0266-107">Description</span></span>

<span data-ttu-id="c0266-108">Il comando `dotnet nuget push` effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="c0266-108">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="c0266-109">Il comando di push usa dettagli del server e delle credenziali presenti nel file di configurazione NuGet o nella catena di file di configurazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="c0266-109">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="c0266-110">Per altre informazioni sui file di configurazione, vedere [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configurazione del comportamento di NuGet).</span><span class="sxs-lookup"><span data-stu-id="c0266-110">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="c0266-111">La configurazione predefinita di NuGet si ottiene caricando *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS) e quindi caricando qualsiasi file *nuget.config* o *.nuget\nuget.config* dalla directory radice dell'unità nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="c0266-111">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="c0266-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c0266-112">Arguments</span></span>

`ROOT`

<span data-ttu-id="c0266-113">Specificare il percorso del pacchetto e la chiave API per effettuare il push del pacchetto al server.</span><span class="sxs-lookup"><span data-stu-id="c0266-113">Specify the path to the package and your API key to push the package to the server.</span></span>

## <a name="options"></a><span data-ttu-id="c0266-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c0266-114">Options</span></span>

`-h|--help`

<span data-ttu-id="c0266-115">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="c0266-115">Prints out a short help for the command.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="c0266-116">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="c0266-116">Specifies the server URL.</span></span> <span data-ttu-id="c0266-117">Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="c0266-117">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`--symbols-source <SOURCE>`

<span data-ttu-id="c0266-118">Specifica l'URL del server di simboli.</span><span class="sxs-lookup"><span data-stu-id="c0266-118">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="c0266-119">Specifica il timeout (in secondi) per il push a un server.</span><span class="sxs-lookup"><span data-stu-id="c0266-119">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="c0266-120">Il valore predefinito è 300 secondi (5 minuti).</span><span class="sxs-lookup"><span data-stu-id="c0266-120">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="c0266-121">Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="c0266-121">Specifying 0 (zero seconds) applies the default value.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="c0266-122">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="c0266-122">The API key for the server.</span></span>

`--symbol-api-key <API_KEY>`

<span data-ttu-id="c0266-123">Chiave API per il server di simboli.</span><span class="sxs-lookup"><span data-stu-id="c0266-123">The API key for the symbol server.</span></span>

`-d|--disable-buffering`

<span data-ttu-id="c0266-124">Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="c0266-124">Disables buffering when pushing to an HTTP(S) server to decrease memory usage.</span></span>

`-n|--no-symbols`

<span data-ttu-id="c0266-125">Non effettua il push dei simboli (anche se presenti).</span><span class="sxs-lookup"><span data-stu-id="c0266-125">Doesn't push symbols (even if present).</span></span>

`--force-english-output`

<span data-ttu-id="c0266-126">Forza la visualizzazione di tutto l'output registrato in inglese.</span><span class="sxs-lookup"><span data-stu-id="c0266-126">Forces all logged output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="c0266-127">Esempi</span><span class="sxs-lookup"><span data-stu-id="c0266-127">Examples</span></span>

<span data-ttu-id="c0266-128">Effettua il push di *foo.nupkg* all'origine push predefinita, specificando la chiave API:</span><span class="sxs-lookup"><span data-stu-id="c0266-128">Pushes *foo.nupkg* to the default push source, providing an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

<span data-ttu-id="c0266-129">Effettua il push di *foo.nupkg* all'origine push personalizzata `http://customsource`, specificando la chiave API:</span><span class="sxs-lookup"><span data-stu-id="c0266-129">Push *foo.nupkg* to the custom push source `http://customsource`, providing an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/`

<span data-ttu-id="c0266-130">Effettua il push di *foo.nupkg* all'origine push predefinita:</span><span class="sxs-lookup"><span data-stu-id="c0266-130">Pushes *foo.nupkg* to the default push source:</span></span>

`dotnet nuget push foo.nupkg`

<span data-ttu-id="c0266-131">Effettua il push di *foo.symbols.nupkg* all'origine simboli predefinita:</span><span class="sxs-lookup"><span data-stu-id="c0266-131">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

`dotnet nuget push foo.symbols.nupkg`

<span data-ttu-id="c0266-132">Effettua il push di *foo.nupkg* all'origine push predefinita, specificando un timeout di 360 secondi:</span><span class="sxs-lookup"><span data-stu-id="c0266-132">Pushes *foo.nupkg* to the default push source, specifying a 360 second timeout:</span></span>

`dotnet nuget push foo.nupkg --timeout 360`

<span data-ttu-id="c0266-133">Effettua il push di tutti i file con estensione *nupkg* presenti nella directory corrente all'origine push predefinita:</span><span class="sxs-lookup"><span data-stu-id="c0266-133">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

`dotnet nuget push *.nupkg`

<span data-ttu-id="c0266-134">Effettua il push di tutti i file con estensione *nupkg* presenti nella directory corrente all'origine push predefinita, specificando un file di configurazione personalizzato *./config/My.Config*:</span><span class="sxs-lookup"><span data-stu-id="c0266-134">Pushes all *.nupkg* files in the current directory to the default push source, specifying a custom config file *./config/My.Config*:</span></span>

`dotnet nuget push *.nupkg --config-file ./config/My.Config`

<span data-ttu-id="c0266-135">Effettua il push di tutti i file con estensione *nupkg* presenti nella directory corrente all'origine push predefinita con il massimo livello di dettaglio:</span><span class="sxs-lookup"><span data-stu-id="c0266-135">Push all *.nupkg* files in the current directory to the default push source with maximum verbosity:</span></span>

`dotnet nuget push *.nupkg --verbosity detailed`
