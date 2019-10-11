---
title: Sondaggio predefinito-.NET Core
description: Panoramica della logica di Probe System. Runtime. loader. AssemblyLoadContext. default di .NET Core per individuare le dipendenze.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 500ee6ee863b1f311970a9e718936f57f7d4efd6
ms.sourcegitcommit: 10db6551ea3c971470cf5d2cc21ba1cbcefe5c55
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2019
ms.locfileid: "72031833"
---
# <a name="default-probing"></a>Sondaggio predefinito

L'istanza <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> è responsabile dell'individuazione delle dipendenze di un assembly. Questo articolo descrive la logica di probe dell'istanza di <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.

## <a name="host-configured-probing-properties"></a>Proprietà di probe configurate dall'host

Quando il runtime viene avviato, l'host di runtime fornisce un set di proprietà di sondaggio denominate che configurano i percorsi di probe <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.

Ogni proprietà di sondaggio è facoltativa. Se presente, ogni proprietà è un valore stringa che contiene un elenco delimitato di percorsi assoluti. Il delimitatore è ";" in Windows e ":" in tutte le altre piattaforme.

|Nome proprietà                 |Descrizione  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | Elenco di percorsi di file di assembly della piattaforma e dell'applicazione. |
|`PLATFORM_RESOURCE_ROOTS`       | Elenco di percorsi di directory in cui cercare gli assembly di risorse satellite. |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | Elenco di percorsi di directory in cui cercare le librerie non gestite (native).        |
|`APP_PATHS`                     | Elenco di percorsi di directory in cui cercare gli assembly gestiti. |
|`APP_NI_PATHS`                  | Elenco di percorsi di directory in cui cercare le immagini native degli assembly gestiti. |

### <a name="how-are-the-properties-populated"></a>Come vengono popolate le proprietà?

Esistono due scenari principali per il popolamento delle proprietà a seconda che esista il file *\<myapp >. Deps. JSON* .

- Quando è presente il file *@no__t 1. Deps. JSON* , viene analizzato per popolare le proprietà di probe.
- Quando il file *@no__t 1. Deps. JSON* non è presente, si presuppone che la directory dell'applicazione contenga tutte le dipendenze. Il contenuto della directory viene usato per popolare le proprietà di probe.

Inoltre, i file *@no__t 1. Deps. JSON* per tutti i Framework a cui si fa riferimento sono analizzati in modo analogo.

Infine, è possibile usare la variabile di ambiente `ADDITIONAL_DEPS` per aggiungere altre dipendenze.

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a>Ricerca per categorie visualizzare le proprietà del sondaggio dal codice gestito?

Ogni proprietà è disponibile chiamando la funzione <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> con il nome della proprietà della tabella precedente.

### <a name="how-do-i-debug-the-probing-properties-construction"></a>Ricerca per categorie eseguire il debug della costruzione delle proprietà di probe?

Quando sono abilitate determinate variabili di ambiente, l'host di runtime di .NET Core restituirà messaggi di traccia utili:

|Variabile di ambiente        |Descrizione  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |Abilita la traccia.|
|`COREHOST_TRACEFILE=<path>` |Traccia in un percorso di file anziché nel valore predefinito `stderr`.|
|`COREHOST_TRACE_VERBOSITY`  |Imposta il livello di dettaglio da 1 (più basso) a 4 (massimo).|

## <a name="managed-assembly-default-probing"></a>Sondaggio predefinito assembly gestito

Quando si esegue il probe per individuare un assembly gestito, il <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> Cerca nell'ordine seguente:

- File corrispondenti a <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` (dopo la rimozione delle estensioni di file).
- File di assembly di immagini native in `APP_NI_PATHS` con estensioni di file comuni.
- File di assembly in `APP_PATHS` con estensioni di file comuni.

## <a name="satellite-resource-assembly-probing"></a>Probe assembly satellite (risorsa)

Per trovare un assembly satellite per impostazioni cultura specifiche, costruire un set di percorsi di file.

Per ogni percorso in `PLATFORM_RESOURCE_ROOTS` e quindi `APP_PATHS`, aggiungere la stringa <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>, un separatore di directory, la stringa <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> e l'estensione ". dll".

Se esiste un file corrispondente, provare a caricarlo e restituirlo.

## <a name="unmanaged-native-library-probing"></a>Sondaggio della libreria non gestito (nativo)

Quando si esegue il probe per individuare una libreria non gestita, viene eseguita la ricerca di una libreria corrispondente nel `NATIVE_DLL_SEARCH_DIRECTORIES`.
