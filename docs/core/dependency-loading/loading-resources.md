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
# <a name="satellite-assembly-loading-algorithm"></a>Algoritmo di caricamento dell'assembly satellitare

Gli assembly satellite vengono utilizzati per archiviare le risorse localizzate personalizzate per la lingua e le impostazioni cultura.

Gli assembly satellite utilizzano un algoritmo di caricamento diverso rispetto agli assembly gestiti generali.

## <a name="when-are-satellite-assemblies-loaded"></a>Quando vengono caricati gli assembly satellite?

Gli assembly satellite vengono caricati durante il caricamento di una risorsa localizzata.

L'API di base per <xref:System.Resources.ResourceManager?displayProperty=fullName> caricare le risorse localizzate è la classe. In definitiva <xref:System.Resources.ResourceManager> la classe <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> chiamerà <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>il metodo per ogni oggetto .

Le API di livello superiore possono astrarre l'API di basso livello.

## <a name="algorithm"></a>Algoritmo

Il processo di fallback per le risorse di .NET Core include i passaggi seguenti:

1. Determinare `active` <xref:System.Runtime.Loader.AssemblyLoadContext> l'istanza. In tutti i `active` casi, l'istanza <xref:System.Runtime.Loader.AssemblyLoadContext>è l'assembly in esecuzione.

2. L'istanza `active` tenta di caricare un assembly satellite per le impostazioni cultura richieste in ordine di priorità:The instance attempts to load a satellite assembly for the requested culture in priority order by:
    - Controllo della cache.
    - Verifica della directory dell'assembly attualmente in esecuzione per <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> una `es-MX`sottodirectory che corrisponde alla richiesta (ad esempio ).

        > [!NOTE]
        > Questa funzionalità non è stata implementata in .NET Core prima della 3.0.
        >
        > [!NOTE]
        > In Linux e macOS, la sottodirectory fa distinzione tra maiuscole e minuscole e deve:
        > - Esattamente caso di corrispondenza.
        > - Essere in minuscolo.

    - Se `active` è <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> l'istanza, eseguendo la logica di [probe dell'assembly satellite (risorsa) predefinita.](default-probing.md#satellite-resource-assembly-probing)

    - Chiamata <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> della funzione.

    - Generazione <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> dell'evento.

    - Generazione <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> dell'evento.

3. Se viene caricato un assembly satellite:
   - Viene generato l'evento <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType>.
   - All'assembly viene cercata la risorsa richiesta. Se il runtime trova la risorsa nell'assembly, la utilizza. In caso contrario la ricerca continua.

    > [!NOTE]
    > Per trovare una risorsa all'interno dell'assembly satellite, il runtime cerca il file di risorse richiesto da <xref:System.Resources.ResourceManager> per la proprietà <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> corrente. All'interno del file di risorse, cerca il nome della risorsa richiesta. Se uno dei due non viene trovato, la risorsa viene considerata come non trovata.

4. Il runtime cerca quindi gli assembly delle impostazioni cultura padre attraverso molti livelli potenziali, ripetendo ogni volta i passaggi 2 & 3.

    Ogni lingua ha un solo elemento <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType> padre, definito dalla proprietà .

    La ricerca delle impostazioni cultura padre <xref:System.Globalization.CultureInfo.Parent%2A> viene <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>interrotta quando la proprietà di un'applicazione delle impostazioni cultura è .

    Per <xref:System.Globalization.CultureInfo.InvariantCulture>il , non torniamo ai passaggi 2 & 3, ma si continua con il passaggio 5.

5. Se la risorsa non viene ancora trovata, viene utilizzata la risorsa per le impostazioni cultura predefinite (fallback).

   In genere le risorse delle impostazioni cultura predefinite sono incluse nell'assembly principale dell'applicazione. Tuttavia, è <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> possibile <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType> specificare per la proprietà. Questo valore indica che il percorso di fallback finale per le risorse è un assembly satellite anziché l'assembly principale.

    > [!NOTE]
    > Le impostazioni cultura predefinite sono il fallback finale. Pertanto, è consigliabile includere sempre un set completo di risorse nel file di risorse predefinito. Ciò evita la generazione di eccezioni. Con un set completo, si fornisce un fallback per tutte le risorse e si garantisce che almeno una risorsa sia sempre presente per l'utente, anche se non è specifica delle impostazioni cultura.

6. Infine
   - Se il runtime non trova un file di risorse per <xref:System.Resources.MissingManifestResourceException> <xref:System.Resources.MissingSatelliteAssemblyException> le impostazioni cultura predefinite (fallback), viene generata un'eccezione o .
   - Se il file di risorse viene trovato ma la `null`risorsa richiesta non è presente, la richiesta restituisce .
