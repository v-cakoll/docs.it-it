---
title: Sondaggio predefinito-.NET Core
description: Panoramica della logica di probe di .NET Core <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> per individuare le dipendenze.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 2fa8a13bcb08a767fa965621f95bec8619aea5cc
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926403"
---
# <a name="default-probing"></a><span data-ttu-id="58a2a-103">Sondaggio predefinito</span><span class="sxs-lookup"><span data-stu-id="58a2a-103">Default probing</span></span>

<span data-ttu-id="58a2a-104">L' <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> istanza è responsabile dell'individuazione delle dipendenze di un assembly.</span><span class="sxs-lookup"><span data-stu-id="58a2a-104">The <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance is responsible for locating an assembly's dependencies.</span></span> <span data-ttu-id="58a2a-105">Questo articolo descrive la <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> logica di probe dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="58a2a-105">This article describes the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance's probing logic.</span></span>

## <a name="host-configured-probing-properties"></a><span data-ttu-id="58a2a-106">Proprietà di probe configurate dall'host</span><span class="sxs-lookup"><span data-stu-id="58a2a-106">Host configured probing properties</span></span>

<span data-ttu-id="58a2a-107">Quando il runtime viene avviato, l'host di runtime fornisce un set di proprietà di sondaggio denominate che configurano <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> i percorsi di probe.</span><span class="sxs-lookup"><span data-stu-id="58a2a-107">When the runtime is started, the runtime host provides a set of named probing properties that configure <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> probe paths.</span></span>

<span data-ttu-id="58a2a-108">Ogni proprietà di sondaggio è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="58a2a-108">Each probing property is optional.</span></span>  <span data-ttu-id="58a2a-109">Se presente, ogni proprietà è un valore stringa che contiene un elenco delimitato di percorsi assoluti.</span><span class="sxs-lookup"><span data-stu-id="58a2a-109">If present, each property is a string value that contains a delimited list of absolute paths.</span></span> <span data-ttu-id="58a2a-110">Il delimitatore è ";" in Windows e ":" in tutte le altre piattaforme.</span><span class="sxs-lookup"><span data-stu-id="58a2a-110">The delimiter is ';' on Windows and ':' on all other platforms.</span></span>

|<span data-ttu-id="58a2a-111">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="58a2a-111">Property Name</span></span>                 |<span data-ttu-id="58a2a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58a2a-112">Description</span></span>  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | <span data-ttu-id="58a2a-113">Elenco di percorsi di file di assembly della piattaforma e dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="58a2a-113">List of platform and application assembly file paths.</span></span> |
|`PLATFORM_RESOURCE_ROOTS`       | <span data-ttu-id="58a2a-114">Elenco di percorsi di directory in cui cercare gli assembly di risorse satellite.</span><span class="sxs-lookup"><span data-stu-id="58a2a-114">List of directory paths to search for satellite resource assemblies.</span></span> |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | <span data-ttu-id="58a2a-115">Elenco di percorsi di directory in cui cercare le librerie non gestite (native).</span><span class="sxs-lookup"><span data-stu-id="58a2a-115">List of directory paths to search for unmanaged (native) libraries.</span></span>        |
|`APP_PATHS`                     | <span data-ttu-id="58a2a-116">Elenco di percorsi di directory in cui cercare gli assembly gestiti</span><span class="sxs-lookup"><span data-stu-id="58a2a-116">List of directory paths to search for managed assemblies</span></span> |
|`APP_NI_PATHS`                  | <span data-ttu-id="58a2a-117">Elenco di percorsi di directory in cui cercare le immagini native degli assembly gestiti.</span><span class="sxs-lookup"><span data-stu-id="58a2a-117">List of directory paths to search for native images of managed assemblies.</span></span> |

### <a name="how-are-the-properties-populated"></a><span data-ttu-id="58a2a-118">Come vengono popolate le proprietà?</span><span class="sxs-lookup"><span data-stu-id="58a2a-118">How are the properties populated?</span></span>

<span data-ttu-id="58a2a-119">Esistono due scenari principali per il popolamento delle proprietà a seconda che il `<myapp>.deps.json` file esista.</span><span class="sxs-lookup"><span data-stu-id="58a2a-119">There are two main scenarios for populating the properties depending on whether the `<myapp>.deps.json` file exists.</span></span>

- <span data-ttu-id="58a2a-120">Quando il `*.deps.json` file è presente, viene analizzato per popolare le proprietà di probe.</span><span class="sxs-lookup"><span data-stu-id="58a2a-120">When the `*.deps.json` file is present, it's parsed to populate the probing properties.</span></span>
- <span data-ttu-id="58a2a-121">Quando il `*.deps.json` file non è presente, si presuppone che la directory dell'applicazione contenga tutte le dipendenze.</span><span class="sxs-lookup"><span data-stu-id="58a2a-121">When the `*.deps.json` file isn't present, the application's directory is assumed to contain all the dependencies.</span></span> <span data-ttu-id="58a2a-122">Il contenuto della directory viene usato per popolare le proprietà di probe.</span><span class="sxs-lookup"><span data-stu-id="58a2a-122">The directory's contents are used to populate the probing properties.</span></span>

<span data-ttu-id="58a2a-123">Inoltre, i `*.deps.json` file per tutti i Framework a cui viene fatto riferimento vengono analizzati in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="58a2a-123">Additionally, the `*.deps.json` files for any referenced frameworks are similarly parsed.</span></span>

<span data-ttu-id="58a2a-124">Infine, è possibile `ADDITIONAL_DEPS` usare la variabile di ambiente per aggiungere altre dipendenze.</span><span class="sxs-lookup"><span data-stu-id="58a2a-124">Finally the environment variable `ADDITIONAL_DEPS` can be used to add additional dependencies.</span></span>

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a><span data-ttu-id="58a2a-125">Ricerca per categorie visualizzare le proprietà del sondaggio dal codice gestito?</span><span class="sxs-lookup"><span data-stu-id="58a2a-125">How do I see the probing properties from managed code?</span></span>

<span data-ttu-id="58a2a-126">Ogni proprietà è disponibile chiamando la <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> funzione con il nome della proprietà della tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="58a2a-126">Each property is available by calling the <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> function with the property name from the table above.</span></span>

### <a name="how-do-i-debug-the-probing-properties-construction"></a><span data-ttu-id="58a2a-127">Ricerca per categorie eseguire il debug della costruzione delle proprietà di probe?</span><span class="sxs-lookup"><span data-stu-id="58a2a-127">How do I debug the probing properties' construction?</span></span>

<span data-ttu-id="58a2a-128">Quando sono abilitate determinate variabili di ambiente, l'host di runtime di .NET Core restituirà messaggi di traccia utili:</span><span class="sxs-lookup"><span data-stu-id="58a2a-128">The .NET Core runtime host will output useful trace messages when certain environment variables are enabled:</span></span>

|<span data-ttu-id="58a2a-129">Variabile di ambiente</span><span class="sxs-lookup"><span data-stu-id="58a2a-129">Environment Variable</span></span>        |<span data-ttu-id="58a2a-130">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="58a2a-130">Description</span></span>  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |<span data-ttu-id="58a2a-131">Abilita la traccia.</span><span class="sxs-lookup"><span data-stu-id="58a2a-131">Enables tracing.</span></span>|
|`COREHOST_TRACEFILE=<path>` |<span data-ttu-id="58a2a-132">Traccia in un percorso di file anziché in quello `stderr`predefinito.</span><span class="sxs-lookup"><span data-stu-id="58a2a-132">Traces to a file path instead of the default `stderr`.</span></span>|
|`COREHOST_TRACE_VERBOSITY`  |<span data-ttu-id="58a2a-133">Imposta il livello di dettaglio da 1 (più basso) a 4 (massimo).</span><span class="sxs-lookup"><span data-stu-id="58a2a-133">Sets the verbosity from 1 (lowest) to 4 (highest).</span></span>|

## <a name="managed-assembly-default-probing"></a><span data-ttu-id="58a2a-134">Sondaggio predefinito assembly gestito</span><span class="sxs-lookup"><span data-stu-id="58a2a-134">Managed assembly default probing</span></span>

<span data-ttu-id="58a2a-135">Quando si esegue il probe per individuare un assembly <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> gestito, il Cerca nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="58a2a-135">When probing to locate a managed assembly, the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> looks in order at:</span></span>

- <span data-ttu-id="58a2a-136">File corrispondenti a <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` (dopo la rimozione di estensioni di file).</span><span class="sxs-lookup"><span data-stu-id="58a2a-136">Files matching the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` (after removing file extensions).</span></span>
- <span data-ttu-id="58a2a-137">File di assembly di immagini `APP_NI_PATHS` native in con estensioni di file comuni.</span><span class="sxs-lookup"><span data-stu-id="58a2a-137">Native image assembly files in `APP_NI_PATHS` with common file extensions.</span></span>
- <span data-ttu-id="58a2a-138">File di assembly `APP_PATHS` in con estensioni di file comuni.</span><span class="sxs-lookup"><span data-stu-id="58a2a-138">Assembly files in `APP_PATHS` with common file extensions.</span></span>

## <a name="satellite-resource-assembly-probing"></a><span data-ttu-id="58a2a-139">Probe assembly satellite (risorsa)</span><span class="sxs-lookup"><span data-stu-id="58a2a-139">Satellite (resource) assembly probing</span></span>

<span data-ttu-id="58a2a-140">Per trovare un assembly satellite per impostazioni cultura specifiche, costruire un set di percorsi di file.</span><span class="sxs-lookup"><span data-stu-id="58a2a-140">To find a satellite assembly for a specific culture, construct a set of file paths.</span></span>

<span data-ttu-id="58a2a-141">Per ogni percorso in `PLATFORM_RESOURCE_ROOTS` e quindi `APP_PATHS`aggiungere la <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> stringa, un separatore di directory, <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> la stringa e l'estensione ". dll".</span><span class="sxs-lookup"><span data-stu-id="58a2a-141">For each path in `PLATFORM_RESOURCE_ROOTS` and then `APP_PATHS`, append the <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> string, a directory separator, the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> string, and the extension '.dll'.</span></span>

<span data-ttu-id="58a2a-142">Se esiste un file corrispondente, provare a caricarlo e restituirlo.</span><span class="sxs-lookup"><span data-stu-id="58a2a-142">If any matching file exists, attempt to load and return it.</span></span>

## <a name="unmanaged-native-library-probing"></a><span data-ttu-id="58a2a-143">Sondaggio della libreria non gestito (nativo)</span><span class="sxs-lookup"><span data-stu-id="58a2a-143">Unmanaged (native) library probing</span></span>

<span data-ttu-id="58a2a-144">Quando si esegue il probe per individuare una libreria non gestita `NATIVE_DLL_SEARCH_DIRECTORIES` , viene eseguita la ricerca di una libreria corrispondente.</span><span class="sxs-lookup"><span data-stu-id="58a2a-144">When probing to locate an unmanaged library, the `NATIVE_DLL_SEARCH_DIRECTORIES` are searched looking for a matching library,</span></span>
