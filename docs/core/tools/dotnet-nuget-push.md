---
title: Comando dotnet nuget push
description: Il comando dotnet nuget push effettua il push di un pacchetto nel server e lo pubblica.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: 8b0437d7f4ada2b56af50e30717d131668c21f7e
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728348"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="aa32c-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="aa32c-103">dotnet nuget push</span></span>

<span data-ttu-id="aa32c-104">**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="aa32c-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="aa32c-105">Nome</span><span class="sxs-lookup"><span data-stu-id="aa32c-105">Name</span></span>

<span data-ttu-id="aa32c-106">`dotnet nuget push`: effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="aa32c-106">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="aa32c-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="aa32c-107">Synopsis</span></span>

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output]
    [--interactive] [-k|--api-key <API_KEY>] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source <SOURCE>] [--skip-duplicate]
    [-sk|--symbol-api-key <API_KEY>] [-ss|--symbol-source <SOURCE>]
    [-t|--timeout <TIMEOUT>]

dotnet nuget push -h|--help
```

## <a name="description"></a><span data-ttu-id="aa32c-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa32c-108">Description</span></span>

<span data-ttu-id="aa32c-109">Il comando `dotnet nuget push` effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="aa32c-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="aa32c-110">Il comando di push usa dettagli del server e delle credenziali presenti nel file di configurazione NuGet o nella catena di file di configurazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="aa32c-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="aa32c-111">Per altre informazioni sui file di configurazione, vedere [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configurazione del comportamento di NuGet).</span><span class="sxs-lookup"><span data-stu-id="aa32c-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="aa32c-112">La configurazione predefinita di NuGet si ottiene caricando *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS) e quindi caricando qualsiasi file *nuget.config* o *.nuget\nuget.config* dalla directory radice dell'unità nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="aa32c-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

<span data-ttu-id="aa32c-113">Il comando effettua il push di un pacchetto esistente.</span><span class="sxs-lookup"><span data-stu-id="aa32c-113">The command pushes an existing package.</span></span> <span data-ttu-id="aa32c-114">Non crea un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="aa32c-114">It doesn't create a package.</span></span> <span data-ttu-id="aa32c-115">Per creare un pacchetto, usare [`dotnet pack`](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="aa32c-115">To create a package, use [`dotnet pack`](dotnet-pack.md).</span></span>

## <a name="arguments"></a><span data-ttu-id="aa32c-116">Argomenti</span><span class="sxs-lookup"><span data-stu-id="aa32c-116">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="aa32c-117">Specifica il percorso del file del pacchetto di cui eseguire il push.</span><span class="sxs-lookup"><span data-stu-id="aa32c-117">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="aa32c-118">Opzioni</span><span class="sxs-lookup"><span data-stu-id="aa32c-118">Options</span></span>

- **`-d|--disable-buffering`**

  <span data-ttu-id="aa32c-119">Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="aa32c-119">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

- **`--force-english-output`**

  <span data-ttu-id="aa32c-120">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="aa32c-120">Forces the application to run using an invariant, English-based culture.</span></span>

- **`-h|--help`**

  <span data-ttu-id="aa32c-121">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="aa32c-121">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="aa32c-122">Consente al comando di bloccare operazioni quali l'autenticazione e richiede un intervento manuale.</span><span class="sxs-lookup"><span data-stu-id="aa32c-122">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="aa32c-123">Opzione disponibile a partire da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="aa32c-123">Option available since .NET Core 2.2 SDK.</span></span>

- **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="aa32c-124">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="aa32c-124">The API key for the server.</span></span>

- **`-n|--no-symbols`**

  <span data-ttu-id="aa32c-125">Non effettua il push dei simboli (anche se presenti).</span><span class="sxs-lookup"><span data-stu-id="aa32c-125">Doesn't push symbols (even if present).</span></span>

- **`--no-service-endpoint`**

  <span data-ttu-id="aa32c-126">Non aggiunge "api/v2/package" all'URL di origine.</span><span class="sxs-lookup"><span data-stu-id="aa32c-126">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="aa32c-127">Opzione disponibile a partire da .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="aa32c-127">Option available since .NET Core 2.1 SDK.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="aa32c-128">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="aa32c-128">Specifies the server URL.</span></span> <span data-ttu-id="aa32c-129">Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="aa32c-129">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

- **`--skip-duplicate`**

  <span data-ttu-id="aa32c-130">Quando si esegue il push di più pacchetti in un server HTTP (S), tratta qualsiasi risposta di conflitto 409 come un avviso, in modo che il push possa continuare.</span><span class="sxs-lookup"><span data-stu-id="aa32c-130">When pushing multiple packages to an HTTP(S) server, treats any 409 Conflict response as a warning so that the push can continue.</span></span> <span data-ttu-id="aa32c-131">Disponibile a partire da .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="aa32c-131">Available since .NET Core 3.1 SDK.</span></span>

- **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="aa32c-132">Chiave API per il server di simboli.</span><span class="sxs-lookup"><span data-stu-id="aa32c-132">The API key for the symbol server.</span></span>

- **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="aa32c-133">Specifica l'URL del server di simboli.</span><span class="sxs-lookup"><span data-stu-id="aa32c-133">Specifies the symbol server URL.</span></span>

- **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="aa32c-134">Specifica il timeout (in secondi) per il push a un server.</span><span class="sxs-lookup"><span data-stu-id="aa32c-134">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="aa32c-135">Il valore predefinito è 300 secondi (5 minuti).</span><span class="sxs-lookup"><span data-stu-id="aa32c-135">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="aa32c-136">Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="aa32c-136">Specifying 0 (zero seconds) applies the default value.</span></span>

## <a name="examples"></a><span data-ttu-id="aa32c-137">Esempi</span><span class="sxs-lookup"><span data-stu-id="aa32c-137">Examples</span></span>

- <span data-ttu-id="aa32c-138">Eseguire il push di *foo. nupkg* nell'origine push predefinita, specificando una chiave API:</span><span class="sxs-lookup"><span data-stu-id="aa32c-138">Push *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

- <span data-ttu-id="aa32c-139">Eseguire il push di *foo. nupkg* nel server NuGet ufficiale, specificando una chiave API:</span><span class="sxs-lookup"><span data-stu-id="aa32c-139">Push *foo.nupkg* to the official NuGet server, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://api.nuget.org/v3/index.json
  ```
  
  * <span data-ttu-id="aa32c-140">Esegue il push di *foo.nupkg* all'origine push personalizzata `https://customsource`, specificando una chiave API:</span><span class="sxs-lookup"><span data-stu-id="aa32c-140">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

- <span data-ttu-id="aa32c-141">Eseguire il push di *foo. nupkg* all'origine push predefinita:</span><span class="sxs-lookup"><span data-stu-id="aa32c-141">Push *foo.nupkg* to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

- <span data-ttu-id="aa32c-142">Eseguire il push di *foo. symbols. nupkg* all'origine simboli predefinita:</span><span class="sxs-lookup"><span data-stu-id="aa32c-142">Push *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

- <span data-ttu-id="aa32c-143">Eseguire il push di *foo. nupkg* all'origine push predefinita, specificando un timeout di 360 secondi:</span><span class="sxs-lookup"><span data-stu-id="aa32c-143">Push *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

- <span data-ttu-id="aa32c-144">Eseguire il push di tutti i file con *estensione nupkg* nella directory corrente all'origine push predefinita:</span><span class="sxs-lookup"><span data-stu-id="aa32c-144">Push all *.nupkg* files in the current directory to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg
  ```

  > [!NOTE]
  > <span data-ttu-id="aa32c-145">Il mancato funzionamento di questo comando può dipendere da un bug che era presente nelle versioni precedenti del SDK (.NET Core 2.1 SDK e versioni precedenti).</span><span class="sxs-lookup"><span data-stu-id="aa32c-145">If this command doesn't work, it might be due to a bug that existed in older versions of the SDK (.NET Core 2.1 SDK and earlier versions).</span></span>
  > <span data-ttu-id="aa32c-146">Per risolvere questo problema, aggiornare la versione del SDK oppure eseguire il comando seguente: `dotnet nuget push **/*.nupkg`</span><span class="sxs-lookup"><span data-stu-id="aa32c-146">To fix this, upgrade your SDK version or run the following command instead: `dotnet nuget push **/*.nupkg`</span></span>

- <span data-ttu-id="aa32c-147">Eseguire il push di tutti i file con *estensione nupkg* anche se una risposta di conflitto 409 viene restituita da un server http (S):</span><span class="sxs-lookup"><span data-stu-id="aa32c-147">Push all *.nupkg* files even if a 409 Conflict response is returned by an HTTP(S) server:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg --skip-duplicate
  ```

- <span data-ttu-id="aa32c-148">Eseguire il push di tutti i file con *estensione nupkg* nella directory corrente in una directory di feed locale:</span><span class="sxs-lookup"><span data-stu-id="aa32c-148">Push all *.nupkg* files in the current directory to a local feed directory:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg -s c:\mydir
  ```

  <span data-ttu-id="aa32c-149">Questo comando non archivia i pacchetti in una struttura di cartelle gerarchica, consigliata per ottimizzare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="aa32c-149">This command doesn't store packages in a hierarchical folder structure, which is recommended to optimize performance.</span></span> <span data-ttu-id="aa32c-150">Per ulteriori informazioni, vedere [feed locali](//nuget/hosting-packages/local-feeds).</span><span class="sxs-lookup"><span data-stu-id="aa32c-150">For more information, see [Local feeds](//nuget/hosting-packages/local-feeds).</span></span>
  