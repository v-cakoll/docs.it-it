---
title: Strutture di debug
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18bf03fee1a95c898e8273fa839e41a86b2d1c32
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828371"
---
# <a name="debugging-structures"></a>Strutture di debug
Questa sezione descrive le strutture non gestite usate dall'API di debug.

## <a name="in-this-section"></a>In questa sezione
 [Struttura CLRDATA_ADDRESS_RANGE](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) definisce un intervallo di indirizzi.

 [Struttura CLRDATA_IL_ADDRESS_MAP](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) definisce un livello di integrità per il mapping dell'indirizzo

 [Struttura CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) definisce la versione del prodotto di common language runtime (CLR) per scopi di debug.

 [CodeChunkInfo Structure1](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) rappresenta un singolo blocco di codice in memoria.

 [COR_ACTIVE_FUNCTION](cor-active-function-structure.md) contiene informazioni sulle funzioni attualmente attive nel frame di un thread.

 [Struttura COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) fornisce informazioni sul layout di un oggetto matrice in memoria.

 [COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) contiene gli offset utilizzati per eseguire il mapping di Microsoft intermediate language (MSIL) del codice in codice nativo.

 [COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) contiene le informazioni sugli offset per un intervallo di codice.

 [Struttura COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) fornisce informazioni su un campo in un oggetto.

 [Struttura COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) contiene informazioni su un oggetto che deve essere sottoposto a garbage collection.

 [Struttura COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) fornisce informazioni generali sull'heap di garbage collection, ad esempio se è enumerabile.

 [Struttura COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) fornisce informazioni su un oggetto nell'heap gestito.

 [COR_IL_MAP](cor-il-map-structure.md) specifica le modifiche nell'offset relativo di una funzione.

 [Struttura COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) contiene informazioni su un'area di memoria nell'heap gestito.

 [Struttura COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) contiene un identificatore di tipo.

 [Struttura COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) fornisce informazioni sul layout di un oggetto in memoria.

 [COR_VERSION](cor-version-structure.md) archivia il numero di versione in quattro parti standard di common language runtime.

 [Struttura CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) definisce un oggetto che blocca un thread e il motivo per cui il thread è bloccato.

 [Struttura CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) rappresenta una clausola di gestione (EH) eccezione per una determinata parte del linguaggio intermedio (IL).

 [Struttura CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) rappresenta le informazioni di frame da un oggetto eccezione dello stack.

 [Struttura CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) mappe una [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID per il corrispondente [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) oggetto.

 [Struttura DacpGetModuleAddress](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) definisce il contenitore per una richiesta del modulo di indirizzo.

 [Struttura DacpMethodDescData](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) definisce un buffer di trasporto per le informazioni di runtime del metodo.

 [Struttura DacpModuleData](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) definisce un buffer di trasporto per le informazioni di runtime del modulo.

 [Struttura DacpReJitData](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) definisce le informazioni di base per un determinato metodo instrumentato del profiler.

 [Struttura StackTrace_SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) fornisce un contesto semplice che può essere usato al posto di una procedura completa `CONTEXT` struttura.



## <a name="related-sections"></a>Sezioni correlate
 [Coclassi di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)

 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

 [Funzioni statiche globali di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)

 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
