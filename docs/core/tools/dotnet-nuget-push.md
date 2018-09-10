---
title: Comando dotnet nuget push - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet nuget push effettua il push di un pacchetto nel server e lo pubblica.
author: karann-msft
ms.author: mairaw
ms.date: 09/04/2018
ms.openlocfilehash: 23d27cef29008955850f9ed9f4a8baed9e7ad982
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44186462"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="38703-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="38703-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="38703-104">nome</span><span class="sxs-lookup"><span data-stu-id="38703-104">Name</span></span>

<span data-ttu-id="38703-105">`dotnet nuget push`: effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="38703-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="38703-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="38703-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="38703-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="38703-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="38703-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="38703-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="38703-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="38703-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="38703-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38703-110">Description</span></span>

<span data-ttu-id="38703-111">Il comando `dotnet nuget push` effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="38703-111">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="38703-112">Il comando di push usa dettagli del server e delle credenziali presenti nel file di configurazione NuGet o nella catena di file di configurazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="38703-112">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="38703-113">Per altre informazioni sui file di configurazione, vedere [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configurazione del comportamento di NuGet).</span><span class="sxs-lookup"><span data-stu-id="38703-113">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="38703-114">La configurazione predefinita di NuGet si ottiene caricando *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS) e quindi caricando qualsiasi file *nuget.config* o *.nuget\nuget.config* dalla directory radice dell'unità nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="38703-114">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="38703-115">Argomenti</span><span class="sxs-lookup"><span data-stu-id="38703-115">Arguments</span></span>

`ROOT`

<span data-ttu-id="38703-116">Specifica il percorso del file del pacchetto di cui eseguire il push.</span><span class="sxs-lookup"><span data-stu-id="38703-116">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="38703-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="38703-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="38703-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="38703-118">.NET Core 2.1</span></span>](#tab/netcore21)

`-d|--disable-buffering`

<span data-ttu-id="38703-119">Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="38703-119">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="38703-120">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="38703-120">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="38703-121">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="38703-121">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="38703-122">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="38703-122">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="38703-123">Non effettua il push dei simboli (anche se presenti).</span><span class="sxs-lookup"><span data-stu-id="38703-123">Doesn't push symbols (even if present).</span></span>

`--no-service-endpoint`

<span data-ttu-id="38703-124">Non aggiunge "api/v2/package" all'URL di origine.</span><span class="sxs-lookup"><span data-stu-id="38703-124">Doesn't append "api/v2/package" to the source URL.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="38703-125">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="38703-125">Specifies the server URL.</span></span> <span data-ttu-id="38703-126">Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="38703-126">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="38703-127">Chiave API per il server di simboli.</span><span class="sxs-lookup"><span data-stu-id="38703-127">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="38703-128">Specifica l'URL del server di simboli.</span><span class="sxs-lookup"><span data-stu-id="38703-128">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="38703-129">Specifica il timeout (in secondi) per il push a un server.</span><span class="sxs-lookup"><span data-stu-id="38703-129">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="38703-130">Il valore predefinito è 300 secondi (5 minuti).</span><span class="sxs-lookup"><span data-stu-id="38703-130">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="38703-131">Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="38703-131">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="38703-132">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="38703-132">.NET Core 2.0</span></span>](#tab/netcore20)

`-d|--disable-buffering`

<span data-ttu-id="38703-133">Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="38703-133">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="38703-134">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="38703-134">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="38703-135">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="38703-135">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="38703-136">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="38703-136">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="38703-137">Non effettua il push dei simboli (anche se presenti).</span><span class="sxs-lookup"><span data-stu-id="38703-137">Doesn't push symbols (even if present).</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="38703-138">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="38703-138">Specifies the server URL.</span></span> <span data-ttu-id="38703-139">Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="38703-139">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="38703-140">Chiave API per il server di simboli.</span><span class="sxs-lookup"><span data-stu-id="38703-140">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="38703-141">Specifica l'URL del server di simboli.</span><span class="sxs-lookup"><span data-stu-id="38703-141">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="38703-142">Specifica il timeout (in secondi) per il push a un server.</span><span class="sxs-lookup"><span data-stu-id="38703-142">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="38703-143">Il valore predefinito è 300 secondi (5 minuti).</span><span class="sxs-lookup"><span data-stu-id="38703-143">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="38703-144">Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="38703-144">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="38703-145">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="38703-145">.NET Core 1.x</span></span>](#tab/netcore1x)

`-d|--disable-buffering`

<span data-ttu-id="38703-146">Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="38703-146">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="38703-147">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="38703-147">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="38703-148">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="38703-148">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="38703-149">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="38703-149">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="38703-150">Non effettua il push dei simboli (anche se presenti).</span><span class="sxs-lookup"><span data-stu-id="38703-150">Doesn't push symbols (even if present).</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="38703-151">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="38703-151">Specifies the server URL.</span></span> <span data-ttu-id="38703-152">Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="38703-152">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="38703-153">Chiave API per il server di simboli.</span><span class="sxs-lookup"><span data-stu-id="38703-153">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="38703-154">Specifica l'URL del server di simboli.</span><span class="sxs-lookup"><span data-stu-id="38703-154">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="38703-155">Specifica il timeout (in secondi) per il push a un server.</span><span class="sxs-lookup"><span data-stu-id="38703-155">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="38703-156">Il valore predefinito è 300 secondi (5 minuti).</span><span class="sxs-lookup"><span data-stu-id="38703-156">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="38703-157">Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="38703-157">Specifying 0 (zero seconds) applies the default value.</span></span>

---

## <a name="examples"></a><span data-ttu-id="38703-158">Esempi</span><span class="sxs-lookup"><span data-stu-id="38703-158">Examples</span></span>

<span data-ttu-id="38703-159">Esegue il push di *foo.nupkg* all'origine push predefinita, specificando una chiave API:</span><span class="sxs-lookup"><span data-stu-id="38703-159">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

<span data-ttu-id="38703-160">Esegue il push di *foo.nupkg* all'origine push personalizzata `http://customsource`, specificando una chiave API:</span><span class="sxs-lookup"><span data-stu-id="38703-160">Push *foo.nupkg* to the custom push source `http://customsource`, specifying an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/`

<span data-ttu-id="38703-161">Effettua il push di *foo.nupkg* all'origine push predefinita:</span><span class="sxs-lookup"><span data-stu-id="38703-161">Pushes *foo.nupkg* to the default push source:</span></span>

`dotnet nuget push foo.nupkg`

<span data-ttu-id="38703-162">Effettua il push di *foo.symbols.nupkg* all'origine simboli predefinita:</span><span class="sxs-lookup"><span data-stu-id="38703-162">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

`dotnet nuget push foo.symbols.nupkg`

<span data-ttu-id="38703-163">Esegue il push di *foo.nupkg* all'origine push predefinita, specificando un timeout di 360 secondi:</span><span class="sxs-lookup"><span data-stu-id="38703-163">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

`dotnet nuget push foo.nupkg --timeout 360`

<span data-ttu-id="38703-164">Effettua il push di tutti i file con estensione *nupkg* presenti nella directory corrente all'origine push predefinita:</span><span class="sxs-lookup"><span data-stu-id="38703-164">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

`dotnet nuget push *.nupkg`
