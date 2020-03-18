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
# <a name="default-probing"></a>Sondaggio predefinito

L'istanza <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> è responsabile dell'individuazione delle dipendenze di un assembly. In questo articolo <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> viene descritta la logica di probe dell'istanza.

## <a name="host-configured-probing-properties"></a>Proprietà di sondaggio configurate dall'host

Quando il runtime viene avviato, l'host di runtime <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> fornisce un set di proprietà di probe denominate che configurano i percorsi probe.

Ogni proprietà di sondaggio è facoltativa. Se presente, ogni proprietà è un valore stringa che contiene un elenco delimitato di percorsi assoluti. Il delimitatore è ';' in Windows e ':' su tutte le altre piattaforme.

|Nome proprietà                 |Descrizione  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | Elenco dei percorsi dei file di assembly della piattaforma e dell'applicazione. |
|`PLATFORM_RESOURCE_ROOTS`       | Elenco dei percorsi di directory per la ricerca di assembly di risorse satellite. |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | Elenco dei percorsi di directory per la ricerca di librerie non gestite (native).        |
|`APP_PATHS`                     | Elenco dei percorsi di directory per la ricerca di assembly gestiti. |
|`APP_NI_PATHS`                  | Elenco dei percorsi di directory per la ricerca di immagini native di assembly gestiti. |

### <a name="how-are-the-properties-populated"></a>Come vengono popolate le proprietà?

Esistono due scenari principali per popolare le proprietà a seconda che il file * \<>.deps.json esista* o meno.

- Quando il * \*file .deps.json* è presente, viene analizzato per popolare le proprietà di sondaggio.
- Quando il * \*file .deps.json* non è presente, si presuppone che la directory dell'applicazione contenga tutte le dipendenze. Il contenuto della directory viene utilizzato per popolare le proprietà di sondaggio.

Inoltre, i * \*file .deps.json* per tutti i framework a cui si fa riferimento vengono analizzati in modo analogo.

Infine la `ADDITIONAL_DEPS` variabile di ambiente può essere utilizzata per aggiungere ulteriori dipendenze.

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a>Come si visualizzano le proprietà di sondaggio dal codice gestito?

Ogni proprietà è disponibile <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> chiamando la funzione con il nome della proprietà dalla tabella precedente.

### <a name="how-do-i-debug-the-probing-properties-construction"></a>Come si esegue il debug della costruzione delle proprietà di sondaggio?

L'host di runtime .NET Core emetterà messaggi di traccia utili quando sono abilitate determinate variabili di ambiente:The .NET Core runtime host will output useful trace messages when certain environment variables are enabled:

|Variabile di ambiente        |Descrizione  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |Abilita la traccia.|
|`COREHOST_TRACEFILE=<path>` |Traccia in un percorso di `stderr`file anziché nell'impostazione predefinita.|
|`COREHOST_TRACE_VERBOSITY`  |Imposta il livello di dettaglio da 1 (più basso) a 4 (più alto).|

## <a name="managed-assembly-default-probing"></a>Sondaggio predefinito dell'assembly gestito

Quando si esegue il probe <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> per individuare un assembly gestito, l'aspetto viene esaminato in ordine:

- File corrispondenti `TRUSTED_PLATFORM_ASSEMBLIES` all'in <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> (dopo la rimozione delle estensioni di file).
- File di assembly `APP_NI_PATHS` di immagini native con estensioni di file comuni.
- File di `APP_PATHS` assembly con estensioni di file comuni.

## <a name="satellite-resource-assembly-probing"></a>Sondaggio dell'assembly satellite (risorsa)

Per trovare un assembly satellite per impostazioni cultura specifiche, creare un set di percorsi di file.

Per ogni `PLATFORM_RESOURCE_ROOTS` percorso `APP_PATHS`in and <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> then , aggiungere <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> la stringa, un separatore di directory, la stringa e l'estensione '.dll'.

Se esiste un file corrispondente, provare a caricarlo e restituirlo.

## <a name="unmanaged-native-library-probing"></a>Sondaggio della libreria non gestita (nativa)Unmanaged (native) library probing

Durante il probe per individuare una `NATIVE_DLL_SEARCH_DIRECTORIES` libreria non gestita, viene cercato una libreria corrispondente.
