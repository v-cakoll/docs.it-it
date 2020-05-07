---
title: Sondaggio predefinito-.NET Core
description: Panoramica della logica di Probe System. Runtime. loader. AssemblyLoadContext. default di .NET Core per individuare le dipendenze.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 1e347c716c2d739a1bd03be056b57fdbda6c678f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859520"
---
# <a name="default-probing"></a>Sondaggio predefinito

L' <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> istanza è responsabile dell'individuazione delle dipendenze di un assembly. Questo articolo descrive la <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> logica di probe dell'istanza.

## <a name="host-configured-probing-properties"></a>Proprietà di probe configurate dall'host

Quando il runtime viene avviato, l'host di runtime fornisce un set di proprietà di sondaggio denominate che configurano <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> i percorsi di probe.

Ogni proprietà di sondaggio è facoltativa. Se presente, ogni proprietà è un valore stringa che contiene un elenco delimitato di percorsi assoluti. Il delimitatore è ";" in Windows e ":" in tutte le altre piattaforme.

|Nome proprietà                 |Descrizione  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | Elenco di percorsi di file di assembly della piattaforma e dell'applicazione. |
|`PLATFORM_RESOURCE_ROOTS`       | Elenco di percorsi di directory in cui cercare gli assembly di risorse satellite. |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | Elenco di percorsi di directory in cui cercare le librerie non gestite (native).        |
|`APP_PATHS`                     | Elenco di percorsi di directory in cui cercare gli assembly gestiti. |
|`APP_NI_PATHS`                  | Elenco di percorsi di directory in cui cercare le immagini native degli assembly gestiti. |

### <a name="how-are-the-properties-populated"></a>Come vengono popolate le proprietà?

Esistono due scenari principali per il popolamento delle proprietà a seconda che esista il * \<file MyApp>. Deps. JSON* .

- Quando il * \*file. Deps. JSON* è presente, viene analizzato per popolare le proprietà di probe.
- Quando il * \*file. Deps. JSON* non è presente, si presuppone che la directory dell'applicazione contenga tutte le dipendenze. Il contenuto della directory viene usato per popolare le proprietà di probe.

Inoltre, i * \*file con estensione Deps. JSON* per tutti i Framework a cui viene fatto riferimento vengono analizzati in modo analogo.

Infine, è possibile `ADDITIONAL_DEPS` usare la variabile di ambiente per aggiungere altre dipendenze.

Per `APP_PATHS` impostazione `APP_NI_PATHS` predefinita, le proprietà e non vengono popolate e vengono omesse per la maggior parte delle applicazioni.

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a>Ricerca per categorie visualizzare le proprietà del sondaggio dal codice gestito?

Ogni proprietà è disponibile chiamando la <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> funzione con il nome della proprietà della tabella precedente.

### <a name="how-do-i-debug-the-probing-properties-construction"></a>Ricerca per categorie eseguire il debug della costruzione delle proprietà di probe?

Quando sono abilitate determinate variabili di ambiente, l'host di runtime di .NET Core restituirà messaggi di traccia utili:

|Variabile di ambiente        |Descrizione  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |Abilita la traccia.|
|`COREHOST_TRACEFILE=<path>` |Traccia in un percorso di file anziché in quello `stderr`predefinito.|
|`COREHOST_TRACE_VERBOSITY`  |Imposta il livello di dettaglio da 1 (più basso) a 4 (massimo).|

## <a name="managed-assembly-default-probing"></a>Sondaggio predefinito assembly gestito

Quando si esegue il probe per individuare un assembly <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> gestito, il Cerca nell'ordine seguente:

- File corrispondenti a <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` (dopo la rimozione di estensioni di file).
- File di assembly di immagini `APP_NI_PATHS` native in con estensioni di file comuni.
- File di assembly `APP_PATHS` in con estensioni di file comuni.

## <a name="satellite-resource-assembly-probing"></a>Probe assembly satellite (risorsa)

Per trovare un assembly satellite per impostazioni cultura specifiche, costruire un set di percorsi di file.

Per ogni percorso in `PLATFORM_RESOURCE_ROOTS` e quindi `APP_PATHS`aggiungere la <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> stringa, un separatore di directory, <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> la stringa e l'estensione ". dll".

Se esiste un file corrispondente, provare a caricarlo e restituirlo.

## <a name="unmanaged-native-library-probing"></a>Sondaggio della libreria non gestito (nativo)

Quando si esegue il probe per individuare una libreria non gestita `NATIVE_DLL_SEARCH_DIRECTORIES` , viene eseguita la ricerca di una libreria corrispondente.
