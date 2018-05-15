---
title: Comando dotnet nuget locals - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet nuget locals cancella o elenca le risorse NuGet locali, quali cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: d0c900a06b00fd5e6b7ad66527c6582483222c45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="5a333-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="5a333-103">dotnet nuget locals</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="5a333-104">nome</span><span class="sxs-lookup"><span data-stu-id="5a333-104">Name</span></span>

<span data-ttu-id="5a333-105">`dotnet nuget locals`: cancella o elenca risorse NuGet locali.</span><span class="sxs-lookup"><span data-stu-id="5a333-105">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5a333-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="5a333-106">Synopsis</span></span>

`dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="5a333-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a333-107">Description</span></span>

<span data-ttu-id="5a333-108">Il comando `dotnet nuget locals` cancella o elenca risorse NuGet locali presenti nella cache delle richieste HTTP, nella cache temporanea o nella cartella globale dei pacchetti a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="5a333-108">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="5a333-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5a333-109">Arguments</span></span>

`CACHE_LOCATION`

<span data-ttu-id="5a333-110">Uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a333-110">One of the following values:</span></span>

* <span data-ttu-id="5a333-111">`all` - Indica che l'operazione specificata viene applicata a tutti i tipi di cache, ovvero alla cache delle richieste HTTP, alla cache globale dei pacchetti e alla cache temporanea.</span><span class="sxs-lookup"><span data-stu-id="5a333-111">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
* <span data-ttu-id="5a333-112">`http-cache` - Indica che l'operazione specificata viene applicata soltanto alla cache delle richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="5a333-112">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="5a333-113">Le altre posizioni di cache non sono interessate.</span><span class="sxs-lookup"><span data-stu-id="5a333-113">The other cache locations are not affected.</span></span>
* <span data-ttu-id="5a333-114">`global-packages` - Indica che l'operazione specificata viene applicata soltanto alla cache dei pacchetti globale.</span><span class="sxs-lookup"><span data-stu-id="5a333-114">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="5a333-115">Le altre posizioni di cache non sono interessate.</span><span class="sxs-lookup"><span data-stu-id="5a333-115">The other cache locations are not affected.</span></span>
* <span data-ttu-id="5a333-116">`temp` - Indica che l'operazione specificata viene applicata soltanto alla cache temporanea.</span><span class="sxs-lookup"><span data-stu-id="5a333-116">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="5a333-117">Le altre posizioni di cache non sono interessate.</span><span class="sxs-lookup"><span data-stu-id="5a333-117">The other cache locations are not affected.</span></span>

## <a name="options"></a><span data-ttu-id="5a333-118">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5a333-118">Options</span></span>

`-h|--help`

<span data-ttu-id="5a333-119">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="5a333-119">Prints out a short help for the command.</span></span>

`-c|--clear`

<span data-ttu-id="5a333-120">L'opzione "clear" consente di eseguire un'operazione di cancellazione sul tipo di cache specificato.</span><span class="sxs-lookup"><span data-stu-id="5a333-120">The clear option performs a clear operation on the specified cache type.</span></span> <span data-ttu-id="5a333-121">Il contenuto delle directory della cache viene eliminato in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="5a333-121">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="5a333-122">L'utente o il gruppo che esegue l'operazione deve disporre delle autorizzazioni per i file presenti nelle directory della cache.</span><span class="sxs-lookup"><span data-stu-id="5a333-122">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="5a333-123">In caso contrario, viene visualizzato un messaggio di errore con l'indicazione delle cartelle e/o dei file che non sono stati cancellati.</span><span class="sxs-lookup"><span data-stu-id="5a333-123">If not, an error is displayed indicating the files/folders which were not cleared.</span></span>

`-l|--list`

<span data-ttu-id="5a333-124">L'opzione "list" viene usata per visualizzare la posizione del tipo di cache specificato.</span><span class="sxs-lookup"><span data-stu-id="5a333-124">The list option is used to display the location of the specified cache type.</span></span> 

`--force-english-output`

<span data-ttu-id="5a333-125">Forza la visualizzazione dell'output della riga di comando in inglese.</span><span class="sxs-lookup"><span data-stu-id="5a333-125">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="5a333-126">Esempi</span><span class="sxs-lookup"><span data-stu-id="5a333-126">Examples</span></span>

<span data-ttu-id="5a333-127">Visualizza i percorsi di tutte le directory locali della cache, ovvero directory della cache HTTP, directory della cache globale dei pacchetti e directory della cache temporanea:</span><span class="sxs-lookup"><span data-stu-id="5a333-127">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals –l all`

<span data-ttu-id="5a333-128">Visualizza il percorso della directory locale della cache HTTP:</span><span class="sxs-lookup"><span data-stu-id="5a333-128">Displays the path for the local http-cache directory:</span></span>

`dotnet nuget locals --list http-cache`

<span data-ttu-id="5a333-129">Cancella tutti i file da tutte le directory locali della cache, ovvero directory della cache HTTP, directory della cache globale dei pacchetti e directory della cache temporanea:</span><span class="sxs-lookup"><span data-stu-id="5a333-129">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals --clear all`

<span data-ttu-id="5a333-130">Cancella tutti i file presenti nella directory locale della cache globale dei pacchetti:</span><span class="sxs-lookup"><span data-stu-id="5a333-130">Clears all files in local global-packages cache directory:</span></span>

`dotnet nuget locals -c global-packages`

<span data-ttu-id="5a333-131">Cancella tutti i file presenti nella directory locale della cache temporanea:</span><span class="sxs-lookup"><span data-stu-id="5a333-131">Clears all files in local temporary cache directory:</span></span>

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a><span data-ttu-id="5a333-132">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="5a333-132">Troubleshooting</span></span>

<span data-ttu-id="5a333-133">Per informazioni su problemi ed errori comuni relativi all'uso del comando `dotnet nuget locals`, vedere [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache) (Gestione della cache NuGet).</span><span class="sxs-lookup"><span data-stu-id="5a333-133">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>