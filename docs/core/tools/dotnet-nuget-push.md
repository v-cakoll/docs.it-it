---
title: Comando dotnet nuget push
description: Il comando dotnet nuget push effettua il push di un pacchetto nel server e lo pubblica.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 87557f606dead921961349fec4575394e6d359fd
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202552"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="c8fd4-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="c8fd4-103">dotnet nuget push</span></span>

<span data-ttu-id="c8fd4-104">**Questo argomento si applica a: ✓** .NET Core 2.1.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="c8fd4-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="c8fd4-105">nome</span><span class="sxs-lookup"><span data-stu-id="c8fd4-105">Name</span></span>

<span data-ttu-id="c8fd4-106">`dotnet nuget push`: effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-106">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c8fd4-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="c8fd4-107">Synopsis</span></span>

```console
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```

## <a name="description"></a><span data-ttu-id="c8fd4-108">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c8fd4-108">Description</span></span>

<span data-ttu-id="c8fd4-109">Il comando `dotnet nuget push` effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="c8fd4-110">Il comando di push usa dettagli del server e delle credenziali presenti nel file di configurazione NuGet o nella catena di file di configurazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="c8fd4-111">Per altre informazioni sui file di configurazione, vedere [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configurazione del comportamento di NuGet).</span><span class="sxs-lookup"><span data-stu-id="c8fd4-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="c8fd4-112">La configurazione predefinita di NuGet si ottiene caricando *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS) e quindi caricando qualsiasi file *nuget.config* o *.nuget\nuget.config* dalla directory radice dell'unità nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="c8fd4-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c8fd4-113">Arguments</span></span>

* **`ROOT`**

  <span data-ttu-id="c8fd4-114">Specifica il percorso del file del pacchetto di cui eseguire il push.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-114">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="c8fd4-115">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c8fd4-115">Options</span></span>

* **`-d|--disable-buffering`**

  <span data-ttu-id="c8fd4-116">Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-116">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="c8fd4-117">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-117">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

<span data-ttu-id="c8fd4-118">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-118">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="c8fd4-119">Consente al comando di bloccare operazioni quali l'autenticazione e richiede un intervento manuale.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="c8fd4-120">Opzione disponibile a partire da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-120">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="c8fd4-121">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-121">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="c8fd4-122">Non effettua il push dei simboli (anche se presenti).</span><span class="sxs-lookup"><span data-stu-id="c8fd4-122">Doesn't push symbols (even if present).</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="c8fd4-123">Non aggiunge "api/v2/package" all'URL di origine.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-123">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="c8fd4-124">Opzione disponibile a partire da .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-124">Option available since .NET Core 2.1 SDK.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="c8fd4-125">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-125">Specifies the server URL.</span></span> <span data-ttu-id="c8fd4-126">Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-126">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="c8fd4-127">Chiave API per il server di simboli.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-127">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="c8fd4-128">Specifica l'URL del server di simboli.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-128">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="c8fd4-129">Specifica il timeout (in secondi) per il push a un server.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-129">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="c8fd4-130">Il valore predefinito è 300 secondi (5 minuti).</span><span class="sxs-lookup"><span data-stu-id="c8fd4-130">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="c8fd4-131">Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="c8fd4-131">Specifying 0 (zero seconds) applies the default value.</span></span>

## <a name="examples"></a><span data-ttu-id="c8fd4-132">Esempi</span><span class="sxs-lookup"><span data-stu-id="c8fd4-132">Examples</span></span>

* <span data-ttu-id="c8fd4-133">Esegue il push di *foo.nupkg* all'origine push predefinita, specificando una chiave API:</span><span class="sxs-lookup"><span data-stu-id="c8fd4-133">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* <span data-ttu-id="c8fd4-134">Esegue il push di *foo.nupkg* all'origine push personalizzata `https://customsource`, specificando una chiave API:</span><span class="sxs-lookup"><span data-stu-id="c8fd4-134">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* <span data-ttu-id="c8fd4-135">Effettua il push di *foo.nupkg* all'origine push predefinita:</span><span class="sxs-lookup"><span data-stu-id="c8fd4-135">Pushes *foo.nupkg* to the default push source:</span></span>

  ```console
  dotnet nuget push foo.nupkg
  ```

* <span data-ttu-id="c8fd4-136">Effettua il push di *foo.symbols.nupkg* all'origine simboli predefinita:</span><span class="sxs-lookup"><span data-stu-id="c8fd4-136">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```console
  dotnet nuget push foo.symbols.nupkg
  ```

* <span data-ttu-id="c8fd4-137">Esegue il push di *foo.nupkg* all'origine push predefinita, specificando un timeout di 360 secondi:</span><span class="sxs-lookup"><span data-stu-id="c8fd4-137">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```console
  dotnet nuget push foo.nupkg --timeout 360
  ```

* <span data-ttu-id="c8fd4-138">Effettua il push di tutti i file con estensione *nupkg* presenti nella directory corrente all'origine push predefinita:</span><span class="sxs-lookup"><span data-stu-id="c8fd4-138">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

  ```console
  dotnet nuget push *.nupkg
  ```
  
  > [!NOTE]
  > <span data-ttu-id="c8fd4-139">Il mancato funzionamento di questo comando può dipendere da un bug che era presente nelle versioni precedenti del SDK (.NET Core 2.1 SDK e versioni precedenti).</span><span class="sxs-lookup"><span data-stu-id="c8fd4-139">If this command doesn't work, it might be due to a bug that existed in older versions of the SDK (.NET Core 2.1 SDK and earlier versions).</span></span>
  > <span data-ttu-id="c8fd4-140">Per risolvere questo problema, aggiornare la versione del SDK oppure eseguire il comando seguente: `dotnet nuget push **/*.nupkg`</span><span class="sxs-lookup"><span data-stu-id="c8fd4-140">To fix this, upgrade your SDK version or run the following command instead: `dotnet nuget push **/*.nupkg`</span></span>
