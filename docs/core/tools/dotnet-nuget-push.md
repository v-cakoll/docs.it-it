---
title: Comando dotnet nuget push
description: Il comando dotnet nuget push effettua il push di un pacchetto nel server e lo pubblica.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: 9f38fb29ef5b802a5b7091dd1e9659c653cf04d0
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2019
ms.locfileid: "59610769"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="aa877-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="aa877-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="aa877-104">nome</span><span class="sxs-lookup"><span data-stu-id="aa877-104">Name</span></span>

<span data-ttu-id="aa877-105">`dotnet nuget push`: effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="aa877-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="aa877-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="aa877-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="aa877-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="aa877-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="aa877-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="aa877-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="aa877-109">Description</span><span class="sxs-lookup"><span data-stu-id="aa877-109">Description</span></span>

<span data-ttu-id="aa877-110">Il comando `dotnet nuget push` effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="aa877-110">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="aa877-111">Il comando di push usa dettagli del server e delle credenziali presenti nel file di configurazione NuGet o nella catena di file di configurazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="aa877-111">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="aa877-112">Per altre informazioni sui file di configurazione, vedere [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configurazione del comportamento di NuGet).</span><span class="sxs-lookup"><span data-stu-id="aa877-112">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="aa877-113">La configurazione predefinita di NuGet si ottiene caricando *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS) e quindi caricando qualsiasi file *nuget.config* o *.nuget\nuget.config* dalla directory radice dell'unità nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="aa877-113">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="aa877-114">Argomenti</span><span class="sxs-lookup"><span data-stu-id="aa877-114">Arguments</span></span>

* **`ROOT`**

  <span data-ttu-id="aa877-115">Specifica il percorso del file del pacchetto di cui eseguire il push.</span><span class="sxs-lookup"><span data-stu-id="aa877-115">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="aa877-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="aa877-116">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="aa877-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="aa877-117">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`-d|--disable-buffering`**

  <span data-ttu-id="aa877-118">Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="aa877-118">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="aa877-119">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="aa877-119">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

<span data-ttu-id="aa877-120">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="aa877-120">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="aa877-121">Consente al comando di bloccare operazioni quali l'autenticazione e richiede un intervento manuale.</span><span class="sxs-lookup"><span data-stu-id="aa877-121">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="aa877-122">Opzione disponibile a partire da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="aa877-122">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="aa877-123">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="aa877-123">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="aa877-124">Non effettua il push dei simboli (anche se presenti).</span><span class="sxs-lookup"><span data-stu-id="aa877-124">Doesn't push symbols (even if present).</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="aa877-125">Non aggiunge "api/v2/package" all'URL di origine.</span><span class="sxs-lookup"><span data-stu-id="aa877-125">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="aa877-126">Opzione disponibile a partire da .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="aa877-126">Option available since .NET Core 2.1 SDK.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="aa877-127">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="aa877-127">Specifies the server URL.</span></span> <span data-ttu-id="aa877-128">Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="aa877-128">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="aa877-129">Chiave API per il server di simboli.</span><span class="sxs-lookup"><span data-stu-id="aa877-129">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="aa877-130">Specifica l'URL del server di simboli.</span><span class="sxs-lookup"><span data-stu-id="aa877-130">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="aa877-131">Specifica il timeout (in secondi) per il push a un server.</span><span class="sxs-lookup"><span data-stu-id="aa877-131">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="aa877-132">Il valore predefinito è 300 secondi (5 minuti).</span><span class="sxs-lookup"><span data-stu-id="aa877-132">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="aa877-133">Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="aa877-133">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="aa877-134">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="aa877-134">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`-d|--disable-buffering`**

  <span data-ttu-id="aa877-135">Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="aa877-135">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="aa877-136">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="aa877-136">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="aa877-137">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="aa877-137">Prints out a short help for the command.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="aa877-138">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="aa877-138">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="aa877-139">Non effettua il push dei simboli (anche se presenti).</span><span class="sxs-lookup"><span data-stu-id="aa877-139">Doesn't push symbols (even if present).</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="aa877-140">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="aa877-140">Specifies the server URL.</span></span> <span data-ttu-id="aa877-141">Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="aa877-141">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="aa877-142">Chiave API per il server di simboli.</span><span class="sxs-lookup"><span data-stu-id="aa877-142">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="aa877-143">Specifica l'URL del server di simboli.</span><span class="sxs-lookup"><span data-stu-id="aa877-143">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="aa877-144">Specifica il timeout (in secondi) per il push a un server.</span><span class="sxs-lookup"><span data-stu-id="aa877-144">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="aa877-145">Il valore predefinito è 300 secondi (5 minuti).</span><span class="sxs-lookup"><span data-stu-id="aa877-145">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="aa877-146">Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="aa877-146">Specifying 0 (zero seconds) applies the default value.</span></span>

---

## <a name="examples"></a><span data-ttu-id="aa877-147">Esempi</span><span class="sxs-lookup"><span data-stu-id="aa877-147">Examples</span></span>

* <span data-ttu-id="aa877-148">Esegue il push di *foo.nupkg* all'origine push predefinita, specificando una chiave API:</span><span class="sxs-lookup"><span data-stu-id="aa877-148">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* <span data-ttu-id="aa877-149">Esegue il push di *foo.nupkg* all'origine push personalizzata `https://customsource`, specificando una chiave API:</span><span class="sxs-lookup"><span data-stu-id="aa877-149">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* <span data-ttu-id="aa877-150">Effettua il push di *foo.nupkg* all'origine push predefinita:</span><span class="sxs-lookup"><span data-stu-id="aa877-150">Pushes *foo.nupkg* to the default push source:</span></span>

  ```console
  dotnet nuget push foo.nupkg
  ```

* <span data-ttu-id="aa877-151">Effettua il push di *foo.symbols.nupkg* all'origine simboli predefinita:</span><span class="sxs-lookup"><span data-stu-id="aa877-151">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```console
  dotnet nuget push foo.symbols.nupkg
  ```

* <span data-ttu-id="aa877-152">Esegue il push di *foo.nupkg* all'origine push predefinita, specificando un timeout di 360 secondi:</span><span class="sxs-lookup"><span data-stu-id="aa877-152">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```console
  dotnet nuget push foo.nupkg --timeout 360
  ```

* <span data-ttu-id="aa877-153">Effettua il push di tutti i file con estensione *nupkg* presenti nella directory corrente all'origine push predefinita:</span><span class="sxs-lookup"><span data-stu-id="aa877-153">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

  ```console
  dotnet nuget push *.nupkg
  ```