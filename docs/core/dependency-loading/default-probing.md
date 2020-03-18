---
title: Sondaggio predefinito - .NET CoreDefault probing - .NET Core
description: Panoramica della logica di probe System.Runtime.Loader.AssemblyLoadContext.Default di .NET Core per individuare le dipendenze.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 500ee6ee863b1f311970a9e718936f57f7d4efd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399091"
---
# <a name="default-probing"></a><span data-ttu-id="c9fa3-103">Sondaggio predefinito</span><span class="sxs-lookup"><span data-stu-id="c9fa3-103">Default probing</span></span>

<span data-ttu-id="c9fa3-104">L'istanza <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> è responsabile dell'individuazione delle dipendenze di un assembly.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-104">The <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance is responsible for locating an assembly's dependencies.</span></span> <span data-ttu-id="c9fa3-105">In questo articolo <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> viene descritta la logica di probe dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-105">This article describes the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance's probing logic.</span></span>

## <a name="host-configured-probing-properties"></a><span data-ttu-id="c9fa3-106">Proprietà di sondaggio configurate dall'host</span><span class="sxs-lookup"><span data-stu-id="c9fa3-106">Host configured probing properties</span></span>

<span data-ttu-id="c9fa3-107">Quando il runtime viene avviato, l'host di runtime <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> fornisce un set di proprietà di probe denominate che configurano i percorsi probe.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-107">When the runtime is started, the runtime host provides a set of named probing properties that configure <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> probe paths.</span></span>

<span data-ttu-id="c9fa3-108">Ogni proprietà di sondaggio è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-108">Each probing property is optional.</span></span> <span data-ttu-id="c9fa3-109">Se presente, ogni proprietà è un valore stringa che contiene un elenco delimitato di percorsi assoluti.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-109">If present, each property is a string value that contains a delimited list of absolute paths.</span></span> <span data-ttu-id="c9fa3-110">Il delimitatore è ';' in Windows e ':' su tutte le altre piattaforme.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-110">The delimiter is ';' on Windows and ':' on all other platforms.</span></span>

|<span data-ttu-id="c9fa3-111">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="c9fa3-111">Property Name</span></span>                 |<span data-ttu-id="c9fa3-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9fa3-112">Description</span></span>  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | <span data-ttu-id="c9fa3-113">Elenco dei percorsi dei file di assembly della piattaforma e dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-113">List of platform and application assembly file paths.</span></span> |
|`PLATFORM_RESOURCE_ROOTS`       | <span data-ttu-id="c9fa3-114">Elenco dei percorsi di directory per la ricerca di assembly di risorse satellite.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-114">List of directory paths to search for satellite resource assemblies.</span></span> |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | <span data-ttu-id="c9fa3-115">Elenco dei percorsi di directory per la ricerca di librerie non gestite (native).</span><span class="sxs-lookup"><span data-stu-id="c9fa3-115">List of directory paths to search for unmanaged (native) libraries.</span></span>        |
|`APP_PATHS`                     | <span data-ttu-id="c9fa3-116">Elenco dei percorsi di directory per la ricerca di assembly gestiti.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-116">List of directory paths to search for managed assemblies.</span></span> |
|`APP_NI_PATHS`                  | <span data-ttu-id="c9fa3-117">Elenco dei percorsi di directory per la ricerca di immagini native di assembly gestiti.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-117">List of directory paths to search for native images of managed assemblies.</span></span> |

### <a name="how-are-the-properties-populated"></a><span data-ttu-id="c9fa3-118">Come vengono popolate le proprietà?</span><span class="sxs-lookup"><span data-stu-id="c9fa3-118">How are the properties populated?</span></span>

<span data-ttu-id="c9fa3-119">Esistono due scenari principali per popolare le proprietà a seconda che il file \* \<>.deps.json esista\* o meno.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-119">There are two main scenarios for populating the properties depending on whether the *\<myapp>.deps.json* file exists.</span></span>

- <span data-ttu-id="c9fa3-120">Quando il \* \*file .deps.json\* è presente, viene analizzato per popolare le proprietà di sondaggio.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-120">When the *\*.deps.json* file is present, it's parsed to populate the probing properties.</span></span>
- <span data-ttu-id="c9fa3-121">Quando il \* \*file .deps.json\* non è presente, si presuppone che la directory dell'applicazione contenga tutte le dipendenze.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-121">When the *\*.deps.json* file isn't present, the application's directory is assumed to contain all the dependencies.</span></span> <span data-ttu-id="c9fa3-122">Il contenuto della directory viene utilizzato per popolare le proprietà di sondaggio.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-122">The directory's contents are used to populate the probing properties.</span></span>

<span data-ttu-id="c9fa3-123">Inoltre, i \* \*file .deps.json\* per tutti i framework a cui si fa riferimento vengono analizzati in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-123">Additionally, the *\*.deps.json* files for any referenced frameworks are similarly parsed.</span></span>

<span data-ttu-id="c9fa3-124">Infine la `ADDITIONAL_DEPS` variabile di ambiente può essere utilizzata per aggiungere ulteriori dipendenze.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-124">Finally the environment variable `ADDITIONAL_DEPS` can be used to add additional dependencies.</span></span>

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a><span data-ttu-id="c9fa3-125">Come si visualizzano le proprietà di sondaggio dal codice gestito?</span><span class="sxs-lookup"><span data-stu-id="c9fa3-125">How do I see the probing properties from managed code?</span></span>

<span data-ttu-id="c9fa3-126">Ogni proprietà è disponibile <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> chiamando la funzione con il nome della proprietà dalla tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-126">Each property is available by calling the <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> function with the property name from the table above.</span></span>

### <a name="how-do-i-debug-the-probing-properties-construction"></a><span data-ttu-id="c9fa3-127">Come si esegue il debug della costruzione delle proprietà di sondaggio?</span><span class="sxs-lookup"><span data-stu-id="c9fa3-127">How do I debug the probing properties' construction?</span></span>

<span data-ttu-id="c9fa3-128">L'host di runtime .NET Core emetterà messaggi di traccia utili quando sono abilitate determinate variabili di ambiente:The .NET Core runtime host will output useful trace messages when certain environment variables are enabled:</span><span class="sxs-lookup"><span data-stu-id="c9fa3-128">The .NET Core runtime host will output useful trace messages when certain environment variables are enabled:</span></span>

|<span data-ttu-id="c9fa3-129">Variabile di ambiente</span><span class="sxs-lookup"><span data-stu-id="c9fa3-129">Environment Variable</span></span>        |<span data-ttu-id="c9fa3-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9fa3-130">Description</span></span>  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |<span data-ttu-id="c9fa3-131">Abilita la traccia.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-131">Enables tracing.</span></span>|
|`COREHOST_TRACEFILE=<path>` |<span data-ttu-id="c9fa3-132">Traccia in un percorso di `stderr`file anziché nell'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-132">Traces to a file path instead of the default `stderr`.</span></span>|
|`COREHOST_TRACE_VERBOSITY`  |<span data-ttu-id="c9fa3-133">Imposta il livello di dettaglio da 1 (più basso) a 4 (più alto).</span><span class="sxs-lookup"><span data-stu-id="c9fa3-133">Sets the verbosity from 1 (lowest) to 4 (highest).</span></span>|

## <a name="managed-assembly-default-probing"></a><span data-ttu-id="c9fa3-134">Sondaggio predefinito dell'assembly gestito</span><span class="sxs-lookup"><span data-stu-id="c9fa3-134">Managed assembly default probing</span></span>

<span data-ttu-id="c9fa3-135">Quando si esegue il probe <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> per individuare un assembly gestito, l'aspetto viene esaminato in ordine:</span><span class="sxs-lookup"><span data-stu-id="c9fa3-135">When probing to locate a managed assembly, the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> looks in order at:</span></span>

- <span data-ttu-id="c9fa3-136">File corrispondenti `TRUSTED_PLATFORM_ASSEMBLIES` all'in <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> (dopo la rimozione delle estensioni di file).</span><span class="sxs-lookup"><span data-stu-id="c9fa3-136">Files matching the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` (after removing file extensions).</span></span>
- <span data-ttu-id="c9fa3-137">File di assembly `APP_NI_PATHS` di immagini native con estensioni di file comuni.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-137">Native image assembly files in `APP_NI_PATHS` with common file extensions.</span></span>
- <span data-ttu-id="c9fa3-138">File di `APP_PATHS` assembly con estensioni di file comuni.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-138">Assembly files in `APP_PATHS` with common file extensions.</span></span>

## <a name="satellite-resource-assembly-probing"></a><span data-ttu-id="c9fa3-139">Sondaggio dell'assembly satellite (risorsa)</span><span class="sxs-lookup"><span data-stu-id="c9fa3-139">Satellite (resource) assembly probing</span></span>

<span data-ttu-id="c9fa3-140">Per trovare un assembly satellite per impostazioni cultura specifiche, creare un set di percorsi di file.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-140">To find a satellite assembly for a specific culture, construct a set of file paths.</span></span>

<span data-ttu-id="c9fa3-141">Per ogni `PLATFORM_RESOURCE_ROOTS` percorso `APP_PATHS`in and <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> then , aggiungere <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> la stringa, un separatore di directory, la stringa e l'estensione '.dll'.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-141">For each path in `PLATFORM_RESOURCE_ROOTS` and then `APP_PATHS`, append the <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> string, a directory separator, the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> string, and the extension '.dll'.</span></span>

<span data-ttu-id="c9fa3-142">Se esiste un file corrispondente, provare a caricarlo e restituirlo.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-142">If any matching file exists, attempt to load and return it.</span></span>

## <a name="unmanaged-native-library-probing"></a><span data-ttu-id="c9fa3-143">Sondaggio della libreria non gestita (nativa)Unmanaged (native) library probing</span><span class="sxs-lookup"><span data-stu-id="c9fa3-143">Unmanaged (native) library probing</span></span>

<span data-ttu-id="c9fa3-144">Durante il probe per individuare una `NATIVE_DLL_SEARCH_DIRECTORIES` libreria non gestita, viene cercato una libreria corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c9fa3-144">When probing to locate an unmanaged library, the `NATIVE_DLL_SEARCH_DIRECTORIES` are searched looking for a matching library.</span></span>
