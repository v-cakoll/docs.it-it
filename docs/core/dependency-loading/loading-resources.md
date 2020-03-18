---
title: Algoritmo di caricamento di assembly satellite - .NET Core
description: Descrizione dei dettagli dell'algoritmo di caricamento dell'assembly Satellite in .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: bfdc1d8179d46a13b3d137a87397fa3e573da33c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70234615"
---
# <a name="satellite-assembly-loading-algorithm"></a><span data-ttu-id="5820e-103">Algoritmo di caricamento dell'assembly satellitare</span><span class="sxs-lookup"><span data-stu-id="5820e-103">Satellite assembly loading algorithm</span></span>

<span data-ttu-id="5820e-104">Gli assembly satellite vengono utilizzati per archiviare le risorse localizzate personalizzate per la lingua e le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="5820e-104">Satellite assemblies are used to store localized resources customized for language and culture.</span></span>

<span data-ttu-id="5820e-105">Gli assembly satellite utilizzano un algoritmo di caricamento diverso rispetto agli assembly gestiti generali.</span><span class="sxs-lookup"><span data-stu-id="5820e-105">Satellite assemblies use a different loading algorithm than general managed assemblies.</span></span>

## <a name="when-are-satellite-assemblies-loaded"></a><span data-ttu-id="5820e-106">Quando vengono caricati gli assembly satellite?</span><span class="sxs-lookup"><span data-stu-id="5820e-106">When are satellite assemblies loaded?</span></span>

<span data-ttu-id="5820e-107">Gli assembly satellite vengono caricati durante il caricamento di una risorsa localizzata.</span><span class="sxs-lookup"><span data-stu-id="5820e-107">Satellite assemblies are loaded when loading a localized resource.</span></span>

<span data-ttu-id="5820e-108">L'API di base per <xref:System.Resources.ResourceManager?displayProperty=fullName> caricare le risorse localizzate è la classe.</span><span class="sxs-lookup"><span data-stu-id="5820e-108">The basic API to load localized resources is the <xref:System.Resources.ResourceManager?displayProperty=fullName> class.</span></span> <span data-ttu-id="5820e-109">In definitiva <xref:System.Resources.ResourceManager> la classe <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> chiamerà <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>il metodo per ogni oggetto .</span><span class="sxs-lookup"><span data-stu-id="5820e-109">Ultimately the <xref:System.Resources.ResourceManager> class will call the <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> method for each <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="5820e-110">Le API di livello superiore possono astrarre l'API di basso livello.</span><span class="sxs-lookup"><span data-stu-id="5820e-110">Higher-level APIs may abstract the low-level API.</span></span>

## <a name="algorithm"></a><span data-ttu-id="5820e-111">Algoritmo</span><span class="sxs-lookup"><span data-stu-id="5820e-111">Algorithm</span></span>

<span data-ttu-id="5820e-112">Il processo di fallback per le risorse di .NET Core include i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5820e-112">The .NET Core resource fallback process involves the following steps:</span></span>

1. <span data-ttu-id="5820e-113">Determinare `active` <xref:System.Runtime.Loader.AssemblyLoadContext> l'istanza.</span><span class="sxs-lookup"><span data-stu-id="5820e-113">Determine the `active` <xref:System.Runtime.Loader.AssemblyLoadContext> instance.</span></span> <span data-ttu-id="5820e-114">In tutti i `active` casi, l'istanza <xref:System.Runtime.Loader.AssemblyLoadContext>è l'assembly in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5820e-114">In all cases, the `active` instance is the executing assembly's <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span>

2. <span data-ttu-id="5820e-115">L'istanza `active` tenta di caricare un assembly satellite per le impostazioni cultura richieste in ordine di priorità:The instance attempts to load a satellite assembly for the requested culture in priority order by:</span><span class="sxs-lookup"><span data-stu-id="5820e-115">The `active` instance attempts to load a satellite assembly for the requested culture in priority order by:</span></span>
    - <span data-ttu-id="5820e-116">Controllo della cache.</span><span class="sxs-lookup"><span data-stu-id="5820e-116">Checking its cache.</span></span>
    - <span data-ttu-id="5820e-117">Verifica della directory dell'assembly attualmente in esecuzione per <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> una `es-MX`sottodirectory che corrisponde alla richiesta (ad esempio ).</span><span class="sxs-lookup"><span data-stu-id="5820e-117">Checking the directory of the currently executing assembly for a subdirectory that matches the requested <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> (for example `es-MX`).</span></span>

        > [!NOTE]
        > <span data-ttu-id="5820e-118">Questa funzionalità non è stata implementata in .NET Core prima della 3.0.</span><span class="sxs-lookup"><span data-stu-id="5820e-118">This feature was not implemented in .NET Core before 3.0.</span></span>
        >
        > [!NOTE]
        > <span data-ttu-id="5820e-119">In Linux e macOS, la sottodirectory fa distinzione tra maiuscole e minuscole e deve:</span><span class="sxs-lookup"><span data-stu-id="5820e-119">On Linux and macOS, the subdirectory is case-sensitive and must either:</span></span>
        > - <span data-ttu-id="5820e-120">Esattamente caso di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="5820e-120">Exactly match case.</span></span>
        > - <span data-ttu-id="5820e-121">Essere in minuscolo.</span><span class="sxs-lookup"><span data-stu-id="5820e-121">Be in lower case.</span></span>

    - <span data-ttu-id="5820e-122">Se `active` è <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> l'istanza, eseguendo la logica di [probe dell'assembly satellite (risorsa) predefinita.](default-probing.md#satellite-resource-assembly-probing)</span><span class="sxs-lookup"><span data-stu-id="5820e-122">If `active` is the <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> instance, by running the [default satellite (resource) assembly probing](default-probing.md#satellite-resource-assembly-probing) logic.</span></span>

    - <span data-ttu-id="5820e-123">Chiamata <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> della funzione.</span><span class="sxs-lookup"><span data-stu-id="5820e-123">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> function.</span></span>

    - <span data-ttu-id="5820e-124">Generazione <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> dell'evento.</span><span class="sxs-lookup"><span data-stu-id="5820e-124">Raising the <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> event.</span></span>

    - <span data-ttu-id="5820e-125">Generazione <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> dell'evento.</span><span class="sxs-lookup"><span data-stu-id="5820e-125">Raising the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>

3. <span data-ttu-id="5820e-126">Se viene caricato un assembly satellite:</span><span class="sxs-lookup"><span data-stu-id="5820e-126">If a satellite assembly is loaded:</span></span>
   - <span data-ttu-id="5820e-127">Viene generato l'evento <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5820e-127">The <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType> event is raised.</span></span>
   - <span data-ttu-id="5820e-128">All'assembly viene cercata la risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="5820e-128">The assembly is searched it for the requested resource.</span></span> <span data-ttu-id="5820e-129">Se il runtime trova la risorsa nell'assembly, la utilizza.</span><span class="sxs-lookup"><span data-stu-id="5820e-129">If the runtime finds the resource in the assembly, it uses it.</span></span> <span data-ttu-id="5820e-130">In caso contrario la ricerca continua.</span><span class="sxs-lookup"><span data-stu-id="5820e-130">If it doesn't find the resource, it continues the search.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5820e-131">Per trovare una risorsa all'interno dell'assembly satellite, il runtime cerca il file di risorse richiesto da <xref:System.Resources.ResourceManager> per la proprietà <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> corrente.</span><span class="sxs-lookup"><span data-stu-id="5820e-131">To find a resource within the satellite assembly, the runtime searches for the resource file requested by the <xref:System.Resources.ResourceManager> for the current <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5820e-132">All'interno del file di risorse, cerca il nome della risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="5820e-132">Within the resource file, it searches for the requested resource name.</span></span> <span data-ttu-id="5820e-133">Se uno dei due non viene trovato, la risorsa viene considerata come non trovata.</span><span class="sxs-lookup"><span data-stu-id="5820e-133">If either is not found, the resource is treated as not found.</span></span>

4. <span data-ttu-id="5820e-134">Il runtime cerca quindi gli assembly delle impostazioni cultura padre attraverso molti livelli potenziali, ripetendo ogni volta i passaggi 2 & 3.</span><span class="sxs-lookup"><span data-stu-id="5820e-134">The runtime next searches the parent culture assemblies through many potential levels, each time repeating steps 2 & 3.</span></span>

    <span data-ttu-id="5820e-135">Ogni lingua ha un solo elemento <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType> padre, definito dalla proprietà .</span><span class="sxs-lookup"><span data-stu-id="5820e-135">Each culture has only one parent, which is defined by the <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType> property.</span></span>

    <span data-ttu-id="5820e-136">La ricerca delle impostazioni cultura padre <xref:System.Globalization.CultureInfo.Parent%2A> viene <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>interrotta quando la proprietà di un'applicazione delle impostazioni cultura è .</span><span class="sxs-lookup"><span data-stu-id="5820e-136">The search for parent cultures stops when a culture's <xref:System.Globalization.CultureInfo.Parent%2A> property is <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>.</span></span>

    <span data-ttu-id="5820e-137">Per <xref:System.Globalization.CultureInfo.InvariantCulture>il , non torniamo ai passaggi 2 & 3, ma si continua con il passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="5820e-137">For the <xref:System.Globalization.CultureInfo.InvariantCulture>, we don't return to steps 2 & 3, but rather continue with step 5.</span></span>

5. <span data-ttu-id="5820e-138">Se la risorsa non viene ancora trovata, viene utilizzata la risorsa per le impostazioni cultura predefinite (fallback).</span><span class="sxs-lookup"><span data-stu-id="5820e-138">If the resource is still not found, the resource for the default (fallback) culture is used.</span></span>

   <span data-ttu-id="5820e-139">In genere le risorse delle impostazioni cultura predefinite sono incluse nell'assembly principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5820e-139">Typically, the resources for the default culture are included in the main application assembly.</span></span> <span data-ttu-id="5820e-140">Tuttavia, è <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> possibile <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType> specificare per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="5820e-140">However, you can specify <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> for the <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="5820e-141">Questo valore indica che il percorso di fallback finale per le risorse è un assembly satellite anziché l'assembly principale.</span><span class="sxs-lookup"><span data-stu-id="5820e-141">This value indicates that the ultimate fallback location for resources is a satellite assembly rather than the main assembly.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5820e-142">Le impostazioni cultura predefinite sono il fallback finale.</span><span class="sxs-lookup"><span data-stu-id="5820e-142">The default culture is the ultimate fallback.</span></span> <span data-ttu-id="5820e-143">Pertanto, è consigliabile includere sempre un set completo di risorse nel file di risorse predefinito.</span><span class="sxs-lookup"><span data-stu-id="5820e-143">Therefore, we recommend that you always include an exhaustive set of resources in the default resource file.</span></span> <span data-ttu-id="5820e-144">Ciò evita la generazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="5820e-144">This helps prevent exceptions from being thrown.</span></span> <span data-ttu-id="5820e-145">Con un set completo, si fornisce un fallback per tutte le risorse e si garantisce che almeno una risorsa sia sempre presente per l'utente, anche se non è specifica delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="5820e-145">By having an exhaustive set, you provide a fallback for all resources and ensure that at least one resource is always present for the user, even if it is not culturally specific.</span></span>

6. <span data-ttu-id="5820e-146">Infine</span><span class="sxs-lookup"><span data-stu-id="5820e-146">Finally,</span></span>
   - <span data-ttu-id="5820e-147">Se il runtime non trova un file di risorse per <xref:System.Resources.MissingManifestResourceException> <xref:System.Resources.MissingSatelliteAssemblyException> le impostazioni cultura predefinite (fallback), viene generata un'eccezione o .</span><span class="sxs-lookup"><span data-stu-id="5820e-147">If the runtime doesn't find a resource file for a default (fallback) culture, a <xref:System.Resources.MissingManifestResourceException> or <xref:System.Resources.MissingSatelliteAssemblyException> exception is thrown.</span></span>
   - <span data-ttu-id="5820e-148">Se il file di risorse viene trovato ma la `null`risorsa richiesta non è presente, la richiesta restituisce .</span><span class="sxs-lookup"><span data-stu-id="5820e-148">If the resource file is found but the requested resource isn't present, the request returns `null`.</span></span>
