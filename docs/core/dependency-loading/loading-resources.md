---
title: Algoritmo di caricamento degli assembly satellite-.NET Core
description: Descrizione dei dettagli dell'algoritmo di caricamento degli assembly satellite in .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 17f29a9aca79019daa91736e586bf1b6b753a9ec
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859524"
---
# <a name="satellite-assembly-loading-algorithm"></a><span data-ttu-id="b5da9-103">Algoritmo di caricamento degli assembly satellite</span><span class="sxs-lookup"><span data-stu-id="b5da9-103">Satellite assembly loading algorithm</span></span>

<span data-ttu-id="b5da9-104">Gli assembly satellite vengono usati per archiviare le risorse localizzate personalizzate per la lingua e le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="b5da9-104">Satellite assemblies are used to store localized resources customized for language and culture.</span></span>

<span data-ttu-id="b5da9-105">Gli assembly satellite usano un algoritmo di caricamento diverso rispetto agli assembly gestiti generali.</span><span class="sxs-lookup"><span data-stu-id="b5da9-105">Satellite assemblies use a different loading algorithm than general managed assemblies.</span></span>

## <a name="when-are-satellite-assemblies-loaded"></a><span data-ttu-id="b5da9-106">Quando vengono caricati gli assembly satellite?</span><span class="sxs-lookup"><span data-stu-id="b5da9-106">When are satellite assemblies loaded?</span></span>

<span data-ttu-id="b5da9-107">Gli assembly satellite vengono caricati durante il caricamento di una risorsa localizzata.</span><span class="sxs-lookup"><span data-stu-id="b5da9-107">Satellite assemblies are loaded when loading a localized resource.</span></span>

<span data-ttu-id="b5da9-108">L'API di base per caricare le risorse localizzate è la <xref:System.Resources.ResourceManager?displayProperty=fullName> classe.</span><span class="sxs-lookup"><span data-stu-id="b5da9-108">The basic API to load localized resources is the <xref:System.Resources.ResourceManager?displayProperty=fullName> class.</span></span> <span data-ttu-id="b5da9-109">Infine, la <xref:System.Resources.ResourceManager> classe chiamerà il <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> metodo per ogni <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b5da9-109">Ultimately the <xref:System.Resources.ResourceManager> class will call the <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> method for each <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="b5da9-110">Le API di livello superiore possono astrarre l'API di basso livello.</span><span class="sxs-lookup"><span data-stu-id="b5da9-110">Higher-level APIs may abstract the low-level API.</span></span>

## <a name="algorithm"></a><span data-ttu-id="b5da9-111">Algoritmo</span><span class="sxs-lookup"><span data-stu-id="b5da9-111">Algorithm</span></span>

<span data-ttu-id="b5da9-112">Il processo di fallback per le risorse di .NET Core include i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5da9-112">The .NET Core resource fallback process involves the following steps:</span></span>

1. <span data-ttu-id="b5da9-113">Determinare l' `active` <xref:System.Runtime.Loader.AssemblyLoadContext> istanza.</span><span class="sxs-lookup"><span data-stu-id="b5da9-113">Determine the `active` <xref:System.Runtime.Loader.AssemblyLoadContext> instance.</span></span> <span data-ttu-id="b5da9-114">In tutti i casi, `active` l'istanza è l'assembly in esecuzione <xref:System.Runtime.Loader.AssemblyLoadContext>.</span><span class="sxs-lookup"><span data-stu-id="b5da9-114">In all cases, the `active` instance is the executing assembly's <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span>

2. <span data-ttu-id="b5da9-115">L' `active` istanza tenta di caricare un assembly satellite per le impostazioni cultura richieste in ordine di priorità:</span><span class="sxs-lookup"><span data-stu-id="b5da9-115">The `active` instance attempts to load a satellite assembly for the requested culture in priority order by:</span></span>
    - <span data-ttu-id="b5da9-116">Verifica della cache.</span><span class="sxs-lookup"><span data-stu-id="b5da9-116">Checking its cache.</span></span>
    - <span data-ttu-id="b5da9-117">Verifica della directory dell'assembly attualmente in esecuzione per una sottodirectory che corrisponde alla richiesta <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> (ad esempio `es-MX`).</span><span class="sxs-lookup"><span data-stu-id="b5da9-117">Checking the directory of the currently executing assembly for a subdirectory that matches the requested <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> (for example `es-MX`).</span></span>

        > [!NOTE]
        > <span data-ttu-id="b5da9-118">Questa funzionalità non è stata implementata in .NET Core prima del 3,0.</span><span class="sxs-lookup"><span data-stu-id="b5da9-118">This feature was not implemented in .NET Core before 3.0.</span></span>
        >
        > [!NOTE]
        > <span data-ttu-id="b5da9-119">In Linux e macOS la sottodirectory fa distinzione tra maiuscole e minuscole e deve:</span><span class="sxs-lookup"><span data-stu-id="b5da9-119">On Linux and macOS, the subdirectory is case-sensitive and must either:</span></span>
        >
        > - <span data-ttu-id="b5da9-120">Corrisponde esattamente al caso.</span><span class="sxs-lookup"><span data-stu-id="b5da9-120">Exactly match case.</span></span>
        > - <span data-ttu-id="b5da9-121">Essere in lettere minuscole.</span><span class="sxs-lookup"><span data-stu-id="b5da9-121">Be in lower case.</span></span>

    - <span data-ttu-id="b5da9-122">Se `active` è l' <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> istanza di, eseguendo la logica di [probe dell'assembly satellite (risorsa) predefinita](default-probing.md#satellite-resource-assembly-probing) .</span><span class="sxs-lookup"><span data-stu-id="b5da9-122">If `active` is the <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> instance, by running the [default satellite (resource) assembly probing](default-probing.md#satellite-resource-assembly-probing) logic.</span></span>

    - <span data-ttu-id="b5da9-123">Chiamata della <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> funzione.</span><span class="sxs-lookup"><span data-stu-id="b5da9-123">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> function.</span></span>

    - <span data-ttu-id="b5da9-124">Generazione dell' <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> evento.</span><span class="sxs-lookup"><span data-stu-id="b5da9-124">Raising the <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> event.</span></span>

    - <span data-ttu-id="b5da9-125">Generazione dell' <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento.</span><span class="sxs-lookup"><span data-stu-id="b5da9-125">Raising the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>

3. <span data-ttu-id="b5da9-126">Se viene caricato un assembly satellite:</span><span class="sxs-lookup"><span data-stu-id="b5da9-126">If a satellite assembly is loaded:</span></span>
   - <span data-ttu-id="b5da9-127">Viene generato l'evento <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b5da9-127">The <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType> event is raised.</span></span>
   - <span data-ttu-id="b5da9-128">Viene eseguita la ricerca dell'assembly per la risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="b5da9-128">The assembly is searched it for the requested resource.</span></span> <span data-ttu-id="b5da9-129">Se il runtime trova la risorsa nell'assembly, la utilizza.</span><span class="sxs-lookup"><span data-stu-id="b5da9-129">If the runtime finds the resource in the assembly, it uses it.</span></span> <span data-ttu-id="b5da9-130">In caso contrario la ricerca continua.</span><span class="sxs-lookup"><span data-stu-id="b5da9-130">If it doesn't find the resource, it continues the search.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b5da9-131">Per trovare una risorsa all'interno dell'assembly satellite, il runtime cerca il file di risorse richiesto da <xref:System.Resources.ResourceManager> per la proprietà <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> corrente.</span><span class="sxs-lookup"><span data-stu-id="b5da9-131">To find a resource within the satellite assembly, the runtime searches for the resource file requested by the <xref:System.Resources.ResourceManager> for the current <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b5da9-132">All'interno del file di risorse, Cerca il nome della risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="b5da9-132">Within the resource file, it searches for the requested resource name.</span></span> <span data-ttu-id="b5da9-133">Se uno dei due non viene trovato, la risorsa viene considerata come non trovata.</span><span class="sxs-lookup"><span data-stu-id="b5da9-133">If either is not found, the resource is treated as not found.</span></span>

4. <span data-ttu-id="b5da9-134">Il runtime cerca quindi gli assembly delle impostazioni cultura padre attraverso molti livelli potenziali, ogni volta che si ripetono i passaggi 2 & 3.</span><span class="sxs-lookup"><span data-stu-id="b5da9-134">The runtime next searches the parent culture assemblies through many potential levels, each time repeating steps 2 & 3.</span></span>

    <span data-ttu-id="b5da9-135">Ogni lingua dispone di un solo elemento padre, definito dalla <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b5da9-135">Each culture has only one parent, which is defined by the <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType> property.</span></span>

    <span data-ttu-id="b5da9-136">La ricerca di impostazioni cultura padre si interrompe quando la <xref:System.Globalization.CultureInfo.Parent%2A> proprietà di <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>una lingua è.</span><span class="sxs-lookup"><span data-stu-id="b5da9-136">The search for parent cultures stops when a culture's <xref:System.Globalization.CultureInfo.Parent%2A> property is <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>.</span></span>

    <span data-ttu-id="b5da9-137">Per il <xref:System.Globalization.CultureInfo.InvariantCulture>non tornare ai passaggi 2 & 3, ma continuare con il passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="b5da9-137">For the <xref:System.Globalization.CultureInfo.InvariantCulture>, we don't return to steps 2 & 3, but rather continue with step 5.</span></span>

5. <span data-ttu-id="b5da9-138">Se la risorsa non viene ancora trovata, viene utilizzata la risorsa per le impostazioni cultura predefinite (fallback).</span><span class="sxs-lookup"><span data-stu-id="b5da9-138">If the resource is still not found, the resource for the default (fallback) culture is used.</span></span>

   <span data-ttu-id="b5da9-139">In genere le risorse delle impostazioni cultura predefinite sono incluse nell'assembly principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b5da9-139">Typically, the resources for the default culture are included in the main application assembly.</span></span> <span data-ttu-id="b5da9-140">Tuttavia, è possibile specificare <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> per la <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b5da9-140">However, you can specify <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> for the <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="b5da9-141">Questo valore indica che il percorso di fallback finale per le risorse è un assembly satellite anziché l'assembly principale.</span><span class="sxs-lookup"><span data-stu-id="b5da9-141">This value indicates that the ultimate fallback location for resources is a satellite assembly rather than the main assembly.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b5da9-142">Le impostazioni cultura predefinite sono il fallback finale.</span><span class="sxs-lookup"><span data-stu-id="b5da9-142">The default culture is the ultimate fallback.</span></span> <span data-ttu-id="b5da9-143">È pertanto consigliabile includere sempre un set completo di risorse nel file di risorse predefinito.</span><span class="sxs-lookup"><span data-stu-id="b5da9-143">Therefore, we recommend that you always include an exhaustive set of resources in the default resource file.</span></span> <span data-ttu-id="b5da9-144">Ciò evita la generazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="b5da9-144">This helps prevent exceptions from being thrown.</span></span> <span data-ttu-id="b5da9-145">Se si dispone di un set esaustivo, si fornisce un fallback per tutte le risorse e si garantisce che almeno una risorsa sia sempre presente per l'utente, anche se non è specifica delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="b5da9-145">By having an exhaustive set, you provide a fallback for all resources and ensure that at least one resource is always present for the user, even if it is not culturally specific.</span></span>

6. <span data-ttu-id="b5da9-146">Infine</span><span class="sxs-lookup"><span data-stu-id="b5da9-146">Finally,</span></span>
   - <span data-ttu-id="b5da9-147">Se il runtime non trova un file di risorse per le impostazioni cultura predefinite (fallback) <xref:System.Resources.MissingManifestResourceException> , <xref:System.Resources.MissingSatelliteAssemblyException> viene generata un'eccezione o.</span><span class="sxs-lookup"><span data-stu-id="b5da9-147">If the runtime doesn't find a resource file for a default (fallback) culture, a <xref:System.Resources.MissingManifestResourceException> or <xref:System.Resources.MissingSatelliteAssemblyException> exception is thrown.</span></span>
   - <span data-ttu-id="b5da9-148">Se il file di risorse viene trovato ma la risorsa richiesta non è presente, la `null`richiesta restituisce.</span><span class="sxs-lookup"><span data-stu-id="b5da9-148">If the resource file is found but the requested resource isn't present, the request returns `null`.</span></span>
