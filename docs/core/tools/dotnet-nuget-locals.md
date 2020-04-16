---
title: Comando dotnet nuget locals
description: Il comando dotnet nuget locals cancella o elenca le risorse NuGet locali, quali cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: 5b421b5058528a93c7be58eef2932937cc9cc12d
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463538"
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="ee4e1-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="ee4e1-103">dotnet nuget locals</span></span>

<span data-ttu-id="ee4e1-104">**Questo articolo si applica a:** ✔️ .NET Core 2.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="ee4e1-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="ee4e1-105">Nome</span><span class="sxs-lookup"><span data-stu-id="ee4e1-105">Name</span></span>

<span data-ttu-id="ee4e1-106">`dotnet nuget locals`: cancella o elenca risorse NuGet locali.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-106">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ee4e1-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="ee4e1-107">Synopsis</span></span>

```dotnetcli
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]

dotnet nuget locals -h|--help
```

## <a name="description"></a><span data-ttu-id="ee4e1-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee4e1-108">Description</span></span>

<span data-ttu-id="ee4e1-109">Il comando `dotnet nuget locals` cancella o elenca risorse NuGet locali presenti nella cache delle richieste HTTP, nella cache temporanea o nella cartella globale dei pacchetti a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-109">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="ee4e1-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ee4e1-110">Arguments</span></span>

- **`CACHE_LOCATION`**

  <span data-ttu-id="ee4e1-111">Il percorso della cache da visualizzare o cancellare.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-111">The cache location to list or clear.</span></span> <span data-ttu-id="ee4e1-112">Il valore può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="ee4e1-112">It accepts one of the following values:</span></span>

  * <span data-ttu-id="ee4e1-113">`all` - Indica che l'operazione specificata viene applicata a tutti i tipi di cache, ovvero alla cache delle richieste HTTP, alla cache globale dei pacchetti e alla cache temporanea.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-113">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
  * <span data-ttu-id="ee4e1-114">`http-cache` - Indica che l'operazione specificata viene applicata soltanto alla cache delle richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-114">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="ee4e1-115">Gli altri percorsi della cache non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-115">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="ee4e1-116">`global-packages` - Indica che l'operazione specificata viene applicata soltanto alla cache dei pacchetti globale.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-116">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="ee4e1-117">Gli altri percorsi della cache non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-117">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="ee4e1-118">`temp` - Indica che l'operazione specificata viene applicata soltanto alla cache temporanea.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-118">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="ee4e1-119">Gli altri percorsi della cache non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-119">The other cache locations aren't affected.</span></span>

## <a name="options"></a><span data-ttu-id="ee4e1-120">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ee4e1-120">Options</span></span>

- **`--force-english-output`**

  <span data-ttu-id="ee4e1-121">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-121">Forces the application to run using an invariant, English-based culture.</span></span>

- **`-h|--help`**

  <span data-ttu-id="ee4e1-122">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-122">Prints out a short help for the command.</span></span>

- **`-c|--clear`**

  <span data-ttu-id="ee4e1-123">L'opzione "clear" consente di eseguire un'operazione di cancellazione sul tipo di cache specificato.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-123">The clear option executes a clear operation on the specified cache type.</span></span> <span data-ttu-id="ee4e1-124">Il contenuto delle directory della cache viene eliminato in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-124">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="ee4e1-125">L'utente o il gruppo che esegue l'operazione deve disporre delle autorizzazioni per i file presenti nelle directory della cache.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-125">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="ee4e1-126">In caso contrario, viene visualizzato un messaggio di errore con l'indicazione delle cartelle e/o dei file che non sono stati cancellati.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-126">If not, an error is displayed indicating the files/folders that weren't cleared.</span></span>

- **`-l|--list`**

  <span data-ttu-id="ee4e1-127">L'opzione "list" viene usata per visualizzare la posizione del tipo di cache specificato.</span><span class="sxs-lookup"><span data-stu-id="ee4e1-127">The list option is used to display the location of the specified cache type.</span></span>

## <a name="examples"></a><span data-ttu-id="ee4e1-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="ee4e1-128">Examples</span></span>

- <span data-ttu-id="ee4e1-129">Visualizza i percorsi di tutte le directory locali della cache, ovvero directory della cache HTTP, directory della cache globale dei pacchetti e directory della cache temporanea:</span><span class="sxs-lookup"><span data-stu-id="ee4e1-129">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```dotnetcli
  dotnet nuget locals all –l
  ```

- <span data-ttu-id="ee4e1-130">Visualizza il percorso della directory locale della cache HTTP:</span><span class="sxs-lookup"><span data-stu-id="ee4e1-130">Displays the path for the local http-cache directory:</span></span>

  ```dotnetcli
  dotnet nuget locals http-cache --list
  ```

- <span data-ttu-id="ee4e1-131">Cancella tutti i file da tutte le directory locali della cache, ovvero directory della cache HTTP, directory della cache globale dei pacchetti e directory della cache temporanea:</span><span class="sxs-lookup"><span data-stu-id="ee4e1-131">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```dotnetcli
  dotnet nuget locals all --clear
  ```

- <span data-ttu-id="ee4e1-132">Cancella tutti i file presenti nella directory locale della cache globale dei pacchetti:</span><span class="sxs-lookup"><span data-stu-id="ee4e1-132">Clears all files in local global-packages cache directory:</span></span>

  ```dotnetcli
  dotnet nuget locals global-packages -c
  ```

- <span data-ttu-id="ee4e1-133">Cancella tutti i file presenti nella directory locale della cache temporanea:</span><span class="sxs-lookup"><span data-stu-id="ee4e1-133">Clears all files in local temporary cache directory:</span></span>

  ```dotnetcli
  dotnet nuget locals temp -c
  ```

## <a name="troubleshooting"></a><span data-ttu-id="ee4e1-134">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="ee4e1-134">Troubleshooting</span></span>

<span data-ttu-id="ee4e1-135">Per informazioni su problemi ed errori comuni relativi all'uso del comando `dotnet nuget locals`, vedere [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache) (Gestione della cache NuGet).</span><span class="sxs-lookup"><span data-stu-id="ee4e1-135">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>
