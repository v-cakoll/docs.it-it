---
title: Comando dotnet nuget locals - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet nuget locals cancella o elenca le risorse NuGet locali, quali cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.
author: karann-msft
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 799acb92d6ab7439e15c23c9f0b7b572c966adda
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696871"
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="985e1-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="985e1-103">dotnet nuget locals</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="985e1-104">nome</span><span class="sxs-lookup"><span data-stu-id="985e1-104">Name</span></span>

<span data-ttu-id="985e1-105">`dotnet nuget locals`: cancella o elenca risorse NuGet locali.</span><span class="sxs-lookup"><span data-stu-id="985e1-105">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="985e1-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="985e1-106">Synopsis</span></span>

```
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a><span data-ttu-id="985e1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="985e1-107">Description</span></span>

<span data-ttu-id="985e1-108">Il comando `dotnet nuget locals` cancella o elenca risorse NuGet locali presenti nella cache delle richieste HTTP, nella cache temporanea o nella cartella globale dei pacchetti a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="985e1-108">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="985e1-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="985e1-109">Arguments</span></span>

`CACHE_LOCATION`

<span data-ttu-id="985e1-110">Il percorso della cache da visualizzare o cancellare.</span><span class="sxs-lookup"><span data-stu-id="985e1-110">The cache location to list or clear.</span></span> <span data-ttu-id="985e1-111">Il valore può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="985e1-111">It accepts one of the following values:</span></span>

* <span data-ttu-id="985e1-112">`all` - Indica che l'operazione specificata viene applicata a tutti i tipi di cache, ovvero alla cache delle richieste HTTP, alla cache globale dei pacchetti e alla cache temporanea.</span><span class="sxs-lookup"><span data-stu-id="985e1-112">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
* <span data-ttu-id="985e1-113">`http-cache` - Indica che l'operazione specificata viene applicata soltanto alla cache delle richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="985e1-113">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="985e1-114">Gli altri percorsi della cache non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="985e1-114">The other cache locations aren't affected.</span></span>
* <span data-ttu-id="985e1-115">`global-packages` - Indica che l'operazione specificata viene applicata soltanto alla cache dei pacchetti globale.</span><span class="sxs-lookup"><span data-stu-id="985e1-115">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="985e1-116">Gli altri percorsi della cache non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="985e1-116">The other cache locations aren't affected.</span></span>
* <span data-ttu-id="985e1-117">`temp` - Indica che l'operazione specificata viene applicata soltanto alla cache temporanea.</span><span class="sxs-lookup"><span data-stu-id="985e1-117">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="985e1-118">Gli altri percorsi della cache non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="985e1-118">The other cache locations aren't affected.</span></span>

## <a name="options"></a><span data-ttu-id="985e1-119">Opzioni</span><span class="sxs-lookup"><span data-stu-id="985e1-119">Options</span></span>

`--force-english-output`

<span data-ttu-id="985e1-120">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="985e1-120">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="985e1-121">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="985e1-121">Prints out a short help for the command.</span></span>

`-c|--clear`

<span data-ttu-id="985e1-122">L'opzione "clear" consente di eseguire un'operazione di cancellazione sul tipo di cache specificato.</span><span class="sxs-lookup"><span data-stu-id="985e1-122">The clear option executes a clear operation on the specified cache type.</span></span> <span data-ttu-id="985e1-123">Il contenuto delle directory della cache viene eliminato in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="985e1-123">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="985e1-124">L'utente o il gruppo che esegue l'operazione deve disporre delle autorizzazioni per i file presenti nelle directory della cache.</span><span class="sxs-lookup"><span data-stu-id="985e1-124">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="985e1-125">In caso contrario, viene visualizzato un messaggio di errore con l'indicazione delle cartelle e/o dei file che non sono stati cancellati.</span><span class="sxs-lookup"><span data-stu-id="985e1-125">If not, an error is displayed indicating the files/folders that weren't cleared.</span></span>

`-l|--list`

<span data-ttu-id="985e1-126">L'opzione "list" viene usata per visualizzare la posizione del tipo di cache specificato.</span><span class="sxs-lookup"><span data-stu-id="985e1-126">The list option is used to display the location of the specified cache type.</span></span>

## <a name="examples"></a><span data-ttu-id="985e1-127">Esempi</span><span class="sxs-lookup"><span data-stu-id="985e1-127">Examples</span></span>

<span data-ttu-id="985e1-128">Visualizza i percorsi di tutte le directory locali della cache, ovvero directory della cache HTTP, directory della cache globale dei pacchetti e directory della cache temporanea:</span><span class="sxs-lookup"><span data-stu-id="985e1-128">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals –l all`

<span data-ttu-id="985e1-129">Visualizza il percorso della directory locale della cache HTTP:</span><span class="sxs-lookup"><span data-stu-id="985e1-129">Displays the path for the local http-cache directory:</span></span>

`dotnet nuget locals --list http-cache`

<span data-ttu-id="985e1-130">Cancella tutti i file da tutte le directory locali della cache, ovvero directory della cache HTTP, directory della cache globale dei pacchetti e directory della cache temporanea:</span><span class="sxs-lookup"><span data-stu-id="985e1-130">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals --clear all`

<span data-ttu-id="985e1-131">Cancella tutti i file presenti nella directory locale della cache globale dei pacchetti:</span><span class="sxs-lookup"><span data-stu-id="985e1-131">Clears all files in local global-packages cache directory:</span></span>

`dotnet nuget locals -c global-packages`

<span data-ttu-id="985e1-132">Cancella tutti i file presenti nella directory locale della cache temporanea:</span><span class="sxs-lookup"><span data-stu-id="985e1-132">Clears all files in local temporary cache directory:</span></span>

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a><span data-ttu-id="985e1-133">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="985e1-133">Troubleshooting</span></span>

<span data-ttu-id="985e1-134">Per informazioni su problemi ed errori comuni relativi all'uso del comando `dotnet nuget locals`, vedere [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache) (Gestione della cache NuGet).</span><span class="sxs-lookup"><span data-stu-id="985e1-134">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>