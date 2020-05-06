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
# <a name="satellite-assembly-loading-algorithm"></a>Algoritmo di caricamento degli assembly satellite

Gli assembly satellite vengono usati per archiviare le risorse localizzate personalizzate per la lingua e le impostazioni cultura.

Gli assembly satellite usano un algoritmo di caricamento diverso rispetto agli assembly gestiti generali.

## <a name="when-are-satellite-assemblies-loaded"></a>Quando vengono caricati gli assembly satellite?

Gli assembly satellite vengono caricati durante il caricamento di una risorsa localizzata.

L'API di base per caricare le risorse localizzate è la <xref:System.Resources.ResourceManager?displayProperty=fullName> classe. Infine, la <xref:System.Resources.ResourceManager> classe chiamerà il <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> metodo per ogni <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.

Le API di livello superiore possono astrarre l'API di basso livello.

## <a name="algorithm"></a>Algoritmo

Il processo di fallback per le risorse di .NET Core include i passaggi seguenti:

1. Determinare l' `active` <xref:System.Runtime.Loader.AssemblyLoadContext> istanza. In tutti i casi, `active` l'istanza è l'assembly in esecuzione <xref:System.Runtime.Loader.AssemblyLoadContext>.

2. L' `active` istanza tenta di caricare un assembly satellite per le impostazioni cultura richieste in ordine di priorità:
    - Verifica della cache.
    - Verifica della directory dell'assembly attualmente in esecuzione per una sottodirectory che corrisponde alla richiesta <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> (ad esempio `es-MX`).

        > [!NOTE]
        > Questa funzionalità non è stata implementata in .NET Core prima del 3,0.
        >
        > [!NOTE]
        > In Linux e macOS la sottodirectory fa distinzione tra maiuscole e minuscole e deve:
        >
        > - Corrisponde esattamente al caso.
        > - Essere in lettere minuscole.

    - Se `active` è l' <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> istanza di, eseguendo la logica di [probe dell'assembly satellite (risorsa) predefinita](default-probing.md#satellite-resource-assembly-probing) .

    - Chiamata della <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> funzione.

    - Generazione dell' <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> evento.

    - Generazione dell' <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento.

3. Se viene caricato un assembly satellite:
   - Viene generato l'evento <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType>.
   - Viene eseguita la ricerca dell'assembly per la risorsa richiesta. Se il runtime trova la risorsa nell'assembly, la utilizza. In caso contrario la ricerca continua.

    > [!NOTE]
    > Per trovare una risorsa all'interno dell'assembly satellite, il runtime cerca il file di risorse richiesto da <xref:System.Resources.ResourceManager> per la proprietà <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> corrente. All'interno del file di risorse, Cerca il nome della risorsa richiesta. Se uno dei due non viene trovato, la risorsa viene considerata come non trovata.

4. Il runtime cerca quindi gli assembly delle impostazioni cultura padre attraverso molti livelli potenziali, ogni volta che si ripetono i passaggi 2 & 3.

    Ogni lingua dispone di un solo elemento padre, definito dalla <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType> proprietà.

    La ricerca di impostazioni cultura padre si interrompe quando la <xref:System.Globalization.CultureInfo.Parent%2A> proprietà di <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>una lingua è.

    Per il <xref:System.Globalization.CultureInfo.InvariantCulture>non tornare ai passaggi 2 & 3, ma continuare con il passaggio 5.

5. Se la risorsa non viene ancora trovata, viene utilizzata la risorsa per le impostazioni cultura predefinite (fallback).

   In genere le risorse delle impostazioni cultura predefinite sono incluse nell'assembly principale dell'applicazione. Tuttavia, è possibile specificare <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> per la <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType> proprietà. Questo valore indica che il percorso di fallback finale per le risorse è un assembly satellite anziché l'assembly principale.

    > [!NOTE]
    > Le impostazioni cultura predefinite sono il fallback finale. È pertanto consigliabile includere sempre un set completo di risorse nel file di risorse predefinito. Ciò evita la generazione di eccezioni. Se si dispone di un set esaustivo, si fornisce un fallback per tutte le risorse e si garantisce che almeno una risorsa sia sempre presente per l'utente, anche se non è specifica delle impostazioni cultura.

6. Infine
   - Se il runtime non trova un file di risorse per le impostazioni cultura predefinite (fallback) <xref:System.Resources.MissingManifestResourceException> , <xref:System.Resources.MissingSatelliteAssemblyException> viene generata un'eccezione o.
   - Se il file di risorse viene trovato ma la risorsa richiesta non è presente, la `null`richiesta restituisce.
