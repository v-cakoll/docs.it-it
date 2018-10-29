---
title: Comando dotnet nuget push - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet nuget push effettua il push di un pacchetto nel server e lo pubblica.
author: karann-msft
ms.author: mairaw
ms.date: 09/04/2018
ms.openlocfilehash: b9c0fad886cd1234325c58bf61b1a010bce421d9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2018
ms.locfileid: "50200026"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="04a84-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="04a84-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="04a84-104">nome</span><span class="sxs-lookup"><span data-stu-id="04a84-104">Name</span></span>

<span data-ttu-id="04a84-105">`dotnet nuget push`: effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="04a84-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="04a84-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="04a84-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="04a84-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="04a84-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="04a84-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="04a84-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="04a84-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="04a84-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="04a84-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04a84-110">Description</span></span>

<span data-ttu-id="04a84-111">Il comando `dotnet nuget push` effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="04a84-111">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="04a84-112">Il comando di push usa dettagli del server e delle credenziali presenti nel file di configurazione NuGet o nella catena di file di configurazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="04a84-112">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="04a84-113">Per altre informazioni sui file di configurazione, vedere [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configurazione del comportamento di NuGet).</span><span class="sxs-lookup"><span data-stu-id="04a84-113">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="04a84-114">La configurazione predefinita di NuGet si ottiene caricando *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS) e quindi caricando qualsiasi file *nuget.config* o *.nuget\nuget.config* dalla directory radice dell'unità nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="04a84-114">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="04a84-115">Argomenti</span><span class="sxs-lookup"><span data-stu-id="04a84-115">Arguments</span></span>

`ROOT`

<span data-ttu-id="04a84-116">Specifica il percorso del file del pacchetto di cui eseguire il push.</span><span class="sxs-lookup"><span data-stu-id="04a84-116">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="04a84-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="04a84-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="04a84-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="04a84-118">.NET Core 2.1</span></span>](#tab/netcore21)

`-d|--disable-buffering`

<span data-ttu-id="04a84-119">Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="04a84-119">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="04a84-120">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="04a84-120">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="04a84-121">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="04a84-121">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="04a84-122">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="04a84-122">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="04a84-123">Non effettua il push dei simboli (anche se presenti).</span><span class="sxs-lookup"><span data-stu-id="04a84-123">Doesn't push symbols (even if present).</span></span>

`--no-service-endpoint`

<span data-ttu-id="04a84-124">Non aggiunge "api/v2/package" all'URL di origine.</span><span class="sxs-lookup"><span data-stu-id="04a84-124">Doesn't append "api/v2/package" to the source URL.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="04a84-125">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="04a84-125">Specifies the server URL.</span></span> <span data-ttu-id="04a84-126">Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="04a84-126">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="04a84-127">Chiave API per il server di simboli.</span><span class="sxs-lookup"><span data-stu-id="04a84-127">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="04a84-128">Specifica l'URL del server di simboli.</span><span class="sxs-lookup"><span data-stu-id="04a84-128">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="04a84-129">Specifica il timeout (in secondi) per il push a un server.</span><span class="sxs-lookup"><span data-stu-id="04a84-129">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="04a84-130">Il valore predefinito è 300 secondi (5 minuti).</span><span class="sxs-lookup"><span data-stu-id="04a84-130">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="04a84-131">Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="04a84-131">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="04a84-132">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="04a84-132">.NET Core 2.0</span></span>](#tab/netcore20)

`-d|--disable-buffering`

<span data-ttu-id="04a84-133">Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="04a84-133">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="04a84-134">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="04a84-134">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="04a84-135">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="04a84-135">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="04a84-136">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="04a84-136">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="04a84-137">Non effettua il push dei simboli (anche se presenti).</span><span class="sxs-lookup"><span data-stu-id="04a84-137">Doesn't push symbols (even if present).</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="04a84-138">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="04a84-138">Specifies the server URL.</span></span> <span data-ttu-id="04a84-139">Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="04a84-139">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="04a84-140">Chiave API per il server di simboli.</span><span class="sxs-lookup"><span data-stu-id="04a84-140">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="04a84-141">Specifica l'URL del server di simboli.</span><span class="sxs-lookup"><span data-stu-id="04a84-141">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="04a84-142">Specifica il timeout (in secondi) per il push a un server.</span><span class="sxs-lookup"><span data-stu-id="04a84-142">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="04a84-143">Il valore predefinito è 300 secondi (5 minuti).</span><span class="sxs-lookup"><span data-stu-id="04a84-143">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="04a84-144">Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="04a84-144">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="04a84-145">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="04a84-145">.NET Core 1.x</span></span>](#tab/netcore1x)

`-d|--disable-buffering`

<span data-ttu-id="04a84-146">Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="04a84-146">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="04a84-147">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="04a84-147">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="04a84-148">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="04a84-148">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="04a84-149">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="04a84-149">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="04a84-150">Non effettua il push dei simboli (anche se presenti).</span><span class="sxs-lookup"><span data-stu-id="04a84-150">Doesn't push symbols (even if present).</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="04a84-151">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="04a84-151">Specifies the server URL.</span></span> <span data-ttu-id="04a84-152">Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="04a84-152">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="04a84-153">Chiave API per il server di simboli.</span><span class="sxs-lookup"><span data-stu-id="04a84-153">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="04a84-154">Specifica l'URL del server di simboli.</span><span class="sxs-lookup"><span data-stu-id="04a84-154">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="04a84-155">Specifica il timeout (in secondi) per il push a un server.</span><span class="sxs-lookup"><span data-stu-id="04a84-155">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="04a84-156">Il valore predefinito è 300 secondi (5 minuti).</span><span class="sxs-lookup"><span data-stu-id="04a84-156">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="04a84-157">Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="04a84-157">Specifying 0 (zero seconds) applies the default value.</span></span>

---

## <a name="examples"></a><span data-ttu-id="04a84-158">Esempi</span><span class="sxs-lookup"><span data-stu-id="04a84-158">Examples</span></span>

<span data-ttu-id="04a84-159">Esegue il push di *foo.nupkg* all'origine push predefinita, specificando una chiave API:</span><span class="sxs-lookup"><span data-stu-id="04a84-159">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

<span data-ttu-id="04a84-160">Esegue il push di *foo.nupkg* all'origine push personalizzata `https://customsource`, specificando una chiave API:</span><span class="sxs-lookup"><span data-stu-id="04a84-160">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/`

<span data-ttu-id="04a84-161">Effettua il push di *foo.nupkg* all'origine push predefinita:</span><span class="sxs-lookup"><span data-stu-id="04a84-161">Pushes *foo.nupkg* to the default push source:</span></span>

`dotnet nuget push foo.nupkg`

<span data-ttu-id="04a84-162">Effettua il push di *foo.symbols.nupkg* all'origine simboli predefinita:</span><span class="sxs-lookup"><span data-stu-id="04a84-162">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

`dotnet nuget push foo.symbols.nupkg`

<span data-ttu-id="04a84-163">Esegue il push di *foo.nupkg* all'origine push predefinita, specificando un timeout di 360 secondi:</span><span class="sxs-lookup"><span data-stu-id="04a84-163">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

`dotnet nuget push foo.nupkg --timeout 360`

<span data-ttu-id="04a84-164">Effettua il push di tutti i file con estensione *nupkg* presenti nella directory corrente all'origine push predefinita:</span><span class="sxs-lookup"><span data-stu-id="04a84-164">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

`dotnet nuget push *.nupkg`
